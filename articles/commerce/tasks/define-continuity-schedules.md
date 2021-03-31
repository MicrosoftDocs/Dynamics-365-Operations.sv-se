---
title: " Definiera kontinuitetstidsplaner"
description: I detta avsnitt beskrivs hur du skapar ett kontinuitetsprogram (även känt som en återkommande order).
author: josaw1
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MCRContinuitySchedule, EcoResProductDetailsExtended
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f385d97ce8c458ada944609e165ebd0db500b546
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5229946"
---
# <a name="define-continuity-schedules"></a><span data-ttu-id="9db08-103"> Definiera kontinuitetstidsplaner</span><span class="sxs-lookup"><span data-stu-id="9db08-103">Define continuity schedules</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9db08-104">I detta avsnitt beskrivs hur du skapar ett kontinuitetsprogram (även känt som en återkommande order).</span><span class="sxs-lookup"><span data-stu-id="9db08-104">This topic walks through setting up a continuity program (otherwise known as reoccurring orders).</span></span> <span data-ttu-id="9db08-105">Detta ämne använder företaget USRT för demonstrationsdatan.</span><span class="sxs-lookup"><span data-stu-id="9db08-105">This topic uses company USRT in the demo data.</span></span>


## <a name="create-continuity-program"></a><span data-ttu-id="9db08-106">Skapa ett kontinuitetsprogram</span><span class="sxs-lookup"><span data-stu-id="9db08-106">Create continuity program</span></span>
1. <span data-ttu-id="9db08-107">Gå till Butik och handel > Kontinuitet > Kontinuitetsprogram.</span><span class="sxs-lookup"><span data-stu-id="9db08-107">Go to Retail and Commerce > Continuity > Continuity programs.</span></span>
2. <span data-ttu-id="9db08-108">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="9db08-108">Click New.</span></span>
3. <span data-ttu-id="9db08-109">Ange ID för kontinuitetstidsplan i fältet Schedule ID.</span><span class="sxs-lookup"><span data-stu-id="9db08-109">In the Schedule ID field, type the continuity schedule ID.</span></span>
4. <span data-ttu-id="9db08-110">I fältet Order start väljer du "First event".</span><span class="sxs-lookup"><span data-stu-id="9db08-110">In the Order start field, select 'First event'.</span></span>
    * <span data-ttu-id="9db08-111">Om en kund lägger en ny order för kontinuitetsprogrammet finns det två alternativ för vilken produkten levereras: 1.</span><span class="sxs-lookup"><span data-stu-id="9db08-111">If a customer places a new order for the continuity program, there are two options for which product will be shipped:  1.</span></span> <span data-ttu-id="9db08-112">Första händelse: den första produkten i kontinuitetsprogrammet ska levereras.</span><span class="sxs-lookup"><span data-stu-id="9db08-112">First event: the first product in the continuity program will be shipped.</span></span>  <span data-ttu-id="9db08-113">2.</span><span class="sxs-lookup"><span data-stu-id="9db08-113">2.</span></span> <span data-ttu-id="9db08-114">Aktuell händelse: den aktuella produkten skickas.</span><span class="sxs-lookup"><span data-stu-id="9db08-114">Current event: the current product will be shipped.</span></span> <span data-ttu-id="9db08-115">Till exempel:</span><span class="sxs-lookup"><span data-stu-id="9db08-115">For example.</span></span> <span data-ttu-id="9db08-116">tre månader efter programmets början får kunden den tredje i programmet.</span><span class="sxs-lookup"><span data-stu-id="9db08-116">three months into the program, the customer will receive the third in the program.</span></span>  
5. <span data-ttu-id="9db08-117">Välj ”Yes” om du vill efterfråga orderstartdatumet.</span><span class="sxs-lookup"><span data-stu-id="9db08-117">Select 'Yes' to prompt for the order start date.</span></span>
6. <span data-ttu-id="9db08-118">Klicka på Lägg till rad.</span><span class="sxs-lookup"><span data-stu-id="9db08-118">Click Add line.</span></span>
7. <span data-ttu-id="9db08-119">I fältet Item number anger du artikelnumret för den första produkten ("0013").</span><span class="sxs-lookup"><span data-stu-id="9db08-119">In the Item number field, type the item number for the first product ('0013').</span></span>
8. <span data-ttu-id="9db08-120">Ange "CP".</span><span class="sxs-lookup"><span data-stu-id="9db08-120">Type 'CP'.</span></span>
9. <span data-ttu-id="9db08-121">Ange det datum då den första produkten finns tillgänglig för order.</span><span class="sxs-lookup"><span data-stu-id="9db08-121">Enter the date when the first product will be available for order.</span></span>
10. <span data-ttu-id="9db08-122">Klicka på Lägg till rad.</span><span class="sxs-lookup"><span data-stu-id="9db08-122">Click Add line.</span></span>
11. <span data-ttu-id="9db08-123">Skriv 0014 i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="9db08-123">In the Item number field, type '0014'.</span></span>
12. <span data-ttu-id="9db08-124">I fältet för datumintervallskod rensar du värdet så att fältet står tomt.</span><span class="sxs-lookup"><span data-stu-id="9db08-124">In the Date interval code field, clear the value so the field is empty.</span></span>
    * <span data-ttu-id="9db08-125">Rensa datumintervallet för denna procedur.</span><span class="sxs-lookup"><span data-stu-id="9db08-125">For this procedure, clear the date interval.</span></span> <span data-ttu-id="9db08-126">Du anger datumet som inkrementellt från startdatum för den första artikeln.</span><span class="sxs-lookup"><span data-stu-id="9db08-126">You'll set the date as incremental from the start date of the first item.</span></span>  
