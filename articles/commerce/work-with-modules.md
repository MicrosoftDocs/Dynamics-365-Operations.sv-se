---
title: Arbeta med moduler
description: I det här avsnittet beskrivs hur och när du ska använda moduler i Microsoft Dynamics 365 Commerce.
author: phinneyridge
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: stuharg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 6d872719d3b1aa27ccfdcf36d7739c883e7b4996
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801371"
---
# <a name="work-with-modules"></a><span data-ttu-id="3d527-103">Arbeta med moduler</span><span class="sxs-lookup"><span data-stu-id="3d527-103">Work with modules</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="3d527-104">I det här avsnittet beskrivs hur och när du ska använda moduler i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="3d527-104">This topic describes how and when to use modules in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="3d527-105">Moduler är logiska byggblock som utgör sidans struktur och har olika syfte och omfång.</span><span class="sxs-lookup"><span data-stu-id="3d527-105">Modules are logical building blocks that make up your page structure, and they have various purposes and scopes.</span></span> <span data-ttu-id="3d527-106">Vissa moduler är behållare på hög nivå, och de är bara avsedda att innehålla och organisera andra moduler (underordnade moduler).</span><span class="sxs-lookup"><span data-stu-id="3d527-106">Some modules are high-level containers, and their only purpose is to hold and organize other modules (child modules).</span></span> <span data-ttu-id="3d527-107">Andra moduler, t.ex. en enkel bildplaceringsmodul, har ett mycket specifikt syfte.</span><span class="sxs-lookup"><span data-stu-id="3d527-107">Other modules, such as a simple image placement module, have a very specific purpose.</span></span> <span data-ttu-id="3d527-108">Andra moduler, till exempel en karusellmodul, ligger någonstans mellan dessa två kategorier.</span><span class="sxs-lookup"><span data-stu-id="3d527-108">Other modules, such as a carousel module, fall somewhere between those two categories.</span></span>

<span data-ttu-id="3d527-109">Webbplatsen Dynamics 365 Commerce innehåller som standard ett modulbibliotek som gör att du kan uppnå de flesta grundläggande näthandelsscenarier.</span><span class="sxs-lookup"><span data-stu-id="3d527-109">By default, your Dynamics 365 Commerce site includes a module library that lets you achieve most basic e-Commerce scenarios.</span></span> <span data-ttu-id="3d527-110">Du bör kunna skapa en slutpunkt-till-slutpunkt-plats för näthandel genom att bara använda de här modulerna.</span><span class="sxs-lookup"><span data-stu-id="3d527-110">You should be able to construct an end-to-end e-Commerce site just by using these modules.</span></span> <span data-ttu-id="3d527-111">Men du kanske också vill anpassa dessa moduler eller bygga nya, anpassade moduler för specifika behov.</span><span class="sxs-lookup"><span data-stu-id="3d527-111">However, you might also want to customize these modules or build new, custom modules for specific needs.</span></span> <span data-ttu-id="3d527-112">Om du vill skapa anpassade moduler kan du använda en moduldesign-SDK (Software Development Kit) som hjälper dig att skapa ett anpassat bibliotek för modulen.</span><span class="sxs-lookup"><span data-stu-id="3d527-112">If you want to build custom modules, a module design software development kit (SDK) is available to help you create a custom module library.</span></span>

## <a name="container-modules-and-slots"></a><span data-ttu-id="3d527-113">Moduler och platser för behållare</span><span class="sxs-lookup"><span data-stu-id="3d527-113">Container modules and slots</span></span>

<span data-ttu-id="3d527-114">Som tidigare nämnts är vissa moduler avsedda att innehålla underordnade moduler.</span><span class="sxs-lookup"><span data-stu-id="3d527-114">As was mentioned earlier, some modules are designed to hold child modules.</span></span> <span data-ttu-id="3d527-115">Dessa moduler kallas *behållare*, och de tillåter hierarkier för kapslade moduler.</span><span class="sxs-lookup"><span data-stu-id="3d527-115">These modules are known as *containers*, and they allow for hierarchies of nested modules.</span></span> <span data-ttu-id="3d527-116">Behållarmoduler inkluderar *platser*.</span><span class="sxs-lookup"><span data-stu-id="3d527-116">Container modules include *slots*.</span></span> <span data-ttu-id="3d527-117">Platser används för att hantera layout och syfte för underordnade moduler i behållaren.</span><span class="sxs-lookup"><span data-stu-id="3d527-117">Slots are used to handle the layout and purpose of child modules in the container.</span></span> <span data-ttu-id="3d527-118">Ett exempel är en grundläggande sidbehållarmodul (en modul på översta nivån för alla sidor) som definierar flera viktiga platser:</span><span class="sxs-lookup"><span data-stu-id="3d527-118">An example is a basic page container module (a top-level module for any page) that defines several important slots:</span></span>

