---
title: Lägga till skriptkod på webbsidor för att stödja telemetri
description: I det här avsnittet beskrivs hur du lägger till skriptkod på klientsidan på webbplatssidorna för att stödja insamling av telemetri på klientsidan.
author: bicyclingfool
ms.date: 09/29/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: fb1773ab10b23a586eb6a8286f145181818585b9
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797441"
---
# <a name="add-script-code-to-site-pages-to-support-telemetry"></a><span data-ttu-id="8de29-103">Lägga till skriptkod på webbsidor för att stödja telemetri</span><span class="sxs-lookup"><span data-stu-id="8de29-103">Add script code to site pages to support telemetry</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="8de29-104">I det här avsnittet beskrivs hur du lägger till skriptkod på klientsidan på webbplatssidorna för att stödja insamling av telemetri på klientsidan.</span><span class="sxs-lookup"><span data-stu-id="8de29-104">This topic describes how to add client-side script code to your site pages to support the collection of client-side telemetry.</span></span>

<span data-ttu-id="8de29-105">Webbanalys är ett viktigt verktyg när du vill förstå hur dina kunder samverkar med din webbplats och fatta beslut som hjälper dig att optimera upplevelsen för maximal konvertering.</span><span class="sxs-lookup"><span data-stu-id="8de29-105">Web analytics are an essential tool when you want to understand how your customers interact with your site and make decisions that will help optimize the experience for maximum conversion.</span></span> <span data-ttu-id="8de29-106">Det finns många webbanalyspaket som hjälper dig att uppnå dessa mål, t.ex. Google Analytics, Clicky, Moz Analytics och KISSMetrics.</span><span class="sxs-lookup"><span data-stu-id="8de29-106">Many web analytics packages are available to help you achieve these goals, such as Google Analytics, Clicky, Moz Analytics, and KISSMetrics.</span></span> <span data-ttu-id="8de29-107">De flesta webbanalyspaketen kräver att du lägger till klientskriptkod i elementet **\<head\>** för HTML på alla sidor på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="8de29-107">Most web analytics packages require that you add client-side script code in the **\<head\>** element of the HTML for all pages of your site.</span></span>

> [!NOTE]
> <span data-ttu-id="8de29-108">Instruktionerna i det här avsnittet gäller även andra anpassade klientfunktioner som Microsoft Dynamics 365 Commerce inte erbjuder.</span><span class="sxs-lookup"><span data-stu-id="8de29-108">The instructions in this topic also apply to other custom client-side functionality that Microsoft Dynamics 365 Commerce doesn't natively offer.</span></span>

## <a name="create-a-reusable-fragment-for-your-script-code"></a><span data-ttu-id="8de29-109">Skapa ett återanvändbart fragment för skriptkoden</span><span class="sxs-lookup"><span data-stu-id="8de29-109">Create a reusable fragment for your script code</span></span>

<span data-ttu-id="8de29-110">Med hjälp av ett fragment kan du återanvända en infogad eller extern skriptkod på alla sidor på din webbplats, oavsett vilken mall de använder.</span><span class="sxs-lookup"><span data-stu-id="8de29-110">A fragment allows you to reuse inline or external script code across all pages on your site, regardless of the template they use.</span></span>

### <a name="create-a-reusable-fragment-for-your-inline-script-code"></a><span data-ttu-id="8de29-111">Skapa ett återanvändbart fragment för den infogade skriptkoden</span><span class="sxs-lookup"><span data-stu-id="8de29-111">Create a reusable fragment for your inline script code</span></span>

<span data-ttu-id="8de29-112">Om du vill skapa ett återanvändbart fragment för den infogade skriptoden i webbplatsskaparen följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="8de29-112">To create a reusable fragment for your inline script code in site builder, follow these steps.</span></span>

