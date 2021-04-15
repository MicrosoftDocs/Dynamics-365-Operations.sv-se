---
title: Lagertillgänglighet vid dubbelriktad skrivning
description: I det här avsnittet finns information om kontroll av lagertillgänglighet vid dubbelriktad skrivning.
author: yijialuan
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: riluan
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-05-26
ms.openlocfilehash: 9d9b7970720218fbcf2f512345ade672810440b4
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5748575"
---
# <a name="inventory-availability-in-dual-write"></a><span data-ttu-id="34f2c-103">Lagertillgänglighet vid dubbelriktad skrivning</span><span class="sxs-lookup"><span data-stu-id="34f2c-103">Inventory availability in dual-write</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="34f2c-104">Genom lagertillgänglighet kan du kontrollera lagret innan du lägger till en produkt sida **Offerter**, **Order** eller **Fakturor** i Microsoft Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="34f2c-104">By using inventory availability, you can check your inventory before you add a product to the **Quotations**, **Orders**, or **Invoices** page in Microsoft Dynamics 365 Sales.</span></span> <span data-ttu-id="34f2c-105">Till exempel är kontroll av lager och bestämning av ett uppfyllelsedatum är en viktig uppgift i processen [potentiell kund till pengar](dual-write-prospect-to-cash.md).</span><span class="sxs-lookup"><span data-stu-id="34f2c-105">For example, you check inventory and determine a fulfillment date as one key task in the [prospect-to-cash](dual-write-prospect-to-cash.md) process.</span></span>

<span data-ttu-id="34f2c-106">Om du inte har tillräckligt med lager kan du uppskatta ett leveransdatum med utgångspunkt i projekterade lagerinleveranser och utleveranser.</span><span class="sxs-lookup"><span data-stu-id="34f2c-106">If you don't have enough inventory, you can estimate a delivery date, based on projected inventory receipts and issues.</span></span> <span data-ttu-id="34f2c-107">Du kan också kontrollera produktens tillgängliga ATP-information, där du kan hitta kvantiteten för tillgängligt att lova i den fördefinierade tidsgränsen.</span><span class="sxs-lookup"><span data-stu-id="34f2c-107">You can also check the product's available-to-promise (ATP) information, where you can find the ATP quantity in the predefined time fence.</span></span>

## <a name="on-hand-inventory"></a><span data-ttu-id="34f2c-108">Lagerbehållning</span><span class="sxs-lookup"><span data-stu-id="34f2c-108">On-hand inventory</span></span>

<span data-ttu-id="34f2c-109">I Dynamics 365 Sales, en ny knapp **Lagerbehållning** har lagts till i rubriken på sidorna **Offerter**, **Order** och **Fakturor**.</span><span class="sxs-lookup"><span data-stu-id="34f2c-109">In Dynamics 365 Sales, a new **On-hand Inventory** button has been added to the header of the **Quotes**, **Orders**, and **Invoices** pages.</span></span> <span data-ttu-id="34f2c-110">När du klickar på knappen visas en dialogruta där du kan ange företaget och produkten som du vill kontrollera lagerbehållningen för.</span><span class="sxs-lookup"><span data-stu-id="34f2c-110">When you select this button, a dialog box appears, where you can specify the company and the product that you want to check the on-hand inventory for.</span></span> <span data-ttu-id="34f2c-111">I den här dialogrutan visas samma information som [lagerbehållning](../../../../supply-chain/inventory/tasks/check-availability-stock.md).</span><span class="sxs-lookup"><span data-stu-id="34f2c-111">This dialog box shows the same information as [On-hand inventory](../../../../supply-chain/inventory/tasks/check-availability-stock.md).</span></span>

<span data-ttu-id="34f2c-112">Dialogrutan returnerar lagerinformationen från Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="34f2c-112">The dialog box returns the inventory information from Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="34f2c-113">I den här information beskrivs följande kvantiteter:</span><span class="sxs-lookup"><span data-stu-id="34f2c-113">This information includes the following quantities:</span></span>

