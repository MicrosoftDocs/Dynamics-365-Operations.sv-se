---
title: Felsöka reservationer i distributionslagerhantering
description: I det här avsnittet beskrivs hur du åtgärdar vanliga problem som kan uppstå när du arbetar med lagerreservationer i Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
manager: tfehr
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-10-19
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: a9a5d20732a802fc58c392853af8334bbc07de73
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5248725"
---
# <a name="troubleshoot-reservations-in-warehouse-management"></a><span data-ttu-id="de7a7-103">Felsöka reservationer i distributionslagerhantering</span><span class="sxs-lookup"><span data-stu-id="de7a7-103">Troubleshoot reservations in warehouse management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="de7a7-104">I det här avsnittet beskrivs hur du åtgärdar vanliga problem som kan uppstå när du arbetar med lagerreservationer i Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="de7a7-104">This topic describes how to fix common issues that you might encounter while you work with warehouse reservations in Microsoft Dynamics 365 Supply Chain Management.</span></span>

## <a name="i-receive-the-following-error-message-reservations-cannot-be-removed-because-there-is-work-created-which-relies-on-the-reservations"></a><span data-ttu-id="de7a7-105">Jag får följande felmeddelande: "reservationer kan inte tas bort eftersom det finns ett arbete skapat som använder reservationerna".</span><span class="sxs-lookup"><span data-stu-id="de7a7-105">I receive the following error message: "Reservations cannot be removed because there is work created which relies on the reservations."</span></span>

### <a name="issue-description"></a><span data-ttu-id="de7a7-106">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="de7a7-106">Issue description</span></span>

<span data-ttu-id="de7a7-107">Du kan inte icke-reserverade på en försäljningsrad, eftersom det är öppet arbete på raden.</span><span class="sxs-lookup"><span data-stu-id="de7a7-107">You can't unreserve inventory on a sales line, because there is open work against the line.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="de7a7-108">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="de7a7-108">Issue resolution</span></span>

<span data-ttu-id="de7a7-109">Undersök om öppna förpackningsgrupparbete finns för att hämta artikeln från en förpackningsstation till en annan plats (t.ex. *Baydoor*).</span><span class="sxs-lookup"><span data-stu-id="de7a7-109">Investigate whether open packing group work exists to bring the item from a packing station to another location (such as *Baydoor*).</span></span> <span data-ttu-id="de7a7-110">Granska posterna på sidorna för **Loggen över arbetsskapande** och **Arbetsinformation** för att avgöra vad som fysiskt reserverar inventeringen och sedan slutföra eller ta bort arbetet för att frigöra reservationen.</span><span class="sxs-lookup"><span data-stu-id="de7a7-110">Review the records on the **Work creation history log** and **Work details** pages to determine what is physically reserving the inventory, and then complete or delete the work to free up the reservation.</span></span>

## <a name="i-receive-the-following-error-message-inventory-quantity--1-could-not-be-updated-due-to-insufficient-inventory-transactions-for-item-2"></a><span data-ttu-id="de7a7-111">Följande felmeddelande visas: "lagerkvantitet -%1 kunde inte uppdateras på grund av otillräckliga lagertransaktioner för artikel %2...".</span><span class="sxs-lookup"><span data-stu-id="de7a7-111">I receive the following error message: "Inventory quantity -%1 could not be updated due to insufficient inventory transactions for item %2...."</span></span>

### <a name="issue-description"></a><span data-ttu-id="de7a7-112">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="de7a7-112">Issue description</span></span>

<span data-ttu-id="de7a7-113">Det här problemet kan uppstå om systemet inte kan uppdatera en lagerkvantitet eftersom det inte finns tillräckligt många lagertransaktioner med de angivna dimensionerna.</span><span class="sxs-lookup"><span data-stu-id="de7a7-113">This issue can occur if the system can't update an inventory quantity because there aren't enough inventory transactions that have the specified dimensions.</span></span> <span data-ttu-id="de7a7-114">Här är hela texten till hela felmeddelandet:</span><span class="sxs-lookup"><span data-stu-id="de7a7-114">Here is the full text of the full error message:</span></span>

