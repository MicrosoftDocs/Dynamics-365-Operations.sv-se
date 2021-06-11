---
title: Konfigurera virtuella Dataverse-register
description: I detta ämne beskrivs hur du konfigurerar virtuella register för Dynamics 365 Human Resources. Generera och uppdatera befintliga virtuella register, samt analysera genererade och tillgängliga register.
author: andreabichsel
ms.date: 01/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CDSIntegrationAdministration
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-10-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8c2e207efe0eeec6fc7e679a6ae12edcb21b291f
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/18/2021
ms.locfileid: "6058594"
---
# <a name="configure-dataverse-virtual-tables"></a><span data-ttu-id="9e247-104">Konfigurera virtuella Dataverse-register</span><span class="sxs-lookup"><span data-stu-id="9e247-104">Configure Dataverse virtual tables</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="9e247-105">Dynamics 365 Human Resources är en virtuell datakälla i Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="9e247-105">Dynamics 365 Human Resources is a virtual data source in Microsoft Dataverse.</span></span> <span data-ttu-id="9e247-106">Det ger fullständiga åtgärder för att skapa, läsa, uppdatera och ta bort (CRUD) från Dataverse och Microsoft Power Platform.</span><span class="sxs-lookup"><span data-stu-id="9e247-106">It provides full create, read, update, and delete (CRUD) operations from Dataverse and Microsoft Power Platform.</span></span> <span data-ttu-id="9e247-107">Data för virtuella register lagras inte i Dataverse utan i programdatabasen.</span><span class="sxs-lookup"><span data-stu-id="9e247-107">The data for virtual tables isn't stored in Dataverse, but in the application database.</span></span>

<span data-ttu-id="9e247-108">Om du vill aktivera CRUD-åtgärder i Personal-entiteter från Dataverse måste du göra entiteterna tillgängliga som virtuella register i Dataverse.</span><span class="sxs-lookup"><span data-stu-id="9e247-108">To enable CRUD operations on Human Resources entities from Dataverse, you must make the entities available as virtual tables in Dataverse.</span></span> <span data-ttu-id="9e247-109">På så sätt kan du utföra CRUD operationer från Dataverse och Microsoft Power Platform på data i personal.</span><span class="sxs-lookup"><span data-stu-id="9e247-109">This lets you perform CRUD operations from Dataverse and Microsoft Power Platform on data that's in Human Resources.</span></span> <span data-ttu-id="9e247-110">Operationerna stöder även de affärslogik valideringar av personal som garanterar data integritet när data skrivs till enheterna.</span><span class="sxs-lookup"><span data-stu-id="9e247-110">The operations also support the full business logic validations of Human Resources to ensure data integrity when writing data to the entities.</span></span>

> [!NOTE]
> <span data-ttu-id="9e247-111">Personal-entiteter motsvarar Dataverse-register.</span><span class="sxs-lookup"><span data-stu-id="9e247-111">Human Resources entities correspond to Dataverse tables.</span></span> <span data-ttu-id="9e247-112">Mer information om Dataverse (tidigare Common Data Service) och terminologiuppdateringar finns i [Vad är Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)</span><span class="sxs-lookup"><span data-stu-id="9e247-112">For more information about Dataverse (formerly Common Data Service) and terminology updates, see [What is Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)</span></span>

## <a name="available-virtual-tables-for-human-resources"></a><span data-ttu-id="9e247-113">Tillgängliga virtuella register för Personal</span><span class="sxs-lookup"><span data-stu-id="9e247-113">Available virtual tables for Human Resources</span></span>

