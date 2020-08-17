---
title: Arbeta med fragment
description: I det här avsnittet beskrivs varför, när och hur du ska använda fragment i Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 07/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: retail
ms.author: phinneyridge
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 7ae834f38fe380ce0a66f5b1968f1261af670979
ms.sourcegitcommit: 078befcd7f3531073ab2c08b365bcf132d6477b0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/31/2020
ms.locfileid: "3646001"
---
# <a name="work-with-fragments"></a><span data-ttu-id="a5233-103">Arbeta med fragment</span><span class="sxs-lookup"><span data-stu-id="a5233-103">Work with fragments</span></span> 

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="a5233-104">I det här avsnittet beskrivs varför, när och hur du ska använda fragment i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="a5233-104">This topic describes why, when, and how to use fragments in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="a5233-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="a5233-105">Overview</span></span>

<span data-ttu-id="a5233-106">Fragment gör det möjligt att använda en central redigeringsupplevelse för modulkonfigurationer som måste återanvändas på hela din webbplats.</span><span class="sxs-lookup"><span data-stu-id="a5233-106">Fragments allow for a centralized authoring experience for module configurations that must be reused throughout your site.</span></span> <span data-ttu-id="a5233-107">Sidhuvuden, sidfötter och banderoller är ofta konfigurerade som fragment, eftersom de delas på många sidor.</span><span class="sxs-lookup"><span data-stu-id="a5233-107">For example, headers, footers, and banners are often configured as fragments, because they are shared across many pages.</span></span> <span data-ttu-id="a5233-108">Du kan betrakta fragment som miniatyrer av webbsidor som kan infogas på andra sidor på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="a5233-108">You can think of fragments as miniature webpages that can be inserted into other pages on your site.</span></span> <span data-ttu-id="a5233-109">Fragment har sin egen livscykel.</span><span class="sxs-lookup"><span data-stu-id="a5233-109">Fragments have their own lifecycle.</span></span> <span data-ttu-id="a5233-110">Det innebär att de skapas, refereras, uppdateras och tas bort som oberoende enheter i redigeringsverktygen.</span><span class="sxs-lookup"><span data-stu-id="a5233-110">In other words, they are created, referenced, updated, and deleted as independent entities in the authoring tools.</span></span>

<span data-ttu-id="a5233-111">När fragment har konfigurerats kan de användas där moduler kan användas i webbplatsstrukturen.</span><span class="sxs-lookup"><span data-stu-id="a5233-111">After fragments are configured, they can be used wherever modules can be used in your site structure.</span></span> <span data-ttu-id="a5233-112">Det går att referera till fragment på sidor, i layouter, i mallar och i andra fragment.</span><span class="sxs-lookup"><span data-stu-id="a5233-112">Fragments can be referenced on pages, in layouts, in templates, and in other fragments.</span></span>

> [!NOTE]
> <span data-ttu-id="a5233-113">Fragment kan kapslas upp till sju nivåer djup inuti andra fragment.</span><span class="sxs-lookup"><span data-stu-id="a5233-113">Fragments can be nested up to seven levels deep inside other fragments.</span></span>

<span data-ttu-id="a5233-114">Om du till exempel vill marknadsföra en säsongshändelse på många sidor på webbplatsen kan du använda ett fragment.</span><span class="sxs-lookup"><span data-stu-id="a5233-114">For example, if you want to promote a seasonal event cross many pages on our site, you can use a fragment.</span></span> <span data-ttu-id="a5233-115">Det första steget i processen med att skapa ett nytt fragment är att välja vilken typ av modul du vill starta från.</span><span class="sxs-lookup"><span data-stu-id="a5233-115">The first step in the process of creating a new fragment is to select the type of module that you want to start from.</span></span> <span data-ttu-id="a5233-116">I det här exemplet kan du skapa avsnittet från en fokusmodul.</span><span class="sxs-lookup"><span data-stu-id="a5233-116">For this example, you can build the fragment from a hero module.</span></span>

> [!NOTE]
> <span data-ttu-id="a5233-117">Fragment kan skapas med alla typer av moduler.</span><span class="sxs-lookup"><span data-stu-id="a5233-117">Fragments can be built from any module type.</span></span>