1. <span data-ttu-id="8de29-113">Gå till **Fragment** och välj sedan **Nytt**.</span><span class="sxs-lookup"><span data-stu-id="8de29-113">Go to **Fragments**, and then select **New**.</span></span>
1. <span data-ttu-id="8de29-114">I dialogrutan **Nytt fragment** välj **infogat skript**.</span><span class="sxs-lookup"><span data-stu-id="8de29-114">In the **New fragment** dialog box, select **Inline script**.</span></span>
1. <span data-ttu-id="8de29-115">Under **fragmentets namn**, anger du ett namn på fragmentet och klickar sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="8de29-115">Under **Fragment name**, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="8de29-116">Under det fragment som du har skapat väljer du modulen **infogat standardskript**.</span><span class="sxs-lookup"><span data-stu-id="8de29-116">Under the fragment that you created, select the **Default inline script** module.</span></span>
1. <span data-ttu-id="8de29-117">Ange skript på klientsidan i egenskapsrutan till höger under **infogat skript**.</span><span class="sxs-lookup"><span data-stu-id="8de29-117">In the property pane on the right, under **Inline script**, enter your client-side script.</span></span> <span data-ttu-id="8de29-118">Konfigurera sedan andra alternativ som du behöver.</span><span class="sxs-lookup"><span data-stu-id="8de29-118">Then configure other options as you require.</span></span>
1. <span data-ttu-id="8de29-119">Välj **spara** och välj sedan **Avsluta redigeringen**.</span><span class="sxs-lookup"><span data-stu-id="8de29-119">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="8de29-120">Markera **Publicera**.</span><span class="sxs-lookup"><span data-stu-id="8de29-120">Select **Publish**.</span></span>

### <a name="create-a-reusable-fragment-for-your-external-script-code"></a><span data-ttu-id="8de29-121">Skapa ett återanvändbart fragment för den externa skriptkoden</span><span class="sxs-lookup"><span data-stu-id="8de29-121">Create a reusable fragment for your external script code</span></span>

<span data-ttu-id="8de29-122">Om du vill skapa ett återanvändbart fragment för den externa skripkoden i webbplatsskaparen följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="8de29-122">To create a reusable fragment for your external script code in site builder, follow these steps.</span></span>

1. <span data-ttu-id="8de29-123">Gå till **Fragment** och välj sedan **Nytt**.</span><span class="sxs-lookup"><span data-stu-id="8de29-123">Go to **Fragments**, and then select **New**.</span></span>
1. <span data-ttu-id="8de29-124">I dialogrutan **Nytt fragment** välj **externt skript**.</span><span class="sxs-lookup"><span data-stu-id="8de29-124">In the **New fragment** dialog box, select **External script**.</span></span>
1. <span data-ttu-id="8de29-125">Under **fragmentets namn**, anger du ett namn på fragmentet och klickar sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="8de29-125">Under **Fragment name**, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="8de29-126">Under det fragment som du har skapat väljer du modulen **externt standardskript**.</span><span class="sxs-lookup"><span data-stu-id="8de29-126">Under the fragment that you created, select the **Default external script** module.</span></span>
1. <span data-ttu-id="8de29-127">I egenskapsrutan till höger, under **Skriptkälla**, lägg till en extern eller relativ URL för den externa skriptkällan.</span><span class="sxs-lookup"><span data-stu-id="8de29-127">In the property pane on the right, under **Script source**, add an external or relative URL for the external script source.</span></span> <span data-ttu-id="8de29-128">Konfigurera sedan andra alternativ som du behöver.</span><span class="sxs-lookup"><span data-stu-id="8de29-128">Then configure other options as you require.</span></span>
1. <span data-ttu-id="8de29-129">Välj **spara** och välj sedan **Avsluta redigeringen**.</span><span class="sxs-lookup"><span data-stu-id="8de29-129">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="8de29-130">Markera **Publicera**.</span><span class="sxs-lookup"><span data-stu-id="8de29-130">Select **Publish**.</span></span>

> [!NOTE]
> <span data-ttu-id="8de29-131">Om säkerhetsprincip (CSP) för innehåll är aktiverad för din webbplats måste du se till att alla externa URL:er läggs till i CSP-direktivet **skript-src** i Commerce-webbplatsbyggaren.</span><span class="sxs-lookup"><span data-stu-id="8de29-131">If content security policy (CSP) is enabled for your site, ensure that all external URLs are added to the **script-src** CSP directive in Commerce site builder.</span></span> <span data-ttu-id="8de29-132">Mer information finns i [hantera säkerhetsprinciper för innehåll (CSP)](manage-csp.md).</span><span class="sxs-lookup"><span data-stu-id="8de29-132">For more information, see [Manage Content Security Policy (CSP)](manage-csp.md).</span></span>