- <span data-ttu-id="34f2c-114">Lagerbehållning</span><span class="sxs-lookup"><span data-stu-id="34f2c-114">On-hand quantity</span></span>
- <span data-ttu-id="34f2c-115">Reserverad lagerbehållning</span><span class="sxs-lookup"><span data-stu-id="34f2c-115">Reserved on-hand quantity</span></span>
- <span data-ttu-id="34f2c-116">Tillgänglig lagerbehållning</span><span class="sxs-lookup"><span data-stu-id="34f2c-116">Available on-hand quantity</span></span>
- <span data-ttu-id="34f2c-117">Beställd kvantitet</span><span class="sxs-lookup"><span data-stu-id="34f2c-117">Ordered quantity</span></span>
- <span data-ttu-id="34f2c-118">Kvantitet som har beställts</span><span class="sxs-lookup"><span data-stu-id="34f2c-118">On-order quantity</span></span>
- <span data-ttu-id="34f2c-119">Reserverad beställd kvantitet</span><span class="sxs-lookup"><span data-stu-id="34f2c-119">Reserved ordered quantity</span></span>
- <span data-ttu-id="34f2c-120">Total tillgänglig kvantitet</span><span class="sxs-lookup"><span data-stu-id="34f2c-120">Total available quantity</span></span>

## <a name="atp-information"></a><span data-ttu-id="34f2c-121">Information om ATP</span><span class="sxs-lookup"><span data-stu-id="34f2c-121">ATP information</span></span>

<span data-ttu-id="34f2c-122">Vid försäljning har en ny knapp **ATP-information** har lagts till i radartikal på sidor **offerter**, **order** och **fakturor**.</span><span class="sxs-lookup"><span data-stu-id="34f2c-122">In Sales, a new **ATP Information** button has been added to line items on the **Quotes**, **Orders**, and **Invoices** pages.</span></span> <span data-ttu-id="34f2c-123">När du klickar på knappen visas en dialogruta där du kan ange företaget, produkten, lagerplats, lagerställe och orderkvantitet.</span><span class="sxs-lookup"><span data-stu-id="34f2c-123">When you select this button, a dialog box appears, where you can specify the company, product, inventory site, inventory warehouse, and order quantity.</span></span> <span data-ttu-id="34f2c-124">Den här dialogrutan har samma inställningar som beskrivs i [Orderlöfte](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations).</span><span class="sxs-lookup"><span data-stu-id="34f2c-124">This dialog box has the same settings that are described in [Order promising](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations).</span></span>

<span data-ttu-id="34f2c-125">Dialogrutan returnerar ATP-information från Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="34f2c-125">The dialog box returns the ATP information from Supply Chain Management.</span></span> <span data-ttu-id="34f2c-126">I den här information beskrivs följande kvantiteter:</span><span class="sxs-lookup"><span data-stu-id="34f2c-126">This information includes the following quantities:</span></span>

- <span data-ttu-id="34f2c-127">Kvantitet för ATP</span><span class="sxs-lookup"><span data-stu-id="34f2c-127">ATP quantity</span></span>
- <span data-ttu-id="34f2c-128">Inleveranskvantitet</span><span class="sxs-lookup"><span data-stu-id="34f2c-128">Receipt quantity</span></span>
- <span data-ttu-id="34f2c-129">Utleveranskvantitet</span><span class="sxs-lookup"><span data-stu-id="34f2c-129">Issue quantity</span></span>
- <span data-ttu-id="34f2c-130">Lagerbehållning</span><span class="sxs-lookup"><span data-stu-id="34f2c-130">On-hand quantity</span></span>

## <a name="how-it-works"></a><span data-ttu-id="34f2c-131">Hur det fungerar</span><span class="sxs-lookup"><span data-stu-id="34f2c-131">How it works</span></span>

