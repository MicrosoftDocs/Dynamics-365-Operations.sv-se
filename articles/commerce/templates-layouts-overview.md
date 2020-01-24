---
title: Översikt över mallar och layouter
description: I det här avsnittet beskrivs mallar och layouter i Microsoft Dynamics 365 Commerce.
author: phinneyridge
manager: annbe
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: niholman
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 4ddae5b77c36151a279a463033079099722d166e
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/20/2019
ms.locfileid: "2914851"
---
# <a name="templates-and-layouts-overview"></a><span data-ttu-id="a09c6-103">Översikt över mallar och layouter</span><span class="sxs-lookup"><span data-stu-id="a09c6-103">Templates and layouts overview</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="a09c6-104">Mallar är grundläggande element i Microsoft Dynamics 365 Commerce sidmodell.</span><span class="sxs-lookup"><span data-stu-id="a09c6-104">Templates are a foundational element of the Microsoft Dynamics 365 Commerce page model.</span></span> <span data-ttu-id="a09c6-105">Om målet är att maximera effektiviteten och kontinuiteten för arbetsflöden för webbplatsredigering är det viktigt att du lär dig hur du kan dra nytta av mallarna för webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="a09c6-105">If your goal is to maximize efficiency and consistency for site authoring workflows, it's important that you learn how to take advantages of templates for your website.</span></span> <span data-ttu-id="a09c6-106">Tidiga beslut om mallstrukturlistan är viktiga och kan märkbart påverka kostnader och rörlighet för dagliga, säsongsmässiga och platsbaserade varumärkesuppdateringar.</span><span class="sxs-lookup"><span data-stu-id="a09c6-106">Early decisions about template structure are important, and can significantly affect cost and agility for daily, seasonal, and site-wide brand updates.</span></span> <span data-ttu-id="a09c6-107">Välstrukturerade mallar har även andra fördelar.</span><span class="sxs-lookup"><span data-stu-id="a09c6-107">Well-structured templates have other benefits too.</span></span> <span data-ttu-id="a09c6-108">De kan till exempel hjälpa till att förbättra SEO-poängen (Search Engine Optimization) för hela webbplatsen och minska antalet fel.</span><span class="sxs-lookup"><span data-stu-id="a09c6-108">For example, they help improve site-wide search engine optimization (SEO) scores and minimize bug counts.</span></span>

<span data-ttu-id="a09c6-109">Ett bra sätt att börja arbeta med mallar är att förstå de funktionella fördelarna med mallar och layouter, skillnaderna mellan dem och hierarkin.</span><span class="sxs-lookup"><span data-stu-id="a09c6-109">A good way to start to work with templates is to understand the functional benefits of templates and layouts, the differences between them, and the hierarchy.</span></span>

<span data-ttu-id="a09c6-110">Följande bild visar sidmodellens hierarki bakom en återgiven webbsida.</span><span class="sxs-lookup"><span data-stu-id="a09c6-110">The following illustration shows the page model hierarchy behind a rendered webpage.</span></span>

![Diagram för sidmodell](../commerce/media/page-model-diagram.png)

| <span data-ttu-id="a09c6-112">Enhet</span><span class="sxs-lookup"><span data-stu-id="a09c6-112">Entity</span></span>        | <span data-ttu-id="a09c6-113">Basfunktion</span><span class="sxs-lookup"><span data-stu-id="a09c6-113">Basic function</span></span> |
|---------------|----------------|
| <span data-ttu-id="a09c6-114">Mall</span><span class="sxs-lookup"><span data-stu-id="a09c6-114">Template</span></span>      | <span data-ttu-id="a09c6-115">Mallar definierar modulens alternativ och grundläggande ställningar för en uppsättning layouter och sidinstanser.</span><span class="sxs-lookup"><span data-stu-id="a09c6-115">Templates define the module options and basic scaffolding for a set of layouts and page instances.</span></span> |
| <span data-ttu-id="a09c6-116">Layout</span><span class="sxs-lookup"><span data-stu-id="a09c6-116">Layout</span></span>        | <span data-ttu-id="a09c6-117">Layouter definierar det slutliga urvalet och arrangemanget av moduler för en sida eller en uppsättning sidor.</span><span class="sxs-lookup"><span data-stu-id="a09c6-117">Layouts define the final selection and arrangement of modules for a page or a set of pages.</span></span> |
| <span data-ttu-id="a09c6-118">Sidinstans</span><span class="sxs-lookup"><span data-stu-id="a09c6-118">Page instance</span></span> | <span data-ttu-id="a09c6-119">Sidinstanser definierar data och innehåll för specifika sidor.</span><span class="sxs-lookup"><span data-stu-id="a09c6-119">Page instances define the data and content for specific pages.</span></span> |