<span data-ttu-id="a5233-118">Du kan sedan konfigurera fokusfragment med ditt specifika säljinnehåll.</span><span class="sxs-lookup"><span data-stu-id="a5233-118">You can then configure the hero fragment with your specific promotional content.</span></span> <span data-ttu-id="a5233-119">Du kan också lokalisera den efter behov.</span><span class="sxs-lookup"><span data-stu-id="a5233-119">You can also localize it as you require.</span></span> <span data-ttu-id="a5233-120">Det nya fristående fokusfragmentet kan sedan förbrukas som en förkonfigurerad modul på hela din webbplats.</span><span class="sxs-lookup"><span data-stu-id="a5233-120">The new stand-alone hero fragment can then be consumed as a preconfigured module throughout your site.</span></span> <span data-ttu-id="a5233-121">Du kan enkelt lägga till det i mallar, specifika sidor eller till andra fragment som kan innehålla fokusmoduler.</span><span class="sxs-lookup"><span data-stu-id="a5233-121">You can easily add it to templates, to specific pages, or to other fragments that can contain hero modules.</span></span>

<span data-ttu-id="a5233-122">Alla platser där fragmenten läggs till är referenser till det centrala fokusfragment som du har skapat.</span><span class="sxs-lookup"><span data-stu-id="a5233-122">All the places where the fragment is added are references to the central hero fragment that you created.</span></span> <span data-ttu-id="a5233-123">Om du publicerar ändringar i avsnittet visas dessa direkt på alla platser där fragmentet refereras på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="a5233-123">If you publish changes to the fragment, those changes are immediately reflected in all the places where the fragment is referenced across the site.</span></span> <span data-ttu-id="a5233-124">Därför utgör fragmenten ett kraftfullt och effektivt sätt att återanvända och centralt hantera konfigurationer på en webbplats.</span><span class="sxs-lookup"><span data-stu-id="a5233-124">Therefore, fragments provide a powerful and efficient way to reuse and centrally manage module configurations on a site.</span></span> <span data-ttu-id="a5233-125">Genom att effektivt använda dem kan du öka flexibiliteten och minska den kostnad som är kopplad till hantering av webbplatsens innehåll.</span><span class="sxs-lookup"><span data-stu-id="a5233-125">By effectively using them, you can significantly increase agility and help reduce the cost that is associated with managing site content.</span></span>

<span data-ttu-id="a5233-126">Följande bild visar hur fragment kan användas för att centralisera redigering av konfigurationer för delade moduler på en e-handelsplats.</span><span class="sxs-lookup"><span data-stu-id="a5233-126">The following illustration shows how fragments can be used to centralize authoring of shared module configurations across an e-Commerce site.</span></span>

![EN bild visar hur fragment kan användas för att centralisera redigering av konfigurationer för delade moduler på en e-handelsplats.](./media/fragment-figure1.png)

## <a name="create-a-fragment"></a><span data-ttu-id="a5233-128">Skapa ett fragment</span><span class="sxs-lookup"><span data-stu-id="a5233-128">Create a fragment</span></span>

<span data-ttu-id="a5233-129">Du kan antingen skapa ett nytt fragment eller spara en befintlig modul som ett fragment.</span><span class="sxs-lookup"><span data-stu-id="a5233-129">You can either create a new fragment or save an existing module configuration as a fragment.</span></span>

### <a name="save-an-existing-module-configuration-as-a-fragment"></a><span data-ttu-id="a5233-130">Spara en befintlig modulkonfiguration som ett fragment</span><span class="sxs-lookup"><span data-stu-id="a5233-130">Save an existing module configuration as a fragment</span></span>

<span data-ttu-id="a5233-131">Om du vill konvertera en tidigare konfigurerad modul till ett återanvändbart fragment följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="a5233-131">To convert a previously configured module to a reusable fragment, follow these steps.</span></span>

