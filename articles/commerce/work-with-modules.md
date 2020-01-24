---
title: Arbeta med moduler
description: I det här avsnittet beskrivs hur och när du ska använda moduler i Microsoft Dynamics 365 Commerce.
author: v-chgri
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
ms.author: phinneyridge
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 3c4161e7a40cdbbb40292a6ce9acab58347460bd
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/20/2019
ms.locfileid: "2914804"
---
# <a name="work-with-modules"></a><span data-ttu-id="e8d1a-103">Arbeta med moduler</span><span class="sxs-lookup"><span data-stu-id="e8d1a-103">Work with modules</span></span>

<span data-ttu-id="e8d1a-104">I det här avsnittet beskrivs hur och när du ska använda moduler i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="e8d1a-104">This topic describes how and when to use modules in Microsoft Dynamics 365 Commerce.</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

## <a name="overview"></a><span data-ttu-id="e8d1a-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="e8d1a-105">Overview</span></span>

<span data-ttu-id="e8d1a-106">Moduler är logiska byggblock som utgör sidans struktur och har olika syfte och omfång.</span><span class="sxs-lookup"><span data-stu-id="e8d1a-106">Modules are logical building blocks that make up your page structure, and they have various purposes and scopes.</span></span> <span data-ttu-id="e8d1a-107">Vissa moduler är behållare på hög nivå, och de är bara avsedda att innehålla och organisera andra moduler (underordnade moduler).</span><span class="sxs-lookup"><span data-stu-id="e8d1a-107">Some modules are high-level containers, and their only purpose is to hold and organize other modules (child modules).</span></span> <span data-ttu-id="e8d1a-108">Andra moduler, t.ex. en enkel bildplaceringsmodul, har ett mycket specifikt syfte.</span><span class="sxs-lookup"><span data-stu-id="e8d1a-108">Other modules, such as a simple image placement module, have a very specific purpose.</span></span> <span data-ttu-id="e8d1a-109">Andra moduler, till exempel en karusellmodul, ligger någonstans mellan dessa två kategorier.</span><span class="sxs-lookup"><span data-stu-id="e8d1a-109">Other modules, such as a carousel module, fall somewhere between those two categories.</span></span>

<span data-ttu-id="e8d1a-110">Webbplatsen Dynamics 365 Commerce innehåller som standard ett bibliotek med startpaketmoduler som gör att du kan uppnå de flesta grundläggande näthandelsscenarier.</span><span class="sxs-lookup"><span data-stu-id="e8d1a-110">By default, your Dynamics 365 Commerce site includes a starter kit module library that lets you achieve most basic e-Commerce scenarios.</span></span> <span data-ttu-id="e8d1a-111">Du bör kunna skapa en slutpunkt-till-slutpunkt-plats för e-handel genom att bara använda de här modulerna.</span><span class="sxs-lookup"><span data-stu-id="e8d1a-111">You should be able to construct an end-to-end e-Commerce site just by using these modules.</span></span> <span data-ttu-id="e8d1a-112">Men du kanske också vill anpassa dessa moduler eller bygga nya, anpassade moduler för specifika behov.</span><span class="sxs-lookup"><span data-stu-id="e8d1a-112">However, you might also want to customize these modules or build new, custom modules for specific needs.</span></span> <span data-ttu-id="e8d1a-113">Om du vill skapa anpassade moduler kan du använda en moduldesign-SDK (Software Development Kit) som hjälper dig att skapa ett anpassat bibliotek för modulen.</span><span class="sxs-lookup"><span data-stu-id="e8d1a-113">If you want to build custom modules, a module design software development kit (SDK) is available to help you create a custom module library.</span></span>

## <a name="container-modules-and-slots"></a><span data-ttu-id="e8d1a-114">Moduler och platser för behållare</span><span class="sxs-lookup"><span data-stu-id="e8d1a-114">Container modules and slots</span></span>

