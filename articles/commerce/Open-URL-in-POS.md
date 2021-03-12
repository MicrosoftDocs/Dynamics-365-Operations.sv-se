---
title: Öppna URL i POS
description: Det här avsnittet innehåller en översikt över de förbättringar som har gjorts i produkt- och kundsökfunktionen i Dynamics 365 Commerce.
author: AamirAllaq
manager: AnnBe
ms.date: 01/28/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.custom: 141393
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2018-10-30
ms.dyn365.ops.version: 8.1.1
ms.openlocfilehash: e4ccb8e03d63a7bd1ab2d118d86633a8c6324d43
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4965462"
---
# <a name="open-url-in-pos"></a><span data-ttu-id="32eaa-103">Öppna webbadressen i POS</span><span class="sxs-lookup"><span data-stu-id="32eaa-103">Open URL in POS</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="32eaa-104">Det här avsnittet beskriver hur du konfigurerar en knapp i Butikskassa (PO) för att öppna en URL.</span><span class="sxs-lookup"><span data-stu-id="32eaa-104">This topic describes how you can configure a button in Retail point of sale (POS) to open a URL.</span></span> <span data-ttu-id="32eaa-105">Den här funktionen kräver inte en kodanpassning och kan konfigureras av en person i en roll som inte är utvecklare.</span><span class="sxs-lookup"><span data-stu-id="32eaa-105">This feature does not require a code customization, and can be configured by someone in a non-developer role.</span></span> 

<span data-ttu-id="32eaa-106">Den här funktionen används för att konfigurera en knapp i POS med hjälp av knappen rutnätsdesigner för att öppna en URL.</span><span class="sxs-lookup"><span data-stu-id="32eaa-106">This feature allows configuration of a button in POS, using the button grid designer to open a URL.</span></span> <span data-ttu-id="32eaa-107">För närvarande stöds detta följande konfigurationer:</span><span class="sxs-lookup"><span data-stu-id="32eaa-107">Currently, this is supported in the following configurations:</span></span>

- <span data-ttu-id="32eaa-108">Öppna i nytt fönster.</span><span class="sxs-lookup"><span data-stu-id="32eaa-108">Open in new window.</span></span>
- <span data-ttu-id="32eaa-109">Öppna i POS.</span><span class="sxs-lookup"><span data-stu-id="32eaa-109">Open within POS.</span></span>
- <span data-ttu-id="32eaa-110">Öppna en inbyggd app.</span><span class="sxs-lookup"><span data-stu-id="32eaa-110">Open a native app.</span></span>

## <a name="open-in-new-window"></a><span data-ttu-id="32eaa-111">Öppna i nytt fönster</span><span class="sxs-lookup"><span data-stu-id="32eaa-111">Open in new window</span></span>

<span data-ttu-id="32eaa-112">Den här konfigurationen definierar om du vill öppna URL i ett nytt fönster eller i appen.</span><span class="sxs-lookup"><span data-stu-id="32eaa-112">This configuration defines whether to open the URL in a new window or within the app.</span></span> <span data-ttu-id="32eaa-113">När du konfigurerar för att öppna en webbadress i appen visas sidonavigeringspanelen och det övre fältet av POS och är tillgängliga för användaren.</span><span class="sxs-lookup"><span data-stu-id="32eaa-113">When configured to open a web URL within the app, the side navigation panel and top bar of POS are visible and available for user interaction.</span></span> <span data-ttu-id="32eaa-114">När de konfigureras för att öppnas i ett nytt fönster öppnas URL i ett nytt appfönster i Modern POS för Windows och på en ny flik i webbläsaren i andra kassaklienter.</span><span class="sxs-lookup"><span data-stu-id="32eaa-114">When configured to open in a new window, the URL will open in a new app window on Modern POS for Windows, and in a new browser tab in all other POS clients.</span></span> <span data-ttu-id="32eaa-115">Om du vill aktivera detta måste du konfigurera URL med alternativet **Öppna i nytt fönster** markerat.</span><span class="sxs-lookup"><span data-stu-id="32eaa-115">To enable this, you must configure the URL with the **Open in new window** option selected.</span></span>

