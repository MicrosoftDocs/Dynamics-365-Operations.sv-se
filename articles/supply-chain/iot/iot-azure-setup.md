---
title: Konfigurera Azure-resurser för IoT-information
description: I det här avsnittet beskrivs hur du skapar och konfigurerar de Microsoft Azure-resurser som krävs för IoT-information.
author: robinarh
manager: AnnBe
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
ms.author: ''
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 1f05f597f86df602c0e00af006b7ccf804f50929
ms.sourcegitcommit: 261b70ea358b2c231e20f320ed8bd6adc1e7d715
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2020
ms.locfileid: "3386563"
---
# <a name="set-up-azure-resources-for-iot-intelligence"></a><span data-ttu-id="38c2a-103">Konfigurera Azure-resurser för IoT-information</span><span class="sxs-lookup"><span data-stu-id="38c2a-103">Set up Azure resources for IoT Intelligence</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="38c2a-104">I det här avsnittet beskrivs hur du skapar och konfigurerar de Microsoft Azure-resurser som krävs för IoT-information.</span><span class="sxs-lookup"><span data-stu-id="38c2a-104">This topic explains how to create and configure the Microsoft Azure resources that you require for IoT Intelligence.</span></span>

## <a name="create-azure-resources"></a><span data-ttu-id="38c2a-105">Skapa Azure-resurser</span><span class="sxs-lookup"><span data-stu-id="38c2a-105">Create Azure resources</span></span>

<span data-ttu-id="38c2a-106">Följ stegen nedan om du vill skapa ett IoT-nav en Redis-cache och ett nyckelvalv som Microsoft Dynamics 365 Supply Chain Management kan få åtkomst till.</span><span class="sxs-lookup"><span data-stu-id="38c2a-106">Follow these steps to create an IoT hub, a Redis cache, and a key vault that can be accessed by Microsoft Dynamics 365 Supply Chain Management.</span></span>

### <a name="verify-that-the-microsoft-dynamics-erp-microservices-first-party-app-id-is-in-your-tenant"></a><span data-ttu-id="38c2a-107">Kontrollera att förstaparts app-ID för Microsoft Dynamics ERP Microservices finns i din klientorganisation</span><span class="sxs-lookup"><span data-stu-id="38c2a-107">Verify that the Microsoft Dynamics ERP Microservices first-party app ID is in your tenant</span></span>

<span data-ttu-id="38c2a-108">Du kan kontrollera att förstaparts app-ID för Microsoft Dynamics ERP Microservices finns i din klientorganisation genom att följa stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="38c2a-108">To verify that the app ID for the Microsoft Dynamics ERP Microservices first-party app is in your tenant, follow these steps.</span></span>