- <span data-ttu-id="3d527-119">En sidhuvudplats</span><span class="sxs-lookup"><span data-stu-id="3d527-119">A header slot</span></span>
- <span data-ttu-id="3d527-120">En plats för underrubrik</span><span class="sxs-lookup"><span data-stu-id="3d527-120">A sub-header slot</span></span>
- <span data-ttu-id="3d527-121">En huvudplats</span><span class="sxs-lookup"><span data-stu-id="3d527-121">A main slot</span></span>
- <span data-ttu-id="3d527-122">En sidfotsplats</span><span class="sxs-lookup"><span data-stu-id="3d527-122">A footer slot</span></span>
- <span data-ttu-id="3d527-123">En plats för underrubrik</span><span class="sxs-lookup"><span data-stu-id="3d527-123">A sub-footer slot</span></span>

<span data-ttu-id="3d527-124">Modulens utvecklare definierar dessa platser och avgör vilka underordnade moduler och hur många underordnade moduler som kan placeras direkt inuti det.</span><span class="sxs-lookup"><span data-stu-id="3d527-124">The module's developer defines these slots, and determines which child modules and how many child modules can be put directly inside it.</span></span> <span data-ttu-id="3d527-125">Sidhuvudsplatsen kan t.ex. stödja bara en av modulerna i typen **Modul för sidhuvud** medan brödtextplatsen kan stödja ett obegränsat antal moduler av vilken typ som helst (utom andra sidbehållarmoduler).</span><span class="sxs-lookup"><span data-stu-id="3d527-125">For example, the header slot might support only one module of the **Header Module** type, whereas the body slot might support an unlimited number of modules of any type (except other page container modules).</span></span>

<span data-ttu-id="3d527-126">I redigeringsverktygen behöver inte sidförfattare veta i förväg vilka moduler som kan och inte kan placeras på varje plats.</span><span class="sxs-lookup"><span data-stu-id="3d527-126">In the authoring tools, page authors don't have to know in advance which modules can and can't be put in each slot.</span></span> <span data-ttu-id="3d527-127">När sidans författare väljer en plats och sedan försöker välja en modul som ska läggas till i den, visas en filtrerad vy av modulens typer som stöds för platsen.</span><span class="sxs-lookup"><span data-stu-id="3d527-127">When page authors select a slot and then try to select a module to add to it, they see a filtered view of module types that are supported for that slot.</span></span>

## <a name="content-modules"></a><span data-ttu-id="3d527-128">Innehållsmoduler</span><span class="sxs-lookup"><span data-stu-id="3d527-128">Content modules</span></span>

<span data-ttu-id="3d527-129">Innehållsmoduler innehåller innehålls- och medieelement, t.ex. text (t.ex. rubriker, stycken och länkar) eller tillgångsreferenser (t.ex. bilder, video och PDF-filer).</span><span class="sxs-lookup"><span data-stu-id="3d527-129">Content modules contain content and media elements, such as text (for example, headlines, paragraphs, and links) or asset references (for example, images, video, and PDFs).</span></span> <span data-ttu-id="3d527-130">Bland de vanligaste typerna av innehållsmoduler finns innehållsblock, textblock och annonsmoduler.</span><span class="sxs-lookup"><span data-stu-id="3d527-130">Typical content module types include content block, text block, and promo banner modules.</span></span> <span data-ttu-id="3d527-131">Moduler av dessa tre typer kan innehålla text eller media och de behöver inte några underordnade moduler för att göra något synligt på en sida.</span><span class="sxs-lookup"><span data-stu-id="3d527-131">Modules of these three types can contain text or media, and they don't require any child modules to make something visible on a page.</span></span>