## <a name="open-within-pos"></a><span data-ttu-id="32eaa-116">Öppna i POS</span><span class="sxs-lookup"><span data-stu-id="32eaa-116">Open within POS</span></span>

<span data-ttu-id="32eaa-117">Öppna en URL i POS stöds för närvarande endast för Modern POS i Windows.</span><span class="sxs-lookup"><span data-stu-id="32eaa-117">Opening a web URL within POS is currently only supported for Modern POS on Windows.</span></span> <span data-ttu-id="32eaa-118">Den här funktionen är under utveckling för andra klienter och planeras släppas i framtida uppdateringar.</span><span class="sxs-lookup"><span data-stu-id="32eaa-118">On other clients, this capability is under development and planned for release in future updates.</span></span> <span data-ttu-id="32eaa-119">Om du vill aktivera detta måste du konfigurera URL med alternativet **Öppna i nytt fönster** inte markerat.</span><span class="sxs-lookup"><span data-stu-id="32eaa-119">To enable this, you must configure the URL with the **Open in new window** option not selected.</span></span>

## <a name="open-a-native-app"></a><span data-ttu-id="32eaa-120">Öppna en inbyggd app</span><span class="sxs-lookup"><span data-stu-id="32eaa-120">Open a native app</span></span>

<span data-ttu-id="32eaa-121">Den här funktionen låter dig också ange icke-URL om du vill öppna en inbyggd app.</span><span class="sxs-lookup"><span data-stu-id="32eaa-121">This feature also allows you to specify non-web URLs to open a native app.</span></span> <span data-ttu-id="32eaa-122">Du kan till exempel ange URL-protokoll såsom MailTo, SIP, IM eller MSTEAMS som sedan kan hanteras av respektive inbyggda appar på värdenheten.</span><span class="sxs-lookup"><span data-stu-id="32eaa-122">For example, you can specify URL protocols such as MailTo, SIP, IM, or MSTEAMS, which can then be handled by respective native apps on the host device.</span></span> <span data-ttu-id="32eaa-123">Om du vill aktivera detta måste du konfigurera URL med alternativet **Öppna i nytt fönster** markerat.</span><span class="sxs-lookup"><span data-stu-id="32eaa-123">To enable this, you must configure the URL with the **Open in new window** option selected.</span></span>

