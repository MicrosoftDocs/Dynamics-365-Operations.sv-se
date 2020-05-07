---
title: Arbeta med förinställda layouter
description: I det här avsnittet beskrivs hur du arbetar med förinställda layouter i Microsoft Dynamics 365 Commerce.
author: phinneyridge
manager: annbe
ms.date: 04/14/2020
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
ms.openlocfilehash: f31dfa1fdbb3732610748abe4a9de851033f2b89
ms.sourcegitcommit: 7a1d01122790b904e2d96a7ea9f1d003392358a6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/17/2020
ms.locfileid: "3269899"
---
# <a name="work-with-preset-layouts"></a><span data-ttu-id="8a622-103">Arbeta med förinställda layouter</span><span class="sxs-lookup"><span data-stu-id="8a622-103">Work with preset layouts</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="8a622-104">I det här avsnittet beskrivs hur du arbetar med förinställda layouter i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="8a622-104">This topic describes how to work with preset layouts in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="8a622-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="8a622-105">Overview</span></span>

<span data-ttu-id="8a622-106">Innan du slutför procedurerna i det här avsnittet bör du läsa [förinställda och anpassade layouter](templates-layouts-overview.md#preset-and-custom-layouts)</span><span class="sxs-lookup"><span data-stu-id="8a622-106">Before you complete the procedures in this topic, be sure to read [Preset and custom layouts](templates-layouts-overview.md#preset-and-custom-layouts).</span></span> <span data-ttu-id="8a622-107">En allmän översikt finns i [mallar och layouter – översikt](templates-layouts-overview.md).</span><span class="sxs-lookup"><span data-stu-id="8a622-107">For a general overview, see [Templates and layouts overview](templates-layouts-overview.md).</span></span>

## <a name="create-a-new-preset-layout"></a><span data-ttu-id="8a622-108">Skapa en ny förinställd layout</span><span class="sxs-lookup"><span data-stu-id="8a622-108">Create a new preset layout</span></span>

<span data-ttu-id="8a622-109">Det finns två metoder för att skapa en förinställd layout.</span><span class="sxs-lookup"><span data-stu-id="8a622-109">There are two methods for creating a preset layout.</span></span> <span data-ttu-id="8a622-110">Du kan spara en befintlig anpassad layout som en ny förinställd layout, eller så kan du skapa en förinställd layout från början.</span><span class="sxs-lookup"><span data-stu-id="8a622-110">You can save an existing custom layout as a new preset layout, or you can create a preset layout from scratch.</span></span>

### <a name="create-a-preset-layout-from-an-existing-custom-layout"></a><span data-ttu-id="8a622-111">Skapa en förinställd layout från en befintlig anpassad layout</span><span class="sxs-lookup"><span data-stu-id="8a622-111">Create a preset layout from an existing custom layout</span></span>

<span data-ttu-id="8a622-112">För att skapa en förinställd layout från en befintlig anpassad layout, följ dessa steg:</span><span class="sxs-lookup"><span data-stu-id="8a622-112">To create a preset layout from an existing custom layout, follow these steps.</span></span>

1. <span data-ttu-id="8a622-113">Öppna en befintlig sida som för tillfället inte använder en förinställd layout och som har en modulstruktur som du vill återanvända för andra sidor på webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="8a622-113">Open an existing page that doesn't currently use a preset layout, and that has a module structure that you want to reuse for other pages on your site.</span></span>
1. <span data-ttu-id="8a622-114">Välj **redigera** om du vill checka ut sidan.</span><span class="sxs-lookup"><span data-stu-id="8a622-114">Select **Edit** to check out the page.</span></span>
1. <span data-ttu-id="8a622-115">Välj **Spara som ny layout**.</span><span class="sxs-lookup"><span data-stu-id="8a622-115">Select **Save as new layout**.</span></span> <span data-ttu-id="8a622-116">Dialogrutan **Spara som ny layout** visas.</span><span class="sxs-lookup"><span data-stu-id="8a622-116">The **Save as new layout** dialog box appears.</span></span>
1. <span data-ttu-id="8a622-117">Ange ett namn och en beskrivning för din förinställda layout.</span><span class="sxs-lookup"><span data-stu-id="8a622-117">Enter a name and description for your preset layout.</span></span> <span data-ttu-id="8a622-118">De värden du anger kommer att visas för andra författare när de skapar nya sidor från layouten eller växlar till den.</span><span class="sxs-lookup"><span data-stu-id="8a622-118">The values that you enter will be shown to other authors when they create new pages from your layout or switch to it.</span></span> <span data-ttu-id="8a622-119">Ange därför värden som är användbara för sidförfattare.</span><span class="sxs-lookup"><span data-stu-id="8a622-119">Therefore, enter values that will be useful to page authors.</span></span>
1. <span data-ttu-id="8a622-120">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="8a622-120">Select **OK**.</span></span>

<span data-ttu-id="8a622-121">Den förinställda layouten blir nu tillgänglig när du skapar nya sidor eller väljer en annan layout för en sida i samma mall.</span><span class="sxs-lookup"><span data-stu-id="8a622-121">The preset layout will now be available when you create new pages or select a different layout for a page in the same template hierarchy.</span></span>

> [!TIP]
> <span data-ttu-id="8a622-122">Om du snabbt vill se om en viss sida är bunden till en förinställd layout, markerar du sidan i listvyn och kontrollerar layoutens metadata i egenskapsrutan till höger.</span><span class="sxs-lookup"><span data-stu-id="8a622-122">To quickly see whether a specific page is currently bound to a preset layout, select the page in the pages list view, and inspect the layout metadata in the property pane on the right.</span></span>

### <a name="create-a-new-preset-layout"></a><span data-ttu-id="8a622-123">Skapa en ny förinställd layout</span><span class="sxs-lookup"><span data-stu-id="8a622-123">Create a new preset layout</span></span>

<span data-ttu-id="8a622-124">För att skapa en förinställd layout från början, följ dessa steg:</span><span class="sxs-lookup"><span data-stu-id="8a622-124">To create a preset layout from scratch, follow these steps.</span></span>

1. <span data-ttu-id="8a622-125">I navigeringsfönstret till vänster, välj **Layouter**.</span><span class="sxs-lookup"><span data-stu-id="8a622-125">In the navigation pane on the left, select **Layouts**.</span></span>
1. <span data-ttu-id="8a622-126">Välj **Ny layout**.</span><span class="sxs-lookup"><span data-stu-id="8a622-126">Select **New Layout**.</span></span> <span data-ttu-id="8a622-127">Dialogrutan **Ny layout** visas.</span><span class="sxs-lookup"><span data-stu-id="8a622-127">The **New layout** dialog box appears.</span></span>
1. <span data-ttu-id="8a622-128">Välj den mall som ska användas för den förvalda layouten.</span><span class="sxs-lookup"><span data-stu-id="8a622-128">Select the template to use for your preset layout.</span></span>
1. <span data-ttu-id="8a622-129">Ange ett namn och en beskrivning för din förinställda layout.</span><span class="sxs-lookup"><span data-stu-id="8a622-129">Enter a name and description for your preset layout.</span></span> <span data-ttu-id="8a622-130">De värden du anger kommer att visas för andra författare när de skapar nya sidor från layouten eller växlar till den.</span><span class="sxs-lookup"><span data-stu-id="8a622-130">The values that you enter will be shown to other authors when they create new pages from your layout or switch to it.</span></span> <span data-ttu-id="8a622-131">Ange därför värden som är användbara för sidförfattare.</span><span class="sxs-lookup"><span data-stu-id="8a622-131">Therefore, enter values that will be useful to page authors.</span></span>
1. <span data-ttu-id="8a622-132">Klicka på **OK** om du vill skapa den nya förinställda layouten och öppna layoutredigeraren.</span><span class="sxs-lookup"><span data-stu-id="8a622-132">Select **OK** to create the new preset layout and open the layout editor.</span></span>
1. <span data-ttu-id="8a622-133">I layoutvyn lägger du till och konfigurerar moduler med hjälp av dispositionsträdet till vänster och egenskapsrutan till höger.</span><span class="sxs-lookup"><span data-stu-id="8a622-133">In the layout editor, add and configure modules by using the outline tree on the left and the property pane on the right.</span></span> <span data-ttu-id="8a622-134">(Processen ser ut som om du lägger till och konfigurerar moduler för en mall i mallredigeraren.) Moduler och låsta standardinställningar blir den centraliserade konfigurationen av alla sidor där den här förvalda layouten används.</span><span class="sxs-lookup"><span data-stu-id="8a622-134">(The process resembles the process for adding and configuring modules for a template in the template editor.) The arrangement of modules and any locked default settings become the centralized module configuration for any pages that use this preset layout.</span></span>

## <a name="modify-a-preset-layout"></a><span data-ttu-id="8a622-135">Ändra en fördefinierad layout</span><span class="sxs-lookup"><span data-stu-id="8a622-135">Modify a preset layout</span></span>

<span data-ttu-id="8a622-136">För att ändra en förinställd layout, följ dessa steg:</span><span class="sxs-lookup"><span data-stu-id="8a622-136">To modify a preset layout, follow these steps.</span></span>

1. <span data-ttu-id="8a622-137">I navigeringsfönstret till vänster, välj **Layouter**.</span><span class="sxs-lookup"><span data-stu-id="8a622-137">In the navigation pane on the left, select **Layouts**.</span></span>
1. <span data-ttu-id="8a622-138">Välj den modul som ska ändras i dispositionsträdet till vänster i layoutvyn.</span><span class="sxs-lookup"><span data-stu-id="8a622-138">In the layout editor, in the outline tree on the left, select the module to modify.</span></span> <span data-ttu-id="8a622-139">Gör sedan något av följande:</span><span class="sxs-lookup"><span data-stu-id="8a622-139">Then follow any of these steps:</span></span>

    - <span data-ttu-id="8a622-140">Om du vill flytta en modul uppåt eller nedåt inuti dess överordnade, markerar du ellipsknappen (**...**) och modulen och välj sedan **flytta upp** eller **flytta ned**.</span><span class="sxs-lookup"><span data-stu-id="8a622-140">To move a module up or down inside its parent, select the ellipsis button (**...**) for the module, and then select **Move up** or **Move down**.</span></span>
    - <span data-ttu-id="8a622-141">Om du vill ändra standardinställningarna för en modul använder du egenskapsfönstret för att ange standardvärden och för att även låsa dem för alla underordnade sidor.</span><span class="sxs-lookup"><span data-stu-id="8a622-141">To change a module's default settings, use the property pane to enter default values and optionally lock them for all downstream pages.</span></span>
    - <span data-ttu-id="8a622-142">Om du vill lägga till nya moduler eller fragment i behållarmoduler markerar du knappen och väljer **Lägg till modul** eller **Lägg till fragment**.</span><span class="sxs-lookup"><span data-stu-id="8a622-142">To add new modules or fragments to container modules, select the ellipsis button, and then select **Add module** or **Add fragment**.</span></span>
    - <span data-ttu-id="8a622-143">Om du vill ta bort en modul från layouten markerar du ellipsknappen och väljer sedan **Ta bort**.</span><span class="sxs-lookup"><span data-stu-id="8a622-143">To remove a module from the layout, select the ellipsis button, and then select **Delete**.</span></span>

## <a name="change-a-preset-layout-theme"></a><span data-ttu-id="8a622-144">Ändra ett förinställt tema för en layout</span><span class="sxs-lookup"><span data-stu-id="8a622-144">Change a preset layout theme</span></span>

<span data-ttu-id="8a622-145">Ett vanligt tillvägagångssätt är att ange ett standardtema för alla sidor som använder en förinställd layout.</span><span class="sxs-lookup"><span data-stu-id="8a622-145">A typical practice is to set a default theme for all pages that use a preset layout.</span></span>

<span data-ttu-id="8a622-146">Om du vill ange eller ändra temat för alla underordnade sidor som använder din förinställda layout följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="8a622-146">To set or change the theme for all child pages that use your preset layout, follow these steps.</span></span>

1. <span data-ttu-id="8a622-147">Välj den modul för sidbehållare som ska ändras i dispositionsträdet till vänster i layoutvyn.</span><span class="sxs-lookup"><span data-stu-id="8a622-147">In the layout editor, in the outline tree on the left, select the page container module.</span></span> <span data-ttu-id="8a622-148">(Normalt är den här modulen den andra noden och får namnet **standardsida**.)</span><span class="sxs-lookup"><span data-stu-id="8a622-148">(Typically, this module is the second node and is named **Default page**.)</span></span>
1. <span data-ttu-id="8a622-149">Välj ett tema i fältet **tema** i egenskapsfönstret till höger.</span><span class="sxs-lookup"><span data-stu-id="8a622-149">In the property pane on the right, in the **Theme** field, select a theme.</span></span>

## <a name="save-check-in-preview-and-publish-a-preset-layout"></a><span data-ttu-id="8a622-150">Spara, checka in, förhandsgranska och publicera en förinställd layout</span><span class="sxs-lookup"><span data-stu-id="8a622-150">Save, check in, preview, and publish a preset layout</span></span>

<span data-ttu-id="8a622-151">Om du vill spara och checka in din förinställda layout, följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="8a622-151">To save and check in your preset layout, follow these steps.</span></span>

1. <span data-ttu-id="8a622-152">Välj **spara** längst upp i layoutredigeraren.</span><span class="sxs-lookup"><span data-stu-id="8a622-152">Select **Save** at the top of the layout editor.</span></span> <span data-ttu-id="8a622-153">Sparade ändringar påverkar inte underordnade sidor förrän de checkas in.</span><span class="sxs-lookup"><span data-stu-id="8a622-153">Saved changes don't affect downstream pages until they are checked in.</span></span>
1. <span data-ttu-id="8a622-154">Välj **Slutför redigering**.</span><span class="sxs-lookup"><span data-stu-id="8a622-154">Select **Finish editing**.</span></span> <span data-ttu-id="8a622-155">Dina ändringar kan nu upptäckas för efterföljande arbetsflöden.</span><span class="sxs-lookup"><span data-stu-id="8a622-155">Your changes are now discoverable for downstream workflows.</span></span>

<span data-ttu-id="8a622-156">Om du vill förhandsgranska ändringarna öppnar du en befintlig sida som använder förinställd layout eller skapar en ny sida från layouten.</span><span class="sxs-lookup"><span data-stu-id="8a622-156">To preview your changes, either open an existing page that uses the preset layout or create a new page from the layout.</span></span>

<span data-ttu-id="8a622-157">När du har förhandsgranskat ändringarna i din förinställda layout gör du följande för att publicera layouten på din aktiva webbplats:</span><span class="sxs-lookup"><span data-stu-id="8a622-157">After you've previewed the changes to your preset layout, follow one of these steps to publish the layout to your live site:</span></span>

* <span data-ttu-id="8a622-158">Gå till **layouter**, markera layouten och välj sedan **publicera**.</span><span class="sxs-lookup"><span data-stu-id="8a622-158">Go to **Layouts**, select the layout, and then select **Publish**.</span></span>
* <span data-ttu-id="8a622-159">Välj layoutnamn för att öppna layoutredigeraren och välj sedan **Publicera**.</span><span class="sxs-lookup"><span data-stu-id="8a622-159">Select the layout name to open the layout editor, and then select **Publish**.</span></span>
* <span data-ttu-id="8a622-160">Publicera en sida som refererar till den opublicerade layouten.</span><span class="sxs-lookup"><span data-stu-id="8a622-160">Publish a page that references the unpublished layout.</span></span> <span data-ttu-id="8a622-161">Layouten kommer att publiceras automatiskt.</span><span class="sxs-lookup"><span data-stu-id="8a622-161">The layout will automatically be published.</span></span>

> [!WARNING]
> <span data-ttu-id="8a622-162">Du kan referera till förinställda layouter av flera sidor.</span><span class="sxs-lookup"><span data-stu-id="8a622-162">Preset layouts can be referenced by multiple pages.</span></span> <span data-ttu-id="8a622-163">När du publicerar en förinställd layout måste du vara medveten om att du kan påverka layouten på flera sidor.</span><span class="sxs-lookup"><span data-stu-id="8a622-163">When you publish a preset layout, be aware that you might affect the layout of multiple pages.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8a622-164">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="8a622-164">Additional resources</span></span>

[<span data-ttu-id="8a622-165">Översikt över mallar och layouter</span><span class="sxs-lookup"><span data-stu-id="8a622-165">Templates and layouts overview</span></span>](templates-layouts-overview.md)

[<span data-ttu-id="8a622-166">Arbeta med mallar</span><span class="sxs-lookup"><span data-stu-id="8a622-166">Work with templates</span></span>](work-with-templates.md)