<span data-ttu-id="3d527-132">De flesta vanliga, dagliga och innehållsredigeringsaktiviteterna omfattar innehållsmoduler, främst på grund av att dessa moduler definierar det faktiska innehållet som återges i sina överordnade behållarmoduler.</span><span class="sxs-lookup"><span data-stu-id="3d527-132">The majority of typical, day-to-day page and content authoring activities involve content modules, primarily because these modules define the actual content that is rendered in their parent container modules.</span></span> <span data-ttu-id="3d527-133">Många innehållsmoduler är tillgängliga och dessa moduler är vanligtvis de sista delarna som du lägger till i en sidas hierarki med kapslade moduler.</span><span class="sxs-lookup"><span data-stu-id="3d527-133">Many content modules are available, and these modules are typically the last pieces that you will add to a page's hierarchy of nested modules.</span></span>

<span data-ttu-id="3d527-134">I följande bild visas hur moduler kapslas inuti överordnade behållarmodulplatser.</span><span class="sxs-lookup"><span data-stu-id="3d527-134">The following illustration shows how modules are nested inside parent container module slots.</span></span>

![Kapslade moduler](../commerce/media/basic-module-nesting.png)

## <a name="add-or-remove-modules"></a><span data-ttu-id="3d527-136">Lägg till eller ta bort moduler</span><span class="sxs-lookup"><span data-stu-id="3d527-136">Add or remove modules</span></span>

<span data-ttu-id="3d527-137">I följande procedurer beskrivs hur du lägger till och tar bort moduler.</span><span class="sxs-lookup"><span data-stu-id="3d527-137">The following procedures describe how to add and remove modules.</span></span>

### <a name="add-a-module"></a><span data-ttu-id="3d527-138">Lägg till modul</span><span class="sxs-lookup"><span data-stu-id="3d527-138">Add a module</span></span>

<span data-ttu-id="3d527-139">För att lägga till en modul till en plats eller behållare på en sida, följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="3d527-139">To add a module to a slot or container on a page, follow these steps.</span></span>

1. <span data-ttu-id="3d527-140">I dispositionsfönstret till vänster eller direkt i huvudarbetsytan, välj en behållare eller fack som underordnade moduler kan läggas till.</span><span class="sxs-lookup"><span data-stu-id="3d527-140">In the outline pane on the left or directly in the main canvas, select a container or slot to which a child module can be added.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3d527-141">Moduldesignern definierar listan med moduler som kan läggas till i en specifik modulplats.</span><span class="sxs-lookup"><span data-stu-id="3d527-141">The module designer defines the list of modules types that can be added to a specific module slot.</span></span> <span data-ttu-id="3d527-142">Mallförfattare kan sedan förfina de tillåtna modulernas alternativ så att du kan garantera en konsekvent sökmotoroptimering (SEO) och redigera effektiviteten för alla sidor som skapas från en viss mall.</span><span class="sxs-lookup"><span data-stu-id="3d527-142">Template authors can then refine the allowed module options to help guarantee consistent search engine optimization (SEO) and authoring efficiency for all the pages that are built from a specific template.</span></span> <span data-ttu-id="3d527-143">Bär du lägger till en modul till en plats filtreras dialogrutan **Lägg till modul** automatiskt så att den bara visar moduler som stöds i den valda behållaren eller platsen.</span><span class="sxs-lookup"><span data-stu-id="3d527-143">When adding a module to a slot, the **Add Module** dialog box is automatically filtered so that it shows only modules that are supported in the selected container or slot.</span></span> <span data-ttu-id="3d527-144">Listan med tillåtna moduler bestäms av sidans mall eller definition för behållarmodul.</span><span class="sxs-lookup"><span data-stu-id="3d527-144">This list of allowed modules is determined by the page's template or the container's module definition.</span></span>

