---
title: Arbeta med fragment
description: I det här avsnittet beskrivs varför, när och hur du ska använda fragment i Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 10/01/2019
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
ms.openlocfilehash: d92b9077f8584bfa0710bbaacbc7caa3220baa4a
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/01/2019
ms.locfileid: "2698106"
---
# <a name="work-with-fragments"></a><span data-ttu-id="95293-103">Arbeta med fragment</span><span class="sxs-lookup"><span data-stu-id="95293-103">Work with fragments</span></span> 

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="95293-104">I det här avsnittet beskrivs varför, när och hur du ska använda fragment i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="95293-104">This topic describes why, when, and how to use fragments in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="95293-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="95293-105">Overview</span></span>

<span data-ttu-id="95293-106">Fragment gör det möjligt att använda en central redigeringsupplevelse för modulkonfigurationer som måste återanvändas på hela din webbplats.</span><span class="sxs-lookup"><span data-stu-id="95293-106">Fragments allow for a centralized authoring experience for module configurations that must be reused throughout your site.</span></span> <span data-ttu-id="95293-107">Sidhuvuden, sidfötter och banderoller är ofta konfigurerade som fragment, eftersom de delas på många sidor.</span><span class="sxs-lookup"><span data-stu-id="95293-107">For example, headers, footers, and banners are often configured as fragments, because they are shared across many pages.</span></span> <span data-ttu-id="95293-108">Du kan betrakta fragment som miniatyrer av webbsidor som kan infogas på andra sidor på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="95293-108">You can think of fragments as miniature webpages that can be inserted into other pages on your site.</span></span> <span data-ttu-id="95293-109">Fragment har sin egen livscykel.</span><span class="sxs-lookup"><span data-stu-id="95293-109">Fragments have their own lifecycle.</span></span> <span data-ttu-id="95293-110">Det innebär att de skapas, refereras, uppdateras och tas bort som oberoende enheter i redigeringsverktygen.</span><span class="sxs-lookup"><span data-stu-id="95293-110">In other words, they are created, referenced, updated, and deleted as independent entities in the authoring tools.</span></span>

<span data-ttu-id="95293-111">När fragment har konfigurerats kan de användas där moduler kan användas i webbplatsstrukturen.</span><span class="sxs-lookup"><span data-stu-id="95293-111">After fragments are configured, they can be used wherever modules can be used in your site structure.</span></span> <span data-ttu-id="95293-112">Det går att referera till fragment på sidor, i layouter, i mallar och i andra fragment.</span><span class="sxs-lookup"><span data-stu-id="95293-112">Fragments can be referenced on pages, in layouts, in templates, and in other fragments.</span></span>

> [!NOTE]
> <span data-ttu-id="95293-113">Fragment kan kapslas upp till sju nivåer djup inuti andra fragment.</span><span class="sxs-lookup"><span data-stu-id="95293-113">Fragments can be nested up to seven levels deep inside other fragments.</span></span>

<span data-ttu-id="95293-114">Om du till exempel vill marknadsföra en säsongshändelse på många sidor på webbplatsen kan du använda ett fragment.</span><span class="sxs-lookup"><span data-stu-id="95293-114">For example, if you want to promote a seasonal event cross many pages on our site, you can use a fragment.</span></span> <span data-ttu-id="95293-115">Det första steget i processen med att skapa ett nytt fragment är att välja vilken typ av modul du vill starta från.</span><span class="sxs-lookup"><span data-stu-id="95293-115">The first step in the process of creating a new fragment is to select the type of module that you want to start from.</span></span> <span data-ttu-id="95293-116">I det här exemplet kan du skapa avsnittet från en fokusmodul.</span><span class="sxs-lookup"><span data-stu-id="95293-116">For this example, you can build the fragment from a hero module.</span></span>

