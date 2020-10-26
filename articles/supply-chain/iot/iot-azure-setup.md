---
title: Konfigurera Azure-resurser för IoT-information
description: I det här avsnittet beskrivs hur du skapar och konfigurerar de Microsoft Azure-resurser som krävs för IoT-information.
author: ''
manager: tfehr
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: ''
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: bbac1676d28c7285c19ed48f77426a37ce123a29
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/10/2020
ms.locfileid: "3982904"
---
# <a name="set-up-azure-resources-for-iot-intelligence"></a><span data-ttu-id="04c09-103">Konfigurera Azure-resurser för IoT-information</span><span class="sxs-lookup"><span data-stu-id="04c09-103">Set up Azure resources for IoT Intelligence</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="04c09-104">I det här avsnittet beskrivs hur du skapar och konfigurerar de Microsoft Azure-resurser som krävs för IoT-information.</span><span class="sxs-lookup"><span data-stu-id="04c09-104">This topic explains how to create and configure the Microsoft Azure resources that you require for IoT Intelligence.</span></span>

## <a name="create-azure-resources"></a><span data-ttu-id="04c09-105">Skapa Azure-resurser</span><span class="sxs-lookup"><span data-stu-id="04c09-105">Create Azure resources</span></span>

<span data-ttu-id="04c09-106">Följ stegen nedan om du vill skapa ett IoT-nav en Redis-cache och ett nyckelvalv som Microsoft Dynamics 365 Supply Chain Management kan få åtkomst till.</span><span class="sxs-lookup"><span data-stu-id="04c09-106">Follow these steps to create an IoT hub, a Redis cache, and a key vault that can be accessed by Microsoft Dynamics 365 Supply Chain Management.</span></span>

### <a name="verify-that-the-microsoft-dynamics-erp-microservices-first-party-app-id-is-in-your-tenant"></a><span data-ttu-id="04c09-107">Kontrollera att förstaparts app-ID för Microsoft Dynamics ERP Microservices finns i din klientorganisation</span><span class="sxs-lookup"><span data-stu-id="04c09-107">Verify that the Microsoft Dynamics ERP Microservices first-party app ID is in your tenant</span></span>

<span data-ttu-id="04c09-108">Du kan kontrollera att förstaparts app-ID för Microsoft Dynamics ERP Microservices finns i din klientorganisation genom att följa stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="04c09-108">To verify that the app ID for the Microsoft Dynamics ERP Microservices first-party app is in your tenant, follow these steps.</span></span>