<span data-ttu-id="e8d1a-115">Som tidigare nämnts är vissa moduler avsedda att innehålla underordnade moduler.</span><span class="sxs-lookup"><span data-stu-id="e8d1a-115">As was mentioned earlier, some modules are designed to hold child modules.</span></span> <span data-ttu-id="e8d1a-116">Dessa moduler kallas *behållare*, och de tillåter hierarkier för kapslade moduler.</span><span class="sxs-lookup"><span data-stu-id="e8d1a-116">These modules are known as *containers*, and they allow for hierarchies of nested modules.</span></span> <span data-ttu-id="e8d1a-117">Behållarmoduler inkluderar *platser*.</span><span class="sxs-lookup"><span data-stu-id="e8d1a-117">Container modules include *slots*.</span></span> <span data-ttu-id="e8d1a-118">Platser används för att hantera layout och syfte för underordnade moduler i behållaren.</span><span class="sxs-lookup"><span data-stu-id="e8d1a-118">Slots are used to handle the layout and purpose of child modules in the container.</span></span> <span data-ttu-id="e8d1a-119">Ett exempel är en grundläggande sidbehållarmodul (en modul på översta nivån för alla sidor) som definierar flera viktiga platser:</span><span class="sxs-lookup"><span data-stu-id="e8d1a-119">An example is a basic page container module (a top-level module for any page) that defines several important slots:</span></span>

- <span data-ttu-id="e8d1a-120">En sidhuvudplats</span><span class="sxs-lookup"><span data-stu-id="e8d1a-120">A header slot</span></span>
- <span data-ttu-id="e8d1a-121">En brödtextplats</span><span class="sxs-lookup"><span data-stu-id="e8d1a-121">A body slot</span></span>
- <span data-ttu-id="e8d1a-122">En sidfotsplats</span><span class="sxs-lookup"><span data-stu-id="e8d1a-122">A footer slot</span></span>

<span data-ttu-id="e8d1a-123">Modulens utvecklare definierar dessa platser och avgör vilka underordnade moduler och hur många underordnade moduler som kan placeras direkt inuti det.</span><span class="sxs-lookup"><span data-stu-id="e8d1a-123">The module's developer defines these slots, and determines which child modules and how many child modules can be put directly inside it.</span></span> <span data-ttu-id="e8d1a-124">Sidhuvudsplatsen kan t.ex. stödja bara en av modulerna i typen **Modul för sidhuvud** medan brödtextplatsen kan stödja ett obegränsat antal moduler av vilken typ som helst (utom andra sidbehållarmoduler).</span><span class="sxs-lookup"><span data-stu-id="e8d1a-124">For example, the header slot might support only one module of the **Header Module** type, whereas the body slot might support an unlimited number of modules of any type (except other page container modules).</span></span>

<span data-ttu-id="e8d1a-125">I redigeringsverktygen behöver inte sidförfattare veta i förväg vilka moduler som kan och inte kan placeras på varje plats.</span><span class="sxs-lookup"><span data-stu-id="e8d1a-125">In the authoring tools, page authors don't have to know in advance which modules can and can't be put in each slot.</span></span> <span data-ttu-id="e8d1a-126">När sidans författare väljer en plats och sedan försöker välja en modul som ska läggas till i den, visas en filtrerad vy av modulens typer som stöds för platsen.</span><span class="sxs-lookup"><span data-stu-id="e8d1a-126">When page authors select a slot and then try to select a module to add to it, they see a filtered view of module types that are supported for that slot.</span></span>

## <a name="content-modules"></a><span data-ttu-id="e8d1a-127">Innehållsmoduler</span><span class="sxs-lookup"><span data-stu-id="e8d1a-127">Content modules</span></span>

<span data-ttu-id="e8d1a-128">Innehållsmoduler innehåller innehålls- och medieelement, t.ex. text (t.ex. rubriker, stycken och länkar) eller tillgångsreferenser (t.ex. bilder, video och PDF-filer).</span><span class="sxs-lookup"><span data-stu-id="e8d1a-128">Content modules contain content and media elements, such as text (for example, headlines, paragraphs, and links) or asset references (for example, images, video, and PDFs).</span></span> <span data-ttu-id="e8d1a-129">Exempel på typiska typer av innehållsmoduler är **funktion**, **innehåll** och **banderoll**.</span><span class="sxs-lookup"><span data-stu-id="e8d1a-129">Examples of typical content module types are **Hero**, **Feature**, and **Banner**.</span></span> <span data-ttu-id="e8d1a-130">Moduler av dessa tre typer kan innehålla text eller media och de behöver inte några underordnade moduler för att göra något synligt på en sida.</span><span class="sxs-lookup"><span data-stu-id="e8d1a-130">Modules of these three types can contain text or media, and they don't require any child modules to make something visible on a page.</span></span>