> <span data-ttu-id="de7a7-115">Lagerkvantitet -%1 kunde inte uppdateras på grund av otillräckliga lagertransaktioner för artikeln %2 med dimensioner Storlek=%3, Färg=%4, Tillägg=%5, Webbplats=%6, Lagerställe=%7, Plats=%8, Lagerstatus=tillgänglig, ID-nummer=%9, Batchnummer=%10 för referens-ID %11 på parti-Lot ID %12.</span><span class="sxs-lookup"><span data-stu-id="de7a7-115">Inventory quantity -%1 could not be updated due to insufficient inventory transactions for item %2 with dimensions Size=%3, Color=%4, Additions=%5, Site=%6, Warehouse=%7, Location=%8, Inventory status=Available, License plate=%9, Batch number=%10 for reference ID %11 on Lot ID %12.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="de7a7-116">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="de7a7-116">Issue resolution</span></span>

<span data-ttu-id="de7a7-117">Se till att inga lagertransaktioner fysiskt reserverar kvantiteten.</span><span class="sxs-lookup"><span data-stu-id="de7a7-117">Make sure that no inventory transactions are physically reserving the quantity.</span></span> <span data-ttu-id="de7a7-118">Dessa transaktioner kan till exempel öppna kvalitetsorder, lagerspärrposter och utleveransorder.</span><span class="sxs-lookup"><span data-stu-id="de7a7-118">For example, these transactions might open quality orders, inventory blocking records, or output orders.</span></span>

## <a name="i-receive-the-following-error-message-physical-on-handcannot-be-reserved-because-only-000-are-available-in-the-inventory"></a><span data-ttu-id="de7a7-119">Jag får följande felmeddelande: "fysisk behållning... Det går inte att reservera eftersom bara 0,00 är tillgängligt i lagret".</span><span class="sxs-lookup"><span data-stu-id="de7a7-119">I receive the following error message: "Physical on-hand...cannot be reserved because only 0.00 are available in the inventory."</span></span>

### <a name="issue-description"></a><span data-ttu-id="de7a7-120">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="de7a7-120">Issue description</span></span>

<span data-ttu-id="de7a7-121">Det här problemet kan uppstå om systemet inte kan uppdatera en lagerkvantitet eftersom det inte finns tillräckligt många lagertransaktioner med de angivna dimensionerna.</span><span class="sxs-lookup"><span data-stu-id="de7a7-121">This issue can occur if the system can't update an inventory quantity because there aren't enough inventory transactions that have the specified dimensions.</span></span> <span data-ttu-id="de7a7-122">Här är hela texten till hela felmeddelandet:</span><span class="sxs-lookup"><span data-stu-id="de7a7-122">Here is the full text of the full error message:</span></span>

> <span data-ttu-id="de7a7-123">Fysisk behållning Webbplats=%1, Lagerställe=%2, Lagerstatus=tillgänglig, batchnummer=%3, Ägare=%4: %5 kan inte reserveras eftersom endast 0,00 är tillgängligt i lagret.</span><span class="sxs-lookup"><span data-stu-id="de7a7-123">Physical on-hand Site=%1, Warehouse=%2, Inventory status=Available, Batch number=%3, Owner=%4: %5 cannot be reserved because only 0.00 are available in the inventory.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="de7a7-124">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="de7a7-124">Issue resolution</span></span>

<span data-ttu-id="de7a7-125">Det här problemet orsakas troligen av öppet arbete.</span><span class="sxs-lookup"><span data-stu-id="de7a7-125">This issue is probably caused by open work.</span></span> <span data-ttu-id="de7a7-126">Antingen slutför du arbetet eller tar emot det utan att arbetet skapas.</span><span class="sxs-lookup"><span data-stu-id="de7a7-126">Either complete the work or receive without work creation.</span></span> <span data-ttu-id="de7a7-127">Se till att inga lagertransaktioner fysiskt reserverar kvantiteten.</span><span class="sxs-lookup"><span data-stu-id="de7a7-127">Make sure that no inventory transactions are physically reserving the quantity.</span></span> <span data-ttu-id="de7a7-128">Dessa transaktioner kan till exempel öppna kvalitetsorder, lagerspärrposter och utleveransorder.</span><span class="sxs-lookup"><span data-stu-id="de7a7-128">For example, these transactions might be open quality orders, inventory blocking records, or output orders.</span></span>

