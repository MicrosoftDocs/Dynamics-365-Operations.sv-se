---
title: Köra och övervaka ett experiment
description: I det här avsnittet beskrivs hur du kör och övervakar ett experiment i en tredjepartstjänst. Det beskriver också hur du gör ändringar i varianter efter att experimentet har startats.
author: sushma-rao
manager: AnnBe
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: ee86a6761b27f3c08a65a2e250659cdcfd71db44
ms.sourcegitcommit: cd83f2bc0e52e13071ad306e07e4c255fc65cb03
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/22/2020
ms.locfileid: "4415976"
---
# <a name="run-and-monitor-an-experiment"></a><span data-ttu-id="b68a0-104">Köra och övervaka ett experiment</span><span class="sxs-lookup"><span data-stu-id="b68a0-104">Run and monitor an experiment</span></span>

<span data-ttu-id="b68a0-105">I det här avsnittet beskrivs hur du kör och övervakar ditt experiment i en annan tillverkare och ändrar varianter om det behövs.</span><span class="sxs-lookup"><span data-stu-id="b68a0-105">This topic describes how to run and monitor your experiment in a third-party app, and change variations if needed.</span></span> <span data-ttu-id="b68a0-106">Innan du slutför stegen i det här avsnittet måste du först [publicera](experimentation-preview-publish.md) experimentet i Commerce.</span><span class="sxs-lookup"><span data-stu-id="b68a0-106">Before you complete the steps in this topic, you'll first need to [publish](experimentation-preview-publish.md) your experiment in Commerce.</span></span> 

<span data-ttu-id="b68a0-107">I bilden nedan visas alla steg som ingår när du ställer in och kör ett experiment på en näthandelswebbplats i Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="b68a0-107">The following diagram shows all of the steps involved in setting up and running an experiment on an e-Commerce website in Dynamics 365 Commerce.</span></span> <span data-ttu-id="b68a0-108">Ytterligare steg beskrivs i olika avsnitt.</span><span class="sxs-lookup"><span data-stu-id="b68a0-108">Additional steps are covered in separate topics.</span></span>