1. <span data-ttu-id="38c2a-109">Logga in på Azure portal på <https://portal.azure.com>.</span><span class="sxs-lookup"><span data-stu-id="38c2a-109">Sign in to the Azure portal at <https://portal.azure.com>.</span></span>
2. <span data-ttu-id="38c2a-110">Gå till **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="38c2a-110">Go to **Azure Active Directory**.</span></span>
3. <span data-ttu-id="38c2a-111">Gå till **Företagsprogram**.</span><span class="sxs-lookup"><span data-stu-id="38c2a-111">Go to **Enterprise applications**.</span></span>
4. <span data-ttu-id="38c2a-112">I fältet **Programtyp** väljer du **Microsoft-program**.</span><span class="sxs-lookup"><span data-stu-id="38c2a-112">In the **Application type** field, select **Microsoft applications**.</span></span>
5. <span data-ttu-id="38c2a-113">I sökfältet anger du **Microsoft Dynamics ERP Microservices**.</span><span class="sxs-lookup"><span data-stu-id="38c2a-113">In the search field, enter **Microsoft Dynamics ERP Microservices**.</span></span>
6. <span data-ttu-id="38c2a-114">Kontrollera att **Microsoft Dynamics ERP Microservices** finns i listan.</span><span class="sxs-lookup"><span data-stu-id="38c2a-114">Verify that **Microsoft Dynamics ERP Microservices** is in the list.</span></span> <span data-ttu-id="38c2a-115">Andra program har liknande namn.</span><span class="sxs-lookup"><span data-stu-id="38c2a-115">Other applications have similar names.</span></span> <span data-ttu-id="38c2a-116">Se därför till att du använder rätt program.</span><span class="sxs-lookup"><span data-stu-id="38c2a-116">Therefore, make sure that you find the correct application.</span></span> <span data-ttu-id="38c2a-117">App-ID:t är **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span><span class="sxs-lookup"><span data-stu-id="38c2a-117">The app ID is **0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span></span>

    <span data-ttu-id="38c2a-118">Om programmet inte finns med i listan måste du lägga till det i klientorganisationen:</span><span class="sxs-lookup"><span data-stu-id="38c2a-118">If the application isn't in the list, you must add it to your tenant:</span></span>

    1. <span data-ttu-id="38c2a-119">I Azure-portalen väljer du knappen för att öppna Azure Cloud Shell i verktygsfältet.</span><span class="sxs-lookup"><span data-stu-id="38c2a-119">In the Azure portal, on the toolbar, select the button to open Azure Cloud Shell.</span></span>
    2. <span data-ttu-id="38c2a-120">Kör kommandot **Install-Module AzureAD**.</span><span class="sxs-lookup"><span data-stu-id="38c2a-120">Run the command **Install-Module AzureAD**.</span></span> <span data-ttu-id="38c2a-121">Ange **J** om du vill installera modulen.</span><span class="sxs-lookup"><span data-stu-id="38c2a-121">Enter **Y** to install the module.</span></span>
    3. <span data-ttu-id="38c2a-122">Kör kommandot **Get-InstalledModule -Name "AzureAD"** för att bekräfta att modulen har installerats.</span><span class="sxs-lookup"><span data-stu-id="38c2a-122">Run the command **Get-InstalledModule -Name "AzureAD"** to verify that the module is installed.</span></span>
    4. <span data-ttu-id="38c2a-123">Kör kommandot **Connect-AzureAD -Confirm** för att köra autentiseringen.</span><span class="sxs-lookup"><span data-stu-id="38c2a-123">Run the command **Connect-AzureAD -Confirm** to run the authentication.</span></span>
    5. <span data-ttu-id="38c2a-124">Kör kommandot **New-AzureADServicePrincipal-AppId 0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span><span class="sxs-lookup"><span data-stu-id="38c2a-124">Run the command **New-AzureADServicePrincipal -AppId 0cdb527f-a8d1-4bf8-9436-b352c68682b2**.</span></span>

    <span data-ttu-id="38c2a-125">Du kan nu upprepa steg 1 till och med 6 och kontrollera att app-ID:t finns i din klientorganisation.</span><span class="sxs-lookup"><span data-stu-id="38c2a-125">You can now repeat steps 1 through 6 to verify that the app ID is in your tenant.</span></span>

### <a name="create-a-key-vault-resource"></a><span data-ttu-id="38c2a-126">Skapa en nyckelvalvresurs</span><span class="sxs-lookup"><span data-stu-id="38c2a-126">Create a key vault resource</span></span>

<span data-ttu-id="38c2a-127">Gör så här om du vill skapa en nyckelvalvsresurs.</span><span class="sxs-lookup"><span data-stu-id="38c2a-127">To create a key vault resource, follow these steps.</span></span>

1. <span data-ttu-id="38c2a-128">Skapa eller gå till en resursgrupp i Azure-portalen.</span><span class="sxs-lookup"><span data-stu-id="38c2a-128">In the Azure portal, create or go to a resource group.</span></span>
2. <span data-ttu-id="38c2a-129">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="38c2a-129">Select **Add**.</span></span>
3. <span data-ttu-id="38c2a-130">På sidan **Ny** anger du **Nyckelvalv** i sökrutan.</span><span class="sxs-lookup"><span data-stu-id="38c2a-130">On the **New** page, in the search field, enter **Key vault**.</span></span> <span data-ttu-id="38c2a-131">Markera sedan **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="38c2a-131">Then select **Create**.</span></span>
4. <span data-ttu-id="38c2a-132">På sidan **Skapa nyckelvalv** anger du ett värde i fältet **Namn på nyckelvalv**.</span><span class="sxs-lookup"><span data-stu-id="38c2a-132">On the **Create key vault** page, in the **Key vault name** field, enter a name.</span></span>
5. <span data-ttu-id="38c2a-133">Granska standardvärdena och välj sedan **Granska + skapa**.</span><span class="sxs-lookup"><span data-stu-id="38c2a-133">Review the default values, and then select **Review + create**.</span></span>
6. <span data-ttu-id="38c2a-134">Markera **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="38c2a-134">Select **Create**.</span></span>

