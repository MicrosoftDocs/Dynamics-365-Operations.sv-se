---
title: Lägga till skriptkod på webbsidor för att stödja telemetri
description: I det här avsnittet beskrivs hur du lägger till skriptkod på klientsidan på webbplatssidorna för att stödja insamling av telemetri på klientsidan.
author: bicyclingfool
manager: annbe
ms.date: 08/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: a88f4f920154aafaa15a48af67365152e21111f7
ms.sourcegitcommit: 420b9e538f706178f8e1f2786e02f4f400bf2336
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/02/2020
ms.locfileid: "3761259"
---
# <a name="add-script-code-to-site-pages-to-support-telemetry"></a><span data-ttu-id="a0b1f-103">Lägga till skriptkod på webbsidor för att stödja telemetri</span><span class="sxs-lookup"><span data-stu-id="a0b1f-103">Add script code to site pages to support telemetry</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="a0b1f-104">I det här avsnittet beskrivs hur du lägger till skriptkod på klientsidan på webbplatssidorna för att stödja insamling av telemetri på klientsidan.</span><span class="sxs-lookup"><span data-stu-id="a0b1f-104">This topic describes how to add client-side script code to your site pages to support the collection of client-side telemetry.</span></span>

## <a name="overview"></a><span data-ttu-id="a0b1f-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="a0b1f-105">Overview</span></span>

<span data-ttu-id="a0b1f-106">Webbanalys är ett viktigt verktyg när du vill förstå hur dina kunder samverkar med din webbplats och fatta beslut som hjälper dig att optimera upplevelsen för maximal konvertering.</span><span class="sxs-lookup"><span data-stu-id="a0b1f-106">Web analytics are an essential tool when you want to understand how your customers interact with your site and make decisions that will help optimize the experience for maximum conversion.</span></span> <span data-ttu-id="a0b1f-107">Det finns många webbanalyspaket som hjälper dig att uppnå dessa mål, t.ex. Google Analytics, Clicky, Moz Analytics och KISSMetrics.</span><span class="sxs-lookup"><span data-stu-id="a0b1f-107">Many web analytics packages are available to help you achieve these goals, such as Google Analytics, Clicky, Moz Analytics, and KISSMetrics.</span></span> <span data-ttu-id="a0b1f-108">De flesta webbanalyspaketen kräver att du lägger till klientskriptkod i elementet **\<head\>** för HTML på alla sidor på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="a0b1f-108">Most web analytics packages require that you add client-side script code in the **\<head\>** element of the HTML for all pages of your site.</span></span>

> [!NOTE]
> <span data-ttu-id="a0b1f-109">Instruktionerna i det här avsnittet gäller även andra anpassade klientfunktioner som Microsoft Dynamics 365 Commerce inte erbjuder.</span><span class="sxs-lookup"><span data-stu-id="a0b1f-109">The instructions in this topic also apply to other custom client-side functionality that Microsoft Dynamics 365 Commerce doesn't natively offer.</span></span>

## <a name="create-a-reusable-fragment-for-your-script-code"></a><span data-ttu-id="a0b1f-110">Skapa ett återanvändbart fragment för skriptkoden</span><span class="sxs-lookup"><span data-stu-id="a0b1f-110">Create a reusable fragment for your script code</span></span>

<span data-ttu-id="a0b1f-111">Med hjälp av ett fragment kan du återanvända en infogad eller extern skriptkod på alla sidor på din webbplats, oavsett vilken mall de använder.</span><span class="sxs-lookup"><span data-stu-id="a0b1f-111">A fragment allows you to reuse inline or external script code across all pages on your site, regardless of the template they use.</span></span>

### <a name="create-a-reusable-fragment-for-your-inline-script-code"></a><span data-ttu-id="a0b1f-112">Skapa ett återanvändbart fragment för den infogade skriptkoden</span><span class="sxs-lookup"><span data-stu-id="a0b1f-112">Create a reusable fragment for your inline script code</span></span>

<span data-ttu-id="a0b1f-113">Om du vill skapa ett återanvändbart fragment för den infogade skriptoden i webbplatsskaparen följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="a0b1f-113">To create a reusable fragment for your inline script code in site builder, follow these steps.</span></span>