1. <span data-ttu-id="04c09-109">Logga in på Azure portal på <https://portal.azure.com>.</span><span class="sxs-lookup"><span data-stu-id="04c09-109">Sign in to the Azure portal at <https://portal.azure.com>.</span></span>
2. <span data-ttu-id="04c09-110">Gå till **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="04c09-110">Go to **Azure Active Directory**.</span></span>
3. <span data-ttu-id="04c09-111">Gå till **Företagsprogram**.</span><span class="sxs-lookup"><span data-stu-id="04c09-111">Go to **Enterprise applications**.</span></span>
4. <span data-ttu-id="04c09-112">I fältet **Programtyp** väljer du **Microsoft-program**.</span><span class="sxs-lookup"><span data-stu-id="04c09-112">In the **Application type** field, select **Microsoft applications**.</span></span>
5. <span data-ttu-id="04c09-113">I sökfältet anger du **Microsoft Dynamics ERP Microservices**.</span><span class="sxs-lookup"><span data-stu-id="04c09-113">In the search field, enter **Microsoft Dynamics ERP Microservices**.</span></span>
6. <span data-ttu-id="04c09-114">Kontrollera att **Microsoft Dynamics ERP Microservices** finns i listan.</span><span class="sxs-lookup"><span data-stu-id="04c09-114">Verify that **Microsoft Dynamics ERP Microservices** is in the list.</span></span> <span data-ttu-id="04c09-115">Andra program har liknande namn.</span><span class="sxs-lookup"><span data-stu-id="04c09-115">Other applications have similar names.</span></span> <span data-ttu-id="04c09-116">Se därför till att du använder rätt program.</span><span class="sxs-lookup"><span data-stu-id="04c09-116">Therefore, make sure that you find the correct application.</span></span> <span data-ttu-id="04c09-117">App-ID:t är **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span><span class="sxs-lookup"><span data-stu-id="04c09-117">The app ID is **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span></span>

    <span data-ttu-id="04c09-118">Om programmet inte finns med i listan måste du lägga till det i klientorganisationen:</span><span class="sxs-lookup"><span data-stu-id="04c09-118">If the application isn't in the list, you must add it to your tenant:</span></span>

    1. <span data-ttu-id="04c09-119">I Azure-portalen väljer du knappen för att öppna Azure Cloud Shell i verktygsfältet.</span><span class="sxs-lookup"><span data-stu-id="04c09-119">In the Azure portal, on the toolbar, select the button to open Azure Cloud Shell.</span></span>
    2. <span data-ttu-id="04c09-120">Kör kommandot **Install-Module AzureAD**.</span><span class="sxs-lookup"><span data-stu-id="04c09-120">Run the command **Install-Module AzureAD**.</span></span> <span data-ttu-id="04c09-121">Ange **J** om du vill installera modulen.</span><span class="sxs-lookup"><span data-stu-id="04c09-121">Enter **Y** to install the module.</span></span>
    3. <span data-ttu-id="04c09-122">Kör kommandot **Get-InstalledModule -Name "AzureAD"** för att bekräfta att modulen har installerats.</span><span class="sxs-lookup"><span data-stu-id="04c09-122">Run the command **Get-InstalledModule -Name "AzureAD"** to verify that the module is installed.</span></span>
    4. <span data-ttu-id="04c09-123">Kör kommandot **Connect-AzureAD -Confirm** för att köra autentiseringen.</span><span class="sxs-lookup"><span data-stu-id="04c09-123">Run the command **Connect-AzureAD -Confirm** to run the authentication.</span></span>
    5. <span data-ttu-id="04c09-124">Kör kommandot **New-AzureADServicePrincipal-AppId 0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span><span class="sxs-lookup"><span data-stu-id="04c09-124">Run the command **New-AzureADServicePrincipal -AppId 0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span></span>

    <span data-ttu-id="04c09-125">Du kan nu upprepa steg 1 till och med 6 och kontrollera att app-ID:t finns i din klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="04c09-125">You can now repeat steps 1 through 6 to verify that the app ID is in your tenant.</span></span>

### <a name="create-a-key-vault-resource"></a><span data-ttu-id="04c09-126">Skapa en nyckelvalvresurs</span><span class="sxs-lookup"><span data-stu-id="04c09-126">Create a key vault resource</span></span>

<span data-ttu-id="04c09-127">Gör så här om du vill skapa en nyckelvalvsresurs.</span><span class="sxs-lookup"><span data-stu-id="04c09-127">To create a key vault resource, follow these steps.</span></span>

1. <span data-ttu-id="04c09-128">Skapa eller gå till en resursgrupp i Azure-portalen.</span><span class="sxs-lookup"><span data-stu-id="04c09-128">In the Azure portal, create or go to a resource group.</span></span>
2. <span data-ttu-id="04c09-129">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="04c09-129">Select **Add**.</span></span>
3. <span data-ttu-id="04c09-130">På sidan **Ny** anger du **Nyckelvalv** i sökrutan.</span><span class="sxs-lookup"><span data-stu-id="04c09-130">On the **New** page, in the search field, enter **Key vault**.</span></span> <span data-ttu-id="04c09-131">Markera sedan **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="04c09-131">Then select **Create**.</span></span>
4. <span data-ttu-id="04c09-132">På sidan **Skapa nyckelvalv** anger du ett värde i fältet **Namn på nyckelvalv**.</span><span class="sxs-lookup"><span data-stu-id="04c09-132">On the **Create key vault** page, in the **Key vault name** field, enter a name.</span></span>
5. <span data-ttu-id="04c09-133">Granska standardvärdena och välj sedan **Granska + skapa**.</span><span class="sxs-lookup"><span data-stu-id="04c09-133">Review the default values, and then select **Review + create**.</span></span>
6. <span data-ttu-id="04c09-134">Markera **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="04c09-134">Select **Create**.</span></span>

