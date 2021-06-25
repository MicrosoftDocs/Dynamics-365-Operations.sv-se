---
title: Konfiguration för Finance Insights – versioner upp till 10.0.19
description: I detta ämne beskrivs de konfigurationssteg som gör att systemet kan använda de funktioner som finns i Finance Insights för versioner upp till 10.0.19.
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
ms.search.validFrom: 2020-07-20
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 6ad06bb6d041fc060b3a99538f6d4d0af333180f
ms.sourcegitcommit: ebcd9019cbb88a7f2afd9e701812e222566fd43d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2021
ms.locfileid: "6186430"
---
# <a name="configuration-for-finance-insights-preview"></a><span data-ttu-id="a8ec6-103">Konfiguration för Finance-insikter (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="a8ec6-103">Configuration for Finance insights (preview)</span></span>

[!include [banner](../includes/banner.md)]

[!include [preview banner](../includes/preview-banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

> [!NOTE]
> <span data-ttu-id="a8ec6-104">Följande procedurer för hur du ställer in Finance Insights gäller för Microsoft Dynamics 365 Finance-versioner upp till 10.0.19.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-104">The following procedures for setting up Finance insights are valid for Microsoft Dynamics 365 Finance versions up to 10.0.19.</span></span> <span data-ttu-id="a8ec6-105">Mer information om hur du ställer in Finance Insights i version 10.0.20 och senare finns i [Konfiguration för Finance Insights (förhandsversion) – versioner 10.0.20 och senare](configure-for-fin-insites-PubPrvw.md).</span><span class="sxs-lookup"><span data-stu-id="a8ec6-105">To set up Finance insights on version 10.0.20 and later, see [Configuration for Finance Insights (preview) - versions 10.0.20 and beyond](configure-for-fin-insites-PubPrvw.md).</span></span>

<span data-ttu-id="a8ec6-106">Ekonomiska insikter kombinerar funktioner från Microsoft Dynamics 365 Finance med Microsoft Dataverse, Azure och AI Builder för att tillhandahålla kraftfulla prognosverktyg för organisationen.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-106">Finance insights combines functionality from Microsoft Dynamics 365 Finance with Microsoft Dataverse, Azure, and AI Builder to provide powerful forecasting tools for your organization.</span></span> <span data-ttu-id="a8ec6-107">I det här avsnittet beskrivs de konfigurationssteg som gör att systemet kan använda de funktioner som finns i Ekonomiska insikter.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-107">This topic explains the configuration steps that will enable your system to use the capabilities that are available in Finance insights.</span></span>

## <a name="deploy-dynamics-365-finance"></a><span data-ttu-id="a8ec6-108">Distribuera Dynamics 365 Finance</span><span class="sxs-lookup"><span data-stu-id="a8ec6-108">Deploy Dynamics 365 Finance</span></span>

<span data-ttu-id="a8ec6-109">Följ dessa steg för att distribuera miljöerna.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-109">Deploy the environments by following these steps.</span></span>

1. <span data-ttu-id="a8ec6-110">I Microsoft Dynamics Lifecycle Services (LCS), skapa eller uppdatera en Dynamics 365 Finance-miljö.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-110">In Microsoft Dynamics Lifecycle Services (LCS), create or update a Dynamics 365 Finance environment.</span></span> <span data-ttu-id="a8ec6-111">Miljön kräver programversion 10.0.11/Platform update 35 eller senare.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-111">The environment requires app version 10.0.11/Platform update 35 or later.</span></span>
2. <span data-ttu-id="a8ec6-112">Miljön måste vara en miljö med hög tillgänglighet (HA) i sandbox-miljö.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-112">The environment must be a high-availability (HA) environment in Sandbox.</span></span> <span data-ttu-id="a8ec6-113">(Den här typen av miljö kallas också för en Nivå-2-miljö.) Mer information finns i [Miljöplanering](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).</span><span class="sxs-lookup"><span data-stu-id="a8ec6-113">(This type of environment is also known as a Tier-2 environment.) For more information, see [Environment planning](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).</span></span>
3. <span data-ttu-id="a8ec6-114">Om du konfigurerar Finance Insights i en sandbox-miljö måste du kanske kopiera produktionsdata till den miljön för att förutsägelser ska fungera.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-114">If you are configuring Finance insights in a Sandbox environment, you might need to copy production data to that environment for predictions to work.</span></span> <span data-ttu-id="a8ec6-115">I modellen för förutsägelse används flera års data för att skapa förutsägelser.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-115">The prediction model uses multiple years of data to build predictions.</span></span> <span data-ttu-id="a8ec6-116">Contoso-demodatan innehåller inte tillräckligt historiska data för att mata förutsägelsemodellen tillräckligt mycket.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-116">The Contoso demo data doesn’t contain enough historical data to train the prediction model adequately.</span></span> 

## <a name="configure-dataverse"></a><span data-ttu-id="a8ec6-117">Konfigurera Dataverse</span><span class="sxs-lookup"><span data-stu-id="a8ec6-117">Configure Dataverse</span></span>

<span data-ttu-id="a8ec6-118">Använd följande steg för att konfigurera Dataverse för Finance insights.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-118">Use the following steps to configure Dataverse for Finance insights.</span></span>

1. <span data-ttu-id="a8ec6-119">Öppna miljösidan i LCS och kontrollera att avsnittet **Power Platform**-integration redan har ställts in.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-119">Open the environment page in LCS and verify that the **Power Platform Integration** section is already setup.</span></span>
    1. <span data-ttu-id="a8ec6-120">Om den redan är inställd ska Dataverse-miljön som är länkat till Dynamics 365 Finance-miljön visas i listan.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-120">If it is already set up, the Dataverse environment name linked to the Dynamics 365 Finance Environment should be listed.</span></span> <span data-ttu-id="a8ec6-121">Kopiera namnet på Dataverse-miljön.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-121">Copy the Dataverse environment name.</span></span>
    2. <span data-ttu-id="a8ec6-122">Om den inte är inställd följer du dessa steg:</span><span class="sxs-lookup"><span data-stu-id="a8ec6-122">If it is not set up, follow these steps:</span></span>
        1. <span data-ttu-id="a8ec6-123">Välj knappen **Inställningar** i avsnittet Power Platform-integrering.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-123">Select the **Setup** button in the Power Platform Integration section.</span></span> <span data-ttu-id="a8ec6-124">Det kan ta upp till en timme innan miljön kan ställas in.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-124">It may take up to an hour for the environment to be set up.</span></span>
        2. <span data-ttu-id="a8ec6-125">Om Dataverse-miljön har ställts in bör det Dataverse-miljönamn som kopplats till Dynamics 365 Finance-miljön listas.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-125">If the Dataverse environment is successfully set up, the Dataverse environment name linked to the Dynamics 365 Finance Environment should be listed.</span></span> <span data-ttu-id="a8ec6-126">Kopiera namnet på Dataverse-miljön.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-126">Copy the Dataverse environment name.</span></span>
> [!NOTE]
> <span data-ttu-id="a8ec6-127">När miljön är klar väljer du **INTE** knappen **Koppla till CDS for Apps**.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-127">After completing the environment set up, **DO NOT** select the **Link to CDS for Apps** button.</span></span> <span data-ttu-id="a8ec6-128">Detta behövs inte för Finance Insights och kommer att inaktivera möjligheten att slutföra de erforderliga miljötilläggen i LCS.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-128">This is not needed for Finance Insights and will disable the ability to complete the required Environment Add-ins in LCS.</span></span>

2. <span data-ttu-id="a8ec6-129">Öppna [Power Platform administrationscenter](https://admin.powerplatform.microsoft.com/) och skapa en ny Dataverse-miljö i samma Active Directory-klientorganisation genom att följa stegen nedan:</span><span class="sxs-lookup"><span data-stu-id="a8ec6-129">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com/), and follow these steps to create a new Dataverse environment in the same Active Directory tenant:</span></span>

    1. <span data-ttu-id="a8ec6-130">Öppna sidan **Miljöer**.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-130">Open the **Environments** page.</span></span>

        <span data-ttu-id="a8ec6-131">[![Sidan Miljöer](./media/power-pltfrm-admin-center.png)](./media/power-pltfrm-admin-center.png)</span><span class="sxs-lookup"><span data-stu-id="a8ec6-131">[![Environments page](./media/power-pltfrm-admin-center.png)](./media/power-pltfrm-admin-center.png)</span></span>

    2. <span data-ttu-id="a8ec6-132">Välj Dataverse-miljön som skapats ovan och välj sedan **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-132">Select the Dataverse environment created above and then select **Settings**.</span></span>
    3. <span data-ttu-id="a8ec6-133">Välj **Resurser \> Alla äldre inställningar**.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-133">Select **Resources \> All Legacy Settings**.</span></span>
    4. <span data-ttu-id="a8ec6-134">Välj **Inställningar** i det övre navigeringsfältet och välj **Anpassningar**.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-134">On the top navigation bar, select **Settings**, and then select **Customizations**.</span></span>
    5. <span data-ttu-id="a8ec6-135">Välj **Utvecklarresurser**.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-135">Select **Developer Resources**.</span></span>
    6. <span data-ttu-id="a8ec6-136">Kopiera värdet för **Organisations-ID för Dataverse**.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-136">Copy the **Dataverse organization ID** value.</span></span>
    7. <span data-ttu-id="a8ec6-137">Notera URL:en till Dataverse-organisationen i webbläsarens adressfält.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-137">In the browser's address bar, make a note of the URL for the Dataverse organization.</span></span> <span data-ttu-id="a8ec6-138">URL-adressen kan till exempel vara `https://org42b2b3d3.crm.dynamics.com`.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-138">For example, the URL might be `https://org42b2b3d3.crm.dynamics.com`.</span></span>

3. <span data-ttu-id="a8ec6-139">Om du planerar att använda kassaflödesprognoser eller budgetprognoser, följer du dessa steg för att uppdatera anteckningsgränsen för organisationen till minst 50 MB:</span><span class="sxs-lookup"><span data-stu-id="a8ec6-139">If you plan to use the Cash flow forecasts or Budget forecasts feature, follow these steps to update the annotation limit for your organization to at least 50 megabytes (MB):</span></span>

    1. <span data-ttu-id="a8ec6-140">Öppna [Power Apps-portal](https://make.powerapps.com).</span><span class="sxs-lookup"><span data-stu-id="a8ec6-140">Open the [Power Apps portal](https://make.powerapps.com).</span></span>
    2. <span data-ttu-id="a8ec6-141">Välj den miljö som du just har skapat och välj sedan **Avancerade inställningar**.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-141">Select the environment that you just created, and then select **Advanced settings**.</span></span>
    3. <span data-ttu-id="a8ec6-142">Välj **Inställningar \> E-postkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-142">Select **Settings \> Email Configuration**.</span></span>
    4. <span data-ttu-id="a8ec6-143">Ändra värdet för fältet **Maximal filstorlek** till **51 200**.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-143">Change the value of the **Maximum file size** field to **51,200**.</span></span> <span data-ttu-id="a8ec6-144">(Värdet uttrycks i kilobyte \[KB\].)</span><span class="sxs-lookup"><span data-stu-id="a8ec6-144">(The value is expressed in kilobytes \[KB\].)</span></span>
    5. <span data-ttu-id="a8ec6-145">Välj **OK** för att spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-145">Select **OK** to save your changes.</span></span>

## <a name="configure-the-azure-setup"></a><span data-ttu-id="a8ec6-146">Konfigurera Azure-inställningen</span><span class="sxs-lookup"><span data-stu-id="a8ec6-146">Configure the Azure setup</span></span>

### <a name="enter-the-dataverse-directory-id-and-the-users-azure-ad-object-id"></a><span data-ttu-id="a8ec6-147">Ange Dataverse-katalog-ID och användarens Azure AD-objekt-ID</span><span class="sxs-lookup"><span data-stu-id="a8ec6-147">Enter the Dataverse directory ID and the user's Azure AD object ID</span></span>

1. <span data-ttu-id="a8ec6-148">Ange Dataverse-katalog-ID:</span><span class="sxs-lookup"><span data-stu-id="a8ec6-148">Enter the Dataverse directory ID:</span></span>

    1. <span data-ttu-id="a8ec6-149">Öppna [Azure-portalen](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="a8ec6-149">Open the [Azure portal](https://portal.azure.com).</span></span>
    2. <span data-ttu-id="a8ec6-150">Logga in genom att använda det användar-ID som användes för att skapa Dataverse-miljön.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-150">Sign in by using the user ID that was used to create the Dataverse environment.</span></span>
    3. <span data-ttu-id="a8ec6-151">Gå till **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-151">Go to **Azure Active Directory**.</span></span>
    4. <span data-ttu-id="a8ec6-152">Kopiera värdet för **Klientorganisations-ID**.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-152">Copy the **Tenant ID** value.</span></span>

2. <span data-ttu-id="a8ec6-153">Ange användarens Azure Active Directory-objekt-ID (Azure AD):</span><span class="sxs-lookup"><span data-stu-id="a8ec6-153">Enter the user's Azure Active Directory (Azure AD) object ID:</span></span>

    1. <span data-ttu-id="a8ec6-154">I [Azure-portalen](https://portal.azure.com), gå till **Användare** och sök efter användaren via e-postadressen.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-154">In the [Azure portal](https://portal.azure.com), go to **Users**, and search for the user by email address.</span></span>
    2. <span data-ttu-id="a8ec6-155">Välj användarens namn.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-155">Select the user's name.</span></span>
    3. <span data-ttu-id="a8ec6-156">Kopiera värdet för **Objekt-ID**.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-156">Copy the **Object ID** value.</span></span>

### <a name="use-azure-cloud-shell-to-set-up-finance-insights-data-lake-resources"></a><span data-ttu-id="a8ec6-157">Använd Azure Cloud Shell för att konfigurera Ekonomiska insikters Data Lake-resurser</span><span class="sxs-lookup"><span data-stu-id="a8ec6-157">Use Azure Cloud Shell to set up Finance insights Data Lake resources</span></span>

# <a name="use-a-windows-powershell-script"></a>[<span data-ttu-id="a8ec6-158">Använd ett Windows PowerShell-skript</span><span class="sxs-lookup"><span data-stu-id="a8ec6-158">Use a Windows PowerShell script</span></span>](#tab/use-a-powershell-script)

<span data-ttu-id="a8ec6-159">Ett Windows PowerShell-skript har angetts så att du enkelt kan ställa in de Azure-resurser som beskrivs i [Konfigurera export till Azure Data Lake](../../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md).</span><span class="sxs-lookup"><span data-stu-id="a8ec6-159">A Windows PowerShell script has been provided, so that you can easily set up the Azure resources that are described in [Configure export to Azure Data Lake](../../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md).</span></span> <span data-ttu-id="a8ec6-160">Om du föredrar att göra manuella inställningar hoppar du över den här proceduren och fortsätter med proceduren i avsnittet [Manuell konfiguration](#manual-setup).</span><span class="sxs-lookup"><span data-stu-id="a8ec6-160">If you prefer to do manual setup, skip this procedure, and continue with the procedure in the [Manual setup](#manual-setup) section.</span></span>

> [!NOTE]
> <span data-ttu-id="a8ec6-161">Kör PowerShell-skriptet genom att följa stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-161">Follow the steps below to run the PowerShell script.</span></span> <span data-ttu-id="a8ec6-162">Azure CLI-alternativet "Pröva" eller att köra skriptet på datorn fungerar kanske inte.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-162">The Azure CLI "Try it" option, or running the script on your PC may not work.</span></span>

<span data-ttu-id="a8ec6-163">Följ dessa steg för att konfigurera Azure med hjälp av Windows PowerShell-skriptet.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-163">Follow these steps to configure Azure by using the Windows PowerShell script.</span></span> <span data-ttu-id="a8ec6-164">Du måste ha behörighet att skapa en Azure-resursgrupp, Azure-resurser och ett Azure AD-program.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-164">You must have rights to create an Azure resource group, Azure resources, and an Azure AD application.</span></span> <span data-ttu-id="a8ec6-165">Information om vilka behörigheter som krävs finns i [Kontrollera Azure AD-behörigheter](/azure/active-directory/develop/howto-create-service-principal-portal#permissions-required-for-registering-an-app).</span><span class="sxs-lookup"><span data-stu-id="a8ec6-165">For information about the required permissions, see [Check Azure AD permissions](/azure/active-directory/develop/howto-create-service-principal-portal#permissions-required-for-registering-an-app).</span></span>

1. <span data-ttu-id="a8ec6-166">I [Azure-portalen](https://portal.azure.com), gå till din mål-Azure-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-166">In the [Azure portal](https://portal.azure.com), go to your target Azure subscription.</span></span> <span data-ttu-id="a8ec6-167">Välj knappen **Cloud Shell** till höger om fältet **Sök**.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-167">Select the **Cloud Shell** button to the right of the **Search** field.</span></span>
2. <span data-ttu-id="a8ec6-168">Välj **PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-168">Select **PowerShell**.</span></span>
3. <span data-ttu-id="a8ec6-169">Skapa lagringsutrymme om du uppmanas göra det.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-169">Create storage if you're prompted to do so.</span></span>
4. <span data-ttu-id="a8ec6-170">Gå till fliken **Azure CLI** och välj **Kopiera**.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-170">Go to the **Azure CLI** tab and select **Copy**.</span></span>  
5. <span data-ttu-id="a8ec6-171">Öppna Anteckningar och klistra in PowerShell-skriptet.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-171">Open Notepad and paste the PowerShell script.</span></span> <span data-ttu-id="a8ec6-172">Spara filen som ConfigureDataLake.ps1.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-172">Save the file as ConfigureDataLake.ps1.</span></span>
6. <span data-ttu-id="a8ec6-173">Ladda upp Windows PowerShell-skriptet till sessionen med hjälp av menyalternativet för uppladdning Cloud Shell.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-173">Upload the Windows PowerShell script to the session using the menu option for upload in Cloud Shell.</span></span>
7. <span data-ttu-id="a8ec6-174">Kör skriptet .\ConfigureDataLake.ps1.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-174">Run the script .\ConfigureDataLake.ps1.</span></span>
8. <span data-ttu-id="a8ec6-175">Kör skriptet genom att följa anvisningarna.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-175">Follow the prompts to run the script.</span></span>
9. <span data-ttu-id="a8ec6-176">Installera tillägget **Exportera till Data Lake** i LCS med hjälp av informationen i skriptets utdata.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-176">Use the information from the script output to install the **Export to Data Lake** add-in in LCS.</span></span>
10. <span data-ttu-id="a8ec6-177">Använd informationen från skriptets utdata för att aktivera entitetsarkivet på sidan **Dataanslutningar** i Finance (**Systemadministration \> Systemparametrar \> Dataanslutningar**).</span><span class="sxs-lookup"><span data-stu-id="a8ec6-177">Use the information from the script output to enable the entity store on the **Data connections** page in Finance (**System administration \> System parameters \> Data connections**).</span></span>

### <a name="manual-setup"></a><span data-ttu-id="a8ec6-178">Manuell konfiguration</span><span class="sxs-lookup"><span data-stu-id="a8ec6-178">Manual setup</span></span>

#### <a name="add-applications-to-the-azure-ad-tenant"></a><span data-ttu-id="a8ec6-179">Lägg till program i Azure AD-klientorganisationen</span><span class="sxs-lookup"><span data-stu-id="a8ec6-179">Add applications to the Azure AD tenant</span></span>

1. <span data-ttu-id="a8ec6-180">I [Azure-portalen](https://portal.azure.com), gå till **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-180">In the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**.</span></span>
2. <span data-ttu-id="a8ec6-181">Välj **Hantera \> Företagsprogram**.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-181">Select **Manage \> Enterprise applications**.</span></span>
3. <span data-ttu-id="a8ec6-182">Sök efter följande program med app-ID.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-182">Search for the following applications by app ID.</span></span>

    | <span data-ttu-id="a8ec6-183">Ansökning</span><span class="sxs-lookup"><span data-stu-id="a8ec6-183">Application</span></span>                              | <span data-ttu-id="a8ec6-184">App-ID</span><span class="sxs-lookup"><span data-stu-id="a8ec6-184">App ID</span></span>                               |
    |------------------------------------------|--------------------------------------|
    | <span data-ttu-id="a8ec6-185">Microsoft Dynamics ERP Microservices</span><span class="sxs-lookup"><span data-stu-id="a8ec6-185">Microsoft Dynamics ERP Microservices</span></span>     | <span data-ttu-id="a8ec6-186">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span><span class="sxs-lookup"><span data-stu-id="a8ec6-186">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span></span> |
    | <span data-ttu-id="a8ec6-187">Microsoft Dynamics ERP Microservices CDS</span><span class="sxs-lookup"><span data-stu-id="a8ec6-187">Microsoft Dynamics ERP Microservices CDS</span></span> | <span data-ttu-id="a8ec6-188">703e2651-d3fc-48f5-942c-74274233dba8</span><span class="sxs-lookup"><span data-stu-id="a8ec6-188">703e2651-d3fc-48f5-942c-74274233dba8</span></span> |
    | <span data-ttu-id="a8ec6-189">AI Builder Authorization Service</span><span class="sxs-lookup"><span data-stu-id="a8ec6-189">AI Builder Authorization Service</span></span>         | <span data-ttu-id="a8ec6-190">ad40333e-9910-4b61-b281-e3aeeb8c3ef3</span><span class="sxs-lookup"><span data-stu-id="a8ec6-190">ad40333e-9910-4b61-b281-e3aeeb8c3ef3</span></span> |

<span data-ttu-id="a8ec6-191">Om du inte hittar något av ovanstående program gör du på följande sätt.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-191">If you can't find any of the preceding applications, try the following steps.</span></span>

1. <span data-ttu-id="a8ec6-192">Välj **Start**-menyn och sök efter **powershell** på den lokala datorn.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-192">On your local machine, select the **Start** menu, and search for **powershell**.</span></span>
2. <span data-ttu-id="a8ec6-193">Markera och håll (eller högerklicka) på **Windows PowerShell** och välj **Kör som administratör**.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-193">Select and hold (or right-click) **Windows PowerShell**, and then select **Run as administrator**.</span></span>
3. <span data-ttu-id="a8ec6-194">Kör följande kommando för att installera modulen **AzureAD**.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-194">Run the following command to install the **AzureAD** module.</span></span>

    `Install-Module -Name AzureAD`

4. <span data-ttu-id="a8ec6-195">Om en NuGet-leverantör krävs för att du ska kunna fortsätta väljer **Y** för att installera den.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-195">If a NuGet provider is required to continue, select **Y** to install it.</span></span>
5. <span data-ttu-id="a8ec6-196">Om meddelandet "Untrusted repository" (Ej betrodd lagringsplats) visas väljer du **Y** för att fortsätta.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-196">If an "Untrusted repository" message appears, select **Y** to continue.</span></span>
6. <span data-ttu-id="a8ec6-197">Kör följande kommandon för varje program som måste läggas till för att du ska kunna lägga till programmet i Azure AD.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-197">For each application that must be added, run the following commands to add the application to Azure AD.</span></span> <span data-ttu-id="a8ec6-198">Logga in som Azure AD-administratör när du uppmanas till det.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-198">When you're prompted, sign in as the Azure AD administrator.</span></span>

    `Connect-AzureAD`

    `New-AzureADServicePrincipal –AppId <AppId>`

#### <a name="create-azure-resources"></a><span data-ttu-id="a8ec6-199">Skapa Azure-resurser</span><span class="sxs-lookup"><span data-stu-id="a8ec6-199">Create Azure resources</span></span>

> [!NOTE]
> <span data-ttu-id="a8ec6-200">Se till att du skapar följande resurser i samma Azure AD-instans som Dataverse-miljön.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-200">Make sure that you create the following resources in the same Azure AD instance as the Dataverse environment.</span></span> <span data-ttu-id="a8ec6-201">Du kan inte använda resurser från en annan Azure AD-instans.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-201">You can't use resources from a different Azure AD instance.</span></span>

1. <span data-ttu-id="a8ec6-202">Skapa ett nytt lagringskonto:</span><span class="sxs-lookup"><span data-stu-id="a8ec6-202">Create a new storage account:</span></span>

    1. <span data-ttu-id="a8ec6-203">Skapa ett lagringskonto i [Azure-portalen](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="a8ec6-203">In the [Azure portal](https://portal.azure.com), create a storage account.</span></span>
    2. <span data-ttu-id="a8ec6-204">I dialogrutan **Skapa lagringskonto**, ställ in följande fält:</span><span class="sxs-lookup"><span data-stu-id="a8ec6-204">In the **Create storage account** dialog box, set the following fields:</span></span>

        - <span data-ttu-id="a8ec6-205">**Plats** – Välj det datacenter där din miljö finns.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-205">**Location** – Select the data center where your environment is located.</span></span>
        - <span data-ttu-id="a8ec6-206">**Prestanda** – Vi rekommenderar att du väljer **Standard**.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-206">**Performance** – We recommend that you select **Standard**.</span></span>
        - <span data-ttu-id="a8ec6-207">**Kontotyp** – Du måste välja **StorageV2**.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-207">**Account kind** – You must select **StorageV2**.</span></span>

    3. <span data-ttu-id="a8ec6-208">I dialogrutan **Avancerade alternativ**, för alternativet **Data Lake Storage Gen2** väljer du **Aktivera** under funktionen **Hierarkiska namnrymder**.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-208">In the **Advanced options** dialog box, for the **Data Lake storage Gen2** option, select **Enable** under the **Hierarchical namespaces** feature.</span></span> <span data-ttu-id="a8ec6-209">Om du inaktiverar den här funktionen kan du inte använda data som Finance and Operations-appar skriver med hjälp av tjänster som Power BI-dataflöden.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-209">If you disable this feature, you can't consume data that Finance and Operations apps write by using services such as Power BI data flows.</span></span>
    4. <span data-ttu-id="a8ec6-210">Välj **Granska och skapa**.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-210">Select **Review and create**.</span></span> <span data-ttu-id="a8ec6-211">När distributionen har slutförts visas den nya resursen i Azure-portalen.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-211">When the deployment is completed, the new resource will be shown in the Azure portal.</span></span>
    5. <span data-ttu-id="a8ec6-212">Gå till det lagringskonto som du har skapat.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-212">Go to the storage account that you created.</span></span>
    6. <span data-ttu-id="a8ec6-213">Välj **Åtkomstnycklar** i menyn till vänster.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-213">On the left menu, select **Access keys**.</span></span>
    7. <span data-ttu-id="a8ec6-214">Kopiera och spara anslutningssträngen för antingen **Key1** eller **Key2**.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-214">Copy and save the connection string for either **Key1** or **Key2**.</span></span>
    8. <span data-ttu-id="a8ec6-215">Kopiera och spara namnet på lagringskontot.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-215">Copy and save the storage account name.</span></span>

2. <span data-ttu-id="a8ec6-216">Skapa en ny nyckelvalvresurs:</span><span class="sxs-lookup"><span data-stu-id="a8ec6-216">Create a new key vault:</span></span>

    1. <span data-ttu-id="a8ec6-217">Skapa ett nyckelvalv i [Azure-portalen](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="a8ec6-217">In the [Azure portal](https://portal.azure.com), create a key vault.</span></span>
    2. <span data-ttu-id="a8ec6-218">I dialogrutan **Skapa nyckelvalv**, i fältet **Plats**, välj det datacenter där din miljö finns.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-218">In the **Create key vault** dialog box, in the **Location** field, select the data center where your environment is located.</span></span>
    3. <span data-ttu-id="a8ec6-219">När nyckelvalvet har skapats väljer du det i listan och väljer sedan **Hemligheter**.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-219">After key vault is created, select it in the list, and then select **Secrets**.</span></span>
    4. <span data-ttu-id="a8ec6-220">Välj **Generera/Importera**.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-220">Select **Generate/Import**.</span></span>
    5. <span data-ttu-id="a8ec6-221">I dialogrutan **Skapa en hemlighet** i fältet **Överföringsalternativ** välj **Manuell**.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-221">In the **Create a secret** dialog box, in the **Upload options** field, select **Manual**.</span></span>
    6. <span data-ttu-id="a8ec6-222">Ange ett namn på hemligheten.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-222">Enter a name for the secret.</span></span> <span data-ttu-id="a8ec6-223">Anteckna namnet eftersom du kommer att behöva ange det senare.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-223">Make a note of the name, because you will have to provide it later.</span></span>
    7. <span data-ttu-id="a8ec6-224">I fältet **Värde** anger du den anslutningssträng som du hämtade från lagringskontot i föregående procedur.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-224">In the **Value** field, enter the connection string that you obtained from the storage account in the previous procedure.</span></span>
    8. <span data-ttu-id="a8ec6-225">Välj **Aktiverat** och välj sedan **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-225">Select **Enabled**, and then select **Create**.</span></span> <span data-ttu-id="a8ec6-226">Hemligheten skapas och läggs till i nyckelvalvet.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-226">The secret is created and added to Key Vault.</span></span>
    9. <span data-ttu-id="a8ec6-227">Gå till **nyckelvalvöversikten** och anteckna DNS-namnet.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-227">Go to the **Key Vault Overview**, and make a note of the DNS name.</span></span>

3. <span data-ttu-id="a8ec6-228">Skapa och registrera ett Azure AD-program:</span><span class="sxs-lookup"><span data-stu-id="a8ec6-228">Create and register an Azure AD application:</span></span>

    1. <span data-ttu-id="a8ec6-229">I [Azure-portalen](https://portal.azure.com), gå till **Azure Active Directory** och välj **Appregistreringar**.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-229">In the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**, and then select **App registrations**.</span></span>
    2. <span data-ttu-id="a8ec6-230">Välj **Ny programregistrering** och ange följande fält:</span><span class="sxs-lookup"><span data-stu-id="a8ec6-230">Select **New application registration**, and set the following fields:</span></span>

        - <span data-ttu-id="a8ec6-231">**Namn** – Ange namnet på appen.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-231">**Name** – Enter the name of the app.</span></span>
        - <span data-ttu-id="a8ec6-232">**Programtyp** – Välj **Webb-API**.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-232">**Application type** – Select **Web API**.</span></span>
        - <span data-ttu-id="a8ec6-233">**Inställning av omdirigerings-URI** – Ange URL:en för din Dynamics 365-instans, till exempel `https://yourdynamicsinstance.dynamics.com/auth`.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-233">**Redirect URI setup** – Enter the URL for your Dynamics 365 instance, such as, `https://yourdynamicsinstance.dynamics.com/auth`.</span></span>

    3. <span data-ttu-id="a8ec6-234">Gå till den app som du just skapade och kopiera och spara dess värde för **Program-ID (klient)**.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-234">Go to the app that you just created, and copy and save its **Application (client) ID** value.</span></span> <span data-ttu-id="a8ec6-235">Du måste ange det här värdet senare när du konfigurerar nyckelvalvet.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-235">You will have to provide this value later, when you set up the key vault.</span></span>
    4. <span data-ttu-id="a8ec6-236">Gå till **API-behörigheter** och gör så här:</span><span class="sxs-lookup"><span data-stu-id="a8ec6-236">Go to **API permissions**, and follow these steps:</span></span>

        1. <span data-ttu-id="a8ec6-237">Välj **Lägg till behörighet**.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-237">Select **Add a permission**.</span></span>
        2. <span data-ttu-id="a8ec6-238">Välj **Azure Key Vault**.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-238">Select **Azure Key vault**.</span></span>
        3. <span data-ttu-id="a8ec6-239">När du har valt delegerade behörigheter väljer du **användare\_personifiering**.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-239">After you select delegated permissions, select **user\_impersonation**.</span></span>
        4. <span data-ttu-id="a8ec6-240">Välj **Lägg till behörigheter**.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-240">Select **Add permissions**.</span></span>

    5. <span data-ttu-id="a8ec6-241">På menyn för appen väljer du **Certifikat \& hemligheter** och följer sedan stegen nedan för att skapa nyckelvalvhemligheter:</span><span class="sxs-lookup"><span data-stu-id="a8ec6-241">On the menu for the app, select **Certificates \& secrets**, and then follow these steps to create Key Vault secrets:</span></span>

        1. <span data-ttu-id="a8ec6-242">Välj **Ny klienthemlighet**.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-242">Select **New client secret**.</span></span>
        2. <span data-ttu-id="a8ec6-243">Ange ett namn i fältet **Nyckelbeskrivning**.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-243">In the **Key Description** field, enter a name.</span></span>
        3. <span data-ttu-id="a8ec6-244">Markera en varaktighet och välj sedan **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-244">Select a duration, and then select **Add**.</span></span> <span data-ttu-id="a8ec6-245">En hemlighet genereras i fältet **Värde**.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-245">A secret is generated in the **Value** field.</span></span>
        4. <span data-ttu-id="a8ec6-246">Kopiera och spara det hemliga värdet.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-246">Copy and save the secret value.</span></span>

4. <span data-ttu-id="a8ec6-247">Skapa nyckelvalvhemligheter:</span><span class="sxs-lookup"><span data-stu-id="a8ec6-247">Create Key Vault secrets:</span></span>

    1. <span data-ttu-id="a8ec6-248">Gå till det nyckelvalv som du skapade tidigare och välj **Hemligheter**.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-248">Go to the key vault that you created earlier, and select **Secrets**.</span></span>
    2. <span data-ttu-id="a8ec6-249">Gör så här för varje hemligt namn i följande tabell:</span><span class="sxs-lookup"><span data-stu-id="a8ec6-249">For each secret name in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="a8ec6-250">Välj **Generera/Importera**.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-250">Select **Generate/Import**.</span></span>
        2. <span data-ttu-id="a8ec6-251">I dialogrutan **Skapa en hemlighet** i fältet **Överföringsalternativ** välj **Manuell**.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-251">In the **Create a secret** dialog box, in the **Upload options** field, select **Manual**.</span></span>
        3. <span data-ttu-id="a8ec6-252">Skapa det hemliga namnet och värdet från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-252">Create the secret name and value from the following table.</span></span>
        4. <span data-ttu-id="a8ec6-253">Välj **Aktiverat** och välj sedan **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-253">Select **Enabled**, and then select **Create**.</span></span> <span data-ttu-id="a8ec6-254">Hemligheten skapas och läggs till i nyckelvalvet.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-254">The secret is created and added to Key Vault.</span></span>

        | <span data-ttu-id="a8ec6-255">Hemligt namn</span><span class="sxs-lookup"><span data-stu-id="a8ec6-255">Secret name</span></span>                       | <span data-ttu-id="a8ec6-256">Hemligt värde</span><span class="sxs-lookup"><span data-stu-id="a8ec6-256">Secret value</span></span>                                                                                |
        |-----------------------------------|---------------------------------------------------------------------------------------------|
        | <span data-ttu-id="a8ec6-257">program-ID</span><span class="sxs-lookup"><span data-stu-id="a8ec6-257">app-id</span></span>                            | <span data-ttu-id="a8ec6-258">App-ID för programmet som du skapade tidigare</span><span class="sxs-lookup"><span data-stu-id="a8ec6-258">The app ID of the application that you created earlier</span></span>                                      |
        | <span data-ttu-id="a8ec6-259">programhemlighet</span><span class="sxs-lookup"><span data-stu-id="a8ec6-259">app-secret</span></span>                        | <span data-ttu-id="a8ec6-260">Klienthemligheten som du sparade tidigare</span><span class="sxs-lookup"><span data-stu-id="a8ec6-260">The client secret that you saved earlier</span></span>                                                    |
        | <span data-ttu-id="a8ec6-261">lagringskontonamn</span><span class="sxs-lookup"><span data-stu-id="a8ec6-261">storage-account-name</span></span>              | <span data-ttu-id="a8ec6-262">Namnet på lagringskontot som du skapade tidigare, t.ex. **lagringskonto1**</span><span class="sxs-lookup"><span data-stu-id="a8ec6-262">The name of the storage account that you created earlier, such as **storageaccount1**</span></span>       |
        | <span data-ttu-id="a8ec6-263">lagringskontots anslutningssträng</span><span class="sxs-lookup"><span data-stu-id="a8ec6-263">storage-account-connection-string</span></span> | <span data-ttu-id="a8ec6-264">Den anslutningssträng som du kopierade från sidan **Åtkomstnycklar** för lagringskontot</span><span class="sxs-lookup"><span data-stu-id="a8ec6-264">The connection string that you copied from the **Access keys** page for the storage account</span></span> |

5. <span data-ttu-id="a8ec6-265">Auktorisera programmet för att få åtkomst till nyckelvalvet:</span><span class="sxs-lookup"><span data-stu-id="a8ec6-265">Authorize the application to access the key vault:</span></span>

    1. <span data-ttu-id="a8ec6-266">I [Azure-portalen](https://portal.azure.com), öppna nyckelvalvet som du skapade tidigare.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-266">In the [Azure portal](https://portal.azure.com), open the key vault that you created earlier.</span></span>
    2. <span data-ttu-id="a8ec6-267">Välj åtkomstprinciper.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-267">Select the access policies.</span></span>
    3. <span data-ttu-id="a8ec6-268">Gör så här för varje program i följande tabell:</span><span class="sxs-lookup"><span data-stu-id="a8ec6-268">For each application in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="a8ec6-269">Välj **Lägg till åtkomstprincip** för att skapa en åtkomstprincip.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-269">Select **Add Access Policy** to create an access policy.</span></span>
        2. <span data-ttu-id="a8ec6-270">I fältet **Hemliga behörigheter**, välj behörigheterna från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-270">In the **Secret permissions** field, select the permissions from the following table.</span></span>
        3. <span data-ttu-id="a8ec6-271">I fältet **Välj huvudnamn**, sök efter programmets visningsnamn från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-271">In the **Select principal** field, search for the application display name from the following table.</span></span>
        4. <span data-ttu-id="a8ec6-272">Välj **Välj**.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-272">Select **Select**.</span></span>
        5. <span data-ttu-id="a8ec6-273">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-273">Select **Add**.</span></span>
        6. <span data-ttu-id="a8ec6-274">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-274">Select **Save**.</span></span>

        | <span data-ttu-id="a8ec6-275">Ansökning</span><span class="sxs-lookup"><span data-stu-id="a8ec6-275">Application</span></span>                                              | <span data-ttu-id="a8ec6-276">Behörighet</span><span class="sxs-lookup"><span data-stu-id="a8ec6-276">Permissions</span></span> |
        |----------------------------------------------------------|-------------|
        | <span data-ttu-id="a8ec6-277">Visningsnamnet för det nya program som du skapade</span><span class="sxs-lookup"><span data-stu-id="a8ec6-277">The display name of the new application that you created</span></span> | <span data-ttu-id="a8ec6-278">Get, List</span><span class="sxs-lookup"><span data-stu-id="a8ec6-278">Get, List</span></span>   |
        | <span data-ttu-id="a8ec6-279">**Microsoft Dynamics ERP Microservices**</span><span class="sxs-lookup"><span data-stu-id="a8ec6-279">**Microsoft Dynamics ERP Microservices**</span></span>                 | <span data-ttu-id="a8ec6-280">Get, List</span><span class="sxs-lookup"><span data-stu-id="a8ec6-280">Get, List</span></span>   |

6. <span data-ttu-id="a8ec6-281">Tilldela roller för åtkomst till lagringskontot:</span><span class="sxs-lookup"><span data-stu-id="a8ec6-281">Assign roles to access the storage account:</span></span>

    1. <span data-ttu-id="a8ec6-282">I [Azure-portalen](https://portal.azure.com), öppna lagringskontot som du skapade tidigare.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-282">In the [Azure portal](https://portal.azure.com), open the storage account that you created earlier.</span></span>
    2. <span data-ttu-id="a8ec6-283">Välj **Åtkomstkontroll (IAM)** och välj **Rolltilldelningar**.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-283">Select **Access Control (IAM)**, and then select **Role Assignments**.</span></span>
    3. <span data-ttu-id="a8ec6-284">Välj **Lägg till, Lägg till rolltilldelning**.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-284">Select **Add, Add Role Assignment**.</span></span>
    4. <span data-ttu-id="a8ec6-285">Gör så här för varje program i följande tabell:</span><span class="sxs-lookup"><span data-stu-id="a8ec6-285">For each application in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="a8ec6-286">Välj rollen bland i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-286">Select the role from the following table.</span></span>
        2. <span data-ttu-id="a8ec6-287">Låt fältet **Tilldela åtkomst till** vara inställt på **Azure AD-användare, -grupp eller -tjänstens huvudnamn**.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-287">Leave the **Assign access to** field set to **Azure AD user, group, or service principal**.</span></span>
        3. <span data-ttu-id="a8ec6-288">I fältet **Välj**, ange programmet från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-288">In the **Select** field, enter the application from the following table.</span></span>
        4. <span data-ttu-id="a8ec6-289">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-289">Select **Save**.</span></span>

        | <span data-ttu-id="a8ec6-290">Ansökning</span><span class="sxs-lookup"><span data-stu-id="a8ec6-290">Application</span></span>                                              | <span data-ttu-id="a8ec6-291">Roll</span><span class="sxs-lookup"><span data-stu-id="a8ec6-291">Role</span></span>                        |
        |----------------------------------------------------------|-----------------------------|
        | <span data-ttu-id="a8ec6-292">Visningsnamnet för det nya program som du skapade</span><span class="sxs-lookup"><span data-stu-id="a8ec6-292">The display name of the new application that you created</span></span> | <span data-ttu-id="a8ec6-293">Ägare</span><span class="sxs-lookup"><span data-stu-id="a8ec6-293">Owner</span></span>                       |
        | <span data-ttu-id="a8ec6-294">Visningsnamnet för det nya program som du skapade</span><span class="sxs-lookup"><span data-stu-id="a8ec6-294">The display name of the new application that you created</span></span> | <span data-ttu-id="a8ec6-295">Deltagare</span><span class="sxs-lookup"><span data-stu-id="a8ec6-295">Contributor</span></span>                 |
        | <span data-ttu-id="a8ec6-296">Visningsnamnet för det nya program som du skapade</span><span class="sxs-lookup"><span data-stu-id="a8ec6-296">The display name of the new application that you created</span></span> | <span data-ttu-id="a8ec6-297">Lagringskontodeltagare</span><span class="sxs-lookup"><span data-stu-id="a8ec6-297">Storage Account Contributor</span></span> |
        | <span data-ttu-id="a8ec6-298">Visningsnamnet för det nya program som du skapade</span><span class="sxs-lookup"><span data-stu-id="a8ec6-298">The display name of the new application that you created</span></span> | <span data-ttu-id="a8ec6-299">Storage Blob Data-ägare</span><span class="sxs-lookup"><span data-stu-id="a8ec6-299">Storage Blob Data Owner</span></span>     |
        | <span data-ttu-id="a8ec6-300">**AI Builder Authorization Service**</span><span class="sxs-lookup"><span data-stu-id="a8ec6-300">**AI Builder Authorization Service**</span></span>                     | <span data-ttu-id="a8ec6-301">Storage Blob Data-läsare</span><span class="sxs-lookup"><span data-stu-id="a8ec6-301">Storage Blob Data Reader</span></span>    |

# <a name="azure-cli"></a>[<span data-ttu-id="a8ec6-302">Azure CLI</span><span class="sxs-lookup"><span data-stu-id="a8ec6-302">Azure CLI</span></span>](#tab/azure-azure-cli)

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



## <a name="configure-the-data-lake"></a><span data-ttu-id="a8ec6-303">Konfigurera datasjön</span><span class="sxs-lookup"><span data-stu-id="a8ec6-303">Configure the data lake</span></span>

<span data-ttu-id="a8ec6-304">Följ dessa steg för att använda LCS för att lägga till Azure Data Lake-tillägget i miljön.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-304">Follow these steps to use LCS to add the Azure Data Lake add-in to the environment.</span></span>

1. <span data-ttu-id="a8ec6-305">Logga in på LCS och välj sedan **Fullständig information** under miljönamnet till höger på sidan.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-305">Sign in to LCS, and then, under the environment name on the right side of the page, select **Full Details**.</span></span>
2. <span data-ttu-id="a8ec6-306">I avsnittet **Miljötillägg**, välj **Installera ett nytt tillägg**.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-306">In the **Environment add-ins** section, select **Install a new add-in**.</span></span>
3. <span data-ttu-id="a8ec6-307">Välj tillägget **Exportera till data Lake**.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-307">Select the **Export to Data Lake** add-in.</span></span>
4. <span data-ttu-id="a8ec6-308">Ange följande värden.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-308">Enter the following values.</span></span>

    | <span data-ttu-id="a8ec6-309">Värde</span><span class="sxs-lookup"><span data-stu-id="a8ec6-309">Value</span></span>                                                              | <span data-ttu-id="a8ec6-310">beskrivning</span><span class="sxs-lookup"><span data-stu-id="a8ec6-310">Description</span></span> |
    |--------------------------------------------------------------------|-------------|
    | <span data-ttu-id="a8ec6-311">Klientorganisations-ID för Azure-prenumerationen där nyckelvalvet finns</span><span class="sxs-lookup"><span data-stu-id="a8ec6-311">Tenant ID of the Azure Subscription where the Key Vault is located</span></span> | <span data-ttu-id="a8ec6-312">Det klientorganisations-ID där lagringskontot, programmen och nyckelvalven finns.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-312">The tenant ID where the storage account, apps, and key vaults are located.</span></span> <span data-ttu-id="a8ec6-313">Du hittar det här värdet genom att öppna [Azure-portalen](https://portal.azure.com), gå till **Azure Active Directory** och kopiera värdet för **Klientorganisations-ID**.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-313">To find this value, open the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**, and copy the **Tenant ID** value.</span></span> |
    | <span data-ttu-id="a8ec6-314">Ange DNS-namnet på ditt Key Vault</span><span class="sxs-lookup"><span data-stu-id="a8ec6-314">Provide the DNS name of your Key Vault</span></span>                             | <span data-ttu-id="a8ec6-315">Nyckelvalvets DNS-namn, till exempel `https://customkeyvault.vault.azure.net/`.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-315">The DNS name of the key vault, such as `https://customkeyvault.vault.azure.net/`.</span></span> <span data-ttu-id="a8ec6-316">(Det här värdet matchar DNS-namnet som används i entitetsarkivet.)</span><span class="sxs-lookup"><span data-stu-id="a8ec6-316">(This value matches the DNS name that is used in the entity store.)</span></span> |
    | <span data-ttu-id="a8ec6-317">Ange hemligheten som innehåller namnet på lagringskontot</span><span class="sxs-lookup"><span data-stu-id="a8ec6-317">Provide the secret that contains the name of the storage account</span></span>   | <span data-ttu-id="a8ec6-318">**lagringskontonamn**</span><span class="sxs-lookup"><span data-stu-id="a8ec6-318">**storage-account-name**</span></span> |
    | <span data-ttu-id="a8ec6-319">Hemligt namn för det program-ID som ska användas för åtkomst till Data Lake</span><span class="sxs-lookup"><span data-stu-id="a8ec6-319">Secret Name for App ID to be used for accessing Data Lake</span></span>          | <span data-ttu-id="a8ec6-320">**program-ID**</span><span class="sxs-lookup"><span data-stu-id="a8ec6-320">**app-id**</span></span> |
    | <span data-ttu-id="a8ec6-321">Hemligt namn som ska användas med program-ID</span><span class="sxs-lookup"><span data-stu-id="a8ec6-321">Secret name to be used with App ID</span></span>                                 | <span data-ttu-id="a8ec6-322">**programhemlighet**</span><span class="sxs-lookup"><span data-stu-id="a8ec6-322">**app-secret**</span></span> |

5. <span data-ttu-id="a8ec6-323">Godkänn villkoren och välj **Installera**.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-323">Agree to the terms, and select **Install**.</span></span>

<span data-ttu-id="a8ec6-324">Tillägget kommer att installeras inom några minuter.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-324">The add-in will be installed within a few minutes.</span></span>

## <a name="configure-ai-builder"></a><span data-ttu-id="a8ec6-325">Konfigurera AI Builder</span><span class="sxs-lookup"><span data-stu-id="a8ec6-325">Configure AI Builder</span></span>

1. <span data-ttu-id="a8ec6-326">Logga in på LCS och öppna sidan **Miljöinformation**.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-326">Sign in to LCS, and open the **Environment details** page.</span></span>
2. <span data-ttu-id="a8ec6-327">Bläddra till avsnittet **Miljötillägg**.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-327">Scroll to the **Environment add-ins** section.</span></span> <span data-ttu-id="a8ec6-328">De tillägg som redan är installerade i den här miljön bör visas.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-328">You should see the add-ins that are already installed in this environment.</span></span> <span data-ttu-id="a8ec6-329">Om tillägget **Exportera till Data Lake** inte är bland dem konfigurerar du det här tillägget.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-329">If the **Export to Data Lake** add-in isn't among them, configure this add-in.</span></span>
3. <span data-ttu-id="a8ec6-330">Välj tillägget **Hämta insikter**.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-330">Select the **Get insights** add-in.</span></span>
4. <span data-ttu-id="a8ec6-331">Ange följande värden på informationssidan för tillägget **Hämta insikter**.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-331">On the **Get insights** add-in details page, enter the following values.</span></span>

    | <span data-ttu-id="a8ec6-332">Värde</span><span class="sxs-lookup"><span data-stu-id="a8ec6-332">Value</span></span>                                                    | <span data-ttu-id="a8ec6-333">beskrivning</span><span class="sxs-lookup"><span data-stu-id="a8ec6-333">Description</span></span> |
    |----------------------------------------------------------|-------------|
    | <span data-ttu-id="a8ec6-334">URL för CDS-organisations</span><span class="sxs-lookup"><span data-stu-id="a8ec6-334">CDS Organization URL</span></span>                                     | <span data-ttu-id="a8ec6-335">Dataverse-organisationens URL kopierat från ovan.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-335">The Dataverse organization URL copied from above.</span></span> |
    | <span data-ttu-id="a8ec6-336">CDS Org-ID</span><span class="sxs-lookup"><span data-stu-id="a8ec6-336">CDS Org ID</span></span>                                               | <span data-ttu-id="a8ec6-337">Dataverse-organisationens ID kopierat från ovan.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-337">The Dataverse organization ID copied from above.</span></span> |
5. <span data-ttu-id="a8ec6-338">Aktivera **Är detta standardmiljön för din klientorganisation**.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-338">Enable **Is this the default environment for you Tenant**.</span></span>
    
## <a name="configure-the-entity-store"></a><span data-ttu-id="a8ec6-339">Konfigurera entitetsarkivet</span><span class="sxs-lookup"><span data-stu-id="a8ec6-339">Configure the entity store</span></span>

<span data-ttu-id="a8ec6-340">Följ dessa steg för att konfigurera entitetsarkivet i Finance-miljön.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-340">Follow these steps to set up the entity store in your Finance environment.</span></span>

1. <span data-ttu-id="a8ec6-341">Gå till **Systemadministration \> Konfigurera \> Systemparametrar \> Dataanslutningar**.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-341">Go to **System administration \> Setup \> System parameters \> Data connections**.</span></span>
2. <span data-ttu-id="a8ec6-342">Ange följande nyckelvalvsfält:</span><span class="sxs-lookup"><span data-stu-id="a8ec6-342">Set the following key vault fields:</span></span>

    - <span data-ttu-id="a8ec6-343">**Program-ID (klient)** – Ange programmets klient-ID som du skapade tidigare.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-343">**Application (client) ID** – Enter the application client ID that you created earlier.</span></span>
    - <span data-ttu-id="a8ec6-344">**Programhemlighet** – Ange hemligheten som du sparade för programmet du skapade tidigare.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-344">**Application Secret** – Enter the secret that you saved for the application that you created earlier.</span></span>
    - <span data-ttu-id="a8ec6-345">**DNS-namn** – Du hittar DNS-namnet (Domain Name System) på sidan med programinformation för programmet som du skapade tidigare.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-345">**DNS name** – You can find the Domain Name System (DNS) name on the application details page for the application that you created earlier.</span></span>
    - <span data-ttu-id="a8ec6-346">**Hemligt namn** – Ange **lagringskontots anslutningssträng**.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-346">**Secret name** – Enter **storage-account-connection-string**.</span></span>
3. <span data-ttu-id="a8ec6-347">Aktivera **Aktivera Data Lake-integrering**.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-347">Enable **Enable Data Lake integration**.</span></span>
4. <span data-ttu-id="a8ec6-348">Välj **Testa Azure Key Vault** och kontrollera att det inte finns några fel.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-348">Select **Test Azure Key Vault** and verify there are no errors.</span></span>
5. <span data-ttu-id="a8ec6-349">Välj **Testa Azure-lagring** och kontrollera att det inte finns några fel.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-349">Select **Test Azure storage** and verify there are no errors.</span></span>

## <a name="feedback-and-support"></a><span data-ttu-id="a8ec6-350">Feedback och support</span><span class="sxs-lookup"><span data-stu-id="a8ec6-350">Feedback and support</span></span>

<span data-ttu-id="a8ec6-351">Skicka ett e-postmeddelande till [Kundbetalningsinsikter (förhandsversion)](mailto:fiap@microsoft.com) om du är intresserad av att ge feedback eller behöver support.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-351">Please send an email to [Customer payment insights (Preview)](mailto:fiap@microsoft.com) if you are interested in providing feedback or need support.</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="a8ec6-352">Sekretesspolicy</span><span class="sxs-lookup"><span data-stu-id="a8ec6-352">Privacy notice</span></span>

<span data-ttu-id="a8ec6-353">Förhandsversioner (1) kan använda färre sekretess- och säkerhetsfunktioner än Dynamics 365 Finance and Operations, (2) de ingår inte i serviceavtalet (SLA) för den här tjänsten, (3) bör inte användas för behandling av personuppgifter eller andra uppgifter som omfattas av lagar och andra efterlevnadskrav, samt (4) har begränsad support.</span><span class="sxs-lookup"><span data-stu-id="a8ec6-353">Previews (1) might use less privacy and fewer security measures than the Dynamics 365 Finance and Operations service, (2) aren't included in the service level agreement (SLA) for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) have limited support.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