1. <span data-ttu-id="a0b1f-114">Gå till **Fragment** och välj sedan **Nytt**.</span><span class="sxs-lookup"><span data-stu-id="a0b1f-114">Go to **Fragments**, and then select **New**.</span></span>
1. <span data-ttu-id="a0b1f-115">I dialogrutan **Nytt fragment** välj **infogat skript**.</span><span class="sxs-lookup"><span data-stu-id="a0b1f-115">In the **New fragment** dialog box, select **Inline script**.</span></span>
1. <span data-ttu-id="a0b1f-116">Under **fragmentets namn**, anger du ett namn på fragmentet och klickar sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="a0b1f-116">Under **Fragment name**, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="a0b1f-117">Under det fragment som du har skapat väljer du modulen **infogat standardskript**.</span><span class="sxs-lookup"><span data-stu-id="a0b1f-117">Under the fragment that you created, select the **Default inline script** module.</span></span>
1. <span data-ttu-id="a0b1f-118">Ange skript på klientsidan i egenskapsrutan till höger under **infogat skript**.</span><span class="sxs-lookup"><span data-stu-id="a0b1f-118">In the property pane on the right, under **Inline script**, enter your client-side script.</span></span> <span data-ttu-id="a0b1f-119">Konfigurera sedan andra alternativ som du behöver.</span><span class="sxs-lookup"><span data-stu-id="a0b1f-119">Then configure other options as you require.</span></span>
1. <span data-ttu-id="a0b1f-120">Välj **spara**och välj sedan **Avsluta redigeringen**.</span><span class="sxs-lookup"><span data-stu-id="a0b1f-120">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="a0b1f-121">Markera **Publicera**.</span><span class="sxs-lookup"><span data-stu-id="a0b1f-121">Select **Publish**.</span></span>

### <a name="create-a-reusable-fragment-for-your-external-script-code"></a><span data-ttu-id="a0b1f-122">Skapa ett återanvändbart fragment för den externa skriptkoden</span><span class="sxs-lookup"><span data-stu-id="a0b1f-122">Create a reusable fragment for your external script code</span></span>

<span data-ttu-id="a0b1f-123">Om du vill skapa ett återanvändbart fragment för den externa skripkoden i webbplatsskaparen följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="a0b1f-123">To create a reusable fragment for your external script code in site builder, follow these steps.</span></span>

1. <span data-ttu-id="a0b1f-124">Gå till **Fragment** och välj sedan **Nytt**.</span><span class="sxs-lookup"><span data-stu-id="a0b1f-124">Go to **Fragments**, and then select **New**.</span></span>
1. <span data-ttu-id="a0b1f-125">I dialogrutan **Nytt fragment** välj **externt skript**.</span><span class="sxs-lookup"><span data-stu-id="a0b1f-125">In the **New fragment** dialog box, select **External script**.</span></span>
1. <span data-ttu-id="a0b1f-126">Under **fragmentets namn**, anger du ett namn på fragmentet och klickar sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="a0b1f-126">Under **Fragment name**, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="a0b1f-127">Under det fragment som du har skapat väljer du modulen **externt standardskript**.</span><span class="sxs-lookup"><span data-stu-id="a0b1f-127">Under the fragment that you created, select the **Default external script** module.</span></span>
1. <span data-ttu-id="a0b1f-128">I egenskapsrutan till höger, under **Skriptkälla**, lägg till en extern eller relativ URL för den externa skriptkällan.</span><span class="sxs-lookup"><span data-stu-id="a0b1f-128">In the property pane on the right, under **Script source**, add an external or relative URL for the external script source.</span></span> <span data-ttu-id="a0b1f-129">Konfigurera sedan andra alternativ som du behöver.</span><span class="sxs-lookup"><span data-stu-id="a0b1f-129">Then configure other options as you require.</span></span>
1. <span data-ttu-id="a0b1f-130">Välj **spara**och välj sedan **Avsluta redigeringen**.</span><span class="sxs-lookup"><span data-stu-id="a0b1f-130">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="a0b1f-131">Markera **Publicera**.</span><span class="sxs-lookup"><span data-stu-id="a0b1f-131">Select **Publish**.</span></span>

