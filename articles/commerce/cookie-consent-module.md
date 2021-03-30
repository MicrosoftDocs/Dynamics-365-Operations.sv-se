---
title: Modul för cookie-samtycke
description: Det här avsnittet handlar om modul för cookie-samtycke och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 57c8876f1faf08ce965ccd796551996a8651e2eb
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5213948"
---
# <a name="cookie-consent-module"></a><span data-ttu-id="9fb50-103">Modul för samtycke till cookies</span><span class="sxs-lookup"><span data-stu-id="9fb50-103">Cookie consent module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="9fb50-104">Det här avsnittet handlar om modul för cookie-samtycke och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="9fb50-104">This topic covers cookie consent modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="9fb50-105">Modul för cookie-samtycke uppmanar webbplatsanvändare att uttryckligen lämna samtycke till att tillåta cookies för alla funktioner eller moduler som spårar webbläsarcookies.</span><span class="sxs-lookup"><span data-stu-id="9fb50-105">The cookie consent module prompts site users to explicitly provide consent to allow cookies for any feature or module that tracks browser cookies.</span></span> <span data-ttu-id="9fb50-106">Samtycke krävs första gången en webbplatsanvändare bläddrar i en ny webbläsarsession.</span><span class="sxs-lookup"><span data-stu-id="9fb50-106">The consent is required the first time a site user browses a site in a new browser session.</span></span> <span data-ttu-id="9fb50-107">När samtycke tas emot spåras det och webbplatsens användare kommer inte att tillfrågas om medgivande igen.</span><span class="sxs-lookup"><span data-stu-id="9fb50-107">When consent is received, it is tracked and the site user will not be prompted for consent again.</span></span> <span data-ttu-id="9fb50-108">Mer information finns i [kompatibilitet med cookies](cookie-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="9fb50-108">For more information, see [Cookie compliance](cookie-compliance.md).</span></span>

<span data-ttu-id="9fb50-109">Om samtycke från webbplatsanvändare inte tas emot, återges inte alla funktioner eller moduler som kräver cookie-samtycke på sidan.</span><span class="sxs-lookup"><span data-stu-id="9fb50-109">If site user cookie consent is not received, any features or modules that require cookie consent will not be rendered on the page.</span></span> <span data-ttu-id="9fb50-110">Till exempel betalningsmodulen, modulen för sociala resurser och önskad butik kräver alla cookie-samtycke och kommer inte att återges om användarens samtycke inte har mottagits på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="9fb50-110">For example, the checkout module, social share module, and preferred store feature all require cookie consent and will not be rendered if site user consent is not received.</span></span> 

<span data-ttu-id="9fb50-111">En modul för cookie-samtycke kan konfigureras på sidans rubrikfragment så att den kan användas när sidan läses in.</span><span class="sxs-lookup"><span data-stu-id="9fb50-111">A cookie consent module can be configured on a page's header fragment so that it can be enforced when the page loads.</span></span> <span data-ttu-id="9fb50-112">Modulen för cookie-samtycke ska ha ett tydligt meddelande som informerar användaren om cookie-användning på webbplatsen och ska innehålla en länk till platsens integritetssida.</span><span class="sxs-lookup"><span data-stu-id="9fb50-112">The cookie consent module should have a clear message informing the site user about cookie usage on the site and should provide a link to the site's privacy page.</span></span>

<span data-ttu-id="9fb50-113">I följande bild visas ett exempel på ett samtyckesmeddelande för en cookie med en länk till platsens sekretesspolicy sida som visas i rubriken på en webbplatssida.</span><span class="sxs-lookup"><span data-stu-id="9fb50-113">The following illustration highlights an example of a cookie consent message with a link to the site's privacy policy page displayed on the header of a site page.</span></span>
<span data-ttu-id="9fb50-114">![Exempel på en modul för cookie-samtycke](./media/ecommerce-cookieconsent.png)</span><span class="sxs-lookup"><span data-stu-id="9fb50-114">![Example of a cookie consent module](./media/ecommerce-cookieconsent.png)</span></span>

