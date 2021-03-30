---
title: Lägga till skriptkod på webbsidor för att stödja telemetri
description: I det här avsnittet beskrivs hur du lägger till skriptkod på klientsidan på webbplatssidorna för att stödja insamling av telemetri på klientsidan.
author: bicyclingfool
manager: annbe
ms.date: 09/29/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: e035c767474cba19c3a31eafdefb08b422b564ba
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5209213"
---
# <a name="add-script-code-to-site-pages-to-support-telemetry"></a><span data-ttu-id="005e4-103">Lägga till skriptkod på webbsidor för att stödja telemetri</span><span class="sxs-lookup"><span data-stu-id="005e4-103">Add script code to site pages to support telemetry</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="005e4-104">I det här avsnittet beskrivs hur du lägger till skriptkod på klientsidan på webbplatssidorna för att stödja insamling av telemetri på klientsidan.</span><span class="sxs-lookup"><span data-stu-id="005e4-104">This topic describes how to add client-side script code to your site pages to support the collection of client-side telemetry.</span></span>

## <a name="overview"></a><span data-ttu-id="005e4-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="005e4-105">Overview</span></span>

<span data-ttu-id="005e4-106">Webbanalys är ett viktigt verktyg när du vill förstå hur dina kunder samverkar med din webbplats och fatta beslut som hjälper dig att optimera upplevelsen för maximal konvertering.</span><span class="sxs-lookup"><span data-stu-id="005e4-106">Web analytics are an essential tool when you want to understand how your customers interact with your site and make decisions that will help optimize the experience for maximum conversion.</span></span> <span data-ttu-id="005e4-107">Det finns många webbanalyspaket som hjälper dig att uppnå dessa mål, t.ex. Google Analytics, Clicky, Moz Analytics och KISSMetrics.</span><span class="sxs-lookup"><span data-stu-id="005e4-107">Many web analytics packages are available to help you achieve these goals, such as Google Analytics, Clicky, Moz Analytics, and KISSMetrics.</span></span> <span data-ttu-id="005e4-108">De flesta webbanalyspaketen kräver att du lägger till klientskriptkod i elementet **\<head\>** för HTML på alla sidor på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="005e4-108">Most web analytics packages require that you add client-side script code in the **\<head\>** element of the HTML for all pages of your site.</span></span>

> [!NOTE]
> <span data-ttu-id="005e4-109">Instruktionerna i det här avsnittet gäller även andra anpassade klientfunktioner som Microsoft Dynamics 365 Commerce inte erbjuder.</span><span class="sxs-lookup"><span data-stu-id="005e4-109">The instructions in this topic also apply to other custom client-side functionality that Microsoft Dynamics 365 Commerce doesn't natively offer.</span></span>

## <a name="create-a-reusable-fragment-for-your-script-code"></a><span data-ttu-id="005e4-110">Skapa ett återanvändbart fragment för skriptkoden</span><span class="sxs-lookup"><span data-stu-id="005e4-110">Create a reusable fragment for your script code</span></span>

<span data-ttu-id="005e4-111">Med hjälp av ett fragment kan du återanvända en infogad eller extern skriptkod på alla sidor på din webbplats, oavsett vilken mall de använder.</span><span class="sxs-lookup"><span data-stu-id="005e4-111">A fragment allows you to reuse inline or external script code across all pages on your site, regardless of the template they use.</span></span>

### <a name="create-a-reusable-fragment-for-your-inline-script-code"></a><span data-ttu-id="005e4-112">Skapa ett återanvändbart fragment för den infogade skriptkoden</span><span class="sxs-lookup"><span data-stu-id="005e4-112">Create a reusable fragment for your inline script code</span></span>

<span data-ttu-id="005e4-113">Om du vill skapa ett återanvändbart fragment för den infogade skriptoden i webbplatsskaparen följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="005e4-113">To create a reusable fragment for your inline script code in site builder, follow these steps.</span></span>

