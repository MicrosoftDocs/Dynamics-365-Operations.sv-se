--- 
title: Avsluta en produktionsorder
description: "Den här proceduren visar hur du avslutar en produktionsorder."
author: johanhoffmann
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 75b91ea330258a5b57e9e58cb32539d57e458f28
ms.contentlocale: sv-se
ms.lasthandoff: 08/29/2017

---
# <a name="end-a-production-order"></a><span data-ttu-id="8b772-103">Avsluta en produktionsorder</span><span class="sxs-lookup"><span data-stu-id="8b772-103">End a production order</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8b772-104">Den här proceduren visar hur du avslutar en produktionsorder.</span><span class="sxs-lookup"><span data-stu-id="8b772-104">This procedure shows how to end a production order.</span></span> <span data-ttu-id="8b772-105">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="8b772-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="8b772-106">Detta är den sista proceduren av sju som förklarar produktionsorderns livscykel.</span><span class="sxs-lookup"><span data-stu-id="8b772-106">This is the final procedure out of seven which explains the production order lifecycle.</span></span>


## <a name="end-a-production-order"></a><span data-ttu-id="8b772-107">Avsluta en produktionsorder</span><span class="sxs-lookup"><span data-stu-id="8b772-107">End a production order</span></span>
1. <span data-ttu-id="8b772-108">Gå till Produktionskontroll > Produktionsorder > Alla produktionsorder.</span><span class="sxs-lookup"><span data-stu-id="8b772-108">Go to Production control > Production orders > All production orders.</span></span>
    * <span data-ttu-id="8b772-109">Välj en produktionsorder som har statusen Rapporterat som färdigt.</span><span class="sxs-lookup"><span data-stu-id="8b772-109">Select a production order that has the status Reported as finished.</span></span>  
2. <span data-ttu-id="8b772-110">Klicka på Produktionsorder i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="8b772-110">On the Action Pane, click Production order.</span></span>
3. <span data-ttu-id="8b772-111">Klicka på Slut.</span><span class="sxs-lookup"><span data-stu-id="8b772-111">Click End.</span></span>
    * <span data-ttu-id="8b772-112">På den här sidan kan du bekräfta att du vill avsluta produktionsordern.</span><span class="sxs-lookup"><span data-stu-id="8b772-112">On this page, you can confirm that you want to end the production order.</span></span>  
4. <span data-ttu-id="8b772-113">Klicka på fliken Allmänt.</span><span class="sxs-lookup"><span data-stu-id="8b772-113">Click the General tab.</span></span>
5. <span data-ttu-id="8b772-114">Ange ett datum i fältet Datum.</span><span class="sxs-lookup"><span data-stu-id="8b772-114">In the Date field, enter a date.</span></span>
6. <span data-ttu-id="8b772-115">Välj ”Allokering” i fältet Kassationsmetod.</span><span class="sxs-lookup"><span data-stu-id="8b772-115">In the Scrap method field, select 'Allocation'.</span></span>
    * <span data-ttu-id="8b772-116">När du väljer allokeringsmetod läggs kostnaderna från de kasserade materialen till för de färdiga varorna.</span><span class="sxs-lookup"><span data-stu-id="8b772-116">When you select the Allocation method, costs from the scrapped materials are added to the finished goods.</span></span>  
7. <span data-ttu-id="8b772-117">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="8b772-117">Click OK.</span></span>

## <a name="validate-calculation-results"></a><span data-ttu-id="8b772-118">Validera beräkningsresultatet</span><span class="sxs-lookup"><span data-stu-id="8b772-118">Validate calculation results</span></span>
1. <span data-ttu-id="8b772-119">Klicka på Hantera kostnader i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="8b772-119">On the Action Pane, click Manage costs.</span></span>
2. <span data-ttu-id="8b772-120">Klicka på Visa kostnadsjämförelse.</span><span class="sxs-lookup"><span data-stu-id="8b772-120">Click View cost comparison.</span></span>
    * <span data-ttu-id="8b772-121">När du har avslutat produktionsordern kan du jämföra den uppskattade självkostnaden med den verkliga självkostnaden för att få en överblick över produktionsavvikelserna.</span><span class="sxs-lookup"><span data-stu-id="8b772-121">After you have ended the production order, you can compare the estimated cost price against the realized cost price to get an overview of the production variances.</span></span>  