## <a name="templates"></a><span data-ttu-id="a09c6-120">Mallar</span><span class="sxs-lookup"><span data-stu-id="a09c6-120">Templates</span></span>

<span data-ttu-id="a09c6-121">Mallarna finns högst upp i Dynamics 365 Commerce sidans modellhierarki och representerar ett viktigt tidigt steg för webbplatskonfigurationen.</span><span class="sxs-lookup"><span data-stu-id="a09c6-121">Templates are at the top of the Dynamics 365 Commerce page model hierarchy and represent an important early step for site configuration.</span></span> <span data-ttu-id="a09c6-122">Mallar hjälper till att kontrollera överensstämmelsen i en familj med underordnade layouter och sidor genom att definiera grundläggande struktur och redigeringsalternativ för att förenkla arbetsflöden för skapande av layout och skapande av sidor.</span><span class="sxs-lookup"><span data-stu-id="a09c6-122">Conceptually, templates help control consistency across a family of child layouts and pages by defining the base structure and authoring options for downstream layout creation and page creation workflows.</span></span> <span data-ttu-id="a09c6-123">Med hjälp av mallarna kan du förenkla processen för redigering genom fördefinierade, centralt hanterade element (t.ex. sidhuvuden och sidfötter) och guidade redigeringsflöden som hjälper till att garantera att alternativen för modulkonfiguration är anpassade.</span><span class="sxs-lookup"><span data-stu-id="a09c6-123">Templates can help simplify the content authoring process through predefined, centrally managed elements (such as headers and footers) and guided authoring flows that help guarantee that module configuration choices are on-brand.</span></span>

### <a name="controlling-consistency"></a><span data-ttu-id="a09c6-124">Kontrollera konsekvens</span><span class="sxs-lookup"><span data-stu-id="a09c6-124">Controlling consistency</span></span>

<span data-ttu-id="a09c6-125">När du utformar en mall är det större affärsbeslut du måste göra hur stor kontroll mallen ska ha över processen för att skapa sidan.</span><span class="sxs-lookup"><span data-stu-id="a09c6-125">When you design a template, the biggest business decision that you must make is how much control the template should have over the page creation process.</span></span> <span data-ttu-id="a09c6-126">En mall som lämnar allting öppet för en underordnad författare är det enklaste sättet att skapa en mall, men det kan också finnas långsiktiga följder för underhållet av sidor som skapas från den.</span><span class="sxs-lookup"><span data-stu-id="a09c6-126">A template that leaves everything open for a downstream author is the easiest type of template to create, but it might have long-term consequences for the maintenance of pages that are created from it.</span></span> <span data-ttu-id="a09c6-127">En välskriven mall ger vägledning och en strömlinjeformad redigeringsupplevelse, men den ger också författarna tillräckligt mycket flexibilitet så att de kan slutföra sin uppgift.</span><span class="sxs-lookup"><span data-stu-id="a09c6-127">A well-written template provides guidance and a streamlined authoring experience, but it also gives authors enough flexibility so that they can complete their task.</span></span> <span data-ttu-id="a09c6-128">Alla dessa aspekter beror på den kontrollnivå som mallen gäller för.</span><span class="sxs-lookup"><span data-stu-id="a09c6-128">All these aspects depend on the level of control that the template enforces.</span></span>

<span data-ttu-id="a09c6-129">Med hjälp av mallar kan innehållsförfattare bli mer effektiva och hålla sig à jour på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="a09c6-129">Templates can help content authors be more efficient and stay on-brand in the following ways:</span></span>