> [!NOTE]
> <span data-ttu-id="95293-117">Fragment kan skapas med alla typer av moduler.</span><span class="sxs-lookup"><span data-stu-id="95293-117">Fragments can be built from any module type.</span></span>

<span data-ttu-id="95293-118">Du kan sedan konfigurera fokusfragment med ditt specifika säljinnehåll.</span><span class="sxs-lookup"><span data-stu-id="95293-118">You can then configure the hero fragment with your specific promotional content.</span></span> <span data-ttu-id="95293-119">Du kan också lokalisera den efter behov.</span><span class="sxs-lookup"><span data-stu-id="95293-119">You can also localize it as you require.</span></span> <span data-ttu-id="95293-120">Det nya fristående fokusfragmentet kan sedan förbrukas som en förkonfigurerad modul på hela din webbplats.</span><span class="sxs-lookup"><span data-stu-id="95293-120">The new stand-alone hero fragment can then be consumed as a preconfigured module throughout your site.</span></span> <span data-ttu-id="95293-121">Du kan enkelt lägga till det i mallar, specifika sidor eller till andra fragment som kan innehålla fokusmoduler.</span><span class="sxs-lookup"><span data-stu-id="95293-121">You can easily add it to templates, to specific pages, or to other fragments that can contain hero modules.</span></span>

<span data-ttu-id="95293-122">Alla platser där fragmenten läggs till är referenser till det centrala fokusfragment som du har skapat.</span><span class="sxs-lookup"><span data-stu-id="95293-122">All the places where the fragment is added are references to the central hero fragment that you created.</span></span> <span data-ttu-id="95293-123">Om du publicerar ändringar i avsnittet visas dessa direkt på alla platser där fragmentet refereras på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="95293-123">If you publish changes to the fragment, those changes are immediately reflected in all the places where the fragment is referenced across the site.</span></span> <span data-ttu-id="95293-124">Därför utgör fragmenten ett kraftfullt och effektivt sätt att återanvända och centralt hantera konfigurationer på en webbplats.</span><span class="sxs-lookup"><span data-stu-id="95293-124">Therefore, fragments provide a powerful and efficient way to reuse and centrally manage module configurations on a site.</span></span> <span data-ttu-id="95293-125">Genom att effektivt använda dem kan du öka flexibiliteten och minska den kostnad som är kopplad till hantering av webbplatsens innehåll.</span><span class="sxs-lookup"><span data-stu-id="95293-125">By effectively using them, you can significantly increase agility and help reduce the cost that is associated with managing site content.</span></span>

<span data-ttu-id="95293-126">Följande bild visar hur fragment kan användas för att centralisera redigering av konfigurationer för delade moduler på en e-handelsplats.</span><span class="sxs-lookup"><span data-stu-id="95293-126">The following illustration shows how fragments can be used to centralize authoring of shared module configurations across an e-Commerce site.</span></span>

![EN bild visar hur fragment kan användas för att centralisera redigering av konfigurationer för delade moduler på en e-handelsplats.](./media/fragment-figure1.png)

## <a name="create-a-fragment"></a><span data-ttu-id="95293-128">Skapa ett fragment</span><span class="sxs-lookup"><span data-stu-id="95293-128">Create a fragment</span></span>

<span data-ttu-id="95293-129">Du kan antingen skapa ett nytt fragment eller spara en befintlig modul som ett fragment.</span><span class="sxs-lookup"><span data-stu-id="95293-129">You can either create a new fragment or save an existing module configuration as a fragment.</span></span>

### <a name="create-a-new-fragment"></a><span data-ttu-id="95293-130">Skapa ett nytt fragment.</span><span class="sxs-lookup"><span data-stu-id="95293-130">Create a new fragment</span></span>

<span data-ttu-id="95293-131">Gör så här om du vill skapa ett nytt fragment.</span><span class="sxs-lookup"><span data-stu-id="95293-131">To create a new fragment, follow these steps.</span></span>