<span data-ttu-id="e8d1a-131">De flesta vanliga, dagliga och innehållsredigeringsaktiviteterna omfattar innehållsmoduler, främst på grund av att dessa moduler definierar det faktiska innehållet som återges i sina överordnade behållarmoduler.</span><span class="sxs-lookup"><span data-stu-id="e8d1a-131">The majority of typical, day-to-day page and content authoring activities involve content modules, primarily because these modules define the actual content that is rendered in their parent container modules.</span></span> <span data-ttu-id="e8d1a-132">Många innehållsmoduler är tillgängliga och dessa moduler är vanligtvis de sista delarna som du lägger till i en sidas hierarki med kapslade moduler.</span><span class="sxs-lookup"><span data-stu-id="e8d1a-132">Many content modules are available, and these modules are typically the last pieces that you will add to a page's hierarchy of nested modules.</span></span>

<span data-ttu-id="e8d1a-133">I följande bild visas hur moduler kapslas inuti överordnade behållarmodulplatser.</span><span class="sxs-lookup"><span data-stu-id="e8d1a-133">The following illustration shows how modules are nested inside parent container module slots.</span></span>

![Kapslade moduler](../commerce/media/basic-module-nesting.png)

## <a name="add-or-remove-modules"></a><span data-ttu-id="e8d1a-135">Lägg till eller ta bort moduler</span><span class="sxs-lookup"><span data-stu-id="e8d1a-135">Add or remove modules</span></span>

<span data-ttu-id="e8d1a-136">I följande procedurer beskrivs hur du lägger till och tar bort moduler.</span><span class="sxs-lookup"><span data-stu-id="e8d1a-136">The following procedures describe how to add and remove modules.</span></span>

### <a name="add-a-module"></a><span data-ttu-id="e8d1a-137">Lägg till modul</span><span class="sxs-lookup"><span data-stu-id="e8d1a-137">Add a module</span></span>

<span data-ttu-id="e8d1a-138">För att lägga till en modul till en plats eller behållare på en sida, följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="e8d1a-138">To add a module to a slot or container on a page, follow these steps.</span></span>

1. <span data-ttu-id="e8d1a-139">I dispositionsrutan till vänster väljer du en behållare eller en plats som en underordnad modul kan läggas till i.</span><span class="sxs-lookup"><span data-stu-id="e8d1a-139">In the outline pane on the left, select a container or slot that a child module can be added to.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e8d1a-140">Moduldesignern definierar listan med moduler som kan läggas till i en specifik modulplats.</span><span class="sxs-lookup"><span data-stu-id="e8d1a-140">The module designer defines the list of modules types that can be added to a specific module slot.</span></span> <span data-ttu-id="e8d1a-141">Mallförfattare kan sedan förfina de tillåtna modulernas alternativ så att du kan garantera en konsekvent sökmotorsoptimering (SEO) och redigera effektiviteten för alla sidor som skapas från en viss mall.</span><span class="sxs-lookup"><span data-stu-id="e8d1a-141">Template authors can then refine the allowed module options to help guarantee consistent search engine optimization (SEO) and authoring efficiency for all the pages pages that are built from a specific template.</span></span>

1. <span data-ttu-id="e8d1a-142">Markera knappen med punkter för modulen (**...**) och välj sedan **Lägg till modul**.</span><span class="sxs-lookup"><span data-stu-id="e8d1a-142">Select the ellipsis button (**...**) for the module, and then select **Add Module**.</span></span> <span data-ttu-id="e8d1a-143">Dialogrutan **Lägg till modul** visas.</span><span class="sxs-lookup"><span data-stu-id="e8d1a-143">The **Add Module** dialog box appears.</span></span> <span data-ttu-id="e8d1a-144">Denna dialogruta filtreras automatiskt så att den bara visar moduler som stöds i den valda behållaren eller platsen.</span><span class="sxs-lookup"><span data-stu-id="e8d1a-144">This dialog box is automatically filtered so that it shows only modules that are supported in the selected container or slot.</span></span> <span data-ttu-id="e8d1a-145">Listan med moduler bestäms av sidans mall eller definition för behållarmodul.</span><span class="sxs-lookup"><span data-stu-id="e8d1a-145">The list of modules is determined by the page's template or the container module definition.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e8d1a-146">Om en behållare eller en plats inte stöder nya underordnade moduler är alternativet **Lägg till modul** inte tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="e8d1a-146">If a container or slot doesn't support new child modules, the **Add Module** option is unavailable.</span></span>