- <span data-ttu-id="a09c6-130">Begränsa de moduler som kan användas på en sida.</span><span class="sxs-lookup"><span data-stu-id="a09c6-130">Limit the modules that can be used on a page.</span></span>
- <span data-ttu-id="a09c6-131">Föreslå standardval för moduler och konfiguration.</span><span class="sxs-lookup"><span data-stu-id="a09c6-131">Suggest default module and configuration choices.</span></span>
- <span data-ttu-id="a09c6-132">Uttryckligen göra vissa modul- och konfigurationsval som kontrolleras på sidnivå.</span><span class="sxs-lookup"><span data-stu-id="a09c6-132">Explicitly make some module and configuration choices that are controlled at the template level.</span></span> <span data-ttu-id="a09c6-133">Den här processen kallas även *låsning* av en inställning.</span><span class="sxs-lookup"><span data-stu-id="a09c6-133">This process is also known as *locking* a setting.</span></span>

<span data-ttu-id="a09c6-134">Följande exempel visar hur en grundläggande mall (mall X) kan konfigureras:</span><span class="sxs-lookup"><span data-stu-id="a09c6-134">The following example shows how a basic template (template X) can be configured:</span></span>

- <span data-ttu-id="a09c6-135">Alla underordnade layouter för mall X måste ha en rubrikbehållare, en brödtextbehållare och en sidfotsbehållare.</span><span class="sxs-lookup"><span data-stu-id="a09c6-135">All child layouts of template X must have a header container, a body container, and a footer container.</span></span>
- <span data-ttu-id="a09c6-136">I mall X är konfigurationen av rubrikbehållaren låst och kan bara ändras i mall X.</span><span class="sxs-lookup"><span data-stu-id="a09c6-136">In template X, the configuration of the header container is locked and can be changed only in template X itself.</span></span> <span data-ttu-id="a09c6-137">Alla underordnade layouter och sidor har alltid den här rubriken.</span><span class="sxs-lookup"><span data-stu-id="a09c6-137">All child layouts and pages always have this header.</span></span>
- <span data-ttu-id="a09c6-138">Brödtextbehållaren måste innehålla minst en modul och upp till tio moduler.</span><span class="sxs-lookup"><span data-stu-id="a09c6-138">The body container requires at least one module and up to a maximum of ten modules.</span></span> <span data-ttu-id="a09c6-139">Dessa moduler definieras av underordnade layouter och sidor.</span><span class="sxs-lookup"><span data-stu-id="a09c6-139">These modules are defined by downstream layouts and pages.</span></span>
- <span data-ttu-id="a09c6-140">För brödtextbehållaren finns det en fokus-, funktions-, karusell- och banderollmodul.</span><span class="sxs-lookup"><span data-stu-id="a09c6-140">For the body container, the hero, feature, carousel, and banner modules are available.</span></span>
- <span data-ttu-id="a09c6-141">En sidfotsbehållare konfigureras i mall X, men kan åsidosättas med efterföljande layouter och sidor.</span><span class="sxs-lookup"><span data-stu-id="a09c6-141">A footer container is configured in template X, but it can be overridden by downstream layouts and pages.</span></span>

<span data-ttu-id="a09c6-142">Mallen i det här exemplet definierar en enkel struktur och en uppsättning alternativ för författare av underordnade innehåll.</span><span class="sxs-lookup"><span data-stu-id="a09c6-142">The template in this example defines a simple structure and set of options for downstream content authors.</span></span> <span data-ttu-id="a09c6-143">Lägg märke till att vissa delar av en sida (i det här fallet rubriken) är fullständigt definierade och låsta i mallen, och att de inte kan ändras av efterföljande författare.</span><span class="sxs-lookup"><span data-stu-id="a09c6-143">Notice that some parts of a page (in this case, the header) are fully defined and locked in the template, and they can't be changed by downstream authors.</span></span> <span data-ttu-id="a09c6-144">Andra delar (i det här fallet brödtext) kan definieras av en underordnad författare inom särskilda riktlinjer (i det här fallet ett minsta antal och högsta antal moduler av specifika typer).</span><span class="sxs-lookup"><span data-stu-id="a09c6-144">Other parts (in this case, the body) can be defined by downstream authors within specific guidelines (in this case, a minimum number and maximum number of modules of specific types).</span></span> <span data-ttu-id="a09c6-145">Och andra delar (i det här fallet sidfoten) definieras i mallen men kan åsidosättas av författare som är underordnade.</span><span class="sxs-lookup"><span data-stu-id="a09c6-145">And other parts (in this case, the footer) are defined in the template but can be overridden by downstream authors.</span></span>