1. <span data-ttu-id="95293-132">I navigeringsfönstret till vänster, välj **fragment**.</span><span class="sxs-lookup"><span data-stu-id="95293-132">In the navigation pane on the left, select **Fragments**.</span></span>
1. <span data-ttu-id="95293-133">Välj **Nytt sidfragment**.</span><span class="sxs-lookup"><span data-stu-id="95293-133">Select **New Page Fragment**.</span></span> <span data-ttu-id="95293-134">En dialogruta visas med alla tillgängliga modultyper.</span><span class="sxs-lookup"><span data-stu-id="95293-134">A dialog box appears that shows all the available module types.</span></span> <span data-ttu-id="95293-135">Som tidigare nämnts kan fragment skapas från alla typer av moduler.</span><span class="sxs-lookup"><span data-stu-id="95293-135">As was mentioned earlier, fragments can be created from any module type.</span></span>
1. <span data-ttu-id="95293-136">Välj en modultyp för fragmentet och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="95293-136">Select a module type for your fragment, and then select **OK**.</span></span>

    > [!TIP]
    > <span data-ttu-id="95293-137">Genom att välja en generisk behållarmodultyp får du den mest flexibla när du måste uppdatera och konfigurera fragmentet senare.</span><span class="sxs-lookup"><span data-stu-id="95293-137">By selecting a generic container module type, you get the most flexibility when you must update and configure your fragment later.</span></span>

### <a name="save-an-existing-module-configuration-as-a-fragment"></a><span data-ttu-id="95293-138">Spara en befintlig modulkonfiguration som ett fragment</span><span class="sxs-lookup"><span data-stu-id="95293-138">Save an existing module configuration as a fragment</span></span>

<span data-ttu-id="95293-139">Om du vill konvertera en tidigare konfigurerad modul till ett återanvändbart fragment följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="95293-139">To convert a previously configured module to a reusable fragment, follow these steps.</span></span>

1. <span data-ttu-id="95293-140">Öppna en sida eller mall som innehåller modulen som du vill konvertera till ett fragment.</span><span class="sxs-lookup"><span data-stu-id="95293-140">Open a page or template that contains the module that you want to convert to a fragment.</span></span>
1. <span data-ttu-id="95293-141">Markera ellipsknappen (**...**) bredvid namnet på den modul som du vill ta bort i dispositionsrutan till vänster och markera sedan **Spara som fragment**.</span><span class="sxs-lookup"><span data-stu-id="95293-141">In the outline pane on the left, select the ellipsis button (**...**) next to the name of the module, and then select **Save as Fragment**.</span></span> <span data-ttu-id="95293-142">En dialogruta visas.</span><span class="sxs-lookup"><span data-stu-id="95293-142">A dialog box appears.</span></span>
1. <span data-ttu-id="95293-143">Ange ett namn och metadata för fragmentet.</span><span class="sxs-lookup"><span data-stu-id="95293-143">Enter a name and metadata for the fragment.</span></span>
1. <span data-ttu-id="95293-144">Välj **OK** om du vill spara modulens konfiguration som ett fragment som kan läggas till på andra sidor.</span><span class="sxs-lookup"><span data-stu-id="95293-144">Select **OK** to save the module configuration as a fragment that can be added to other pages.</span></span>

## <a name="add-remove-or-edit-fragments-on-a-page"></a><span data-ttu-id="95293-145">Lägga till, ta bort eller redigera fragment på en sida</span><span class="sxs-lookup"><span data-stu-id="95293-145">Add, remove, or edit fragments on a page</span></span>

<span data-ttu-id="95293-146">I följande procedurer beskrivs hur du lägger till, tar bort och redigerar fragment.</span><span class="sxs-lookup"><span data-stu-id="95293-146">The following procedures describe how to add, remove, and edit fragments.</span></span>