1. <span data-ttu-id="e8d1a-147">Sök efter och markera en modul som ska läggas till på sidan i dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="e8d1a-147">In the dialog box, search for and select a module to add to your page.</span></span>

    > [!TIP]
    > <span data-ttu-id="e8d1a-148">**Funktion** och **fokus** är bra modultyper som nybörjare kan arbeta med.</span><span class="sxs-lookup"><span data-stu-id="e8d1a-148">**Feature** and **Hero** are good module types for beginners to work with.</span></span>

1. <span data-ttu-id="e8d1a-149">Klicka på **OK** om du vill lägga till den valda modulen i den valda behållaren eller platsen på sidan.</span><span class="sxs-lookup"><span data-stu-id="e8d1a-149">Select **OK** to add the selected module to the selected container or slot on your page.</span></span>

### <a name="remove-a-module"></a><span data-ttu-id="e8d1a-150">Ta bort en modul</span><span class="sxs-lookup"><span data-stu-id="e8d1a-150">Remove a module</span></span>

<span data-ttu-id="e8d1a-151">För att ta bort en modul från en plats eller behållare på en sida, följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="e8d1a-151">To remove a module from a slot or container on a page, follow these steps.</span></span>

1. <span data-ttu-id="e8d1a-152">Markera ellipsknappen bredvid namnet på den modul som du vill ta bort i dispositionsrutan till vänster och markera sedan knappen papperskorgen.</span><span class="sxs-lookup"><span data-stu-id="e8d1a-152">In the outline pane on the left, select the ellipsis button next to the name of the module to remove, and then select the trash can button.</span></span>
1. <span data-ttu-id="e8d1a-153">När du uppmanas att bekräfta att du vill ta bort modulen väljer du **OK**.</span><span class="sxs-lookup"><span data-stu-id="e8d1a-153">When you're prompted to confirm that you want to remove the module, select **OK**.</span></span>

## <a name="configure-modules"></a><span data-ttu-id="e8d1a-154">Konfigurera moduler</span><span class="sxs-lookup"><span data-stu-id="e8d1a-154">Configure modules</span></span>

<span data-ttu-id="e8d1a-155">I följande procedurer beskrivs hur du konfigurerar innehåll och behållarmoduler.</span><span class="sxs-lookup"><span data-stu-id="e8d1a-155">The following procedures describe how to configure content and container modules.</span></span>

### <a name="configure-a-content-module"></a><span data-ttu-id="e8d1a-156">Konfigurera en innehållsmodul</span><span class="sxs-lookup"><span data-stu-id="e8d1a-156">Configure a content module</span></span>

<span data-ttu-id="e8d1a-157">Om du vill konfigurera en innehållsmodul på en sida följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="e8d1a-157">To configure a content module on a page, follow these steps.</span></span>

1. <span data-ttu-id="e8d1a-158">I dispositionsfönstret till vänster väljer du en innehållsmodultyp (t.ex. **innehåll**, **fokus** eller **banderoll**).</span><span class="sxs-lookup"><span data-stu-id="e8d1a-158">In the outline pane on the left, select a content module type (for example, **Feature**, **Hero**, or **Banner**).</span></span>
1. <span data-ttu-id="e8d1a-159">I egenskapsrutan till höger expanderar du de kapslade kontrollerna genom att markera rubrikerna och ange önskade kontrollvärden.</span><span class="sxs-lookup"><span data-stu-id="e8d1a-159">In the properties pane on the right, expand the nested controls by selecting the headers, and set any required control values.</span></span>
1. <span data-ttu-id="e8d1a-160">Om egenskapsfönstret har ett avsnitt för **datakonfiguration**, markerar du det för att expandera det.</span><span class="sxs-lookup"><span data-stu-id="e8d1a-160">If the properties pane has a **Data Configuration** section, select it to expand it.</span></span> <span data-ttu-id="e8d1a-161">Gå annars till steg 5.</span><span class="sxs-lookup"><span data-stu-id="e8d1a-161">Otherwise, go to step 5.</span></span>
1. <span data-ttu-id="e8d1a-162">Om det finns en knapp för att **Lägga till datakälla** markerar du den och markerar sedan de innehållsobjekt som ska läggas till.</span><span class="sxs-lookup"><span data-stu-id="e8d1a-162">If there is a **Add Data Source** button, select it, and then select the content items to add.</span></span>
1. <span data-ttu-id="e8d1a-163">Ange inställningar för alla nödvändiga eller önskade modulkontroller.</span><span class="sxs-lookup"><span data-stu-id="e8d1a-163">Enter settings for any required or desired module controls.</span></span>
1. <span data-ttu-id="e8d1a-164">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="e8d1a-164">Select **Save**.</span></span>

