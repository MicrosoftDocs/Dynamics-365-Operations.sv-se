---
title: Konfiguration för Finance Insights för offentlig förhandsgranskning (förhandsversion) – version 10.0.20 och senare
description: I detta ämne beskrivs hur du konfigurerar ditt system för att använda de funktioner som finns i Finance Insights för allmänt tillgänglig förhandsversion i version 10.0.20 och senare.
author: ShivamPandey-msft
ms.date: 06/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2021-06-03
ms.dyn365.ops.version: AX 10.0.20
ms.openlocfilehash: 613bd4816e2f0c4fbb56cf79779a08c6a09592bd
ms.sourcegitcommit: 655b0e16c7aef6182cd58bc816b901470e1bb2ce
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/10/2021
ms.locfileid: "6222622"
---
# <a name="configuration-for-finance-insights-for-public-preview-preview---version-10020-and-later"></a><span data-ttu-id="d5a9e-103">Konfiguration för Finance Insights för offentlig förhandsgranskning (förhandsversion) – version 10.0.20 och senare</span><span class="sxs-lookup"><span data-stu-id="d5a9e-103">Configuration for Finance insights for public preview (preview) - version 10.0.20 and later</span></span>

[!include [banner](../includes/banner.md)]

[!include [preview banner](../includes/preview-banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="d5a9e-104">Ekonomiska insikter kombinerar funktioner från Microsoft Dynamics 365 Finance med Dataverse, Azure och AI Builder för att tillhandahålla kraftfulla prognosverktyg för organisationen.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-104">Finance insights combines functionality from Microsoft Dynamics 365 Finance with Dataverse, Azure, and AI Builder to provide powerful forecasting tools for your organization.</span></span> <span data-ttu-id="d5a9e-105">I detta ämne beskrivs hur du konfigurerar Dynamics 365 Finance version 10.0.20 så att ditt system kan använda de funktioner som finns i Finance Insights för allmänt tillgänglig förhandsversion.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-105">This topic explains how to configure Dynamics 365 Finance version 10.0.20 so that your system can use the capabilities that are available in Finance insights public preview.</span></span>

> [!NOTE]
> <span data-ttu-id="d5a9e-106">Konfigurationsstegen som beskrivs i det här ämnet gäller bara för Finance version 10.0.20 och senare.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-106">The configuration steps that are described in this topic apply only to Finance version 10.0.20 and later.</span></span> <span data-ttu-id="d5a9e-107">"Mer information om hur du ställer in Finance Insights i version 10.0.19 och senare finns i [Konfiguration för Finance Insights – versioner upp till 10.0.18](configure-for-fin-insites.md).</span><span class="sxs-lookup"><span data-stu-id="d5a9e-107">'To set up Finance insights on version 10.0.19 and earlier, see [Configuration for Finance insights - versions up to 10.0.18](configure-for-fin-insites.md).</span></span>

## <a name="deploy-finance"></a><span data-ttu-id="d5a9e-108">Distribuera Finance</span><span class="sxs-lookup"><span data-stu-id="d5a9e-108">Deploy Finance</span></span>

<span data-ttu-id="d5a9e-109">Följ dessa steg för att distribuera miljöerna.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-109">Follow these steps to deploy the environments.</span></span>

1. <span data-ttu-id="d5a9e-110">I Microsoft Dynamics Lifecycle Services (LCS) skapar eller uppdaterar du en Finance-miljö.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-110">In Microsoft Dynamics Lifecycle Services (LCS), create or update a Finance environment.</span></span> <span data-ttu-id="d5a9e-111">Miljön kräver Finance and Operations-appar i version 10.0.20 eller senare.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-111">The environment requires app version 10.0.20 or later of Finance and Operations apps.</span></span>
2. <span data-ttu-id="d5a9e-112">Miljön måste vara en miljö med hög tillgänglighet (HA) i sandbox-miljö.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-112">The environment must be a high-availability (HA) environment in Sandbox.</span></span> <span data-ttu-id="d5a9e-113">(Den här typen av miljö kallas också för en Nivå-2-miljö.) Mer information finns i [Miljöplanering](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).</span><span class="sxs-lookup"><span data-stu-id="d5a9e-113">(This type of environment is also known as a Tier-2 environment.) For more information, see [Environment planning](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).</span></span>
3. <span data-ttu-id="d5a9e-114">Om du konfigurerar Finance Insights i en sandbox-miljö måste du kanske kopiera produktionsdata till den miljön för att förutsägelser ska fungera.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-114">If you are configuring Finance insights in a Sandbox environment, you might need to copy production data to that environment for predictions to work.</span></span> <span data-ttu-id="d5a9e-115">I modellen för förutsägelse används flera års data för att skapa förutsägelser.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-115">The prediction model uses multiple years of data to build predictions.</span></span> <span data-ttu-id="d5a9e-116">Contoso-demodatan innehåller inte tillräckligt historiska data för att mata förutsägelsemodellen tillräckligt mycket.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-116">The Contoso demo data doesn’t contain enough historical data to train the prediction model adequately.</span></span> 

## <a name="configure-dataverse"></a><span data-ttu-id="d5a9e-117">Konfigurera Dataverse</span><span class="sxs-lookup"><span data-stu-id="d5a9e-117">Configure Dataverse</span></span>

<span data-ttu-id="d5a9e-118">Följ dessa steg för att konfigurera Dataverse för Finance Insights.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-118">Follow these steps to configure Dataverse for Finance insights.</span></span>

1. <span data-ttu-id="d5a9e-119">I LCS öppnar du miljösidan och bekräftar att avsnittet **Power Platform-integrering** redan har konfigurerats.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-119">In LCS, open the environment page, and verify that the **Power Platform Integration** section is already set up.</span></span>

    - <span data-ttu-id="d5a9e-120">Om detta redan har konfigurerats ska namnet på den Dataverse-miljö som kopplats till Finance-miljön listas.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-120">If it's already set up, the Dataverse environment name that is linked to the Finance environment should be listed.</span></span>
    - <span data-ttu-id="d5a9e-121">Om detta ännu inte har konfigurerats följer du dessa steg:</span><span class="sxs-lookup"><span data-stu-id="d5a9e-121">If it isn't yet set up, follow these steps:</span></span>

        1. <span data-ttu-id="d5a9e-122">I avsnittet **Power Platform-integrering** väljer du **Konfigurera**.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-122">In the **Power Platform Integration** section, select **Setup**.</span></span> <span data-ttu-id="d5a9e-123">Inställningen av miljön kan ta upp till en timme.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-123">Setup of the environment might take up to an hour.</span></span>
        2. <span data-ttu-id="d5a9e-124">Om Dataverse-miljön har ställts in korrekt ska namnet på den Dataverse-miljö som kopplats till Finance-miljön listas.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-124">If the Dataverse environment is successfully set up, the Dataverse environment name that is linked to the Finance environment should be listed.</span></span>

        > [!NOTE]
        > <span data-ttu-id="d5a9e-125">När du är klar med inställningen av miljön ska du **inte** välja **Länka till CDS for Apps**.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-125">After you complete the environment setup, do **not** select **Link to CDS for Apps**.</span></span> <span data-ttu-id="d5a9e-126">Den här knappen behövs inte för Finance Insights.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-126">This button isn't required for Finance insights.</span></span> <span data-ttu-id="d5a9e-127">Om du väljer den kommer du inte att kunna konfigurera erforderliga miljötillägg i LCS.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-127">If you select it, you won't be able to configure the required environment add-ins in LCS.</span></span>

## <a name="configure-azure"></a><span data-ttu-id="d5a9e-128">Konfigurera Azure</span><span class="sxs-lookup"><span data-stu-id="d5a9e-128">Configure Azure</span></span>

### <a name="use-azure-cloud-shell-to-set-up-finance-insights-data-lake-resources"></a><span data-ttu-id="d5a9e-129">Använd Azure Cloud Shell för att konfigurera Ekonomiska insikters Data Lake-resurser</span><span class="sxs-lookup"><span data-stu-id="d5a9e-129">Use Azure Cloud Shell to set up Finance insights Data Lake resources</span></span>

# <a name="use-a-windows-powershell-script"></a>[<span data-ttu-id="d5a9e-130">Använd ett Windows PowerShell-skript</span><span class="sxs-lookup"><span data-stu-id="d5a9e-130">Use a Windows PowerShell script</span></span>](#tab/use-a-powershell-script)

<span data-ttu-id="d5a9e-131">Ett Windows PowerShell-skript har tillhandahållits så att du enkelt kan ställa in de Azure-resurser som beskrivs i [Konfigurera export till Azure Data Lake](../../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md).</span><span class="sxs-lookup"><span data-stu-id="d5a9e-131">A Windows PowerShell script has been provided so that you can easily set up the Azure resources that are described in [Configure export to Azure Data Lake](../../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md).</span></span> <span data-ttu-id="d5a9e-132">Om du föredrar att konfigurera manuellt hoppar du över den här proceduren och slutför proceduren i avsnittet [Manuell konfiguration](#manual-setup) istället.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-132">If you prefer to do the setup manually, skip this procedure, and complete the procedure in the [Manual setup](#manual-setup) section instead.</span></span>

> [!NOTE]
> <span data-ttu-id="d5a9e-133">Gör på följande sätt när du vill köra Windows PowerShell-skriptet:</span><span class="sxs-lookup"><span data-stu-id="d5a9e-133">Use the following procedure to run the Windows PowerShell script.</span></span> <span data-ttu-id="d5a9e-134">Konfigureringen kanske inte fungerar om du använder alternativet **Testa** i Azure CLI eller om du kör skriptet på datorn.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-134">The setup might not work if you use the **Try it** option in Azure CLI or if you run the script on your computer.</span></span>

<span data-ttu-id="d5a9e-135">Följ dessa steg för att använda Windows PowerShell-skriptet för att konfigurera Azure.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-135">Follow these steps to use the Windows PowerShell script to configure Azure.</span></span> <span data-ttu-id="d5a9e-136">Du måste ha behörighet att skapa en Azure-resursgrupp, Azure-resurser och ett Azure AD-program.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-136">You must have rights to create an Azure resource group, Azure resources, and an Azure AD application.</span></span> <span data-ttu-id="d5a9e-137">Information om vilka behörigheter som krävs finns i [Kontrollera Azure AD-behörigheter](/azure/active-directory/develop/howto-create-service-principal-portal#permissions-required-for-registering-an-app).</span><span class="sxs-lookup"><span data-stu-id="d5a9e-137">For information about the required permissions, see [Check Azure AD permissions](/azure/active-directory/develop/howto-create-service-principal-portal#permissions-required-for-registering-an-app).</span></span>

1. <span data-ttu-id="d5a9e-138">I [Azure-portalen](https://portal.azure.com), gå till din mål-Azure-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-138">In the [Azure portal](https://portal.azure.com), go to your target Azure subscription.</span></span>
2. <span data-ttu-id="d5a9e-139">Välj **Cloud Shell** till höger om fältet **Search**.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-139">Select **Cloud Shell** to the right of the **Search** field.</span></span>
3. <span data-ttu-id="d5a9e-140">Välj **PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-140">Select **PowerShell**.</span></span>
4. <span data-ttu-id="d5a9e-141">Skapa lagringsutrymme om du uppmanas göra det.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-141">Create storage if you're prompted to create it.</span></span>
5. <span data-ttu-id="d5a9e-142">På fliken **Azure CLI** väljer du **Kopiera**.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-142">On the **Azure CLI** tab, select **Copy**.</span></span>
6. <span data-ttu-id="d5a9e-143">Öppna en ny fil i Anteckningar och klistra in Windows PowerShell-skriptet.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-143">In Notepad, open a new file, and paste in the Windows PowerShell script.</span></span>
7. <span data-ttu-id="d5a9e-144">Spara filen som **ConfigureDataLake.ps1**.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-144">Save the file as **ConfigureDataLake.ps1**.</span></span>
8. <span data-ttu-id="d5a9e-145">Ladda upp Windows PowerShell-skriptet till sessionen med hjälp av menyalternativet för uppladdning i Cloud Shell.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-145">Upload the Windows PowerShell script to the session by using the menu option for upload in Cloud Shell.</span></span>
9. <span data-ttu-id="d5a9e-146">Kör skriptet **.\ConfigureDataLake.ps1**.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-146">Run the **.\ConfigureDataLake.ps1** script.</span></span>
10. <span data-ttu-id="d5a9e-147">Kör skriptet genom att följa anvisningarna.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-147">Follow the prompts to run the script.</span></span>
11. <span data-ttu-id="d5a9e-148">Installera tillägget Exportera till Data Lake i LCS med hjälp av informationen i skriptets utdata.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-148">Use the information from the script output to install the Export to Data Lake add-in in LCS.</span></span>

### <a name="manual-setup"></a><span data-ttu-id="d5a9e-149">Manuell konfiguration</span><span class="sxs-lookup"><span data-stu-id="d5a9e-149">Manual setup</span></span>

#### <a name="add-applications-to-the-azure-ad-tenant"></a><span data-ttu-id="d5a9e-150">Lägg till program i Azure AD-klientorganisationen</span><span class="sxs-lookup"><span data-stu-id="d5a9e-150">Add applications to the Azure AD tenant</span></span>

1. <span data-ttu-id="d5a9e-151">I [Azure-portalen](https://portal.azure.com), gå till **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-151">In the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**.</span></span>
2. <span data-ttu-id="d5a9e-152">Välj **Hantera \> Företagsprogram**.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-152">Select **Manage \> Enterprise applications**.</span></span>
3. <span data-ttu-id="d5a9e-153">Sök efter följande program med app-ID.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-153">Search for the following applications by app ID.</span></span>

    | <span data-ttu-id="d5a9e-154">Ansökning</span><span class="sxs-lookup"><span data-stu-id="d5a9e-154">Application</span></span>                              | <span data-ttu-id="d5a9e-155">App-ID</span><span class="sxs-lookup"><span data-stu-id="d5a9e-155">App ID</span></span>                               |
    |------------------------------------------|--------------------------------------|
    | <span data-ttu-id="d5a9e-156">Microsoft Dynamics ERP Microservices</span><span class="sxs-lookup"><span data-stu-id="d5a9e-156">Microsoft Dynamics ERP Microservices</span></span>     | <span data-ttu-id="d5a9e-157">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span><span class="sxs-lookup"><span data-stu-id="d5a9e-157">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span></span> |
    | <span data-ttu-id="d5a9e-158">Microsoft Dynamics ERP Microservices CDS</span><span class="sxs-lookup"><span data-stu-id="d5a9e-158">Microsoft Dynamics ERP Microservices CDS</span></span> | <span data-ttu-id="d5a9e-159">703e2651-d3fc-48f5-942c-74274233dba8</span><span class="sxs-lookup"><span data-stu-id="d5a9e-159">703e2651-d3fc-48f5-942c-74274233dba8</span></span> |
    | <span data-ttu-id="d5a9e-160">AI Builder Authorization Service</span><span class="sxs-lookup"><span data-stu-id="d5a9e-160">AI Builder Authorization Service</span></span>         | <span data-ttu-id="d5a9e-161">ad40333e-9910-4b61-b281-e3aeeb8c3ef3</span><span class="sxs-lookup"><span data-stu-id="d5a9e-161">ad40333e-9910-4b61-b281-e3aeeb8c3ef3</span></span> |

<span data-ttu-id="d5a9e-162">Om du inte hittar något av ovanstående program gör du på följande sätt.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-162">If you can't find any of the preceding applications, try the following steps.</span></span>

1. <span data-ttu-id="d5a9e-163">I menyn **Start** på din lokala dator söker du efter **powershell**.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-163">On your local computer, on the **Start** menu, search for **powershell**.</span></span>
2. <span data-ttu-id="d5a9e-164">Markera och håll (eller högerklicka) på **Windows PowerShell** och välj **Kör som administratör**.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-164">Select and hold (or right-click) **Windows PowerShell**, and then select **Run as administrator**.</span></span>
3. <span data-ttu-id="d5a9e-165">Kör följande kommando för att installera modulen **AzureAD**.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-165">Run the following command to install the **AzureAD** module.</span></span>

    `Install-Module -Name AzureAD`

4. <span data-ttu-id="d5a9e-166">Om en NuGet-leverantör krävs för att du ska kunna fortsätta väljer **Y** för att installera den.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-166">If a NuGet provider is required to continue, select **Y** to install it.</span></span>
5. <span data-ttu-id="d5a9e-167">Om du får meddelandet "Untrusted repository" (Ej betrodd lagringsplats) väljer du **Y** för att fortsätta.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-167">If you receive an "Untrusted repository" message, select **Y** to continue.</span></span>
6. <span data-ttu-id="d5a9e-168">Kör följande kommandon för varje program som måste läggas till för att du ska kunna lägga till programmet i Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-168">For each application that must be added, run the following commands to add the application to Azure AD.</span></span> <span data-ttu-id="d5a9e-169">Logga in som Azure AD-administratör när du uppmanas till det.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-169">When you're prompted, sign in as the Azure AD administrator.</span></span>

    `Connect-AzureAD`

    `New-AzureADServicePrincipal –AppId <AppId>`

#### <a name="create-azure-resources"></a><span data-ttu-id="d5a9e-170">Skapa Azure-resurser</span><span class="sxs-lookup"><span data-stu-id="d5a9e-170">Create Azure resources</span></span>

> [!NOTE]
> <span data-ttu-id="d5a9e-171">Se till att du skapar följande resurser i samma Azure AD-instans som Dataverse-miljön finns i.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-171">Make sure that you create the following resources in the same Azure AD instance that the Dataverse environment is in.</span></span> <span data-ttu-id="d5a9e-172">Du kan inte använda resurser från en annan Azure AD-instans.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-172">You can't use resources from a different Azure AD instance.</span></span>

1. <span data-ttu-id="d5a9e-173">Skapa ett lagringskonto:</span><span class="sxs-lookup"><span data-stu-id="d5a9e-173">Create a storage account:</span></span>

    1. <span data-ttu-id="d5a9e-174">Skapa ett lagringskonto i [Azure-portalen](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="d5a9e-174">In the [Azure portal](https://portal.azure.com), create a storage account.</span></span>
    2. <span data-ttu-id="d5a9e-175">I dialogrutan **Skapa lagringskonto**, ställ in följande fält:</span><span class="sxs-lookup"><span data-stu-id="d5a9e-175">In the **Create storage account** dialog box, set the following fields:</span></span>

        - <span data-ttu-id="d5a9e-176">**Plats** – Välj det datacenter där din miljö finns.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-176">**Location** – Select the data center where your environment is located.</span></span>
        - <span data-ttu-id="d5a9e-177">**Prestanda** – Vi rekommenderar att du väljer **Standard**.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-177">**Performance** – We recommend that you select **Standard**.</span></span>
        - <span data-ttu-id="d5a9e-178">**Kontotyp** – Du måste välja **StorageV2**.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-178">**Account kind** – You must select **StorageV2**.</span></span>

    3. <span data-ttu-id="d5a9e-179">I dialogrutan **Avancerade alternativ**, för alternativet **Data Lake Storage Gen2** väljer du **Aktivera** under funktionen **Hierarkiska namnrymder**.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-179">In the **Advanced options** dialog box, for the **Data Lake storage Gen2** option, select **Enable** under the **Hierarchical namespaces** feature.</span></span> <span data-ttu-id="d5a9e-180">Om du inte aktiverar den här funktionen kan du inte använda data som Finance and Operations-appar skriver med hjälp av tjänster som exempelvis Power BI-dataflöden.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-180">If you don't enable this feature, you can't consume data that Finance and Operations apps write by using services such as Power BI data flows.</span></span>
    4. <span data-ttu-id="d5a9e-181">Välj **Granska och skapa**.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-181">Select **Review and create**.</span></span> <span data-ttu-id="d5a9e-182">När distributionen har slutförts visas den nya resursen i Azure-portalen.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-182">When the deployment is completed, the new resource is shown in the Azure portal.</span></span>
    5. <span data-ttu-id="d5a9e-183">Gå till det lagringskonto som du har skapat.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-183">Go to the storage account that you created.</span></span>
    6. <span data-ttu-id="d5a9e-184">Välj **Åtkomstnycklar** i menyn till vänster.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-184">On the left menu, select **Access keys**.</span></span>
    7. <span data-ttu-id="d5a9e-185">Kopiera och spara namnet på lagringskontot.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-185">Copy and save the name of the storage account.</span></span> <span data-ttu-id="d5a9e-186">Du måste ange det här värdet senare när du konfigurerar hemligheter för nyckelvalvet.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-186">You will have to provide this value later, when you set up key vault secrets.</span></span>

2. <span data-ttu-id="d5a9e-187">Skapa ett nyckelvalv:</span><span class="sxs-lookup"><span data-stu-id="d5a9e-187">Create a key vault:</span></span>

    1. <span data-ttu-id="d5a9e-188">Skapa ett nyckelvalv i [Azure-portalen](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="d5a9e-188">In the [Azure portal](https://portal.azure.com), create a key vault.</span></span>
    2. <span data-ttu-id="d5a9e-189">I dialogrutan **Skapa nyckelvalv**, i fältet **Plats**, välj det datacenter där din miljö finns.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-189">In the **Create key vault** dialog box, in the **Location** field, select the data center where your environment is located.</span></span>
    3. <span data-ttu-id="d5a9e-190">När du har skapat nyckelvalvet går du till **Nyckelvalvsöversikt** och kopierar samt sparar DNS-namnet.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-190">After key vault is created, go to **Key Vault Overview**, and copy and save the DNS name.</span></span> <span data-ttu-id="d5a9e-191">Du måste ange det här värdet senare när du konfigurerar tillägget för Data Lake.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-191">You will have to provide this value later, when you set up the Data Lake add-in.</span></span>

3. <span data-ttu-id="d5a9e-192">Skapa och registrera ett Azure AD-program:</span><span class="sxs-lookup"><span data-stu-id="d5a9e-192">Create and register an Azure AD application:</span></span>

    1. <span data-ttu-id="d5a9e-193">I [Azure-portalen](https://portal.azure.com), gå till **Azure Active Directory** och välj **Appregistreringar**.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-193">In the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**, and then select **App registrations**.</span></span>
    2. <span data-ttu-id="d5a9e-194">Välj **Ny programregistrering** och ange följande fält:</span><span class="sxs-lookup"><span data-stu-id="d5a9e-194">Select **New application registration**, and set the following fields:</span></span>

        - <span data-ttu-id="d5a9e-195">**Namn** – Ange namnet på appen.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-195">**Name** – Enter the name of the app.</span></span>
        - <span data-ttu-id="d5a9e-196">**Programtyp** – Välj **Webb-API**.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-196">**Application type** – Select **Web API**.</span></span>
        - <span data-ttu-id="d5a9e-197">**Inställning av omdirigerings-URI** – Ange URL:en för din Dynamics 365-instans, till exempel `https://yourdynamicsinstance.dynamics.com/auth`.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-197">**Redirect URI setup** – Enter the URL for your Dynamics 365 instance, such as `https://yourdynamicsinstance.dynamics.com/auth`.</span></span>

    3. <span data-ttu-id="d5a9e-198">Gå till den app som du just skapade och kopiera och spara dess värde för **Program-ID (klient)**.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-198">Go to the app that you just created, and copy and save its **Application (client) ID** value.</span></span> <span data-ttu-id="d5a9e-199">Du måste ange det här värdet senare när du konfigurerar hemligheter för nyckelvalvet.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-199">You will have to provide this value later, when you set up key vault secrets.</span></span>
    4. <span data-ttu-id="d5a9e-200">Gå till **API-behörigheter** och gör så här:</span><span class="sxs-lookup"><span data-stu-id="d5a9e-200">Go to **API permissions**, and follow these steps:</span></span>

        1. <span data-ttu-id="d5a9e-201">Välj **Lägg till behörighet**.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-201">Select **Add a permission**.</span></span>
        2. <span data-ttu-id="d5a9e-202">Välj **Azure Key Vault**.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-202">Select **Azure Key vault**.</span></span>
        3. <span data-ttu-id="d5a9e-203">När du har valt delegerade behörigheter väljer du **användare\_personifiering**.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-203">After you select delegated permissions, select **user\_impersonation**.</span></span>
        4. <span data-ttu-id="d5a9e-204">Välj **Lägg till behörigheter**.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-204">Select **Add permissions**.</span></span>

    5. <span data-ttu-id="d5a9e-205">På menyn för appen väljer du **Certifikat \& hemligheter** och följer sedan stegen nedan för att skapa nyckelvalvhemligheter:</span><span class="sxs-lookup"><span data-stu-id="d5a9e-205">On the menu for the app, select **Certificates \& secrets**, and then follow these steps to create Key Vault secrets:</span></span>

        1. <span data-ttu-id="d5a9e-206">Välj **Ny klienthemlighet**.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-206">Select **New client secret**.</span></span>
        2. <span data-ttu-id="d5a9e-207">Ange ett namn i fältet **Nyckelbeskrivning**.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-207">In the **Key Description** field, enter a name.</span></span>
        3. <span data-ttu-id="d5a9e-208">Markera en varaktighet och välj sedan **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-208">Select a duration, and then select **Add**.</span></span> <span data-ttu-id="d5a9e-209">En hemlighet genereras i fältet **Värde**.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-209">A secret is generated in the **Value** field.</span></span>
        4. <span data-ttu-id="d5a9e-210">Kopiera och spara värdet för klienthemlighet.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-210">Copy and save the client secret value.</span></span> <span data-ttu-id="d5a9e-211">Du måste ange det här värdet senare när du konfigurerar hemligheter för nyckelvalvet.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-211">You will have to provide this value later, when you set up key vault secrets.</span></span>

4. <span data-ttu-id="d5a9e-212">Skapa nyckelvalvhemligheter:</span><span class="sxs-lookup"><span data-stu-id="d5a9e-212">Create Key Vault secrets:</span></span>

    1. <span data-ttu-id="d5a9e-213">Gå till det nyckelvalv som du skapade tidigare och välj **Hemligheter**.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-213">Go to the key vault that you created earlier, and select **Secrets**.</span></span>
    2. <span data-ttu-id="d5a9e-214">Gör så här för varje hemligt namn i följande tabell:</span><span class="sxs-lookup"><span data-stu-id="d5a9e-214">For each secret name in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="d5a9e-215">Välj **Generera/Importera**.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-215">Select **Generate/Import**.</span></span>
        2. <span data-ttu-id="d5a9e-216">I dialogrutan **Skapa en hemlighet** i fältet **Överföringsalternativ** välj **Manuell**.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-216">In the **Create a secret** dialog box, in the **Upload options** field, select **Manual**.</span></span>
        3. <span data-ttu-id="d5a9e-217">Skapa det hemliga namnet och värdet från tabellen.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-217">Create the secret name and value from the table.</span></span>
        4. <span data-ttu-id="d5a9e-218">Välj **Aktiverat** och välj sedan **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-218">Select **Enabled**, and then select **Create**.</span></span> <span data-ttu-id="d5a9e-219">Hemligheten skapas och läggs till i nyckelvalvet.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-219">The secret is created and added to Key Vault.</span></span>

        | <span data-ttu-id="d5a9e-220">Hemligt namn</span><span class="sxs-lookup"><span data-stu-id="d5a9e-220">Secret name</span></span>                       | <span data-ttu-id="d5a9e-221">Hemligt värde</span><span class="sxs-lookup"><span data-stu-id="d5a9e-221">Secret value</span></span>                                                                                 |
        |-----------------------------------|----------------------------------------------------------------------------------------------|
        | <span data-ttu-id="d5a9e-222">program-ID</span><span class="sxs-lookup"><span data-stu-id="d5a9e-222">app-id</span></span>                            | <span data-ttu-id="d5a9e-223">App-ID för programmet som du skapade tidigare.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-223">The app ID of the application that you created earlier.</span></span>                                      |
        | <span data-ttu-id="d5a9e-224">programhemlighet</span><span class="sxs-lookup"><span data-stu-id="d5a9e-224">app-secret</span></span>                        | <span data-ttu-id="d5a9e-225">Den klienthemlighet som du sparade tidigare.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-225">The client secret that you saved earlier.</span></span>                                                    |
        | <span data-ttu-id="d5a9e-226">lagringskontonamn</span><span class="sxs-lookup"><span data-stu-id="d5a9e-226">storage-account-name</span></span>              | <span data-ttu-id="d5a9e-227">Namnet på det lagringskonto som du skapade tidigare, t.ex. **lagringskonto1**.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-227">The name of the storage account that you created earlier, such as **storageaccount1**.</span></span>       |

5. <span data-ttu-id="d5a9e-228">Auktorisera programmet för att få åtkomst till nyckelvalvet:</span><span class="sxs-lookup"><span data-stu-id="d5a9e-228">Authorize the application to access the key vault:</span></span>

    1. <span data-ttu-id="d5a9e-229">I [Azure-portalen](https://portal.azure.com), öppna nyckelvalvet som du skapade tidigare.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-229">In the [Azure portal](https://portal.azure.com), open the key vault that you created earlier.</span></span>
    2. <span data-ttu-id="d5a9e-230">Välj åtkomstprinciper.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-230">Select the access policies.</span></span>
    3. <span data-ttu-id="d5a9e-231">Gör så här för varje program i följande tabell:</span><span class="sxs-lookup"><span data-stu-id="d5a9e-231">For each application in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="d5a9e-232">Välj **Lägg till åtkomstprincip** för att skapa en åtkomstprincip.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-232">Select **Add Access Policy** to create an access policy.</span></span>
        2. <span data-ttu-id="d5a9e-233">I fältet **Hemliga behörigheter** väljer du behörigheterna från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-233">In the **Secret permissions** field, select the permissions from the table.</span></span>
        3. <span data-ttu-id="d5a9e-234">I fältet **Välj huvudkonto** söker du efter programmets visningsnamn i tabellen.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-234">In the **Select principal** field, search for the application display name from the table.</span></span>
        4. <span data-ttu-id="d5a9e-235">Välj **Välj**.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-235">Select **Select**.</span></span>
        5. <span data-ttu-id="d5a9e-236">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-236">Select **Add**.</span></span>
        6. <span data-ttu-id="d5a9e-237">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-237">Select **Save**.</span></span>

        | <span data-ttu-id="d5a9e-238">Ansökning</span><span class="sxs-lookup"><span data-stu-id="d5a9e-238">Application</span></span>                                              | <span data-ttu-id="d5a9e-239">Behörighet</span><span class="sxs-lookup"><span data-stu-id="d5a9e-239">Permissions</span></span> |
        |----------------------------------------------------------|-------------|
        | <span data-ttu-id="d5a9e-240">Visningsnamnet för det nya program som du skapade</span><span class="sxs-lookup"><span data-stu-id="d5a9e-240">The display name of the new application that you created</span></span> | <span data-ttu-id="d5a9e-241">Get, List</span><span class="sxs-lookup"><span data-stu-id="d5a9e-241">Get, List</span></span>   |
        | <span data-ttu-id="d5a9e-242">**Microsoft Dynamics ERP Microservices**</span><span class="sxs-lookup"><span data-stu-id="d5a9e-242">**Microsoft Dynamics ERP Microservices**</span></span>                 | <span data-ttu-id="d5a9e-243">Get, List</span><span class="sxs-lookup"><span data-stu-id="d5a9e-243">Get, List</span></span>   |

6. <span data-ttu-id="d5a9e-244">Tilldela roller för åtkomst till lagringskontot:</span><span class="sxs-lookup"><span data-stu-id="d5a9e-244">Assign roles to access the storage account:</span></span>

    1. <span data-ttu-id="d5a9e-245">I [Azure-portalen](https://portal.azure.com), öppna lagringskontot som du skapade tidigare.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-245">In the [Azure portal](https://portal.azure.com), open the storage account that you created earlier.</span></span>
    2. <span data-ttu-id="d5a9e-246">Välj **Åtkomstkontroll (IAM)** och välj **Rolltilldelningar**.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-246">Select **Access Control (IAM)**, and then select **Role Assignments**.</span></span>
    3. <span data-ttu-id="d5a9e-247">Välj **Lägg till, Lägg till rolltilldelning**.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-247">Select **Add, Add Role Assignment**.</span></span>
    4. <span data-ttu-id="d5a9e-248">Gör så här för varje program i följande tabell:</span><span class="sxs-lookup"><span data-stu-id="d5a9e-248">For each application in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="d5a9e-249">Välj rollen i tabellen.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-249">Select the role from the table.</span></span>
        2. <span data-ttu-id="d5a9e-250">Låt fältet **Tilldela åtkomst till** vara inställt på **Azure AD-användare, -grupp eller -tjänstens huvudnamn**.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-250">Leave the **Assign access to** field set to **Azure AD user, group, or service principal**.</span></span>
        3. <span data-ttu-id="d5a9e-251">I fältet **Välj** anger programmet i tabellen.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-251">In the **Select** field, enter the application from the table.</span></span>
        4. <span data-ttu-id="d5a9e-252">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-252">Select **Save**.</span></span>

        | <span data-ttu-id="d5a9e-253">Ansökning</span><span class="sxs-lookup"><span data-stu-id="d5a9e-253">Application</span></span>                                              | <span data-ttu-id="d5a9e-254">Roll</span><span class="sxs-lookup"><span data-stu-id="d5a9e-254">Role</span></span>                        |
        |----------------------------------------------------------|-----------------------------|
        | <span data-ttu-id="d5a9e-255">Visningsnamnet för det nya program som du skapade</span><span class="sxs-lookup"><span data-stu-id="d5a9e-255">The display name of the new application that you created</span></span> | <span data-ttu-id="d5a9e-256">Ägare</span><span class="sxs-lookup"><span data-stu-id="d5a9e-256">Owner</span></span>                       |
        | <span data-ttu-id="d5a9e-257">Visningsnamnet för det nya program som du skapade</span><span class="sxs-lookup"><span data-stu-id="d5a9e-257">The display name of the new application that you created</span></span> | <span data-ttu-id="d5a9e-258">Deltagare</span><span class="sxs-lookup"><span data-stu-id="d5a9e-258">Contributor</span></span>                 |
        | <span data-ttu-id="d5a9e-259">Visningsnamnet för det nya program som du skapade</span><span class="sxs-lookup"><span data-stu-id="d5a9e-259">The display name of the new application that you created</span></span> | <span data-ttu-id="d5a9e-260">Lagringskontodeltagare</span><span class="sxs-lookup"><span data-stu-id="d5a9e-260">Storage Account Contributor</span></span> |
        | <span data-ttu-id="d5a9e-261">Visningsnamnet för det nya program som du skapade</span><span class="sxs-lookup"><span data-stu-id="d5a9e-261">The display name of the new application that you created</span></span> | <span data-ttu-id="d5a9e-262">Storage Blob Data-ägare</span><span class="sxs-lookup"><span data-stu-id="d5a9e-262">Storage Blob Data Owner</span></span>     |
        | <span data-ttu-id="d5a9e-263">**AI Builder Authorization Service**</span><span class="sxs-lookup"><span data-stu-id="d5a9e-263">**AI Builder Authorization Service**</span></span>                     | <span data-ttu-id="d5a9e-264">Storage Blob Data-läsare</span><span class="sxs-lookup"><span data-stu-id="d5a9e-264">Storage Blob Data Reader</span></span>    |

# <a name="azure-cli"></a>[<span data-ttu-id="d5a9e-265">Azure CLI</span><span class="sxs-lookup"><span data-stu-id="d5a9e-265">Azure CLI</span></span>](#tab/azure-azure-cli)

```
function New-FinanceDataLakeAzureResources {
    Assert-ScriptSetup

    $ClientAppName = 'Finance Data Lake Application'
    $DefaultSecretExpiryInYear = 1
    $MicrosoftDynamicsERPMicroservicesAppId = '0cdb527f-a8d1-4bf8-9436-b352c68682b2'
    $MicrosoftDynamicsERPMicroservicesCDSAppId = '703e2651-d3fc-48f5-942c-74274233dba8'
    $AIBuilderAuthorizationServiceAppId = 'ad40333e-9910-4b61-b281-e3aeeb8c3ef3'
    $KeyVaultServicePrincipalAppId = 'cfa8b339-82a2-471a-a3c9-0fc0be7a4093'
    $GraphServicePrincipalAppId = '00000003-0000-0000-c000-000000000000'

    Import-Module AzureAD.Standard.Preview
    $connectAzureADParameters = @{ 'Identity' = $true; 'TenantId' = $env:ACC_TID }
    $azContext = AzureAD.Standard.Preview\Connect-AzureAD @connectAzureADParameters
    $userContext = ConvertFrom-Json ((az ad signed-in-user show) -join '')
    $user = Get-AzureADUser -Filter ("UserPrincipalName eq '" + $userContext.UserPrincipalName + "'")

    Set-AzureSubscription
    
    $resourceGroup = $null
    $ResourceGroupName = 'D365FinanceInsightsDataLake'
    $ResourceGroupNameSuffix = ''
    $FullResourceGroupName = ''
    Write-Output ("The default Azure Resource Group name is '{0}'" -f $ResourceGroupName)
    while (-not ($resourceGroup)) {
        $ResourceGroupNameSuffix = (Read-Host -Prompt "Enter optional Azure Resource Group name suffix: (leave blank for no suffix)")
        if ([string]::IsNullOrWhitespace($ResourceGroupNameSuffix))
        {
            $FullResourceGroupName = $ResourceGroupName
        }
        else
        {
            if ($ResourceGroupNameSuffix -notmatch "^[A-Za-z0-9]+$") {
                Write-Warning "The Azure Resource Group name suffix can only include alphanumeric characters."
                continue
            }

            if ($ResourceGroupNameSuffix.Length -gt 60) {
                Write-Warning "The Azure Resource Group name suffix cannot be longer than 60 characters."
                continue
            }

            $FullResourceGroupName = $ResourceGroupName + $ResourceGroupNameSuffix
        }
        
        $resourceGroup = Get-AzResourceGroup -Name $FullResourceGroupName -ErrorAction SilentlyContinue

        if (-not ($resourceGroup)) {
            Write-Output ("Your new Azure Resource Group name is '{0}'" -f $FullResourceGroupName)
            $resourceLocation = ''
            $azResourceLocations = (Get-AzLocation | Select-Object Location).Location
            while ([string]::IsNullOrWhitespace($resourceLocation) -or (-not ($resourceLocation -in $azResourceLocations))) {
                $resourceLocation = (Read-Host -Prompt "Enter the location in which to create the Azure Resource Group: ('help' to see values)")
                if ($resourceLocation -eq 'help') {
                    Write-Output ("List of available regions is '{0}'" -f ($azResourceLocations -join ','))
                }
                elseif ([string]::IsNullOrWhitespace($resourceLocation) -or (-not ($resourceLocation -in $azResourceLocations)))
                {
                    Write-Warning ("The provided location is not available for resource group. List of available regions is '{0}'" -f ($azResourceLocations -join ','))
                }
            }
            $resourceGroup = New-AzResourceGroup -Name $FullResourceGroupName -Location $resourceLocation
            Write-Output ("Created Azure Resource Group '{0}'" -f $resourceGroup.ResourceGroupName)
        }
        else {
            Write-Output ("Found Azure Resource Group '{0}'" -f ($resourceGroup.ResourceGroupName))
        }
    }

    Write-Output '================================================================================='
    $MicrosoftDynamicsERPMicroservicesAppObjectId = Create-ADServicePrincipal -AppId $MicrosoftDynamicsERPMicroservicesAppId
    Create-ADServicePrincipal -AppId $MicrosoftDynamicsERPMicroservicesCDSAppId | Out-Null
    $aibuilderAuthorizationServiceObjectId = Create-ADServicePrincipal -AppId $AIBuilderAuthorizationServiceAppId
    Write-Output ('=================================================================================')

    $clientAppSPN = Get-AzureADServicePrincipal -Filter ("DisplayName eq '" + $ClientAppName + "'")
    if (-not ($clientAppSPN)) {
        $keyVaultPrincipal = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $KeyVaultServicePrincipalAppId + "'")
        if (-not $keyVaultPrincipal)
        {
            New-AzureADServicePrincipal -AppId $KeyVaultServicePrincipalAppId | Format-Table -AutoSize
            Write-Output "Added Key Vault principal to AAD"
            $keyVaultPrincipal = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $KeyVaultServicePrincipalAppId + "'")
        }
        $keyVaultAccess = New-Object -TypeName "Microsoft.Open.AzureAD.Model.RequiredResourceAccess"
        $keyVaultAccess.ResourceAppId = $keyVaultPrincipal.AppId
        $keyVaultAccess.ResourceAccess = (New-Object -TypeName "microsoft.open.azuread.model.resourceAccess" -ArgumentList $keyVaultPrincipal.Oauth2Permissions.Id, "Scope")

        $graphPrincipal = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $GraphServicePrincipalAppId + "'")
        if (-not $graphPrincipal)
        {
            New-AzureADServicePrincipal -AppId $GraphServicePrincipalAppId | Format-Table -AutoSize
            Write-Output "Added Graph principal to AAD"
            $graphPrincipal = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $GraphServicePrincipalAppId + "'")
        }
        $userRead = $graphPrincipal.Oauth2Permissions | Where-Object { $_.Type -eq "User" -and $_.Value -eq "User.Read" }
        $graphAccess = New-Object -TypeName "Microsoft.Open.AzureAD.Model.RequiredResourceAccess"
        $graphAccess.ResourceAppId = $graphPrincipal.AppId
        $graphAccess.ResourceAccess = (New-Object -TypeName "microsoft.open.azuread.model.resourceAccess" -ArgumentList $userRead.Id, "Scope")

        $clientApp = New-AzureADApplication -DisplayName $ClientAppName -RequiredResourceAccess @($keyVaultAccess, $graphAccess)
        $clientAppSPN = New-AzureADServicePrincipal -AppId $clientApp.AppId -Tags @($ClientAppName)
        $clientAppId = $clientApp.AppId
        Write-Output ('Created App Registration "' + $ClientAppName + '" with Application Id: ' + $clientAppId)
    }
    else {
        $clientApp = Get-AzureADApplication -Filter ("DisplayName eq '" + $ClientAppName + "'")
        $clientAppId = $clientApp.AppId
        Write-Output ('Found App Registration "' + $ClientAppName + '" with Application Id: ' + $clientAppId)
    }
            
    $clientAppSecretCredential = New-AzureADApplicationPasswordCredential -ObjectId $clientApp.ObjectId -CustomKeyIdentifier "ClientAppAccessKey" -EndDate (get-date).AddYears($DefaultSecretExpiryInYear)
    $ClientAppSecret = $clientAppSecretCredential.Value
    $clientAppSpId = $clientAppSPN.ObjectId

    Write-Output ('Generated application secret: ' + $ClientAppSecret)
    Write-Output '================================================================================='

    $templateObject = ConvertFrom-Json $azureTemplate -AsHashtable
    $templateObject.{$schema} = "https://schema.management.azure.com/schemas/2019-04-01/deploymentTemplate.json#"
    Write-Output 'Provisioning Azure resources. This may take a few minutes.'
    try {
        $deployment = New-AzResourceGroupDeployment -ResourceGroupName $FullResourceGroupName -TemplateObject $templateObject -aibuilderAppObjectId $aibuilderAuthorizationServiceObjectId -clientAppId $clientAppId -clientAppSecret $ClientAppSecret -clientAppSpObjectId  $clientAppSpId -microserviceSpObjectId $MicrosoftDynamicsERPMicroservicesAppObjectId -userSpObjectId $user.ObjectId -Force -ErrorAction Stop
    }
    catch {
        $ErrorMessage = $_.Exception.Message
        if ($ErrorMessage.Contains("not allowed to be updated"))
        {
            Write-Error ($ErrorMessage)
            Write-Warning "Some items in the existing resource group $FullResourceGroupName could not be updated. To resolve the issue, remove the existing resource group $FullResourceGroupName and run the script again."
        }
        else {
            throw
        }

    }
    if ($deployment.ProvisioningState -eq 'Succeeded') {
        Write-Output "Successfully deployed the following resources to Azure:"
        Write-Output ("  Key Vault:                         " + $deployment.Outputs.keyVaultName.Value)
        Write-Output ("  Storage Account:                   " + $deployment.Outputs.storageAccountName.Value)
        
        $keyVault = Get-AzKeyVault -VaultName $deployment.Outputs.keyVaultName.Value
        $tenantId = (Get-AzContext).Tenant.Id

        Write-Output "Values for LCS Data Lake Add-In:"
        Write-Output ("  Tenant ID:                         " + $tenantId)
        Write-Output ("  DNS Name:                          " + $keyVault.VaultUri)
        Write-Output "  Storage account secret name:       storage-account-name"
        Write-Output "  Application ID secret name:        app-id"
        Write-Output "  Application Secret secret name:    app-secret"
        Write-Warning "Copy this information for the LCS Add-in for easy access. Azure Cloud Shell will eventually time out and close."

        Write-Output '================================================================================='
        Write-Output "Values for System parameters > Data connections:"
        Write-Output ("  Application ID:                    " + $clientAppId)
        Write-Output ("  Application Secret:                " + $ClientAppSecret)
        Write-Output ("  DNS name:                          " + $keyVault.VaultUri)
        Write-Output "  Secret name:                       storage-account-connection-string"
        Write-Warning "Copy this information for the System parameters for easy access. Azure Cloud Shell will eventually time out and close."
    }
    else {
        Write-Output ("Provisioning Azure resources failed with the following state: " + $deployment.ProvisioningState)
        Write-Output ("Some of the resources may have been created in resource group: " + $FullResourceGroupName)
    }
}

function Assert-ScriptSetup {
    if ($PSVersionTable.PSEdition -ne 'Core' -or -not $env:ACC_TID) { 
        throw "This script needs to be uploaded and run from Azure Cloud Shell (PowerShell)." 
    }
    
    if ((Get-AzContext) -eq $null -and (Connect-AzAccount) -eq $null) {
        throw 'Unable to connect to Azure account.'
    }
}

function Set-AzureSubscription {
    $azSubscription = $null
    while (-not ($azSubscription)) {
        $subscriptionId = (Read-Host -Prompt "Enter the Azure Subscription ID: (leave blank for default)")
        if ([string]::IsNullOrWhitespace($subscriptionId)){
            break
        }
        elseif (-not [guid]::TryParse($subscriptionId, $([ref][guid]::Empty))) {
                Write-Warning "Azure Subscription ID must be a valid GUID."
                continue
        }

        $azSubscription = Select-AzSubscription -SubscriptionId $subscriptionId
    }
}

function Create-ADServicePrincipal {
    param (
        [string] $AppId
    )

    $service = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $AppId + "'")
    if (-not $service) {
        New-AzureADServicePrincipal -AppId $AppId | Out-Null
        $service = Get-AzureADServicePrincipal -Filter ("AppId eq '" + $AppId + "'")
        Write-Host ("Added AAD Enterprise Application {0} with Application ID {1}" -f $service.DisplayName,$AppId)
    }
    else {
        Write-Host ("Found AAD Enterprise Application {0} with Application ID {1}" -f $service.DisplayName,$AppId)
    }

    return $service.ObjectId
}

$azureTemplate = @"
{
    "contentVersion": "1.0.0.0",
    "parameters": {
      "aibuilderAppObjectId": {
        "type": "string",
        "metadata": {
          "description": "Specifies the object ID of the AI Builder application."
        }
      },
      "clientAppId": {
        "type": "string",
        "metadata": {
          "description": "Specifies the application ID of client application."
        }
      },
      "clientAppSecret": {
        "type": "String",
        "metadata": {
          "description": "Specifies the Azure App ID client secret to in azure key vault."
        }
      },
      "clientAppSpObjectId": {
        "type": "string",
        "metadata": {
          "description": "Specifies the object ID of a client application service principal."
        }
      },
      "userSpObjectId": {
        "type": "string",
        "metadata": {
          "description": "Specifies the object ID of tenant admin service principal."
        }
      },
      "microserviceSpObjectId": {
        "type": "string",
        "metadata": {
          "description": "Specifies the object ID of Microsoft Dynamics ERP Microservices service principal."
        }
      },
      "storageAccountType": {
        "type": "string",
        "defaultValue": "Standard_LRS",
        "allowedValues": [
          "Standard_LRS",
          "Standard_GRS",
          "Standard_ZRS",
          "Premium_LRS"
        ],
        "metadata": {
          "description": "Storage Account type"
        }
      }
    },
    "variables": {
      "storageAccountApiVersion": "2019-06-01",
      "keyVaultApiVersion": "2018-02-14",
      "secretsPermissions": [
        "list",
        "get"
      ],
      "location": "[resourceGroup().location]",
      "storageAccountName": "[concat('store', uniquestring(resourceGroup().id))]",
      "keyVaultName": "[concat('keyvault', uniquestring(resourceGroup().id))]",
      "owner": "[concat('/subscriptions/', subscription().subscriptionId, '/providers/Microsoft.Authorization/roleDefinitions/', '8e3af657-a8ff-443c-a75c-2fe8c4bcb635')]",
      "contributor": "[concat('/subscriptions/', subscription().subscriptionId, '/providers/Microsoft.Authorization/roleDefinitions/', 'b24988ac-6180-42a0-ab88-20f7382dd24c')]",
      "storageAccountContributor": "[concat('/subscriptions/', subscription().subscriptionId, '/providers/Microsoft.Authorization/roleDefinitions/', '17d1049b-9a84-46fb-8f53-869881c3d3ab')]",
      "storageBlobDataOwner": "[concat('/subscriptions/', subscription().subscriptionId, '/providers/Microsoft.Authorization/roleDefinitions/', 'b7e6dc6d-f1e8-4753-8033-0f276bb0955b')]",
      "storageBlobDataReader": "[concat('/subscriptions/', subscription().subscriptionId, '/providers/Microsoft.Authorization/roleDefinitions/', '2a2b9908-6ea1-4ae2-8e65-a410df84e7d1')]"
    },
    "resources": [
      {
        "type": "Microsoft.Storage/storageAccounts",
        "apiVersion": "[variables('storageAccountApiVersion')]",
        "name": "[variables('storageAccountName')]",
        "location": "[variables('location')]",
        "sku": {
          "name": "[parameters('storageAccountType')]"
        },
        "kind": "StorageV2",
        "properties": {
          "accessTier": "Hot",
          "supportsHttpsTrafficOnly": true,
          "isHnsEnabled": true
        },
        "resources": [
          {
            "type": "Microsoft.Storage/storageAccounts/providers/roleAssignments",
            "apiVersion": "2018-09-01-preview",
            "name": "[concat(variables('storageAccountName'), '/Microsoft.Authorization/', guid(uniqueString(variables('storageAccountName'),'1')))]",
            "dependsOn": [
              "[variables('storageAccountName')]"
            ],
            "properties": {
              "roleDefinitionId": "[variables('owner')]",
              "principalId": "[parameters('clientAppSpObjectId')]"
            }
          },
          {
            "type": "Microsoft.Storage/storageAccounts/providers/roleAssignments",
            "apiVersion": "2018-09-01-preview",
            "name": "[concat(variables('storageAccountName'), '/Microsoft.Authorization/', guid(uniqueString(variables('storageAccountName'),'2')))]",
            "dependsOn": [
              "[variables('storageAccountName')]"
            ],
            "properties": {
              "roleDefinitionId": "[variables('contributor')]",
              "principalId": "[parameters('clientAppSpObjectId')]"
            }
          },
          {
            "type": "Microsoft.Storage/storageAccounts/providers/roleAssignments",
            "apiVersion": "2018-09-01-preview",
            "name": "[concat(variables('storageAccountName'), '/Microsoft.Authorization/', guid(uniqueString(variables('storageAccountName'),'3')))]",
            "dependsOn": [
              "[variables('storageAccountName')]"
            ],
            "properties": {
              "roleDefinitionId": "[variables('storageAccountContributor')]",
              "principalId": "[parameters('clientAppSpObjectId')]"
            }
          },
          {
            "type": "Microsoft.Storage/storageAccounts/providers/roleAssignments",
            "apiVersion": "2018-09-01-preview",
            "name": "[concat(variables('storageAccountName'), '/Microsoft.Authorization/', guid(uniqueString(variables('storageAccountName'),'4')))]",
            "dependsOn": [
              "[variables('storageAccountName')]"
            ],
            "properties": {
              "roleDefinitionId": "[variables('storageBlobDataOwner')]",
              "principalId": "[parameters('clientAppSpObjectId')]"
            }
          },
          {
            "type": "Microsoft.Storage/storageAccounts/providers/roleAssignments",
            "apiVersion": "2018-09-01-preview",
            "name": "[concat(variables('storageAccountName'), '/Microsoft.Authorization/', guid(uniqueString(variables('storageAccountName'),'5')))]",
            "dependsOn": [
              "[variables('storageAccountName')]"
            ],
            "properties": {
              "roleDefinitionId": "[variables('storageBlobDataReader')]",
              "principalId": "[parameters('aibuilderAppObjectId')]"
            }
          }
        ]
      },
      {
        "type": "Microsoft.KeyVault/vaults",
        "apiVersion": "[variables('keyVaultApiVersion')]",
        "name": "[variables('keyVaultName')]",
        "location": "[variables('location')]",
        "dependsOn": [
          "[resourceId('Microsoft.Storage/storageAccounts', variables('storageAccountName'))]"
        ],
        "tags": {
        },
        "properties": {
          "enabledForDeployment": false,
          "enabledForTemplateDeployment": false,
          "enabledForDiskEncryption": false,
          "enableRbacAuthorization": false,
          "accessPolicies": [
            {
              "objectId": "[parameters('clientAppSpObjectId')]",
              "tenantId": "[subscription().tenantId]",
              "permissions": {
                "secrets": "[variables('secretsPermissions')]"
              }
            },
            {
              "objectId": "[parameters('microserviceSpObjectId')]",
              "tenantId": "[subscription().tenantId]",
              "permissions": {
                "secrets": "[variables('secretsPermissions')]"
              }
            },
            {
              "objectId": "[parameters('userSpObjectId')]",
              "tenantId": "[subscription().tenantId]",
              "permissions": {
                "secrets": "[variables('secretsPermissions')]"
              }
            }
          ],
          "tenantId": "[subscription().tenantId]",
          "sku": {
            "name": "Standard",
            "family": "A"
          },
          "enableSoftDelete": false,
          "networkAcls": {
            "defaultAction": "Allow",
            "bypass": "AzureServices"
          }
        }
      },
      {
        "type": "Microsoft.KeyVault/vaults/secrets",
        "name": "[concat(variables('keyVaultName'), '/', 'app-id')]",
        "apiVersion": "[variables('keyVaultApiVersion')]",
        "location": "[variables('location')]",
        "dependsOn": [
          "[resourceId('Microsoft.KeyVault/vaults', variables('keyVaultName'))]"
        ],
        "properties": {
          "value": "[parameters('clientAppId')]"
        }
      },
      {
        "type": "Microsoft.KeyVault/vaults/secrets",
        "name": "[concat(variables('keyVaultName'), '/', 'app-secret')]",
        "apiVersion": "[variables('keyVaultApiVersion')]",
        "location": "[variables('location')]",
        "dependsOn": [
          "[resourceId('Microsoft.KeyVault/vaults', variables('keyVaultName'))]"
        ],
        "properties": {
          "value": "[parameters('clientAppSecret')]"
        }
      },
      {
        "type": "Microsoft.KeyVault/vaults/secrets",
        "name": "[concat(variables('keyVaultName'), '/', 'storage-account-name')]",
        "apiVersion": "[variables('keyVaultApiVersion')]",
        "location": "[variables('location')]",
        "dependsOn": [
          "[resourceId('Microsoft.KeyVault/vaults', variables('keyVaultName'))]"
        ],
        "properties": {
          "value": "[variables('storageAccountName')]"
        }
      },
      {
        "type": "Microsoft.KeyVault/vaults/secrets",
        "name": "[concat(variables('keyVaultName'), '/', 'storage-account-connection-string')]",
        "apiVersion": "[variables('keyVaultApiVersion')]",
        "location": "[variables('location')]",
        "dependsOn": [
          "[resourceId('Microsoft.KeyVault/vaults', variables('keyVaultName'))]"
        ],
        "properties": {
          "value": "[concat('DefaultEndpointsProtocol=https;AccountName=', variables('storageAccountName'), ';AccountKey=', listKeys(resourceId('Microsoft.Storage/storageAccounts', variables('storageAccountName')), variables('storageAccountApiVersion')).keys[0].value, ';EndpointSuffix=core.windows.net')]"
        }
      }
    ],
    "outputs": {
      "storageAccountName": {
        "type": "string",
        "value": "[variables('storageAccountName')]"
      },
      "keyVaultName": {
        "type": "string",
        "value": "[variables('keyVaultName')]"
      }
    }
  }
"@

try {
  Start-Transcript -path (Join-Path $HOME Provision-FinInsights-Azure.log)
  New-FinanceDataLakeAzureResources
}
catch {
  Write-Error $_.Exception.Message

  if ($PSItem.Exception.StackTrace -ne $null)
  {
      Write-Warning $_.Exception.StackTrace
  }

  $inner = $_.Exception.InnerException
  while ($null -ne $inner) {
    Write-Output 'Inner Exception:'
    Write-Error $_.Exception.Message
    Write-Warning $_.Exception.StackTrace
    $inner = $inner.InnerException
  }
}
finally {
  Stop-Transcript
}
```
---

## <a name="configure-the-export-to-data-lake-add-in"></a><span data-ttu-id="d5a9e-266">Konfigurera tillägget Exportera till Data Lake</span><span class="sxs-lookup"><span data-stu-id="d5a9e-266">Configure the Export to Data Lake add-in</span></span>

<span data-ttu-id="d5a9e-267">Följ dessa steg för att använda LCS om du vill lägga till Exportera till Data Lake-tillägget i miljön.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-267">Follow these steps to use LCS to add the Export to Data Lake add-in to the environment.</span></span>

1. <span data-ttu-id="d5a9e-268">Logga in på LCS och välj sedan **Fullständig information** under miljönamnet till höger på sidan.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-268">Sign in to LCS, and then, under the environment name on the right side of the page, select **Full Details**.</span></span>
2. <span data-ttu-id="d5a9e-269">I avsnittet **Miljötillägg**, välj **Installera ett nytt tillägg**.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-269">In the **Environment add-ins** section, select **Install a new add-in**.</span></span>
3. <span data-ttu-id="d5a9e-270">Välj tillägget **Exportera till data Lake**.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-270">Select the **Export to Data Lake** add-in.</span></span>
4. <span data-ttu-id="d5a9e-271">Ange följande värden.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-271">Enter the following values.</span></span>

    | <span data-ttu-id="d5a9e-272">Värde</span><span class="sxs-lookup"><span data-stu-id="d5a9e-272">Value</span></span>                                                              | <span data-ttu-id="d5a9e-273">beskrivning</span><span class="sxs-lookup"><span data-stu-id="d5a9e-273">Description</span></span> |
    |--------------------------------------------------------------------|-------------|
    | <span data-ttu-id="d5a9e-274">Klientorganisations-ID för Azure-prenumerationen där nyckelvalvet finns</span><span class="sxs-lookup"><span data-stu-id="d5a9e-274">Tenant ID of the Azure Subscription where the Key Vault is located</span></span> | <span data-ttu-id="d5a9e-275">Det klientorganisations-ID där lagringskontot, programmen och nyckelvalven finns.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-275">The tenant ID where the storage account, apps, and key vaults are located.</span></span> <span data-ttu-id="d5a9e-276">Du får det här värdet genom att öppna [Azure-portalen](https://portal.azure.com), gå till **Azure Active Directory** och kopiera värdet för **Klientorganisations-ID**.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-276">To obtain this value, open the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**, and copy the **Tenant ID** value.</span></span> |
    | <span data-ttu-id="d5a9e-277">Ange DNS-namnet på ditt Key Vault</span><span class="sxs-lookup"><span data-stu-id="d5a9e-277">Provide the DNS name of your Key Vault</span></span>                             | <span data-ttu-id="d5a9e-278">Nyckelvalvets DNS-namn, till exempel `https://customkeyvault.vault.azure.net/`.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-278">The DNS name of the key vault, such as `https://customkeyvault.vault.azure.net/`.</span></span> |
    | <span data-ttu-id="d5a9e-279">Ange hemligheten som innehåller namnet på lagringskontot</span><span class="sxs-lookup"><span data-stu-id="d5a9e-279">Provide the secret that contains the name of the storage account</span></span>   | <span data-ttu-id="d5a9e-280">**lagringskontonamn**</span><span class="sxs-lookup"><span data-stu-id="d5a9e-280">**storage-account-name**</span></span> |
    | <span data-ttu-id="d5a9e-281">Hemligt namn för det program-ID som ska användas för åtkomst till Data Lake</span><span class="sxs-lookup"><span data-stu-id="d5a9e-281">Secret Name for App ID to be used for accessing Data Lake</span></span>          | <span data-ttu-id="d5a9e-282">**program-ID**</span><span class="sxs-lookup"><span data-stu-id="d5a9e-282">**app-id**</span></span> |
    | <span data-ttu-id="d5a9e-283">Hemligt namn för klienthemlighet för app</span><span class="sxs-lookup"><span data-stu-id="d5a9e-283">Secret name for App client secret</span></span>                                  | <span data-ttu-id="d5a9e-284">**programhemlighet**</span><span class="sxs-lookup"><span data-stu-id="d5a9e-284">**app-secret**</span></span> |

5. <span data-ttu-id="d5a9e-285">Godkänn villkoren och välj sedan **Installera**.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-285">Agree to the terms, and then select **Install**.</span></span>

<span data-ttu-id="d5a9e-286">Tillägget kommer att installeras inom några minuter.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-286">The add-in will be installed within a few minutes.</span></span>

## <a name="configure-the-finance-insights-add-in"></a><span data-ttu-id="d5a9e-287">Konfigurera tillägget Finance Insights</span><span class="sxs-lookup"><span data-stu-id="d5a9e-287">Configure the Finance insights add-in</span></span>

> [!NOTE]
> <span data-ttu-id="d5a9e-288">Om du tidigare installerat tillägget Hämta insikter (Get Insights) avinstallerar du detta innan du slutför följande procedur.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-288">If you previously installed the Get insights add-in, uninstall it before you complete the following procedure.</span></span>

<span data-ttu-id="d5a9e-289">Följ anvisningarna nedan för att installera tillägget Finance Insights.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-289">Follow these steps to install the Finance insights add-in.</span></span>

1. <span data-ttu-id="d5a9e-290">Logga in på LCS och välj sedan **Fullständig information** under miljönamnet till höger på sidan.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-290">Sign in to LCS, and then, under the environment name on the right side of the page, select **Full Details**.</span></span>
2. <span data-ttu-id="d5a9e-291">I avsnittet **Miljötillägg**, välj **Installera ett nytt tillägg**.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-291">In the **Environment add-ins** section, select **Install a new add-in**.</span></span>
3. <span data-ttu-id="d5a9e-292">Välj tillägget **Finance insights**.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-292">Select the **Finance insights** add-in.</span></span>
4. <span data-ttu-id="d5a9e-293">Godkänn villkoren och välj sedan **Installera**.</span><span class="sxs-lookup"><span data-stu-id="d5a9e-293">Agree to the terms, and then select **Install**.</span></span>

## <a name="feedback-and-support"></a><span data-ttu-id="d5a9e-294">Feedback och support</span><span class="sxs-lookup"><span data-stu-id="d5a9e-294">Feedback and support</span></span>

<span data-ttu-id="d5a9e-295">Om du är intresserad av att lämna feedback, eller om du behöver support, skicka då ett e-postmeddelande till [Finance Insights (förhandsversion)](mailto:fiap@microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="d5a9e-295">If you're interested in providing feedback, or if you require support, send an email to [Finance insights (Preview)](mailto:fiap@microsoft.com).</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
