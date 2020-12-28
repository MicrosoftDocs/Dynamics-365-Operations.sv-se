---
title: Konfigurera virtuella Common Data Service-enheter
description: I det här avsnittet beskrivs hur du konfigurerar virtuella entiteter för Dynamics 365 Human Resources. Generera och uppdatera befintliga virtuella entiteter samt analysera genererade och tillgängliga entiteter.
author: andreabichsel
manager: tfehr
ms.date: 11/02/2020
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
ms.openlocfilehash: 2b590faeab600d04c9d5303693ec1e9ac682250d
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/25/2020
ms.locfileid: "4645611"
---
# <a name="configure-common-data-service-virtual-entities"></a><span data-ttu-id="0fb36-104">Konfigurera virtuella Common Data Service-enheter</span><span class="sxs-lookup"><span data-stu-id="0fb36-104">Configure Common Data Service virtual entities</span></span>

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="0fb36-105">Dynamics 365 Human Resources är en virtuell datakälla i Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="0fb36-105">Dynamics 365 Human Resources is a virtual data source in Common Data Service.</span></span> <span data-ttu-id="0fb36-106">Det ger fullständiga åtgärder för att skapa, läsa, uppdatera och ta bort (CRUD) från Common Data Service och Microsoft Power Platform.</span><span class="sxs-lookup"><span data-stu-id="0fb36-106">It provides full create, read, update, and delete (CRUD) operations from Common Data Service and Microsoft Power Platform.</span></span> <span data-ttu-id="0fb36-107">Data för virtuella entiteter lagras inte i Common Data Service, men i appdatabasen.</span><span class="sxs-lookup"><span data-stu-id="0fb36-107">The data for virtual entities isn't stored in Common Data Service, but in the application database.</span></span> 

<span data-ttu-id="0fb36-108">Om du vill aktivera CRUD åtgärder från personalenheter från Common Data Service måste du göra enheterna tillgängliga som virtuella entiteter i Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="0fb36-108">To enable CRUD operations on Human Resources entities from Common Data Service, you must make the entities available as virtual entities in Common Data Service.</span></span> <span data-ttu-id="0fb36-109">På så sätt kan du utföra CRUD operationer från Common Data Service och Microsoft Power Platform på data i personal.</span><span class="sxs-lookup"><span data-stu-id="0fb36-109">This lets you perform CRUD operations from Common Data Service and Microsoft Power Platform on data that's in Human Resources.</span></span> <span data-ttu-id="0fb36-110">Operationerna stöder även de affärslogik valideringar av personal som garanterar data integritet när data skrivs till enheterna.</span><span class="sxs-lookup"><span data-stu-id="0fb36-110">The operations also support the full business logic validations of Human Resources to ensure data integrity when writing data to the entities.</span></span>

## <a name="available-virtual-entities-for-human-resources"></a><span data-ttu-id="0fb36-111">Tillgängliga virtuella enheter för personal</span><span class="sxs-lookup"><span data-stu-id="0fb36-111">Available virtual entities for Human Resources</span></span>

<span data-ttu-id="0fb36-112">Alla OData-entiteter (Open Data Protocol) i personal är tillgängliga som virtuella entiteter i Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="0fb36-112">All Open Data Protocol (OData) entities in Human Resources are available as virtual entities in Common Data Service.</span></span> <span data-ttu-id="0fb36-113">De är också tillgängliga i Power Platform.</span><span class="sxs-lookup"><span data-stu-id="0fb36-113">They're also available in Power Platform.</span></span> <span data-ttu-id="0fb36-114">Du kan nu bygga appar och erfarenheter med data direkt från personal med fullständig CRUD-kapacitet, utan att kopiera eller synkronisera data till Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="0fb36-114">You can now build apps and experiences with data directly from Human Resources with full CRUD capability, without copying or synchronizing data to Common Data Service.</span></span> <span data-ttu-id="0fb36-115">Du kan använda Power Apps-portaler för att skapa externa webbplatser som möjliggör samarbetsscenarier för affärsprocesser i personal.</span><span class="sxs-lookup"><span data-stu-id="0fb36-115">You can use Power Apps portals to build external-facing websites that enable collaboration scenarios for business processes in Human Resources.</span></span>