### <a name="add-a-fragment"></a><span data-ttu-id="95293-147">Lägg till ett fragment</span><span class="sxs-lookup"><span data-stu-id="95293-147">Add a fragment</span></span>

<span data-ttu-id="95293-148">Om du vill lägga till ett fragment till en sida gör du följande.</span><span class="sxs-lookup"><span data-stu-id="95293-148">To add a fragment to a page, follow these steps.</span></span>

1. <span data-ttu-id="95293-149">I dispositionsrutan till vänster väljer du en behållare eller en plats som underordnade moduler kan läggas till i.</span><span class="sxs-lookup"><span data-stu-id="95293-149">In the outline pane on the left, select a container or slot that child modules can be added to.</span></span>
1. <span data-ttu-id="95293-150">Markera knappen med punkter bredvid namnet på behållaren eller platsen och välj sedan **Lägg till fragment**.</span><span class="sxs-lookup"><span data-stu-id="95293-150">Select the ellipsis button next to the name of the container or slot, and then select **Add Fragment**.</span></span> <span data-ttu-id="95293-151">En dialogruta visas.</span><span class="sxs-lookup"><span data-stu-id="95293-151">A dialog box appears.</span></span>

    > [!NOTE]
    > <span data-ttu-id="95293-152">Om en behållare eller en plats inte stöder nya underordnade moduler är alternativet **Lägg till fragment** inte tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="95293-152">If the container or slot doesn't support new child modules, the **Add Fragment** option is unavailable.</span></span>

1. <span data-ttu-id="95293-153">Sök efter och markera ett fragment som ska läggas till i dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="95293-153">In the dialog box, search for and select a fragment to add.</span></span> <span data-ttu-id="95293-154">Om det inte finns några tillgängliga fragment kanske du först måste skapa ett fragment från en modultyp som den valda behållaren eller platsen stöder.</span><span class="sxs-lookup"><span data-stu-id="95293-154">If no available fragments are listed, you might first have to create a fragment from a module type that the selected container or slot supports.</span></span>
1. <span data-ttu-id="95293-155">Klicka på **OK** om du vill lägga till det valda fragmentet i den valda behållaren eller platsen på sidan.</span><span class="sxs-lookup"><span data-stu-id="95293-155">Select **OK** to add the selected fragment to the selected container or slot on your page.</span></span>

> [!NOTE]
> <span data-ttu-id="95293-156">Modulerna som är tillåtna i en behållare eller plats definieras av sidans mall eller modulernas egna definitioner.</span><span class="sxs-lookup"><span data-stu-id="95293-156">The modules that are allowed in a container or slot are defined by the page's template or the modules' own definitions.</span></span>

### <a name="remove-a-fragment"></a><span data-ttu-id="95293-157">Ta bort ett fragment</span><span class="sxs-lookup"><span data-stu-id="95293-157">Remove a fragment</span></span>

<span data-ttu-id="95293-158">För att ta bort ett fragment från en plats eller behållare på en sida, följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="95293-158">To remove a fragment from a slot or container on a page, follow these steps.</span></span>

1. <span data-ttu-id="95293-159">Markera ellipsknappen bredvid namnet på det fragment som du vill ta bort i dispositionsrutan till vänster och markera sedan knappen papperskorgen.</span><span class="sxs-lookup"><span data-stu-id="95293-159">In the outline pane on the left, select the ellipsis button next to the name of the fragment to remove, and then select the trash can button.</span></span>
1. <span data-ttu-id="95293-160">När du uppmanas att bekräfta att du vill ta bort fragmentet väljer du **OK**.</span><span class="sxs-lookup"><span data-stu-id="95293-160">When you're prompted to confirm that you want to remove the fragment, select **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="95293-161">När du tar bort ett fragment från en sida tar du bara bort referensen till det från den sidan.</span><span class="sxs-lookup"><span data-stu-id="95293-161">When you remove a fragment from a page, you just remove the reference to it from that page.</span></span> <span data-ttu-id="95293-162">Du tar **inte** bort fragmentet från webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="95293-162">You do **not** delete the fragment from your site.</span></span> <span data-ttu-id="95293-163">Om du vill ta bort fragment från platsen måste du använda användargränssnittet för fragmentkontrollen.</span><span class="sxs-lookup"><span data-stu-id="95293-163">To delete fragments from your site, you must use the fragment inspector user interface (UI).</span></span> <span data-ttu-id="95293-164">Du kan bara ta bort fragment från en plats om de inte är refererade till några sidor, mallar eller andra fragment.</span><span class="sxs-lookup"><span data-stu-id="95293-164">You can delete fragments from a site only if they aren't currently referenced by any pages, templates, or other fragments.</span></span>

