---
title: Konfigurera virtuella Common Data Service-enheter
description: I det här avsnittet beskrivs hur du konfigurerar virtuella entiteter för Dynamics 365 Human Resources. Generera och uppdatera befintliga virtuella entiteter samt analysera genererade och tillgängliga entiteter.
author: andreabichsel
manager: tfehr
ms.date: 10/05/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
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
ms.openlocfilehash: 0d6f79ea569a7a9b0d25e73e8666bf9ba19095d0
ms.sourcegitcommit: a8665c47696028d371cdc4671db1fd8fcf9e1088
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/21/2020
ms.locfileid: "4058164"
---
# <a name="configure-common-data-service-virtual-entities"></a><span data-ttu-id="5539f-104">Konfigurera virtuella Common Data Service-enheter</span><span class="sxs-lookup"><span data-stu-id="5539f-104">Configure Common Data Service virtual entities</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="5539f-105">Dynamics 365 Human Resources är en virtuell datakälla i Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="5539f-105">Dynamics 365 Human Resources is a virtual data source in Common Data Service.</span></span> <span data-ttu-id="5539f-106">Det ger fullständiga åtgärder för att skapa, läsa, uppdatera och ta bort (CRUD) från Common Data Service och Microsoft Power Platform.</span><span class="sxs-lookup"><span data-stu-id="5539f-106">It provides full create, read, update, and delete (CRUD) operations from Common Data Service and Microsoft Power Platform.</span></span> <span data-ttu-id="5539f-107">Data för virtuella entiteter lagras inte i Common Data Service, men i appdatabasen.</span><span class="sxs-lookup"><span data-stu-id="5539f-107">The data for virtual entities isn't stored in Common Data Service, but in the application database.</span></span> 

<span data-ttu-id="5539f-108">Om du vill aktivera CRUD åtgärder från personalenheter från Common Data Service måste du göra enheterna tillgängliga som virtuella entiteter i Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="5539f-108">To enable CRUD operations on Human Resources entities from Common Data Service, you must make the entities available as virtual entities in Common Data Service.</span></span> <span data-ttu-id="5539f-109">På så sätt kan du utföra CRUD operationer från Common Data Service och Microsoft Power Platform på data i personal.</span><span class="sxs-lookup"><span data-stu-id="5539f-109">This lets you perform CRUD operations from Common Data Service and Microsoft Power Platform on data that's in Human Resources.</span></span> <span data-ttu-id="5539f-110">Operationerna stöder även de affärslogik valideringar av personal som garanterar data integritet när data skrivs till enheterna.</span><span class="sxs-lookup"><span data-stu-id="5539f-110">The operations also support the full business logic validations of Human Resources to ensure data integrity when writing data to the entities.</span></span>

## <a name="available-virtual-entities-for-human-resources"></a><span data-ttu-id="5539f-111">Tillgängliga virtuella enheter för personal</span><span class="sxs-lookup"><span data-stu-id="5539f-111">Available virtual entities for Human Resources</span></span>

<span data-ttu-id="5539f-112">Alla OData-entiteter (Open Data Protocol) i personal är tillgängliga som virtuella entiteter i Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="5539f-112">All Open Data Protocol (OData) entities in Human Resources are available as virtual entities in Common Data Service.</span></span> <span data-ttu-id="5539f-113">De är också tillgängliga i Power Platform.</span><span class="sxs-lookup"><span data-stu-id="5539f-113">They're also available in Power Platform.</span></span> <span data-ttu-id="5539f-114">Du kan nu bygga appar och erfarenheter med data direkt från personal med fullständig CRUD-kapacitet, utan att kopiera eller synkronisera data till Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="5539f-114">You can now build apps and experiences with data directly from Human Resources with full CRUD capability, without copying or synchronizing data to Common Data Service.</span></span> <span data-ttu-id="5539f-115">Du kan använda Power Apps-portaler för att skapa externa webbplatser som möjliggör samarbetsscenarier för affärsprocesser i personal.</span><span class="sxs-lookup"><span data-stu-id="5539f-115">You can use Power Apps portals to build external-facing websites that enable collaboration scenarios for business processes in Human Resources.</span></span>