<span data-ttu-id="38c2a-135">Nyckelvärdet skapas i bakgrunden.</span><span class="sxs-lookup"><span data-stu-id="38c2a-135">The key vault is created in the background.</span></span>

### <a name="create-an-iot-hub-resource"></a><span data-ttu-id="38c2a-136">Skapa en IoT-navresurs</span><span class="sxs-lookup"><span data-stu-id="38c2a-136">Create an IoT hub resource</span></span>

<span data-ttu-id="38c2a-137">Gör så här om du vill skapa en IoT-navresurs.</span><span class="sxs-lookup"><span data-stu-id="38c2a-137">To create an IoT hub resource, follow these steps.</span></span>

1. <span data-ttu-id="38c2a-138">Skapa eller gå till en resursgrupp.</span><span class="sxs-lookup"><span data-stu-id="38c2a-138">Create or go to a resource group.</span></span>
2. <span data-ttu-id="38c2a-139">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="38c2a-139">Select **Add**.</span></span>
3. <span data-ttu-id="38c2a-140">På sidan **Ny** anger du **Iot-nav** i sökrutan.</span><span class="sxs-lookup"><span data-stu-id="38c2a-140">On the **New** page, in the search field, enter **Iot Hub**.</span></span> <span data-ttu-id="38c2a-141">Markera sedan **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="38c2a-141">Then select **Create**.</span></span>
4. <span data-ttu-id="38c2a-142">I fältet **IoT-navnamn** anger du ett namn.</span><span class="sxs-lookup"><span data-stu-id="38c2a-142">In the **IoT hub name** field, enter a name.</span></span>
5. <span data-ttu-id="38c2a-143">Granska standardvärdena och välj sedan **Granska + skapa**.</span><span class="sxs-lookup"><span data-stu-id="38c2a-143">Review the default values, and then select **Review + create**.</span></span>
6. <span data-ttu-id="38c2a-144">Markera **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="38c2a-144">Select **Create**.</span></span>

<span data-ttu-id="38c2a-145">IoT-navet skapas i bakgrunden.</span><span class="sxs-lookup"><span data-stu-id="38c2a-145">The IoT hub is created in the background.</span></span>

> [!NOTE]
> <span data-ttu-id="38c2a-146">Vi rekommenderar att du endast skapar en enda IoT-navresurs per miljö.</span><span class="sxs-lookup"><span data-stu-id="38c2a-146">We recommend that you create only one IoT hub resource per environment.</span></span>

### <a name="create-a-redis-cache-resource"></a><span data-ttu-id="38c2a-147">Skapa en resurs för Redis-cache</span><span class="sxs-lookup"><span data-stu-id="38c2a-147">Create a Redis cache resource</span></span>

<span data-ttu-id="38c2a-148">Gör så här om du vill skapa en Redis-cacheresurs.</span><span class="sxs-lookup"><span data-stu-id="38c2a-148">To create a Redis cache resource, follow these steps.</span></span>

