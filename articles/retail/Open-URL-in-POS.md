---
title: Öppna URL i kassan
description: Det här avsnittet innehåller en översikt över de förbättringar som har gjorts i produkt- och kundsökfunktionen i Microsoft Dynamics 365 for Retail.
author: AamirAllaq
manager: AnnBe
ms.date: 01/28/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 141393
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2018-10-30
ms.dyn365.ops.version: 8.1.1
ms.openlocfilehash: 729caf9fad9097a3ecbf7d546c8f8a96f67aec92
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2019
ms.locfileid: "1845700"
---
# <a name="open-url-in-pos"></a><span data-ttu-id="fe14e-103">Öppna webbadressen i kassan</span><span class="sxs-lookup"><span data-stu-id="fe14e-103">Open URL in POS</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="fe14e-104">Det här avsnittet beskriver hur du konfigurerar en knapp i Butikskassa (PO) för att öppna en URL.</span><span class="sxs-lookup"><span data-stu-id="fe14e-104">This topic describes how you can configure a button in Retail point of sale (POS) to open a URL.</span></span> <span data-ttu-id="fe14e-105">Den här funktionen kräver inte en kodanpassning och kan konfigureras av en person i en roll som inte är utvecklare.</span><span class="sxs-lookup"><span data-stu-id="fe14e-105">This feature does not require a code customization, and can be configured by someone in a non-developer role.</span></span> <span data-ttu-id="fe14e-106">Den här funktionen är tillgänglig som en del av den Dynamics 365 for Finance and Operations version 8.1.3 versionen (build 8.1.227.10014) och senare.</span><span class="sxs-lookup"><span data-stu-id="fe14e-106">This feature is available as part of the Dynamics 365 for Finance and Operations version 8.1.3 release (build 8.1.227.10014) and later.</span></span> 

<span data-ttu-id="fe14e-107">Den här funktionen används för att konfigurera en knapp i kassan med hjälp av knappen rutnätsdesigner för att öppna en URL.</span><span class="sxs-lookup"><span data-stu-id="fe14e-107">This feature allows configuration of a button in POS, using the button grid designer to open a URL.</span></span> <span data-ttu-id="fe14e-108">För närvarande stöds detta följande konfigurationer:</span><span class="sxs-lookup"><span data-stu-id="fe14e-108">Currently, this is supported in the following configurations:</span></span>

- <span data-ttu-id="fe14e-109">Öppna i nytt fönster.</span><span class="sxs-lookup"><span data-stu-id="fe14e-109">Open in new window.</span></span>
- <span data-ttu-id="fe14e-110">Öppna i kassan.</span><span class="sxs-lookup"><span data-stu-id="fe14e-110">Open within POS.</span></span>
- <span data-ttu-id="fe14e-111">Öppna en inbyggd app.</span><span class="sxs-lookup"><span data-stu-id="fe14e-111">Open a native app.</span></span>

## <a name="open-in-new-window"></a><span data-ttu-id="fe14e-112">Öppna i nytt fönster</span><span class="sxs-lookup"><span data-stu-id="fe14e-112">Open in new window</span></span>

<span data-ttu-id="fe14e-113">Den här konfigurationen definierar om du vill öppna URL i ett nytt fönster eller i appen.</span><span class="sxs-lookup"><span data-stu-id="fe14e-113">This configuration defines whether to open the URL in a new window or within the app.</span></span> <span data-ttu-id="fe14e-114">När du konfigurerar för att öppna en webbadress i appen visas sidonavigeringspanelen och det övre fältet av kassan och är tillgängliga för användaren.</span><span class="sxs-lookup"><span data-stu-id="fe14e-114">When configured to open a web URL within the app, the side navigation panel and top bar of POS are visible and available for user interaction.</span></span> <span data-ttu-id="fe14e-115">När de konfigureras för att öppnas i ett nytt fönster öppnas URL i ett nytt appfönster i Modern POS för Windows och på en ny flik i webbläsaren i andra kassaklienter.</span><span class="sxs-lookup"><span data-stu-id="fe14e-115">When configured to open in a new window, the URL will open in a new app window on Modern POS for Windows, and in a new browser tab in all other POS clients.</span></span> <span data-ttu-id="fe14e-116">Om du vill aktivera detta måste du konfigurera URL med alternativet **Öppna i nytt fönster** markerat.</span><span class="sxs-lookup"><span data-stu-id="fe14e-116">To enable this, you must configure the URL with the **Open in new window** option selected.</span></span>