<span data-ttu-id="5539f-116">Du kan visa listan med virtuella entiteter som är aktiverade i miljön och börja arbeta med entiteterna i [Power Apps](https://make.powerapps.com) i lösningen **virtuella Dynamics 365 personalenheter**.</span><span class="sxs-lookup"><span data-stu-id="5539f-116">You can view the list of virtual entities enabled in the environment, and begin working with the entities in [Power Apps](https://make.powerapps.com), in the **Dynamics 365 HR Virtual Entities** solution.</span></span>

![Virtuella Dynamics 365 personalenheter i Power Apps](./media/hr-admin-integration-virtual-entities-power-apps.jpg)

## <a name="virtual-entities-versus-natural-entities"></a><span data-ttu-id="5539f-118">Virtuella enheter jämfört med fysiska enheter</span><span class="sxs-lookup"><span data-stu-id="5539f-118">Virtual entities versus natural entities</span></span>

<span data-ttu-id="5539f-119">Virtuella enheter för personal är inte samma sak som de fysiska Common Data Service-enheter som har skapats för personal.</span><span class="sxs-lookup"><span data-stu-id="5539f-119">Virtual entities for Human Resources aren't the same as the natural Common Data Service entities created for Human Resources.</span></span> <span data-ttu-id="5539f-120">De naturliga enheterna för personal genereras separat och underhålls i den HCM gemensamma lösningen i Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="5539f-120">The natural entities for Human Resources are generated separately and maintained in the HCM Common solution in Common Data Service.</span></span> <span data-ttu-id="5539f-121">Med fysiska enheter lagras data i Common Data Service och måste synkroniseras med appdatabasen för personal.</span><span class="sxs-lookup"><span data-stu-id="5539f-121">With natural entities, the data is stored in Common Data Service and requires synchronization with the Human Resources application database.</span></span>

> [!NOTE]
> <span data-ttu-id="5539f-122">En lista över de naturliga Common Data Service-enheterna för personal finns i [Common Data Service-entiteter](https://docs.microsoft.com/dynamics365/human-resources/hr-developer-entities).</span><span class="sxs-lookup"><span data-stu-id="5539f-122">For a list of the natural Common Data Service entities for Human Resources, see [Common Data Service entities](https://docs.microsoft.com/dynamics365/human-resources/hr-developer-entities).</span></span>

## <a name="setup"></a><span data-ttu-id="5539f-123">Ställ in</span><span class="sxs-lookup"><span data-stu-id="5539f-123">Setup</span></span>

<span data-ttu-id="5539f-124">Följ dessa installationssteg för att aktivera virtuella enheter i miljön.</span><span class="sxs-lookup"><span data-stu-id="5539f-124">Follow these setup steps to enable virtual entities in your environment.</span></span> 

### <a name="register-the-app-in-microsoft-azure"></a><span data-ttu-id="5539f-125">Registrera appen i Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="5539f-125">Register the app in Microsoft Azure</span></span>

<span data-ttu-id="5539f-126">Först måste du registrera programmet på Azure-portalen så att Microsofts identitetsplattform kan tillhandahålla autentisering och auktoriseringstjänster för appen och användarna.</span><span class="sxs-lookup"><span data-stu-id="5539f-126">First, you need to register the app in the Azure portal so the Microsoft identity platform can provide authentication and authorization services for the app and users.</span></span> <span data-ttu-id="5539f-127">Mer information om registrering av program i Azure finns i [snabbstart: registrera ett app med Microsoft identitetsplattform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span><span class="sxs-lookup"><span data-stu-id="5539f-127">For more information about registering apps in Azure, see [Quickstart: Register an application with the Microsoft identity platform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span></span>

1. <span data-ttu-id="5539f-128">Öppna [Microsoft Azure-portal](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="5539f-128">Open the [Microsoft Azure portal](https://portal.azure.com).</span></span>

2. <span data-ttu-id="5539f-129">I listan Azure-tjänster, välj **App-registreringar**.</span><span class="sxs-lookup"><span data-stu-id="5539f-129">In the Azure services list, select **App registrations**.</span></span>

3. <span data-ttu-id="5539f-130">Välj **Ny registrering**.</span><span class="sxs-lookup"><span data-stu-id="5539f-130">Select **New registration**.</span></span>

4. <span data-ttu-id="5539f-131">I fältet **Namn** ange ett beskrivande namn för appen.</span><span class="sxs-lookup"><span data-stu-id="5539f-131">In the **Name** field, enter a descriptive name for the app.</span></span> <span data-ttu-id="5539f-132">Till exempel **Dynamics 365 Human Resources virtuella enheter**.</span><span class="sxs-lookup"><span data-stu-id="5539f-132">For example, **Dynamics 365 Human Resources Virtual Entities**.</span></span>

5. <span data-ttu-id="5539f-133">I fältet **Omdirigera URI** ange namnrymd-URL för din instans av personal.</span><span class="sxs-lookup"><span data-stu-id="5539f-133">In the **Redirect URI** field, enter the namespace URL of your instance of Human Resources.</span></span>

6. <span data-ttu-id="5539f-134">Välj **Registrera**.</span><span class="sxs-lookup"><span data-stu-id="5539f-134">Select **Register**.</span></span>

7. <span data-ttu-id="5539f-135">När registreringen är klar visar Azure-portalen appregistreringen rutan **översikt** som innehåller dess **App-ID (klient)**.</span><span class="sxs-lookup"><span data-stu-id="5539f-135">When registration completes, the Azure portal displays the app registration's **Overview** pane, which includes its **Application (client) ID**.</span></span> <span data-ttu-id="5539f-136">Anteckna **App-ID (klient)** för tillfället.</span><span class="sxs-lookup"><span data-stu-id="5539f-136">Take note of the **Application (client) ID** at this time.</span></span> <span data-ttu-id="5539f-137">Du anger den här informationen när du [konfigurerar den virtuella enhetens datakälla](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).</span><span class="sxs-lookup"><span data-stu-id="5539f-137">You'll enter this information when you [Configure the virtual entity data source](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).</span></span>

8. <span data-ttu-id="5539f-138">I det vänstra navigeringsfönstret, välj **certifikat och hemligheter**.</span><span class="sxs-lookup"><span data-stu-id="5539f-138">In the left navigation pane, select **Certificates and secrets**.</span></span>

9. <span data-ttu-id="5539f-139">I avsnittet **klienthemlighet** på sidan **ny klienthemlighet**.</span><span class="sxs-lookup"><span data-stu-id="5539f-139">In the **Client secrets** section of the page, select **New client secret**.</span></span>

10. <span data-ttu-id="5539f-140">Ange en beskrivning, välj en varaktighet och välj sedan **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="5539f-140">Provide a description, select a duration, and select **Add**.</span></span>

11. <span data-ttu-id="5539f-141">Registrera hemlighetens värde.</span><span class="sxs-lookup"><span data-stu-id="5539f-141">Record the secret's value.</span></span> <span data-ttu-id="5539f-142">Du anger den här informationen när du [konfigurerar den virtuella enhetens datakälla](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).</span><span class="sxs-lookup"><span data-stu-id="5539f-142">You'll enter this information when you [Configure the virtual entity data source](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="5539f-143">Se till att du noterar hemlighetens värde just nu.</span><span class="sxs-lookup"><span data-stu-id="5539f-143">Be sure to take note of the secret's value at this time.</span></span> <span data-ttu-id="5539f-144">Hemligheten visas aldrig igen när du har lämnat den här sidan.</span><span class="sxs-lookup"><span data-stu-id="5539f-144">The secret is never displayed again after you leave this page.</span></span>

### <a name="install-the-dynamics-365-hr-virtual-entity-app"></a><span data-ttu-id="5539f-145">Installera appen Dynamics 365 HR Virtual Entity</span><span class="sxs-lookup"><span data-stu-id="5539f-145">Install the Dynamics 365 HR Virtual Entity app</span></span>

<span data-ttu-id="5539f-146">Installera appen Dynamics 365 HR Virtual Entity i din Power Apps-miljö för att distribuera lösningspaketet för virtuell enhet till Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="5539f-146">Install the Dynamics 365 HR Virtual Entity app in your Power Apps environment to deploy the virtual entity solution package to Common Data Service.</span></span>

1. <span data-ttu-id="5539f-147">Öppna [Power Platform administrationscenter](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="5539f-147">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="5539f-148">I listan **miljöer** , välj Power Apps-miljö som är kopplad till personalinstansen.</span><span class="sxs-lookup"><span data-stu-id="5539f-148">In the **Environments** list, select the Power Apps environment associated with your Human Resources instance.</span></span>

3. <span data-ttu-id="5539f-149">I avsnittet **resurser** på sidan väljer du **Dynamics 365-appar**.</span><span class="sxs-lookup"><span data-stu-id="5539f-149">In the **Resources** section of the page, select **Dynamics 365 apps**.</span></span>

4. <span data-ttu-id="5539f-150">Välj åtgärden **Installera app**.</span><span class="sxs-lookup"><span data-stu-id="5539f-150">Select the **Install app** action.</span></span>

5. <span data-ttu-id="5539f-151">Välj **Dynamics 365 HR Virtual Entity** och välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="5539f-151">Select **Dynamics 365 HR Virtual Entity** , and select **Next**.</span></span>

6. <span data-ttu-id="5539f-152">Granska och markera det här alternativet om du vill godkänna tjänstvillkoren.</span><span class="sxs-lookup"><span data-stu-id="5539f-152">Review and mark to agree to the terms of service.</span></span>

7. <span data-ttu-id="5539f-153">Välj **Installera**.</span><span class="sxs-lookup"><span data-stu-id="5539f-153">Select **Install**.</span></span>

<span data-ttu-id="5539f-154">Installationen tar några minuter.</span><span class="sxs-lookup"><span data-stu-id="5539f-154">The install takes a few minutes.</span></span> <span data-ttu-id="5539f-155">När den är klar fortsätter du till nästa steg.</span><span class="sxs-lookup"><span data-stu-id="5539f-155">When it completes, continue to the next steps.</span></span>

![Installera appen Dynamics 365 HR Virtual Entity från Power Platform administrationscentret](./media/hr-admin-integration-virtual-entities-power-platform-install.jpg)

### <a name="configure-the-virtual-entity-data-source"></a><span data-ttu-id="5539f-157">Konfigurera den virtuella datakällan för entiteten</span><span class="sxs-lookup"><span data-stu-id="5539f-157">Configure the virtual entity data source</span></span> 

<span data-ttu-id="5539f-158">Nästa steg är att konfigurera datakällan för den virtuella enheten i Power Apps-miljön.</span><span class="sxs-lookup"><span data-stu-id="5539f-158">The next step is to configure the virtual entity data source in the Power Apps environment.</span></span> 

1. <span data-ttu-id="5539f-159">Öppna [Power Platform administrationscenter](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="5539f-159">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="5539f-160">I listan **miljöer** , välj Power Apps-miljö som är kopplad till personalinstansen.</span><span class="sxs-lookup"><span data-stu-id="5539f-160">In the **Environments** list, select the Power Apps environment associated with your Human Resources instance.</span></span>

3. <span data-ttu-id="5539f-161">Välj **miljö-URL** i avsnittet **information** på sidan.</span><span class="sxs-lookup"><span data-stu-id="5539f-161">Select the **Environment URL** in the **Details** section of the page.</span></span>

4. <span data-ttu-id="5539f-162">I **Lösning hälsocenter** , välj ikonen **Avancerad sökning** längst upp till höger på appsidan.</span><span class="sxs-lookup"><span data-stu-id="5539f-162">In the **Solution Health Hub** , select the **Advanced Find** icon in the top right of the application page.</span></span>

5. <span data-ttu-id="5539f-163">På sidan **Avancerad sökning** i listrutan **Sök efter** välj **Konfiguration av virtuella enhetens datakälla i Finance and Operations**.</span><span class="sxs-lookup"><span data-stu-id="5539f-163">On the **Advanced Find** page, in the **Look for** dropdown list, select **Finance and Operations Virtual Data Source Configurations**.</span></span>

6. <span data-ttu-id="5539f-164">Välj **resultat**.</span><span class="sxs-lookup"><span data-stu-id="5539f-164">Select **Results**.</span></span>

7. <span data-ttu-id="5539f-165">Markera posten **Microsoft HR datakälla**.</span><span class="sxs-lookup"><span data-stu-id="5539f-165">Select the **Microsoft HR Data Source** record.</span></span>

8. <span data-ttu-id="5539f-166">Ange den information som krävs för konfigurationen av datakällan.</span><span class="sxs-lookup"><span data-stu-id="5539f-166">Enter the required information for the data source configuration.</span></span>

   - <span data-ttu-id="5539f-167">**Mål-URL** : en URL till din personal namnrymd.</span><span class="sxs-lookup"><span data-stu-id="5539f-167">**Target URL** : The URL of your Human Resources namespace.</span></span>
   - <span data-ttu-id="5539f-168">**Klientorganisations-ID** : Azure Active Directory (Azure AD) klientorganisations-ID.</span><span class="sxs-lookup"><span data-stu-id="5539f-168">**Tenant ID** : The Azure Active Directory (Azure AD) tenant ID.</span></span>
   - <span data-ttu-id="5539f-169">**AAD app-ID** : det app-ID (klient) som skapades för den app som är registrerat i Microsoft Azure-portalen.</span><span class="sxs-lookup"><span data-stu-id="5539f-169">**AAD Application ID** : The application (client) ID created for the application registered in the Microsoft Azure portal.</span></span> <span data-ttu-id="5539f-170">Du har fått den här informationen tidigare under steget [Registrera appen i Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span><span class="sxs-lookup"><span data-stu-id="5539f-170">You received this information earlier during the step [Register the app in Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span></span>
   - <span data-ttu-id="5539f-171">**Hemlighet för AAD app-ID** : klienthemligheten som skapades för den app som är registrerat i Microsoft Azure-portalen.</span><span class="sxs-lookup"><span data-stu-id="5539f-171">**AAD Application Secret** : The client secret created for the application registered in the Microsoft Azure portal.</span></span> <span data-ttu-id="5539f-172">Du har fått den här informationen tidigare under steget [Registrera appen i Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span><span class="sxs-lookup"><span data-stu-id="5539f-172">You received this information earlier during the step [Register the app in Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span></span>

9. <span data-ttu-id="5539f-173">Välj **Spara och stäng**.</span><span class="sxs-lookup"><span data-stu-id="5539f-173">Select **Save & Close**.</span></span>

   ![Microsoft HR-datakälla](./media/hr-admin-integration-virtual-entities-hr-data-source.jpg)

### <a name="grant-app-permissions-in-human-resources"></a><span data-ttu-id="5539f-175">Ge appbehörighet i Human Resources</span><span class="sxs-lookup"><span data-stu-id="5539f-175">Grant app permissions in Human Resources</span></span>

<span data-ttu-id="5539f-176">Bevilja behörigheter för de två Azure AD-apparna i Human Resources:</span><span class="sxs-lookup"><span data-stu-id="5539f-176">Grant permissions for the two Azure AD applications in Human Resources:</span></span>

- <span data-ttu-id="5539f-177">Appen som har skapats för din innehavare på Microsoft Azure-portalen</span><span class="sxs-lookup"><span data-stu-id="5539f-177">The app created for your tenant in the Microsoft Azure portal</span></span>
- <span data-ttu-id="5539f-178">Appen Dynamics 365 HR Virtual Entity installeras Power Apps-miljön</span><span class="sxs-lookup"><span data-stu-id="5539f-178">The Dynamics 365 HR Virtual Entity app installed in the Power Apps environment</span></span> 

1. <span data-ttu-id="5539f-179">I Human Resources, öppna sidan **Azure Active Directory-appar**.</span><span class="sxs-lookup"><span data-stu-id="5539f-179">In Human Resources, open the **Azure Active Directory applications** page.</span></span>

2. <span data-ttu-id="5539f-180">Välj **Nytt** för att skapa en ny appost:</span><span class="sxs-lookup"><span data-stu-id="5539f-180">Select **New** to create a new application record:</span></span>

    - <span data-ttu-id="5539f-181">I fältet **klient-ID** anger du klient-ID för appen som du registrerade på Microsoft Azure-portalen.</span><span class="sxs-lookup"><span data-stu-id="5539f-181">In the **Client ID** field, enter the client ID of the app you registered in the Microsoft Azure portal.</span></span>
    - <span data-ttu-id="5539f-182">I fältet **Namn** anger du namnet för appen som du registrerade på Microsoft Azure-portalen.</span><span class="sxs-lookup"><span data-stu-id="5539f-182">In the **Name** field, enter the name of the app you registered in the Microsoft Azure portal.</span></span>
    - <span data-ttu-id="5539f-183">I fältet **Användar-ID** väljer du användar-ID för en användare med administratörsbehörighet i Human Resources och Power Apps-miljön.</span><span class="sxs-lookup"><span data-stu-id="5539f-183">In the **User ID** field, select the user ID of a user with admin permissions in Human Resources and the Power Apps environment.</span></span>

3. <span data-ttu-id="5539f-184">Välj **Nytt** för att skapa en andra appost:</span><span class="sxs-lookup"><span data-stu-id="5539f-184">Select **New** to create a second application record:</span></span>

    - <span data-ttu-id="5539f-185">**Klient-ID** : f9be0c49-aa22-4ec6-911a-c5da515226ff</span><span class="sxs-lookup"><span data-stu-id="5539f-185">**Client Id** : f9be0c49-aa22-4ec6-911a-c5da515226ff</span></span>
    - <span data-ttu-id="5539f-186">**Namn** : Dynamics 365 HR Virtual Entity</span><span class="sxs-lookup"><span data-stu-id="5539f-186">**Name** : Dynamics 365 HR Virtual Entity</span></span>
    - <span data-ttu-id="5539f-187">I fältet **Användar-ID** väljer du användar-ID för en användare med administratörsbehörighet i Human Resources och Power Apps-miljön.</span><span class="sxs-lookup"><span data-stu-id="5539f-187">In the **User ID** field, select the user ID of a user with admin permissions in Human Resources and the Power Apps environment.</span></span>

## <a name="generate-virtual-entities"></a><span data-ttu-id="5539f-188">Generera virtuella enheter</span><span class="sxs-lookup"><span data-stu-id="5539f-188">Generate virtual entities</span></span>

<span data-ttu-id="5539f-189">När installationsprogrammet är klart kan du välja vilka virtuella entiteter du vill generera och aktivera i din Common Data Service-instans.</span><span class="sxs-lookup"><span data-stu-id="5539f-189">When setup completes, you can select the virtual entities you want to generate and enable in your Common Data Service instance.</span></span>

1. <span data-ttu-id="5539f-190">I Human Resources, öppna sidan **Common Data Service (CDS) integration**.</span><span class="sxs-lookup"><span data-stu-id="5539f-190">In Human Resources, open the **Common Data Service (CDS) integration** page.</span></span>

2. <span data-ttu-id="5539f-191">Välj fliken **virtuella entiteter**.</span><span class="sxs-lookup"><span data-stu-id="5539f-191">Select the **Virtual entities** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="5539f-192">Växlingsknappen **Aktivera virtuell entitet** kommer att ställas in på **Ja** automatiskt när alla nödvändiga inställningar har slutförts.</span><span class="sxs-lookup"><span data-stu-id="5539f-192">The **Enable the virtual entity** toggle will be set to **Yes** automatically when all required setup has been completed.</span></span> <span data-ttu-id="5539f-193">Om växlingsknappen är inställd på **Nej** bör du granska stegen i de tidigare avsnitten i det här dokumentet så att alla nödvändiga inställningar är slutförda.</span><span class="sxs-lookup"><span data-stu-id="5539f-193">If the toggle is set to **No** , review the steps in previous sections of this document to ensure all prerequisite setup is completed.</span></span>

3. <span data-ttu-id="5539f-194">Välj den eller de entiteter du vill generera i Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="5539f-194">Select the entity or entities you want to generate in Common Data Service.</span></span>

4. <span data-ttu-id="5539f-195">Välj **generera/uppdatera**.</span><span class="sxs-lookup"><span data-stu-id="5539f-195">Select **Generate/refresh**.</span></span>

![Common Data Service-integration](./media/hr-admin-integration-common-data-service-integration.jpg)

## <a name="check-entity-generation-status"></a><span data-ttu-id="5539f-197">Kontrollera entitetens statusgenerering</span><span class="sxs-lookup"><span data-stu-id="5539f-197">Check entity generation status</span></span>

<span data-ttu-id="5539f-198">Virtuella entiteter genereras i Common Data Service genom en asynkron bakgrundsprocess.</span><span class="sxs-lookup"><span data-stu-id="5539f-198">Virtual entities are generated in Common Data Service through an asynchronous background process.</span></span> <span data-ttu-id="5539f-199">Uppdateringar av processvisningen i åtgärdscentret.</span><span class="sxs-lookup"><span data-stu-id="5539f-199">Updates on the process display in the action center.</span></span> <span data-ttu-id="5539f-200">Information om processen, inklusive felloggar, visas på sidan **Processautomatiseringar**.</span><span class="sxs-lookup"><span data-stu-id="5539f-200">Details on the process, including error logs, appear in the **Process automations** page.</span></span>

1. <span data-ttu-id="5539f-201">I Personal, öppna listsidan **Processautomatiseringar**.</span><span class="sxs-lookup"><span data-stu-id="5539f-201">In Human Resources, open the **Process automations** page.</span></span>

2. <span data-ttu-id="5539f-202">Välj fliken **Bakgrundsprocesser**.</span><span class="sxs-lookup"><span data-stu-id="5539f-202">Select the **Background processes** tab.</span></span>

3. <span data-ttu-id="5539f-203">Välj **Process för bakgrundsförfarande för asynkron operation av virtuell enhet**.</span><span class="sxs-lookup"><span data-stu-id="5539f-203">Select **Virtual entity poll async operation background process**.</span></span>

4. <span data-ttu-id="5539f-204">Välj **Visa senaste resultat**.</span><span class="sxs-lookup"><span data-stu-id="5539f-204">Select **View most recent results**.</span></span>

<span data-ttu-id="5539f-205">I det utfällbara fönstret visas de senaste körningsresultaten för processen.</span><span class="sxs-lookup"><span data-stu-id="5539f-205">The slideout pane displays the most recent execution results for the process.</span></span> <span data-ttu-id="5539f-206">Du kan visa loggen för processen, inklusive eventuella fel som returnerats från Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="5539f-206">You can view the log for the process, including any errors returned from Common Data Service.</span></span>

## <a name="see-also"></a><span data-ttu-id="5539f-207">Se även</span><span class="sxs-lookup"><span data-stu-id="5539f-207">See also</span></span>

[<span data-ttu-id="5539f-208">Vad är Common Data Service?</span><span class="sxs-lookup"><span data-stu-id="5539f-208">What is Common Data Service?</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)<br>
[<span data-ttu-id="5539f-209">Enhetsöversikt</span><span class="sxs-lookup"><span data-stu-id="5539f-209">Entity overview</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/entity-overview)<br>
[<span data-ttu-id="5539f-210">Översikt över entitetsrelationer</span><span class="sxs-lookup"><span data-stu-id="5539f-210">Entity relationships overview</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/relationships-overview)<br>
[<span data-ttu-id="5539f-211">Skapa och redigera virtuella entiteter som innehåller data från en extern datakälla</span><span class="sxs-lookup"><span data-stu-id="5539f-211">Create and edit virtual entities that contain data from an external data source</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/create-edit-virtual-entities)<br>
[<span data-ttu-id="5539f-212">Vad är Power Apps-portaler?</span><span class="sxs-lookup"><span data-stu-id="5539f-212">What is Power Apps portals?</span></span>](https://docs.microsoft.com/powerapps/maker/portals/overview)<br>
[<span data-ttu-id="5539f-213">Översikt över att skapa appar i Power Apps</span><span class="sxs-lookup"><span data-stu-id="5539f-213">Overview of creating apps in Power Apps</span></span>](https://docs.microsoft.com/powerapps/maker/)
