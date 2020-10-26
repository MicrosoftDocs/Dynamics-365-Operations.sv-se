---
title: Höja en variant och slutföra ett experiment
description: I det här avsnittet beskrivs hur du höjer upp en framgångsrik variant och slutför ett experiment i Dynamics 365 Commerce.
author: sushma-rao
manager: AnnBe
ms.date: 09/15/2020
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
ms.openlocfilehash: 2e011f10e908d6a2efe2e928fc5e0abc7659cb8b
ms.sourcegitcommit: b6ab46f6e5ce60e2c3d70a348827eaf60c84cae2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/01/2020
ms.locfileid: "3930288"
---
# <a name="promote-a-variation-and-complete-an-experiment"></a><span data-ttu-id="811c9-103">Höja en variant och slutföra ett experiment</span><span class="sxs-lookup"><span data-stu-id="811c9-103">Promote a variation and complete an experiment</span></span>

<span data-ttu-id="811c9-104">I det här avsnittet beskrivs hur du höjer den variant som gav bäst resultat i experimentet och hur du slutför experimentet.</span><span class="sxs-lookup"><span data-stu-id="811c9-104">This topic describes how to promote the variation that produced the best results in your experiment, and how to complete the experiment.</span></span> <span data-ttu-id="811c9-105">I bilden nedan visas alla steg som ingår när du ställer in och kör ett experiment på en e-handelswebbplats i Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="811c9-105">The following diagram shows all of the steps involved in setting up and running an experiment on an e-Commerce website in Dynamics 365 Commerce.</span></span> <span data-ttu-id="811c9-106">Ytterligare steg beskrivs i olika avsnitt.</span><span class="sxs-lookup"><span data-stu-id="811c9-106">Additional steps are covered in separate topics.</span></span>