1. <span data-ttu-id="3d527-145">Om du använder konturfönstret väljer du tre punkter (**...**) bredvid modulnamnet och väljer **Lägg till modul**.</span><span class="sxs-lookup"><span data-stu-id="3d527-145">If using the outline pane, select the ellipsis (**...**) next to the module name, and then select **Add Module**.</span></span> <span data-ttu-id="3d527-146">Om du använder kontrollerna direkt på arbetsytan markerar du plustecknet (**+**) i en tom plats eller invid den valda modulen och väljer sedan **Lägg till modul**.</span><span class="sxs-lookup"><span data-stu-id="3d527-146">If using the controls directly within the canvas, select the plus symbol (**+**) in an empty slot or adjacent to the currently selected module, and then select **Add Module**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3d527-147">Om en behållare eller en plats inte stöder nya underordnade moduler är alternativet **Lägg till modul** inte tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="3d527-147">If a container or slot doesn't support new child modules, the **Add Module** option is unavailable.</span></span>

1. <span data-ttu-id="3d527-148">I dialogrutan **Lägg till modul** välj en modul för att lägga till din sida.</span><span class="sxs-lookup"><span data-stu-id="3d527-148">In the **Add Module** dialog box, select a module to add to your page.</span></span>

    > [!TIP]
    > <span data-ttu-id="3d527-149">**Innehållsblock** är en god modultyp som den nybörjare kan arbeta med.</span><span class="sxs-lookup"><span data-stu-id="3d527-149">**Content block** is a good module type for beginners to work with.</span></span>

1. <span data-ttu-id="3d527-150">Klicka på **OK** om du vill lägga till den valda modulen i den valda behållaren eller platsen på sidan.</span><span class="sxs-lookup"><span data-stu-id="3d527-150">Select **OK** to add the selected module to the selected container or slot on your page.</span></span>

### <a name="remove-a-module"></a><span data-ttu-id="3d527-151">Ta bort en modul</span><span class="sxs-lookup"><span data-stu-id="3d527-151">Remove a module</span></span>

<span data-ttu-id="3d527-152">För att ta bort en modul från en plats eller behållare på en sida, följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="3d527-152">To remove a module from a slot or container on a page, follow these steps.</span></span>

1. <span data-ttu-id="3d527-153">I dispositionsrutan till vänster, välj ellipsknappen (**...**) bredvid namnet på det modul som du vill ta bort och markera sedan knappen papperskorgen.</span><span class="sxs-lookup"><span data-stu-id="3d527-153">In the outline pane on the left, select the ellipsis (**...**) next to the name of the module to be removed, and then select the trash can symbol.</span></span> <span data-ttu-id="3d527-154">Alternativt kan du, på huvudarbetsytan, välja papperskorgssymbol i verktygsfältet för en markerad modul.</span><span class="sxs-lookup"><span data-stu-id="3d527-154">Alternately, in the main canvas you can select the trash can symbol on a selected module's toolbar.</span></span>
1. <span data-ttu-id="3d527-155">När du uppmanas att bekräfta att du vill ta bort modulen väljer du **OK**.</span><span class="sxs-lookup"><span data-stu-id="3d527-155">When prompted to confirm that you want to remove the module, select **OK**.</span></span>

## <a name="move-a-module-to-a-new-position"></a><span data-ttu-id="3d527-156">Flytta en fokusmodul på en ny position</span><span class="sxs-lookup"><span data-stu-id="3d527-156">Move a module to a new position</span></span>

<span data-ttu-id="3d527-157">Om du vill flytta en modul till en ny plats på sidan använder du någon av följande metoder.</span><span class="sxs-lookup"><span data-stu-id="3d527-157">To move a module to a new position within your page, use any of the following methods.</span></span>

### <a name="move-a-module-using-the-outline-pane"></a><span data-ttu-id="3d527-158">Flytta en modul med hjälp av dispositionsfönstret</span><span class="sxs-lookup"><span data-stu-id="3d527-158">Move a module using the outline pane</span></span>

<span data-ttu-id="3d527-159">Flytta en modul med hjälp av dispositionsfönstret enligt följande instruktioner.</span><span class="sxs-lookup"><span data-stu-id="3d527-159">To move a module using the outline pane, follow these steps.</span></span>

1. <span data-ttu-id="3d527-160">Markera och håll modulen du vill flytta i dispositionsfönstret och dra sedan modulen till en ny position i dispositionen.</span><span class="sxs-lookup"><span data-stu-id="3d527-160">Select and hold the module you want to move in the outline pane, then drag the module to a new position in the outline.</span></span> <span data-ttu-id="3d527-161">Den blå linjen i dispositionen och på arbetsytan anger var modulen kan placeras.</span><span class="sxs-lookup"><span data-stu-id="3d527-161">The blue line in the outline and on the canvas indicates where the module can be placed.</span></span>
1. <span data-ttu-id="3d527-162">Släpp modulen om du vill släppa den på den nya platsen.</span><span class="sxs-lookup"><span data-stu-id="3d527-162">Release the module to drop it into the new position.</span></span>