## <a name="add-a-fragment-that-includes-script-code-to-a-template"></a><span data-ttu-id="8de29-133">Lägga till ett fragment som innehåller skriptkod i en mall</span><span class="sxs-lookup"><span data-stu-id="8de29-133">Add a fragment that includes script code to a template</span></span>

<span data-ttu-id="8de29-134">Följ dessa steg för att lägga till ett fragment som innehåller skriptkod till en mall i webbplatsbyggaren.</span><span class="sxs-lookup"><span data-stu-id="8de29-134">To add a fragment that includes script code to a template in site builder, follow these steps.</span></span>

1. <span data-ttu-id="8de29-135">Gå till **mallarna** och öppna mallen för sidorna som du vill lägga till skriptkoden i.</span><span class="sxs-lookup"><span data-stu-id="8de29-135">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
1. <span data-ttu-id="8de29-136">I det vänstra fönstret expanderar du mallstrukturlistan så att platsen **HTML-huvud** visas.</span><span class="sxs-lookup"><span data-stu-id="8de29-136">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
1. <span data-ttu-id="8de29-137">På platsen **HTML-huvud** markera knappen med punkter (**...**) och välj sedan **Lägg till fragment**.</span><span class="sxs-lookup"><span data-stu-id="8de29-137">In the **HTML Head** slot, select the ellipsis button (**...**), and then select **Add fragment**.</span></span>
1. <span data-ttu-id="8de29-138">Markera det fragment som du har skapat för skriptkoden.</span><span class="sxs-lookup"><span data-stu-id="8de29-138">Select the fragment that you created for your script code.</span></span>
1. <span data-ttu-id="8de29-139">Välj **spara** och välj sedan **Avsluta redigeringen**.</span><span class="sxs-lookup"><span data-stu-id="8de29-139">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="8de29-140">Markera **Publicera**.</span><span class="sxs-lookup"><span data-stu-id="8de29-140">Select **Publish**.</span></span>

## <a name="add-an-external-script-or-inline-script-directly-to-a-template"></a><span data-ttu-id="8de29-141">Lägga till ett externt skript eller infogat skript direkt i en mall</span><span class="sxs-lookup"><span data-stu-id="8de29-141">Add an external script or inline script directly to a template</span></span>

<span data-ttu-id="8de29-142">Om du vill infoga ett infogat eller externt skript direkt på en uppsättning sidor som kontrolleras av en enskild mall, behöver du inte skapa ett fragment först.</span><span class="sxs-lookup"><span data-stu-id="8de29-142">If you want to insert an inline or external script directly into a set of pages that are controlled by a single template, you don't have to create a fragment first.</span></span>

### <a name="add-an-inline-script-directly-to-a-template"></a><span data-ttu-id="8de29-143">Lägga till ett infogat skript direkt i en mall</span><span class="sxs-lookup"><span data-stu-id="8de29-143">Add an inline script directly to a template</span></span>

<span data-ttu-id="8de29-144">Om du vill lägga till ett infogat skript direkt på en mall i webbplatsskaparen följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="8de29-144">To add an inline script directly to a template in site builder, follow these steps.</span></span>