<span data-ttu-id="a09c6-146">Ett viktigt första steg för webbplats- och varumärkesadministratörer är att fastställa rätt balans mellan begränsning och flexibilitet för underordnade layouter och sidförfattare.</span><span class="sxs-lookup"><span data-stu-id="a09c6-146">An important initial step for site and brand admins is to determine the correct balance between constraint and flexibility for child layout and page authors.</span></span> <span data-ttu-id="a09c6-147">När mallar används är saldot helt konfigurerbart.</span><span class="sxs-lookup"><span data-stu-id="a09c6-147">When templates are used, this balance is completely configurable.</span></span> <span data-ttu-id="a09c6-148">Det påverkar om sidelementen har uppdaterats centralt (låsts i mallen) eller till enskilda underordnade nivåer som är lägre i sidhierarkin.</span><span class="sxs-lookup"><span data-stu-id="a09c6-148">It affects whether page elements are centrally updated (locked in the template) or left to individual child levels that are lower in the page hierarchy.</span></span>

<span data-ttu-id="a09c6-149">Om du vill börja använda mallar [arbeta med mallar](work-with-templates.md).</span><span class="sxs-lookup"><span data-stu-id="a09c6-149">To start to use templates, [Work with templates](work-with-templates.md).</span></span>

## <a name="layouts"></a><span data-ttu-id="a09c6-150">Layouter</span><span class="sxs-lookup"><span data-stu-id="a09c6-150">Layouts</span></span>

<span data-ttu-id="a09c6-151">Layouter är nästa nivå i sidmodellens hierarki, under mallar.</span><span class="sxs-lookup"><span data-stu-id="a09c6-151">Layouts are the next level in the page model hierarchy, below templates.</span></span> <span data-ttu-id="a09c6-152">En mall definierar alla moduler som är tillåtna för en sida, men en layout är ett explicit urval och arrangemang av moduler.</span><span class="sxs-lookup"><span data-stu-id="a09c6-152">Whereas a template defines all the modules that are allowed for a page, a layout is an explicit selection and arrangement of modules.</span></span> <span data-ttu-id="a09c6-153">Sidor är nästa nivå i sidmodellens hierarki, under layouter.</span><span class="sxs-lookup"><span data-stu-id="a09c6-153">Pages are the next level in the page model hierarchy, below layouts.</span></span> <span data-ttu-id="a09c6-154">De definierar det lokaliserade innehållet för modulerna som väljs i layouten.</span><span class="sxs-lookup"><span data-stu-id="a09c6-154">They define the localized content for the modules that are selected in the layout.</span></span>

<span data-ttu-id="a09c6-155">Följande exempel bygger på mallen från föregående avsnitt och visar hur en grundläggande layout kan konfigureras:</span><span class="sxs-lookup"><span data-stu-id="a09c6-155">The following example builds on the template example from the previous section, and shows how a basic layout can be configured:</span></span>

- <span data-ttu-id="a09c6-156">Den överordnade mallen för layouten kräver att brödtextbehållaren har mellan en och tio moduler.</span><span class="sxs-lookup"><span data-stu-id="a09c6-156">The parent template of the layout requires that the body container have between one and ten modules.</span></span> <span data-ttu-id="a09c6-157">Modulerna kan bara vara fokus-, funktions-, karusell- och banderollmoduler.</span><span class="sxs-lookup"><span data-stu-id="a09c6-157">These modules can be only hero, feature, carousel, and banner modules.</span></span> <span data-ttu-id="a09c6-158">Därför kan layouten definiera följande urval och arrangemang för moduler:</span><span class="sxs-lookup"><span data-stu-id="a09c6-158">Therefore, the layout can define the following selection and arrangement of modules:</span></span>

    - <span data-ttu-id="a09c6-159">Den första modulen i brödtextbehållaren är en webbannons, som följs av en fokusmodul och två funktionsmoduler.</span><span class="sxs-lookup"><span data-stu-id="a09c6-159">The first module in the body container is a banner module, and it's followed by a hero module and two feature modules.</span></span>
    - <span data-ttu-id="a09c6-160">Den första funktionsmodulen är vänsterjusterad och den andra modulen är högerjusterad.</span><span class="sxs-lookup"><span data-stu-id="a09c6-160">The first feature module is left-aligned, and the second feature module is right-aligned.</span></span>