1. <span data-ttu-id="a5233-132">Öppna en sida eller mall som innehåller modulen som du vill konvertera till ett fragment.</span><span class="sxs-lookup"><span data-stu-id="a5233-132">Open a page or template that contains the module that you want to convert to a fragment.</span></span>
1. <span data-ttu-id="a5233-133">Markera den tidigare konfigurerade modulen i dispositionsrutan till vänster eller direkt i huvudarbetsytan.</span><span class="sxs-lookup"><span data-stu-id="a5233-133">In the outline pane on the left or directly in the main canvas, select the previously configured module.</span></span>
1. <span data-ttu-id="a5233-134">Markera tre punkter (**...**) bredvid modulens namn i antingen dispositionsfönstret eller i den markerade modulens verktygsfält på arbetsytan.</span><span class="sxs-lookup"><span data-stu-id="a5233-134">Select the ellipsis (**...**) next to the name of the module in either the outline pane or the selected module's toolbar in the canvas.</span></span> 
1. <span data-ttu-id="a5233-135">Välj **dela som sidfragment**.</span><span class="sxs-lookup"><span data-stu-id="a5233-135">Select **Share as Page Fragment**.</span></span> 
1. <span data-ttu-id="a5233-136">I dialogrutan **Spara som sidfragment** anger du namnet för fragmentet.</span><span class="sxs-lookup"><span data-stu-id="a5233-136">In the **Save as Page Fragment** dialog box, enter a name for the fragment.</span></span>
1. <span data-ttu-id="a5233-137">Välj **OK** om du vill spara modulens konfiguration som ett fragment som kan läggas till på andra sidor.</span><span class="sxs-lookup"><span data-stu-id="a5233-137">Select **OK** to save the module configuration as a fragment that can be added to other pages.</span></span>

<span data-ttu-id="a5233-138">Följande bild visar hur du sparar en moduls konfiguration som ett fragment.</span><span class="sxs-lookup"><span data-stu-id="a5233-138">The following image shows how to save a module configuration as a fragment.</span></span>

![En skärmbild av hur du sparar en modulkonfiguration som ett fragment](./media/save-as-fragment.png)

### <a name="create-a-new-fragment"></a><span data-ttu-id="a5233-140">Skapa ett nytt fragment.</span><span class="sxs-lookup"><span data-stu-id="a5233-140">Create a new fragment</span></span>

<span data-ttu-id="a5233-141">Gör så här om du vill skapa ett nytt fragment.</span><span class="sxs-lookup"><span data-stu-id="a5233-141">To create a new fragment, follow these steps.</span></span>

1. <span data-ttu-id="a5233-142">I navigeringsfönstret till vänster, välj **fragment**.</span><span class="sxs-lookup"><span data-stu-id="a5233-142">In the navigation pane on the left, select **Fragments**.</span></span>
1. <span data-ttu-id="a5233-143">Välj **Nytt sidfragment**.</span><span class="sxs-lookup"><span data-stu-id="a5233-143">Select **New Page Fragment**.</span></span> <span data-ttu-id="a5233-144">En dialogruta visas med alla tillgängliga modultyper.</span><span class="sxs-lookup"><span data-stu-id="a5233-144">A dialog box appears that shows all the available module types.</span></span> <span data-ttu-id="a5233-145">Som tidigare nämnts kan fragment skapas från alla typer av moduler.</span><span class="sxs-lookup"><span data-stu-id="a5233-145">As was mentioned earlier, fragments can be created from any module type.</span></span>
1. <span data-ttu-id="a5233-146">Välj en modultyp för fragmentet.</span><span class="sxs-lookup"><span data-stu-id="a5233-146">Select a module type for your fragment.</span></span>

<span data-ttu-id="a5233-147">I följande bild visas var du kan skapa ett nytt fragment.</span><span class="sxs-lookup"><span data-stu-id="a5233-147">The following image shows where to create a new fragment.</span></span>

![En skärmbild av var du ska skapa ett nytt fragment](./media/fragment-nav-menu.png)

> [!TIP]
> <span data-ttu-id="a5233-149">Genom att välja en generisk behållarmodultyp får du den mest flexibla när du måste uppdatera och konfigurera fragmentet senare.</span><span class="sxs-lookup"><span data-stu-id="a5233-149">By selecting a generic container module type, you get the most flexibility when you need to update and configure your fragment later.</span></span>

## <a name="add-remove-or-edit-fragments-on-a-page"></a><span data-ttu-id="a5233-150">Lägga till, ta bort eller redigera fragment på en sida</span><span class="sxs-lookup"><span data-stu-id="a5233-150">Add, remove, or edit fragments on a page</span></span>

<span data-ttu-id="a5233-151">I följande procedurer beskrivs hur du lägger till, tar bort och redigerar fragment.</span><span class="sxs-lookup"><span data-stu-id="a5233-151">The following procedures describe how to add, remove, and edit fragments.</span></span>

### <a name="add-a-fragment"></a><span data-ttu-id="a5233-152">Lägg till ett fragment</span><span class="sxs-lookup"><span data-stu-id="a5233-152">Add a fragment</span></span>

<span data-ttu-id="a5233-153">Om du vill lägga till ett fragment till en sida gör du följande.</span><span class="sxs-lookup"><span data-stu-id="a5233-153">To add a fragment to a page, follow these steps.</span></span>