## <a name="add-a-fragment-that-includes-script-code-to-a-template"></a><span data-ttu-id="a0b1f-132">Lägga till ett fragment som innehåller skriptkod i en mall</span><span class="sxs-lookup"><span data-stu-id="a0b1f-132">Add a fragment that includes script code to a template</span></span>

<span data-ttu-id="a0b1f-133">Följ dessa steg för att lägga till ett fragment som innehåller skriptkod till en mall i webbplatsbyggaren.</span><span class="sxs-lookup"><span data-stu-id="a0b1f-133">To add a fragment that includes script code to a template in site builder, follow these steps.</span></span>

1. <span data-ttu-id="a0b1f-134">Gå till **mallarna** och öppna mallen för sidorna som du vill lägga till skriptkoden i.</span><span class="sxs-lookup"><span data-stu-id="a0b1f-134">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
1. <span data-ttu-id="a0b1f-135">I det vänstra fönstret expanderar du mallstrukturlistan så att platsen **HTML-huvud** visas.</span><span class="sxs-lookup"><span data-stu-id="a0b1f-135">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
1. <span data-ttu-id="a0b1f-136">På platsen **HTML-huvud** markera knappen med punkter (**...**) och välj sedan **Lägg till fragment**.</span><span class="sxs-lookup"><span data-stu-id="a0b1f-136">In the **HTML Head** slot, select the ellipsis button (**...**), and then select **Add fragment**.</span></span>
1. <span data-ttu-id="a0b1f-137">Markera det fragment som du har skapat för skriptkoden.</span><span class="sxs-lookup"><span data-stu-id="a0b1f-137">Select the fragment that you created for your script code.</span></span>
1. <span data-ttu-id="a0b1f-138">Välj **spara**och välj sedan **Avsluta redigeringen**.</span><span class="sxs-lookup"><span data-stu-id="a0b1f-138">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="a0b1f-139">Markera **Publicera**.</span><span class="sxs-lookup"><span data-stu-id="a0b1f-139">Select **Publish**.</span></span>

## <a name="add-an-external-script-or-inline-script-directly-to-a-template"></a><span data-ttu-id="a0b1f-140">Lägga till ett externt skript eller infogat skript direkt i en mall</span><span class="sxs-lookup"><span data-stu-id="a0b1f-140">Add an external script or inline script directly to a template</span></span>

<span data-ttu-id="a0b1f-141">Om du vill infoga ett infogat eller externt skript direkt på en uppsättning sidor som kontrolleras av en enskild mall, behöver du inte skapa ett fragment först.</span><span class="sxs-lookup"><span data-stu-id="a0b1f-141">If you want to insert an inline or external script directly into a set of pages that are controlled by a single template, you don't have to create a fragment first.</span></span>

### <a name="add-an-inline-script-directly-to-a-template"></a><span data-ttu-id="a0b1f-142">Lägga till ett infogat skript direkt i en mall</span><span class="sxs-lookup"><span data-stu-id="a0b1f-142">Add an inline script directly to a template</span></span>

<span data-ttu-id="a0b1f-143">Om du vill lägga till ett infogat skript direkt på en mall i webbplatsskaparen följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="a0b1f-143">To add an inline script directly to a template in site builder, follow these steps.</span></span>

1. <span data-ttu-id="a0b1f-144">Gå till **mallarna** och öppna mallen för sidorna som du vill lägga till skriptkoden i.</span><span class="sxs-lookup"><span data-stu-id="a0b1f-144">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
1. <span data-ttu-id="a0b1f-145">I det vänstra fönstret expanderar du mallstrukturlistan så att platsen **HTML-huvud** visas.</span><span class="sxs-lookup"><span data-stu-id="a0b1f-145">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
1. <span data-ttu-id="a0b1f-146">I facket **HTML-huvud** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.</span><span class="sxs-lookup"><span data-stu-id="a0b1f-146">In the **HTML Head** slot, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="a0b1f-147">I dialogrutan **Lägg till modul** välj **infogat skript**.</span><span class="sxs-lookup"><span data-stu-id="a0b1f-147">In the **Add Module** dialog box, select **Inline script**.</span></span>
1. <span data-ttu-id="a0b1f-148">Ange skript på klientsidan i egenskapsrutan till höger under **infogat skript**.</span><span class="sxs-lookup"><span data-stu-id="a0b1f-148">In the property pane on the right, under **Inline script**, enter your client-side script.</span></span> <span data-ttu-id="a0b1f-149">Konfigurera sedan andra alternativ som du behöver.</span><span class="sxs-lookup"><span data-stu-id="a0b1f-149">Then configure other options as you require.</span></span>
1. <span data-ttu-id="a0b1f-150">Välj **spara**och välj sedan **Avsluta redigeringen**.</span><span class="sxs-lookup"><span data-stu-id="a0b1f-150">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="a0b1f-151">Markera **Publicera**.</span><span class="sxs-lookup"><span data-stu-id="a0b1f-151">Select **Publish**.</span></span>