- <span data-ttu-id="a09c6-161">Även om en standardsidfoten är ärvd från den överordnade mallen, lämnade mallförfattaren sidfoten olåst.</span><span class="sxs-lookup"><span data-stu-id="a09c6-161">Even though a default footer is inherited from the parent template, the template author left the footer unlocked.</span></span> <span data-ttu-id="a09c6-162">Därför kan layouten åsidosättas genom att ett annat sidfotsavsnitt definieras.</span><span class="sxs-lookup"><span data-stu-id="a09c6-162">Therefore, the layout can override it by defining a different footer fragment.</span></span>

<span data-ttu-id="a09c6-163">Layouten i det här exemplet definierar den slutliga ordningen för moduler för underordnade sidor.</span><span class="sxs-lookup"><span data-stu-id="a09c6-163">The layout in this example defines the final arrangement of modules for child pages.</span></span> <span data-ttu-id="a09c6-164">Precis som en mall kan en layout definiera standardformat eller låsta modulegenskaper som alltid ska ärvas av underordnade sidor (t.ex. justeringen av funktionsmodulen).</span><span class="sxs-lookup"><span data-stu-id="a09c6-164">Like a template, a layout can define default or locked module properties that will always be inherited by child pages (for example, the alignment of the feature modules).</span></span> <span data-ttu-id="a09c6-165">Det faktiska innehållet eller data för varje modul i layouten definieras sedan längre ned i hierarkin, i varje instans av underordnad sida.</span><span class="sxs-lookup"><span data-stu-id="a09c6-165">The actual content or data for every module in the layout is then defined farther down the hierarchy, in each child page instance.</span></span> <span data-ttu-id="a09c6-166">En viktig skillnad här är att layouterna inte direkt innehåller lokaliseringsbara innehåll, medan deras underordnade sidor gör det.</span><span class="sxs-lookup"><span data-stu-id="a09c6-166">An important distinction here is that layouts don't directly contain localizable content, whereas their child pages do.</span></span> <span data-ttu-id="a09c6-167">Layoutens primära funktion är att definiera den slutliga ordningen och standardkonfigurationen av moduler för underordnade sidor.</span><span class="sxs-lookup"><span data-stu-id="a09c6-167">The layout's primary function is to define the final arrangement and default configuration of modules for its child pages.</span></span>

<span data-ttu-id="a09c6-168">Den här hierarkin är kraftfull av två skäl.</span><span class="sxs-lookup"><span data-stu-id="a09c6-168">This hierarchy is powerful for two reasons.</span></span> <span data-ttu-id="a09c6-169">För det första behandlas layouter som delar samma överordnade mall som kompatibla med layoutväxlingsscenarier.</span><span class="sxs-lookup"><span data-stu-id="a09c6-169">First, layouts that share the same parent template are treated as compatible for layout switching scenarios.</span></span> <span data-ttu-id="a09c6-170">Därför kan layouten för en sida ändras till en annan layout från samma mall, utan att sidnivåinnehållet måste redigeras på nytt.</span><span class="sxs-lookup"><span data-stu-id="a09c6-170">Therefore, the layout for any page can be changed to another layout from the same template hierarchy without requiring that page-level content be reauthored.</span></span> <span data-ttu-id="a09c6-171">Du kan dra nytta av den här möjligheten att göra säsongsmässiga designuppdateringar, experimentera eller göra en omdefiniering av en permanent webbplats.</span><span class="sxs-lookup"><span data-stu-id="a09c6-171">You can take advantage of this capability to do seasonal design updates, experiment, or do a permanent site redesign.</span></span> <span data-ttu-id="a09c6-172">För det andra kan du med hjälp av layouten ändra delade element centralt för en grupp med sidor utan att behöva uppdatera enskilda sidor.</span><span class="sxs-lookup"><span data-stu-id="a09c6-172">Second, layouts provide another way to centrally modify shared elements for a group of pages without requiring updates to individual pages.</span></span> <span data-ttu-id="a09c6-173">Om en produktkategori till exempel har 1 000 sidor som delar samma layout, kan modulerna ordnas om i layouten och den här ändringen återspeglas i alla 1 000 underordnade sidor.</span><span class="sxs-lookup"><span data-stu-id="a09c6-173">For example, if a product category has 1,000 pages that share the same layout, the modules can be reordered in the layout, and this change will immediately be reflected in all 1,000 child pages.</span></span>