## <a name="cookie-consent-module-properties"></a><span data-ttu-id="9fb50-115">Egenskaper för modul för cookie-samtycke</span><span class="sxs-lookup"><span data-stu-id="9fb50-115">Cookie consent module properties</span></span>

| <span data-ttu-id="9fb50-116">Egenskapsnamn</span><span class="sxs-lookup"><span data-stu-id="9fb50-116">Property name</span></span>             | <span data-ttu-id="9fb50-117">Värde</span><span class="sxs-lookup"><span data-stu-id="9fb50-117">Value</span></span>                 | <span data-ttu-id="9fb50-118">beskrivning</span><span class="sxs-lookup"><span data-stu-id="9fb50-118">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="9fb50-119">RTF-format</span><span class="sxs-lookup"><span data-stu-id="9fb50-119">Rich Text</span></span>                  | <span data-ttu-id="9fb50-120">RTF-format</span><span class="sxs-lookup"><span data-stu-id="9fb50-120">Rich Text</span></span> | <span data-ttu-id="9fb50-121">Anger ett RTF-meddelande till webbplatsanvändare som webbplatsen använder webbläsarcookies och som användarna bör acceptera för att använda cookies för webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="9fb50-121">Specifies a Rich Text notification to site users that the site uses browser cookies and that users should accept the use of cookies for the site to be fully functional.</span></span> |
| <span data-ttu-id="9fb50-122">Länkar</span><span class="sxs-lookup"><span data-stu-id="9fb50-122">Links</span></span> | <span data-ttu-id="9fb50-123">URL</span><span class="sxs-lookup"><span data-stu-id="9fb50-123">URL</span></span> | <span data-ttu-id="9fb50-124">En eller flera länkar kan läggas till på en webbplats sekretesspolicy som beskriver de typer av cookies som spåras på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="9fb50-124">One or more links can be added to a site's privacy page that describes the types of cookies that are tracked on the site.</span></span> |

## <a name="add-a-cookie-consent-module-to-site-pages"></a><span data-ttu-id="9fb50-125">Lägga till en modul för cookie-samtycke på webbplatssidor</span><span class="sxs-lookup"><span data-stu-id="9fb50-125">Add a cookie consent module to site pages</span></span>

<span data-ttu-id="9fb50-126">Om du vill lägga till en modul för cookie-samtycke på flera webbplatssidor kan den läggas till i ett avsnitt på en delad sidrubrik.</span><span class="sxs-lookup"><span data-stu-id="9fb50-126">To efficiently add a cookie consent module to multiple site pages, it can be added to a shared page header fragment.</span></span> <span data-ttu-id="9fb50-127">När du har lagt till huvudavsnittet på alla webbplatssidor kommer ett meddelande om godkännande för cookies automatiskt att återges första gången en webbplatsanvändare navigerar till en webbplatssida.</span><span class="sxs-lookup"><span data-stu-id="9fb50-127">After the header fragment is added to all site pages, a cookie consent notification will automatically be rendered the first time a site user navigates to any site page.</span></span>

<span data-ttu-id="9fb50-128">Mer information om fragment och moduler för rubriker finns i [huvudmodul](author-header-module.md).</span><span class="sxs-lookup"><span data-stu-id="9fb50-128">For more information about header fragments and modules, see [Header module](author-header-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9fb50-129">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="9fb50-129">Additional resources</span></span>

[<span data-ttu-id="9fb50-130">Översikt över modulbibliotek</span><span class="sxs-lookup"><span data-stu-id="9fb50-130">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="9fb50-131">Modul för sidhuvud</span><span class="sxs-lookup"><span data-stu-id="9fb50-131">Header module</span></span>](author-header-module.md) 

[<span data-ttu-id="9fb50-132">Cookie-kompatibilitet</span><span class="sxs-lookup"><span data-stu-id="9fb50-132">Cookie compliance</span></span>](cookie-compliance.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]