## <a name="open-within-pos"></a><span data-ttu-id="fe14e-117">Öppna i kassan</span><span class="sxs-lookup"><span data-stu-id="fe14e-117">Open within POS</span></span>

<span data-ttu-id="fe14e-118">Öppna en URL i kassan stöds för närvarande endast för Modern POS i Windows.</span><span class="sxs-lookup"><span data-stu-id="fe14e-118">Opening a web URL within POS is currently only supported for Modern POS on Windows.</span></span> <span data-ttu-id="fe14e-119">Den här funktionen är under utveckling för andra klienter och planeras släppas i framtida uppdateringar.</span><span class="sxs-lookup"><span data-stu-id="fe14e-119">On other clients, this capability is under development and planned for release in future updates.</span></span> <span data-ttu-id="fe14e-120">Om du vill aktivera detta måste du konfigurera URL med alternativet **Öppna i nytt fönster** inte markerat.</span><span class="sxs-lookup"><span data-stu-id="fe14e-120">To enable this, you must configure the URL with the **Open in new window** option not selected.</span></span>

## <a name="open-a-native-app"></a><span data-ttu-id="fe14e-121">Öppna en inbyggd app</span><span class="sxs-lookup"><span data-stu-id="fe14e-121">Open a native app</span></span>

<span data-ttu-id="fe14e-122">Den här funktionen låter dig också ange icke-URL om du vill öppna en inbyggd app.</span><span class="sxs-lookup"><span data-stu-id="fe14e-122">This feature also allows you to specify non-web URLs to open a native app.</span></span> <span data-ttu-id="fe14e-123">Du kan till exempel ange URL-protokoll såsom MailTo, SIP, IM eller MSTEAMS som sedan kan hanteras av respektive inbyggda appar på värdenheten.</span><span class="sxs-lookup"><span data-stu-id="fe14e-123">For example, you can specify URL protocols such as MailTo, SIP, IM, or MSTEAMS, which can then be handled by respective native apps on the host device.</span></span> <span data-ttu-id="fe14e-124">Om du vill aktivera detta måste du konfigurera URL med alternativet **Öppna i nytt fönster** markerat.</span><span class="sxs-lookup"><span data-stu-id="fe14e-124">To enable this, you must configure the URL with the **Open in new window** option selected.</span></span>