### <a name="configure-a-container-module"></a><span data-ttu-id="e8d1a-165">Konfigurera en behållarmodul</span><span class="sxs-lookup"><span data-stu-id="e8d1a-165">Configure a container module</span></span>

<span data-ttu-id="e8d1a-166">Om du vill konfigurera en behållarmodul på en sida följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="e8d1a-166">To configure a container module on a page, follow these steps.</span></span>

1. <span data-ttu-id="e8d1a-167">Välj en behållarmodul på sidan (t.ex. en karusell eller en flytande behållarmodul).</span><span class="sxs-lookup"><span data-stu-id="e8d1a-167">Select a container module on your page (for example, a carousel or fluid container module).</span></span>
1. <span data-ttu-id="e8d1a-168">I egenskapsrutan till höger expanderar du de kapslade kontrollerna genom att markera rubrikerna och ange önskade kontrollvärden.</span><span class="sxs-lookup"><span data-stu-id="e8d1a-168">In the properties pane on the right, expand the nested controls by selecting the headers, and set any required control values.</span></span>
1. <span data-ttu-id="e8d1a-169">I dispositionsfönstret till vänster väljer du ellipsknappen bredvid namnet på antingen behållaren eller valfri plats i behållaren och välj sedan **Lägg till modul**.</span><span class="sxs-lookup"><span data-stu-id="e8d1a-169">In the outline pane on the left, select the ellipsis button next to the name of either the container or any slots inside the container, and then select **Add Module**.</span></span> <span data-ttu-id="e8d1a-170">Lägg sedan till underordnade moduler i den valda behållaren.</span><span class="sxs-lookup"><span data-stu-id="e8d1a-170">Then add child modules to the selected container.</span></span> <span data-ttu-id="e8d1a-171">Mer information finns i proceduren [Lägg till en modul](#add-a-module) tidigare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="e8d1a-171">For more information, see the [Add a module](#add-a-module) procedure earlier in this topic.</span></span>
1. <span data-ttu-id="e8d1a-172">Om det finns flera underordnade moduler på samma nivå i en överordnad behållare kan du ändra deras visningsordning i den överordnade behållaren.</span><span class="sxs-lookup"><span data-stu-id="e8d1a-172">If multiple child modules exist as siblings in a parent container, you can change their display order in the parent container.</span></span> <span data-ttu-id="e8d1a-173">Välj ellipsknappen för en modul och använd sedan knapparna uppåtpil och nedåtpil.</span><span class="sxs-lookup"><span data-stu-id="e8d1a-173">Select the ellipsis button for a module, and then use the up arrow and down arrow buttons.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e8d1a-174">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="e8d1a-174">Additional resources</span></span>

[<span data-ttu-id="e8d1a-175">Översikt över mallar och layouter</span><span class="sxs-lookup"><span data-stu-id="e8d1a-175">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="e8d1a-176">Arbeta med mallar</span><span class="sxs-lookup"><span data-stu-id="e8d1a-176">Work with templates</span></span>](work-with-templates.md)

[<span data-ttu-id="e8d1a-177">Arbeta med förinställda layouter</span><span class="sxs-lookup"><span data-stu-id="e8d1a-177">Work with preset layouts</span></span>](work-with-layouts.md)

[<span data-ttu-id="e8d1a-178">Arbeta med fragment</span><span class="sxs-lookup"><span data-stu-id="e8d1a-178">Work with fragments</span></span>](work-with-fragments.md)

[<span data-ttu-id="e8d1a-179">Lägg till en behållarmodul på en sida</span><span class="sxs-lookup"><span data-stu-id="e8d1a-179">Add a container module to a page</span></span>](add-container-module.md)

[<span data-ttu-id="e8d1a-180">Lägg till modul för innehållsplacering till en sida</span><span class="sxs-lookup"><span data-stu-id="e8d1a-180">Add content placement modules to a page</span></span>](add-content-placement-modules.md)

[<span data-ttu-id="e8d1a-181">Arbeta med publiceringsgrupper</span><span class="sxs-lookup"><span data-stu-id="e8d1a-181">Work with publish groups</span></span>](publish-groups.md)