<span data-ttu-id="9e247-114">Alla OData-entiteter (Open Data Protocol) i Personal är tillgängliga som virtuella register i Dataverse.</span><span class="sxs-lookup"><span data-stu-id="9e247-114">All Open Data Protocol (OData) entities in Human Resources are available as virtual tables in Dataverse.</span></span> <span data-ttu-id="9e247-115">De är också tillgängliga i Power Platform.</span><span class="sxs-lookup"><span data-stu-id="9e247-115">They're also available in Power Platform.</span></span> <span data-ttu-id="9e247-116">Du kan nu bygga appar och erfarenheter med data direkt från personal med fullständig CRUD-kapacitet, utan att kopiera eller synkronisera data till Dataverse.</span><span class="sxs-lookup"><span data-stu-id="9e247-116">You can now build apps and experiences with data directly from Human Resources with full CRUD capability, without copying or synchronizing data to Dataverse.</span></span> <span data-ttu-id="9e247-117">Du kan använda Power Apps-portaler för att skapa externa webbplatser som möjliggör samarbetsscenarier för affärsprocesser i personal.</span><span class="sxs-lookup"><span data-stu-id="9e247-117">You can use Power Apps portals to build external-facing websites that enable collaboration scenarios for business processes in Human Resources.</span></span>