### <a name="add-an-external-script-directly-to-a-template"></a><span data-ttu-id="a0b1f-152">Lägga till ett externt skript direkt i en mall</span><span class="sxs-lookup"><span data-stu-id="a0b1f-152">Add an external script directly to a template</span></span>

<span data-ttu-id="a0b1f-153">Om du vill lägga till ett extern skript direkt på en mall i webbplatsskaparen följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="a0b1f-153">To add an external script directly to a template in site builder, follow these steps.</span></span>

1. <span data-ttu-id="a0b1f-154">Gå till **mallarna** och öppna mallen för sidorna som du vill lägga till skriptkoden i.</span><span class="sxs-lookup"><span data-stu-id="a0b1f-154">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
1. <span data-ttu-id="a0b1f-155">I det vänstra fönstret expanderar du mallstrukturlistan så att platsen **HTML-huvud** visas.</span><span class="sxs-lookup"><span data-stu-id="a0b1f-155">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
1. <span data-ttu-id="a0b1f-156">I facket **HTML-huvud** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.</span><span class="sxs-lookup"><span data-stu-id="a0b1f-156">In the **HTML Head** slot, select the ellipsis button (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="a0b1f-157">I dialogrutan **Lägg till modul** välj **externt skript**.</span><span class="sxs-lookup"><span data-stu-id="a0b1f-157">In the **Add Module** dialog box, select **External script**.</span></span>
1. <span data-ttu-id="a0b1f-158">I egenskapsrutan till höger, under **Skriptkälla**, lägg till en extern eller relativ URL för den externa skriptkällan.</span><span class="sxs-lookup"><span data-stu-id="a0b1f-158">In the property pane on the right, under **Script source**, add an external or relative URL for the external script source.</span></span> <span data-ttu-id="a0b1f-159">Konfigurera sedan andra alternativ som du behöver.</span><span class="sxs-lookup"><span data-stu-id="a0b1f-159">Then configure other options as you require.</span></span>
1. <span data-ttu-id="a0b1f-160">Välj **spara**och välj sedan **Avsluta redigeringen**.</span><span class="sxs-lookup"><span data-stu-id="a0b1f-160">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="a0b1f-161">Markera **Publicera**.</span><span class="sxs-lookup"><span data-stu-id="a0b1f-161">Select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a0b1f-162">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="a0b1f-162">Additional resources</span></span>

[<span data-ttu-id="a0b1f-163">Lägga till en logotyp</span><span class="sxs-lookup"><span data-stu-id="a0b1f-163">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="a0b1f-164">Välja ett tema för webbplatsen</span><span class="sxs-lookup"><span data-stu-id="a0b1f-164">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="a0b1f-165">Arbeta med CSS åsidosättningsfiler</span><span class="sxs-lookup"><span data-stu-id="a0b1f-165">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="a0b1f-166">Lägg till en favoritikon</span><span class="sxs-lookup"><span data-stu-id="a0b1f-166">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="a0b1f-167">Lägg till ett välkomstmeddelande</span><span class="sxs-lookup"><span data-stu-id="a0b1f-167">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="a0b1f-168">Lägg till copyrightmeddelande</span><span class="sxs-lookup"><span data-stu-id="a0b1f-168">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="a0b1f-169">Lägg till språk på din webbplats</span><span class="sxs-lookup"><span data-stu-id="a0b1f-169">Add languages to your site</span></span>](add-languages-to-site.md)