- <span data-ttu-id="fe14e-125">Windows-datorer finns i [Exportera eller importera standardassociationer för applikationer](https://docs.microsoft.com/windows-hardware/manufacture/desktop/export-or-import-default-application-associations) för att ange standardassociationer för protokollet om du ställer in datorn med Deployment Image Servicing and Management (DISM).</span><span class="sxs-lookup"><span data-stu-id="fe14e-125">For Windows computers, see [Export or Import Default Application Associations](https://docs.microsoft.com/windows-hardware/manufacture/desktop/export-or-import-default-application-associations) to set the default protocol associations if you are setting up your computer using Deployment Image Servicing and Management (DISM).</span></span>
- <span data-ttu-id="fe14e-126">Om du använder Mobile Device Manager, till exempel Intune för att hantera Windows-datorer, se [Policy CSP - ApplicationDefaults](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationdefaults).</span><span class="sxs-lookup"><span data-stu-id="fe14e-126">If you are using MDM, such as Intune to manage your Windows computers, see [Policy CSP - ApplicationDefaults](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-applicationdefaults).</span></span>
- <span data-ttu-id="fe14e-127">Om du utvecklar en egen webbserver, se [Starta standardappen för en URI](https://docs.microsoft.com/windows/uwp/launch-resume/launch-default-app).</span><span class="sxs-lookup"><span data-stu-id="fe14e-127">If you are a developer building a custom website, see [Launch the default app for a URI](https://docs.microsoft.com/windows/uwp/launch-resume/launch-default-app).</span></span>

## <a name="open-a-native-app-seamlessly"></a><span data-ttu-id="fe14e-128">Öppna en inbyggd app sömlöst</span><span class="sxs-lookup"><span data-stu-id="fe14e-128">Open a native app seamlessly</span></span>

<span data-ttu-id="fe14e-129">Windows, iOS och Android tillåter också öppning av appar mer sömlöst utifrån association av approtokoll.</span><span class="sxs-lookup"><span data-stu-id="fe14e-129">Windows, iOS, and Android also allow opening of apps more seamlessly, based on app protocol association.</span></span> <span data-ttu-id="fe14e-130">Om din app inte redan är konfigurerad för att hantera att öppnas från en webbläsare kanske du behöver en utvecklare för att konfigurera detta.</span><span class="sxs-lookup"><span data-stu-id="fe14e-130">If your app is not already configured to handle opening from a web browser, you may need a developer to configure this.</span></span>

- <span data-ttu-id="fe14e-131">For Windows, se [Aktivera appar för webbplatser som använder app-URL-hanterare](https://docs.microsoft.com/windows/uwp/launch-resume/web-to-app-linking).</span><span class="sxs-lookup"><span data-stu-id="fe14e-131">For Windows, see [Enable apps for websites using app URI handlers](https://docs.microsoft.com/windows/uwp/launch-resume/web-to-app-linking).</span></span>
- <span data-ttu-id="fe14e-132">För iOS, se [Universella länkar för utvecklare](https://developer.apple.com/ios/universal-links/).</span><span class="sxs-lookup"><span data-stu-id="fe14e-132">For iOS, see [Universal Links for Developers](https://developer.apple.com/ios/universal-links/).</span></span>
- <span data-ttu-id="fe14e-133">För Android, se [Handling Android applänkar](https://developer.android.com/training/app-links/).</span><span class="sxs-lookup"><span data-stu-id="fe14e-133">For Android, see [Handling Android App Links](https://developer.android.com/training/app-links/).</span></span>

| <span data-ttu-id="fe14e-134">Klient</span><span class="sxs-lookup"><span data-stu-id="fe14e-134">Client</span></span>                | <span data-ttu-id="fe14e-135">Öppna i nytt fönster</span><span class="sxs-lookup"><span data-stu-id="fe14e-135">Open in new window</span></span> | <span data-ttu-id="fe14e-136">Öppna en inbyggd app</span><span class="sxs-lookup"><span data-stu-id="fe14e-136">Open native app</span></span> | <span data-ttu-id="fe14e-137">Öppna i kassan</span><span class="sxs-lookup"><span data-stu-id="fe14e-137">Open within POS</span></span> | <span data-ttu-id="fe14e-138">Detaljer</span><span class="sxs-lookup"><span data-stu-id="fe14e-138">Details</span></span>                           |
|-----------------------|--------------------|-----------------|-----------------|-----------------------------------|
| <span data-ttu-id="fe14e-139">Modern POS på Windows</span><span class="sxs-lookup"><span data-stu-id="fe14e-139">Modern POS on Windows</span></span> | <span data-ttu-id="fe14e-140">✓\*</span><span class="sxs-lookup"><span data-stu-id="fe14e-140">✓\*</span></span>                | <span data-ttu-id="fe14e-141">✓</span><span class="sxs-lookup"><span data-stu-id="fe14e-141">✓</span></span>               | <span data-ttu-id="fe14e-142">✓</span><span class="sxs-lookup"><span data-stu-id="fe14e-142">✓</span></span>              | <span data-ttu-id="fe14e-143">\* Öppnas i ett nytt Modern POS-fönster</span><span class="sxs-lookup"><span data-stu-id="fe14e-143">\* Opens in new Modern POS window</span></span> |
| <span data-ttu-id="fe14e-144">Cloud POS</span><span class="sxs-lookup"><span data-stu-id="fe14e-144">Cloud POS</span></span>             | <span data-ttu-id="fe14e-145">✓\*</span><span class="sxs-lookup"><span data-stu-id="fe14e-145">✓\*</span></span>                | <span data-ttu-id="fe14e-146">✓</span><span class="sxs-lookup"><span data-stu-id="fe14e-146">✓</span></span>               | <span data-ttu-id="fe14e-147">X</span><span class="sxs-lookup"><span data-stu-id="fe14e-147">X</span></span>              | <span data-ttu-id="fe14e-148">\* Öppnar i en ny webbläsarflik</span><span class="sxs-lookup"><span data-stu-id="fe14e-148">\* Opens in new browser tab</span></span>        |
| <span data-ttu-id="fe14e-149">Modern POS på iOS</span><span class="sxs-lookup"><span data-stu-id="fe14e-149">Modern POS on iOS</span></span>     | <span data-ttu-id="fe14e-150">✓\*</span><span class="sxs-lookup"><span data-stu-id="fe14e-150">✓\*</span></span>                | <span data-ttu-id="fe14e-151">✓</span><span class="sxs-lookup"><span data-stu-id="fe14e-151">✓</span></span>               | <span data-ttu-id="fe14e-152">X</span><span class="sxs-lookup"><span data-stu-id="fe14e-152">X</span></span>              | <span data-ttu-id="fe14e-153">\* Öppnar i en ny webbläsarflik</span><span class="sxs-lookup"><span data-stu-id="fe14e-153">\* Opens in new browser tab</span></span>        |
| <span data-ttu-id="fe14e-154">Modern POS på Android</span><span class="sxs-lookup"><span data-stu-id="fe14e-154">Modern POS on Android</span></span> | <span data-ttu-id="fe14e-155">✓\*</span><span class="sxs-lookup"><span data-stu-id="fe14e-155">✓\*</span></span>                | <span data-ttu-id="fe14e-156">✓</span><span class="sxs-lookup"><span data-stu-id="fe14e-156">✓</span></span>               | <span data-ttu-id="fe14e-157">X</span><span class="sxs-lookup"><span data-stu-id="fe14e-157">X</span></span>              | <span data-ttu-id="fe14e-158">\* Öppnar i en ny webbläsarflik</span><span class="sxs-lookup"><span data-stu-id="fe14e-158">\* Opens in new browser tab</span></span>        |

## <a name="before-you-begin"></a><span data-ttu-id="fe14e-159">Innan du börjar</span><span class="sxs-lookup"><span data-stu-id="fe14e-159">Before you begin</span></span>

<span data-ttu-id="fe14e-160">Innan du börjar, gå igenom hur du konfigurerar [Skärmlayouter för kassa (POS)](pos-screen-layouts.md).</span><span class="sxs-lookup"><span data-stu-id="fe14e-160">Before you begin, review how to configure [Screen layouts for the point of sale (POS)](pos-screen-layouts.md).</span></span>

## <a name="open-url-in-pos"></a><span data-ttu-id="fe14e-161">Öppna URL i kassan</span><span class="sxs-lookup"><span data-stu-id="fe14e-161">Open URL in POS</span></span>

<span data-ttu-id="fe14e-162">Gör följande om du vill konfigurera en URL-adress att öppnas i kassan.</span><span class="sxs-lookup"><span data-stu-id="fe14e-162">To configure a URL to be opened in POS, perform the following steps.</span></span>

1. <span data-ttu-id="fe14e-163">I huvudkontor, gå till **Retail \> Kanalinställningar \> Kassainställningar \> Kassa \> Skärmlayout**.</span><span class="sxs-lookup"><span data-stu-id="fe14e-163">In head office, go to **Retail \> Channel Setup \> POS Setup \> POS \> Screen Layouts**.</span></span>
2. <span data-ttu-id="fe14e-164">Välj **Knappraster \> Designer**.</span><span class="sxs-lookup"><span data-stu-id="fe14e-164">Select **Button Grids \> Designer**.</span></span>
3. <span data-ttu-id="fe14e-165">Skapa en ny knapp.</span><span class="sxs-lookup"><span data-stu-id="fe14e-165">Create a new button.</span></span>
4. <span data-ttu-id="fe14e-166">Välj **Knappegenskaper**.</span><span class="sxs-lookup"><span data-stu-id="fe14e-166">Select **Button** properties.</span></span>
5. <span data-ttu-id="fe14e-167">Välj **Öppna URL** som åtgärd.</span><span class="sxs-lookup"><span data-stu-id="fe14e-167">Select **Open URL** as the action.</span></span>
6. <span data-ttu-id="fe14e-168">Ange den URL som du vill använda.</span><span class="sxs-lookup"><span data-stu-id="fe14e-168">Enter the URL that you want to use.</span></span>
7. <span data-ttu-id="fe14e-169">Konfigurera om du vill öppna URL i ett nytt fönster.</span><span class="sxs-lookup"><span data-stu-id="fe14e-169">Configure whether to open the URL in a new window.</span></span>
