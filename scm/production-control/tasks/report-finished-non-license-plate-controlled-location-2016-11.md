--- 
title: "Rapportera som färdig till en plats som styrs av ID-nummer "
description: "Den här uppgiftsguiden visar ett exempel på rapporteringen som slutförd till en plats som inte är ID-nummertyrd."
author: ChristianRytt
manager: AnnBe
ms.date: 06/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: a14efeda12cdb677bf9e82f251d1cb91e36337fb
ms.contentlocale: sv-se
ms.lasthandoff: 08/29/2017

---
# <a name="report-as-finished-to-a-plate-controlled-location"></a><span data-ttu-id="9d6c1-103">Rapportera som färdig till en plats som styrs av ID-nummer </span><span class="sxs-lookup"><span data-stu-id="9d6c1-103">Report as finished to a plate-controlled location</span></span> 

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="9d6c1-104">Den här uppgiftsguiden visar ett exempel på rapporteringen som slutförd till en plats som inte är ID-nummertyrd.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-104">This task guide shows an example of reporting as finished to a location that isn't license plate–controlled.</span></span> <span data-ttu-id="9d6c1-105">En tillämplig arbetspolicy är förutsättningen är den här uppgiften.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-105">An applicable work policy is the prerequisite for this task.</span></span> <span data-ttu-id="9d6c1-106">En tidigare uppgiftsguide visade inställningarna för arbetspolicyn.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-106">A previous task guide showed the setup of the work policy.</span></span> <span data-ttu-id="9d6c1-107">Den här uppgiftsguiden kräver Dynamics AX program 7.0.1 eller senare.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-107">This task guide requires Dynamics AX application 7.0.1 or later.</span></span>




## <a name="set-up-an-output-location"></a><span data-ttu-id="9d6c1-108">Ställ in en utleveransplats</span><span class="sxs-lookup"><span data-stu-id="9d6c1-108">Set up an output location</span></span>
1. <span data-ttu-id="9d6c1-109">Gå till Organisationsadministration > Resurser > Resursgrupper.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-109">Go to Organization administration > Resources > Resource groups.</span></span>
2. <span data-ttu-id="9d6c1-110">Välj resursgrupp "5102" i listan.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-110">In the list, select resource group '5102'.</span></span>
3. <span data-ttu-id="9d6c1-111">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-111">Click Edit.</span></span>
4. <span data-ttu-id="9d6c1-112">Ange "51" i fältet Utleveranslagerställe.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-112">In the Output warehouse field, enter '51'.</span></span>
5. <span data-ttu-id="9d6c1-113">Ange "001" i fältet Utleveransplats.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-113">In the Output location field, enter '001'.</span></span>
    * <span data-ttu-id="9d6c1-114">Plats 001 är en ej ID-nummertyrd plats.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-114">Location 001 isn't a license plate–controlled location.</span></span> <span data-ttu-id="9d6c1-115">Du kan ställa in en plats för ej ID-nummertyrd utleveransplats bara om en lämplig arbetspolicy finns för platsen.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-115">You can set up a non–license plate output location only if an applicable work policy exists for the location.</span></span>  

## <a name="create-a-production-order-and-report-it-as-finished"></a><span data-ttu-id="9d6c1-116">Skapa en produktionsorder och rapportera den som färdig.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-116">Create a production order and report it as finished</span></span>
1. <span data-ttu-id="9d6c1-117">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-117">Close the page.</span></span>
2. <span data-ttu-id="9d6c1-118">Gå till Produktionskontroll > Produktionsorder > Alla produktionsorder.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-118">Go to Production control > Production orders > All production orders.</span></span>
3. <span data-ttu-id="9d6c1-119">Klicka på Ny produktionsorder.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-119">Click New production order.</span></span>
4. <span data-ttu-id="9d6c1-120">Ange ett artikelnummer i fältet "L0101".</span><span class="sxs-lookup"><span data-stu-id="9d6c1-120">In the Item number field, enter 'L0101'.</span></span>
5. <span data-ttu-id="9d6c1-121">Klicka på Skapa.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-121">Click Create.</span></span>
6. <span data-ttu-id="9d6c1-122">Klicka på Produktionsorder i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-122">On the Action Pane, click Production order.</span></span>
7. <span data-ttu-id="9d6c1-123">Klicka på Uppskattning.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-123">Click Estimate.</span></span>
8. <span data-ttu-id="9d6c1-124">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-124">Click OK.</span></span>
9. <span data-ttu-id="9d6c1-125">Klicka på Start.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-125">Click Start.</span></span>
10. <span data-ttu-id="9d6c1-126">Klicka på fliken Allmänt.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-126">Click the General tab.</span></span>
11. <span data-ttu-id="9d6c1-127">Välj "Aldrig" i fältet Automatisk strukturlisteförbrukning.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-127">In the Automatic BOM consumption field, select 'Never'.</span></span>
12. <span data-ttu-id="9d6c1-128">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-128">Click OK.</span></span>
13. <span data-ttu-id="9d6c1-129">Klicka på Rapportera som färdigt.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-129">Click Report as finished.</span></span>
14. <span data-ttu-id="9d6c1-130">Klicka på fliken Allmänt.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-130">Click the General tab.</span></span>
15. <span data-ttu-id="9d6c1-131">Välj Ja i fältet Godkänn fel.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-131">Select Yes in the Accept error field.</span></span>
16. <span data-ttu-id="9d6c1-132">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-132">Click OK.</span></span>
17. <span data-ttu-id="9d6c1-133">Klicka på Lagerställe i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-133">On the Action Pane, click Warehouse.</span></span>
18. <span data-ttu-id="9d6c1-134">Klicka på Information om arbete.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-134">Click Work details.</span></span>
    * <span data-ttu-id="9d6c1-135">När tillverkningsordern rapporterades som färdig, genererades inget arbete för plats.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-135">When the production order was reported as finished, no work was generated for put-away.</span></span> <span data-ttu-id="9d6c1-136">Detta inträffar, eftersom en arbetspolicy definieras som hindrar arbete från att genereras när produkten L0101 rapporterats som färdig till plats 001.</span><span class="sxs-lookup"><span data-stu-id="9d6c1-136">This occurs because a work policy is defined that prevents work from being generated when product L0101 is reported as finished to location 001.</span></span>  