<span data-ttu-id="34f2c-132">När du väljer knappen **Lagerbehållning** på sidan **Offerter**, **Order** eller **Fakturor** görs ett liveanrop med dubbel avskrivning till API för **Lagerbehållning**.</span><span class="sxs-lookup"><span data-stu-id="34f2c-132">When you select the **On-hand Inventory** button on the **Quotes**, **Orders**, or **Invoices** page, a live dual-write call is made to the **Onhand inventory** API.</span></span> <span data-ttu-id="34f2c-133">API:t beräknar lagerbehållningen för den angivna produkten.</span><span class="sxs-lookup"><span data-stu-id="34f2c-133">The API calculates the on-hand inventory for the given product.</span></span> <span data-ttu-id="34f2c-134">Resultatet lagras i tabellerna **InventCDSInventoryOnHandRequestEntity** och **InventCDSInventoryOnHandEntryEntity** och skrivs sedan till Dataverse via dubbelriktad skrivning.</span><span class="sxs-lookup"><span data-stu-id="34f2c-134">The result is stored in the **InventCDSInventoryOnHandRequestEntity** and **InventCDSInventoryOnHandEntryEntity** tables, and then is written to Dataverse by dual-write.</span></span> <span data-ttu-id="34f2c-135">Om du vill använda den här funktionen måste du köra följande mappningar:</span><span class="sxs-lookup"><span data-stu-id="34f2c-135">To use this functionality, you need to run the following dual-write maps.</span></span> <span data-ttu-id="34f2c-136">Hoppa över ursprunglig synkronisering när du kör kartorna.</span><span class="sxs-lookup"><span data-stu-id="34f2c-136">Skip initial synchronization when you run the maps.</span></span>

- <span data-ttu-id="34f2c-137">CDS-lagerbehållningsposter (msdyn_inventoryonhandentries)</span><span class="sxs-lookup"><span data-stu-id="34f2c-137">CDS inventory on-hand entries (msdyn_inventoryonhandentries)</span></span>
- <span data-ttu-id="34f2c-138">CDS-lagerbehållningsbegäranden (msdyn_inventoryonhandrequests)</span><span class="sxs-lookup"><span data-stu-id="34f2c-138">CDS inventory on-hand requests (msdyn_inventoryonhandrequests)</span></span>

## <a name="templates"></a><span data-ttu-id="34f2c-139">Mallar</span><span class="sxs-lookup"><span data-stu-id="34f2c-139">Templates</span></span>
<span data-ttu-id="34f2c-140">Följande mallar är tillgängliga för utsätter lagerdata.</span><span class="sxs-lookup"><span data-stu-id="34f2c-140">The following templates are available for the exposing the onhand inventory data.</span></span>

