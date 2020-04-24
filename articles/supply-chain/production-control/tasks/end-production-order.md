---
title: Avsluta en produktionsorder
description: Den här proceduren visar hur du avslutar en produktionsorder.
author: johanhoffmann
manager: tfehr
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fade659c320e0ea1059644324859c9a3cb273c96
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3207081"
---
# <a name="end-a-production-order"></a><span data-ttu-id="5c608-103">Avsluta en produktionsorder</span><span class="sxs-lookup"><span data-stu-id="5c608-103">End a production order</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="5c608-104">Den här proceduren visar hur du avslutar en produktionsorder.</span><span class="sxs-lookup"><span data-stu-id="5c608-104">This procedure shows how to end a production order.</span></span> <span data-ttu-id="5c608-105">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="5c608-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="5c608-106">Detta är den sista proceduren av sju som förklarar produktionsorderns livscykel.</span><span class="sxs-lookup"><span data-stu-id="5c608-106">This is the final procedure out of seven which explains the production order lifecycle.</span></span>


## <a name="end-a-production-order"></a><span data-ttu-id="5c608-107">Avsluta en produktionsorder</span><span class="sxs-lookup"><span data-stu-id="5c608-107">End a production order</span></span>
1. <span data-ttu-id="5c608-108">Gå till Produktionskontroll > Produktionsorder > Alla produktionsorder.</span><span class="sxs-lookup"><span data-stu-id="5c608-108">Go to Production control > Production orders > All production orders.</span></span>
    * <span data-ttu-id="5c608-109">Välj en produktionsorder som har statusen Rapporterat som färdigt.</span><span class="sxs-lookup"><span data-stu-id="5c608-109">Select a production order that has the status Reported as finished.</span></span>  
2. <span data-ttu-id="5c608-110">Klicka på Produktionsorder i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="5c608-110">On the Action Pane, click Production order.</span></span>
3. <span data-ttu-id="5c608-111">Klicka på Slut.</span><span class="sxs-lookup"><span data-stu-id="5c608-111">Click End.</span></span>
    * <span data-ttu-id="5c608-112">På den här sidan kan du bekräfta att du vill avsluta produktionsordern.</span><span class="sxs-lookup"><span data-stu-id="5c608-112">On this page, you can confirm that you want to end the production order.</span></span>  
4. <span data-ttu-id="5c608-113">Klicka på fliken Allmänt.</span><span class="sxs-lookup"><span data-stu-id="5c608-113">Click the General tab.</span></span>
5. <span data-ttu-id="5c608-114">Ange ett datum i fältet Datum.</span><span class="sxs-lookup"><span data-stu-id="5c608-114">In the Date field, enter a date.</span></span>
6. <span data-ttu-id="5c608-115">Välj ”Allokering” i fältet Kassationsmetod.</span><span class="sxs-lookup"><span data-stu-id="5c608-115">In the Scrap method field, select 'Allocation'.</span></span>
    * <span data-ttu-id="5c608-116">När du väljer allokeringsmetod läggs kostnaderna från de kasserade materialen till för de färdiga varorna.</span><span class="sxs-lookup"><span data-stu-id="5c608-116">When you select the Allocation method, costs from the scrapped materials are added to the finished goods.</span></span>  
7. <span data-ttu-id="5c608-117">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="5c608-117">Click OK.</span></span>

## <a name="validate-calculation-results"></a><span data-ttu-id="5c608-118">Validera beräkningsresultatet</span><span class="sxs-lookup"><span data-stu-id="5c608-118">Validate calculation results</span></span>
1. <span data-ttu-id="5c608-119">Klicka på Hantera kostnader i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="5c608-119">On the Action Pane, click Manage costs.</span></span>
2. <span data-ttu-id="5c608-120">Klicka på Visa kostnadsjämförelse.</span><span class="sxs-lookup"><span data-stu-id="5c608-120">Click View cost comparison.</span></span>
    * <span data-ttu-id="5c608-121">När du har avslutat produktionsordern kan du jämföra den uppskattade självkostnaden med den verkliga självkostnaden för att få en överblick över produktionsavvikelserna.</span><span class="sxs-lookup"><span data-stu-id="5c608-121">After you have ended the production order, you can compare the estimated cost price against the realized cost price to get an overview of the production variances.</span></span>  