1. <span data-ttu-id="005e4-114">Gå till **Fragment** och välj sedan **Nytt**.</span><span class="sxs-lookup"><span data-stu-id="005e4-114">Go to **Fragments**, and then select **New**.</span></span>
1. <span data-ttu-id="005e4-115">I dialogrutan **Nytt fragment** välj **infogat skript**.</span><span class="sxs-lookup"><span data-stu-id="005e4-115">In the **New fragment** dialog box, select **Inline script**.</span></span>
1. <span data-ttu-id="005e4-116">Under **fragmentets namn**, anger du ett namn på fragmentet och klickar sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="005e4-116">Under **Fragment name**, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="005e4-117">Under det fragment som du har skapat väljer du modulen **infogat standardskript**.</span><span class="sxs-lookup"><span data-stu-id="005e4-117">Under the fragment that you created, select the **Default inline script** module.</span></span>
1. <span data-ttu-id="005e4-118">Ange skript på klientsidan i egenskapsrutan till höger under **infogat skript**.</span><span class="sxs-lookup"><span data-stu-id="005e4-118">In the property pane on the right, under **Inline script**, enter your client-side script.</span></span> <span data-ttu-id="005e4-119">Konfigurera sedan andra alternativ som du behöver.</span><span class="sxs-lookup"><span data-stu-id="005e4-119">Then configure other options as you require.</span></span>
1. <span data-ttu-id="005e4-120">Välj **spara** och välj sedan **Avsluta redigeringen**.</span><span class="sxs-lookup"><span data-stu-id="005e4-120">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="005e4-121">Markera **Publicera**.</span><span class="sxs-lookup"><span data-stu-id="005e4-121">Select **Publish**.</span></span>

### <a name="create-a-reusable-fragment-for-your-external-script-code"></a><span data-ttu-id="005e4-122">Skapa ett återanvändbart fragment för den externa skriptkoden</span><span class="sxs-lookup"><span data-stu-id="005e4-122">Create a reusable fragment for your external script code</span></span>

<span data-ttu-id="005e4-123">Om du vill skapa ett återanvändbart fragment för den externa skripkoden i webbplatsskaparen följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="005e4-123">To create a reusable fragment for your external script code in site builder, follow these steps.</span></span>

1. <span data-ttu-id="005e4-124">Gå till **Fragment** och välj sedan **Nytt**.</span><span class="sxs-lookup"><span data-stu-id="005e4-124">Go to **Fragments**, and then select **New**.</span></span>
1. <span data-ttu-id="005e4-125">I dialogrutan **Nytt fragment** välj **externt skript**.</span><span class="sxs-lookup"><span data-stu-id="005e4-125">In the **New fragment** dialog box, select **External script**.</span></span>
1. <span data-ttu-id="005e4-126">Under **fragmentets namn**, anger du ett namn på fragmentet och klickar sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="005e4-126">Under **Fragment name**, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="005e4-127">Under det fragment som du har skapat väljer du modulen **externt standardskript**.</span><span class="sxs-lookup"><span data-stu-id="005e4-127">Under the fragment that you created, select the **Default external script** module.</span></span>
1. <span data-ttu-id="005e4-128">I egenskapsrutan till höger, under **Skriptkälla**, lägg till en extern eller relativ URL för den externa skriptkällan.</span><span class="sxs-lookup"><span data-stu-id="005e4-128">In the property pane on the right, under **Script source**, add an external or relative URL for the external script source.</span></span> <span data-ttu-id="005e4-129">Konfigurera sedan andra alternativ som du behöver.</span><span class="sxs-lookup"><span data-stu-id="005e4-129">Then configure other options as you require.</span></span>
1. <span data-ttu-id="005e4-130">Välj **spara** och välj sedan **Avsluta redigeringen**.</span><span class="sxs-lookup"><span data-stu-id="005e4-130">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="005e4-131">Markera **Publicera**.</span><span class="sxs-lookup"><span data-stu-id="005e4-131">Select **Publish**.</span></span>

> [!NOTE]
> <span data-ttu-id="005e4-132">Om säkerhetsprincip (CSP) för innehåll är aktiverad för din webbplats måste du se till att alla externa URL:er läggs till i CSP-direktivet **skript-src** i Commerce-webbplatsbyggaren.</span><span class="sxs-lookup"><span data-stu-id="005e4-132">If content security policy (CSP) is enabled for your site, ensure that all external URLs are added to the **script-src** CSP directive in Commerce site builder.</span></span> <span data-ttu-id="005e4-133">Mer information finns i [hantera säkerhetsprinciper för innehåll (CSP)](manage-csp.md).</span><span class="sxs-lookup"><span data-stu-id="005e4-133">For more information, see [Manage Content Security Policy (CSP)](manage-csp.md).</span></span>