<span data-ttu-id="0fb36-116">Du kan visa listan med virtuella entiteter som är aktiverade i miljön och börja arbeta med entiteterna i [Power Apps](https://make.powerapps.com) i lösningen **virtuella Dynamics 365 personalenheter**.</span><span class="sxs-lookup"><span data-stu-id="0fb36-116">You can view the list of virtual entities enabled in the environment, and begin working with the entities in [Power Apps](https://make.powerapps.com), in the **Dynamics 365 HR Virtual Entities** solution.</span></span>

![Virtuella Dynamics 365 personalenheter i Power Apps](./media/hr-admin-integration-virtual-entities-power-apps.jpg)

## <a name="virtual-entities-versus-natural-entities"></a><span data-ttu-id="0fb36-118">Virtuella enheter jämfört med fysiska enheter</span><span class="sxs-lookup"><span data-stu-id="0fb36-118">Virtual entities versus natural entities</span></span>

<span data-ttu-id="0fb36-119">Virtuella enheter för personal är inte samma sak som de fysiska Common Data Service-enheter som har skapats för personal.</span><span class="sxs-lookup"><span data-stu-id="0fb36-119">Virtual entities for Human Resources aren't the same as the natural Common Data Service entities created for Human Resources.</span></span> <span data-ttu-id="0fb36-120">De naturliga enheterna för personal genereras separat och underhålls i den HCM gemensamma lösningen i Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="0fb36-120">The natural entities for Human Resources are generated separately and maintained in the HCM Common solution in Common Data Service.</span></span> <span data-ttu-id="0fb36-121">Med fysiska enheter lagras data i Common Data Service och måste synkroniseras med appdatabasen för personal.</span><span class="sxs-lookup"><span data-stu-id="0fb36-121">With natural entities, the data is stored in Common Data Service and requires synchronization with the Human Resources application database.</span></span>

> [!NOTE]
> <span data-ttu-id="0fb36-122">En lista över de naturliga Common Data Service-enheterna för personal finns i [Common Data Service-entiteter](https://docs.microsoft.com/dynamics365/human-resources/hr-developer-entities).</span><span class="sxs-lookup"><span data-stu-id="0fb36-122">For a list of the natural Common Data Service entities for Human Resources, see [Common Data Service entities](https://docs.microsoft.com/dynamics365/human-resources/hr-developer-entities).</span></span>

## <a name="setup"></a><span data-ttu-id="0fb36-123">Ställ in</span><span class="sxs-lookup"><span data-stu-id="0fb36-123">Setup</span></span>

<span data-ttu-id="0fb36-124">Följ dessa installationssteg för att aktivera virtuella enheter i miljön.</span><span class="sxs-lookup"><span data-stu-id="0fb36-124">Follow these setup steps to enable virtual entities in your environment.</span></span>

### <a name="enable-virtual-entities-in-human-resources"></a><span data-ttu-id="0fb36-125">Aktivera virtuella entiteter i Human Resources</span><span class="sxs-lookup"><span data-stu-id="0fb36-125">Enable virtual entities in Human Resources</span></span>

<span data-ttu-id="0fb36-126">Först måste du aktivera virtuella entiteter i arbetsytan **Funktionshantering**.</span><span class="sxs-lookup"><span data-stu-id="0fb36-126">First, you must enable virtual entities in the **Feature management** workspace.</span></span>

1. <span data-ttu-id="0fb36-127">I Personal, välj **Systemadministration**.</span><span class="sxs-lookup"><span data-stu-id="0fb36-127">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="0fb36-128">Välj panelen **funktionshantering**.</span><span class="sxs-lookup"><span data-stu-id="0fb36-128">Select the **Feature management** tile.</span></span>

3. <span data-ttu-id="0fb36-129">Välj **Stöd för virtuell entitet i HR/CDS** och sedan **Aktivera**.</span><span class="sxs-lookup"><span data-stu-id="0fb36-129">Select **Virtual Entity support in HR/CDS**, and then select **Enable**.</span></span>

<span data-ttu-id="0fb36-130">Mer information om att aktivera och inaktivera funktioner finns i [Hantera funktioner](hr-admin-manage-features.md).</span><span class="sxs-lookup"><span data-stu-id="0fb36-130">For more information about enabling and disabling features, see [Manage features](hr-admin-manage-features.md).</span></span>

### <a name="register-the-app-in-microsoft-azure"></a><span data-ttu-id="0fb36-131">Registrera appen i Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="0fb36-131">Register the app in Microsoft Azure</span></span>

<span data-ttu-id="0fb36-132">Du måste registrera din Human Resource-instans i Azure-portalen så att Microsofts identitetsplattform kan tillhandahålla autentisering och auktoriseringstjänster för appen och användarna.</span><span class="sxs-lookup"><span data-stu-id="0fb36-132">You must register your Human Resources instance in the Azure portal so the Microsoft identity platform can provide authentication and authorization services for the app and users.</span></span> <span data-ttu-id="0fb36-133">Mer information om registrering av program i Azure finns i [snabbstart: registrera ett app med Microsoft identitetsplattform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span><span class="sxs-lookup"><span data-stu-id="0fb36-133">For more information about registering apps in Azure, see [Quickstart: Register an application with the Microsoft identity platform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span></span>

1. <span data-ttu-id="0fb36-134">Öppna [Microsoft Azure-portal](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="0fb36-134">Open the [Microsoft Azure portal](https://portal.azure.com).</span></span>

2. <span data-ttu-id="0fb36-135">I listan Azure-tjänster, välj **App-registreringar**.</span><span class="sxs-lookup"><span data-stu-id="0fb36-135">In the Azure services list, select **App registrations**.</span></span>

3. <span data-ttu-id="0fb36-136">Välj **Ny registrering**.</span><span class="sxs-lookup"><span data-stu-id="0fb36-136">Select **New registration**.</span></span>

4. <span data-ttu-id="0fb36-137">I fältet **Namn** ange ett beskrivande namn för appen.</span><span class="sxs-lookup"><span data-stu-id="0fb36-137">In the **Name** field, enter a descriptive name for the app.</span></span> <span data-ttu-id="0fb36-138">Till exempel **Dynamics 365 Human Resources virtuella enheter**.</span><span class="sxs-lookup"><span data-stu-id="0fb36-138">For example, **Dynamics 365 Human Resources Virtual Entities**.</span></span>

5. <span data-ttu-id="0fb36-139">I fältet **Omdirigera URI** ange namnrymd-URL för din instans av personal.</span><span class="sxs-lookup"><span data-stu-id="0fb36-139">In the **Redirect URI** field, enter the namespace URL of your instance of Human Resources.</span></span>

6. <span data-ttu-id="0fb36-140">Välj **Registrera**.</span><span class="sxs-lookup"><span data-stu-id="0fb36-140">Select **Register**.</span></span>

7. <span data-ttu-id="0fb36-141">När registreringen är klar visar Azure-portalen appregistreringen rutan **översikt** som innehåller dess **App-ID (klient)**.</span><span class="sxs-lookup"><span data-stu-id="0fb36-141">When registration completes, the Azure portal displays the app registration's **Overview** pane, which includes its **Application (client) ID**.</span></span> <span data-ttu-id="0fb36-142">Anteckna **App-ID (klient)** för tillfället.</span><span class="sxs-lookup"><span data-stu-id="0fb36-142">Take note of the **Application (client) ID** at this time.</span></span> <span data-ttu-id="0fb36-143">Du anger den här informationen när du [konfigurerar den virtuella enhetens datakälla](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).</span><span class="sxs-lookup"><span data-stu-id="0fb36-143">You'll enter this information when you [Configure the virtual entity data source](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).</span></span>

8. <span data-ttu-id="0fb36-144">I det vänstra navigeringsfönstret, välj **certifikat och hemligheter**.</span><span class="sxs-lookup"><span data-stu-id="0fb36-144">In the left navigation pane, select **Certificates and secrets**.</span></span>

9. <span data-ttu-id="0fb36-145">I avsnittet **klienthemlighet** på sidan **ny klienthemlighet**.</span><span class="sxs-lookup"><span data-stu-id="0fb36-145">In the **Client secrets** section of the page, select **New client secret**.</span></span>

10. <span data-ttu-id="0fb36-146">Ange en beskrivning, välj en varaktighet och välj sedan **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="0fb36-146">Provide a description, select a duration, and select **Add**.</span></span>

11. <span data-ttu-id="0fb36-147">Registrera hemlighetens värde.</span><span class="sxs-lookup"><span data-stu-id="0fb36-147">Record the secret's value.</span></span> <span data-ttu-id="0fb36-148">Du anger den här informationen när du [konfigurerar den virtuella enhetens datakälla](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).</span><span class="sxs-lookup"><span data-stu-id="0fb36-148">You'll enter this information when you [Configure the virtual entity data source](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="0fb36-149">Se till att du noterar hemlighetens värde just nu.</span><span class="sxs-lookup"><span data-stu-id="0fb36-149">Be sure to take note of the secret's value at this time.</span></span> <span data-ttu-id="0fb36-150">Hemligheten visas aldrig igen när du har lämnat den här sidan.</span><span class="sxs-lookup"><span data-stu-id="0fb36-150">The secret is never displayed again after you leave this page.</span></span>

### <a name="install-the-dynamics-365-hr-virtual-entity-app"></a><span data-ttu-id="0fb36-151">Installera appen Dynamics 365 HR Virtual Entity</span><span class="sxs-lookup"><span data-stu-id="0fb36-151">Install the Dynamics 365 HR Virtual Entity app</span></span>

<span data-ttu-id="0fb36-152">Installera appen Dynamics 365 HR Virtual Entity i din Power Apps-miljö för att distribuera lösningspaketet för virtuell enhet till Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="0fb36-152">Install the Dynamics 365 HR Virtual Entity app in your Power Apps environment to deploy the virtual entity solution package to Common Data Service.</span></span>

1. <span data-ttu-id="0fb36-153">Öppna [Power Platform administrationscenter](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="0fb36-153">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="0fb36-154">I listan **miljöer**, välj Power Apps-miljö som är kopplad till personalinstansen.</span><span class="sxs-lookup"><span data-stu-id="0fb36-154">In the **Environments** list, select the Power Apps environment associated with your Human Resources instance.</span></span>

3. <span data-ttu-id="0fb36-155">I avsnittet **resurser** på sidan väljer du **Dynamics 365-appar**.</span><span class="sxs-lookup"><span data-stu-id="0fb36-155">In the **Resources** section of the page, select **Dynamics 365 apps**.</span></span>

4. <span data-ttu-id="0fb36-156">Välj åtgärden **Installera app**.</span><span class="sxs-lookup"><span data-stu-id="0fb36-156">Select the **Install app** action.</span></span>

5. <span data-ttu-id="0fb36-157">Välj **Dynamics 365 HR Virtual Entity** och välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="0fb36-157">Select **Dynamics 365 HR Virtual Entity**, and select **Next**.</span></span>

6. <span data-ttu-id="0fb36-158">Granska och markera det här alternativet om du vill godkänna tjänstvillkoren.</span><span class="sxs-lookup"><span data-stu-id="0fb36-158">Review and mark to agree to the terms of service.</span></span>

7. <span data-ttu-id="0fb36-159">Välj **Installera**.</span><span class="sxs-lookup"><span data-stu-id="0fb36-159">Select **Install**.</span></span>

<span data-ttu-id="0fb36-160">Installationen tar några minuter.</span><span class="sxs-lookup"><span data-stu-id="0fb36-160">The install takes a few minutes.</span></span> <span data-ttu-id="0fb36-161">När den är klar fortsätter du till nästa steg.</span><span class="sxs-lookup"><span data-stu-id="0fb36-161">When it completes, continue to the next steps.</span></span>

![Installera appen Dynamics 365 HR Virtual Entity från Power Platform administrationscentret](./media/hr-admin-integration-virtual-entities-power-platform-install.jpg)

### <a name="configure-the-virtual-entity-data-source"></a><span data-ttu-id="0fb36-163">Konfigurera den virtuella datakällan för entiteten</span><span class="sxs-lookup"><span data-stu-id="0fb36-163">Configure the virtual entity data source</span></span> 

<span data-ttu-id="0fb36-164">Nästa steg är att konfigurera datakällan för den virtuella enheten i Power Apps-miljön.</span><span class="sxs-lookup"><span data-stu-id="0fb36-164">The next step is to configure the virtual entity data source in the Power Apps environment.</span></span> 

1. <span data-ttu-id="0fb36-165">Öppna [Power Platform administrationscenter](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="0fb36-165">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="0fb36-166">I listan **miljöer**, välj Power Apps-miljö som är kopplad till personalinstansen.</span><span class="sxs-lookup"><span data-stu-id="0fb36-166">In the **Environments** list, select the Power Apps environment associated with your Human Resources instance.</span></span>

3. <span data-ttu-id="0fb36-167">Välj **miljö-URL** i avsnittet **information** på sidan.</span><span class="sxs-lookup"><span data-stu-id="0fb36-167">Select the **Environment URL** in the **Details** section of the page.</span></span>

4. <span data-ttu-id="0fb36-168">I **Lösning hälsocenter**, välj ikonen **Avancerad sökning** längst upp till höger på appsidan.</span><span class="sxs-lookup"><span data-stu-id="0fb36-168">In the **Solution Health Hub**, select the **Advanced Find** icon in the top right of the application page.</span></span>

5. <span data-ttu-id="0fb36-169">På sidan **Avancerad sökning** i listrutan **Sök efter** välj **Konfiguration av virtuella enhetens datakälla i Finance and Operations**.</span><span class="sxs-lookup"><span data-stu-id="0fb36-169">On the **Advanced Find** page, in the **Look for** dropdown list, select **Finance and Operations Virtual Data Source Configurations**.</span></span>

6. <span data-ttu-id="0fb36-170">Välj **resultat**.</span><span class="sxs-lookup"><span data-stu-id="0fb36-170">Select **Results**.</span></span>

7. <span data-ttu-id="0fb36-171">Markera posten **Microsoft HR datakälla**.</span><span class="sxs-lookup"><span data-stu-id="0fb36-171">Select the **Microsoft HR Data Source** record.</span></span>

8. <span data-ttu-id="0fb36-172">Ange den information som krävs för konfigurationen av datakällan:</span><span class="sxs-lookup"><span data-stu-id="0fb36-172">Enter the required information for the data source configuration:</span></span>

   - <span data-ttu-id="0fb36-173">**Mål-URL**: en URL till din personal namnrymd.</span><span class="sxs-lookup"><span data-stu-id="0fb36-173">**Target URL**: The URL of your Human Resources namespace.</span></span> <span data-ttu-id="0fb36-174">Formatet för mål-URL:en är:</span><span class="sxs-lookup"><span data-stu-id="0fb36-174">The format of the target URL is:</span></span>
     
     <span data-ttu-id="0fb36-175">https://\<hostname\>.hr.talent.dynamics.com/namespaces/\<namespaceID\>/</span><span class="sxs-lookup"><span data-stu-id="0fb36-175">https://\<hostname\>.hr.talent.dynamics.com/namespaces/\<namespaceID\>/</span></span>

     <span data-ttu-id="0fb36-176">Exempel:</span><span class="sxs-lookup"><span data-stu-id="0fb36-176">For example:</span></span>
     
     `https://aos.rts-sf-5ea54e35c68-westus2.hr.talent.dynamics.com/namespaces/49d24c565-8f4d-4891-b174-bf83d948ed0c/`

     >[!NOTE]
     ><span data-ttu-id="0fb36-177">Se till att du tar med "**/**"-tecknet i slutet av URL:en för att undvika att få ett fel.</span><span class="sxs-lookup"><span data-stu-id="0fb36-177">Be sure to include the "**/**" character at the end of the URL to avoid receiving an error.</span></span>

   - <span data-ttu-id="0fb36-178">**Klientorganisations-ID**: Azure Active Directory (Azure AD) klientorganisations-ID.</span><span class="sxs-lookup"><span data-stu-id="0fb36-178">**Tenant ID**: The Azure Active Directory (Azure AD) tenant ID.</span></span>

   - <span data-ttu-id="0fb36-179">**AAD app-ID**: det app-ID (klient) som skapades för den app som är registrerat i Microsoft Azure-portalen.</span><span class="sxs-lookup"><span data-stu-id="0fb36-179">**AAD Application ID**: The application (client) ID created for the application registered in the Microsoft Azure portal.</span></span> <span data-ttu-id="0fb36-180">Du har fått den här informationen tidigare under steget [Registrera appen i Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span><span class="sxs-lookup"><span data-stu-id="0fb36-180">You received this information earlier during the step [Register the app in Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span></span>

   - <span data-ttu-id="0fb36-181">**Hemlighet för AAD app-ID**: klienthemligheten som skapades för den app som är registrerat i Microsoft Azure-portalen.</span><span class="sxs-lookup"><span data-stu-id="0fb36-181">**AAD Application Secret**: The client secret created for the application registered in the Microsoft Azure portal.</span></span> <span data-ttu-id="0fb36-182">Du har fått den här informationen tidigare under steget [Registrera appen i Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span><span class="sxs-lookup"><span data-stu-id="0fb36-182">You received this information earlier during the step [Register the app in Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span></span>

   ![Microsoft HR-datakälla](./media/hr-admin-integration-virtual-entities-hr-data-source.jpg)

9. <span data-ttu-id="0fb36-184">Välj **Spara och stäng**.</span><span class="sxs-lookup"><span data-stu-id="0fb36-184">Select **Save & Close**.</span></span>

### <a name="grant-app-permissions-in-human-resources"></a><span data-ttu-id="0fb36-185">Ge appbehörighet i Human Resources</span><span class="sxs-lookup"><span data-stu-id="0fb36-185">Grant app permissions in Human Resources</span></span>

<span data-ttu-id="0fb36-186">Bevilja behörigheter för de två Azure AD-apparna i Human Resources:</span><span class="sxs-lookup"><span data-stu-id="0fb36-186">Grant permissions for the two Azure AD applications in Human Resources:</span></span>

- <span data-ttu-id="0fb36-187">Appen som har skapats för din innehavare på Microsoft Azure-portalen</span><span class="sxs-lookup"><span data-stu-id="0fb36-187">The app created for your tenant in the Microsoft Azure portal</span></span>
- <span data-ttu-id="0fb36-188">Appen Dynamics 365 HR Virtual Entity installeras Power Apps-miljön</span><span class="sxs-lookup"><span data-stu-id="0fb36-188">The Dynamics 365 HR Virtual Entity app installed in the Power Apps environment</span></span> 

1. <span data-ttu-id="0fb36-189">I Human Resources, öppna sidan **Azure Active Directory-appar**.</span><span class="sxs-lookup"><span data-stu-id="0fb36-189">In Human Resources, open the **Azure Active Directory applications** page.</span></span>

2. <span data-ttu-id="0fb36-190">Välj **Nytt** för att skapa en ny appost:</span><span class="sxs-lookup"><span data-stu-id="0fb36-190">Select **New** to create a new application record:</span></span>

    - <span data-ttu-id="0fb36-191">I fältet **klient-ID** anger du klient-ID för appen som du registrerade på Microsoft Azure-portalen.</span><span class="sxs-lookup"><span data-stu-id="0fb36-191">In the **Client ID** field, enter the client ID of the app you registered in the Microsoft Azure portal.</span></span>
    - <span data-ttu-id="0fb36-192">I fältet **Namn** anger du namnet för appen som du registrerade på Microsoft Azure-portalen.</span><span class="sxs-lookup"><span data-stu-id="0fb36-192">In the **Name** field, enter the name of the app you registered in the Microsoft Azure portal.</span></span>
    - <span data-ttu-id="0fb36-193">I fältet **Användar-ID** väljer du användar-ID för en användare med administratörsbehörighet i Human Resources och Power Apps-miljön.</span><span class="sxs-lookup"><span data-stu-id="0fb36-193">In the **User ID** field, select the user ID of a user with admin permissions in Human Resources and the Power Apps environment.</span></span>

3. <span data-ttu-id="0fb36-194">Välj **Nytt** för att skapa en andra appost:</span><span class="sxs-lookup"><span data-stu-id="0fb36-194">Select **New** to create a second application record:</span></span>

    - <span data-ttu-id="0fb36-195">**Klient-ID**: f9be0c49-aa22-4ec6-911a-c5da515226ff</span><span class="sxs-lookup"><span data-stu-id="0fb36-195">**Client Id**: f9be0c49-aa22-4ec6-911a-c5da515226ff</span></span>
    - <span data-ttu-id="0fb36-196">**Namn**: Dynamics 365 HR Virtual Entity</span><span class="sxs-lookup"><span data-stu-id="0fb36-196">**Name**: Dynamics 365 HR Virtual Entity</span></span>
    - <span data-ttu-id="0fb36-197">I fältet **Användar-ID** väljer du användar-ID för en användare med administratörsbehörighet i Human Resources och Power Apps-miljön.</span><span class="sxs-lookup"><span data-stu-id="0fb36-197">In the **User ID** field, select the user ID of a user with admin permissions in Human Resources and the Power Apps environment.</span></span>

## <a name="generate-virtual-entities"></a><span data-ttu-id="0fb36-198">Generera virtuella enheter</span><span class="sxs-lookup"><span data-stu-id="0fb36-198">Generate virtual entities</span></span>

<span data-ttu-id="0fb36-199">När installationsprogrammet är klart kan du välja vilka virtuella entiteter du vill generera och aktivera i din Common Data Service-instans.</span><span class="sxs-lookup"><span data-stu-id="0fb36-199">When setup completes, you can select the virtual entities you want to generate and enable in your Common Data Service instance.</span></span>

1. <span data-ttu-id="0fb36-200">I Human Resources, öppna sidan **Common Data Service (CDS) integration**.</span><span class="sxs-lookup"><span data-stu-id="0fb36-200">In Human Resources, open the **Common Data Service (CDS) integration** page.</span></span>

2. <span data-ttu-id="0fb36-201">Välj fliken **virtuella entiteter**.</span><span class="sxs-lookup"><span data-stu-id="0fb36-201">Select the **Virtual entities** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="0fb36-202">Växlingsknappen **Aktivera virtuell entitet** kommer att ställas in på **Ja** automatiskt när alla nödvändiga inställningar har slutförts.</span><span class="sxs-lookup"><span data-stu-id="0fb36-202">The **Enable the virtual entity** toggle will be set to **Yes** automatically when all required setup has been completed.</span></span> <span data-ttu-id="0fb36-203">Om växlingsknappen är inställd på **Nej** bör du granska stegen i de tidigare avsnitten i det här dokumentet så att alla nödvändiga inställningar är slutförda.</span><span class="sxs-lookup"><span data-stu-id="0fb36-203">If the toggle is set to **No**, review the steps in previous sections of this document to ensure all prerequisite setup is completed.</span></span>

3. <span data-ttu-id="0fb36-204">Välj den eller de entiteter du vill generera i Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="0fb36-204">Select the entity or entities you want to generate in Common Data Service.</span></span>

4. <span data-ttu-id="0fb36-205">Välj **generera/uppdatera**.</span><span class="sxs-lookup"><span data-stu-id="0fb36-205">Select **Generate/refresh**.</span></span>

![Common Data Service-integration](./media/hr-admin-integration-common-data-service-integration.jpg)

## <a name="check-entity-generation-status"></a><span data-ttu-id="0fb36-207">Kontrollera entitetens statusgenerering</span><span class="sxs-lookup"><span data-stu-id="0fb36-207">Check entity generation status</span></span>

<span data-ttu-id="0fb36-208">Virtuella entiteter genereras i Common Data Service genom en asynkron bakgrundsprocess.</span><span class="sxs-lookup"><span data-stu-id="0fb36-208">Virtual entities are generated in Common Data Service through an asynchronous background process.</span></span> <span data-ttu-id="0fb36-209">Uppdateringar av processvisningen i åtgärdscentret.</span><span class="sxs-lookup"><span data-stu-id="0fb36-209">Updates on the process display in the action center.</span></span> <span data-ttu-id="0fb36-210">Information om processen, inklusive felloggar, visas på sidan **Processautomatiseringar**.</span><span class="sxs-lookup"><span data-stu-id="0fb36-210">Details on the process, including error logs, appear in the **Process automations** page.</span></span>

1. <span data-ttu-id="0fb36-211">I Personal, öppna listsidan **Processautomatiseringar**.</span><span class="sxs-lookup"><span data-stu-id="0fb36-211">In Human Resources, open the **Process automations** page.</span></span>

2. <span data-ttu-id="0fb36-212">Välj fliken **Bakgrundsprocesser**.</span><span class="sxs-lookup"><span data-stu-id="0fb36-212">Select the **Background processes** tab.</span></span>

3. <span data-ttu-id="0fb36-213">Välj **Process för bakgrundsförfarande för asynkron operation av virtuell enhet**.</span><span class="sxs-lookup"><span data-stu-id="0fb36-213">Select **Virtual entity poll async operation background process**.</span></span>

4. <span data-ttu-id="0fb36-214">Välj **Visa senaste resultat**.</span><span class="sxs-lookup"><span data-stu-id="0fb36-214">Select **View most recent results**.</span></span>

<span data-ttu-id="0fb36-215">I det utfällbara fönstret visas de senaste körningsresultaten för processen.</span><span class="sxs-lookup"><span data-stu-id="0fb36-215">The slideout pane displays the most recent execution results for the process.</span></span> <span data-ttu-id="0fb36-216">Du kan visa loggen för processen, inklusive eventuella fel som returnerats från Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="0fb36-216">You can view the log for the process, including any errors returned from Common Data Service.</span></span>

## <a name="see-also"></a><span data-ttu-id="0fb36-217">Se även</span><span class="sxs-lookup"><span data-stu-id="0fb36-217">See also</span></span>

[<span data-ttu-id="0fb36-218">Vad är Common Data Service?</span><span class="sxs-lookup"><span data-stu-id="0fb36-218">What is Common Data Service?</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)<br>
[<span data-ttu-id="0fb36-219">Enhetsöversikt</span><span class="sxs-lookup"><span data-stu-id="0fb36-219">Entity overview</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/entity-overview)<br>
[<span data-ttu-id="0fb36-220">Översikt över entitetsrelationer</span><span class="sxs-lookup"><span data-stu-id="0fb36-220">Entity relationships overview</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/relationships-overview)<br>
[<span data-ttu-id="0fb36-221">Skapa och redigera virtuella entiteter som innehåller data från en extern datakälla</span><span class="sxs-lookup"><span data-stu-id="0fb36-221">Create and edit virtual entities that contain data from an external data source</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/create-edit-virtual-entities)<br>
[<span data-ttu-id="0fb36-222">Vad är Power Apps-portaler?</span><span class="sxs-lookup"><span data-stu-id="0fb36-222">What is Power Apps portals?</span></span>](https://docs.microsoft.com/powerapps/maker/portals/overview)<br>
[<span data-ttu-id="0fb36-223">Översikt över att skapa appar i Power Apps</span><span class="sxs-lookup"><span data-stu-id="0fb36-223">Overview of creating apps in Power Apps</span></span>](https://docs.microsoft.com/powerapps/maker/)