<span data-ttu-id="a09c6-174">Genom att förstå den här hierarkin kan du ge en smidig och effektiv webbplatsstruktur som hjälper till att spara kostnader, är skalbar och ger bättre resultat allt eftersom webbplatsen utvecklas över tiden.</span><span class="sxs-lookup"><span data-stu-id="a09c6-174">By understanding this hierarchy, you can deliver an agile and efficient site structure that helps save cost, is scalable, and produces better results as the site evolves over time.</span></span>

### <a name="preset-and-custom-layouts"></a><span data-ttu-id="a09c6-175">Förinställda och anpassade layouter</span><span class="sxs-lookup"><span data-stu-id="a09c6-175">Preset and custom layouts</span></span>

<span data-ttu-id="a09c6-176">Layouterna på din webbplats kan vara antingen *förinställda* eller *anpassade*:</span><span class="sxs-lookup"><span data-stu-id="a09c6-176">Layouts on your site can be either *preset* or *custom*:</span></span>

- <span data-ttu-id="a09c6-177">**Förinställda layouter** gör det möjligt att skapa ett arbetsflöde där alla moduler redan är markerade och ordnade, och endast datainmatning krävs.</span><span class="sxs-lookup"><span data-stu-id="a09c6-177">**Preset layouts** allow for a page creation workflow where all modules are already selected and arranged, and only data entry is required.</span></span> <span data-ttu-id="a09c6-178">Det här tillvägagångssättet gör det enklare att spara tid när många sidor måste ha samma krav på layouten.</span><span class="sxs-lookup"><span data-stu-id="a09c6-178">This approach can help save time when many pages must be authored that have the same layout requirements.</span></span> <span data-ttu-id="a09c6-179">Förinställda layouter har en 1:n-relation till sina underordnade sidor.</span><span class="sxs-lookup"><span data-stu-id="a09c6-179">Preset layouts have a one-to-many relationship with their child pages.</span></span> <span data-ttu-id="a09c6-180">Därför kan en enda förinställd layout användas för att styra modulen för hundratals eller tusentals underordnade sidor centralt.</span><span class="sxs-lookup"><span data-stu-id="a09c6-180">Therefore, a single preset layout can be used to centrally control the module arrangement for hundreds or thousands of child pages.</span></span>
- <span data-ttu-id="a09c6-181">**Anpassade layouter** är i huvudsak layouter för engångsbruk som är inbäddade på en sida.</span><span class="sxs-lookup"><span data-stu-id="a09c6-181">**Custom layouts** are essentially single-use layouts that are embedded in one page.</span></span> <span data-ttu-id="a09c6-182">De visas inte som ett alternativ när andra nya sidor skapas eller när du växlar mellan olika layouter.</span><span class="sxs-lookup"><span data-stu-id="a09c6-182">They aren't exposed as an option when other new pages are created or in layout switching scenarios.</span></span> <span data-ttu-id="a09c6-183">Fördelen med den här metoden är att en författare kan experimentera genom att redigera en sida som använder en anpassad layout.</span><span class="sxs-lookup"><span data-stu-id="a09c6-183">The benefit of this approach is that an author can experiment by authoring a page that uses a custom layout.</span></span> <span data-ttu-id="a09c6-184">Om författaren vill återanvända layouten för andra sidor kan den enkelt konverteras till en förinställd layout.</span><span class="sxs-lookup"><span data-stu-id="a09c6-184">Then, if the author wants to reuse the layout for other pages, it can easily be converted to a preset layout.</span></span> <span data-ttu-id="a09c6-185">Den nya förinställda layouten visas sedan som ett alternativ i arbetsflöden för sid skapande och i layoutändringar för sidor från samma mall.</span><span class="sxs-lookup"><span data-stu-id="a09c6-185">The new preset layout is then exposed as an option in page creation workflows and in layout switching scenarios for pages from the same template hierarchy.</span></span> <span data-ttu-id="a09c6-186">Omvänt kan förinställda layouter förgrenas i anpassade layouter.</span><span class="sxs-lookup"><span data-stu-id="a09c6-186">Conversely, preset layouts can be branched into custom layouts.</span></span> <span data-ttu-id="a09c6-187">På så sätt kan en författare bryta en sida utanför den förinställda layouten och skapa en ny anpassad layout med en enda användning.</span><span class="sxs-lookup"><span data-stu-id="a09c6-187">In this way, an author can break a page away from the preset layout and create a new single-use custom layout.</span></span> <span data-ttu-id="a09c6-188">(Den nya anpassade layouten är fortfarande bunden av eventuella begränsningar i den överordnade mallen.)</span><span class="sxs-lookup"><span data-stu-id="a09c6-188">(This new custom layout is still bound by any constraints in the parent template.)</span></span>