## <a name="add-a-fragment-that-includes-script-code-to-a-template"></a><span data-ttu-id="005e4-134">Lägga till ett fragment som innehåller skriptkod i en mall</span><span class="sxs-lookup"><span data-stu-id="005e4-134">Add a fragment that includes script code to a template</span></span>

<span data-ttu-id="005e4-135">Följ dessa steg för att lägga till ett fragment som innehåller skriptkod till en mall i webbplatsbyggaren.</span><span class="sxs-lookup"><span data-stu-id="005e4-135">To add a fragment that includes script code to a template in site builder, follow these steps.</span></span>

1. <span data-ttu-id="005e4-136">Gå till **mallarna** och öppna mallen för sidorna som du vill lägga till skriptkoden i.</span><span class="sxs-lookup"><span data-stu-id="005e4-136">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
1. <span data-ttu-id="005e4-137">I det vänstra fönstret expanderar du mallstrukturlistan så att platsen **HTML-huvud** visas.</span><span class="sxs-lookup"><span data-stu-id="005e4-137">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
1. <span data-ttu-id="005e4-138">På platsen **HTML-huvud** markera knappen med punkter (**...**) och välj sedan **Lägg till fragment**.</span><span class="sxs-lookup"><span data-stu-id="005e4-138">In the **HTML Head** slot, select the ellipsis button (**...**), and then select **Add fragment**.</span></span>
1. <span data-ttu-id="005e4-139">Markera det fragment som du har skapat för skriptkoden.</span><span class="sxs-lookup"><span data-stu-id="005e4-139">Select the fragment that you created for your script code.</span></span>
1. <span data-ttu-id="005e4-140">Välj **spara** och välj sedan **Avsluta redigeringen**.</span><span class="sxs-lookup"><span data-stu-id="005e4-140">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="005e4-141">Markera **Publicera**.</span><span class="sxs-lookup"><span data-stu-id="005e4-141">Select **Publish**.</span></span>

## <a name="add-an-external-script-or-inline-script-directly-to-a-template"></a><span data-ttu-id="005e4-142">Lägga till ett externt skript eller infogat skript direkt i en mall</span><span class="sxs-lookup"><span data-stu-id="005e4-142">Add an external script or inline script directly to a template</span></span>

<span data-ttu-id="005e4-143">Om du vill infoga ett infogat eller externt skript direkt på en uppsättning sidor som kontrolleras av en enskild mall, behöver du inte skapa ett fragment först.</span><span class="sxs-lookup"><span data-stu-id="005e4-143">If you want to insert an inline or external script directly into a set of pages that are controlled by a single template, you don't have to create a fragment first.</span></span>

### <a name="add-an-inline-script-directly-to-a-template"></a><span data-ttu-id="005e4-144">Lägga till ett infogat skript direkt i en mall</span><span class="sxs-lookup"><span data-stu-id="005e4-144">Add an inline script directly to a template</span></span>

<span data-ttu-id="005e4-145">Om du vill lägga till ett infogat skript direkt på en mall i webbplatsskaparen följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="005e4-145">To add an inline script directly to a template in site builder, follow these steps.</span></span>

