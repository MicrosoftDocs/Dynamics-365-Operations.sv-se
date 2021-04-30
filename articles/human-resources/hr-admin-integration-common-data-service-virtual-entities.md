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
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-10-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ae36f1436ddd7f41bf0c3510b47cbc440224f484
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "5890062"
---
# <a name="configure-dataverse-virtual-tables"></a><span data-ttu-id="397be-104">Konfigurera virtuella Dataverse-register</span><span class="sxs-lookup"><span data-stu-id="397be-104">Configure Dataverse virtual tables</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="397be-105">Dynamics 365 Human Resources är en virtuell datakälla i Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="397be-105">Dynamics 365 Human Resources is a virtual data source in Microsoft Dataverse.</span></span> <span data-ttu-id="397be-106">Det ger fullständiga åtgärder för att skapa, läsa, uppdatera och ta bort (CRUD) från Dataverse och Microsoft Power Platform.</span><span class="sxs-lookup"><span data-stu-id="397be-106">It provides full create, read, update, and delete (CRUD) operations from Dataverse and Microsoft Power Platform.</span></span> <span data-ttu-id="397be-107">Data för virtuella register lagras inte i Dataverse utan i programdatabasen.</span><span class="sxs-lookup"><span data-stu-id="397be-107">The data for virtual tables isn't stored in Dataverse, but in the application database.</span></span>

<span data-ttu-id="397be-108">Om du vill aktivera CRUD-åtgärder i Personal-entiteter från Dataverse måste du göra entiteterna tillgängliga som virtuella register i Dataverse.</span><span class="sxs-lookup"><span data-stu-id="397be-108">To enable CRUD operations on Human Resources entities from Dataverse, you must make the entities available as virtual tables in Dataverse.</span></span> <span data-ttu-id="397be-109">På så sätt kan du utföra CRUD operationer från Dataverse och Microsoft Power Platform på data i personal.</span><span class="sxs-lookup"><span data-stu-id="397be-109">This lets you perform CRUD operations from Dataverse and Microsoft Power Platform on data that's in Human Resources.</span></span> <span data-ttu-id="397be-110">Operationerna stöder även de affärslogik valideringar av personal som garanterar data integritet när data skrivs till enheterna.</span><span class="sxs-lookup"><span data-stu-id="397be-110">The operations also support the full business logic validations of Human Resources to ensure data integrity when writing data to the entities.</span></span>

> [!NOTE]
> <span data-ttu-id="397be-111">Personal-entiteter motsvarar Dataverse-register.</span><span class="sxs-lookup"><span data-stu-id="397be-111">Human Resources entities correspond to Dataverse tables.</span></span> <span data-ttu-id="397be-112">Mer information om Dataverse (tidigare Common Data Service) och terminologiuppdateringar finns i [Vad är Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)</span><span class="sxs-lookup"><span data-stu-id="397be-112">For more information about Dataverse (formerly Common Data Service) and terminology updates, see [What is Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)</span></span>

## <a name="available-virtual-tables-for-human-resources"></a><span data-ttu-id="397be-113">Tillgängliga virtuella register för Personal</span><span class="sxs-lookup"><span data-stu-id="397be-113">Available virtual tables for Human Resources</span></span>

<span data-ttu-id="397be-114">Alla OData-entiteter (Open Data Protocol) i Personal är tillgängliga som virtuella register i Dataverse.</span><span class="sxs-lookup"><span data-stu-id="397be-114">All Open Data Protocol (OData) entities in Human Resources are available as virtual tables in Dataverse.</span></span> <span data-ttu-id="397be-115">De är också tillgängliga i Power Platform.</span><span class="sxs-lookup"><span data-stu-id="397be-115">They're also available in Power Platform.</span></span> <span data-ttu-id="397be-116">Du kan nu bygga appar och erfarenheter med data direkt från personal med fullständig CRUD-kapacitet, utan att kopiera eller synkronisera data till Dataverse.</span><span class="sxs-lookup"><span data-stu-id="397be-116">You can now build apps and experiences with data directly from Human Resources with full CRUD capability, without copying or synchronizing data to Dataverse.</span></span> <span data-ttu-id="397be-117">Du kan använda Power Apps-portaler för att skapa externa webbplatser som möjliggör samarbetsscenarier för affärsprocesser i personal.</span><span class="sxs-lookup"><span data-stu-id="397be-117">You can use Power Apps portals to build external-facing websites that enable collaboration scenarios for business processes in Human Resources.</span></span>