1. <span data-ttu-id="a5233-154">I dispositionsfönstret till vänster eller direkt i huvudarbetsytan, välj en behållare eller fack som underordnade moduler kan läggas till.</span><span class="sxs-lookup"><span data-stu-id="a5233-154">In the outline pane on the left or directly in the main canvas, select a container or slot to which child modules can be added.</span></span>
1. <span data-ttu-id="a5233-155">Välj tre punkter (**...**) bredvid namnet på behållaren eller platsen.</span><span class="sxs-lookup"><span data-stu-id="a5233-155">In the online pane, select the ellipsis (**...**) next to the name of the container or slot.</span></span>  <span data-ttu-id="a5233-156">Om du vill kan du även välja plustecknet (**+**) om du använder huvudarbetsytan.</span><span class="sxs-lookup"><span data-stu-id="a5233-156">Alternately, if using the main canvas, select the plus symbol (**+**).</span></span>  
1. <span data-ttu-id="a5233-157">Välj **Lägg till fragment**.</span><span class="sxs-lookup"><span data-stu-id="a5233-157">Select **Add Fragment**.</span></span>

    ![En skärmbild av hur man lägger till ett befintligt fragment på en plats eller en behållare](./media/add-fragment.png)
 
    > [!NOTE]
    > <span data-ttu-id="a5233-159">Om en behållare eller en plats inte stöder nya underordnade moduler är alternativet **Lägg till fragment** inte tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="a5233-159">If the container or slot doesn't support new child modules, the **Add Fragment** option is unavailable.</span></span>
    
1. <span data-ttu-id="a5233-160">Sök efter och markera ett fragment som ska läggas till i dialogrutan **Lägg till fragment**.</span><span class="sxs-lookup"><span data-stu-id="a5233-160">In the **Add Fragment** dialog box, search for and select a fragment to add.</span></span> <span data-ttu-id="a5233-161">Om det inte finns några tillgängliga fragment kanske du först måste skapa ett fragment från en modultyp som den valda behållaren eller platsen stöder.</span><span class="sxs-lookup"><span data-stu-id="a5233-161">If no available fragments are listed, you might first have to create a fragment from a module type that the selected container or slot supports.</span></span>
1. <span data-ttu-id="a5233-162">Välj önskat fragment om du vill lägga till behållaren eller platsen på sidan.</span><span class="sxs-lookup"><span data-stu-id="a5233-162">Select your desired fragment to add it to the container or slot on your page.</span></span>

    ![En skärmdump av spärrat fönster för fragmentväljare](./media/fragment-picker.png)

> [!NOTE]
> <span data-ttu-id="a5233-164">Modulerna som är tillåtna i en behållare eller plats definieras av sidans mall eller modulernas egna definitioner.</span><span class="sxs-lookup"><span data-stu-id="a5233-164">The modules that are allowed in a container or slot are defined by the page's template or the modules' own definitions.</span></span>

### <a name="remove-a-fragment"></a><span data-ttu-id="a5233-165">Ta bort ett fragment</span><span class="sxs-lookup"><span data-stu-id="a5233-165">Remove a fragment</span></span>

<span data-ttu-id="a5233-166">För att ta bort ett fragment från en plats eller behållare på en sida, följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="a5233-166">To remove a fragment from a slot or container on a page, follow these steps.</span></span>

1. <span data-ttu-id="a5233-167">I dispositionsrutan till vänster, välj ellipsknappen (**...**) bredvid namnet på det fragment som du vill ta bort och markera sedan knappen papperskorgen.</span><span class="sxs-lookup"><span data-stu-id="a5233-167">In the outline pane on the left, select the ellipsis (**...**) next to the name of the fragment to be removed, and then select the trash can symbol.</span></span>  <span data-ttu-id="a5233-168">Du kan också markera avsnittet på arbetsytan och välja papperskorgssymbolen i fragmentets verktygsfält.</span><span class="sxs-lookup"><span data-stu-id="a5233-168">Alternately, you can select the fragment in the canvas and select the trash can symbol in the fragment's toolbar.</span></span>
1. <span data-ttu-id="a5233-169">När du uppmanas att bekräfta att du vill ta bort fragmentet väljer du **OK**.</span><span class="sxs-lookup"><span data-stu-id="a5233-169">When you're prompted to confirm that you want to remove the fragment, select **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="a5233-170">När du tar bort ett fragment från en sida tar du bara bort referensen till det från den sidan.</span><span class="sxs-lookup"><span data-stu-id="a5233-170">When you remove a fragment from a page, you just remove the reference to it from that page.</span></span> <span data-ttu-id="a5233-171">Du tar **inte** bort fragmentet från webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="a5233-171">You do **not** delete the fragment from your site.</span></span> <span data-ttu-id="a5233-172">Om du vill ta bort fragment från platsen måste du använda användargränssnittet för fragmentkontrollen.</span><span class="sxs-lookup"><span data-stu-id="a5233-172">To delete fragments from your site, you must use the fragment inspector user interface (UI).</span></span> <span data-ttu-id="a5233-173">Du kan bara ta bort fragment från en plats om de inte är refererade till några sidor, mallar eller andra fragment.</span><span class="sxs-lookup"><span data-stu-id="a5233-173">You can delete fragments from a site only if they aren't currently referenced by any pages, templates, or other fragments.</span></span>

