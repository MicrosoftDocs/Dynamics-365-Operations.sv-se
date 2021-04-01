---
title: Språkinformation för sökmotoroptimering (SEO) för din webbplats
description: Det här avsnittet handlar om sökmotorns SEO-information för din webbplats från utveckling till produktion.
author: psimolin
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: c4d1a4a1b14f7af1db1c53bd9ee1993cc9187609
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5254803"
---
# <a name="search-engine-optimization-seo-considerations-for-your-site"></a><span data-ttu-id="f96fb-103">Språkinformation för sökmotoroptimering (SEO) för din webbplats</span><span class="sxs-lookup"><span data-stu-id="f96fb-103">Search engine optimization (SEO) considerations for your site</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="f96fb-104">Det här avsnittet handlar om varje sökmotors SEO-information för din webbplats från utveckling till produktion.</span><span class="sxs-lookup"><span data-stu-id="f96fb-104">This topic covers earch engine optimization (SEO) considerations for your site from development to production.</span></span>

## <a name="a-site-that-is-under-development"></a><span data-ttu-id="f96fb-105">En webbplats som är under utveckling</span><span class="sxs-lookup"><span data-stu-id="f96fb-105">A site that is under development</span></span>

<span data-ttu-id="f96fb-106">Medan en webbplats är under utveckling ska alla sidor ha metataggarna **NOINDEX** och **NOFOLLOW** så att sökmotorer inte kan indexera sidorna och lagra utvecklingsversionerna av din webbplats i cacheminnet.</span><span class="sxs-lookup"><span data-stu-id="f96fb-106">While a site is under development, all site pages should have the **NOINDEX** and **NOFOLLOW** meta tags, so that search engines don't index the pages and store development versions of your site in their cache.</span></span> <span data-ttu-id="f96fb-107">För att kunna utföra den här konfigurationen måste du lägga till standardmodulen för metataggar på webbplatsmallen.</span><span class="sxs-lookup"><span data-stu-id="f96fb-107">To do this configuration, you must add the default meta tags module to the site page template.</span></span> <span data-ttu-id="f96fb-108">Standardegenskaperna för metataggarna är sedan tillgängliga i avsnittet SEO-egenskaper i sidredigeraren.</span><span class="sxs-lookup"><span data-stu-id="f96fb-108">The default meta tags properties will then be available in the SEO properties section in the page editor.</span></span> <span data-ttu-id="f96fb-109">Du kan använda dessa egenskaper för att hantera metataggarna.</span><span class="sxs-lookup"><span data-stu-id="f96fb-109">You can use these properties to manage the meta tags.</span></span>

## <a name="soft-launch-of-a-site"></a><span data-ttu-id="f96fb-110">Mjuk start av en plats</span><span class="sxs-lookup"><span data-stu-id="f96fb-110">Soft launch of a site</span></span>

<span data-ttu-id="f96fb-111">Under en "mjuk start" görs en webbplats tillgänglig för en begränsad publik eller marknad innan den fullständiga lanseringen sker.</span><span class="sxs-lookup"><span data-stu-id="f96fb-111">During a "soft launch," a website is made available to a limited audience or market before the full launch occurs.</span></span> <span data-ttu-id="f96fb-112">Om du gör en mjuk start av din webbplats bör du överväga att lämna metataggarna **NOINDEX** på plats.</span><span class="sxs-lookup"><span data-stu-id="f96fb-112">If you do a soft launch of your website, you should consider leaving the **NOINDEX** meta tags in place.</span></span> <span data-ttu-id="f96fb-113">På så sätt garanterar du att den mjuka starten förblir begränsad till de begränsade målgrupper som du vill uppnå.</span><span class="sxs-lookup"><span data-stu-id="f96fb-113">In this way, you help guarantee that the soft launch remains restricted to the limited audience that you want to reach.</span></span>

## <a name="a-site-that-is-in-production"></a><span data-ttu-id="f96fb-114">En webbplats som är i produktion</span><span class="sxs-lookup"><span data-stu-id="f96fb-114">A site that is in production</span></span>