1. <span data-ttu-id="38c2a-149">Skapa eller gå till en resursgrupp.</span><span class="sxs-lookup"><span data-stu-id="38c2a-149">Create or go to a resource group.</span></span>
2. <span data-ttu-id="38c2a-150">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="38c2a-150">Select **Add**.</span></span>
3. <span data-ttu-id="38c2a-151">På sidan **Ny** anger du **Azure Cache for Redis** i sökfältet.</span><span class="sxs-lookup"><span data-stu-id="38c2a-151">On the **New** page, in the search field, enter **Azure Cache for Redis**.</span></span> <span data-ttu-id="38c2a-152">Markera sedan **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="38c2a-152">Then select **Create**.</span></span>
4. <span data-ttu-id="38c2a-153">I fältet **DNS-namn** anger du ett namn.</span><span class="sxs-lookup"><span data-stu-id="38c2a-153">In the **DNS name** field, enter a name.</span></span>
5. <span data-ttu-id="38c2a-154">Granska standardvärdena och välj sedan **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="38c2a-154">Review the default values, and then select **Create**.</span></span>

<span data-ttu-id="38c2a-155">Redis-cachen skapas i bakgrunden.</span><span class="sxs-lookup"><span data-stu-id="38c2a-155">The Redis cache is created in the background.</span></span>

> [!NOTE]
> <span data-ttu-id="38c2a-156">Vi rekommenderar att du endast skapar en enda Redis-cache per miljö.</span><span class="sxs-lookup"><span data-stu-id="38c2a-156">We recommend that you create only one Redis cache per environment.</span></span>

<span data-ttu-id="38c2a-157">Alla resurser har nu skapats.</span><span class="sxs-lookup"><span data-stu-id="38c2a-157">All the resources have now been created.</span></span>

## <a name="configure-the-azure-resources"></a><span data-ttu-id="38c2a-158">Konfigurera Azure-resurserna</span><span class="sxs-lookup"><span data-stu-id="38c2a-158">Configure the Azure resources</span></span>

### <a name="configure-the-iot-hub"></a><span data-ttu-id="38c2a-159">Konfigurera IoT-navet</span><span class="sxs-lookup"><span data-stu-id="38c2a-159">Configure the IoT hub</span></span>

<span data-ttu-id="38c2a-160">Följ dessa steg för att konfigurera IoT-navet:</span><span class="sxs-lookup"><span data-stu-id="38c2a-160">To configure the IoT hub, follow these steps.</span></span>

1. <span data-ttu-id="38c2a-161">Markera IoT Hub-resursen bland dina resurser.</span><span class="sxs-lookup"><span data-stu-id="38c2a-161">In your resources, select the IoT hub resource.</span></span>
2. <span data-ttu-id="38c2a-162">I det vänstra navigeringsfönstret väljer du **Inbyggda slutpunkter**.</span><span class="sxs-lookup"><span data-stu-id="38c2a-162">In the left navigation pane, select **Built-in endpoints**.</span></span>
3. <span data-ttu-id="38c2a-163">Under **Konsumentgrupper** klistrar du in följande konsumentgrupper.</span><span class="sxs-lookup"><span data-stu-id="38c2a-163">Under **Consumer groups**, paste the following consumer groups.</span></span> <span data-ttu-id="38c2a-164">Dessa konsumentgrupper motsvarar de färdiga scenarierna.</span><span class="sxs-lookup"><span data-stu-id="38c2a-164">These consumer groups correspond to the out-of-box scenarios.</span></span>

    + <span data-ttu-id="38c2a-165">microsoft.dynamics.iotintelligence-1</span><span class="sxs-lookup"><span data-stu-id="38c2a-165">microsoft.dynamics.iotintelligence-1</span></span>
    + <span data-ttu-id="38c2a-166">microsoft.dynamics.iotintelligence-2</span><span class="sxs-lookup"><span data-stu-id="38c2a-166">microsoft.dynamics.iotintelligence-2</span></span>
    + <span data-ttu-id="38c2a-167">microsoft.dynamics.iotintelligence-3</span><span class="sxs-lookup"><span data-stu-id="38c2a-167">microsoft.dynamics.iotintelligence-3</span></span>

### <a name="configure-the-key-vault"></a><span data-ttu-id="38c2a-168">Konfigurera nyckelvalvet</span><span class="sxs-lookup"><span data-stu-id="38c2a-168">Configure the key vault</span></span>

<span data-ttu-id="38c2a-169">Följ dessa steg när du vill konfigurera nyckelvalvet.</span><span class="sxs-lookup"><span data-stu-id="38c2a-169">To configure the key vault, follow these steps.</span></span>