<span data-ttu-id="04c09-135">Nyckelvärdet skapas i bakgrunden.</span><span class="sxs-lookup"><span data-stu-id="04c09-135">The key vault is created in the background.</span></span>

### <a name="create-an-iot-hub-resource"></a><span data-ttu-id="04c09-136">Skapa en IoT-navresurs</span><span class="sxs-lookup"><span data-stu-id="04c09-136">Create an IoT hub resource</span></span>

<span data-ttu-id="04c09-137">Gör så här om du vill skapa en IoT-navresurs.</span><span class="sxs-lookup"><span data-stu-id="04c09-137">To create an IoT hub resource, follow these steps.</span></span>

1. <span data-ttu-id="04c09-138">Skapa eller gå till en resursgrupp.</span><span class="sxs-lookup"><span data-stu-id="04c09-138">Create or go to a resource group.</span></span>
2. <span data-ttu-id="04c09-139">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="04c09-139">Select **Add**.</span></span>
3. <span data-ttu-id="04c09-140">På sidan **Ny** anger du **Iot-nav** i sökrutan.</span><span class="sxs-lookup"><span data-stu-id="04c09-140">On the **New** page, in the search field, enter **Iot Hub**.</span></span> <span data-ttu-id="04c09-141">Markera sedan **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="04c09-141">Then select **Create**.</span></span>
4. <span data-ttu-id="04c09-142">I fältet **IoT-navnamn** anger du ett namn.</span><span class="sxs-lookup"><span data-stu-id="04c09-142">In the **IoT hub name** field, enter a name.</span></span>
5. <span data-ttu-id="04c09-143">Granska standardvärdena och välj sedan **Granska + skapa**.</span><span class="sxs-lookup"><span data-stu-id="04c09-143">Review the default values, and then select **Review + create**.</span></span>
6. <span data-ttu-id="04c09-144">Markera **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="04c09-144">Select **Create**.</span></span>

<span data-ttu-id="04c09-145">IoT-navet skapas i bakgrunden.</span><span class="sxs-lookup"><span data-stu-id="04c09-145">The IoT hub is created in the background.</span></span>

> [!NOTE]
> <span data-ttu-id="04c09-146">Vi rekommenderar att du endast skapar en enda IoT-navresurs per miljö.</span><span class="sxs-lookup"><span data-stu-id="04c09-146">We recommend that you create only one IoT hub resource per environment.</span></span>

### <a name="create-a-redis-cache-resource"></a><span data-ttu-id="04c09-147">Skapa en resurs för Redis-cache</span><span class="sxs-lookup"><span data-stu-id="04c09-147">Create a Redis cache resource</span></span>

<span data-ttu-id="04c09-148">Gör så här om du vill skapa en Redis-cacheresurs.</span><span class="sxs-lookup"><span data-stu-id="04c09-148">To create a Redis cache resource, follow these steps.</span></span>

1. <span data-ttu-id="04c09-149">Skapa eller gå till en resursgrupp.</span><span class="sxs-lookup"><span data-stu-id="04c09-149">Create or go to a resource group.</span></span>
2. <span data-ttu-id="04c09-150">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="04c09-150">Select **Add**.</span></span>
3. <span data-ttu-id="04c09-151">På sidan **Ny** anger du **Azure Cache for Redis** i sökfältet.</span><span class="sxs-lookup"><span data-stu-id="04c09-151">On the **New** page, in the search field, enter **Azure Cache for Redis**.</span></span> <span data-ttu-id="04c09-152">Markera sedan **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="04c09-152">Then select **Create**.</span></span>
4. <span data-ttu-id="04c09-153">I fältet **DNS-namn** anger du ett namn.</span><span class="sxs-lookup"><span data-stu-id="04c09-153">In the **DNS name** field, enter a name.</span></span>
5. <span data-ttu-id="04c09-154">Granska standardvärdena och välj sedan **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="04c09-154">Review the default values, and then select **Create**.</span></span>

