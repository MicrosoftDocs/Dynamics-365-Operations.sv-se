---
title: Konfiguration för Finance-insikter (förhandsversion)
description: I det här avsnittet beskrivs de konfigurationssteg som gör att systemet kan använda de funktioner som finns i Ekonomiska insikter.
author: ShivamPandey-msft
ms.date: 11/25/2020
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
ms.openlocfilehash: 60e4d69157d7b73bd9e47310adae320687230080
ms.sourcegitcommit: a202bf67c3c2c054e2a47cb7b3145cb7c0ee635e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/25/2021
ms.locfileid: "5941236"
---
# <a name="configuration-for-finance-insights-preview"></a><span data-ttu-id="53ef7-103">Konfiguration för Finance-insikter (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="53ef7-103">Configuration for Finance insights (preview)</span></span>

[!include [banner](../includes/banner.md)]

[!include [preview banner](../includes/preview-banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="53ef7-104">Ekonomiska insikter kombinerar funktioner från Microsoft Dynamics 365 Finance med Microsoft Dataverse, Azure och AI Builder för att tillhandahålla kraftfulla prognosverktyg för organisationen.</span><span class="sxs-lookup"><span data-stu-id="53ef7-104">Finance insights combines functionality from Microsoft Dynamics 365 Finance with Microsoft Dataverse, Azure, and AI Builder to provide powerful forecasting tools for your organization.</span></span> <span data-ttu-id="53ef7-105">I det här avsnittet beskrivs de konfigurationssteg som gör att systemet kan använda de funktioner som finns i Ekonomiska insikter.</span><span class="sxs-lookup"><span data-stu-id="53ef7-105">This topic explains the configuration steps that will enable your system to use the capabilities that are available in Finance insights.</span></span>

## <a name="deploy-dynamics-365-finance"></a><span data-ttu-id="53ef7-106">Distribuera Dynamics 365 Finance</span><span class="sxs-lookup"><span data-stu-id="53ef7-106">Deploy Dynamics 365 Finance</span></span>

<span data-ttu-id="53ef7-107">Följ dessa steg för att distribuera miljöerna.</span><span class="sxs-lookup"><span data-stu-id="53ef7-107">Deploy the environments by following these steps.</span></span>

1. <span data-ttu-id="53ef7-108">I Microsoft Dynamics Lifecycle Services (LCS), skapa eller uppdatera en Dynamics 365 Finance-miljö.</span><span class="sxs-lookup"><span data-stu-id="53ef7-108">In Microsoft Dynamics Lifecycle Services (LCS), create or update a Dynamics 365 Finance environment.</span></span> <span data-ttu-id="53ef7-109">Miljön kräver programversion 10.0.11/Platform update 35 eller senare.</span><span class="sxs-lookup"><span data-stu-id="53ef7-109">The environment requires app version 10.0.11/Platform update 35 or later.</span></span>
2. <span data-ttu-id="53ef7-110">Miljön måste vara en miljö med hög tillgänglighet (HA) i sandbox-miljö.</span><span class="sxs-lookup"><span data-stu-id="53ef7-110">The environment must be a high-availability (HA) environment in Sandbox.</span></span> <span data-ttu-id="53ef7-111">(Den här typen av miljö kallas också för en Nivå-2-miljö.) Mer information finns i [Miljöplanering](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).</span><span class="sxs-lookup"><span data-stu-id="53ef7-111">(This type of environment is also known as a Tier-2 environment.) For more information, see [Environment planning](../../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md).</span></span>
3. <span data-ttu-id="53ef7-112">Om du använder Contoso-demodata behöver du ytterligare exempeldata för att kunna använda funktionerna för kundbetalningsförutsägelser, kassaflödesprognoser och budgetprognoser.</span><span class="sxs-lookup"><span data-stu-id="53ef7-112">If you're using Contoso demo data, you will require additional sample data to use the Customer payment predictions, Cash flow forecasts, and Budget forecasts features.</span></span> 

## <a name="configure-dataverse"></a><span data-ttu-id="53ef7-113">Konfigurera Dataverse</span><span class="sxs-lookup"><span data-stu-id="53ef7-113">Configure Dataverse</span></span>

<span data-ttu-id="53ef7-114">Använd följande steg för att konfigurera Dataverse för Finance insights.</span><span class="sxs-lookup"><span data-stu-id="53ef7-114">Use the following steps to configure Dataverse for Finance insights.</span></span>

1. <span data-ttu-id="53ef7-115">Öppna miljösidan i LCS och kontrollera att avsnittet **Power Platform**-integration redan har ställts in.</span><span class="sxs-lookup"><span data-stu-id="53ef7-115">Open the environment page in LCS and verify that the **Power Platform Integration** section is already setup.</span></span>
    1. <span data-ttu-id="53ef7-116">Om den redan är inställd ska Dataverse-miljön som är länkat till Dynamics 365 Finance-miljön visas i listan.</span><span class="sxs-lookup"><span data-stu-id="53ef7-116">If it is already set up, the Dataverse environment name linked to the Dynamics 365 Finance Environment should be listed.</span></span> <span data-ttu-id="53ef7-117">Kopiera namnet på Dataverse-miljön.</span><span class="sxs-lookup"><span data-stu-id="53ef7-117">Copy the Dataverse environment name.</span></span>
    2. <span data-ttu-id="53ef7-118">Om den inte är inställd följer du dessa steg:</span><span class="sxs-lookup"><span data-stu-id="53ef7-118">If it is not set up, follow these steps:</span></span>
        1. <span data-ttu-id="53ef7-119">Välj knappen **Inställningar** i avsnittet Power Platform-integrering.</span><span class="sxs-lookup"><span data-stu-id="53ef7-119">Select the **Setup** button in the Power Platform Integration section.</span></span> <span data-ttu-id="53ef7-120">Det kan ta upp till en timme innan miljön kan ställas in.</span><span class="sxs-lookup"><span data-stu-id="53ef7-120">It may take up to an hour for the environment to be set up.</span></span>
        2. <span data-ttu-id="53ef7-121">Om Dataverse-miljön har ställts in bör det Dataverse-miljönamn som kopplats till Dynamics 365 Finance-miljön listas.</span><span class="sxs-lookup"><span data-stu-id="53ef7-121">If the Dataverse environment is successfully set up, the Dataverse environment name linked to the Dynamics 365 Finance Environment should be listed.</span></span> <span data-ttu-id="53ef7-122">Kopiera namnet på Dataverse-miljön.</span><span class="sxs-lookup"><span data-stu-id="53ef7-122">Copy the Dataverse environment name.</span></span>
> [!NOTE]
> <span data-ttu-id="53ef7-123">När miljön är klar väljer du **INTE** knappen **Koppla till CDS for Apps**.</span><span class="sxs-lookup"><span data-stu-id="53ef7-123">After completing the environment set up, **DO NOT** select the **Link to CDS for Apps** button.</span></span> <span data-ttu-id="53ef7-124">Detta behövs inte för Finance Insights och kommer att inaktivera möjligheten att slutföra de erforderliga miljötilläggen i LCS.</span><span class="sxs-lookup"><span data-stu-id="53ef7-124">This is not needed for Finance Insights and will disable the ability to complete the required Environment Add-ins in LCS.</span></span>

2. <span data-ttu-id="53ef7-125">Öppna [Power Platform administrationscenter](https://admin.powerplatform.microsoft.com/) och skapa en ny Dataverse-miljö i samma Active Directory-klientorganisation genom att följa stegen nedan:</span><span class="sxs-lookup"><span data-stu-id="53ef7-125">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com/), and follow these steps to create a new Dataverse environment in the same Active Directory tenant:</span></span>

    1. <span data-ttu-id="53ef7-126">Öppna sidan **Miljöer**.</span><span class="sxs-lookup"><span data-stu-id="53ef7-126">Open the **Environments** page.</span></span>

        <span data-ttu-id="53ef7-127">[![Sidan Miljöer](./media/power-pltfrm-admin-center.png)](./media/power-pltfrm-admin-center.png)</span><span class="sxs-lookup"><span data-stu-id="53ef7-127">[![Environments page](./media/power-pltfrm-admin-center.png)](./media/power-pltfrm-admin-center.png)</span></span>

    2. <span data-ttu-id="53ef7-128">Välj Dataverse-miljön som skapats ovan och välj sedan **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="53ef7-128">Select the Dataverse environment created above and then select **Settings**.</span></span>
    3. <span data-ttu-id="53ef7-129">Välj **Resurser \> Alla äldre inställningar**.</span><span class="sxs-lookup"><span data-stu-id="53ef7-129">Select **Resources \> All Legacy Settings**.</span></span>
    4. <span data-ttu-id="53ef7-130">Välj **Inställningar** i det övre navigeringsfältet och välj **Anpassningar**.</span><span class="sxs-lookup"><span data-stu-id="53ef7-130">On the top navigation bar, select **Settings**, and then select **Customizations**.</span></span>
    5. <span data-ttu-id="53ef7-131">Välj **Utvecklarresurser**.</span><span class="sxs-lookup"><span data-stu-id="53ef7-131">Select **Developer Resources**.</span></span>
    6. <span data-ttu-id="53ef7-132">Kopiera värdet för **Organisations-ID för Dataverse**.</span><span class="sxs-lookup"><span data-stu-id="53ef7-132">Copy the **Dataverse organization ID** value.</span></span>
    7. <span data-ttu-id="53ef7-133">Notera URL:en till Dataverse-organisationen i webbläsarens adressfält.</span><span class="sxs-lookup"><span data-stu-id="53ef7-133">In the browser's address bar, make a note of the URL for the Dataverse organization.</span></span> <span data-ttu-id="53ef7-134">URL-adressen kan till exempel vara `https://org42b2b3d3.crm.dynamics.com`.</span><span class="sxs-lookup"><span data-stu-id="53ef7-134">For example, the URL might be `https://org42b2b3d3.crm.dynamics.com`.</span></span>

3. <span data-ttu-id="53ef7-135">Om du planerar att använda kassaflödesprognoser eller budgetprognoser, följer du dessa steg för att uppdatera anteckningsgränsen för organisationen till minst 50 MB:</span><span class="sxs-lookup"><span data-stu-id="53ef7-135">If you plan to use the Cash flow forecasts or Budget forecasts feature, follow these steps to update the annotation limit for your organization to at least 50 megabytes (MB):</span></span>

    1. <span data-ttu-id="53ef7-136">Öppna [Power Apps-portal](https://make.powerapps.com).</span><span class="sxs-lookup"><span data-stu-id="53ef7-136">Open the [Power Apps portal](https://make.powerapps.com).</span></span>
    2. <span data-ttu-id="53ef7-137">Välj den miljö som du just har skapat och välj sedan **Avancerade inställningar**.</span><span class="sxs-lookup"><span data-stu-id="53ef7-137">Select the environment that you just created, and then select **Advanced settings**.</span></span>
    3. <span data-ttu-id="53ef7-138">Välj **Inställningar \> E-postkonfiguration**.</span><span class="sxs-lookup"><span data-stu-id="53ef7-138">Select **Settings \> Email Configuration**.</span></span>
    4. <span data-ttu-id="53ef7-139">Ändra värdet för fältet **Maximal filstorlek** till **51 200**.</span><span class="sxs-lookup"><span data-stu-id="53ef7-139">Change the value of the **Maximum file size** field to **51,200**.</span></span> <span data-ttu-id="53ef7-140">(Värdet uttrycks i kilobyte \[KB\].)</span><span class="sxs-lookup"><span data-stu-id="53ef7-140">(The value is expressed in kilobytes \[KB\].)</span></span>
    5. <span data-ttu-id="53ef7-141">Välj **OK** för att spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="53ef7-141">Select **OK** to save your changes.</span></span>

## <a name="configure-the-azure-setup"></a><span data-ttu-id="53ef7-142">Konfigurera Azure-inställningen</span><span class="sxs-lookup"><span data-stu-id="53ef7-142">Configure the Azure setup</span></span>

### <a name="enter-the-dataverse-directory-id-and-the-users-azure-ad-object-id"></a><span data-ttu-id="53ef7-143">Ange Dataverse-katalog-ID och användarens Azure AD-objekt-ID</span><span class="sxs-lookup"><span data-stu-id="53ef7-143">Enter the Dataverse directory ID and the user's Azure AD object ID</span></span>

1. <span data-ttu-id="53ef7-144">Ange Dataverse-katalog-ID:</span><span class="sxs-lookup"><span data-stu-id="53ef7-144">Enter the Dataverse directory ID:</span></span>

    1. <span data-ttu-id="53ef7-145">Öppna [Azure-portalen](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="53ef7-145">Open the [Azure portal](https://portal.azure.com).</span></span>
    2. <span data-ttu-id="53ef7-146">Logga in genom att använda det användar-ID som användes för att skapa Dataverse-miljön.</span><span class="sxs-lookup"><span data-stu-id="53ef7-146">Sign in by using the user ID that was used to create the Dataverse environment.</span></span>
    3. <span data-ttu-id="53ef7-147">Gå till **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="53ef7-147">Go to **Azure Active Directory**.</span></span>
    4. <span data-ttu-id="53ef7-148">Kopiera värdet för **Klientorganisations-ID**.</span><span class="sxs-lookup"><span data-stu-id="53ef7-148">Copy the **Tenant ID** value.</span></span>

2. <span data-ttu-id="53ef7-149">Ange användarens Azure Active Directory-objekt-ID (Azure AD):</span><span class="sxs-lookup"><span data-stu-id="53ef7-149">Enter the user's Azure Active Directory (Azure AD) object ID:</span></span>

    1. <span data-ttu-id="53ef7-150">I [Azure-portalen](https://portal.azure.com), gå till **Användare** och sök efter användaren via e-postadressen.</span><span class="sxs-lookup"><span data-stu-id="53ef7-150">In the [Azure portal](https://portal.azure.com), go to **Users**, and search for the user by email address.</span></span>
    2. <span data-ttu-id="53ef7-151">Välj användarens namn.</span><span class="sxs-lookup"><span data-stu-id="53ef7-151">Select the user's name.</span></span>
    3. <span data-ttu-id="53ef7-152">Kopiera värdet för **Objekt-ID**.</span><span class="sxs-lookup"><span data-stu-id="53ef7-152">Copy the **Object ID** value.</span></span>

### <a name="use-azure-cloud-shell-to-set-up-finance-insights-data-lake-resources"></a><span data-ttu-id="53ef7-153">Använd Azure Cloud Shell för att konfigurera Ekonomiska insikters Data Lake-resurser</span><span class="sxs-lookup"><span data-stu-id="53ef7-153">Use Azure Cloud Shell to set up Finance insights Data Lake resources</span></span>

# <a name="use-a-windows-powershell-script"></a>[<span data-ttu-id="53ef7-154">Använd ett Windows PowerShell-skript</span><span class="sxs-lookup"><span data-stu-id="53ef7-154">Use a Windows PowerShell script</span></span>](#tab/use-a-powershell-script)

<span data-ttu-id="53ef7-155">Ett Windows PowerShell-skript har angetts så att du enkelt kan ställa in de Azure-resurser som beskrivs i [Konfigurera export till Azure Data Lake](../../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md).</span><span class="sxs-lookup"><span data-stu-id="53ef7-155">A Windows PowerShell script has been provided, so that you can easily set up the Azure resources that are described in [Configure export to Azure Data Lake](../../fin-ops-core/dev-itpro/data-entities/configure-export-data-lake.md).</span></span> <span data-ttu-id="53ef7-156">Om du föredrar att göra manuella inställningar hoppar du över den här proceduren och fortsätter med proceduren i avsnittet [Manuell konfiguration](#manual-setup).</span><span class="sxs-lookup"><span data-stu-id="53ef7-156">If you prefer to do manual setup, skip this procedure, and continue with the procedure in the [Manual setup](#manual-setup) section.</span></span>

> [!NOTE]
> <span data-ttu-id="53ef7-157">Kör PowerShell-skriptet genom att följa stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="53ef7-157">Follow the steps below to run the PowerShell script.</span></span> <span data-ttu-id="53ef7-158">Azure CLI-alternativet "Pröva" eller att köra skriptet på datorn fungerar kanske inte.</span><span class="sxs-lookup"><span data-stu-id="53ef7-158">The Azure CLI "Try it" option, or running the script on your PC may not work.</span></span>

<span data-ttu-id="53ef7-159">Följ dessa steg för att konfigurera Azure med hjälp av Windows PowerShell-skriptet.</span><span class="sxs-lookup"><span data-stu-id="53ef7-159">Follow these steps to configure Azure by using the Windows PowerShell script.</span></span> <span data-ttu-id="53ef7-160">Du måste ha behörighet att skapa en Azure-resursgrupp, Azure-resurser och ett Azure AD-program.</span><span class="sxs-lookup"><span data-stu-id="53ef7-160">You must have rights to create an Azure resource group, Azure resources, and an Azure AD application.</span></span> <span data-ttu-id="53ef7-161">Information om vilka behörigheter som krävs finns i [Kontrollera Azure AD-behörigheter](/azure/active-directory/develop/howto-create-service-principal-portal#permissions-required-for-registering-an-app).</span><span class="sxs-lookup"><span data-stu-id="53ef7-161">For information about the required permissions, see [Check Azure AD permissions](/azure/active-directory/develop/howto-create-service-principal-portal#permissions-required-for-registering-an-app).</span></span>

1. <span data-ttu-id="53ef7-162">I [Azure-portalen](https://portal.azure.com), gå till din mål-Azure-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="53ef7-162">In the [Azure portal](https://portal.azure.com), go to your target Azure subscription.</span></span> <span data-ttu-id="53ef7-163">Välj knappen **Cloud Shell** till höger om fältet **Sök**.</span><span class="sxs-lookup"><span data-stu-id="53ef7-163">Select the **Cloud Shell** button to the right of the **Search** field.</span></span>
2. <span data-ttu-id="53ef7-164">Välj **PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="53ef7-164">Select **PowerShell**.</span></span>
3. <span data-ttu-id="53ef7-165">Skapa lagringsutrymme om du uppmanas göra det.</span><span class="sxs-lookup"><span data-stu-id="53ef7-165">Create storage if you're prompted to do so.</span></span>
4. <span data-ttu-id="53ef7-166">Gå till fliken **Azure CLI** och välj **Kopiera**.</span><span class="sxs-lookup"><span data-stu-id="53ef7-166">Go to the **Azure CLI** tab and select **Copy**.</span></span>  
5. <span data-ttu-id="53ef7-167">Öppna Anteckningar och klistra in PowerShell-skriptet.</span><span class="sxs-lookup"><span data-stu-id="53ef7-167">Open Notepad and paste the PowerShell script.</span></span> <span data-ttu-id="53ef7-168">Spara filen som ConfigureDataLake.ps1.</span><span class="sxs-lookup"><span data-stu-id="53ef7-168">Save the file as ConfigureDataLake.ps1.</span></span>
6. <span data-ttu-id="53ef7-169">Ladda upp Windows PowerShell-skriptet till sessionen med hjälp av menyalternativet för uppladdning Cloud Shell.</span><span class="sxs-lookup"><span data-stu-id="53ef7-169">Upload the Windows PowerShell script to the session using the menu option for upload in Cloud Shell.</span></span>
7. <span data-ttu-id="53ef7-170">Kör skriptet .\ConfigureDataLake.ps1.</span><span class="sxs-lookup"><span data-stu-id="53ef7-170">Run the script .\ConfigureDataLake.ps1.</span></span>
8. <span data-ttu-id="53ef7-171">Kör skriptet genom att följa anvisningarna.</span><span class="sxs-lookup"><span data-stu-id="53ef7-171">Follow the prompts to run the script.</span></span>
9. <span data-ttu-id="53ef7-172">Installera tillägget **Exportera till Data Lake** i LCS med hjälp av informationen i skriptets utdata.</span><span class="sxs-lookup"><span data-stu-id="53ef7-172">Use the information from the script output to install the **Export to Data Lake** add-in in LCS.</span></span>
10. <span data-ttu-id="53ef7-173">Använd informationen från skriptets utdata för att aktivera entitetsarkivet på sidan **Dataanslutningar** i Finance (**Systemadministration \> Systemparametrar \> Dataanslutningar**).</span><span class="sxs-lookup"><span data-stu-id="53ef7-173">Use the information from the script output to enable the entity store on the **Data connections** page in Finance (**System administration \> System parameters \> Data connections**).</span></span>

### <a name="manual-setup"></a><span data-ttu-id="53ef7-174">Manuell konfiguration</span><span class="sxs-lookup"><span data-stu-id="53ef7-174">Manual setup</span></span>

#### <a name="add-applications-to-the-azure-ad-tenant"></a><span data-ttu-id="53ef7-175">Lägg till program i Azure AD-klientorganisationen</span><span class="sxs-lookup"><span data-stu-id="53ef7-175">Add applications to the Azure AD tenant</span></span>

1. <span data-ttu-id="53ef7-176">I [Azure-portalen](https://portal.azure.com), gå till **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="53ef7-176">In the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**.</span></span>
2. <span data-ttu-id="53ef7-177">Välj **Hantera \> Företagsprogram**.</span><span class="sxs-lookup"><span data-stu-id="53ef7-177">Select **Manage \> Enterprise applications**.</span></span>
3. <span data-ttu-id="53ef7-178">Sök efter följande program med app-ID.</span><span class="sxs-lookup"><span data-stu-id="53ef7-178">Search for the following applications by app ID.</span></span>

    | <span data-ttu-id="53ef7-179">Ansökning</span><span class="sxs-lookup"><span data-stu-id="53ef7-179">Application</span></span>                              | <span data-ttu-id="53ef7-180">App-ID</span><span class="sxs-lookup"><span data-stu-id="53ef7-180">App ID</span></span>                               |
    |------------------------------------------|--------------------------------------|
    | <span data-ttu-id="53ef7-181">Microsoft Dynamics ERP Microservices</span><span class="sxs-lookup"><span data-stu-id="53ef7-181">Microsoft Dynamics ERP Microservices</span></span>     | <span data-ttu-id="53ef7-182">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span><span class="sxs-lookup"><span data-stu-id="53ef7-182">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span></span> |
    | <span data-ttu-id="53ef7-183">Microsoft Dynamics ERP Microservices CDS</span><span class="sxs-lookup"><span data-stu-id="53ef7-183">Microsoft Dynamics ERP Microservices CDS</span></span> | <span data-ttu-id="53ef7-184">703e2651-d3fc-48f5-942c-74274233dba8</span><span class="sxs-lookup"><span data-stu-id="53ef7-184">703e2651-d3fc-48f5-942c-74274233dba8</span></span> |
    | <span data-ttu-id="53ef7-185">AI Builder Authorization Service</span><span class="sxs-lookup"><span data-stu-id="53ef7-185">AI Builder Authorization Service</span></span>         | <span data-ttu-id="53ef7-186">ad40333e-9910-4b61-b281-e3aeeb8c3ef3</span><span class="sxs-lookup"><span data-stu-id="53ef7-186">ad40333e-9910-4b61-b281-e3aeeb8c3ef3</span></span> |

<span data-ttu-id="53ef7-187">Om du inte hittar något av ovanstående program gör du på följande sätt.</span><span class="sxs-lookup"><span data-stu-id="53ef7-187">If you can't find any of the preceding applications, try the following steps.</span></span>

1. <span data-ttu-id="53ef7-188">Välj **Start**-menyn och sök efter **powershell** på den lokala datorn.</span><span class="sxs-lookup"><span data-stu-id="53ef7-188">On your local machine, select the **Start** menu, and search for **powershell**.</span></span>
2. <span data-ttu-id="53ef7-189">Markera och håll (eller högerklicka) på **Windows PowerShell** och välj **Kör som administratör**.</span><span class="sxs-lookup"><span data-stu-id="53ef7-189">Select and hold (or right-click) **Windows PowerShell**, and then select **Run as administrator**.</span></span>
3. <span data-ttu-id="53ef7-190">Kör följande kommando för att installera modulen **AzureAD**.</span><span class="sxs-lookup"><span data-stu-id="53ef7-190">Run the following command to install the **AzureAD** module.</span></span>

    `Install-Module -Name AzureAD`

4. <span data-ttu-id="53ef7-191">Om en NuGet-leverantör krävs för att du ska kunna fortsätta väljer **Y** för att installera den.</span><span class="sxs-lookup"><span data-stu-id="53ef7-191">If a NuGet provider is required to continue, select **Y** to install it.</span></span>
5. <span data-ttu-id="53ef7-192">Om meddelandet "Untrusted repository" (Ej betrodd lagringsplats) visas väljer du **Y** för att fortsätta.</span><span class="sxs-lookup"><span data-stu-id="53ef7-192">If an "Untrusted repository" message appears, select **Y** to continue.</span></span>
6. <span data-ttu-id="53ef7-193">Kör följande kommandon för varje program som måste läggas till för att du ska kunna lägga till programmet i Azure AD.</span><span class="sxs-lookup"><span data-stu-id="53ef7-193">For each application that must be added, run the following commands to add the application to Azure AD.</span></span> <span data-ttu-id="53ef7-194">Logga in som Azure AD-administratör när du uppmanas till det.</span><span class="sxs-lookup"><span data-stu-id="53ef7-194">When you're prompted, sign in as the Azure AD administrator.</span></span>

    `Connect-AzureAD`

    `New-AzureADServicePrincipal –AppId <AppId>`

#### <a name="create-azure-resources"></a><span data-ttu-id="53ef7-195">Skapa Azure-resurser</span><span class="sxs-lookup"><span data-stu-id="53ef7-195">Create Azure resources</span></span>

> [!NOTE]
> <span data-ttu-id="53ef7-196">Se till att du skapar följande resurser i samma Azure AD-instans som Dataverse-miljön.</span><span class="sxs-lookup"><span data-stu-id="53ef7-196">Make sure that you create the following resources in the same Azure AD instance as the Dataverse environment.</span></span> <span data-ttu-id="53ef7-197">Du kan inte använda resurser från en annan Azure AD-instans.</span><span class="sxs-lookup"><span data-stu-id="53ef7-197">You can't use resources from a different Azure AD instance.</span></span>

1. <span data-ttu-id="53ef7-198">Skapa ett nytt lagringskonto:</span><span class="sxs-lookup"><span data-stu-id="53ef7-198">Create a new storage account:</span></span>

    1. <span data-ttu-id="53ef7-199">Skapa ett lagringskonto i [Azure-portalen](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="53ef7-199">In the [Azure portal](https://portal.azure.com), create a storage account.</span></span>
    2. <span data-ttu-id="53ef7-200">I dialogrutan **Skapa lagringskonto**, ställ in följande fält:</span><span class="sxs-lookup"><span data-stu-id="53ef7-200">In the **Create storage account** dialog box, set the following fields:</span></span>

        - <span data-ttu-id="53ef7-201">**Plats** – Välj det datacenter där din miljö finns.</span><span class="sxs-lookup"><span data-stu-id="53ef7-201">**Location** – Select the data center where your environment is located.</span></span>
        - <span data-ttu-id="53ef7-202">**Prestanda** – Vi rekommenderar att du väljer **Standard**.</span><span class="sxs-lookup"><span data-stu-id="53ef7-202">**Performance** – We recommend that you select **Standard**.</span></span>
        - <span data-ttu-id="53ef7-203">**Kontotyp** – Du måste välja **StorageV2**.</span><span class="sxs-lookup"><span data-stu-id="53ef7-203">**Account kind** – You must select **StorageV2**.</span></span>

    3. <span data-ttu-id="53ef7-204">I dialogrutan **Avancerade alternativ**, för alternativet **Data Lake Storage Gen2** väljer du **Aktivera** under funktionen **Hierarkiska namnrymder**.</span><span class="sxs-lookup"><span data-stu-id="53ef7-204">In the **Advanced options** dialog box, for the **Data Lake storage Gen2** option, select **Enable** under the **Hierarchical namespaces** feature.</span></span> <span data-ttu-id="53ef7-205">Om du inaktiverar den här funktionen kan du inte använda data som Finance and Operations-appar skriver med hjälp av tjänster som Power BI-dataflöden.</span><span class="sxs-lookup"><span data-stu-id="53ef7-205">If you disable this feature, you can't consume data that Finance and Operations apps write by using services such as Power BI data flows.</span></span>
    4. <span data-ttu-id="53ef7-206">Välj **Granska och skapa**.</span><span class="sxs-lookup"><span data-stu-id="53ef7-206">Select **Review and create**.</span></span> <span data-ttu-id="53ef7-207">När distributionen har slutförts visas den nya resursen i Azure-portalen.</span><span class="sxs-lookup"><span data-stu-id="53ef7-207">When the deployment is completed, the new resource will be shown in the Azure portal.</span></span>
    5. <span data-ttu-id="53ef7-208">Gå till det lagringskonto som du har skapat.</span><span class="sxs-lookup"><span data-stu-id="53ef7-208">Go to the storage account that you created.</span></span>
    6. <span data-ttu-id="53ef7-209">Välj **Åtkomstnycklar** i menyn till vänster.</span><span class="sxs-lookup"><span data-stu-id="53ef7-209">On the left menu, select **Access keys**.</span></span>
    7. <span data-ttu-id="53ef7-210">Kopiera och spara anslutningssträngen för antingen **Key1** eller **Key2**.</span><span class="sxs-lookup"><span data-stu-id="53ef7-210">Copy and save the connection string for either **Key1** or **Key2**.</span></span>
    8. <span data-ttu-id="53ef7-211">Kopiera och spara namnet på lagringskontot.</span><span class="sxs-lookup"><span data-stu-id="53ef7-211">Copy and save the storage account name.</span></span>

2. <span data-ttu-id="53ef7-212">Skapa en ny nyckelvalvresurs:</span><span class="sxs-lookup"><span data-stu-id="53ef7-212">Create a new key vault:</span></span>

    1. <span data-ttu-id="53ef7-213">Skapa ett nyckelvalv i [Azure-portalen](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="53ef7-213">In the [Azure portal](https://portal.azure.com), create a key vault.</span></span>
    2. <span data-ttu-id="53ef7-214">I dialogrutan **Skapa nyckelvalv**, i fältet **Plats**, välj det datacenter där din miljö finns.</span><span class="sxs-lookup"><span data-stu-id="53ef7-214">In the **Create key vault** dialog box, in the **Location** field, select the data center where your environment is located.</span></span>
    3. <span data-ttu-id="53ef7-215">När nyckelvalvet har skapats väljer du det i listan och väljer sedan **Hemligheter**.</span><span class="sxs-lookup"><span data-stu-id="53ef7-215">After key vault is created, select it in the list, and then select **Secrets**.</span></span>
    4. <span data-ttu-id="53ef7-216">Välj **Generera/Importera**.</span><span class="sxs-lookup"><span data-stu-id="53ef7-216">Select **Generate/Import**.</span></span>
    5. <span data-ttu-id="53ef7-217">I dialogrutan **Skapa en hemlighet** i fältet **Överföringsalternativ** välj **Manuell**.</span><span class="sxs-lookup"><span data-stu-id="53ef7-217">In the **Create a secret** dialog box, in the **Upload options** field, select **Manual**.</span></span>
    6. <span data-ttu-id="53ef7-218">Ange ett namn på hemligheten.</span><span class="sxs-lookup"><span data-stu-id="53ef7-218">Enter a name for the secret.</span></span> <span data-ttu-id="53ef7-219">Anteckna namnet eftersom du kommer att behöva ange det senare.</span><span class="sxs-lookup"><span data-stu-id="53ef7-219">Make a note of the name, because you will have to provide it later.</span></span>
    7. <span data-ttu-id="53ef7-220">I fältet **Värde** anger du den anslutningssträng som du hämtade från lagringskontot i föregående procedur.</span><span class="sxs-lookup"><span data-stu-id="53ef7-220">In the **Value** field, enter the connection string that you obtained from the storage account in the previous procedure.</span></span>
    8. <span data-ttu-id="53ef7-221">Välj **Aktiverat** och välj sedan **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="53ef7-221">Select **Enabled**, and then select **Create**.</span></span> <span data-ttu-id="53ef7-222">Hemligheten skapas och läggs till i nyckelvalvet.</span><span class="sxs-lookup"><span data-stu-id="53ef7-222">The secret is created and added to Key Vault.</span></span>
    9. <span data-ttu-id="53ef7-223">Gå till **nyckelvalvöversikten** och anteckna DNS-namnet.</span><span class="sxs-lookup"><span data-stu-id="53ef7-223">Go to the **Key Vault Overview**, and make a note of the DNS name.</span></span>

3. <span data-ttu-id="53ef7-224">Skapa och registrera ett Azure AD-program:</span><span class="sxs-lookup"><span data-stu-id="53ef7-224">Create and register an Azure AD application:</span></span>

    1. <span data-ttu-id="53ef7-225">I [Azure-portalen](https://portal.azure.com), gå till **Azure Active Directory** och välj **Appregistreringar**.</span><span class="sxs-lookup"><span data-stu-id="53ef7-225">In the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**, and then select **App registrations**.</span></span>
    2. <span data-ttu-id="53ef7-226">Välj **Ny programregistrering** och ange följande fält:</span><span class="sxs-lookup"><span data-stu-id="53ef7-226">Select **New application registration**, and set the following fields:</span></span>

        - <span data-ttu-id="53ef7-227">**Namn** – Ange namnet på appen.</span><span class="sxs-lookup"><span data-stu-id="53ef7-227">**Name** – Enter the name of the app.</span></span>
        - <span data-ttu-id="53ef7-228">**Programtyp** – Välj **Webb-API**.</span><span class="sxs-lookup"><span data-stu-id="53ef7-228">**Application type** – Select **Web API**.</span></span>
        - <span data-ttu-id="53ef7-229">**Inställning av omdirigerings-URI** – Ange URL:en för din Dynamics 365-instans, till exempel `https://yourdynamicsinstance.dynamics.com/auth`.</span><span class="sxs-lookup"><span data-stu-id="53ef7-229">**Redirect URI setup** – Enter the URL for your Dynamics 365 instance, such as, `https://yourdynamicsinstance.dynamics.com/auth`.</span></span>

    3. <span data-ttu-id="53ef7-230">Gå till den app som du just skapade och kopiera och spara dess värde för **Program-ID (klient)**.</span><span class="sxs-lookup"><span data-stu-id="53ef7-230">Go to the app that you just created, and copy and save its **Application (client) ID** value.</span></span> <span data-ttu-id="53ef7-231">Du måste ange det här värdet senare när du konfigurerar nyckelvalvet.</span><span class="sxs-lookup"><span data-stu-id="53ef7-231">You will have to provide this value later, when you set up the key vault.</span></span>
    4. <span data-ttu-id="53ef7-232">Gå till **API-behörigheter** och gör så här:</span><span class="sxs-lookup"><span data-stu-id="53ef7-232">Go to **API permissions**, and follow these steps:</span></span>

        1. <span data-ttu-id="53ef7-233">Välj **Lägg till behörighet**.</span><span class="sxs-lookup"><span data-stu-id="53ef7-233">Select **Add a permission**.</span></span>
        2. <span data-ttu-id="53ef7-234">Välj **Azure Key Vault**.</span><span class="sxs-lookup"><span data-stu-id="53ef7-234">Select **Azure Key vault**.</span></span>
        3. <span data-ttu-id="53ef7-235">När du har valt delegerade behörigheter väljer du **användare\_personifiering**.</span><span class="sxs-lookup"><span data-stu-id="53ef7-235">After you select delegated permissions, select **user\_impersonation**.</span></span>
        4. <span data-ttu-id="53ef7-236">Välj **Lägg till behörigheter**.</span><span class="sxs-lookup"><span data-stu-id="53ef7-236">Select **Add permissions**.</span></span>

    5. <span data-ttu-id="53ef7-237">På menyn för appen väljer du **Certifikat \& hemligheter** och följer sedan stegen nedan för att skapa nyckelvalvhemligheter:</span><span class="sxs-lookup"><span data-stu-id="53ef7-237">On the menu for the app, select **Certificates \& secrets**, and then follow these steps to create Key Vault secrets:</span></span>

        1. <span data-ttu-id="53ef7-238">Välj **Ny klienthemlighet**.</span><span class="sxs-lookup"><span data-stu-id="53ef7-238">Select **New client secret**.</span></span>
        2. <span data-ttu-id="53ef7-239">Ange ett namn i fältet **Nyckelbeskrivning**.</span><span class="sxs-lookup"><span data-stu-id="53ef7-239">In the **Key Description** field, enter a name.</span></span>
        3. <span data-ttu-id="53ef7-240">Markera en varaktighet och välj sedan **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="53ef7-240">Select a duration, and then select **Add**.</span></span> <span data-ttu-id="53ef7-241">En hemlighet genereras i fältet **Värde**.</span><span class="sxs-lookup"><span data-stu-id="53ef7-241">A secret is generated in the **Value** field.</span></span>
        4. <span data-ttu-id="53ef7-242">Kopiera och spara det hemliga värdet.</span><span class="sxs-lookup"><span data-stu-id="53ef7-242">Copy and save the secret value.</span></span>

4. <span data-ttu-id="53ef7-243">Skapa nyckelvalvhemligheter:</span><span class="sxs-lookup"><span data-stu-id="53ef7-243">Create Key Vault secrets:</span></span>

    1. <span data-ttu-id="53ef7-244">Gå till det nyckelvalv som du skapade tidigare och välj **Hemligheter**.</span><span class="sxs-lookup"><span data-stu-id="53ef7-244">Go to the key vault that you created earlier, and select **Secrets**.</span></span>
    2. <span data-ttu-id="53ef7-245">Gör så här för varje hemligt namn i följande tabell:</span><span class="sxs-lookup"><span data-stu-id="53ef7-245">For each secret name in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="53ef7-246">Välj **Generera/Importera**.</span><span class="sxs-lookup"><span data-stu-id="53ef7-246">Select **Generate/Import**.</span></span>
        2. <span data-ttu-id="53ef7-247">I dialogrutan **Skapa en hemlighet** i fältet **Överföringsalternativ** välj **Manuell**.</span><span class="sxs-lookup"><span data-stu-id="53ef7-247">In the **Create a secret** dialog box, in the **Upload options** field, select **Manual**.</span></span>
        3. <span data-ttu-id="53ef7-248">Skapa det hemliga namnet och värdet från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="53ef7-248">Create the secret name and value from the following table.</span></span>
        4. <span data-ttu-id="53ef7-249">Välj **Aktiverat** och välj sedan **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="53ef7-249">Select **Enabled**, and then select **Create**.</span></span> <span data-ttu-id="53ef7-250">Hemligheten skapas och läggs till i nyckelvalvet.</span><span class="sxs-lookup"><span data-stu-id="53ef7-250">The secret is created and added to Key Vault.</span></span>

        | <span data-ttu-id="53ef7-251">Hemligt namn</span><span class="sxs-lookup"><span data-stu-id="53ef7-251">Secret name</span></span>                       | <span data-ttu-id="53ef7-252">Hemligt värde</span><span class="sxs-lookup"><span data-stu-id="53ef7-252">Secret value</span></span>                                                                                |
        |-----------------------------------|---------------------------------------------------------------------------------------------|
        | <span data-ttu-id="53ef7-253">program-ID</span><span class="sxs-lookup"><span data-stu-id="53ef7-253">app-id</span></span>                            | <span data-ttu-id="53ef7-254">App-ID för programmet som du skapade tidigare</span><span class="sxs-lookup"><span data-stu-id="53ef7-254">The app ID of the application that you created earlier</span></span>                                      |
        | <span data-ttu-id="53ef7-255">programhemlighet</span><span class="sxs-lookup"><span data-stu-id="53ef7-255">app-secret</span></span>                        | <span data-ttu-id="53ef7-256">Klienthemligheten som du sparade tidigare</span><span class="sxs-lookup"><span data-stu-id="53ef7-256">The client secret that you saved earlier</span></span>                                                    |
        | <span data-ttu-id="53ef7-257">lagringskontonamn</span><span class="sxs-lookup"><span data-stu-id="53ef7-257">storage-account-name</span></span>              | <span data-ttu-id="53ef7-258">Namnet på lagringskontot som du skapade tidigare, t.ex. **lagringskonto1**</span><span class="sxs-lookup"><span data-stu-id="53ef7-258">The name of the storage account that you created earlier, such as **storageaccount1**</span></span>       |
        | <span data-ttu-id="53ef7-259">lagringskontots anslutningssträng</span><span class="sxs-lookup"><span data-stu-id="53ef7-259">storage-account-connection-string</span></span> | <span data-ttu-id="53ef7-260">Den anslutningssträng som du kopierade från sidan **Åtkomstnycklar** för lagringskontot</span><span class="sxs-lookup"><span data-stu-id="53ef7-260">The connection string that you copied from the **Access keys** page for the storage account</span></span> |

5. <span data-ttu-id="53ef7-261">Auktorisera programmet för att få åtkomst till nyckelvalvet:</span><span class="sxs-lookup"><span data-stu-id="53ef7-261">Authorize the application to access the key vault:</span></span>

    1. <span data-ttu-id="53ef7-262">I [Azure-portalen](https://portal.azure.com), öppna nyckelvalvet som du skapade tidigare.</span><span class="sxs-lookup"><span data-stu-id="53ef7-262">In the [Azure portal](https://portal.azure.com), open the key vault that you created earlier.</span></span>
    2. <span data-ttu-id="53ef7-263">Välj åtkomstprinciper.</span><span class="sxs-lookup"><span data-stu-id="53ef7-263">Select the access policies.</span></span>
    3. <span data-ttu-id="53ef7-264">Gör så här för varje program i följande tabell:</span><span class="sxs-lookup"><span data-stu-id="53ef7-264">For each application in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="53ef7-265">Välj **Lägg till åtkomstprincip** för att skapa en åtkomstprincip.</span><span class="sxs-lookup"><span data-stu-id="53ef7-265">Select **Add Access Policy** to create an access policy.</span></span>
        2. <span data-ttu-id="53ef7-266">I fältet **Hemliga behörigheter**, välj behörigheterna från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="53ef7-266">In the **Secret permissions** field, select the permissions from the following table.</span></span>
        3. <span data-ttu-id="53ef7-267">I fältet **Välj huvudnamn**, sök efter programmets visningsnamn från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="53ef7-267">In the **Select principal** field, search for the application display name from the following table.</span></span>
        4. <span data-ttu-id="53ef7-268">Välj **Välj**.</span><span class="sxs-lookup"><span data-stu-id="53ef7-268">Select **Select**.</span></span>
        5. <span data-ttu-id="53ef7-269">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="53ef7-269">Select **Add**.</span></span>
        6. <span data-ttu-id="53ef7-270">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="53ef7-270">Select **Save**.</span></span>

        | <span data-ttu-id="53ef7-271">Ansökning</span><span class="sxs-lookup"><span data-stu-id="53ef7-271">Application</span></span>                                              | <span data-ttu-id="53ef7-272">Behörighet</span><span class="sxs-lookup"><span data-stu-id="53ef7-272">Permissions</span></span> |
        |----------------------------------------------------------|-------------|
        | <span data-ttu-id="53ef7-273">Visningsnamnet för det nya program som du skapade</span><span class="sxs-lookup"><span data-stu-id="53ef7-273">The display name of the new application that you created</span></span> | <span data-ttu-id="53ef7-274">Get, List</span><span class="sxs-lookup"><span data-stu-id="53ef7-274">Get, List</span></span>   |
        | <span data-ttu-id="53ef7-275">**Microsoft Dynamics ERP Microservices**</span><span class="sxs-lookup"><span data-stu-id="53ef7-275">**Microsoft Dynamics ERP Microservices**</span></span>                 | <span data-ttu-id="53ef7-276">Get, List</span><span class="sxs-lookup"><span data-stu-id="53ef7-276">Get, List</span></span>   |

6. <span data-ttu-id="53ef7-277">Tilldela roller för åtkomst till lagringskontot:</span><span class="sxs-lookup"><span data-stu-id="53ef7-277">Assign roles to access the storage account:</span></span>

    1. <span data-ttu-id="53ef7-278">I [Azure-portalen](https://portal.azure.com), öppna lagringskontot som du skapade tidigare.</span><span class="sxs-lookup"><span data-stu-id="53ef7-278">In the [Azure portal](https://portal.azure.com), open the storage account that you created earlier.</span></span>
    2. <span data-ttu-id="53ef7-279">Välj **Åtkomstkontroll (IAM)** och välj **Rolltilldelningar**.</span><span class="sxs-lookup"><span data-stu-id="53ef7-279">Select **Access Control (IAM)**, and then select **Role Assignments**.</span></span>
    3. <span data-ttu-id="53ef7-280">Välj **Lägg till, Lägg till rolltilldelning**.</span><span class="sxs-lookup"><span data-stu-id="53ef7-280">Select **Add, Add Role Assignment**.</span></span>
    4. <span data-ttu-id="53ef7-281">Gör så här för varje program i följande tabell:</span><span class="sxs-lookup"><span data-stu-id="53ef7-281">For each application in the following table, follow these steps:</span></span>

        1. <span data-ttu-id="53ef7-282">Välj rollen bland i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="53ef7-282">Select the role from the following table.</span></span>
        2. <span data-ttu-id="53ef7-283">Låt fältet **Tilldela åtkomst till** vara inställt på **Azure AD-användare, -grupp eller -tjänstens huvudnamn**.</span><span class="sxs-lookup"><span data-stu-id="53ef7-283">Leave the **Assign access to** field set to **Azure AD user, group, or service principal**.</span></span>
        3. <span data-ttu-id="53ef7-284">I fältet **Välj**, ange programmet från följande tabell.</span><span class="sxs-lookup"><span data-stu-id="53ef7-284">In the **Select** field, enter the application from the following table.</span></span>
        4. <span data-ttu-id="53ef7-285">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="53ef7-285">Select **Save**.</span></span>

        | <span data-ttu-id="53ef7-286">Ansökning</span><span class="sxs-lookup"><span data-stu-id="53ef7-286">Application</span></span>                                              | <span data-ttu-id="53ef7-287">Roll</span><span class="sxs-lookup"><span data-stu-id="53ef7-287">Role</span></span>                        |
        |----------------------------------------------------------|-----------------------------|
        | <span data-ttu-id="53ef7-288">Visningsnamnet för det nya program som du skapade</span><span class="sxs-lookup"><span data-stu-id="53ef7-288">The display name of the new application that you created</span></span> | <span data-ttu-id="53ef7-289">Ägare</span><span class="sxs-lookup"><span data-stu-id="53ef7-289">Owner</span></span>                       |
        | <span data-ttu-id="53ef7-290">Visningsnamnet för det nya program som du skapade</span><span class="sxs-lookup"><span data-stu-id="53ef7-290">The display name of the new application that you created</span></span> | <span data-ttu-id="53ef7-291">Deltagare</span><span class="sxs-lookup"><span data-stu-id="53ef7-291">Contributor</span></span>                 |
        | <span data-ttu-id="53ef7-292">Visningsnamnet för det nya program som du skapade</span><span class="sxs-lookup"><span data-stu-id="53ef7-292">The display name of the new application that you created</span></span> | <span data-ttu-id="53ef7-293">Lagringskontodeltagare</span><span class="sxs-lookup"><span data-stu-id="53ef7-293">Storage Account Contributor</span></span> |
        | <span data-ttu-id="53ef7-294">Visningsnamnet för det nya program som du skapade</span><span class="sxs-lookup"><span data-stu-id="53ef7-294">The display name of the new application that you created</span></span> | <span data-ttu-id="53ef7-295">Storage Blob Data-ägare</span><span class="sxs-lookup"><span data-stu-id="53ef7-295">Storage Blob Data Owner</span></span>     |
        | <span data-ttu-id="53ef7-296">**AI Builder Authorization Service**</span><span class="sxs-lookup"><span data-stu-id="53ef7-296">**AI Builder Authorization Service**</span></span>                     | <span data-ttu-id="53ef7-297">Storage Blob Data-läsare</span><span class="sxs-lookup"><span data-stu-id="53ef7-297">Storage Blob Data Reader</span></span>    |

# <a name="azure-cli"></a>[<span data-ttu-id="53ef7-298">Azure CLI</span><span class="sxs-lookup"><span data-stu-id="53ef7-298">Azure CLI</span></span>](#tab/azure-azure-cli)

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



## <a name="configure-the-data-lake"></a><span data-ttu-id="53ef7-299">Konfigurera datasjön</span><span class="sxs-lookup"><span data-stu-id="53ef7-299">Configure the data lake</span></span>

<span data-ttu-id="53ef7-300">Följ dessa steg för att använda LCS för att lägga till Azure Data Lake-tillägget i miljön.</span><span class="sxs-lookup"><span data-stu-id="53ef7-300">Follow these steps to use LCS to add the Azure Data Lake add-in to the environment.</span></span>

1. <span data-ttu-id="53ef7-301">Logga in på LCS och välj sedan **Fullständig information** under miljönamnet till höger på sidan.</span><span class="sxs-lookup"><span data-stu-id="53ef7-301">Sign in to LCS, and then, under the environment name on the right side of the page, select **Full Details**.</span></span>
2. <span data-ttu-id="53ef7-302">I avsnittet **Miljötillägg**, välj **Installera ett nytt tillägg**.</span><span class="sxs-lookup"><span data-stu-id="53ef7-302">In the **Environment add-ins** section, select **Install a new add-in**.</span></span>
3. <span data-ttu-id="53ef7-303">Välj tillägget **Exportera till data Lake**.</span><span class="sxs-lookup"><span data-stu-id="53ef7-303">Select the **Export to Data Lake** add-in.</span></span>
4. <span data-ttu-id="53ef7-304">Ange följande värden.</span><span class="sxs-lookup"><span data-stu-id="53ef7-304">Enter the following values.</span></span>

    | <span data-ttu-id="53ef7-305">Värde</span><span class="sxs-lookup"><span data-stu-id="53ef7-305">Value</span></span>                                                              | <span data-ttu-id="53ef7-306">beskrivning</span><span class="sxs-lookup"><span data-stu-id="53ef7-306">Description</span></span> |
    |--------------------------------------------------------------------|-------------|
    | <span data-ttu-id="53ef7-307">Klientorganisations-ID för Azure-prenumerationen där nyckelvalvet finns</span><span class="sxs-lookup"><span data-stu-id="53ef7-307">Tenant ID of the Azure Subscription where the Key Vault is located</span></span> | <span data-ttu-id="53ef7-308">Det klientorganisations-ID där lagringskontot, programmen och nyckelvalven finns.</span><span class="sxs-lookup"><span data-stu-id="53ef7-308">The tenant ID where the storage account, apps, and key vaults are located.</span></span> <span data-ttu-id="53ef7-309">Du hittar det här värdet genom att öppna [Azure-portalen](https://portal.azure.com), gå till **Azure Active Directory** och kopiera värdet för **Klientorganisations-ID**.</span><span class="sxs-lookup"><span data-stu-id="53ef7-309">To find this value, open the [Azure portal](https://portal.azure.com), go to **Azure Active Directory**, and copy the **Tenant ID** value.</span></span> |
    | <span data-ttu-id="53ef7-310">Ange DNS-namnet på ditt Key Vault</span><span class="sxs-lookup"><span data-stu-id="53ef7-310">Provide the DNS name of your Key Vault</span></span>                             | <span data-ttu-id="53ef7-311">Nyckelvalvets DNS-namn, till exempel `https://customkeyvault.vault.azure.net/`.</span><span class="sxs-lookup"><span data-stu-id="53ef7-311">The DNS name of the key vault, such as `https://customkeyvault.vault.azure.net/`.</span></span> <span data-ttu-id="53ef7-312">(Det här värdet matchar DNS-namnet som används i entitetsarkivet.)</span><span class="sxs-lookup"><span data-stu-id="53ef7-312">(This value matches the DNS name that is used in the entity store.)</span></span> |
    | <span data-ttu-id="53ef7-313">Ange hemligheten som innehåller namnet på lagringskontot</span><span class="sxs-lookup"><span data-stu-id="53ef7-313">Provide the secret that contains the name of the storage account</span></span>   | <span data-ttu-id="53ef7-314">**lagringskontonamn**</span><span class="sxs-lookup"><span data-stu-id="53ef7-314">**storage-account-name**</span></span> |
    | <span data-ttu-id="53ef7-315">Hemligt namn för det program-ID som ska användas för åtkomst till Data Lake</span><span class="sxs-lookup"><span data-stu-id="53ef7-315">Secret Name for App ID to be used for accessing Data Lake</span></span>          | <span data-ttu-id="53ef7-316">**program-ID**</span><span class="sxs-lookup"><span data-stu-id="53ef7-316">**app-id**</span></span> |
    | <span data-ttu-id="53ef7-317">Hemligt namn som ska användas med program-ID</span><span class="sxs-lookup"><span data-stu-id="53ef7-317">Secret name to be used with App ID</span></span>                                 | <span data-ttu-id="53ef7-318">**programhemlighet**</span><span class="sxs-lookup"><span data-stu-id="53ef7-318">**app-secret**</span></span> |

5. <span data-ttu-id="53ef7-319">Godkänn villkoren och välj **Installera**.</span><span class="sxs-lookup"><span data-stu-id="53ef7-319">Agree to the terms, and select **Install**.</span></span>

<span data-ttu-id="53ef7-320">Tillägget kommer att installeras inom några minuter.</span><span class="sxs-lookup"><span data-stu-id="53ef7-320">The add-in will be installed within a few minutes.</span></span>

## <a name="configure-ai-builder"></a><span data-ttu-id="53ef7-321">Konfigurera AI Builder</span><span class="sxs-lookup"><span data-stu-id="53ef7-321">Configure AI Builder</span></span>

1. <span data-ttu-id="53ef7-322">Logga in på LCS och öppna sidan **Miljöinformation**.</span><span class="sxs-lookup"><span data-stu-id="53ef7-322">Sign in to LCS, and open the **Environment details** page.</span></span>
2. <span data-ttu-id="53ef7-323">Bläddra till avsnittet **Miljötillägg**.</span><span class="sxs-lookup"><span data-stu-id="53ef7-323">Scroll to the **Environment add-ins** section.</span></span> <span data-ttu-id="53ef7-324">De tillägg som redan är installerade i den här miljön bör visas.</span><span class="sxs-lookup"><span data-stu-id="53ef7-324">You should see the add-ins that are already installed in this environment.</span></span> <span data-ttu-id="53ef7-325">Om tillägget **Exportera till Data Lake** inte är bland dem konfigurerar du det här tillägget.</span><span class="sxs-lookup"><span data-stu-id="53ef7-325">If the **Export to Data Lake** add-in isn't among them, configure this add-in.</span></span>
3. <span data-ttu-id="53ef7-326">Välj tillägget **Hämta insikter**.</span><span class="sxs-lookup"><span data-stu-id="53ef7-326">Select the **Get insights** add-in.</span></span>
4. <span data-ttu-id="53ef7-327">Ange följande värden på informationssidan för tillägget **Hämta insikter**.</span><span class="sxs-lookup"><span data-stu-id="53ef7-327">On the **Get insights** add-in details page, enter the following values.</span></span>

    | <span data-ttu-id="53ef7-328">Värde</span><span class="sxs-lookup"><span data-stu-id="53ef7-328">Value</span></span>                                                    | <span data-ttu-id="53ef7-329">beskrivning</span><span class="sxs-lookup"><span data-stu-id="53ef7-329">Description</span></span> |
    |----------------------------------------------------------|-------------|
    | <span data-ttu-id="53ef7-330">URL för CDS-organisations</span><span class="sxs-lookup"><span data-stu-id="53ef7-330">CDS Organization URL</span></span>                                     | <span data-ttu-id="53ef7-331">Dataverse-organisationens URL kopierat från ovan.</span><span class="sxs-lookup"><span data-stu-id="53ef7-331">The Dataverse organization URL copied from above.</span></span> |
    | <span data-ttu-id="53ef7-332">CDS Org-ID</span><span class="sxs-lookup"><span data-stu-id="53ef7-332">CDS Org ID</span></span>                                               | <span data-ttu-id="53ef7-333">Dataverse-organisationens ID kopierat från ovan.</span><span class="sxs-lookup"><span data-stu-id="53ef7-333">The Dataverse organization ID copied from above.</span></span> |
5. <span data-ttu-id="53ef7-334">Aktivera **Är detta standardmiljön för din klientorganisation**.</span><span class="sxs-lookup"><span data-stu-id="53ef7-334">Enable **Is this the default environment for you Tenant**.</span></span>
    
## <a name="configure-the-entity-store"></a><span data-ttu-id="53ef7-335">Konfigurera entitetsarkivet</span><span class="sxs-lookup"><span data-stu-id="53ef7-335">Configure the entity store</span></span>

<span data-ttu-id="53ef7-336">Följ dessa steg för att konfigurera entitetsarkivet i Finance-miljön.</span><span class="sxs-lookup"><span data-stu-id="53ef7-336">Follow these steps to set up the entity store in your Finance environment.</span></span>

1. <span data-ttu-id="53ef7-337">Gå till **Systemadministration \> Konfigurera \> Systemparametrar \> Dataanslutningar**.</span><span class="sxs-lookup"><span data-stu-id="53ef7-337">Go to **System administration \> Setup \> System parameters \> Data connections**.</span></span>
2. <span data-ttu-id="53ef7-338">Ange följande nyckelvalvsfält:</span><span class="sxs-lookup"><span data-stu-id="53ef7-338">Set the following key vault fields:</span></span>

    - <span data-ttu-id="53ef7-339">**Program-ID (klient)** – Ange programmets klient-ID som du skapade tidigare.</span><span class="sxs-lookup"><span data-stu-id="53ef7-339">**Application (client) ID** – Enter the application client ID that you created earlier.</span></span>
    - <span data-ttu-id="53ef7-340">**Programhemlighet** – Ange hemligheten som du sparade för programmet du skapade tidigare.</span><span class="sxs-lookup"><span data-stu-id="53ef7-340">**Application Secret** – Enter the secret that you saved for the application that you created earlier.</span></span>
    - <span data-ttu-id="53ef7-341">**DNS-namn** – Du hittar DNS-namnet (Domain Name System) på sidan med programinformation för programmet som du skapade tidigare.</span><span class="sxs-lookup"><span data-stu-id="53ef7-341">**DNS name** – You can find the Domain Name System (DNS) name on the application details page for the application that you created earlier.</span></span>
    - <span data-ttu-id="53ef7-342">**Hemligt namn** – Ange **lagringskontots anslutningssträng**.</span><span class="sxs-lookup"><span data-stu-id="53ef7-342">**Secret name** – Enter **storage-account-connection-string**.</span></span>
3. <span data-ttu-id="53ef7-343">Aktivera **Aktivera Data Lake-integrering**.</span><span class="sxs-lookup"><span data-stu-id="53ef7-343">Enable **Enable Data Lake integration**.</span></span>
4. <span data-ttu-id="53ef7-344">Välj **Testa Azure Key Vault** och kontrollera att det inte finns några fel.</span><span class="sxs-lookup"><span data-stu-id="53ef7-344">Select **Test Azure Key Vault** and verify there are no errors.</span></span>
5. <span data-ttu-id="53ef7-345">Välj **Testa Azure-lagring** och kontrollera att det inte finns några fel.</span><span class="sxs-lookup"><span data-stu-id="53ef7-345">Select **Test Azure storage** and verify there are no errors.</span></span>

## <a name="feedback-and-support"></a><span data-ttu-id="53ef7-346">Feedback och support</span><span class="sxs-lookup"><span data-stu-id="53ef7-346">Feedback and support</span></span>

<span data-ttu-id="53ef7-347">Skicka ett e-postmeddelande till [Kundbetalningsinsikter (förhandsversion)](mailto:fiap@microsoft.com) om du är intresserad av att ge feedback eller behöver support.</span><span class="sxs-lookup"><span data-stu-id="53ef7-347">Please send an email to [Customer payment insights (Preview)](mailto:fiap@microsoft.com) if you are interested in providing feedback or need support.</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="53ef7-348">Sekretesspolicy</span><span class="sxs-lookup"><span data-stu-id="53ef7-348">Privacy notice</span></span>

<span data-ttu-id="53ef7-349">Förhandsversioner (1) kan använda färre sekretess- och säkerhetsfunktioner än Dynamics 365 Finance and Operations, (2) de ingår inte i serviceavtalet (SLA) för den här tjänsten, (3) bör inte användas för behandling av personuppgifter eller andra uppgifter som omfattas av lagar och andra efterlevnadskrav, samt (4) har begränsad support.</span><span class="sxs-lookup"><span data-stu-id="53ef7-349">Previews (1) might use less privacy and fewer security measures than the Dynamics 365 Finance and Operations service, (2) aren't included in the service level agreement (SLA) for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) have limited support.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