<span data-ttu-id="b68a0-109">[ ![Experimentets användarresa - kör och övervaka](./media/experimentation_run_monitor.svg) ](./media/experimentation_run_monitor.svg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="b68a0-109">[ ![Experimentation user journey - Run & Monitor](./media/experimentation_run_monitor.svg) ](./media/experimentation_run_monitor.svg#lightbox)</span></span>

<span data-ttu-id="b68a0-110">När du har publicerat dina varianter måste du utföra experimentet med alla steg du behöver slutföra i Commerce.</span><span class="sxs-lookup"><span data-stu-id="b68a0-110">After you publish your variations, all of the steps you need to do in Commerce to run your experiment are complete.</span></span> <span data-ttu-id="b68a0-111">Nästa steg bestämmer vilken variant som ska visas för varje användare när de begär en sida.</span><span class="sxs-lookup"><span data-stu-id="b68a0-111">The next step is determining which variation to show to each user when they request a page.</span></span> <span data-ttu-id="b68a0-112">Den tredje partens tjänst gör det enkelt att fastställa, men först måste du aktivera experimentet inom tjänsten.</span><span class="sxs-lookup"><span data-stu-id="b68a0-112">The third-party service makes that determination, but first you have to activate the experiment within the service.</span></span> <span data-ttu-id="b68a0-113">Eftersom stegen för att aktivera ett experiment varierar från tjänst till tjänst måste du följa instruktionerna som medföljde tjänsten eller leverantören.</span><span class="sxs-lookup"><span data-stu-id="b68a0-113">Since the steps for activating an experiment vary from service to service, you'll need to follow the instructions included with your service or provider.</span></span> <span data-ttu-id="b68a0-114">Om experimentet inte har aktiverats visas standardversionen för sidan (utan att några varianter visas).</span><span class="sxs-lookup"><span data-stu-id="b68a0-114">If the experiment is not activated, users will only see the default version of the page (no variations will be displayed).</span></span>

<span data-ttu-id="b68a0-115">Du måste hålla experimentet tillräckligt länge för att samla in data för statistiskt giltiga resultat.</span><span class="sxs-lookup"><span data-stu-id="b68a0-115">You'll need to keep the experiment running long enough to gather data for statistically valid results.</span></span> <span data-ttu-id="b68a0-116">Använd tjänsten från en annan leverantör för att övervaka de experimentbaserade data och analyser medan experimentet körs.</span><span class="sxs-lookup"><span data-stu-id="b68a0-116">Use the third-party service to monitor the experiment-related data and analytics while the experiment is running.</span></span>

## <a name="adjust-your-variations"></a><span data-ttu-id="b68a0-117">Justera varianterna</span><span class="sxs-lookup"><span data-stu-id="b68a0-117">Adjust your variations</span></span>
<span data-ttu-id="b68a0-118">Om du av någon anledning skulle behöva ändra varianterna följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="b68a0-118">If for any reason you need to modify your variations, follow the steps below.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b68a0-119">Om du gör ändringar i ett publicerat experiment i Commerce eller från tjänsten för tredje part, kan resultaten bli betydligt effektfulla.</span><span class="sxs-lookup"><span data-stu-id="b68a0-119">If you make changes to a live experiment in Commerce or the third-party service, your results may be significantly impacted.</span></span> <span data-ttu-id="b68a0-120">Överväg att låta experimentet köra kursen och sedan skapa ett nytt experiment med större ändringar.</span><span class="sxs-lookup"><span data-stu-id="b68a0-120">Consider letting the experiment run its course and then creating a new experiment for major changes.</span></span>

1. <span data-ttu-id="b68a0-121">I Commerce webbplatsskaparen, välj **experiment** i det vänstra navigeringsfönstret och välj sedan experimentet.</span><span class="sxs-lookup"><span data-stu-id="b68a0-121">In Commerce site builder, select **Experiments** in the left navigation pane, and then select the experiment.</span></span> 
1. <span data-ttu-id="b68a0-122">Välj den variant som du vill uppdatera på listrutan.</span><span class="sxs-lookup"><span data-stu-id="b68a0-122">Select the variation you want to update from the drop-down menu.</span></span>
1. <span data-ttu-id="b68a0-123">Gör nödvändiga ändringar och förhandsgranska och publicera sedan varianterna.</span><span class="sxs-lookup"><span data-stu-id="b68a0-123">Make any needed changes, and then preview and publish the variations.</span></span> <span data-ttu-id="b68a0-124">Mer information finns i [Förhandsgranska och publicera ett experiment](experimentation-preview-publish.md).</span><span class="sxs-lookup"><span data-stu-id="b68a0-124">For more information, see [Preview and publish an experiment](experimentation-preview-publish.md).</span></span>
1. <span data-ttu-id="b68a0-125">Gå till tjänsten från tredje part för att göra eventuella experiment inställningar som är relaterade till ändring.</span><span class="sxs-lookup"><span data-stu-id="b68a0-125">Go to the third-party service to make any experiment setup-related changes.</span></span>
    
## <a name="previous-step"></a><span data-ttu-id="b68a0-126">Föregående steg</span><span class="sxs-lookup"><span data-stu-id="b68a0-126">Previous step</span></span>
[<span data-ttu-id="b68a0-127">Förhandsgranska och publicera ett experiment</span><span class="sxs-lookup"><span data-stu-id="b68a0-127">Preview and publish an experiment</span></span>](experimentation-preview-publish.md)

## <a name="next-step"></a><span data-ttu-id="b68a0-128">Gå vidare</span><span class="sxs-lookup"><span data-stu-id="b68a0-128">Next step</span></span>
[<span data-ttu-id="b68a0-129">Höja en variant och slutföra ett experiment</span><span class="sxs-lookup"><span data-stu-id="b68a0-129">Promote a variation and complete an experiment</span></span>](experimentation-review-complete.md)