<span data-ttu-id="f96fb-115">När en webbplats är i produktion bör du kontrollera att alla webbplatssidor är korrekt märkta.</span><span class="sxs-lookup"><span data-stu-id="f96fb-115">When a site is in production, you should make sure that all site pages are correctly tagged.</span></span> <span data-ttu-id="f96fb-116">Microsoft Dynamics 365 Commerce använder informationen som anges för en sida för att återge all SEO-information på sidan.</span><span class="sxs-lookup"><span data-stu-id="f96fb-116">Microsoft Dynamics 365 Commerce uses the information that is entered for a page to render all the SEO information on that page.</span></span> <span data-ttu-id="f96fb-117">Följande moduler ger den här funktionen: sammanfattning av kategorisidor, sammanfattning av listsidor och sammanfattning av produktsidor.</span><span class="sxs-lookup"><span data-stu-id="f96fb-117">The following modules provide this functionality: category page summary, list page summary, and product page summary.</span></span>

<span data-ttu-id="f96fb-118">För att optimera indexeringen använder återgivningsramverket både information från SEO-egenskaperna som konfigureras i Dynamics 365 Commerce och modulspecifik information.</span><span class="sxs-lookup"><span data-stu-id="f96fb-118">To optimize search engine indexing, the rendering framework uses both information from the SEO properties that are configured in Dynamics 365 Commerce and module-specific information.</span></span> <span data-ttu-id="f96fb-119">För en plats i produktionen bör du se till att filen robots.txt tillåter indexering av hela webbplatsen och att den innehåller länkar till det publicerade dokumentet för webbplatsöversikt.</span><span class="sxs-lookup"><span data-stu-id="f96fb-119">For a site that is in production, you should make sure that the robots.txt file allows for indexing of your whole site, and that it contains links to your published site map document.</span></span> <span data-ttu-id="f96fb-120">Du bör aktivera funktionen för att skapa webbplatsöversikt på **webbplatsinställningar \> webbplatsmappningar är aktiverade**.</span><span class="sxs-lookup"><span data-stu-id="f96fb-120">You should turn on the site map generation functionality at **Site Settings \> Site maps enabled**.</span></span>

### <a name="page-seo-settings-for-internal-preview-limited-audiences-and-all-audiences"></a><span data-ttu-id="f96fb-121">Sidinställningar för SEO för intern förhandsgranskning, begränsade målgrupper och alla målgrupper</span><span class="sxs-lookup"><span data-stu-id="f96fb-121">Page SEO settings for internal preview, limited audiences, and all audiences</span></span>

<span data-ttu-id="f96fb-122">Eftersom Dynamics 365 Commerce ger stöd för "vad du ser är vad du får" (WYSIWYG)-autentiserade förhandsgranskningar i visuell sidskapare, kan författare förbereda sitt sidinnehåll utan att behöva oroa sig om att informationen kommer att visas för besökare på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="f96fb-122">Because Dynamics 365 Commerce supports "what you see is what you get" (WYSIWYG) authenticated previews in visual page builder, authors can prepare their page content without having to worry that the information will become visible to site visitors.</span></span> <span data-ttu-id="f96fb-123">Om en sida måste publiceras, men dess exponering måste vara begränsad måste den ha metataggen **NOINDEX**, så att den inte indexeras av sökmotorer.</span><span class="sxs-lookup"><span data-stu-id="f96fb-123">If a page must be published, but its exposure must be limited, it should have the **NOINDEX** meta tag, so that it won't be indexed by search engines.</span></span> <span data-ttu-id="f96fb-124">När sidan är klar för alla målgrupper bör alla de grundläggande SEO-metadata finnas tillgängliga, vilket maximerar effektiviteten hos sökmotorindexeringen.</span><span class="sxs-lookup"><span data-stu-id="f96fb-124">Then, when the page is ready for all audiences, all the basic SEO metadata should be present, to maximize the efficiency of search engine indexing.</span></span> <span data-ttu-id="f96fb-125">Dessutom bör metataggen **NOLIMIT** tas bort.</span><span class="sxs-lookup"><span data-stu-id="f96fb-125">Additionally, the **NOLIMIT** meta tag should be removed.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f96fb-126">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="f96fb-126">Additional resources</span></span>

[<span data-ttu-id="f96fb-127">Hantera näthandelsanvändare och roller</span><span class="sxs-lookup"><span data-stu-id="f96fb-127">Manage e-Commerce users and roles</span></span>](manage-ecommerce-users-roles.md)

[<span data-ttu-id="f96fb-128">Lägga till skriptkod på webbsidor för att stödja telemetri</span><span class="sxs-lookup"><span data-stu-id="f96fb-128">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)

[<span data-ttu-id="f96fb-129">Hantera säkerhetspolicy för innehåll (CSP)</span><span class="sxs-lookup"><span data-stu-id="f96fb-129">Manage Content Security Policy (CSP)</span></span>](manage-csp.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]