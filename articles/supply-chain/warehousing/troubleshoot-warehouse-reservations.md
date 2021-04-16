---
title: Felsöka reservationer i distributionslagerhantering
description: I det här avsnittet beskrivs hur du åtgärdar vanliga problem som kan uppstå när du arbetar med lagerreservationer i Microsoft Dynamics 365 Supply Chain Management.
author: perlynne
ms.date: 10/19/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: d0d73396772ed9e8397797d6685fb550d911303b
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828116"
---
# <a name="troubleshoot-reservations-in-warehouse-management"></a><span data-ttu-id="1134e-103">Felsöka reservationer i distributionslagerhantering</span><span class="sxs-lookup"><span data-stu-id="1134e-103">Troubleshoot reservations in warehouse management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1134e-104">I det här avsnittet beskrivs hur du åtgärdar vanliga problem som kan uppstå när du arbetar med lagerreservationer i Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="1134e-104">This topic describes how to fix common issues that you might encounter while you work with warehouse reservations in Microsoft Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="1134e-105">Avsnitt som är relaterade till batch- och serienummerregistreringar finns i [Felsöka batch- och seriereservationhierarkier för lagerställen](troubleshoot-warehouse-batch-and-serial-reservation-hierarchies.md).</span><span class="sxs-lookup"><span data-stu-id="1134e-105">For topics that are related to batch and serial number registrations, see [Troubleshoot warehouse batch and serial reservation hierarchies](troubleshoot-warehouse-batch-and-serial-reservation-hierarchies.md).</span></span>

## <a name="i-receive-the-following-error-message-reservations-cannot-be-removed-because-there-is-work-created-which-relies-on-the-reservations"></a><span data-ttu-id="1134e-106">Jag får följande felmeddelande: "reservationer kan inte tas bort eftersom det finns ett arbete skapat som använder reservationerna".</span><span class="sxs-lookup"><span data-stu-id="1134e-106">I receive the following error message: "Reservations cannot be removed because there is work created which relies on the reservations."</span></span>

### <a name="issue-description"></a><span data-ttu-id="1134e-107">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="1134e-107">Issue description</span></span>

<span data-ttu-id="1134e-108">Du kan inte icke-reserverade på en försäljningsrad, eftersom det är öppet arbete på raden.</span><span class="sxs-lookup"><span data-stu-id="1134e-108">You can't unreserve inventory on a sales line, because there is open work against the line.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="1134e-109">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="1134e-109">Issue resolution</span></span>

<span data-ttu-id="1134e-110">Undersök om öppna förpackningsgrupparbete finns för att hämta artikeln från en förpackningsstation till en annan plats (t.ex. *Baydoor*).</span><span class="sxs-lookup"><span data-stu-id="1134e-110">Investigate whether open packing group work exists to bring the item from a packing station to another location (such as *Baydoor*).</span></span> <span data-ttu-id="1134e-111">Granska posterna på sidorna för **Loggen över arbetsskapande** och **Arbetsinformation** för att avgöra vad som fysiskt reserverar inventeringen och sedan slutföra eller ta bort arbetet för att frigöra reservationen.</span><span class="sxs-lookup"><span data-stu-id="1134e-111">Review the records on the **Work creation history log** and **Work details** pages to determine what is physically reserving the inventory, and then complete or delete the work to free up the reservation.</span></span>

## <a name="i-receive-the-following-error-message-inventory-quantity--1-could-not-be-updated-due-to-insufficient-inventory-transactions-for-item-2"></a><span data-ttu-id="1134e-112">Följande felmeddelande visas: "lagerkvantitet -%1 kunde inte uppdateras på grund av otillräckliga lagertransaktioner för artikel %2...".</span><span class="sxs-lookup"><span data-stu-id="1134e-112">I receive the following error message: "Inventory quantity -%1 could not be updated due to insufficient inventory transactions for item %2...."</span></span>

### <a name="issue-description"></a><span data-ttu-id="1134e-113">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="1134e-113">Issue description</span></span>

<span data-ttu-id="1134e-114">Det här problemet kan uppstå om systemet inte kan uppdatera en lagerkvantitet eftersom det inte finns tillräckligt många lagertransaktioner med de angivna dimensionerna.</span><span class="sxs-lookup"><span data-stu-id="1134e-114">This issue can occur if the system can't update an inventory quantity because there aren't enough inventory transactions that have the specified dimensions.</span></span> <span data-ttu-id="1134e-115">Här är hela texten till hela felmeddelandet:</span><span class="sxs-lookup"><span data-stu-id="1134e-115">Here is the full text of the full error message:</span></span>