1. <span data-ttu-id="005e4-146">Gå till **mallarna** och öppna mallen för sidorna som du vill lägga till skriptkoden i.</span><span class="sxs-lookup"><span data-stu-id="005e4-146">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
1. <span data-ttu-id="005e4-147">I det vänstra fönstret expanderar du mallstrukturlistan så att platsen **HTML-huvud** visas.</span><span class="sxs-lookup"><span data-stu-id="005e4-147">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
1. <span data-ttu-id="005e4-148">I facket **HTML-huvud** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.</span><span class="sxs-lookup"><span data-stu-id="005e4-148">In the **HTML Head** slot, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="005e4-149">I dialogrutan **Lägg till modul** välj **infogat skript**.</span><span class="sxs-lookup"><span data-stu-id="005e4-149">In the **Add Module** dialog box, select **Inline script**.</span></span>
1. <span data-ttu-id="005e4-150">Ange skript på klientsidan i egenskapsrutan till höger under **infogat skript**.</span><span class="sxs-lookup"><span data-stu-id="005e4-150">In the property pane on the right, under **Inline script**, enter your client-side script.</span></span> <span data-ttu-id="005e4-151">Konfigurera sedan andra alternativ som du behöver.</span><span class="sxs-lookup"><span data-stu-id="005e4-151">Then configure other options as you require.</span></span>
1. <span data-ttu-id="005e4-152">Välj **spara** och välj sedan **Avsluta redigeringen**.</span><span class="sxs-lookup"><span data-stu-id="005e4-152">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="005e4-153">Markera **Publicera**.</span><span class="sxs-lookup"><span data-stu-id="005e4-153">Select **Publish**.</span></span>

### <a name="add-an-external-script-directly-to-a-template"></a><span data-ttu-id="005e4-154">Lägga till ett externt skript direkt i en mall</span><span class="sxs-lookup"><span data-stu-id="005e4-154">Add an external script directly to a template</span></span>

<span data-ttu-id="005e4-155">Om du vill lägga till ett extern skript direkt på en mall i webbplatsskaparen följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="005e4-155">To add an external script directly to a template in site builder, follow these steps.</span></span>

1. <span data-ttu-id="005e4-156">Gå till **mallarna** och öppna mallen för sidorna som du vill lägga till skriptkoden i.</span><span class="sxs-lookup"><span data-stu-id="005e4-156">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
1. <span data-ttu-id="005e4-157">I det vänstra fönstret expanderar du mallstrukturlistan så att platsen **HTML-huvud** visas.</span><span class="sxs-lookup"><span data-stu-id="005e4-157">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
1. <span data-ttu-id="005e4-158">I facket **HTML-huvud** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.</span><span class="sxs-lookup"><span data-stu-id="005e4-158">In the **HTML Head** slot, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="005e4-159">I dialogrutan **Lägg till modul** välj **externt skript**.</span><span class="sxs-lookup"><span data-stu-id="005e4-159">In the **Add Module** dialog box, select **External script**.</span></span>
1. <span data-ttu-id="005e4-160">I egenskapsrutan till höger, under **Skriptkälla**, lägg till en extern eller relativ URL för den externa skriptkällan.</span><span class="sxs-lookup"><span data-stu-id="005e4-160">In the property pane on the right, under **Script source**, add an external or relative URL for the external script source.</span></span> <span data-ttu-id="005e4-161">Konfigurera sedan andra alternativ som du behöver.</span><span class="sxs-lookup"><span data-stu-id="005e4-161">Then configure other options as you require.</span></span>
1. <span data-ttu-id="005e4-162">Välj **spara** och välj sedan **Avsluta redigeringen**.</span><span class="sxs-lookup"><span data-stu-id="005e4-162">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="005e4-163">Markera **Publicera**.</span><span class="sxs-lookup"><span data-stu-id="005e4-163">Select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="005e4-164">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="005e4-164">Additional resources</span></span>

[<span data-ttu-id="005e4-165">Lägga till en logotyp</span><span class="sxs-lookup"><span data-stu-id="005e4-165">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="005e4-166">Välja ett tema för webbplatsen</span><span class="sxs-lookup"><span data-stu-id="005e4-166">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="005e4-167">Arbeta med CSS åsidosättningsfiler</span><span class="sxs-lookup"><span data-stu-id="005e4-167">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="005e4-168">Lägg till en favoritikon</span><span class="sxs-lookup"><span data-stu-id="005e4-168">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="005e4-169">Lägg till ett välkomstmeddelande</span><span class="sxs-lookup"><span data-stu-id="005e4-169">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="005e4-170">Lägg till copyrightmeddelande</span><span class="sxs-lookup"><span data-stu-id="005e4-170">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="005e4-171">Lägg till språk på din webbplats</span><span class="sxs-lookup"><span data-stu-id="005e4-171">Add languages to your site</span></span>](add-languages-to-site.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]