1. <span data-ttu-id="38c2a-170">Markera nyckelvalvsresursen bland dina resurser.</span><span class="sxs-lookup"><span data-stu-id="38c2a-170">In your resources, select the key vault resource.</span></span>
2. <span data-ttu-id="38c2a-171">I det vänstra navigeringsfönstret välj er du **Policyåtkomst**.</span><span class="sxs-lookup"><span data-stu-id="38c2a-171">In the left navigation pane, select **Access policies**.</span></span>
3. <span data-ttu-id="38c2a-172">Välj **Lägg till en åtkomstpolicy**.</span><span class="sxs-lookup"><span data-stu-id="38c2a-172">Select **Add an access policy**.</span></span>
4. <span data-ttu-id="38c2a-173">På sidan **Lägg till åtkomstpolicy**, i fältet **Hemliga behörigheter**, väljer du **Hämta** och **Lista**.</span><span class="sxs-lookup"><span data-stu-id="38c2a-173">On the **Add access policy** page, in the **Secret permissions** field, select **Get** and **List**.</span></span>
5. <span data-ttu-id="38c2a-174">Klicka på i **Välj primär**.</span><span class="sxs-lookup"><span data-stu-id="38c2a-174">Click in the **Select principal**.</span></span>
6. <span data-ttu-id="38c2a-175">I dialogrutan **Primär** letar du upp och väljer **Microsoft Dynamics ERP Microservices**.</span><span class="sxs-lookup"><span data-stu-id="38c2a-175">In the **Principal** dialog box, search for and select **Microsoft Dynamics ERP Microservices**.</span></span> <span data-ttu-id="38c2a-176">Välj sedan **Välj**.</span><span class="sxs-lookup"><span data-stu-id="38c2a-176">Then select **Select**.</span></span>
7. <span data-ttu-id="38c2a-177">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="38c2a-177">Select **Add**.</span></span>
8. <span data-ttu-id="38c2a-178">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="38c2a-178">Select **Save**.</span></span>

<span data-ttu-id="38c2a-179">Appen har nu åtkomst till hemligheterna i nyckelvalvet.</span><span class="sxs-lookup"><span data-stu-id="38c2a-179">The app now has access to the secrets in the key vault.</span></span>

### <a name="save-the-iot-hub-connection-string-secret"></a><span data-ttu-id="38c2a-180">Spara hemligheten för IoT-navets anslutningssträng</span><span class="sxs-lookup"><span data-stu-id="38c2a-180">Save the IoT hub connection string secret</span></span>

<span data-ttu-id="38c2a-181">Gör så här om du vill spara hemligheten för IoT-navets anslutningssträng:</span><span class="sxs-lookup"><span data-stu-id="38c2a-181">To save the secret for the IoT hub connection string, follow these steps.</span></span>

1. <span data-ttu-id="38c2a-182">Markera IoT Hub-resursen bland dina resurser.</span><span class="sxs-lookup"><span data-stu-id="38c2a-182">In your resources, select the IoT hub resource.</span></span>
2. <span data-ttu-id="38c2a-183">I det vänstra navigeringsfönstret väljer du **Inbyggda slutpunkter**.</span><span class="sxs-lookup"><span data-stu-id="38c2a-183">In the left navigation pane, select **Built-in endpoints**.</span></span>
3. <span data-ttu-id="38c2a-184">Kopiera värdet i fältet för **Händelsenavskompatilbel slutpunkt**.</span><span class="sxs-lookup"><span data-stu-id="38c2a-184">Copy the value in the **Event Hub-compatible endpoint** field.</span></span>
4. <span data-ttu-id="38c2a-185">Gå till nyckelvalvsresursen.</span><span class="sxs-lookup"><span data-stu-id="38c2a-185">Go to the key vault resource.</span></span>
5. <span data-ttu-id="38c2a-186">I navigeringsfönstret till vänster välj er du **Hemligheter**.</span><span class="sxs-lookup"><span data-stu-id="38c2a-186">In the left navigation pane, select **Secrets**.</span></span>
6. <span data-ttu-id="38c2a-187">Välj **Generera/Importera**.</span><span class="sxs-lookup"><span data-stu-id="38c2a-187">Select **Generate/Import**.</span></span>
7. <span data-ttu-id="38c2a-188">Ange sedan ett namn i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="38c2a-188">In the **Name** field, enter a name.</span></span>
8. <span data-ttu-id="38c2a-189">I fältet **Värde** klistrar du in det slutpunktsvärde som du tidigare kopierade.</span><span class="sxs-lookup"><span data-stu-id="38c2a-189">In the **Value** field, paste the endpoint value that you copied earlier.</span></span>
9. <span data-ttu-id="38c2a-190">Markera **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="38c2a-190">Select **Create**.</span></span>