<span data-ttu-id="811c9-107">[ ![Experimentets användarresa - granska och slutför](./media/experimentation_review_complete.svg) ](./media/experimentation_review_complete.svg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="811c9-107">[ ![Experimentation user journey - Review & Complete](./media/experimentation_review_complete.svg) ](./media/experimentation_review_complete.svg#lightbox)</span></span>

<span data-ttu-id="811c9-108">När du har [kört ditt experiment](experimentation-run-monitor.md) och samlat in tillräckligt med data för att avgöra vilken variant du vill använda på den aktiva platsen höjer du varianten och avslutar experimentet.</span><span class="sxs-lookup"><span data-stu-id="811c9-108">After you've [run your experiment](experimentation-run-monitor.md) and collected sufficient data to determine which variation you want to use on your live site, you'll promote the variation and end the experiment.</span></span>

## <a name="promote-a-variation"></a><span data-ttu-id="811c9-109">Höj en variant</span><span class="sxs-lookup"><span data-stu-id="811c9-109">Promote a variation</span></span>
<span data-ttu-id="811c9-110">Använd de data och den analys som är relaterade till experimentet i tredjepartstjänsten för att avgöra vilken variant som gav bäst resultat.</span><span class="sxs-lookup"><span data-stu-id="811c9-110">Use the data and analytics related to the experiment in the third-party service to decide which variation produced the best results.</span></span> <span data-ttu-id="811c9-111">Om du vill ersätta det aktuella innehållet på den aktiva platsen med den vinnande varianten så att den är tillgänglig för alla användare av webbplatsen gör du följande:</span><span class="sxs-lookup"><span data-stu-id="811c9-111">To replace the current content on the live site with the winning variation so that it's available to all users of your website, do the following.</span></span> 

1. <span data-ttu-id="811c9-112">Gå till fliken **experiment** i webbplatsskaparen och välj experimentet.</span><span class="sxs-lookup"><span data-stu-id="811c9-112">Go to the **Experiments** tab in site builder and select the experiment.</span></span>
1. <span data-ttu-id="811c9-113">Välj **slutför experimentet** i den översta raden.</span><span class="sxs-lookup"><span data-stu-id="811c9-113">Select **Complete experiment** on the top bar.</span></span>
1. <span data-ttu-id="811c9-114">I dialogmenyn **Slutför experiment** välj **Granska status för ett experiment**.</span><span class="sxs-lookup"><span data-stu-id="811c9-114">In the **Complete the experiment** dialog menu, select **Review the experiment data**.</span></span> <span data-ttu-id="811c9-115">Tredjepartstjänsten öppnas där du kan validera mätvärdena och bestämma vilken variant som presterade bäst.</span><span class="sxs-lookup"><span data-stu-id="811c9-115">The third-party service opens where you can validate the metrics and determine which variation performed the best.</span></span>
1. <span data-ttu-id="811c9-116">I dialogmenyn **Slutför experiment** i webbplatsskaparen, välj vinnande variant och välj sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="811c9-116">In the **Complete the experiment** dialog menu in site builder, select the winning variation and then select **Next**.</span></span>
1. <span data-ttu-id="811c9-117">Öppna tredjepartstjänsten och stoppa experimentet.</span><span class="sxs-lookup"><span data-stu-id="811c9-117">Open the third-party service and stop the experiment.</span></span>
1. <span data-ttu-id="811c9-118">I webbplatsskaparen välj **Slutför** om du vill skriva över den ursprungliga publicerade sidan och publicera den vinnande varianten så att den blir tillgänglig för alla användare av webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="811c9-118">In site builder, select **Complete** to overwrite the original live page and publish the winning variation so that it's available to all users of your website.</span></span> 

> [!NOTE]
> <span data-ttu-id="811c9-119">Om du väljer att behålla den aktuella publicerade sidan och inte publicera en variant väljer du **Publicera om den ursprungliga sidan**.</span><span class="sxs-lookup"><span data-stu-id="811c9-119">If you choose to keep the current live page and not publish a variation, select **Republish the original page**.</span></span>

## <a name="delete-your-experiment"></a><span data-ttu-id="811c9-120">Ta bort experimentet</span><span class="sxs-lookup"><span data-stu-id="811c9-120">Delete your experiment</span></span>
<span data-ttu-id="811c9-121">Det är inte nödvändigt att du tar bort ett slutfört experiment i Commerce, men du kan välja att ta bort det för att spara utrymme eller rensa arbetsytan.</span><span class="sxs-lookup"><span data-stu-id="811c9-121">While it's not required that you delete a completed experiment in Commerce, you may choose to delete it to save space or clean up your workspace.</span></span> <span data-ttu-id="811c9-122">Om du vill ta bort ett experiment gör du följande.</span><span class="sxs-lookup"><span data-stu-id="811c9-122">To delete an experiment, do the following.</span></span>

1. <span data-ttu-id="811c9-123">Gå till fliken **experiment** i webbplatsskaparen och välj experimentet.</span><span class="sxs-lookup"><span data-stu-id="811c9-123">Go to the **Experiments** tab in site builder and select the experiment.</span></span> 
    > [!NOTE]
    > <span data-ttu-id="811c9-124">Om experimentet fortfarande är aktivt, stoppar du experimentet i tredjepartstjänst innan du fortsätter.</span><span class="sxs-lookup"><span data-stu-id="811c9-124">If the experiment is still active, stop the experiment in the third-party service before proceeding.</span></span>
1. <span data-ttu-id="811c9-125">Välj **Upphäv publicering** i kommandofältet om du vill ta bort variantsinnehållet från den aktiva webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="811c9-125">Select **Unpublish** in the command bar to remove the variation content from the live site.</span></span>
1. <span data-ttu-id="811c9-126">Välj **Ta bort** i kommandofältet för att ta bort experimentet.</span><span class="sxs-lookup"><span data-stu-id="811c9-126">Select **Delete** in the command bar to delete the experiment.</span></span>

## <a name="previous-step"></a><span data-ttu-id="811c9-127">Föregående steg</span><span class="sxs-lookup"><span data-stu-id="811c9-127">Previous step</span></span>
[<span data-ttu-id="811c9-128">Köra och övervaka ett experiment</span><span class="sxs-lookup"><span data-stu-id="811c9-128">Run and monitor an experiment</span></span>](experimentation-run-monitor.md)