<span data-ttu-id="04c09-155">Redis-cachen skapas i bakgrunden.</span><span class="sxs-lookup"><span data-stu-id="04c09-155">The Redis cache is created in the background.</span></span>

> [!NOTE]
> <span data-ttu-id="04c09-156">Vi rekommenderar att du endast skapar en enda Redis-cache per miljö.</span><span class="sxs-lookup"><span data-stu-id="04c09-156">We recommend that you create only one Redis cache per environment.</span></span>

<span data-ttu-id="04c09-157">Alla resurser har nu skapats.</span><span class="sxs-lookup"><span data-stu-id="04c09-157">All the resources have now been created.</span></span>

## <a name="configure-the-azure-resources"></a><span data-ttu-id="04c09-158">Konfigurera Azure-resurserna</span><span class="sxs-lookup"><span data-stu-id="04c09-158">Configure the Azure resources</span></span>

### <a name="configure-the-iot-hub"></a><span data-ttu-id="04c09-159">Konfigurera IoT-navet</span><span class="sxs-lookup"><span data-stu-id="04c09-159">Configure the IoT hub</span></span>

<span data-ttu-id="04c09-160">Följ dessa steg för att konfigurera IoT-navet:</span><span class="sxs-lookup"><span data-stu-id="04c09-160">To configure the IoT hub, follow these steps.</span></span>

1. <span data-ttu-id="04c09-161">Markera IoT Hub-resursen bland dina resurser.</span><span class="sxs-lookup"><span data-stu-id="04c09-161">In your resources, select the IoT hub resource.</span></span>
2. <span data-ttu-id="04c09-162">I det vänstra navigeringsfönstret väljer du **Inbyggda slutpunkter**.</span><span class="sxs-lookup"><span data-stu-id="04c09-162">In the left navigation pane, select **Built-in endpoints**.</span></span>
3. <span data-ttu-id="04c09-163">Under **Konsumentgrupper** klistrar du in följande konsumentgrupper.</span><span class="sxs-lookup"><span data-stu-id="04c09-163">Under **Consumer groups**, paste the following consumer groups.</span></span> <span data-ttu-id="04c09-164">Dessa konsumentgrupper motsvarar de färdiga scenarierna.</span><span class="sxs-lookup"><span data-stu-id="04c09-164">These consumer groups correspond to the out-of-box scenarios.</span></span>

    + <span data-ttu-id="04c09-165">microsoft.dynamics.iotintelligence-1</span><span class="sxs-lookup"><span data-stu-id="04c09-165">microsoft.dynamics.iotintelligence-1</span></span>
    + <span data-ttu-id="04c09-166">microsoft.dynamics.iotintelligence-2</span><span class="sxs-lookup"><span data-stu-id="04c09-166">microsoft.dynamics.iotintelligence-2</span></span>
    + <span data-ttu-id="04c09-167">microsoft.dynamics.iotintelligence-3</span><span class="sxs-lookup"><span data-stu-id="04c09-167">microsoft.dynamics.iotintelligence-3</span></span>

### <a name="configure-the-key-vault"></a><span data-ttu-id="04c09-168">Konfigurera nyckelvalvet</span><span class="sxs-lookup"><span data-stu-id="04c09-168">Configure the key vault</span></span>

<span data-ttu-id="04c09-169">Följ dessa steg när du vill konfigurera nyckelvalvet.</span><span class="sxs-lookup"><span data-stu-id="04c09-169">To configure the key vault, follow these steps.</span></span>