<span data-ttu-id="34f2c-141">Finance and Operations-appar</span><span class="sxs-lookup"><span data-stu-id="34f2c-141">Finance and Operations apps</span></span> | <span data-ttu-id="34f2c-142">Kundengagemangsapp</span><span class="sxs-lookup"><span data-stu-id="34f2c-142">Customer engagement app</span></span> | <span data-ttu-id="34f2c-143">beskrivning</span><span class="sxs-lookup"><span data-stu-id="34f2c-143">Description</span></span> 
---|---|---
[<span data-ttu-id="34f2c-144">CDS-lagerbehållningsposter</span><span class="sxs-lookup"><span data-stu-id="34f2c-144">CDS inventory on-hand entries</span></span>](#145) | <span data-ttu-id="34f2c-145">msdyn_inventoryonhandentries</span><span class="sxs-lookup"><span data-stu-id="34f2c-145">msdyn_inventoryonhandentries</span></span> |
[<span data-ttu-id="34f2c-146">CDS-lagerbehållningsbegäranden</span><span class="sxs-lookup"><span data-stu-id="34f2c-146">CDS inventory on-hand requests</span></span>](#147) | <span data-ttu-id="34f2c-147">msdyn_inventoryonhandrequests</span><span class="sxs-lookup"><span data-stu-id="34f2c-147">msdyn_inventoryonhandrequests</span></span> |

[!include [banner](../../includes/dual-write-symbols.md)]

###  <a name="cds-inventory-on-hand-entries-msdyn_inventoryonhandentries"></a><a name="145"></a><span data-ttu-id="34f2c-148">CDS-lagerbehållningsposter (msdyn_inventoryonhandentries)</span><span class="sxs-lookup"><span data-stu-id="34f2c-148">CDS inventory on-hand entries (msdyn_inventoryonhandentries)</span></span>

<span data-ttu-id="34f2c-149">Den här mallen synkroniserar data mellan Finance and Operations-appar och Dataverse.</span><span class="sxs-lookup"><span data-stu-id="34f2c-149">This template synchronizes data between Finance and Operations apps and Dataverse.</span></span>

<span data-ttu-id="34f2c-150">Finance and Operations-fält</span><span class="sxs-lookup"><span data-stu-id="34f2c-150">Finance and Operations field</span></span> | <span data-ttu-id="34f2c-151">Mappningstyp</span><span class="sxs-lookup"><span data-stu-id="34f2c-151">Map type</span></span> | <span data-ttu-id="34f2c-152">Customer Engagement-fält</span><span class="sxs-lookup"><span data-stu-id="34f2c-152">Customer engagement field</span></span> | <span data-ttu-id="34f2c-153">Standardvärde</span><span class="sxs-lookup"><span data-stu-id="34f2c-153">Default value</span></span>
---|---|---|---
`REQUESTID` | = | `msdyn_request.msdyn_requestid` |
`INVENTORYSITEID` | = | `msdyn_inventorysite.msdyn_siteid` |
`INVENTORYWAREHOUSEID` | = | `msdyn_inventorywarehouse.msdyn_warehouseidentifier` |
`AVAILABLEONHANDQUANTITY` | > | `msdyn_availableonhandquantity` |
`AVAILABLEORDEREDQUANTITY` | > | `msdyn_availableorderedquantity` |
`ONHANDQUANTITY` | > | `msdyn_onhandquantity` |
`ONORDERQUANTITY` | > | `msdyn_onorderquantity` |
`ORDEREDQUANTITY` | > | `msdyn_orderedquantity` |
`RESERVEDONHANDQUANTITY` | > | `msdyn_reservedonhandquantity` |
`RESERVEDORDEREDQUANTITY` | > | `msdyn_reservedorderedquantity` |
`TOTALAVAILABLEQUANTITY` | > | `msdyn_totalavailablequantity` |
`ATPDATE` | = | `msdyn_atpdate` |
`ATPQUANTITY` | > | `msdyn_atpquantity` |
`PROJECTEDISSUEQUANTITY` | > | `msdyn_projectedissuequantity` |
`PROJECTEDONHANDQUANTITY` | > | `msdyn_projectedonhandquantity` |
`PROJECTEDRECEIPTQUANTITY` | > | `msdyn_projectedreceiptquantity` |
`ORDERQUANTITY` | > | `msdyn_orderquantity` |
`UNAVAILABLEONHANDQUANTITY` | > | `msdyn_unavailableonhandquantity` |

###  <a name="cds-inventory-on-hand-requests-msdyn_inventoryonhandrequests"></a><a name="147"></a><span data-ttu-id="34f2c-154">CDS-lagerbehållningsbegäranden (msdyn_inventoryonhandrequests)</span><span class="sxs-lookup"><span data-stu-id="34f2c-154">CDS inventory on-hand requests (msdyn_inventoryonhandrequests)</span></span>

<span data-ttu-id="34f2c-155">Den här mallen synkroniserar data mellan Finance and Operations-appar och Dataverse.</span><span class="sxs-lookup"><span data-stu-id="34f2c-155">This template synchronizes data between Finance and Operations apps and Dataverse.</span></span>

<span data-ttu-id="34f2c-156">Finance and Operations-fält</span><span class="sxs-lookup"><span data-stu-id="34f2c-156">Finance and Operations field</span></span> | <span data-ttu-id="34f2c-157">Mappningstyp</span><span class="sxs-lookup"><span data-stu-id="34f2c-157">Map type</span></span> | <span data-ttu-id="34f2c-158">Customer Engagement-fält</span><span class="sxs-lookup"><span data-stu-id="34f2c-158">Customer engagement field</span></span> | <span data-ttu-id="34f2c-159">Standardvärde</span><span class="sxs-lookup"><span data-stu-id="34f2c-159">Default value</span></span>
---|---|---|---
`REQUESTID` | = | `msdyn_requestid` |
`PRODUCTNUMBER` | < | `msdyn_product.msdyn_productnumber` |
`ISATPCALCULATION` | << | `msdyn_isatpcalculation` |
`ORDERQUANTITY` | < | `msdyn_orderquantity` |
`INVENTORYSITEID` | < | `msdyn_inventorysite.msdyn_siteid` |
`INVENTORYWAREHOUSEID` | < | `msdyn_inventorywarehouse.msdyn_warehouseidentifier` |
`REFERENCENUMBER` | < | `msdyn_referencenumber` |
`LINECREATIONSEQUENCENUMBER` | < | `msdyn_linecreationsequencenumber` |






[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]