- <span data-ttu-id="32eaa-124">Windows-datorer finns i [Exportera eller importera standardassociationer för applikationer](https://docs.microsoft.com/windows-hardware/manufacture/desktop/export-or-import-default-application-associations) för att ange standardassociationer för protokollet om du ställer in datorn med Deployment Image Servicing and Management (DISM).</span><span class="sxs-lookup"><span data-stu-id="32eaa-124">For Windows computers, see [Export or Import Default Application Associations](https://docs.microsoft.com/windows-hardware/manufacture/desktop/export-or-import-default-application-associations) to set the default protocol associations if you are setting up your computer using Deployment Image Servicing and Management (DISM).</span></span>
- <span data-ttu-id="32eaa-125">Om du använder Mobile Device Manager, till exempel Intune för att hantera Windows-datorer, se [Policy CSP – ApplicationDefaults](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationdefaults).</span><span class="sxs-lookup"><span data-stu-id="32eaa-125">If you are using MDM, such as Intune to manage your Windows computers, see [Policy CSP - ApplicationDefaults](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationdefaults).</span></span>
- <span data-ttu-id="32eaa-126">Om du utvecklar en egen webbserver, se [Starta standardappen för en URI](https://docs.microsoft.com/windows/uwp/launch-resume/launch-default-app).</span><span class="sxs-lookup"><span data-stu-id="32eaa-126">If you are a developer building a custom website, see [Launch the default app for a URI](https://docs.microsoft.com/windows/uwp/launch-resume/launch-default-app).</span></span>

## <a name="open-a-native-app-seamlessly"></a><span data-ttu-id="32eaa-127">Öppna en inbyggd app sömlöst</span><span class="sxs-lookup"><span data-stu-id="32eaa-127">Open a native app seamlessly</span></span>

<span data-ttu-id="32eaa-128">Windows, iOS och Android tillåter också öppning av appar mer sömlöst utifrån association av approtokoll.</span><span class="sxs-lookup"><span data-stu-id="32eaa-128">Windows, iOS, and Android also allow opening of apps more seamlessly, based on app protocol association.</span></span> <span data-ttu-id="32eaa-129">Om din app inte redan är konfigurerad för att hantera att öppnas från en webbläsare kanske du behöver en utvecklare för att konfigurera detta.</span><span class="sxs-lookup"><span data-stu-id="32eaa-129">If your app is not already configured to handle opening from a web browser, you may need a developer to configure this.</span></span>

- <span data-ttu-id="32eaa-130">For Windows, se [Aktivera appar för webbplatser som använder app-URL-hanterare](https://docs.microsoft.com/windows/uwp/launch-resume/web-to-app-linking).</span><span class="sxs-lookup"><span data-stu-id="32eaa-130">For Windows, see [Enable apps for websites using app URI handlers](https://docs.microsoft.com/windows/uwp/launch-resume/web-to-app-linking).</span></span>
- <span data-ttu-id="32eaa-131">För iOS, se [Universella länkar för utvecklare](https://developer.apple.com/ios/universal-links/).</span><span class="sxs-lookup"><span data-stu-id="32eaa-131">For iOS, see [Universal Links for Developers](https://developer.apple.com/ios/universal-links/).</span></span>
- <span data-ttu-id="32eaa-132">För Android, se [Handling Android applänkar](https://developer.android.com/training/app-links/).</span><span class="sxs-lookup"><span data-stu-id="32eaa-132">For Android, see [Handling Android App Links](https://developer.android.com/training/app-links/).</span></span>

| <span data-ttu-id="32eaa-133">Klient</span><span class="sxs-lookup"><span data-stu-id="32eaa-133">Client</span></span>                | <span data-ttu-id="32eaa-134">Öppna i nytt fönster</span><span class="sxs-lookup"><span data-stu-id="32eaa-134">Open in new window</span></span> | <span data-ttu-id="32eaa-135">Öppna en inbyggd app</span><span class="sxs-lookup"><span data-stu-id="32eaa-135">Open native app</span></span> | <span data-ttu-id="32eaa-136">Öppna i POS</span><span class="sxs-lookup"><span data-stu-id="32eaa-136">Open within POS</span></span> | <span data-ttu-id="32eaa-137">Detaljer</span><span class="sxs-lookup"><span data-stu-id="32eaa-137">Details</span></span>                           |
|-----------------------|--------------------|-----------------|-----------------|-----------------------------------|
| <span data-ttu-id="32eaa-138">Modern POS på Windows</span><span class="sxs-lookup"><span data-stu-id="32eaa-138">Modern POS on Windows</span></span> | <span data-ttu-id="32eaa-139">✓\*</span><span class="sxs-lookup"><span data-stu-id="32eaa-139">✓\*</span></span>                | <span data-ttu-id="32eaa-140">✓</span><span class="sxs-lookup"><span data-stu-id="32eaa-140">✓</span></span>               | <span data-ttu-id="32eaa-141">✓</span><span class="sxs-lookup"><span data-stu-id="32eaa-141">✓</span></span>              | <span data-ttu-id="32eaa-142">\* Öppnas i ett nytt Modern POS-fönster</span><span class="sxs-lookup"><span data-stu-id="32eaa-142">\* Opens in new Modern POS window</span></span> |
| <span data-ttu-id="32eaa-143">Cloud POS</span><span class="sxs-lookup"><span data-stu-id="32eaa-143">Cloud POS</span></span>             | <span data-ttu-id="32eaa-144">✓\*</span><span class="sxs-lookup"><span data-stu-id="32eaa-144">✓\*</span></span>                | <span data-ttu-id="32eaa-145">✓</span><span class="sxs-lookup"><span data-stu-id="32eaa-145">✓</span></span>               | <span data-ttu-id="32eaa-146">X</span><span class="sxs-lookup"><span data-stu-id="32eaa-146">X</span></span>              | <span data-ttu-id="32eaa-147">\* Öppnar i en ny webbläsarflik</span><span class="sxs-lookup"><span data-stu-id="32eaa-147">\* Opens in new browser tab</span></span>        |
| <span data-ttu-id="32eaa-148">Modern POS på iOS</span><span class="sxs-lookup"><span data-stu-id="32eaa-148">Modern POS on iOS</span></span>     | <span data-ttu-id="32eaa-149">✓\*</span><span class="sxs-lookup"><span data-stu-id="32eaa-149">✓\*</span></span>                | <span data-ttu-id="32eaa-150">✓</span><span class="sxs-lookup"><span data-stu-id="32eaa-150">✓</span></span>               | <span data-ttu-id="32eaa-151">X</span><span class="sxs-lookup"><span data-stu-id="32eaa-151">X</span></span>              | <span data-ttu-id="32eaa-152">\* Öppnar i en ny webbläsarflik</span><span class="sxs-lookup"><span data-stu-id="32eaa-152">\* Opens in new browser tab</span></span>        |
| <span data-ttu-id="32eaa-153">Modern POS på Android</span><span class="sxs-lookup"><span data-stu-id="32eaa-153">Modern POS on Android</span></span> | <span data-ttu-id="32eaa-154">✓\*</span><span class="sxs-lookup"><span data-stu-id="32eaa-154">✓\*</span></span>                | <span data-ttu-id="32eaa-155">✓</span><span class="sxs-lookup"><span data-stu-id="32eaa-155">✓</span></span>               | <span data-ttu-id="32eaa-156">X</span><span class="sxs-lookup"><span data-stu-id="32eaa-156">X</span></span>              | <span data-ttu-id="32eaa-157">\* Öppnar i en ny webbläsarflik</span><span class="sxs-lookup"><span data-stu-id="32eaa-157">\* Opens in new browser tab</span></span>        |

## <a name="before-you-begin"></a><span data-ttu-id="32eaa-158">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="32eaa-158">Before you begin</span></span>

<span data-ttu-id="32eaa-159">Innan du börjar, gå igenom hur du konfigurerar [Skärmlayouter för kassa (POS)](pos-screen-layouts.md).</span><span class="sxs-lookup"><span data-stu-id="32eaa-159">Before you begin, review how to configure [Screen layouts for the point of sale (POS)](pos-screen-layouts.md).</span></span>

## <a name="open-url-in-pos"></a><span data-ttu-id="32eaa-160">Öppna URL i POS</span><span class="sxs-lookup"><span data-stu-id="32eaa-160">Open URL in POS</span></span>

<span data-ttu-id="32eaa-161">Gör följande om du vill konfigurera en URL-adress att öppnas i POS.</span><span class="sxs-lookup"><span data-stu-id="32eaa-161">To configure a URL to be opened in POS, perform the following steps.</span></span>

1. <span data-ttu-id="32eaa-162">I huvudkontor, gå till **Butik och handel \> Kanalinställningar \> Kassainställningar \> Kassa \> Skärmlayout**.</span><span class="sxs-lookup"><span data-stu-id="32eaa-162">In head office, go to **Retail and Commerce \> Channel Setup \> POS Setup \> POS \> Screen Layouts**.</span></span>
2. <span data-ttu-id="32eaa-163">Välj **Knappraster \> Designer**.</span><span class="sxs-lookup"><span data-stu-id="32eaa-163">Select **Button Grids \> Designer**.</span></span>
3. <span data-ttu-id="32eaa-164">Skapa en ny knapp.</span><span class="sxs-lookup"><span data-stu-id="32eaa-164">Create a new button.</span></span>
4. <span data-ttu-id="32eaa-165">Välj **Knappegenskaper**.</span><span class="sxs-lookup"><span data-stu-id="32eaa-165">Select **Button** properties.</span></span>
5. <span data-ttu-id="32eaa-166">Välj **Öppna URL** som åtgärd.</span><span class="sxs-lookup"><span data-stu-id="32eaa-166">Select **Open URL** as the action.</span></span>
6. <span data-ttu-id="32eaa-167">Ange den URL som du vill använda.</span><span class="sxs-lookup"><span data-stu-id="32eaa-167">Enter the URL that you want to use.</span></span>
7. <span data-ttu-id="32eaa-168">Konfigurera om du vill öppna URL i ett nytt fönster.</span><span class="sxs-lookup"><span data-stu-id="32eaa-168">Configure whether to open the URL in a new window.</span></span>