1. <span data-ttu-id="04c09-170">Markera nyckelvalvsresursen bland dina resurser.</span><span class="sxs-lookup"><span data-stu-id="04c09-170">In your resources, select the key vault resource.</span></span>
2. <span data-ttu-id="04c09-171">I det vänstra navigeringsfönstret välj er du **Policyåtkomst**.</span><span class="sxs-lookup"><span data-stu-id="04c09-171">In the left navigation pane, select **Access policies**.</span></span>
3. <span data-ttu-id="04c09-172">Välj **Lägg till en åtkomstpolicy**.</span><span class="sxs-lookup"><span data-stu-id="04c09-172">Select **Add an access policy**.</span></span>
4. <span data-ttu-id="04c09-173">På sidan **Lägg till åtkomstpolicy**, i fältet **Hemliga behörigheter**, väljer du **Hämta** och **Lista**.</span><span class="sxs-lookup"><span data-stu-id="04c09-173">On the **Add access policy** page, in the **Secret permissions** field, select **Get** and **List**.</span></span>
5. <span data-ttu-id="04c09-174">Klicka på i **Välj primär**.</span><span class="sxs-lookup"><span data-stu-id="04c09-174">Click in the **Select principal**.</span></span>
6. <span data-ttu-id="04c09-175">I dialogrutan **Primär** letar du upp och väljer **Microsoft Dynamics ERP Microservices**.</span><span class="sxs-lookup"><span data-stu-id="04c09-175">In the **Principal** dialog box, search for and select **Microsoft Dynamics ERP Microservices**.</span></span> <span data-ttu-id="04c09-176">Välj sedan **Välj**.</span><span class="sxs-lookup"><span data-stu-id="04c09-176">Then select **Select**.</span></span>
7. <span data-ttu-id="04c09-177">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="04c09-177">Select **Add**.</span></span>
8. <span data-ttu-id="04c09-178">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="04c09-178">Select **Save**.</span></span>

<span data-ttu-id="04c09-179">Appen har nu åtkomst till hemligheterna i nyckelvalvet.</span><span class="sxs-lookup"><span data-stu-id="04c09-179">The app now has access to the secrets in the key vault.</span></span>

### <a name="save-the-iot-hub-connection-string-secret"></a><span data-ttu-id="04c09-180">Spara hemligheten för IoT-navets anslutningssträng</span><span class="sxs-lookup"><span data-stu-id="04c09-180">Save the IoT hub connection string secret</span></span>

<span data-ttu-id="04c09-181">Gör så här om du vill spara hemligheten för IoT-navets anslutningssträng:</span><span class="sxs-lookup"><span data-stu-id="04c09-181">To save the secret for the IoT hub connection string, follow these steps.</span></span>

1. <span data-ttu-id="04c09-182">Markera IoT Hub-resursen bland dina resurser.</span><span class="sxs-lookup"><span data-stu-id="04c09-182">In your resources, select the IoT hub resource.</span></span>
2. <span data-ttu-id="04c09-183">I det vänstra navigeringsfönstret väljer du **Inbyggda slutpunkter**.</span><span class="sxs-lookup"><span data-stu-id="04c09-183">In the left navigation pane, select **Built-in endpoints**.</span></span>
3. <span data-ttu-id="04c09-184">Kopiera värdet i fältet för **Händelsenavskompatilbel slutpunkt**.</span><span class="sxs-lookup"><span data-stu-id="04c09-184">Copy the value in the **Event Hub-compatible endpoint** field.</span></span>
4. <span data-ttu-id="04c09-185">Gå till nyckelvalvsresursen.</span><span class="sxs-lookup"><span data-stu-id="04c09-185">Go to the key vault resource.</span></span>
5. <span data-ttu-id="04c09-186">I navigeringsfönstret till vänster välj er du **Hemligheter**.</span><span class="sxs-lookup"><span data-stu-id="04c09-186">In the left navigation pane, select **Secrets**.</span></span>
6. <span data-ttu-id="04c09-187">Välj **Generera/Importera**.</span><span class="sxs-lookup"><span data-stu-id="04c09-187">Select **Generate/Import**.</span></span>
7. <span data-ttu-id="04c09-188">Ange sedan ett namn i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="04c09-188">In the **Name** field, enter a name.</span></span>
8. <span data-ttu-id="04c09-189">I fältet **Värde** klistrar du in det slutpunktsvärde som du tidigare kopierade.</span><span class="sxs-lookup"><span data-stu-id="04c09-189">In the **Value** field, paste the endpoint value that you copied earlier.</span></span>
9. <span data-ttu-id="04c09-190">Markera **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="04c09-190">Select **Create**.</span></span>