### <a name="save-the-redis-cache-connection-string-secret"></a><span data-ttu-id="38c2a-191">Spara hemligheten för Redis-cachens anslutningssträng</span><span class="sxs-lookup"><span data-stu-id="38c2a-191">Save the Redis cache connection string secret</span></span>

<span data-ttu-id="38c2a-192">Gör så här om du vill spara hemligheten för Redis-cachens anslutningssträng:</span><span class="sxs-lookup"><span data-stu-id="38c2a-192">To save the secret for the Redis cache connection string, follow these steps.</span></span>

1. <span data-ttu-id="38c2a-193">Markera Redis-cache-resursen bland dina resurser.</span><span class="sxs-lookup"><span data-stu-id="38c2a-193">In your resources, select the Redis cache resource.</span></span>
2. <span data-ttu-id="38c2a-194">Välj **Åtkomstnycklar**.</span><span class="sxs-lookup"><span data-stu-id="38c2a-194">Select **Access keys**.</span></span>
3. <span data-ttu-id="38c2a-195">Kopiera värdet i fältet **Primär anslutningssträng**.</span><span class="sxs-lookup"><span data-stu-id="38c2a-195">Copy the value in the **Primary connection string** field.</span></span>
4. <span data-ttu-id="38c2a-196">Gå till nyckelvalvsresursen.</span><span class="sxs-lookup"><span data-stu-id="38c2a-196">Go to the key vault resource.</span></span>
5. <span data-ttu-id="38c2a-197">I navigeringsfönstret till vänster välj er du **Hemligheter**.</span><span class="sxs-lookup"><span data-stu-id="38c2a-197">In the left navigation pane, select **Secrets**.</span></span>
6. <span data-ttu-id="38c2a-198">Välj **Generera/Importera**.</span><span class="sxs-lookup"><span data-stu-id="38c2a-198">Select **Generate/Import**.</span></span>
7. <span data-ttu-id="38c2a-199">Ange sedan ett namn i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="38c2a-199">In the **Name** field, enter a name.</span></span>
8. <span data-ttu-id="38c2a-200">I fältet **Värde** klistrar du in den anslutningssträng som du tidigare kopierade.</span><span class="sxs-lookup"><span data-stu-id="38c2a-200">In the **Value** field, paste the connection string that you copied earlier.</span></span>
9. <span data-ttu-id="38c2a-201">Markera **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="38c2a-201">Select **Create**.</span></span>

> [!NOTE]
> <span data-ttu-id="38c2a-202">När du uppdaterar en av anslutningssträngarna måste du också uppdatera de hemliga värdena.</span><span class="sxs-lookup"><span data-stu-id="38c2a-202">Whenever you update one of the connection strings, you must also update the secret values.</span></span>

<span data-ttu-id="38c2a-203">Du har nu slutfört etableringen av de nödvändiga Azure-resurserna.</span><span class="sxs-lookup"><span data-stu-id="38c2a-203">You've now finished provisioning the required Azure resources.</span></span> <span data-ttu-id="38c2a-204">Nästa steg är att [installera IoT-information-tillägget i Microsoft Dynamics Lifecycle Services (LCS)](iot-lcs-setup.md).</span><span class="sxs-lookup"><span data-stu-id="38c2a-204">The next step is to [install the IoT Intelligence add-in in Microsoft Dynamics Lifecycle Services (LCS)](iot-lcs-setup.md).</span></span>