### <a name="move-a-module-directly-within-the-canvas"></a><span data-ttu-id="3d527-163">Flytta en modul direkt på arbetsytan</span><span class="sxs-lookup"><span data-stu-id="3d527-163">Move a module directly within the canvas</span></span>

<span data-ttu-id="3d527-164">Flytta en modul direkt i arbetsytan enligt följande instruktioner.</span><span class="sxs-lookup"><span data-stu-id="3d527-164">To move a module directly within the canvas, follow these steps.</span></span>

1. <span data-ttu-id="3d527-165">Välj den modul du vill flytta på arbetsytan.</span><span class="sxs-lookup"><span data-stu-id="3d527-165">Select the module you want to move in the canvas.</span></span> 
1. <span data-ttu-id="3d527-166">Markera antingen en pil som pekar uppåt eller nedåt i modulens verktygsfält och dra sedan pilen till en ny plats på sidan.</span><span class="sxs-lookup"><span data-stu-id="3d527-166">Select either an upward or downward pointing arrow symbol in the module's toolbar, and then drag the arrow to a new position on the page.</span></span> <span data-ttu-id="3d527-167">Den blå linjen i arbetsytan och dispositionen anger var modulen kan placeras.</span><span class="sxs-lookup"><span data-stu-id="3d527-167">The blue line in the canvas and outline indicates where the module can be placed.</span></span> <span data-ttu-id="3d527-168">Om en modul inte kan flyttas uppåt eller nedåt, kommer den att vara nedtonad.</span><span class="sxs-lookup"><span data-stu-id="3d527-168">If a module cannot be moved up or down, that arrow symbol will be grayed out.</span></span> 
1. <span data-ttu-id="3d527-169">Släpp modulen om du vill släppa den på den nya platsen.</span><span class="sxs-lookup"><span data-stu-id="3d527-169">Release the module to drop it into the new position.</span></span>

### <a name="move-a-module-using-the-ellipsis-menu"></a><span data-ttu-id="3d527-170">Flytta en modul med hjälp av ellips-menyn</span><span class="sxs-lookup"><span data-stu-id="3d527-170">Move a module using the ellipsis menu</span></span>

<span data-ttu-id="3d527-171">Flytta en modul med hjälp av ellips-menyn enligt följande instruktioner.</span><span class="sxs-lookup"><span data-stu-id="3d527-171">To move a module using the ellipsis menu, follow these steps.</span></span>

1. <span data-ttu-id="3d527-172">Välj en modul antingen i dispositionen eller på arbetsytan.</span><span class="sxs-lookup"><span data-stu-id="3d527-172">Select a module in either the outline or the canvas.</span></span>
1. <span data-ttu-id="3d527-173">Markera tre punkter (**...**) bredvid modulens namn i antingen dispositionsfönstret eller i den markerade modulens verktygsfält på arbetsytan.</span><span class="sxs-lookup"><span data-stu-id="3d527-173">Select the ellipsis (**...**) next to the module's name in the outline pane, or in the module's toolbar in the canvas.</span></span>
1. <span data-ttu-id="3d527-174">Om modulen kan flyttas upp eller ned i behållaren eller platsen visas alternativ för **Flytta upp** eller **Flytta ned**.</span><span class="sxs-lookup"><span data-stu-id="3d527-174">If the module can be moved up or down within the container or slot, you will see options for **Move up** or **Move down**.</span></span> <span data-ttu-id="3d527-175">Markera alternativet flytta om du vill flytta modulen uppåt eller nedåt i förhållande till objekt på samma nivå.</span><span class="sxs-lookup"><span data-stu-id="3d527-175">Select the desired move option to move the module up or down relative to its siblings.</span></span>

## <a name="configure-modules"></a><span data-ttu-id="3d527-176">Konfigurera moduler</span><span class="sxs-lookup"><span data-stu-id="3d527-176">Configure modules</span></span>

