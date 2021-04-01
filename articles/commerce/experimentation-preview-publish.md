---
title: Förhandsgranska och publicera ett experiment
description: I det här avsnittet beskrivs hur du förhandsgranskar och publicerar ett experiment från Dynamics 365 Commerce.
author: sushma-rao
manager: AnnBe
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 7b35af35f5d0347192ed94bed51dfd2484cfa481
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5238592"
---
# <a name="preview-and-publish-an-experiment"></a><span data-ttu-id="3c591-103">Förhandsgranska och publicera ett experiment</span><span class="sxs-lookup"><span data-stu-id="3c591-103">Preview and publish an experiment</span></span>

<span data-ttu-id="3c591-104">I det här avsnittet beskrivs hur du förhandsgranskar och publicerar ditt experiment Dynamics 365 Commerce när du har [kopplat experimentet och redigerat dina varianter](experimentation-connect-edit.md).</span><span class="sxs-lookup"><span data-stu-id="3c591-104">This topic describes how to preview and publish your experiment in Dynamics 365 Commerce after you've [connected your experiment and edited your variations](experimentation-connect-edit.md).</span></span> <span data-ttu-id="3c591-105">I bilden nedan visas alla steg som ingår när du ställer in och kör ett experiment på en näthandelssajt i Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="3c591-105">The following diagram shows all of the steps involved in setting up and running an experiment on an e-Commerce website in Dynamics 365 Commerce.</span></span> <span data-ttu-id="3c591-106">Ytterligare steg beskrivs i olika avsnitt.</span><span class="sxs-lookup"><span data-stu-id="3c591-106">Additional steps are covered in separate topics.</span></span>

