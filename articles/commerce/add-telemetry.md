---
title: Lägga till skriptkod på webbsidor för att stödja telemetri
description: I det här avsnittet beskrivs hur du lägger till skriptkod på klientsidan på webbplatssidorna för att stödja insamling av telemetri på klientsidan.
author: bicyclingfool
manager: annbe
ms.date: 12/12/2019
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
ms.openlocfilehash: 674d00faf1b30f87a0b0062129e1b9fbff955dd4
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/01/2020
ms.locfileid: "3001287"
---
# <a name="add-script-code-to-site-pages-to-support-telemetry"></a><span data-ttu-id="0673f-103">Lägga till skriptkod på webbsidor för att stödja telemetri</span><span class="sxs-lookup"><span data-stu-id="0673f-103">Add script code to site pages to support telemetry</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="0673f-104">I det här avsnittet beskrivs hur du lägger till skriptkod på klientsidan på webbplatssidorna för att stödja insamling av telemetri på klientsidan.</span><span class="sxs-lookup"><span data-stu-id="0673f-104">This topic describes how to add client-side script code to your site pages to support the collection of client-side telemetry.</span></span>

## <a name="overview"></a><span data-ttu-id="0673f-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="0673f-105">Overview</span></span>

<span data-ttu-id="0673f-106">Webbanalys är ett viktigt verktyg när du vill förstå hur dina kunder samverkar med din webbplats och fatta beslut som hjälper dig att optimera upplevelsen för maximal konvertering.</span><span class="sxs-lookup"><span data-stu-id="0673f-106">Web analytics are an essential tool when you want to understand how your customers interact with your site and make decisions that will help optimize the experience for maximum conversion.</span></span> <span data-ttu-id="0673f-107">Det finns många webbanalyspaket som hjälper dig att uppnå dessa mål, t.ex. Google Analytics, Clicky, Moz Analytics och KISSMetrics.</span><span class="sxs-lookup"><span data-stu-id="0673f-107">Many web analytics packages are available to help you achieve these goals, such as Google Analytics, Clicky, Moz Analytics, and KISSMetrics.</span></span> <span data-ttu-id="0673f-108">De flesta webbanalyspaketen kräver att du lägger till klientskriptkod i elementet **\<head\>** för HTML på alla sidor på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="0673f-108">Most web analytics packages require that you add client-side script code in the **\<head\>** element of the HTML for all pages of your site.</span></span>

> [!NOTE]
> <span data-ttu-id="0673f-109">Instruktionerna i det här avsnittet gäller även andra anpassade klientfunktioner som Microsoft Dynamics 365 Commerce inte erbjuder.</span><span class="sxs-lookup"><span data-stu-id="0673f-109">The instructions in this topic also apply to other custom client-side functionality that Microsoft Dynamics 365 Commerce doesn't natively offer.</span></span>

## <a name="create-a-reusable-fragment-for-your-script-code"></a><span data-ttu-id="0673f-110">Skapa ett återanvändbart fragment för skriptkoden</span><span class="sxs-lookup"><span data-stu-id="0673f-110">Create a reusable fragment for your script code</span></span>

<span data-ttu-id="0673f-111">När du har skapat ett fragment för skriptkoden kan det återanvändas på alla sidor på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="0673f-111">After you create a fragment for your script code, it can be reused across all pages on your site.</span></span>

1. <span data-ttu-id="0673f-112">Gå till **fragment \> fragment för ny sida**.</span><span class="sxs-lookup"><span data-stu-id="0673f-112">Go to **Fragments \> New page fragment**.</span></span>
2. <span data-ttu-id="0673f-113">Välj **Externt skript**, ange ett namn på fragmentet och klicka sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="0673f-113">Select **External Script**, enter a name for the fragment, and then select **OK**.</span></span>
3. <span data-ttu-id="0673f-114">I fragmenthierarkin väljer du underordnad modul för **skriptinmatare** för det fragment du just skapade.</span><span class="sxs-lookup"><span data-stu-id="0673f-114">In the fragment hierarchy, select the **script injector** module child of the fragment that you just created.</span></span>
4. <span data-ttu-id="0673f-115">Lägg till klientskript i egenskapsrutan till höger och ange andra konfigurations alternativ som du behöver.</span><span class="sxs-lookup"><span data-stu-id="0673f-115">In the property pane on the right, add your client-side script, and set other configuration options as you require.</span></span>

## <a name="add-the-fragment-to-templates"></a><span data-ttu-id="0673f-116">Lägg till avsnittet i mallarna</span><span class="sxs-lookup"><span data-stu-id="0673f-116">Add the fragment to templates</span></span>

1. <span data-ttu-id="0673f-117">Gå till **mallarna** och öppna mallen för sidorna som du vill lägga till skriptkoden i.</span><span class="sxs-lookup"><span data-stu-id="0673f-117">Go to **Templates**, and open the template for the pages that you want to add your script code to.</span></span>
2. <span data-ttu-id="0673f-118">I det vänstra fönstret expanderar du mallstrukturlistan så att platsen **HTML-huvud** visas.</span><span class="sxs-lookup"><span data-stu-id="0673f-118">In the left pane, expand the template hierarchy to show the **HTML Head** slot.</span></span>
3. <span data-ttu-id="0673f-119">Markera knappen med punkter (**...**) för platsen **HTML-huvud** och välj sedan **Lägg till fragment**.</span><span class="sxs-lookup"><span data-stu-id="0673f-119">Select the ellipsis button (**...**) for the **HTML Head** slot, and then select **Add fragment**.</span></span>
4. <span data-ttu-id="0673f-120">Markera det fragment som du har skapat för skriptkoden.</span><span class="sxs-lookup"><span data-stu-id="0673f-120">Select the fragment that you created for your script code.</span></span>
5. <span data-ttu-id="0673f-121">Spara mallen och checka in den.</span><span class="sxs-lookup"><span data-stu-id="0673f-121">Save the template, and check it in.</span></span>

> [!NOTE]
> <span data-ttu-id="0673f-122">När du är klar måste du publicera fragmentet och huvudmallen.</span><span class="sxs-lookup"><span data-stu-id="0673f-122">After you've finished, you must publish the fragment and the master template.</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="0673f-123">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="0673f-123">Additional resources</span></span>

[<span data-ttu-id="0673f-124">Lägg till en logotyp</span><span class="sxs-lookup"><span data-stu-id="0673f-124">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="0673f-125">Välj ett tema för webbplatsen</span><span class="sxs-lookup"><span data-stu-id="0673f-125">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="0673f-126">Arbeta med CSS åsidosättningsfiler</span><span class="sxs-lookup"><span data-stu-id="0673f-126">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="0673f-127">Lägg till en favoritikon</span><span class="sxs-lookup"><span data-stu-id="0673f-127">Add a favicon</span></span>](add-favicon.md)

[<span data-ttu-id="0673f-128">Lägg till ett välkomstmeddelande</span><span class="sxs-lookup"><span data-stu-id="0673f-128">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="0673f-129">Lägg till copyrightmeddelande</span><span class="sxs-lookup"><span data-stu-id="0673f-129">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="0673f-130">Lägg till språk på din webbplats</span><span class="sxs-lookup"><span data-stu-id="0673f-130">Add languages to your site</span></span>](add-languages-to-site.md)