13. <span data-ttu-id="9db08-127">Här kan du ange det intervallet då produkterna skickas.</span><span class="sxs-lookup"><span data-stu-id="9db08-127">Here you'll enter the interval at which the products are shipped.</span></span> <span data-ttu-id="9db08-128">Ange "30".</span><span class="sxs-lookup"><span data-stu-id="9db08-128">Type '30'.</span></span>
    * <span data-ttu-id="9db08-129">För att ett månatligt program ska du ange 30 dagar för intervallet.</span><span class="sxs-lookup"><span data-stu-id="9db08-129">For a monthly program, you'll enter 30 days for the interval.</span></span>  
14. <span data-ttu-id="9db08-130">Klicka på Lägg till rad.</span><span class="sxs-lookup"><span data-stu-id="9db08-130">Click Add line.</span></span>
15. <span data-ttu-id="9db08-131">Skriv 0015 i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="9db08-131">In the Item number field, type '0015'.</span></span>
16. <span data-ttu-id="9db08-132">Ange "End".</span><span class="sxs-lookup"><span data-stu-id="9db08-132">Type 'End'.</span></span>
17. <span data-ttu-id="9db08-133">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="9db08-133">Click Save.</span></span>

## <a name="assign-to-continuity-item"></a><span data-ttu-id="9db08-134">Tilldela till en kontinuitetsartikel</span><span class="sxs-lookup"><span data-stu-id="9db08-134">Assign to continuity item</span></span>
1. <span data-ttu-id="9db08-135">Gå till Produktinformationshantering > Produkter > Frisläppta produkter.</span><span class="sxs-lookup"><span data-stu-id="9db08-135">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="9db08-136">Välj artikel "0016".</span><span class="sxs-lookup"><span data-stu-id="9db08-136">Select item '0016'.</span></span>
    * <span data-ttu-id="9db08-137">För den här proceduren väljer du artikel nummer 0016.</span><span class="sxs-lookup"><span data-stu-id="9db08-137">For this procedure, you'll select item number 0016.</span></span> <span data-ttu-id="9db08-138">Normalt har du skapat en frisläppt produkt som har ytterligare tillämpad kontinuitetsaffärslogik när den läggs på en försäljningsorder hos kundtjänsten.</span><span class="sxs-lookup"><span data-stu-id="9db08-138">Normally, you'll have created a released product that has additional continuity business logic applied when it's placed on a sales order in call center.</span></span>  
3. <span data-ttu-id="9db08-139">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="9db08-139">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="9db08-140">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="9db08-140">Click Edit.</span></span>
5. <span data-ttu-id="9db08-141">Expandera eller komprimera sälja avsnitt.</span><span class="sxs-lookup"><span data-stu-id="9db08-141">Expand or collapse the Sell section.</span></span>
6. <span data-ttu-id="9db08-142">Här kan du ange det kontinuitetsprogram som denna artikel representerar.</span><span class="sxs-lookup"><span data-stu-id="9db08-142">Here you'll enter the continuity program that this item represents.</span></span> <span data-ttu-id="9db08-143">Ange det tidsplans-ID som du skapade tidigare.</span><span class="sxs-lookup"><span data-stu-id="9db08-143">Type the Schedule ID you created earlier.</span></span>
    * <span data-ttu-id="9db08-144">När artikeln säljs hos en kundtjänst tillämpas affärslogik från det valda kontinuitetsprogrammet.</span><span class="sxs-lookup"><span data-stu-id="9db08-144">When this item is sold in a call center, additional business logic is applied from the selected continuity program.</span></span>  
7. <span data-ttu-id="9db08-145">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="9db08-145">Click Save.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]