<span data-ttu-id="3c591-107">[ ![Experimentets användarresa – granska och publicera](./media/experimentation_preview_publish.svg) ](./media/experimentation_preview_publish.svg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="3c591-107">[ ![Experimentation user journey - Preview & Publish](./media/experimentation_preview_publish.svg) ](./media/experimentation_preview_publish.svg#lightbox)</span></span>

## <a name="preview-your-experiment-variations"></a><span data-ttu-id="3c591-108">Förhandsgranska experimentvarianterna</span><span class="sxs-lookup"><span data-stu-id="3c591-108">Preview your experiment variations</span></span>
<span data-ttu-id="3c591-109">Du kan förhandsgranskavarianterna och fortsätta redigera dem tills de ser ut som de ska.</span><span class="sxs-lookup"><span data-stu-id="3c591-109">You can preview your variations and continue editing them until they look the way you want them to.</span></span>

<span data-ttu-id="3c591-110">För att förhandsgranska dina experimentvarianter i Commerce webbplatsskaparen, följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="3c591-110">To preview your experiment variations in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="3c591-111">Från rullgardinsmenyn varianter under kommandofältet för att välja innehållet du vill förhandsgranska.</span><span class="sxs-lookup"><span data-stu-id="3c591-111">From the variations drop-down menu below the command bar, select the content you want to preview.</span></span> 
1. <span data-ttu-id="3c591-112">Klicka på **förhandsversion** i kommandofältet.</span><span class="sxs-lookup"><span data-stu-id="3c591-112">On the command bar, select **Preview**.</span></span> <span data-ttu-id="3c591-113">En förhandsversion av hur innehållet kommer att se ut när det publiceras visas.</span><span class="sxs-lookup"><span data-stu-id="3c591-113">A preview of what the content will look like when it's published is displayed.</span></span>
1. <span data-ttu-id="3c591-114">Om du vill förhandsgranska en annan variant markerar du den i variantens listruta och väljer **förhandsversion** igen.</span><span class="sxs-lookup"><span data-stu-id="3c591-114">To preview a different variation, select it from the variation drop-down menu and select **Preview** again.</span></span>

## <a name="publish-your-experiment"></a><span data-ttu-id="3c591-115">Publicera experimentet</span><span class="sxs-lookup"><span data-stu-id="3c591-115">Publish your experiment</span></span>
<span data-ttu-id="3c591-116">Om du inte använder en publiceringsgrupp för att schemalägga när experimentet går i drift och du vill publicera direkt, väljer du **publicera** i kommandofältet.</span><span class="sxs-lookup"><span data-stu-id="3c591-116">If you aren't using a publish group to schedule when your experiment goes live and you want to publish immediately, select **Publish** in the command bar.</span></span> <span data-ttu-id="3c591-117">Alla varianter som hör till experimentet kommer att publiceras.</span><span class="sxs-lookup"><span data-stu-id="3c591-117">All variations that belong to the experiment will be published.</span></span>
    
> [!IMPORTANT]
> <span data-ttu-id="3c591-118">Om sidan har en opublicerad URL måste du först publicera URL:en eller så visas den inte för webbplatsanvändarna.</span><span class="sxs-lookup"><span data-stu-id="3c591-118">If the page has an unpublished URL, you must first publish the URL or it won't be visible to your website users.</span></span> <span data-ttu-id="3c591-119">För detaljer, se [Spara, förhandsgranska och publicera en sida](save-preview-publish-page.md).</span><span class="sxs-lookup"><span data-stu-id="3c591-119">For details, see [Save, preview, and publish a page](save-preview-publish-page.md).</span></span>
    
### <a name="use-publish-groups-to-schedule-when-your-experiment-goes-live"></a><span data-ttu-id="3c591-120">Använda publiceringsgrupper för att schemalägga när experimentet går i drift</span><span class="sxs-lookup"><span data-stu-id="3c591-120">Use publish groups to schedule when your experiment goes live</span></span>
<span data-ttu-id="3c591-121">varianter som skapas i webbplatsskaparen kan schemaläggas för publicering med hjälp av en publiceringsgrupp.</span><span class="sxs-lookup"><span data-stu-id="3c591-121">Variations created in site builder can be scheduled for publishing by using a publish group.</span></span> <span data-ttu-id="3c591-122">I en publiceringsgrupp kan du ansluta en sida eller ett avsnitt till experimentet genom att välja **experiment** i det vänstra navigeringsfönstret.</span><span class="sxs-lookup"><span data-stu-id="3c591-122">Within a publish group, you can connect a page or fragment to your experiment by selecting **Experiments** in the left navigation pane.</span></span> <span data-ttu-id="3c591-123">Du kan också göra detta genom att markera **Sidor** eller **Fragment** och följa instruktionerna i [Anslut ett experiment och redigera variationer](experimentation-connect-edit.md).</span><span class="sxs-lookup"><span data-stu-id="3c591-123">You can also do this by selecting **Pages** or **Fragments** and following the instructions in [Connect an experiment and edit variations](experimentation-connect-edit.md).</span></span> <span data-ttu-id="3c591-124">Mer information om publiceringsgrupper finns i [arbeta med publiceringsgrupper](publish-groups.md).</span><span class="sxs-lookup"><span data-stu-id="3c591-124">For information about publish groups, see [Work with publish groups](publish-groups.md).</span></span>

<span data-ttu-id="3c591-125">När du använder publiceringsgrupper med experiment finns det några viktiga överväganden att tänka på.</span><span class="sxs-lookup"><span data-stu-id="3c591-125">When using publish groups with experiments, there are some important considerations to be aware of.</span></span>
- <span data-ttu-id="3c591-126">När du lägger till en sida eller ett avsnitt som har ett experiment som körs på en publiceringsgrupp, tas experimentet bort från sidan eller avsnittet i publiceringsgruppen.</span><span class="sxs-lookup"><span data-stu-id="3c591-126">When you add a page or fragment that has an experiment running on it to a publish group, the experiment will be removed from the page or fragment in the publish group.</span></span>
- <span data-ttu-id="3c591-127">Experiment som är anslutna till sidor på en aktiv webbplats är inte tillgängliga för sidor i publiceringsgrupper och tvärtom.</span><span class="sxs-lookup"><span data-stu-id="3c591-127">Experiments that are connected to pages in a live site aren't available to pages within publish groups and vice-versa.</span></span> <span data-ttu-id="3c591-128">På samma sätt är sidor som har experiment som körs på den aktiva platsen inte tillgängliga för andra experiment i publiceringsgrupper och vice versa.</span><span class="sxs-lookup"><span data-stu-id="3c591-128">Similarly, pages that have experiments running on them in a live site aren't available to other experiments in publish groups and vice versa.</span></span>
- <span data-ttu-id="3c591-129">När du publicerar eller schemalägger en publiceringsgrupp, publiceras allt innehåll i publiceringsgruppen, oavsett om det finns ett experiment som är associerat med publiceringsgruppen.</span><span class="sxs-lookup"><span data-stu-id="3c591-129">When you publish or schedule a publish group, all content in the publish group is published, regardless of whether there's an experiment associated with the publish group.</span></span>
- <span data-ttu-id="3c591-130">Eftersom en publiceringsgrupp fortsätter att behållas efter att den har publicerats på en aktiv plats, kommer experimenten i publiceringsgruppen också att sparas.</span><span class="sxs-lookup"><span data-stu-id="3c591-130">Because a publish group continues to persist after it's been published to a live site, experiments in the publish group will also persist.</span></span> <span data-ttu-id="3c591-131">Därför kommer du inte att kunna associera andra experiment med samma sida eller fragment.</span><span class="sxs-lookup"><span data-stu-id="3c591-131">Therefore, you won't be able to associate other experiments with the same page or fragment.</span></span> <span data-ttu-id="3c591-132">Du undviker den här begränsningen genom att ta bort alla publiceringsgrupper med beständiga experiment.</span><span class="sxs-lookup"><span data-stu-id="3c591-132">To avoid this limitation, delete any publish groups with persisting experiments.</span></span> <span data-ttu-id="3c591-133">Om du vill ta bort ett experiment på en pågående webbplats som också finns i en publiceringsgrupp ska du ta bort den från publiceringsgruppen först.</span><span class="sxs-lookup"><span data-stu-id="3c591-133">Similarly, if you want to delete an experiment in a live site that also exists in a publish group, delete it from the publish group first.</span></span>

## <a name="previous-step"></a><span data-ttu-id="3c591-134">Föregående steg</span><span class="sxs-lookup"><span data-stu-id="3c591-134">Previous step</span></span>
[<span data-ttu-id="3c591-135">Ansluta till och redigera ett experiment</span><span class="sxs-lookup"><span data-stu-id="3c591-135">Connect and edit an experiment</span></span>](experimentation-connect-edit.md)

## <a name="next-step"></a><span data-ttu-id="3c591-136">Gå vidare</span><span class="sxs-lookup"><span data-stu-id="3c591-136">Next step</span></span>
[<span data-ttu-id="3c591-137">Köra och övervaka ett experiment</span><span class="sxs-lookup"><span data-stu-id="3c591-137">Run and monitor an experiment</span></span>](experimentation-run-monitor.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]