<span data-ttu-id="397be-118">Du kan visa listan med virtuella register som är aktiverade i miljön och börja arbeta med registren i [Power Apps](https://make.powerapps.com), i lösningen **Virtuella personalregister för Dynamics 365**.</span><span class="sxs-lookup"><span data-stu-id="397be-118">You can view the list of virtual tables enabled in the environment, and begin working with the tables in [Power Apps](https://make.powerapps.com), in the **Dynamics 365 HR Virtual Tables** solution.</span></span>

![Virtuella personalregister för Dynamics 365 i Power Apps](./media/hr-admin-integration-virtual-entities-power-apps.jpg)

## <a name="virtual-tables-versus-native-tables"></a><span data-ttu-id="397be-120">Virtuella register kontra inbyggda register</span><span class="sxs-lookup"><span data-stu-id="397be-120">Virtual tables versus native tables</span></span>

<span data-ttu-id="397be-121">Virtuella register Personal är inte samma sak som de inbyggda Dataverse-register som har skapats för Personal.</span><span class="sxs-lookup"><span data-stu-id="397be-121">Virtual tables for Human Resources aren't the same as the native Dataverse tables created for Human Resources.</span></span> 

<span data-ttu-id="397be-122">De inbyggda registren för Personal genereras separat och underhålls i den gemensamma HCM-lösningen i Dataverse.</span><span class="sxs-lookup"><span data-stu-id="397be-122">The native tables for Human Resources are generated separately and maintained in the HCM Common solution in Dataverse.</span></span> <span data-ttu-id="397be-123">Med inbyggda register lagras data i Dataverse och måste synkroniseras med programdatabasen för Personal.</span><span class="sxs-lookup"><span data-stu-id="397be-123">With native tables, the data is stored in Dataverse and requires synchronization with the Human Resources application database.</span></span>

> [!NOTE]
> <span data-ttu-id="397be-124">En lista över de inbyggda Dataverse-registren för Personal finns i [Dataverse-register](./hr-developer-entities.md).</span><span class="sxs-lookup"><span data-stu-id="397be-124">For a list of the native Dataverse tables for Human Resources, see [Dataverse tables](./hr-developer-entities.md).</span></span>

## <a name="setup"></a><span data-ttu-id="397be-125">Ställ in</span><span class="sxs-lookup"><span data-stu-id="397be-125">Setup</span></span>

<span data-ttu-id="397be-126">Följ dessa installationssteg för att aktivera virtuella register i din miljö.</span><span class="sxs-lookup"><span data-stu-id="397be-126">Follow these setup steps to enable virtual tables in your environment.</span></span>

### <a name="enable-virtual-tables-in-human-resources"></a><span data-ttu-id="397be-127">Aktivera virtuella register i Personal</span><span class="sxs-lookup"><span data-stu-id="397be-127">Enable virtual tables in Human Resources</span></span>

<span data-ttu-id="397be-128">Först måste du aktivera virtuella register i arbetsytan **Funktionshantering**.</span><span class="sxs-lookup"><span data-stu-id="397be-128">First, you must enable virtual tables in the **Feature management** workspace.</span></span>

1. <span data-ttu-id="397be-129">I Personal, välj **Systemadministration**.</span><span class="sxs-lookup"><span data-stu-id="397be-129">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="397be-130">Välj panelen **funktionshantering**.</span><span class="sxs-lookup"><span data-stu-id="397be-130">Select the **Feature management** tile.</span></span>

3. <span data-ttu-id="397be-131">Välj **Stöd för virtuella register för Personal i Dataverse** och sedan **Aktivera**.</span><span class="sxs-lookup"><span data-stu-id="397be-131">Select **Virtual table support for HR in Dataverse**, and then select **Enable**.</span></span>

<span data-ttu-id="397be-132">Mer information om att aktivera och inaktivera funktioner finns i [Hantera funktioner](hr-admin-manage-features.md).</span><span class="sxs-lookup"><span data-stu-id="397be-132">For more information about enabling and disabling features, see [Manage features](hr-admin-manage-features.md).</span></span>

### <a name="register-the-app-in-microsoft-azure"></a><span data-ttu-id="397be-133">Registrera appen i Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="397be-133">Register the app in Microsoft Azure</span></span>

<span data-ttu-id="397be-134">Du måste registrera din Human Resource-instans i Azure-portalen så att Microsofts identitetsplattform kan tillhandahålla autentisering och auktoriseringstjänster för appen och användarna.</span><span class="sxs-lookup"><span data-stu-id="397be-134">You must register your Human Resources instance in the Azure portal so the Microsoft identity platform can provide authentication and authorization services for the app and users.</span></span> <span data-ttu-id="397be-135">Mer information om registrering av program i Azure finns i [snabbstart: registrera ett app med Microsoft identitetsplattform](/azure/active-directory/develop/quickstart-register-app).</span><span class="sxs-lookup"><span data-stu-id="397be-135">For more information about registering apps in Azure, see [Quickstart: Register an application with the Microsoft identity platform](/azure/active-directory/develop/quickstart-register-app).</span></span>

1. <span data-ttu-id="397be-136">Öppna [Microsoft Azure-portal](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="397be-136">Open the [Microsoft Azure portal](https://portal.azure.com).</span></span>

2. <span data-ttu-id="397be-137">I listan Azure-tjänster, välj **App-registreringar**.</span><span class="sxs-lookup"><span data-stu-id="397be-137">In the Azure services list, select **App registrations**.</span></span>

3. <span data-ttu-id="397be-138">Välj **Ny registrering**.</span><span class="sxs-lookup"><span data-stu-id="397be-138">Select **New registration**.</span></span>

4. <span data-ttu-id="397be-139">I fältet **Namn** ange ett beskrivande namn för appen.</span><span class="sxs-lookup"><span data-stu-id="397be-139">In the **Name** field, enter a descriptive name for the app.</span></span> <span data-ttu-id="397be-140">Till exempel **Virtuella register för Dynamics 365 Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="397be-140">For example, **Dynamics 365 Human Resources Virtual Tables**.</span></span>

5. <span data-ttu-id="397be-141">I fältet **Omdirigera URI** ange namnrymd-URL för din instans av personal.</span><span class="sxs-lookup"><span data-stu-id="397be-141">In the **Redirect URI** field, enter the namespace URL of your instance of Human Resources.</span></span>

6. <span data-ttu-id="397be-142">Välj **Registrera**.</span><span class="sxs-lookup"><span data-stu-id="397be-142">Select **Register**.</span></span>

7. <span data-ttu-id="397be-143">När registreringen är klar visar Azure-portalen appregistreringen rutan **översikt** som innehåller dess **App-ID (klient)**.</span><span class="sxs-lookup"><span data-stu-id="397be-143">When registration completes, the Azure portal displays the app registration's **Overview** pane, which includes its **Application (client) ID**.</span></span> <span data-ttu-id="397be-144">Anteckna **App-ID (klient)** för tillfället.</span><span class="sxs-lookup"><span data-stu-id="397be-144">Take note of the **Application (client) ID** at this time.</span></span> <span data-ttu-id="397be-145">Du anger denna information när du [konfigurerar det virtuella registrets datakälla](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source).</span><span class="sxs-lookup"><span data-stu-id="397be-145">You'll enter this information when you [Configure the virtual table data source](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source).</span></span>

8. <span data-ttu-id="397be-146">I det vänstra navigeringsfönstret, välj **certifikat och hemligheter**.</span><span class="sxs-lookup"><span data-stu-id="397be-146">In the left navigation pane, select **Certificates and secrets**.</span></span>

9. <span data-ttu-id="397be-147">I avsnittet **klienthemlighet** på sidan **ny klienthemlighet**.</span><span class="sxs-lookup"><span data-stu-id="397be-147">In the **Client secrets** section of the page, select **New client secret**.</span></span>

10. <span data-ttu-id="397be-148">Ange en beskrivning, välj en varaktighet och välj sedan **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="397be-148">Provide a description, select a duration, and select **Add**.</span></span>

11. <span data-ttu-id="397be-149">Registrera hemlighetens värde från egenskapen **Värde** för registret.</span><span class="sxs-lookup"><span data-stu-id="397be-149">Record the secret's value from the **Value** property of the table.</span></span> <span data-ttu-id="397be-150">Du anger denna information när du [konfigurerar det virtuella registrets datakälla](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source).</span><span class="sxs-lookup"><span data-stu-id="397be-150">You'll enter this information when you [Configure the virtual table data source](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="397be-151">Se till att du noterar hemlighetens värde just nu.</span><span class="sxs-lookup"><span data-stu-id="397be-151">Be sure to take note of the secret's value at this time.</span></span> <span data-ttu-id="397be-152">Hemligheten visas aldrig igen när du har lämnat den här sidan.</span><span class="sxs-lookup"><span data-stu-id="397be-152">The secret is never displayed again after you leave this page.</span></span>

### <a name="install-the-dynamics-365-hr-virtual-table-app"></a><span data-ttu-id="397be-153">Installera appen Dynamics 365 HR Virtual Table</span><span class="sxs-lookup"><span data-stu-id="397be-153">Install the Dynamics 365 HR Virtual Table app</span></span>

<span data-ttu-id="397be-154">Installera appen Dynamics 365 HR Virtual Table i din Power Apps-miljö för att distribuera lösningspaketet för virtuellt register till Dataverse.</span><span class="sxs-lookup"><span data-stu-id="397be-154">Install the Dynamics 365 HR Virtual Table app in your Power Apps environment to deploy the virtual table solution package to Dataverse.</span></span>

1. <span data-ttu-id="397be-155">Öppna [Power Platform administrationscenter](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="397be-155">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="397be-156">I listan **miljöer**, välj Power Apps-miljö som är kopplad till personalinstansen.</span><span class="sxs-lookup"><span data-stu-id="397be-156">In the **Environments** list, select the Power Apps environment associated with your Human Resources instance.</span></span>

3. <span data-ttu-id="397be-157">I avsnittet **resurser** på sidan väljer du **Dynamics 365-appar**.</span><span class="sxs-lookup"><span data-stu-id="397be-157">In the **Resources** section of the page, select **Dynamics 365 apps**.</span></span>

4. <span data-ttu-id="397be-158">Välj åtgärden **Installera app**.</span><span class="sxs-lookup"><span data-stu-id="397be-158">Select the **Install app** action.</span></span>

5. <span data-ttu-id="397be-159">Välj **Dynamics 365 HR Virtual Table** och sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="397be-159">Select **Dynamics 365 HR Virtual Table**, and select **Next**.</span></span>

6. <span data-ttu-id="397be-160">Granska och markera det här alternativet om du vill godkänna tjänstvillkoren.</span><span class="sxs-lookup"><span data-stu-id="397be-160">Review and mark to agree to the terms of service.</span></span>

7. <span data-ttu-id="397be-161">Välj **Installera**.</span><span class="sxs-lookup"><span data-stu-id="397be-161">Select **Install**.</span></span>

<span data-ttu-id="397be-162">Installationen tar några minuter.</span><span class="sxs-lookup"><span data-stu-id="397be-162">The install takes a few minutes.</span></span> <span data-ttu-id="397be-163">När den är klar fortsätter du till nästa steg.</span><span class="sxs-lookup"><span data-stu-id="397be-163">When it completes, continue to the next steps.</span></span>

![Installera appen Dynamics 365 HR Virtual Table från administrationscentret för Power Platform](./media/hr-admin-integration-virtual-entities-power-platform-install.jpg)

### <a name="configure-the-virtual-table-data-source"></a><span data-ttu-id="397be-165">Konfigurera den virtuella datakällan för register</span><span class="sxs-lookup"><span data-stu-id="397be-165">Configure the virtual table data source</span></span> 

<span data-ttu-id="397be-166">Nästa steg är att konfigurera datakällan för det virtuella registret i Power Apps-miljön.</span><span class="sxs-lookup"><span data-stu-id="397be-166">The next step is to configure the virtual table data source in the Power Apps environment.</span></span> 

1. <span data-ttu-id="397be-167">Öppna [Power Platform administrationscenter](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="397be-167">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="397be-168">I listan **miljöer**, välj Power Apps-miljö som är kopplad till personalinstansen.</span><span class="sxs-lookup"><span data-stu-id="397be-168">In the **Environments** list, select the Power Apps environment associated with your Human Resources instance.</span></span>

3. <span data-ttu-id="397be-169">Välj **miljö-URL** i avsnittet **information** på sidan.</span><span class="sxs-lookup"><span data-stu-id="397be-169">Select the **Environment URL** in the **Details** section of the page.</span></span>

4. <span data-ttu-id="397be-170">I **Lösning hälsocenter**, välj ikonen **Avancerad sökning** längst upp till höger på appsidan.</span><span class="sxs-lookup"><span data-stu-id="397be-170">In the **Solution Health Hub**, select the **Advanced Find** icon in the top right of the application page.</span></span>

5. <span data-ttu-id="397be-171">På sidan **Avancerad sökning** i listrutan **Sök efter** välj **Konfiguration av virtuella enhetens datakälla i Finance and Operations**.</span><span class="sxs-lookup"><span data-stu-id="397be-171">On the **Advanced Find** page, in the **Look for** dropdown list, select **Finance and Operations Virtual Data Source Configurations**.</span></span>

6. <span data-ttu-id="397be-172">Välj **resultat**.</span><span class="sxs-lookup"><span data-stu-id="397be-172">Select **Results**.</span></span>

7. <span data-ttu-id="397be-173">Markera posten **Microsoft HR datakälla**.</span><span class="sxs-lookup"><span data-stu-id="397be-173">Select the **Microsoft HR Data Source** record.</span></span>

8. <span data-ttu-id="397be-174">Ange den information som krävs för konfigurationen av datakällan:</span><span class="sxs-lookup"><span data-stu-id="397be-174">Enter the required information for the data source configuration:</span></span>

   - <span data-ttu-id="397be-175">**Mål-URL**: en URL till din personal namnrymd.</span><span class="sxs-lookup"><span data-stu-id="397be-175">**Target URL**: The URL of your Human Resources namespace.</span></span> <span data-ttu-id="397be-176">Formatet för mål-URL:en är:</span><span class="sxs-lookup"><span data-stu-id="397be-176">The format of the target URL is:</span></span>
     
     <span data-ttu-id="397be-177">https://\<hostname\>.hr.talent.dynamics.com/namespaces/\<namespaceID\>/</span><span class="sxs-lookup"><span data-stu-id="397be-177">https://\<hostname\>.hr.talent.dynamics.com/namespaces/\<namespaceID\>/</span></span>

     <span data-ttu-id="397be-178">Exempel:</span><span class="sxs-lookup"><span data-stu-id="397be-178">For example:</span></span>
     
     `https://aos.rts-sf-5ea54e35c68-westus2.hr.talent.dynamics.com/namespaces/49d24c565-8f4d-4891-b174-bf83d948ed0c/`

     >[!NOTE]
     ><span data-ttu-id="397be-179">Se till att du tar med "**/**"-tecknet i slutet av URL:en för att undvika att få ett fel.</span><span class="sxs-lookup"><span data-stu-id="397be-179">Be sure to include the "**/**" character at the end of the URL to avoid receiving an error.</span></span>

   - <span data-ttu-id="397be-180">**Klientorganisations-ID**: Azure Active Directory (Azure AD) klientorganisations-ID.</span><span class="sxs-lookup"><span data-stu-id="397be-180">**Tenant ID**: The Azure Active Directory (Azure AD) tenant ID.</span></span>

   - <span data-ttu-id="397be-181">**AAD app-ID**: det app-ID (klient) som skapades för den app som är registrerat i Microsoft Azure-portalen.</span><span class="sxs-lookup"><span data-stu-id="397be-181">**AAD Application ID**: The application (client) ID created for the application registered in the Microsoft Azure portal.</span></span> <span data-ttu-id="397be-182">Du har fått den här informationen tidigare under steget [Registrera appen i Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span><span class="sxs-lookup"><span data-stu-id="397be-182">You received this information earlier during the step [Register the app in Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span></span>

   - <span data-ttu-id="397be-183">**Hemlighet för AAD app-ID**: klienthemligheten som skapades för den app som är registrerat i Microsoft Azure-portalen.</span><span class="sxs-lookup"><span data-stu-id="397be-183">**AAD Application Secret**: The client secret created for the application registered in the Microsoft Azure portal.</span></span> <span data-ttu-id="397be-184">Du har fått den här informationen tidigare under steget [Registrera appen i Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span><span class="sxs-lookup"><span data-stu-id="397be-184">You received this information earlier during the step [Register the app in Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span></span>

   ![Microsoft HR-datakälla](./media/hr-admin-integration-virtual-entities-hr-data-source.jpg)

9. <span data-ttu-id="397be-186">Välj **Spara och stäng**.</span><span class="sxs-lookup"><span data-stu-id="397be-186">Select **Save & Close**.</span></span>

### <a name="grant-app-permissions-in-human-resources"></a><span data-ttu-id="397be-187">Ge appbehörighet i Personal</span><span class="sxs-lookup"><span data-stu-id="397be-187">Grant app permissions in Human Resources</span></span>

<span data-ttu-id="397be-188">Bevilja behörigheter för de två Azure AD-apparna i Personal:</span><span class="sxs-lookup"><span data-stu-id="397be-188">Grant permissions for the two Azure AD applications in Human Resources:</span></span>

- <span data-ttu-id="397be-189">Appen som har skapats för din innehavare på Microsoft Azure-portalen</span><span class="sxs-lookup"><span data-stu-id="397be-189">The app created for your tenant in the Microsoft Azure portal</span></span>
- <span data-ttu-id="397be-190">Appen Dynamics 365 HR Virtual Table installeras i Power Apps-miljön</span><span class="sxs-lookup"><span data-stu-id="397be-190">The Dynamics 365 HR Virtual Table app installed in the Power Apps environment</span></span> 

1. <span data-ttu-id="397be-191">I Personal, öppna sidan **Azure Active Directory-appar**.</span><span class="sxs-lookup"><span data-stu-id="397be-191">In Human Resources, open the **Azure Active Directory applications** page.</span></span>

2. <span data-ttu-id="397be-192">Välj **Nytt** för att skapa en ny appost:</span><span class="sxs-lookup"><span data-stu-id="397be-192">Select **New** to create a new application record:</span></span>

    - <span data-ttu-id="397be-193">I fältet **klient-ID** anger du klient-ID för appen som du registrerade på Microsoft Azure-portalen.</span><span class="sxs-lookup"><span data-stu-id="397be-193">In the **Client ID** field, enter the client ID of the app you registered in the Microsoft Azure portal.</span></span>
    - <span data-ttu-id="397be-194">I fältet **Namn** anger du namnet för appen som du registrerade på Microsoft Azure-portalen.</span><span class="sxs-lookup"><span data-stu-id="397be-194">In the **Name** field, enter the name of the app you registered in the Microsoft Azure portal.</span></span>
    - <span data-ttu-id="397be-195">I fältet **Användar-ID** väljer du användar-ID för en användare med administratörsbehörighet i Personal och Power Apps-miljön.</span><span class="sxs-lookup"><span data-stu-id="397be-195">In the **User ID** field, select the user ID of a user with admin permissions in Human Resources and the Power Apps environment.</span></span>

3. <span data-ttu-id="397be-196">Välj **Nytt** för att skapa en andra appost:</span><span class="sxs-lookup"><span data-stu-id="397be-196">Select **New** to create a second application record:</span></span>

    - <span data-ttu-id="397be-197">**Klient-ID**: f9be0c49-aa22-4ec6-911a-c5da515226ff</span><span class="sxs-lookup"><span data-stu-id="397be-197">**Client Id**: f9be0c49-aa22-4ec6-911a-c5da515226ff</span></span>
    - <span data-ttu-id="397be-198">**Namn**: Dynamics 365 HR Virtual Table</span><span class="sxs-lookup"><span data-stu-id="397be-198">**Name**: Dynamics 365 HR Virtual Table</span></span>
    - <span data-ttu-id="397be-199">I fältet **Användar-ID** väljer du användar-ID för en användare med administratörsbehörighet i Personal och Power Apps-miljön.</span><span class="sxs-lookup"><span data-stu-id="397be-199">In the **User ID** field, select the user ID of a user with admin permissions in Human Resources and the Power Apps environment.</span></span>

## <a name="generate-virtual-tables"></a><span data-ttu-id="397be-200">Generera virtuella register</span><span class="sxs-lookup"><span data-stu-id="397be-200">Generate virtual tables</span></span>

<span data-ttu-id="397be-201">När installationsprogrammet är slutfört kan du välja vilka virtuella register du vill generera och aktivera i din Dataverse-instans.</span><span class="sxs-lookup"><span data-stu-id="397be-201">When setup completes, you can select the virtual tables you want to generate and enable in your Dataverse instance.</span></span>

1. <span data-ttu-id="397be-202">I Personal öppnar du sidan **Dataverse-integrering**.</span><span class="sxs-lookup"><span data-stu-id="397be-202">In Human Resources, open the **Dataverse integration** page.</span></span>

2. <span data-ttu-id="397be-203">Välj fliken **Virtuella register**.</span><span class="sxs-lookup"><span data-stu-id="397be-203">Select the **Virtual tables** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="397be-204">Växlingsknappen **Aktivera virtuella register** anges automatiskt som **Ja** när alla erforderliga inställningar har gjorts.</span><span class="sxs-lookup"><span data-stu-id="397be-204">The **Enable virtual tables** toggle will be set to **Yes** automatically when all required setup has been completed.</span></span> <span data-ttu-id="397be-205">Om växlingsknappen är inställd på **Nej** bör du granska stegen i de tidigare avsnitten i det här dokumentet så att alla nödvändiga inställningar är slutförda.</span><span class="sxs-lookup"><span data-stu-id="397be-205">If the toggle is set to **No**, review the steps in previous sections of this document to ensure all prerequisite setup is completed.</span></span>

3. <span data-ttu-id="397be-206">Välj det eller de register du vill generera i Dataverse.</span><span class="sxs-lookup"><span data-stu-id="397be-206">Select the table or tables you want to generate in Dataverse.</span></span>

4. <span data-ttu-id="397be-207">Välj **generera/uppdatera**.</span><span class="sxs-lookup"><span data-stu-id="397be-207">Select **Generate/refresh**.</span></span>

![Dataverse-integration](./media/hr-admin-integration-common-data-service-integration.jpg)

## <a name="check-table-generation-status"></a><span data-ttu-id="397be-209">Kontrollera registrets genereringsstatus</span><span class="sxs-lookup"><span data-stu-id="397be-209">Check table generation status</span></span>

<span data-ttu-id="397be-210">Virtuella register genereras i Dataverse genom en asynkron bakgrundsprocess.</span><span class="sxs-lookup"><span data-stu-id="397be-210">Virtual tables are generated in Dataverse through an asynchronous background process.</span></span> <span data-ttu-id="397be-211">Uppdateringar av processvisningen i åtgärdscentret.</span><span class="sxs-lookup"><span data-stu-id="397be-211">Updates on the process display in the action center.</span></span> <span data-ttu-id="397be-212">Information om processen, inklusive felloggar, visas på sidan **Processautomatiseringar**.</span><span class="sxs-lookup"><span data-stu-id="397be-212">Details on the process, including error logs, appear in the **Process automations** page.</span></span>

1. <span data-ttu-id="397be-213">I Personal, öppna listsidan **Processautomatiseringar**.</span><span class="sxs-lookup"><span data-stu-id="397be-213">In Human Resources, open the **Process automations** page.</span></span>

2. <span data-ttu-id="397be-214">Välj fliken **Bakgrundsprocesser**.</span><span class="sxs-lookup"><span data-stu-id="397be-214">Select the **Background processes** tab.</span></span>

3. <span data-ttu-id="397be-215">Välj **Bakgrundsprocess för virtuell registersökning av asynkron åtgärd**.</span><span class="sxs-lookup"><span data-stu-id="397be-215">Select **Virtual table poll async operation background process**.</span></span>

4. <span data-ttu-id="397be-216">Välj **Visa senaste resultat**.</span><span class="sxs-lookup"><span data-stu-id="397be-216">Select **View most recent results**.</span></span>

<span data-ttu-id="397be-217">I det utfällbara fönstret visas de senaste körningsresultaten för processen.</span><span class="sxs-lookup"><span data-stu-id="397be-217">The slideout pane displays the most recent execution results for the process.</span></span> <span data-ttu-id="397be-218">Du kan visa loggen för processen, inklusive eventuella fel som returnerats från Dataverse.</span><span class="sxs-lookup"><span data-stu-id="397be-218">You can view the log for the process, including any errors returned from Dataverse.</span></span>

## <a name="see-also"></a><span data-ttu-id="397be-219">Se även</span><span class="sxs-lookup"><span data-stu-id="397be-219">See also</span></span>

[<span data-ttu-id="397be-220">Vad är Dataverse?</span><span class="sxs-lookup"><span data-stu-id="397be-220">What is Dataverse?</span></span>](/powerapps/maker/common-data-service/data-platform-intro)<br>
[<span data-ttu-id="397be-221">Register i Dataverse</span><span class="sxs-lookup"><span data-stu-id="397be-221">Tables in Dataverse</span></span>](/powerapps/maker/common-data-service/entity-overview)<br>
[<span data-ttu-id="397be-222">Översikt över registerrelationer</span><span class="sxs-lookup"><span data-stu-id="397be-222">Table relationships overview</span></span>](/powerapps/maker/common-data-service/relationships-overview)<br>
[<span data-ttu-id="397be-223">Skapa och redigera virtuella register som innehåller data från en extern datakälla</span><span class="sxs-lookup"><span data-stu-id="397be-223">Create and edit virtual tables that contain data from an external data source</span></span>](/powerapps/maker/common-data-service/create-edit-virtual-entities)<br>
[<span data-ttu-id="397be-224">Vad är Power Apps-portaler?</span><span class="sxs-lookup"><span data-stu-id="397be-224">What is Power Apps portals?</span></span>](/powerapps/maker/portals/overview)<br>
[<span data-ttu-id="397be-225">Översikt över att skapa appar i Power Apps</span><span class="sxs-lookup"><span data-stu-id="397be-225">Overview of creating apps in Power Apps</span></span>](/powerapps/maker/)

[!INCLUDE[footer-include](../includes/footer-banner.md)]