<span data-ttu-id="3d527-177">I följande procedurer beskrivs hur du konfigurerar innehåll och behållarmoduler.</span><span class="sxs-lookup"><span data-stu-id="3d527-177">The following procedures describe how to configure content and container modules.</span></span>

### <a name="configure-a-content-module"></a><span data-ttu-id="3d527-178">Konfigurera en innehållsmodul</span><span class="sxs-lookup"><span data-stu-id="3d527-178">Configure a content module</span></span>

<span data-ttu-id="3d527-179">Om du vill konfigurera en innehållsmodul på en sida följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="3d527-179">To configure a content module on a page, follow these steps.</span></span>

1. <span data-ttu-id="3d527-180">I dispositionsfönstret till vänster expanderar du trädet och väljer en innehållsmodul (t.ex. **innehållsblock**).</span><span class="sxs-lookup"><span data-stu-id="3d527-180">In the outline pane on the left, expand the tree and select any content module (for example, **Content block**).</span></span> <span data-ttu-id="3d527-181">Alternativt kan du välja modulen i huvudarbetsytan.</span><span class="sxs-lookup"><span data-stu-id="3d527-181">Alternately, you can select the module in the main canvas.</span></span>
1. <span data-ttu-id="3d527-182">I fönstret för modulegenskaper till höger anger du egenskaper för alla önskade modulkontroller.</span><span class="sxs-lookup"><span data-stu-id="3d527-182">In the module properties pane on the right, enter properties for any desired module controls.</span></span>
1. <span data-ttu-id="3d527-183">På kommandofältet, välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="3d527-183">On the command bar, select **Save**.</span></span> <span data-ttu-id="3d527-184">Då uppdateras även arbetsytan med förhandsgranskning.</span><span class="sxs-lookup"><span data-stu-id="3d527-184">This will also refresh the preview canvas.</span></span>

### <a name="edit-module-text-properties"></a><span data-ttu-id="3d527-185">Redigera egenskaper för textmodul</span><span class="sxs-lookup"><span data-stu-id="3d527-185">Edit module text properties</span></span>

<span data-ttu-id="3d527-186">Modulens textegenskaper som inte är skrivskyddade kan redigeras direkt på arbetsytan.</span><span class="sxs-lookup"><span data-stu-id="3d527-186">Module text properties that are not read-only can be edited directly in the canvas.</span></span>

<span data-ttu-id="3d527-187">Om du vill redigera textegenskaperna för modulen följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="3d527-187">To edit module text properties, follow these steps.</span></span>

1. <span data-ttu-id="3d527-188">Markera textkontrollen på arbetsytan och placera markören där du vill redigera texten.</span><span class="sxs-lookup"><span data-stu-id="3d527-188">Select the text control in the canvas, then place your cursor where you wish to edit text.</span></span>
1. <span data-ttu-id="3d527-189">Ange ditt textinnehåll.</span><span class="sxs-lookup"><span data-stu-id="3d527-189">Enter your text content.</span></span>
1. <span data-ttu-id="3d527-190">Välj var som helst utanför textinnehållet om du vill fortsätta redigera annat innehåll.</span><span class="sxs-lookup"><span data-stu-id="3d527-190">Select anywhere outside the text content to continue editing other content.</span></span>

### <a name="inline-image-selection"></a><span data-ttu-id="3d527-191">Markering av infogad bild</span><span class="sxs-lookup"><span data-stu-id="3d527-191">Inline image selection</span></span>

<span data-ttu-id="3d527-192">Modulbilder som inte är skrivskyddade kan ändras direkt från arbetsytan.</span><span class="sxs-lookup"><span data-stu-id="3d527-192">Module images that are not read-only can be changed directly from the canvas.</span></span>

<span data-ttu-id="3d527-193">Om du vill välja en ny bild för innehållsmodul följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="3d527-193">To choose a new image for a content module, follow these steps.</span></span>

