---
title: Höja en variant och slutföra ett experiment
description: I det här avsnittet beskrivs hur du höjer upp en framgångsrik variant och slutför ett experiment i Dynamics 365 Commerce.
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
ms.openlocfilehash: 25cccbeae5c263a3032eeebf2fc5335e22c1415a
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "5009943"
---
# <a name="promote-a-variation-and-complete-an-experiment"></a><span data-ttu-id="d19e2-103">Höja en variant och slutföra ett experiment</span><span class="sxs-lookup"><span data-stu-id="d19e2-103">Promote a variation and complete an experiment</span></span>

<span data-ttu-id="d19e2-104">I det här avsnittet beskrivs hur du höjer den variant som gav bäst resultat i experimentet och hur du slutför experimentet.</span><span class="sxs-lookup"><span data-stu-id="d19e2-104">This topic describes how to promote the variation that produced the best results in your experiment, and how to complete the experiment.</span></span> <span data-ttu-id="d19e2-105">I bilden nedan visas alla steg som ingår när du ställer in och kör ett experiment på en näthandelssajt i Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="d19e2-105">The following diagram shows all of the steps involved in setting up and running an experiment on an e-Commerce website in Dynamics 365 Commerce.</span></span> <span data-ttu-id="d19e2-106">Ytterligare steg beskrivs i olika avsnitt.</span><span class="sxs-lookup"><span data-stu-id="d19e2-106">Additional steps are covered in separate topics.</span></span>