### <a name="edit-a-fragment"></a><span data-ttu-id="95293-165">Redigera ett fragment</span><span class="sxs-lookup"><span data-stu-id="95293-165">Edit a fragment</span></span>

<span data-ttu-id="95293-166">Om du vill redigera fragment måste du använda gränssnittet för fragmentredigeraren.</span><span class="sxs-lookup"><span data-stu-id="95293-166">To edit fragments, you must use the fragment editor UI.</span></span> <span data-ttu-id="95293-167">Denna begränsning är av design.</span><span class="sxs-lookup"><span data-stu-id="95293-167">This restriction is by design.</span></span> <span data-ttu-id="95293-168">Den garanterar att författare inte förvirrar processen att redigera modulerna för en viss sida med processen för att redigera fragment som kan delas på många sidor.</span><span class="sxs-lookup"><span data-stu-id="95293-168">It helps guarantee that authors don't confuse the process of editing the modules for a specific page with the process of editing fragments that might be shared across many pages.</span></span>

<span data-ttu-id="95293-169">Gör så här om du vill redigera ett fragment.</span><span class="sxs-lookup"><span data-stu-id="95293-169">To edit a fragment, follow these steps.</span></span>

1. <span data-ttu-id="95293-170">I navigeringsfönstret till vänster, välj **fragment**.</span><span class="sxs-lookup"><span data-stu-id="95293-170">In the navigation pane on the left, select **Fragments**.</span></span>
1. <span data-ttu-id="95293-171">Under **Fragment**, välj det fragment du redigera.</span><span class="sxs-lookup"><span data-stu-id="95293-171">Under **Fragments**, select the fragment to edit.</span></span>
1. <span data-ttu-id="95293-172">Redigera fragmentets modulegenskaper och struktur efter behov.</span><span class="sxs-lookup"><span data-stu-id="95293-172">Edit the fragment's module properties and structure as you require.</span></span> <span data-ttu-id="95293-173">Processen ser ut som om du redigerar modulerna i vyn sidredigerare.</span><span class="sxs-lookup"><span data-stu-id="95293-173">The process resembles the process for editing modules are edited in the page editor view.</span></span>

<span data-ttu-id="95293-174">Du kan också redigera ett fragment genom att markera det på en sida, i en mall eller i ett överordnat fragment, och sedan välja **redigera fragment** i egenskapsrutan till höger.</span><span class="sxs-lookup"><span data-stu-id="95293-174">You can also edit a fragment by selecting it on a page, in a template, or in a parent fragment, and then selecting **Edit Fragment** in the properties pane on the right.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="95293-175">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="95293-175">Additional resources</span></span>

[<span data-ttu-id="95293-176">Översikt över mallar och layouter</span><span class="sxs-lookup"><span data-stu-id="95293-176">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="95293-177">Arbeta med mallar</span><span class="sxs-lookup"><span data-stu-id="95293-177">Work with templates</span></span>](work-with-templates.md)

[<span data-ttu-id="95293-178">Arbeta med förinställda layouter</span><span class="sxs-lookup"><span data-stu-id="95293-178">Work with preset layouts</span></span>](work-with-layouts.md)