<span data-ttu-id="9e247-118">Du kan visa listan med virtuella register som är aktiverade i miljön och börja arbeta med registren i [Power Apps](https://make.powerapps.com), i lösningen **Virtuella personalregister för Dynamics 365**.</span><span class="sxs-lookup"><span data-stu-id="9e247-118">You can view the list of virtual tables enabled in the environment, and begin working with the tables in [Power Apps](https://make.powerapps.com), in the **Dynamics 365 HR Virtual Tables** solution.</span></span>

![Virtuella personalregister för Dynamics 365 i Power Apps](./media/hr-admin-integration-virtual-entities-power-apps.jpg)

## <a name="virtual-tables-versus-native-tables"></a><span data-ttu-id="9e247-120">Virtuella register kontra inbyggda register</span><span class="sxs-lookup"><span data-stu-id="9e247-120">Virtual tables versus native tables</span></span>

<span data-ttu-id="9e247-121">Virtuella register Personal är inte samma sak som de inbyggda Dataverse-register som har skapats för Personal.</span><span class="sxs-lookup"><span data-stu-id="9e247-121">Virtual tables for Human Resources aren't the same as the native Dataverse tables created for Human Resources.</span></span> 

<span data-ttu-id="9e247-122">De inbyggda registren för Personal genereras separat och underhålls i den gemensamma HCM-lösningen i Dataverse.</span><span class="sxs-lookup"><span data-stu-id="9e247-122">The native tables for Human Resources are generated separately and maintained in the HCM Common solution in Dataverse.</span></span> <span data-ttu-id="9e247-123">Med inbyggda register lagras data i Dataverse och måste synkroniseras med programdatabasen för Personal.</span><span class="sxs-lookup"><span data-stu-id="9e247-123">With native tables, the data is stored in Dataverse and requires synchronization with the Human Resources application database.</span></span>

> [!NOTE]
> <span data-ttu-id="9e247-124">En lista över de inbyggda Dataverse-registren för Personal finns i [Dataverse-register](./hr-developer-entities.md).</span><span class="sxs-lookup"><span data-stu-id="9e247-124">For a list of the native Dataverse tables for Human Resources, see [Dataverse tables](./hr-developer-entities.md).</span></span>

## <a name="setup"></a><span data-ttu-id="9e247-125">Ställ in</span><span class="sxs-lookup"><span data-stu-id="9e247-125">Setup</span></span>

<span data-ttu-id="9e247-126">Följ dessa installationssteg för att aktivera virtuella register i din miljö.</span><span class="sxs-lookup"><span data-stu-id="9e247-126">Follow these setup steps to enable virtual tables in your environment.</span></span>

### <a name="enable-virtual-tables-in-human-resources"></a><span data-ttu-id="9e247-127">Aktivera virtuella register i Personal</span><span class="sxs-lookup"><span data-stu-id="9e247-127">Enable virtual tables in Human Resources</span></span>

<span data-ttu-id="9e247-128">Först måste du aktivera virtuella register i arbetsytan **Funktionshantering**.</span><span class="sxs-lookup"><span data-stu-id="9e247-128">First, you must enable virtual tables in the **Feature management** workspace.</span></span>

1. <span data-ttu-id="9e247-129">I Personal, välj **Systemadministration**.</span><span class="sxs-lookup"><span data-stu-id="9e247-129">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="9e247-130">Välj panelen **funktionshantering**.</span><span class="sxs-lookup"><span data-stu-id="9e247-130">Select the **Feature management** tile.</span></span>

3. <span data-ttu-id="9e247-131">Välj **Stöd för virtuella register för Personal i Dataverse** och sedan **Aktivera**.</span><span class="sxs-lookup"><span data-stu-id="9e247-131">Select **Virtual table support for HR in Dataverse**, and then select **Enable**.</span></span>

<span data-ttu-id="9e247-132">Mer information om att aktivera och inaktivera funktioner finns i [Hantera funktioner](hr-admin-manage-features.md).</span><span class="sxs-lookup"><span data-stu-id="9e247-132">For more information about enabling and disabling features, see [Manage features](hr-admin-manage-features.md).</span></span>

### <a name="register-the-app-in-microsoft-azure"></a><span data-ttu-id="9e247-133">Registrera appen i Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="9e247-133">Register the app in Microsoft Azure</span></span>

<span data-ttu-id="9e247-134">Du måste registrera din Human Resource-instans i Azure-portalen så att Microsofts identitetsplattform kan tillhandahålla autentisering och auktoriseringstjänster för appen och användarna.</span><span class="sxs-lookup"><span data-stu-id="9e247-134">You must register your Human Resources instance in the Azure portal so the Microsoft identity platform can provide authentication and authorization services for the app and users.</span></span> <span data-ttu-id="9e247-135">Mer information om registrering av program i Azure finns i [snabbstart: registrera ett app med Microsoft identitetsplattform](/azure/active-directory/develop/quickstart-register-app).</span><span class="sxs-lookup"><span data-stu-id="9e247-135">For more information about registering apps in Azure, see [Quickstart: Register an application with the Microsoft identity platform](/azure/active-directory/develop/quickstart-register-app).</span></span>

1. <span data-ttu-id="9e247-136">Öppna [Microsoft Azure-portal](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="9e247-136">Open the [Microsoft Azure portal](https://portal.azure.com).</span></span>

2. <span data-ttu-id="9e247-137">I listan Azure-tjänster, välj **App-registreringar**.</span><span class="sxs-lookup"><span data-stu-id="9e247-137">In the Azure services list, select **App registrations**.</span></span>

3. <span data-ttu-id="9e247-138">Välj **Ny registrering**.</span><span class="sxs-lookup"><span data-stu-id="9e247-138">Select **New registration**.</span></span>

4. <span data-ttu-id="9e247-139">I fältet **Namn** ange ett beskrivande namn för appen.</span><span class="sxs-lookup"><span data-stu-id="9e247-139">In the **Name** field, enter a descriptive name for the app.</span></span> <span data-ttu-id="9e247-140">Till exempel **Virtuella register för Dynamics 365 Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="9e247-140">For example, **Dynamics 365 Human Resources Virtual Tables**.</span></span>

5. <span data-ttu-id="9e247-141">I fältet **Omdirigera URI** ange namnrymd-URL för din instans av personal.</span><span class="sxs-lookup"><span data-stu-id="9e247-141">In the **Redirect URI** field, enter the namespace URL of your instance of Human Resources.</span></span>

6. <span data-ttu-id="9e247-142">Välj **Registrera**.</span><span class="sxs-lookup"><span data-stu-id="9e247-142">Select **Register**.</span></span>

7. <span data-ttu-id="9e247-143">När registreringen är klar visar Azure-portalen appregistreringen rutan **översikt** som innehåller dess **App-ID (klient)**.</span><span class="sxs-lookup"><span data-stu-id="9e247-143">When registration completes, the Azure portal displays the app registration's **Overview** pane, which includes its **Application (client) ID**.</span></span> <span data-ttu-id="9e247-144">Anteckna **App-ID (klient)** för tillfället.</span><span class="sxs-lookup"><span data-stu-id="9e247-144">Take note of the **Application (client) ID** at this time.</span></span> <span data-ttu-id="9e247-145">Du anger denna information när du [konfigurerar det virtuella registrets datakälla](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source).</span><span class="sxs-lookup"><span data-stu-id="9e247-145">You'll enter this information when you [Configure the virtual table data source](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source).</span></span>

8. <span data-ttu-id="9e247-146">I det vänstra navigeringsfönstret, välj **certifikat och hemligheter**.</span><span class="sxs-lookup"><span data-stu-id="9e247-146">In the left navigation pane, select **Certificates and secrets**.</span></span>

9. <span data-ttu-id="9e247-147">I avsnittet **klienthemlighet** på sidan **ny klienthemlighet**.</span><span class="sxs-lookup"><span data-stu-id="9e247-147">In the **Client secrets** section of the page, select **New client secret**.</span></span>

10. <span data-ttu-id="9e247-148">Ange en beskrivning, välj en varaktighet och välj sedan **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="9e247-148">Provide a description, select a duration, and select **Add**.</span></span>

11. <span data-ttu-id="9e247-149">Registrera hemlighetens värde från egenskapen **Värde** för registret.</span><span class="sxs-lookup"><span data-stu-id="9e247-149">Record the secret's value from the **Value** property of the table.</span></span> <span data-ttu-id="9e247-150">Du anger denna information när du [konfigurerar det virtuella registrets datakälla](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source).</span><span class="sxs-lookup"><span data-stu-id="9e247-150">You'll enter this information when you [Configure the virtual table data source](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="9e247-151">Se till att du noterar hemlighetens värde just nu.</span><span class="sxs-lookup"><span data-stu-id="9e247-151">Be sure to take note of the secret's value at this time.</span></span> <span data-ttu-id="9e247-152">Hemligheten visas aldrig igen när du har lämnat den här sidan.</span><span class="sxs-lookup"><span data-stu-id="9e247-152">The secret is never displayed again after you leave this page.</span></span>

### <a name="install-the-dynamics-365-hr-virtual-table-app"></a><span data-ttu-id="9e247-153">Installera appen Dynamics 365 HR Virtual Table</span><span class="sxs-lookup"><span data-stu-id="9e247-153">Install the Dynamics 365 HR Virtual Table app</span></span>

<span data-ttu-id="9e247-154">Installera appen Dynamics 365 HR Virtual Table i din Power Apps-miljö för att distribuera lösningspaketet för virtuellt register till Dataverse.</span><span class="sxs-lookup"><span data-stu-id="9e247-154">Install the Dynamics 365 HR Virtual Table app in your Power Apps environment to deploy the virtual table solution package to Dataverse.</span></span>

1. <span data-ttu-id="9e247-155">I Personal öppnar du sidan **Microsoft Dataverse-integrering**.</span><span class="sxs-lookup"><span data-stu-id="9e247-155">In Human Resources, open the **Microsoft Dataverse integration** page.</span></span>

2. <span data-ttu-id="9e247-156">Välj fliken **Virtuella register**.</span><span class="sxs-lookup"><span data-stu-id="9e247-156">Select the **Virtual tables** tab.</span></span>

3. <span data-ttu-id="9e247-157">Välj **Installera program för virtuellt register**.</span><span class="sxs-lookup"><span data-stu-id="9e247-157">Select **Install virtual table app**.</span></span>

### <a name="configure-the-virtual-table-data-source"></a><span data-ttu-id="9e247-158">Konfigurera den virtuella datakällan för register</span><span class="sxs-lookup"><span data-stu-id="9e247-158">Configure the virtual table data source</span></span>

<span data-ttu-id="9e247-159">Nästa steg är att konfigurera datakällan för det virtuella registret i Power Apps-miljön.</span><span class="sxs-lookup"><span data-stu-id="9e247-159">The next step is to configure the virtual table data source in the Power Apps environment.</span></span>

1. <span data-ttu-id="9e247-160">Öppna [Power Platform administrationscenter](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="9e247-160">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="9e247-161">I listan **miljöer**, välj Power Apps-miljö som är kopplad till personalinstansen.</span><span class="sxs-lookup"><span data-stu-id="9e247-161">In the **Environments** list, select the Power Apps environment associated with your Human Resources instance.</span></span>

3. <span data-ttu-id="9e247-162">Välj **miljö-URL** i avsnittet **information** på sidan.</span><span class="sxs-lookup"><span data-stu-id="9e247-162">Select the **Environment URL** in the **Details** section of the page.</span></span>

4. <span data-ttu-id="9e247-163">I **Lösning hälsocenter**, välj ikonen **Avancerad sökning** längst upp till höger på appsidan.</span><span class="sxs-lookup"><span data-stu-id="9e247-163">In the **Solution Health Hub**, select the **Advanced Find** icon in the top right of the application page.</span></span>

5. <span data-ttu-id="9e247-164">På sidan **Avancerad sökning** i listrutan **Sök efter** välj **Konfiguration av virtuella enhetens datakälla i Finance and Operations**.</span><span class="sxs-lookup"><span data-stu-id="9e247-164">On the **Advanced Find** page, in the **Look for** dropdown list, select **Finance and Operations Virtual Data Source Configurations**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="9e247-165">Installationen av det virtuella registerprogrammet från föregående inställningssteg kan ta några minuter.</span><span class="sxs-lookup"><span data-stu-id="9e247-165">The installation of the virtual table app from the previous setup step can take a few minutes.</span></span> <span data-ttu-id="9e247-166">Om **Källkonfigurationer för virtuella Finance and Operations-data** inte är tillgängligt i listan ska du vänta en minut och sedan uppdatera listan.</span><span class="sxs-lookup"><span data-stu-id="9e247-166">If **Finance and Operations Virtual Data Source Configurations** isn't available in the list, wait for a minute and refresh the list.</span></span>

6. <span data-ttu-id="9e247-167">Välj **resultat**.</span><span class="sxs-lookup"><span data-stu-id="9e247-167">Select **Results**.</span></span>

7. <span data-ttu-id="9e247-168">Markera posten **Microsoft HR datakälla**.</span><span class="sxs-lookup"><span data-stu-id="9e247-168">Select the **Microsoft HR Data Source** record.</span></span>

8. <span data-ttu-id="9e247-169">Ange den information som krävs för konfigurationen av datakällan:</span><span class="sxs-lookup"><span data-stu-id="9e247-169">Enter the required information for the data source configuration:</span></span>

   - <span data-ttu-id="9e247-170">**Mål-URL**: en URL till din personal namnrymd.</span><span class="sxs-lookup"><span data-stu-id="9e247-170">**Target URL**: The URL of your Human Resources namespace.</span></span> <span data-ttu-id="9e247-171">Formatet för mål-URL:en är:</span><span class="sxs-lookup"><span data-stu-id="9e247-171">The format of the target URL is:</span></span>
     
     <span data-ttu-id="9e247-172">https://\<hostname\>.hr.talent.dynamics.com/namespaces/\<namespaceID\>/</span><span class="sxs-lookup"><span data-stu-id="9e247-172">https://\<hostname\>.hr.talent.dynamics.com/namespaces/\<namespaceID\>/</span></span>

     <span data-ttu-id="9e247-173">Exempel:</span><span class="sxs-lookup"><span data-stu-id="9e247-173">For example:</span></span>
     
     `https://aos.rts-sf-5ea54e35c68-westus2.hr.talent.dynamics.com/namespaces/49d24c565-8f4d-4891-b174-bf83d948ed0c/`

     >[!NOTE]
     ><span data-ttu-id="9e247-174">Se till att du tar med "**/**"-tecknet i slutet av URL:en för att undvika att få ett fel.</span><span class="sxs-lookup"><span data-stu-id="9e247-174">Be sure to include the "**/**" character at the end of the URL to avoid receiving an error.</span></span>

   - <span data-ttu-id="9e247-175">**Klientorganisations-ID**: Azure Active Directory (Azure AD) klientorganisations-ID.</span><span class="sxs-lookup"><span data-stu-id="9e247-175">**Tenant ID**: The Azure Active Directory (Azure AD) tenant ID.</span></span>

   - <span data-ttu-id="9e247-176">**AAD app-ID**: det app-ID (klient) som skapades för den app som är registrerat i Microsoft Azure-portalen.</span><span class="sxs-lookup"><span data-stu-id="9e247-176">**AAD Application ID**: The application (client) ID created for the application registered in the Microsoft Azure portal.</span></span> <span data-ttu-id="9e247-177">Du har fått den här informationen tidigare under steget [Registrera appen i Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span><span class="sxs-lookup"><span data-stu-id="9e247-177">You received this information earlier during the step [Register the app in Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span></span>

   - <span data-ttu-id="9e247-178">**Hemlighet för AAD app-ID**: klienthemligheten som skapades för den app som är registrerat i Microsoft Azure-portalen.</span><span class="sxs-lookup"><span data-stu-id="9e247-178">**AAD Application Secret**: The client secret created for the application registered in the Microsoft Azure portal.</span></span> <span data-ttu-id="9e247-179">Du har fått den här informationen tidigare under steget [Registrera appen i Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span><span class="sxs-lookup"><span data-stu-id="9e247-179">You received this information earlier during the step [Register the app in Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span></span>

   ![Microsoft HR-datakälla](./media/hr-admin-integration-virtual-entities-hr-data-source.jpg)

9. <span data-ttu-id="9e247-181">Välj **Spara och stäng**.</span><span class="sxs-lookup"><span data-stu-id="9e247-181">Select **Save & Close**.</span></span>

### <a name="grant-app-permissions-in-human-resources"></a><span data-ttu-id="9e247-182">Ge appbehörighet i Personal</span><span class="sxs-lookup"><span data-stu-id="9e247-182">Grant app permissions in Human Resources</span></span>

<span data-ttu-id="9e247-183">Bevilja behörigheter för de två Azure AD-apparna i Personal:</span><span class="sxs-lookup"><span data-stu-id="9e247-183">Grant permissions for the two Azure AD applications in Human Resources:</span></span>

- <span data-ttu-id="9e247-184">Appen som har skapats för din innehavare på Microsoft Azure-portalen</span><span class="sxs-lookup"><span data-stu-id="9e247-184">The app created for your tenant in the Microsoft Azure portal</span></span>
- <span data-ttu-id="9e247-185">Appen Dynamics 365 HR Virtual Table installeras i Power Apps-miljön</span><span class="sxs-lookup"><span data-stu-id="9e247-185">The Dynamics 365 HR Virtual Table app installed in the Power Apps environment</span></span> 

1. <span data-ttu-id="9e247-186">I Personal, öppna sidan **Azure Active Directory-appar**.</span><span class="sxs-lookup"><span data-stu-id="9e247-186">In Human Resources, open the **Azure Active Directory applications** page.</span></span>

2. <span data-ttu-id="9e247-187">Välj **Nytt** för att skapa en ny appost:</span><span class="sxs-lookup"><span data-stu-id="9e247-187">Select **New** to create a new application record:</span></span>

    - <span data-ttu-id="9e247-188">I fältet **klient-ID** anger du klient-ID för appen som du registrerade på Microsoft Azure-portalen.</span><span class="sxs-lookup"><span data-stu-id="9e247-188">In the **Client ID** field, enter the client ID of the app you registered in the Microsoft Azure portal.</span></span>
    - <span data-ttu-id="9e247-189">I fältet **Namn** anger du namnet för appen som du registrerade på Microsoft Azure-portalen.</span><span class="sxs-lookup"><span data-stu-id="9e247-189">In the **Name** field, enter the name of the app you registered in the Microsoft Azure portal.</span></span>
    - <span data-ttu-id="9e247-190">I fältet **Användar-ID** väljer du användar-ID för en användare med administratörsbehörighet i Personal och Power Apps-miljön.</span><span class="sxs-lookup"><span data-stu-id="9e247-190">In the **User ID** field, select the user ID of a user with admin permissions in Human Resources and the Power Apps environment.</span></span>

3. <span data-ttu-id="9e247-191">Välj **Nytt** för att skapa en andra appost:</span><span class="sxs-lookup"><span data-stu-id="9e247-191">Select **New** to create a second application record:</span></span>

    - <span data-ttu-id="9e247-192">**Klient-ID**: f9be0c49-aa22-4ec6-911a-c5da515226ff</span><span class="sxs-lookup"><span data-stu-id="9e247-192">**Client Id**: f9be0c49-aa22-4ec6-911a-c5da515226ff</span></span>
    - <span data-ttu-id="9e247-193">**Namn**: Dynamics 365 HR Virtual Table</span><span class="sxs-lookup"><span data-stu-id="9e247-193">**Name**: Dynamics 365 HR Virtual Table</span></span>
    - <span data-ttu-id="9e247-194">I fältet **Användar-ID** väljer du användar-ID för en användare med administratörsbehörighet i Personal och Power Apps-miljön.</span><span class="sxs-lookup"><span data-stu-id="9e247-194">In the **User ID** field, select the user ID of a user with admin permissions in Human Resources and the Power Apps environment.</span></span>

## <a name="generate-virtual-tables"></a><span data-ttu-id="9e247-195">Generera virtuella register</span><span class="sxs-lookup"><span data-stu-id="9e247-195">Generate virtual tables</span></span>

<span data-ttu-id="9e247-196">När installationsprogrammet är slutfört kan du välja vilka virtuella register du vill generera och aktivera i din Dataverse-instans.</span><span class="sxs-lookup"><span data-stu-id="9e247-196">When setup completes, you can select the virtual tables you want to generate and enable in your Dataverse instance.</span></span>

1. <span data-ttu-id="9e247-197">I Personal öppnar du sidan **Microsoft Dataverse-integrering**.</span><span class="sxs-lookup"><span data-stu-id="9e247-197">In Human Resources, open the **Microsoft Dataverse integration** page.</span></span>

2. <span data-ttu-id="9e247-198">Välj fliken **Virtuella register**.</span><span class="sxs-lookup"><span data-stu-id="9e247-198">Select the **Virtual tables** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="9e247-199">Växlingsknappen **Aktivera virtuella register** anges automatiskt som **Ja** när alla erforderliga inställningar har gjorts.</span><span class="sxs-lookup"><span data-stu-id="9e247-199">The **Enable virtual tables** toggle will be set to **Yes** automatically when all required setup has been completed.</span></span> <span data-ttu-id="9e247-200">Om växlingsknappen är inställd på **Nej** bör du granska stegen i de tidigare avsnitten i det här dokumentet så att alla nödvändiga inställningar är slutförda.</span><span class="sxs-lookup"><span data-stu-id="9e247-200">If the toggle is set to **No**, review the steps in previous sections of this document to ensure all prerequisite setup is completed.</span></span>

3. <span data-ttu-id="9e247-201">Välj det eller de register du vill generera i Dataverse.</span><span class="sxs-lookup"><span data-stu-id="9e247-201">Select the table or tables you want to generate in Dataverse.</span></span>

4. <span data-ttu-id="9e247-202">Välj **generera/uppdatera**.</span><span class="sxs-lookup"><span data-stu-id="9e247-202">Select **Generate/refresh**.</span></span>

![Dataverse-integration](./media/hr-admin-integration-dataverse-integration.png)

## <a name="check-table-generation-status"></a><span data-ttu-id="9e247-204">Kontrollera registrets genereringsstatus</span><span class="sxs-lookup"><span data-stu-id="9e247-204">Check table generation status</span></span>

<span data-ttu-id="9e247-205">Virtuella register genereras i Dataverse genom en asynkron bakgrundsprocess.</span><span class="sxs-lookup"><span data-stu-id="9e247-205">Virtual tables are generated in Dataverse through an asynchronous background process.</span></span> <span data-ttu-id="9e247-206">Uppdateringar av processvisningen i åtgärdscentret.</span><span class="sxs-lookup"><span data-stu-id="9e247-206">Updates on the process display in the action center.</span></span> <span data-ttu-id="9e247-207">Information om processen, inklusive felloggar, visas på sidan **Processautomatiseringar**.</span><span class="sxs-lookup"><span data-stu-id="9e247-207">Details on the process, including error logs, appear in the **Process automations** page.</span></span>

1. <span data-ttu-id="9e247-208">I Personal, öppna listsidan **Processautomatiseringar**.</span><span class="sxs-lookup"><span data-stu-id="9e247-208">In Human Resources, open the **Process automations** page.</span></span>

2. <span data-ttu-id="9e247-209">Välj fliken **Bakgrundsprocesser**.</span><span class="sxs-lookup"><span data-stu-id="9e247-209">Select the **Background processes** tab.</span></span>

3. <span data-ttu-id="9e247-210">Välj **Bakgrundsprocess för virtuell registersökning av asynkron åtgärd**.</span><span class="sxs-lookup"><span data-stu-id="9e247-210">Select **Virtual table poll async operation background process**.</span></span>

4. <span data-ttu-id="9e247-211">Välj **Visa senaste resultat**.</span><span class="sxs-lookup"><span data-stu-id="9e247-211">Select **View most recent results**.</span></span>

<span data-ttu-id="9e247-212">I det utfällbara fönstret visas de senaste körningsresultaten för processen.</span><span class="sxs-lookup"><span data-stu-id="9e247-212">The slideout pane displays the most recent execution results for the process.</span></span> <span data-ttu-id="9e247-213">Du kan visa loggen för processen, inklusive eventuella fel som returnerats från Dataverse.</span><span class="sxs-lookup"><span data-stu-id="9e247-213">You can view the log for the process, including any errors returned from Dataverse.</span></span>

## <a name="see-also"></a><span data-ttu-id="9e247-214">Se även</span><span class="sxs-lookup"><span data-stu-id="9e247-214">See also</span></span>

[<span data-ttu-id="9e247-215">Vad är Dataverse?</span><span class="sxs-lookup"><span data-stu-id="9e247-215">What is Dataverse?</span></span>](/powerapps/maker/common-data-service/data-platform-intro)<br>
[<span data-ttu-id="9e247-216">Register i Dataverse</span><span class="sxs-lookup"><span data-stu-id="9e247-216">Tables in Dataverse</span></span>](/powerapps/maker/common-data-service/entity-overview)<br>
[<span data-ttu-id="9e247-217">Översikt över registerrelationer</span><span class="sxs-lookup"><span data-stu-id="9e247-217">Table relationships overview</span></span>](/powerapps/maker/common-data-service/relationships-overview)<br>
[<span data-ttu-id="9e247-218">Skapa och redigera virtuella register som innehåller data från en extern datakälla</span><span class="sxs-lookup"><span data-stu-id="9e247-218">Create and edit virtual tables that contain data from an external data source</span></span>](/powerapps/maker/common-data-service/create-edit-virtual-entities)<br>
[<span data-ttu-id="9e247-219">Vad är Power Apps-portaler?</span><span class="sxs-lookup"><span data-stu-id="9e247-219">What is Power Apps portals?</span></span>](/powerapps/maker/portals/overview)<br>
[<span data-ttu-id="9e247-220">Översikt över att skapa appar i Power Apps</span><span class="sxs-lookup"><span data-stu-id="9e247-220">Overview of creating apps in Power Apps</span></span>](/powerapps/maker/)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