<span data-ttu-id="d19e2-107">[ ![Experimentets användarresa – granska och slutför](./media/experimentation_review_complete.svg) ](./media/experimentation_review_complete.svg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="d19e2-107">[ ![Experimentation user journey - Review & Complete](./media/experimentation_review_complete.svg) ](./media/experimentation_review_complete.svg#lightbox)</span></span>

<span data-ttu-id="d19e2-108">När du har [kört ditt experiment](experimentation-run-monitor.md) och samlat in tillräckligt med data för att avgöra vilken variant du vill använda på den aktiva platsen höjer du varianten och avslutar experimentet.</span><span class="sxs-lookup"><span data-stu-id="d19e2-108">After you've [run your experiment](experimentation-run-monitor.md) and collected sufficient data to determine which variation you want to use on your live site, you'll promote the variation and end the experiment.</span></span>

## <a name="promote-a-variation"></a><span data-ttu-id="d19e2-109">Höj en variant</span><span class="sxs-lookup"><span data-stu-id="d19e2-109">Promote a variation</span></span>
<span data-ttu-id="d19e2-110">Använd de data och den analys som är relaterade till experimentet i tredjepartstjänsten för att avgöra vilken variant som gav bäst resultat.</span><span class="sxs-lookup"><span data-stu-id="d19e2-110">Use the data and analytics related to the experiment in the third-party service to decide which variation produced the best results.</span></span> <span data-ttu-id="d19e2-111">Du kan sedan flytta upp det genom att ersätta det aktuella innehållet på den aktiva platsen med den vinnande varianten så att den är tillgänglig för alla användare av webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="d19e2-111">You can then promote it by replacing the current content on the live site with the winning variation so that it's available to all users of your website.</span></span>

<span data-ttu-id="d19e2-112">Gör så här för att befordra den vinnande variationen:</span><span class="sxs-lookup"><span data-stu-id="d19e2-112">To promote the winning variation, follow these steps.</span></span> 

1. <span data-ttu-id="d19e2-113">I Commerce webbplatsskaparen, välj **experiment** i det vänstra navigeringsfönstret och välj sedan experimentet.</span><span class="sxs-lookup"><span data-stu-id="d19e2-113">In Commerce site builder, select **Experiments** in the left navigation pane, and then select the experiment.</span></span>
1. <span data-ttu-id="d19e2-114">I kommandofältet, välj **slutför experimentet**.</span><span class="sxs-lookup"><span data-stu-id="d19e2-114">On the command bar, select **Complete experiment**.</span></span>
1. <span data-ttu-id="d19e2-115">I dialogrutan **Slutför experiment** välj **Granska status för ett experiment**.</span><span class="sxs-lookup"><span data-stu-id="d19e2-115">In the **Complete the experiment** dialog box, select **Review the experiment data**.</span></span> <span data-ttu-id="d19e2-116">Tredjepartstjänsten öppnas där du kan validera mätvärdena och bestämma vilken variant som presterade bäst.</span><span class="sxs-lookup"><span data-stu-id="d19e2-116">The third-party service opens where you can validate the metrics and determine which variation performed the best.</span></span>
1. <span data-ttu-id="d19e2-117">I dialogrutan **Slutför experiment**, välj vinnande variant och välj sedan **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="d19e2-117">In the **Complete the experiment** dialog box, select the winning variation, and then select **Next**.</span></span>
1. <span data-ttu-id="d19e2-118">Öppna tredjepartstjänsten och stoppa experimentet.</span><span class="sxs-lookup"><span data-stu-id="d19e2-118">Open the third-party service and stop the experiment.</span></span>
1. <span data-ttu-id="d19e2-119">I webbplatsskaparen välj **Slutför** om du vill skriva över den ursprungliga publicerade sidan och publicera den vinnande varianten så att den blir tillgänglig för alla användare av webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="d19e2-119">In site builder, select **Complete** to overwrite the original live page and publish the winning variation so that it's available to all users of your website.</span></span> 

> [!NOTE]
> <span data-ttu-id="d19e2-120">Om du väljer att behålla den aktuella publicerade sidan och inte publicera en variant väljer du **Publicera om den ursprungliga sidan**.</span><span class="sxs-lookup"><span data-stu-id="d19e2-120">If you choose to keep the current live page and not publish a variation, select **Republish the original page**.</span></span>

## <a name="delete-your-experiment"></a><span data-ttu-id="d19e2-121">Ta bort experimentet</span><span class="sxs-lookup"><span data-stu-id="d19e2-121">Delete your experiment</span></span>
<span data-ttu-id="d19e2-122">Det är inte nödvändigt att du tar bort ett slutfört experiment i Commerce, men du kan välja att ta bort det för att spara utrymme eller rensa arbetsytan.</span><span class="sxs-lookup"><span data-stu-id="d19e2-122">While it's not required that you delete a completed experiment in Commerce, you may choose to delete it to save space or clean up your workspace.</span></span> 

<span data-ttu-id="d19e2-123">För att ta bort ett experiment i Commerce webbplatsskaparen, följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="d19e2-123">To delete an experiment in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="d19e2-124">Välj **experiment** i det vänstra navigeringsfönstret och välj sedan experimentet.</span><span class="sxs-lookup"><span data-stu-id="d19e2-124">Select **Experiments** in the left navigation pane, and then select the experiment.</span></span> 
    > [!NOTE]
    > <span data-ttu-id="d19e2-125">Om experimentet fortfarande är aktivt, stoppar du experimentet i tredjepartstjänst innan du fortsätter.</span><span class="sxs-lookup"><span data-stu-id="d19e2-125">If the experiment is still active, stop the experiment in the third-party service before proceeding.</span></span>
1. <span data-ttu-id="d19e2-126">I kommandofältet, välj **Upphäv publicering** om du vill ta bort variantinnehållet från den aktiva webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="d19e2-126">On the command bar, select **Unpublish**  to remove the variation content from the live site.</span></span>
1. <span data-ttu-id="d19e2-127">Välj **Ta bort** för att ta bort experimentet.</span><span class="sxs-lookup"><span data-stu-id="d19e2-127">Select **Delete** to delete the experiment.</span></span>

## <a name="previous-step"></a><span data-ttu-id="d19e2-128">Föregående steg</span><span class="sxs-lookup"><span data-stu-id="d19e2-128">Previous step</span></span>
[<span data-ttu-id="d19e2-129">Köra och övervaka ett experiment</span><span class="sxs-lookup"><span data-stu-id="d19e2-129">Run and monitor an experiment</span></span>](experimentation-run-monitor.md)