1. <span data-ttu-id="8de29-145">Gå till **mallarna** och öppna mallen för sidorna som du vill lägga till skriptkoden i.</span><span class="sxs-lookup"><span data-stu-id="8de29-145">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
1. <span data-ttu-id="8de29-146">I det vänstra fönstret expanderar du mallstrukturlistan så att platsen **HTML-huvud** visas.</span><span class="sxs-lookup"><span data-stu-id="8de29-146">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
1. <span data-ttu-id="8de29-147">I facket **HTML-huvud** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.</span><span class="sxs-lookup"><span data-stu-id="8de29-147">In the **HTML Head** slot, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="8de29-148">I dialogrutan **Lägg till modul** välj **infogat skript**.</span><span class="sxs-lookup"><span data-stu-id="8de29-148">In the **Add Module** dialog box, select **Inline script**.</span></span>
1. <span data-ttu-id="8de29-149">Ange skript på klientsidan i egenskapsrutan till höger under **infogat skript**.</span><span class="sxs-lookup"><span data-stu-id="8de29-149">In the property pane on the right, under **Inline script**, enter your client-side script.</span></span> <span data-ttu-id="8de29-150">Konfigurera sedan andra alternativ som du behöver.</span><span class="sxs-lookup"><span data-stu-id="8de29-150">Then configure other options as you require.</span></span>
1. <span data-ttu-id="8de29-151">Välj **spara** och välj sedan **Avsluta redigeringen**.</span><span class="sxs-lookup"><span data-stu-id="8de29-151">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="8de29-152">Markera **Publicera**.</span><span class="sxs-lookup"><span data-stu-id="8de29-152">Select **Publish**.</span></span>

### <a name="add-an-external-script-directly-to-a-template"></a><span data-ttu-id="8de29-153">Lägga till ett externt skript direkt i en mall</span><span class="sxs-lookup"><span data-stu-id="8de29-153">Add an external script directly to a template</span></span>

<span data-ttu-id="8de29-154">Om du vill lägga till ett extern skript direkt på en mall i webbplatsskaparen följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="8de29-154">To add an external script directly to a template in site builder, follow these steps.</span></span>

1. <span data-ttu-id="8de29-155">Gå till **mallarna** och öppna mallen för sidorna som du vill lägga till skriptkoden i.</span><span class="sxs-lookup"><span data-stu-id="8de29-155">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
1. <span data-ttu-id="8de29-156">I det vänstra fönstret expanderar du mallstrukturlistan så att platsen **HTML-huvud** visas.</span><span class="sxs-lookup"><span data-stu-id="8de29-156">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
1. <span data-ttu-id="8de29-157">I facket **HTML-huvud** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.</span><span class="sxs-lookup"><span data-stu-id="8de29-157">In the **HTML Head** slot, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="8de29-158">I dialogrutan **Lägg till modul** välj **externt skript**.</span><span class="sxs-lookup"><span data-stu-id="8de29-158">In the **Add Module** dialog box, select **External script**.</span></span>
1. <span data-ttu-id="8de29-159">I egenskapsrutan till höger, under **Skriptkälla**, lägg till en extern eller relativ URL för den externa skriptkällan.</span><span class="sxs-lookup"><span data-stu-id="8de29-159">In the property pane on the right, under **Script source**, add an external or relative URL for the external script source.</span></span> <span data-ttu-id="8de29-160">Konfigurera sedan andra alternativ som du behöver.</span><span class="sxs-lookup"><span data-stu-id="8de29-160">Then configure other options as you require.</span></span>
1. <span data-ttu-id="8de29-161">Välj **spara** och välj sedan **Avsluta redigeringen**.</span><span class="sxs-lookup"><span data-stu-id="8de29-161">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="8de29-162">Markera **Publicera**.</span><span class="sxs-lookup"><span data-stu-id="8de29-162">Select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8de29-163">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="8de29-163">Additional resources</span></span>

[<span data-ttu-id="8de29-164">Lägga till en logotyp</span><span class="sxs-lookup"><span data-stu-id="8de29-164">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="8de29-165">Välja ett tema för webbplatsen</span><span class="sxs-lookup"><span data-stu-id="8de29-165">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="8de29-166">Arbeta med CSS åsidosättningsfiler</span><span class="sxs-lookup"><span data-stu-id="8de29-166">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="8de29-167">Lägg till en favoritikon</span><span class="sxs-lookup"><span data-stu-id="8de29-167">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="8de29-168">Lägg till ett välkomstmeddelande</span><span class="sxs-lookup"><span data-stu-id="8de29-168">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="8de29-169">Lägg till copyrightmeddelande</span><span class="sxs-lookup"><span data-stu-id="8de29-169">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="8de29-170">Lägg till språk på din webbplats</span><span class="sxs-lookup"><span data-stu-id="8de29-170">Add languages to your site</span></span>](add-languages-to-site.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
