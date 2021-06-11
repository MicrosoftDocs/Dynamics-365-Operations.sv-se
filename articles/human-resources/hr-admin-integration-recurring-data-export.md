---
title: Skapa en app för återkommande dataexport
description: I den här artikeln beskrivs hur du skapar en Microsoft Azure logisk app som exporterar data från Microsoft Dynamics 365 Human Resources på ett återkommande schema.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: a4a963bcfe5932f5642b43751ccd96c472fec0d9
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/18/2021
ms.locfileid: "6055014"
---
# <a name="create-a-recurring-data-export-app"></a><span data-ttu-id="e1b29-103">Skapa en app för återkommande dataexport</span><span class="sxs-lookup"><span data-stu-id="e1b29-103">Create a recurring data export app</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="e1b29-104">I den här artikeln beskrivs hur du skapar en Microsoft Azure logisk app som exporterar data från Microsoft Dynamics 365 Human Resources på ett återkommande schema.</span><span class="sxs-lookup"><span data-stu-id="e1b29-104">This article shows how to create a Microsoft Azure logic app that exports data from Microsoft Dynamics 365 Human Resources on a recurring schedule.</span></span> <span data-ttu-id="e1b29-105">Självstudierna drar fördel av personalens DMF-paket REST API (Application Programming Interface) för att exportera data.</span><span class="sxs-lookup"><span data-stu-id="e1b29-105">The tutorial takes advantage of Human Resources' DMF package REST application programming interface (API) to export the data.</span></span> <span data-ttu-id="e1b29-106">När data har exporterats sparar logikprogrammet det exporterade datapaketet i en Microsoft OneDrive för företag-mapp.</span><span class="sxs-lookup"><span data-stu-id="e1b29-106">After the data has been exported, the logic app saves the exported data package to a Microsoft OneDrive for Business folder.</span></span>

## <a name="business-scenario"></a><span data-ttu-id="e1b29-107">Affärsscenario</span><span class="sxs-lookup"><span data-stu-id="e1b29-107">Business scenario</span></span>

<span data-ttu-id="e1b29-108">I ett typiskt affärsscenario för Microsoft Dynamics 365-integrationer måste data exporteras till ett underordnat system i ett återkommande schema.</span><span class="sxs-lookup"><span data-stu-id="e1b29-108">In one typical business scenario for Microsoft Dynamics 365 integrations, data must be exported to a downstream system on a recurring schedule.</span></span> <span data-ttu-id="e1b29-109">I den här självstudien visas hur du exporterar alla Microsoft Dynamics 365 Human Resources och spara listan över arbetare i OneDrive för företag-mapp.</span><span class="sxs-lookup"><span data-stu-id="e1b29-109">This tutorial shows how to export all worker records from Microsoft Dynamics 365 Human Resources and save the list of workers in a OneDrive for Business folder.</span></span>

> [!TIP]
> <span data-ttu-id="e1b29-110">De specifika data som exporteras i den här självstudien och de exporterade data är bara exempel.</span><span class="sxs-lookup"><span data-stu-id="e1b29-110">The specific data that is exported in this tutorial and the destination of the exported data are only examples.</span></span> <span data-ttu-id="e1b29-111">Du kan enkelt ändra dem för att uppfylla affärskrav.</span><span class="sxs-lookup"><span data-stu-id="e1b29-111">You can easily change them to meet your business needs.</span></span>

## <a name="technologies-used"></a><span data-ttu-id="e1b29-112">Tekniker som används</span><span class="sxs-lookup"><span data-stu-id="e1b29-112">Technologies used</span></span>

<span data-ttu-id="e1b29-113">I den här självstudien används följande tekniker:</span><span class="sxs-lookup"><span data-stu-id="e1b29-113">This tutorial uses the following technologies:</span></span>