## <a name="i-receive-the-following-error-message-to-be-assigned-to-wave-load-lines-must-specify-the-dimensions-above-the-location-to-assign-these-dimensions-reserve-and-recreate-the-load-line"></a><span data-ttu-id="de7a7-129">Följande felmeddelande visas: "För att tilldelas en cykel måste lastlinjer ange dimensionerna ovanför platsen.</span><span class="sxs-lookup"><span data-stu-id="de7a7-129">I receive the following error message: "To be assigned to wave, load lines must specify the dimensions above the location.</span></span> <span data-ttu-id="de7a7-130">För att tilldela dessa dimensioner, reservera och återskapa lastraden".</span><span class="sxs-lookup"><span data-stu-id="de7a7-130">To assign these dimensions, reserve and recreate the load line."</span></span>

### <a name="issue-description"></a><span data-ttu-id="de7a7-131">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="de7a7-131">Issue description</span></span>

<span data-ttu-id="de7a7-132">När du använder ett objekt som har en "batch ovan" bokningshierarki (med dimensionen **Batchnummer** placerad *ovan* dimensionen **Plats**), kommandot **Släppa till distributionslager** på sidan **Workbench för lastplanering** för en delkvantitet fungerar inte.</span><span class="sxs-lookup"><span data-stu-id="de7a7-132">When you use an item that has a "batch above" reservation hierarchy (with the **Batch number** dimension placed *above* the **Location** dimension), the **Release to warehouse** command on the **Load planning workbench** page for a partial quantity doesn't work.</span></span> <span data-ttu-id="de7a7-133">Det här felmeddelandet visas och inget arbete skapas för delkvantiteten.</span><span class="sxs-lookup"><span data-stu-id="de7a7-133">You receive this error message, and no work is created for the partial quantity.</span></span>

<span data-ttu-id="de7a7-134">Men om du använder en artikel som har en "batch under" bokningshierarki (med **Batchnummer** placerad *under* dimensionen **Plats** dimension), kan du frisläppa en last från **Workbench för lastplanering** för en delkvantitet.</span><span class="sxs-lookup"><span data-stu-id="de7a7-134">However, if you use an item that has a "batch below" reservation hierarchy (with the **Batch number** dimension placed *below* the **Location** dimension), you can release a load from the **Load planning workbench** page for a partial quantity.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="de7a7-135">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="de7a7-135">Issue resolution</span></span>

<span data-ttu-id="de7a7-136">Detta beteende är av design.</span><span class="sxs-lookup"><span data-stu-id="de7a7-136">This behavior is by design.</span></span> <span data-ttu-id="de7a7-137">Om du placerar en dimension ovanför dimensionen **Plats** i reservationshierarkin måste den anges innan den kan frisläppas till lagerstället.</span><span class="sxs-lookup"><span data-stu-id="de7a7-137">If you put a dimension above the **Location** dimension in the reservation hierarchy, it must be specified before the release to the warehouse.</span></span> <span data-ttu-id="de7a7-138">Microsoft har utvärderat det här problemet och har fastställt att det är en begränsning av funktionen under versioner till lagret från workbench för lastplanering.</span><span class="sxs-lookup"><span data-stu-id="de7a7-138">Microsoft has evaluated this issue and has determined that it's a feature limitation during releases to the warehouse from the load planning workbench.</span></span> <span data-ttu-id="de7a7-139">Delkvantiteter kan inte frisläppas om en eller flera dimensioner ovanför **plats** inte har angetts.</span><span class="sxs-lookup"><span data-stu-id="de7a7-139">Partial quantities can't be released if one or more dimensions above **Location** aren't specified.</span></span>

<span data-ttu-id="de7a7-140">För mer information [Flexibel reservationspolicy för dimension på distributionslagernivå](flexible-warehouse-level-dimension-reservation.md).</span><span class="sxs-lookup"><span data-stu-id="de7a7-140">For more information, see [Flexible warehouse-level dimension reservation policy](flexible-warehouse-level-dimension-reservation.md).</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]