### <a name="save-the-redis-cache-connection-string-secret"></a><span data-ttu-id="04c09-191">Spara hemligheten för Redis-cachens anslutningssträng</span><span class="sxs-lookup"><span data-stu-id="04c09-191">Save the Redis cache connection string secret</span></span>

<span data-ttu-id="04c09-192">Gör så här om du vill spara hemligheten för Redis-cachens anslutningssträng:</span><span class="sxs-lookup"><span data-stu-id="04c09-192">To save the secret for the Redis cache connection string, follow these steps.</span></span>

1. <span data-ttu-id="04c09-193">Markera Redis-cache-resursen bland dina resurser.</span><span class="sxs-lookup"><span data-stu-id="04c09-193">In your resources, select the Redis cache resource.</span></span>
2. <span data-ttu-id="04c09-194">Välj **Åtkomstnycklar**.</span><span class="sxs-lookup"><span data-stu-id="04c09-194">Select **Access keys**.</span></span>
3. <span data-ttu-id="04c09-195">Kopiera värdet i fältet **Primär anslutningssträng**.</span><span class="sxs-lookup"><span data-stu-id="04c09-195">Copy the value in the **Primary connection string** field.</span></span>
4. <span data-ttu-id="04c09-196">Gå till nyckelvalvsresursen.</span><span class="sxs-lookup"><span data-stu-id="04c09-196">Go to the key vault resource.</span></span>
5. <span data-ttu-id="04c09-197">I navigeringsfönstret till vänster välj er du **Hemligheter**.</span><span class="sxs-lookup"><span data-stu-id="04c09-197">In the left navigation pane, select **Secrets**.</span></span>
6. <span data-ttu-id="04c09-198">Välj **Generera/Importera**.</span><span class="sxs-lookup"><span data-stu-id="04c09-198">Select **Generate/Import**.</span></span>
7. <span data-ttu-id="04c09-199">Ange sedan ett namn i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="04c09-199">In the **Name** field, enter a name.</span></span>
8. <span data-ttu-id="04c09-200">I fältet **Värde** klistrar du in den anslutningssträng som du tidigare kopierade.</span><span class="sxs-lookup"><span data-stu-id="04c09-200">In the **Value** field, paste the connection string that you copied earlier.</span></span>
9. <span data-ttu-id="04c09-201">Markera **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="04c09-201">Select **Create**.</span></span>

> [!NOTE]
> <span data-ttu-id="04c09-202">När du uppdaterar en av anslutningssträngarna måste du också uppdatera de hemliga värdena.</span><span class="sxs-lookup"><span data-stu-id="04c09-202">Whenever you update one of the connection strings, you must also update the secret values.</span></span>

<span data-ttu-id="04c09-203">Du har nu slutfört etableringen av de nödvändiga Azure-resurserna.</span><span class="sxs-lookup"><span data-stu-id="04c09-203">You've now finished provisioning the required Azure resources.</span></span> <span data-ttu-id="04c09-204">Nästa steg är att [installera IoT-information-tillägget i Microsoft Dynamics Lifecycle Services (LCS)](iot-lcs-setup.md).</span><span class="sxs-lookup"><span data-stu-id="04c09-204">The next step is to [install the IoT Intelligence add-in in Microsoft Dynamics Lifecycle Services (LCS)](iot-lcs-setup.md).</span></span>