- <span data-ttu-id="e1b29-114">**[Dynamics 365 Human Resources](https://dynamics.microsoft.com/talent/overview/)**– Huvuddatakällan för arbetare som ska exporteras.</span><span class="sxs-lookup"><span data-stu-id="e1b29-114">**[Dynamics 365 Human Resources](https://dynamics.microsoft.com/talent/overview/)** – The master data source for workers that will be exported.</span></span>
- <span data-ttu-id="e1b29-115">**[Azure Logic Apps](https://azure.microsoft.com/services/logic-apps/)** – tekniken som tillhandahåller dirigering och schemaläggning av den återkommande exporten.</span><span class="sxs-lookup"><span data-stu-id="e1b29-115">**[Azure Logic Apps](https://azure.microsoft.com/services/logic-apps/)** – The technology that provides orchestration and scheduling of the recurring export.</span></span>

    - <span data-ttu-id="e1b29-116">**[Kopplingar](/azure/connectors/apis-list)** – tekniken som används för att ansluta logikappen till de obligatoriska slutpunkterna.</span><span class="sxs-lookup"><span data-stu-id="e1b29-116">**[Connectors](/azure/connectors/apis-list)** – The technology that is used to connect the logic app to the required endpoints.</span></span>

        - <span data-ttu-id="e1b29-117">[HTTP med Azure AD](/connectors/webcontents/)koppling</span><span class="sxs-lookup"><span data-stu-id="e1b29-117">[HTTP with Azure AD](/connectors/webcontents/) connector</span></span>
        - <span data-ttu-id="e1b29-118">[OneDrive för företag](/azure/connectors/connectors-create-api-onedriveforbusiness) koppling</span><span class="sxs-lookup"><span data-stu-id="e1b29-118">[OneDrive for Business](/azure/connectors/connectors-create-api-onedriveforbusiness) connector</span></span>

- <span data-ttu-id="e1b29-119">**[DMF-paket REST API](../fin-ops-core/dev-itpro/data-entities/data-management-api.md)** – den teknik som används för att utlösa exporten och övervakningen av dess förlopp.</span><span class="sxs-lookup"><span data-stu-id="e1b29-119">**[DMF package REST API](../fin-ops-core/dev-itpro/data-entities/data-management-api.md)** – The technology that is used to trigger the export and monitor its progress.</span></span>
- <span data-ttu-id="e1b29-120">**[OneDrive för företag](https://onedrive.live.com/about/business/)** – målet för de exporterade arbetarna.</span><span class="sxs-lookup"><span data-stu-id="e1b29-120">**[OneDrive for Business](https://onedrive.live.com/about/business/)** – The destination for the exported workers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e1b29-121">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="e1b29-121">Prerequisites</span></span>

<span data-ttu-id="e1b29-122">Innan du börjar övningen i den här självstudien måste du ha följande artiklar:</span><span class="sxs-lookup"><span data-stu-id="e1b29-122">Before you begin the exercise in this tutorial, you must have the following items:</span></span>

- <span data-ttu-id="e1b29-123">En personalmiljö med behörigheter på administratörsnivå i miljön</span><span class="sxs-lookup"><span data-stu-id="e1b29-123">A Human Resources environment that has admin-level permissions in the environment</span></span>
- <span data-ttu-id="e1b29-124">En [Azure-prenumeration](https://azure.microsoft.com/free/) som ska vara värd för logikappen</span><span class="sxs-lookup"><span data-stu-id="e1b29-124">An [Azure subscription](https://azure.microsoft.com/free/) to host the logic app</span></span>

## <a name="the-exercise"></a><span data-ttu-id="e1b29-125">Övningen</span><span class="sxs-lookup"><span data-stu-id="e1b29-125">The exercise</span></span>

<span data-ttu-id="e1b29-126">I slutet av övningen har du en logiskapp som är ansluten till personalmiljön och ditt OneDrive för företag-konto.</span><span class="sxs-lookup"><span data-stu-id="e1b29-126">At the end of this exercise, you will have a logic app that is connected to your Human Resources environment and your OneDrive for Business account.</span></span> <span data-ttu-id="e1b29-127">Logikappen exporterar ett datapaket från personal, väntar på att exporten ska slutföras, hämta det exporterade datapaketet och sparar datapaketet i den OneDrive för företag-mapp som du har angett.</span><span class="sxs-lookup"><span data-stu-id="e1b29-127">The logic app will export a data package from Human Resources, wait for the export to be completed, download the exported data package, and save the data package in the OneDrive for Business folder that you specified.</span></span>

<span data-ttu-id="e1b29-128">Den slutförda logikappen kommer att likna följande bild.</span><span class="sxs-lookup"><span data-stu-id="e1b29-128">The completed logic app will resemble the following illustration.</span></span>

![Översikt över logikappar](media/integration-logic-app-overview.png)

### <a name="step-1-create-a-data-export-project-in-human-resources"></a><span data-ttu-id="e1b29-130">Steg 1: skapa ett projekt för dataexport i personal</span><span class="sxs-lookup"><span data-stu-id="e1b29-130">Step 1: Create a data export project in Human Resources</span></span>

<span data-ttu-id="e1b29-131">Skapa ett dataexportprojekt i personal som exporterar arbetare.</span><span class="sxs-lookup"><span data-stu-id="e1b29-131">In Human Resources, create a data export project that exports workers.</span></span> <span data-ttu-id="e1b29-132">Namnge projektets **exportarbetare** och se till att alternativet **Generera datapaket** är inställt på **ja**.</span><span class="sxs-lookup"><span data-stu-id="e1b29-132">Name the project **Export Workers**, and make sure that the **Generate data package** option is set to **Yes**.</span></span> <span data-ttu-id="e1b29-133">Lägg till en enskild enhet **(** arbetare) i projektet och välj det format du vill exportera i.</span><span class="sxs-lookup"><span data-stu-id="e1b29-133">Add a single entity (**Worker**) to the project, and select the format to export in.</span></span> <span data-ttu-id="e1b29-134">(Microsoft Excel-formatet används i den här självstudien.)</span><span class="sxs-lookup"><span data-stu-id="e1b29-134">(Microsoft Excel format is used in this tutorial.)</span></span>

![Exportera dataprojekt för medarbetare](media/integration-logic-app-export-workers-project.png)

> [!IMPORTANT]
> <span data-ttu-id="e1b29-136">Kom ihåg namnet på dataexportprojektet.</span><span class="sxs-lookup"><span data-stu-id="e1b29-136">Remember the name of the data export project.</span></span> <span data-ttu-id="e1b29-137">Du kommer att behöva det när du skapar logikappen i nästa steg.</span><span class="sxs-lookup"><span data-stu-id="e1b29-137">You will need it when you create the logic app in the next step.</span></span>

### <a name="step-2-create-the-logic-app"></a><span data-ttu-id="e1b29-138">Steg 2: skapa logikappen</span><span class="sxs-lookup"><span data-stu-id="e1b29-138">Step 2: Create the logic app</span></span>

<span data-ttu-id="e1b29-139">Den stora delen av övningen innebär att skapa logikappen.</span><span class="sxs-lookup"><span data-stu-id="e1b29-139">The bulk of the exercise involves creating the logic app.</span></span>

1. <span data-ttu-id="e1b29-140">Skapa en logikapp i Azure-portalen.</span><span class="sxs-lookup"><span data-stu-id="e1b29-140">In the Azure portal, create a logic app.</span></span>

    ![Sidan för att skapa logikapp](media/integration-logic-app-creation-1.png)

2. <span data-ttu-id="e1b29-142">Starta med en tom logikapp i modulen Logic Apps Designer.</span><span class="sxs-lookup"><span data-stu-id="e1b29-142">In the Logic Apps Designer, start with a blank logic app.</span></span>
3. <span data-ttu-id="e1b29-143">Lägg till en [utlösare för upprepningsschema](/azure/connectors/connectors-native-recurrence) om du vill köra logikappen var 24:e timme (eller enligt ett schema som du väljer).</span><span class="sxs-lookup"><span data-stu-id="e1b29-143">Add a [Recurrence Schedule trigger](/azure/connectors/connectors-native-recurrence) to run the logic app every 24 hours (or according to a schedule of your choice).</span></span>

    ![Dialogrutan Upprepning](media/integration-logic-app-recurrence-step.png)

4. <span data-ttu-id="e1b29-145">Anropa [ExportToPackage](../fin-ops-core/dev-itpro/data-entities/data-management-api.md#exporttopackage) DMF REST API för att schemalägga exporten av ditt datapaket.</span><span class="sxs-lookup"><span data-stu-id="e1b29-145">Call the [ExportToPackage](../fin-ops-core/dev-itpro/data-entities/data-management-api.md#exporttopackage) DMF REST API to schedule the export of your data package.</span></span>

    1. <span data-ttu-id="e1b29-146">Använd åtgärden **anropa en HTTP-begäran** från HTTP med Azure AD-koppling.</span><span class="sxs-lookup"><span data-stu-id="e1b29-146">Use the **Invoke an HTTP request** action from the HTTP with Azure AD connector.</span></span>

        - <span data-ttu-id="e1b29-147">**Grundläggande resurs-URL** : URL för din personalmiljö (inkluderar inte information om sökväg/namnområde.)</span><span class="sxs-lookup"><span data-stu-id="e1b29-147">**Base Resource URL:** The URL of your Human Resources environment (Don't include path/namespace information.)</span></span>
        - <span data-ttu-id="e1b29-148">**Azure AD resurs-URI:** `http://hr.talent.dynamics.com`</span><span class="sxs-lookup"><span data-stu-id="e1b29-148">**Azure AD Resource URI:** `http://hr.talent.dynamics.com`</span></span>

        > [!NOTE]
        > <span data-ttu-id="e1b29-149">Personaltjänsten tillhandahåller inte ännu en anslutning som visar alla API:er som utgör DMF-paketets REST API, t.ex. **ExportToPackage**.</span><span class="sxs-lookup"><span data-stu-id="e1b29-149">The Human Resources service doesn't yet provide a connector that exposes all the APIs that make up the DMF package REST API, such as **ExportToPackage**.</span></span> <span data-ttu-id="e1b29-150">I stället måste du anropa API:erna genom att använda råa HTTPS-begäran via HTTP med Azure AD-kopplingen.</span><span class="sxs-lookup"><span data-stu-id="e1b29-150">Instead, you must call the APIs by using raw HTTPS requests through the HTTP with Azure AD connector.</span></span> <span data-ttu-id="e1b29-151">Den här kopplingen använder Azure Active Directory (Azure AD) för autentisering och auktorisering till personal.</span><span class="sxs-lookup"><span data-stu-id="e1b29-151">This connector uses Azure Active Directory (Azure AD) for authentication and authorization to Human Resources.</span></span>

        ![HTTP med Azure AD-koppling](media/integration-logic-app-http-aad-connector-step.png)

    2. <span data-ttu-id="e1b29-153">Logga in på din personalmiljön via HTTP med Azure AD-koppling.</span><span class="sxs-lookup"><span data-stu-id="e1b29-153">Sign in to your Human Resources environment through the HTTP with Azure AD connector.</span></span>
    3. <span data-ttu-id="e1b29-154">Ställ in en HTTP **POST**-begäran för att anropa **ExportToPackage** DMF REST API.</span><span class="sxs-lookup"><span data-stu-id="e1b29-154">Set up an HTTP **POST** request to call the **ExportToPackage** DMF REST API.</span></span>

        - <span data-ttu-id="e1b29-155">**Metod:** POST</span><span class="sxs-lookup"><span data-stu-id="e1b29-155">**Method:** POST</span></span>
        - <span data-ttu-id="e1b29-156">**Url för begäran:** https://\<hostname\>/namespaces/\<namespace\_guid\>/data/DataManagementDefinitionGroups/Microsoft.Dynamics.DataEntities.ExportToPackage</span><span class="sxs-lookup"><span data-stu-id="e1b29-156">**Url of the request:** https://\<hostname\>/namespaces/\<namespace\_guid\>/data/DataManagementDefinitionGroups/Microsoft.Dynamics.DataEntities.ExportToPackage</span></span>
        - <span data-ttu-id="e1b29-157">**Huvudtext av begäran:**</span><span class="sxs-lookup"><span data-stu-id="e1b29-157">**Body of the request:**</span></span>

            ```JSON
            {
                "definitionGroupId":"Export Workers",
                "packageName":"talent_package.zip",
                "executionId":"",
                "reExecute":false,
                "legalEntityId":"USMF"
            }
            ```

        ![Åtgärden anropa en HTTP-begäran](media/integration-logic-app-export-to-package-step.png)

    > [!TIP]
    > <span data-ttu-id="e1b29-159">Du kanske vill byta namn på varje steg så att det blir mer meningsfullt än standardnamnet **Anropa en HTTP-begäran**.</span><span class="sxs-lookup"><span data-stu-id="e1b29-159">You might want to rename each step so that it's more meaningful than the default name, **Invoke an HTTP request**.</span></span> <span data-ttu-id="e1b29-160">Du kan till exempel byta namn på det här steget **ExportToPackage**.</span><span class="sxs-lookup"><span data-stu-id="e1b29-160">For example, you can rename this step **ExportToPackage**.</span></span>

5. <span data-ttu-id="e1b29-161">[Initiera en variabel](/azure/logic-apps/logic-apps-create-variables-store-values#initialize-variable) för att lagra körningsstatusen för **ExportToPackage**-begäran.</span><span class="sxs-lookup"><span data-stu-id="e1b29-161">[Initialize a variable](/azure/logic-apps/logic-apps-create-variables-store-values#initialize-variable) to store the execution status of the **ExportToPackage** request.</span></span>

    ![Åtgärden Initiera variabel](media/integration-logic-app-initialize-variable-step.png)

6. <span data-ttu-id="e1b29-163">Vänta tills körningsstatusen för dataexporten har **slutförts**.</span><span class="sxs-lookup"><span data-stu-id="e1b29-163">Wait until the execution status of the data export is **Succeeded**.</span></span>

    1. <span data-ttu-id="e1b29-164">Lägg till en [Till slinga](/azure/logic-apps/logic-apps-control-flow-loops#until-loop) som upprepas tills värdet av **ExecutionStatus**-variabeln är **slutförd**.</span><span class="sxs-lookup"><span data-stu-id="e1b29-164">Add an [Until loop](/azure/logic-apps/logic-apps-control-flow-loops#until-loop) that repeats until the value of the **ExecutionStatus** variable is **Succeeded**.</span></span>
    2. <span data-ttu-id="e1b29-165">Lägg till åtgärden **fördröjning** som väntar fem sekunder innan den avsöker den aktuella körningsstatusen för exporten.</span><span class="sxs-lookup"><span data-stu-id="e1b29-165">Add a **Delay** action that waits five seconds before it polls for the current execution status of the export.</span></span>

        ![Fram till slinga-behållare](media/integration-logic-app-until-loop-step.png)

        > [!NOTE]
        > <span data-ttu-id="e1b29-167">Ställ in gränsvärdet till **15** om du vill vänta i högst 75 sekunder (15 iterationer × 5 sekunder) för att exporten ska kunna slutföras.</span><span class="sxs-lookup"><span data-stu-id="e1b29-167">Set the limit count to **15** to wait a maximum of 75 seconds (15 iterations × 5 seconds) for the export to be completed.</span></span> <span data-ttu-id="e1b29-168">Om exporten tar längre tid, kan du justera antalet så att det blir lämpligt.</span><span class="sxs-lookup"><span data-stu-id="e1b29-168">If your export takes more time, adjust the limit count as appropriate.</span></span>        

    3. <span data-ttu-id="e1b29-169">Lägg till åtgärden **Anropa HTTP-begäran** för att anropa [GetExecutionSummaryStatus](../fin-ops-core/dev-itpro/data-entities/data-management-api.md#getexecutionsummarystatus) DMF REST API, och ange **ExecutionStatus**-variabeln till resultatet av **GetExecutionSummaryStatus**-svar.</span><span class="sxs-lookup"><span data-stu-id="e1b29-169">Add an **Invoke HTTP request** action to call the [GetExecutionSummaryStatus](../fin-ops-core/dev-itpro/data-entities/data-management-api.md#getexecutionsummarystatus) DMF REST API, and set the **ExecutionStatus** variable to the result of the **GetExecutionSummaryStatus** response.</span></span>

        > <span data-ttu-id="e1b29-170">Det här exemplet utför ingen felkontroll.</span><span class="sxs-lookup"><span data-stu-id="e1b29-170">This sample doesn't do error checking.</span></span> <span data-ttu-id="e1b29-171">**GetExecutionSummaryStatus** API:n kan returnera terminaltillstånd som har misslyckats (dvs. andra lägen än **slutförd**).</span><span class="sxs-lookup"><span data-stu-id="e1b29-171">The **GetExecutionSummaryStatus** API can return non-successful terminal states (that is, states other than **Succeeded**).</span></span> <span data-ttu-id="e1b29-172">Mer information finns i [API-dokumentationen](../fin-ops-core/dev-itpro/data-entities/data-management-api.md#getexecutionsummarystatus).</span><span class="sxs-lookup"><span data-stu-id="e1b29-172">For more information, see the [API documentation](../fin-ops-core/dev-itpro/data-entities/data-management-api.md#getexecutionsummarystatus).</span></span>

        - <span data-ttu-id="e1b29-173">**Metod:** POST</span><span class="sxs-lookup"><span data-stu-id="e1b29-173">**Method:** POST</span></span>
        - <span data-ttu-id="e1b29-174">**Url för begäran:** https://\<hostname\>/namespaces/\<namespace\_guid\>/data/DataManagementDefinitionGroups/Microsoft.Dynamics.DataEntities.GetExecutionSummaryStatus</span><span class="sxs-lookup"><span data-stu-id="e1b29-174">**Url of the request:** https://\<hostname\>/namespaces/\<namespace\_guid\>/data/DataManagementDefinitionGroups/Microsoft.Dynamics.DataEntities.GetExecutionSummaryStatus</span></span>
        - <span data-ttu-id="e1b29-175">**Brödtext för begäran:** body('Invoke\_an\_HTTP\_request')?['value']</span><span class="sxs-lookup"><span data-stu-id="e1b29-175">**Body of the request:** body('Invoke\_an\_HTTP\_request')?['value']</span></span>

            > [!NOTE]
            > <span data-ttu-id="e1b29-176">Du kan behöva ange värdet för **brödtext för begäran** antingen i kodvyn eller i funktionsredigeraren i designern.</span><span class="sxs-lookup"><span data-stu-id="e1b29-176">You might have to enter the **Body of the request** value either in code view or in the function editor in the designer.</span></span>

        ![Åtgärden anropa en HTTP-begäran 2](media/integration-logic-app-get-execution-status-step.png)

        ![Åtgärden Ange variabel](media/integration-logic-app-set-variable-step.png)

        > [!IMPORTANT]
        > <span data-ttu-id="e1b29-179">Värdet för åtgärden **Ange variabel** (**body('Invoke\_an\_HTTP\_request\_2')?['value']**) skiljer sig från värdet för **Invoke an HTTP request 2** brödtextvärde, även om designern visar värdena på samma sätt.</span><span class="sxs-lookup"><span data-stu-id="e1b29-179">The value for the **Set variable** action (**body('Invoke\_an\_HTTP\_request\_2')?['value']**) will differ from the value for the **Invoke an HTTP request 2** body value, even though the designer will show the values in the same way.</span></span>

7. <span data-ttu-id="e1b29-180">Skaffa hämtnings-URL för det exporterade paketet.</span><span class="sxs-lookup"><span data-stu-id="e1b29-180">Get the download URL of the exported package.</span></span>

    - <span data-ttu-id="e1b29-181">Lägg till åtgärden **Anropa HTTP-begäran** för att anropa [GetExportedPackageUrl](../fin-ops-core/dev-itpro/data-entities/data-management-api.md#getexportedpackageurl) DMF REST API.</span><span class="sxs-lookup"><span data-stu-id="e1b29-181">Add an **Invoke HTTP request** action to call the [GetExportedPackageUrl](../fin-ops-core/dev-itpro/data-entities/data-management-api.md#getexportedpackageurl) DMF REST API.</span></span>

        - <span data-ttu-id="e1b29-182">**Metod:** POST</span><span class="sxs-lookup"><span data-stu-id="e1b29-182">**Method:** POST</span></span>
        - <span data-ttu-id="e1b29-183">**Url för begäran:** https://\<hostname\>/namespaces/\<namespace\_guid\>/data/DataManagementDefinitionGroups/Microsoft.Dynamics.DataEntities.GetExportedPackageUrl</span><span class="sxs-lookup"><span data-stu-id="e1b29-183">**Url of the request:** https://\<hostname\>/namespaces/\<namespace\_guid\>/data/DataManagementDefinitionGroups/Microsoft.Dynamics.DataEntities.GetExportedPackageUrl</span></span>
        - <span data-ttu-id="e1b29-184">**Begärans brödtext:** {"executionId": body('GetExportedPackageURL')?['value']}</span><span class="sxs-lookup"><span data-stu-id="e1b29-184">**Body of the request:** {"executionId": body('GetExportedPackageURL')?['value']}</span></span>

        ![Åtgärden GetExportedPackageURL](media/integration-logic-app-get-exported-package-step.png)

8. <span data-ttu-id="e1b29-186">Hämta det exporterade paketet.</span><span class="sxs-lookup"><span data-stu-id="e1b29-186">Download the exported package.</span></span>

    - <span data-ttu-id="e1b29-187">Lägg till en HTTP **GET**-begäran (en inbyggd [åtgärd för HTTP-koppling](/azure/connectors/connectors-native-http)) för att hämta paketet från den URL som returnerades i föregående steg.</span><span class="sxs-lookup"><span data-stu-id="e1b29-187">Add an HTTP **GET** request (a built-in [HTTP connector action](/azure/connectors/connectors-native-http)) to download the package from the URL that was returned in the previous step.</span></span>

        - <span data-ttu-id="e1b29-188">**Metod:** GET</span><span class="sxs-lookup"><span data-stu-id="e1b29-188">**Method:** GET</span></span>
        - <span data-ttu-id="e1b29-189">**URI:** body('Invoke\_an\_HTTP\_request\_3').value</span><span class="sxs-lookup"><span data-stu-id="e1b29-189">**URI:** body('Invoke\_an\_HTTP\_request\_3').value</span></span>

            > [!NOTE]
            > <span data-ttu-id="e1b29-190">Du kan behöva ange värdet för **URI** antingen i kodvyn eller i funktionsredigeraren i designern.</span><span class="sxs-lookup"><span data-stu-id="e1b29-190">You might have to enter the **URI** value either in code view or in the function editor in the designer.</span></span>

        ![Åtgärden HTTP GET](media/integration-logic-app-download-file-step.png)

        > [!NOTE]
        > <span data-ttu-id="e1b29-192">Denna begäran kräver ingen ytterligare autentisering eftersom den URL som **GetExportedPackageUrl** API:n returnerar innehåller en token för delad åtkomst för signaturer som beviljar åtkomst för att hämta filen.</span><span class="sxs-lookup"><span data-stu-id="e1b29-192">This request doesn't require any additional authentication, because the URL that the **GetExportedPackageUrl** API returns includes a shared access signatures token that grants access to download the file.</span></span>

9. <span data-ttu-id="e1b29-193">Spara det hämtade paketet med hjälp av [OneDrive för företag](/azure/connectors/connectors-create-api-onedriveforbusiness)-kopplingen.</span><span class="sxs-lookup"><span data-stu-id="e1b29-193">Save the downloaded package by using the [OneDrive for Business](/azure/connectors/connectors-create-api-onedriveforbusiness) connector.</span></span>

    - <span data-ttu-id="e1b29-194">Lägg till en åtgärd för OneDrive för företag [Skapa fil](/connectors/onedriveforbusinessconnector/#create-file).</span><span class="sxs-lookup"><span data-stu-id="e1b29-194">Add a OneDrive for Business [Create File](/connectors/onedriveforbusinessconnector/#create-file) action.</span></span>
    - <span data-ttu-id="e1b29-195">Anslut till ditt OneDrive för företag-konto efter behov.</span><span class="sxs-lookup"><span data-stu-id="e1b29-195">Connect to your OneDrive for Business account, as required.</span></span>

        - <span data-ttu-id="e1b29-196">**Mappsökväg:** en mapp som du väljer</span><span class="sxs-lookup"><span data-stu-id="e1b29-196">**Folder Path:** A folder of your choice</span></span>
        - <span data-ttu-id="e1b29-197">**Filnamn:** worker\_package.zip</span><span class="sxs-lookup"><span data-stu-id="e1b29-197">**File Name:** worker\_package.zip</span></span>
        - <span data-ttu-id="e1b29-198">**Filinnehåll:** brödtexten från föregående steg (dynamiskt innehåll)</span><span class="sxs-lookup"><span data-stu-id="e1b29-198">**File Content:** The body from the previous step (dynamic content)</span></span>

        ![Åtgärden Skapa fil](media/integration-logic-app-create-file-step.png)

### <a name="step-3-test-the-logic-app"></a><span data-ttu-id="e1b29-200">Steg 3: testa logikappen</span><span class="sxs-lookup"><span data-stu-id="e1b29-200">Step 3: Test the logic app</span></span>

<span data-ttu-id="e1b29-201">Om du vill testa din logikapp väljer du knappen **Kör** i designern.</span><span class="sxs-lookup"><span data-stu-id="e1b29-201">To test your logic app, select the **Run** button in the designer.</span></span> <span data-ttu-id="e1b29-202">Du kommer att se att stegen i logikappen börjar köras.</span><span class="sxs-lookup"><span data-stu-id="e1b29-202">You will see that the steps of the logic app start to run.</span></span> <span data-ttu-id="e1b29-203">Efter 30 till 40 sekunder bör logikappen slutföras och mappen OneDrive för företag bör innehålla en ny paketfil som innehåller de exporterade arbetarna.</span><span class="sxs-lookup"><span data-stu-id="e1b29-203">After 30 to 40 seconds, the logic app should finish running, and your OneDrive for Business folder should include a new package file that contains the exported workers.</span></span>

<span data-ttu-id="e1b29-204">Om ett fel rapporteras för något steg väljer du det misslyckade steget i designer och granskar fälten **indata** och **utdata**.</span><span class="sxs-lookup"><span data-stu-id="e1b29-204">If a failure is reported for any step, select the failed step in the designer, and examine the **Inputs** and **Outputs** fields for it.</span></span> <span data-ttu-id="e1b29-205">Felsök och justera steget efter behov för att korrigera felen.</span><span class="sxs-lookup"><span data-stu-id="e1b29-205">Debug and adjust the step as required to correct the errors.</span></span>

<span data-ttu-id="e1b29-206">Följande bild visar hur Logic Apps Designer ser ut när alla steg i logikappen körs korrekt.</span><span class="sxs-lookup"><span data-stu-id="e1b29-206">The following illustration shows what the Logic Apps Designer looks like when all the steps of the logic app run successfully.</span></span>

![Körning av lyckade logikappar](media/integration-logic-app-successful-run.png)

## <a name="summary"></a><span data-ttu-id="e1b29-208">Sammanfattning</span><span class="sxs-lookup"><span data-stu-id="e1b29-208">Summary</span></span>

<span data-ttu-id="e1b29-209">I den här självstudien lärde du dig att använda en logikapp för att exportera data från personal och spara exporterade data till en OneDrive för företag-mapp.</span><span class="sxs-lookup"><span data-stu-id="e1b29-209">In this tutorial, you learned how to use a logic app to export data from Human Resources and save the exported data to a OneDrive for Business folder.</span></span> <span data-ttu-id="e1b29-210">Du kan ändra stegen i den här självstudien så att de passar dina affärsbehov.</span><span class="sxs-lookup"><span data-stu-id="e1b29-210">You can modify the steps of this tutorial as required to suit your business needs.</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]