### <a name="edit-a-fragment"></a><span data-ttu-id="a5233-174">Redigera ett fragment</span><span class="sxs-lookup"><span data-stu-id="a5233-174">Edit a fragment</span></span>

<span data-ttu-id="a5233-175">Om du vill redigera fragment måste du använda gränssnittet för fragmentredigeraren.</span><span class="sxs-lookup"><span data-stu-id="a5233-175">To edit fragments, you must use the fragment editor UI.</span></span> <span data-ttu-id="a5233-176">Denna begränsning är av design.</span><span class="sxs-lookup"><span data-stu-id="a5233-176">This restriction is by design.</span></span> <span data-ttu-id="a5233-177">Den garanterar att författare inte förvirrar processen att redigera modulerna för en viss sida med processen för att redigera fragment som kan delas på många sidor.</span><span class="sxs-lookup"><span data-stu-id="a5233-177">It helps guarantee that authors don't confuse the process of editing the modules for a specific page with the process of editing fragments that might be shared across many pages.</span></span>

<span data-ttu-id="a5233-178">Gör så här om du vill redigera ett fragment.</span><span class="sxs-lookup"><span data-stu-id="a5233-178">To edit a fragment, follow these steps.</span></span>

1. <span data-ttu-id="a5233-179">I navigeringsfönstret till vänster, välj **fragment**.</span><span class="sxs-lookup"><span data-stu-id="a5233-179">In the navigation pane on the left, select **Fragments**.</span></span>
1. <span data-ttu-id="a5233-180">Under **Fragment**, välj det fragment du redigera.</span><span class="sxs-lookup"><span data-stu-id="a5233-180">Under **Fragments**, select the fragment to edit.</span></span>
1. <span data-ttu-id="a5233-181">Redigera fragmentets modulegenskaper och struktur efter behov.</span><span class="sxs-lookup"><span data-stu-id="a5233-181">Edit the fragment's module properties and structure as you require.</span></span> <span data-ttu-id="a5233-182">Processen ser ut som om du redigerar modulerna i vyn sidredigerare.</span><span class="sxs-lookup"><span data-stu-id="a5233-182">The process resembles the process for editing modules are edited in the page editor view.</span></span>

<span data-ttu-id="a5233-183">Du kan också redigera ett fragment genom att markera det på en sida, i en mall eller i ett överordnat fragment, och sedan välja **redigera fragment** i egenskapsrutan till höger.</span><span class="sxs-lookup"><span data-stu-id="a5233-183">You can also edit a fragment by selecting it on a page, in a template, or in a parent fragment, and then selecting **Edit Fragment** in the properties pane on the right.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a5233-184">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="a5233-184">Additional resources</span></span>

[<span data-ttu-id="a5233-185">Översikt över mallar och layouter</span><span class="sxs-lookup"><span data-stu-id="a5233-185">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="a5233-186">Arbeta med mallar</span><span class="sxs-lookup"><span data-stu-id="a5233-186">Work with templates</span></span>](work-with-templates.md)

[<span data-ttu-id="a5233-187">Arbeta med förinställda layouter</span><span class="sxs-lookup"><span data-stu-id="a5233-187">Work with preset layouts</span></span>](work-with-layouts.md)

[<span data-ttu-id="a5233-188">Arbeta med publiceringsgrupper</span><span class="sxs-lookup"><span data-stu-id="a5233-188">Work with publish groups</span></span>](publish-groups.md)