1. <span data-ttu-id="3d527-194">Dubbelklicka på bilden i arbetsytan.</span><span class="sxs-lookup"><span data-stu-id="3d527-194">In the canvas, double-click the image.</span></span> <span data-ttu-id="3d527-195">Detta gör att fönstret för medieväljaren visas.</span><span class="sxs-lookup"><span data-stu-id="3d527-195">This will bring up the media picker window.</span></span>
1. <span data-ttu-id="3d527-196">Sök reda på och välj en ny bild som du vill använda och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="3d527-196">Find and select a new image you want to use, and then select **OK**.</span></span> <span data-ttu-id="3d527-197">Den nya bilden återges nu på arbetsytan.</span><span class="sxs-lookup"><span data-stu-id="3d527-197">The new image is now rendered in the canvas.</span></span>

### <a name="configure-a-container-module"></a><span data-ttu-id="3d527-198">Konfigurera en behållarmodul</span><span class="sxs-lookup"><span data-stu-id="3d527-198">Configure a container module</span></span>

<span data-ttu-id="3d527-199">Om du vill konfigurera en behållarmodul på en sida följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="3d527-199">To configure a container module on a page, follow these steps.</span></span>

1. <span data-ttu-id="3d527-200">Välj en behållarmodul på sidan (t.ex. en karusell eller en flytande behållarmodul).</span><span class="sxs-lookup"><span data-stu-id="3d527-200">Select a container module on your page (for example, a carousel or fluid container module).</span></span>
1. <span data-ttu-id="3d527-201">I egenskapsrutan till höger expanderar du de kapslade kontrollerna genom att markera rubrikerna och ange önskade kontrollvärden.</span><span class="sxs-lookup"><span data-stu-id="3d527-201">In the properties pane on the right, expand the nested controls by selecting the headers, and set any required control values.</span></span>
1. <span data-ttu-id="3d527-202">I dispositionsfönstret till vänster väljer du ellipsknappen bredvid namnet på antingen behållaren eller valfri plats i behållaren och välj sedan **Lägg till modul**.</span><span class="sxs-lookup"><span data-stu-id="3d527-202">In the outline pane on the left, select the ellipsis button next to the name of either the container or any slots inside the container, and then select **Add Module**.</span></span> <span data-ttu-id="3d527-203">Lägg sedan till underordnade moduler i den valda behållaren.</span><span class="sxs-lookup"><span data-stu-id="3d527-203">Then, add child modules to the selected container.</span></span> <span data-ttu-id="3d527-204">Mer information finns i avsnitt [Arbeta med moduler modul](#add-a-module) tidigare i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="3d527-204">For more information, see the [Work with modules](#add-a-module) section earlier in this topic.</span></span>
1. <span data-ttu-id="3d527-205">Om det finns flera underordnade moduler på samma nivå i en överordnad behållare kan du ändra deras visningsordning i den överordnade behållaren.</span><span class="sxs-lookup"><span data-stu-id="3d527-205">If multiple child modules exist as siblings in a parent container, you can change their display order in the parent container.</span></span> <span data-ttu-id="3d527-206">Välj ellipsknappen för en modul och använd sedan knapparna uppåtpil och nedåtpil.</span><span class="sxs-lookup"><span data-stu-id="3d527-206">Select the ellipsis button for a module, and then use the up arrow and down arrow buttons.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="3d527-207">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="3d527-207">Additional resources</span></span>

[<span data-ttu-id="3d527-208">Översikt över mallar och layouter</span><span class="sxs-lookup"><span data-stu-id="3d527-208">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="3d527-209">Arbeta med mallar</span><span class="sxs-lookup"><span data-stu-id="3d527-209">Work with templates</span></span>](work-with-templates.md)

[<span data-ttu-id="3d527-210">Arbeta med förinställda layouter</span><span class="sxs-lookup"><span data-stu-id="3d527-210">Work with preset layouts</span></span>](work-with-layouts.md)

[<span data-ttu-id="3d527-211">Arbeta med fragment</span><span class="sxs-lookup"><span data-stu-id="3d527-211">Work with fragments</span></span>](work-with-fragments.md)

[<span data-ttu-id="3d527-212">Lägg till en behållarmodul på en sida</span><span class="sxs-lookup"><span data-stu-id="3d527-212">Add a container module to a page</span></span>](add-container-module.md)

[<span data-ttu-id="3d527-213">Arbeta med publiceringsgrupper</span><span class="sxs-lookup"><span data-stu-id="3d527-213">Work with publish groups</span></span>](publish-groups.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
