---
title: Spåra löpande genomsnittlig kostnad per lagerdimension
description: En lagerdimensionsgrupp kopplas till varje lagerartikel. Därför beräknas den löpande genomsnittliga självkostnaden för en artikel utifrån valet av lagerdimensioner som spåras ekonomiskt.
author: AndersGirke
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventOnhandItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 75053
ms.assetid: 68cc00f4-0f7a-4a7d-be90-8f2e0d0563d3
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b2bf04a42edf09c35e81742b1c60db8944eba2ac
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5252880"
---
# <a name="track-running-average-cost-per-inventory-dimension"></a><span data-ttu-id="7e936-104">Spåra löpande genomsnittlig kostnad per lagerdimension</span><span class="sxs-lookup"><span data-stu-id="7e936-104">Track running average cost per inventory dimension</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7e936-105">En lagerdimensionsgrupp kopplas till varje lagerartikel.</span><span class="sxs-lookup"><span data-stu-id="7e936-105">An inventory dimension group is attached to every inventory item.</span></span> <span data-ttu-id="7e936-106">Därför beräknas den löpande genomsnittliga självkostnaden för en artikel utifrån valet av lagerdimensioner som spåras ekonomiskt.</span><span class="sxs-lookup"><span data-stu-id="7e936-106">Therefore, the running average cost price of an item is calculated based on the selected inventory dimensions that are being tracked financially.</span></span>

<span data-ttu-id="7e936-107">Det finns tre typer av lagerdimensioner: produkt, lagring och spårning.</span><span class="sxs-lookup"><span data-stu-id="7e936-107">There are three types of inventory dimensions: product, storage, and tracking.</span></span> <span data-ttu-id="7e936-108">Produktdimensioner omfattar konfiguration, storlek och färg.</span><span class="sxs-lookup"><span data-stu-id="7e936-108">Product dimensions include configuration, size, and color.</span></span> <span data-ttu-id="7e936-109">Produktdimensioner spåras alltid ekonomiskt.</span><span class="sxs-lookup"><span data-stu-id="7e936-109">Product dimensions are always tracked financially.</span></span> <span data-ttu-id="7e936-110">Lagrings- och spårningsdimensioner omfattar site, lagerställe, placering, lagerstatus, batchnummer och serienummer.</span><span class="sxs-lookup"><span data-stu-id="7e936-110">Storage and tracking dimensions include site, warehouse, location, inventory status, license plate, batch number, and serial number.</span></span> <span data-ttu-id="7e936-111">Du kan bestämma vilka lagrings- och spårningsdimensioner som spåras ekonomiskt.</span><span class="sxs-lookup"><span data-stu-id="7e936-111">You can decide which storage and tracking dimensions are tracked financially.</span></span> 

<span data-ttu-id="7e936-112">**Exempel 1**</span><span class="sxs-lookup"><span data-stu-id="7e936-112">**Example 1**</span></span> 

<span data-ttu-id="7e936-113">Om lagerdimensionsgruppen som kopplas till artikeln spåras automatiskt av lagerstället, beräknas den löpande genomsnittliga självkostnaden för respektive lagerställe.</span><span class="sxs-lookup"><span data-stu-id="7e936-113">If the storage dimension group that is attached to the item is financially tracked by warehouse, the running average cost price is calculated per warehouse.</span></span> <span data-ttu-id="7e936-114">Följande inköpsorder har fakturerats:</span><span class="sxs-lookup"><span data-stu-id="7e936-114">The following purchase orders have been invoiced:</span></span>

-   <span data-ttu-id="7e936-115">En inköpsorder för kvantiteten 2 med en självkostnad på 100,00 kronor har fakturerats för lagerstället GW.</span><span class="sxs-lookup"><span data-stu-id="7e936-115">A purchase order for a quantity of 2 at a cost price of USD 10.00 has been invoiced for warehouse GW.</span></span>
-   <span data-ttu-id="7e936-116">En inköpsorder för kvantiteten 3 med en självkostnad på 120,00 kronor har fakturerats för lagerstället GW.</span><span class="sxs-lookup"><span data-stu-id="7e936-116">A purchase order for a quantity of 3 at a cost price of USD 12.00 has been invoiced for warehouse GW.</span></span>
-   <span data-ttu-id="7e936-117">En inköpsorder för kvantiteten 5 med en självkostnad på 150,00 kronor har fakturerats för lagerstället MW.</span><span class="sxs-lookup"><span data-stu-id="7e936-117">A purchase order for a quantity of 5 at a cost price of USD 15.00 has been invoiced for warehouse MW.</span></span>