> <span data-ttu-id="1134e-116">Lagerkvantitet -%1 kunde inte uppdateras på grund av otillräckliga lagertransaktioner för artikeln %2 med dimensioner Storlek=%3, Färg=%4, Tillägg=%5, Webbplats=%6, Lagerställe=%7, Plats=%8, Lagerstatus=tillgänglig, ID-nummer=%9, Batchnummer=%10 för referens-ID %11 på parti-Lot ID %12.</span><span class="sxs-lookup"><span data-stu-id="1134e-116">Inventory quantity -%1 could not be updated due to insufficient inventory transactions for item %2 with dimensions Size=%3, Color=%4, Additions=%5, Site=%6, Warehouse=%7, Location=%8, Inventory status=Available, License plate=%9, Batch number=%10 for reference ID %11 on Lot ID %12.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="1134e-117">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="1134e-117">Issue resolution</span></span>

<span data-ttu-id="1134e-118">Se till att inga lagertransaktioner fysiskt reserverar kvantiteten.</span><span class="sxs-lookup"><span data-stu-id="1134e-118">Make sure that no inventory transactions are physically reserving the quantity.</span></span> <span data-ttu-id="1134e-119">Dessa transaktioner kan till exempel öppna kvalitetsorder, lagerspärrposter och utleveransorder.</span><span class="sxs-lookup"><span data-stu-id="1134e-119">For example, these transactions might open quality orders, inventory blocking records, or output orders.</span></span>

## <a name="i-receive-the-following-error-message-physical-on-handcannot-be-reserved-because-only-000-are-available-in-the-inventory"></a><span data-ttu-id="1134e-120">Jag får följande felmeddelande: "fysisk behållning... Det går inte att reservera eftersom bara 0,00 är tillgängligt i lagret".</span><span class="sxs-lookup"><span data-stu-id="1134e-120">I receive the following error message: "Physical on-hand...cannot be reserved because only 0.00 are available in the inventory."</span></span>

### <a name="issue-description"></a><span data-ttu-id="1134e-121">Problembeskrivning</span><span class="sxs-lookup"><span data-stu-id="1134e-121">Issue description</span></span>

<span data-ttu-id="1134e-122">Det här problemet kan uppstå om systemet inte kan uppdatera en lagerkvantitet eftersom det inte finns tillräckligt många lagertransaktioner med de angivna dimensionerna.</span><span class="sxs-lookup"><span data-stu-id="1134e-122">This issue can occur if the system can't update an inventory quantity because there aren't enough inventory transactions that have the specified dimensions.</span></span> <span data-ttu-id="1134e-123">Här är hela texten till hela felmeddelandet:</span><span class="sxs-lookup"><span data-stu-id="1134e-123">Here is the full text of the full error message:</span></span>

> <span data-ttu-id="1134e-124">Fysisk behållning Webbplats=%1, Lagerställe=%2, Lagerstatus=tillgänglig, batchnummer=%3, Ägare=%4: %5 kan inte reserveras eftersom endast 0,00 är tillgängligt i lagret.</span><span class="sxs-lookup"><span data-stu-id="1134e-124">Physical on-hand Site=%1, Warehouse=%2, Inventory status=Available, Batch number=%3, Owner=%4: %5 cannot be reserved because only 0.00 are available in the inventory.</span></span>

### <a name="issue-resolution"></a><span data-ttu-id="1134e-125">Problemlösning</span><span class="sxs-lookup"><span data-stu-id="1134e-125">Issue resolution</span></span>

<span data-ttu-id="1134e-126">Det här problemet orsakas troligen av öppet arbete.</span><span class="sxs-lookup"><span data-stu-id="1134e-126">This issue is probably caused by open work.</span></span> <span data-ttu-id="1134e-127">Antingen slutför du arbetet eller tar emot det utan att arbetet skapas.</span><span class="sxs-lookup"><span data-stu-id="1134e-127">Either complete the work or receive without work creation.</span></span> <span data-ttu-id="1134e-128">Se till att inga lagertransaktioner fysiskt reserverar kvantiteten.</span><span class="sxs-lookup"><span data-stu-id="1134e-128">Make sure that no inventory transactions are physically reserving the quantity.</span></span> <span data-ttu-id="1134e-129">Dessa transaktioner kan till exempel öppna kvalitetsorder, lagerspärrposter och utleveransorder.</span><span class="sxs-lookup"><span data-stu-id="1134e-129">For example, these transactions might be open quality orders, inventory blocking records, or output orders.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