<span data-ttu-id="a09c6-189">Förinställd layout och anpassade layouter redigeras i olika delar av redigeringsverktygen.</span><span class="sxs-lookup"><span data-stu-id="a09c6-189">Preset layout and custom layouts are edited in different parts of the authoring toolset.</span></span> <span data-ttu-id="a09c6-190">Eftersom anpassade layouter inte är beroende av andra sidor redigeras de direkt i sidredigeraren.</span><span class="sxs-lookup"><span data-stu-id="a09c6-190">Because custom layouts have no dependencies on other pages, they are edited directly in the page editor.</span></span> <span data-ttu-id="a09c6-191">I detta fall är det oftast genomskinligt att använda en layout för användaren och den visas bara i egenskaper på sidnivå och genom åtgärderna för layoutalternativ.</span><span class="sxs-lookup"><span data-stu-id="a09c6-191">In this case, the existence of a layout is mostly transparent to the user and is exposed only in page-level properties and through the actions for layout options.</span></span> <span data-ttu-id="a09c6-192">Eftersom ändringar av förinställda layouter kan påverka många underordnade sidor måste de dock redigeras i layoutredigeraren, där publiceringsåtgärder ser hela den fullständiga effekten på underordnade sidor.</span><span class="sxs-lookup"><span data-stu-id="a09c6-192">However, because changes to preset layouts can affect many child pages, they must be edited in the layout editor, where publish actions consider the full downstream impact on child pages.</span></span>

<span data-ttu-id="a09c6-193">I följande illustrationer visas scenarierna för förinställda och anpassade layouter.</span><span class="sxs-lookup"><span data-stu-id="a09c6-193">The following illustrations shows scenarios for preset and custom layouts.</span></span>

![Förinställda och anpassade layouter](../commerce/media/template-figure1.png)

<span data-ttu-id="a09c6-195">Information om hur du använder förinställda layouter finns i [arbeta med förinställda layouter](work-with-layouts.md).</span><span class="sxs-lookup"><span data-stu-id="a09c6-195">To start to use preset layouts, see [Work with preset layouts](work-with-layouts.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a09c6-196">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="a09c6-196">Additional resources</span></span>

[<span data-ttu-id="a09c6-197">Arbeta med mallar</span><span class="sxs-lookup"><span data-stu-id="a09c6-197">Work with templates</span></span>](work-with-templates.md)

[<span data-ttu-id="a09c6-198">Arbeta med förinställda layouter</span><span class="sxs-lookup"><span data-stu-id="a09c6-198">Work with preset layouts</span></span>](work-with-layouts.md)

[<span data-ttu-id="a09c6-199">Arbeta med publiceringsgrupper</span><span class="sxs-lookup"><span data-stu-id="a09c6-199">Work with publish groups</span></span>](publish-groups.md)