<span data-ttu-id="7e936-118">Den löpande genomsnittliga självkostnaden för lagerställe GW är 112,00 kronor, och den löpande genomsnittliga självkostnaden för lagerställe MW är 150,00 kronor.</span><span class="sxs-lookup"><span data-stu-id="7e936-118">The running average cost price for warehouse GW is USD 11.20, and the running average cost price for warehouse MW is USD 15.00.</span></span> <span data-ttu-id="7e936-119">En försäljningsorder bokförs för lagerställe GW.</span><span class="sxs-lookup"><span data-stu-id="7e936-119">A sales order invoice is posted for warehouse GW.</span></span> <span data-ttu-id="7e936-120">Värdet på lagret och kostnader för sålda varor (före lagerstängningen och utan markering) är 112,00 kronor.</span><span class="sxs-lookup"><span data-stu-id="7e936-120">The value of the inventory and the cost of goods sold (before inventory close is run and without marking) is USD 11.20.</span></span> <span data-ttu-id="7e936-121">En annan försäljningsorder bokförs för lagerställe MW.</span><span class="sxs-lookup"><span data-stu-id="7e936-121">Another sales order is posted for warehouse MW.</span></span> <span data-ttu-id="7e936-122">Värdet på lagret och kostnader för sålda varor (före lagerstängningen och utan markering) är 150,00 kronor.</span><span class="sxs-lookup"><span data-stu-id="7e936-122">The value of the inventory and the cost of goods sold (before inventory close is run and without marking) is USD 15.00.</span></span> 

<span data-ttu-id="7e936-123">**Exempel 2** Om lagringsdimensiongruppen, som är kopplad till artikeln spåras ekonomiskt av lager och spårningsdimensiongruppen spåras ekonomiskt av batchnummer, beräknas den löpande genomsnittliga självkostnaden för respektive batch.</span><span class="sxs-lookup"><span data-stu-id="7e936-123">**Example 2** If the storage dimension group that is attached to the item is financially tracked by warehouse, and the tracking dimension group is financially tracked by batch number, the running average cost price is calculated for each batch.</span></span> 

<span data-ttu-id="7e936-124">**Obs!** Vi rekommenderar att du alltid visar självkostnaden med alla ekonomiska dimensioner spårade.</span><span class="sxs-lookup"><span data-stu-id="7e936-124">**Note:** We recommend that you always view the cost price for all financial dimensions that are being tracked.</span></span> <span data-ttu-id="7e936-125">Följande inköpsorder har fakturerats:</span><span class="sxs-lookup"><span data-stu-id="7e936-125">The following purchase orders have been invoiced:</span></span>

-   <span data-ttu-id="7e936-126">En inköpsorder för kvantiteten 2 med en självkostnad på 100,00 kronor har fakturerats för lagerstället GW och batch AAA.</span><span class="sxs-lookup"><span data-stu-id="7e936-126">A purchase order for a quantity of 2 at a cost price of USD 10.00 has been invoiced for warehouse GW and batch AAA.</span></span>
-   <span data-ttu-id="7e936-127">En inköpsorder för kvantiteten 3 med en självkostnad på 120,00 kronor har fakturerats för lagerstället GW och batch AAA.</span><span class="sxs-lookup"><span data-stu-id="7e936-127">A purchase order for a quantity of 3 at a cost price of USD 12.00 has been invoiced for warehouse GW and batch AAA.</span></span>
-   <span data-ttu-id="7e936-128">En inköpsorder för kvantiteten 2 med en självkostnad på 150,00 kronor har fakturerats för lagerstället GW och batch BBB.</span><span class="sxs-lookup"><span data-stu-id="7e936-128">A purchase order for a quantity of 2 at a cost price of USD 15.00 has been invoiced for warehouse GW and batch BBB.</span></span>

<span data-ttu-id="7e936-129">Den löpande genomsnittliga självkostnaden för lagerställe GW och batch AAA är 112,00 kronor, och den löpande genomsnittliga självkostnaden för lagerställe GW och batch BBB är 150,00 kronor.</span><span class="sxs-lookup"><span data-stu-id="7e936-129">The running average cost price for warehouse GW and batch AAA is USD 11.20, and the running average cost price for warehouse GW and batch BBB is USD 15.00.</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]