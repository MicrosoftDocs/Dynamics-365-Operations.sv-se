---
title: Lagertillgänglighet vid dubbelriktad skrivning
description: I det här avsnittet finns information om kontroll av lagertillgänglighet vid dubbelriktad skrivning.
author: yijialuan
manager: AnnBe
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
ms.openlocfilehash: 48e54c043967ea5db15938857bd8f020dd4dfc64
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5566749"
---
# <a name="inventory-availability-in-dual-write"></a><span data-ttu-id="aad71-103">Lagertillgänglighet vid dubbelriktad skrivning</span><span class="sxs-lookup"><span data-stu-id="aad71-103">Inventory availability in dual-write</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="aad71-104">Genom lagertillgänglighet kan du kontrollera lagret innan du lägger till en produkt sida **Offerter**, **Order** eller **Fakturor** i Microsoft Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="aad71-104">By using inventory availability, you can check your inventory before you add a product to the **Quotations**, **Orders**, or **Invoices** page in Microsoft Dynamics 365 Sales.</span></span> <span data-ttu-id="aad71-105">Till exempel är kontroll av lager och bestämning av ett uppfyllelsedatum är en viktig uppgift i processen [potentiell kund till pengar](dual-write-prospect-to-cash.md).</span><span class="sxs-lookup"><span data-stu-id="aad71-105">For example, you check inventory and determine a fulfillment date as one key task in the [prospect-to-cash](dual-write-prospect-to-cash.md) process.</span></span>

<span data-ttu-id="aad71-106">Om du inte har tillräckligt med lager kan du uppskatta ett leveransdatum med utgångspunkt i projekterade lagerinleveranser och utleveranser.</span><span class="sxs-lookup"><span data-stu-id="aad71-106">If you don't have enough inventory, you can estimate a delivery date, based on projected inventory receipts and issues.</span></span> <span data-ttu-id="aad71-107">Du kan också kontrollera produktens tillgängliga ATP-information, där du kan hitta kvantiteten för tillgängligt att lova i den fördefinierade tidsgränsen.</span><span class="sxs-lookup"><span data-stu-id="aad71-107">You can also check the product's available-to-promise (ATP) information, where you can find the ATP quantity in the predefined time fence.</span></span>

## <a name="on-hand-inventory"></a><span data-ttu-id="aad71-108">Lagerbehållning</span><span class="sxs-lookup"><span data-stu-id="aad71-108">On-hand inventory</span></span>

<span data-ttu-id="aad71-109">I Dynamics 365 Sales, en ny knapp **Lagerbehållning** har lagts till i rubriken på sidorna **Offerter**, **Order** och **Fakturor**.</span><span class="sxs-lookup"><span data-stu-id="aad71-109">In Dynamics 365 Sales, a new **On-hand Inventory** button has been added to the header of the **Quotes**, **Orders**, and **Invoices** pages.</span></span> <span data-ttu-id="aad71-110">När du klickar på knappen visas en dialogruta där du kan ange företaget och produkten som du vill kontrollera lagerbehållningen för.</span><span class="sxs-lookup"><span data-stu-id="aad71-110">When you select this button, a dialog box appears, where you can specify the company and the product that you want to check the on-hand inventory for.</span></span> <span data-ttu-id="aad71-111">I den här dialogrutan visas samma information som [lagerbehållning](../../../../supply-chain/inventory/tasks/check-availability-stock.md).</span><span class="sxs-lookup"><span data-stu-id="aad71-111">This dialog box shows the same information as [On-hand inventory](../../../../supply-chain/inventory/tasks/check-availability-stock.md).</span></span>

<span data-ttu-id="aad71-112">Dialogrutan returnerar lagerinformationen från Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="aad71-112">The dialog box returns the inventory information from Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="aad71-113">I den här information beskrivs följande kvantiteter:</span><span class="sxs-lookup"><span data-stu-id="aad71-113">This information includes the following quantities:</span></span>

- <span data-ttu-id="aad71-114">Lagerbehållning</span><span class="sxs-lookup"><span data-stu-id="aad71-114">On-hand quantity</span></span>
- <span data-ttu-id="aad71-115">Reserverad lagerbehållning</span><span class="sxs-lookup"><span data-stu-id="aad71-115">Reserved on-hand quantity</span></span>
- <span data-ttu-id="aad71-116">Tillgänglig lagerbehållning</span><span class="sxs-lookup"><span data-stu-id="aad71-116">Available on-hand quantity</span></span>
- <span data-ttu-id="aad71-117">Beställd kvantitet</span><span class="sxs-lookup"><span data-stu-id="aad71-117">Ordered quantity</span></span>
- <span data-ttu-id="aad71-118">Kvantitet som har beställts</span><span class="sxs-lookup"><span data-stu-id="aad71-118">On-order quantity</span></span>
- <span data-ttu-id="aad71-119">Reserverad beställd kvantitet</span><span class="sxs-lookup"><span data-stu-id="aad71-119">Reserved ordered quantity</span></span>
- <span data-ttu-id="aad71-120">Total tillgänglig kvantitet</span><span class="sxs-lookup"><span data-stu-id="aad71-120">Total available quantity</span></span>

## <a name="atp-information"></a><span data-ttu-id="aad71-121">Information om ATP</span><span class="sxs-lookup"><span data-stu-id="aad71-121">ATP information</span></span>

<span data-ttu-id="aad71-122">Vid försäljning har en ny knapp **ATP-information** har lagts till i radartikal på sidor **offerter**, **order** och **fakturor**.</span><span class="sxs-lookup"><span data-stu-id="aad71-122">In Sales, a new **ATP Information** button has been added to line items on the **Quotes**, **Orders**, and **Invoices** pages.</span></span> <span data-ttu-id="aad71-123">När du klickar på knappen visas en dialogruta där du kan ange företaget, produkten, lagerplats, lagerställe och orderkvantitet.</span><span class="sxs-lookup"><span data-stu-id="aad71-123">When you select this button, a dialog box appears, where you can specify the company, product, inventory site, inventory warehouse, and order quantity.</span></span> <span data-ttu-id="aad71-124">Den här dialogrutan har samma inställningar som beskrivs i [Orderlöfte](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations).</span><span class="sxs-lookup"><span data-stu-id="aad71-124">This dialog box has the same settings that are described in [Order promising](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations).</span></span>

<span data-ttu-id="aad71-125">Dialogrutan returnerar ATP-information från Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="aad71-125">The dialog box returns the ATP information from Supply Chain Management.</span></span> <span data-ttu-id="aad71-126">I den här information beskrivs följande kvantiteter:</span><span class="sxs-lookup"><span data-stu-id="aad71-126">This information includes the following quantities:</span></span>

- <span data-ttu-id="aad71-127">Kvantitet för ATP</span><span class="sxs-lookup"><span data-stu-id="aad71-127">ATP quantity</span></span>
- <span data-ttu-id="aad71-128">Inleveranskvantitet</span><span class="sxs-lookup"><span data-stu-id="aad71-128">Receipt quantity</span></span>
- <span data-ttu-id="aad71-129">Utleveranskvantitet</span><span class="sxs-lookup"><span data-stu-id="aad71-129">Issue quantity</span></span>
- <span data-ttu-id="aad71-130">Lagerbehållning</span><span class="sxs-lookup"><span data-stu-id="aad71-130">On-hand quantity</span></span>

## <a name="how-it-works"></a><span data-ttu-id="aad71-131">Hur det fungerar</span><span class="sxs-lookup"><span data-stu-id="aad71-131">How it works</span></span>

<span data-ttu-id="aad71-132">När du väljer knappen **Lagerbehållning** på sidan **Offerter**, **Order** eller **Fakturor** görs ett liveanrop med dubbel avskrivning till API för **Lagerbehållning**.</span><span class="sxs-lookup"><span data-stu-id="aad71-132">When you select the **On-hand Inventory** button on the **Quotes**, **Orders**, or **Invoices** page, a live dual-write call is made to the **Onhand inventory** API.</span></span> <span data-ttu-id="aad71-133">API:t beräknar lagerbehållningen för den angivna produkten.</span><span class="sxs-lookup"><span data-stu-id="aad71-133">The API calculates the on-hand inventory for the given product.</span></span> <span data-ttu-id="aad71-134">Resultatet lagras i tabellerna **InventCDSInventoryOnHandRequestEntity** och **InventCDSInventoryOnHandEntryEntity** och skrivs sedan till Dataverse via dubbelriktad skrivning.</span><span class="sxs-lookup"><span data-stu-id="aad71-134">The result is stored in the **InventCDSInventoryOnHandRequestEntity** and **InventCDSInventoryOnHandEntryEntity** tables, and then is written to Dataverse by dual-write.</span></span> <span data-ttu-id="aad71-135">Om du vill använda den här funktionen måste du köra följande mappningar:</span><span class="sxs-lookup"><span data-stu-id="aad71-135">To use this functionality, you need to run the following dual-write maps.</span></span> <span data-ttu-id="aad71-136">Hoppa över ursprunglig synkronisering när du kör kartorna.</span><span class="sxs-lookup"><span data-stu-id="aad71-136">Skip initial synchronization when you run the maps.</span></span>

- <span data-ttu-id="aad71-137">CDS-lagerbehållningsposter (msdyn_inventoryonhandentries)</span><span class="sxs-lookup"><span data-stu-id="aad71-137">CDS inventory on-hand entries (msdyn_inventoryonhandentries)</span></span>
- <span data-ttu-id="aad71-138">CDS-lagerbehållningsbegäranden (msdyn_inventoryonhandrequests)</span><span class="sxs-lookup"><span data-stu-id="aad71-138">CDS inventory on-hand requests (msdyn_inventoryonhandrequests)</span></span>

## <a name="templates"></a><span data-ttu-id="aad71-139">Mallar</span><span class="sxs-lookup"><span data-stu-id="aad71-139">Templates</span></span>
<span data-ttu-id="aad71-140">Följande mallar är tillgängliga för utsätter lagerdata.</span><span class="sxs-lookup"><span data-stu-id="aad71-140">The following templates are available for the exposing the onhand inventory data.</span></span>

<span data-ttu-id="aad71-141">Finance and Operations-appar</span><span class="sxs-lookup"><span data-stu-id="aad71-141">Finance and Operations apps</span></span> | <span data-ttu-id="aad71-142">Kundengagemangsapp</span><span class="sxs-lookup"><span data-stu-id="aad71-142">Customer engagement app</span></span> | <span data-ttu-id="aad71-143">beskrivning</span><span class="sxs-lookup"><span data-stu-id="aad71-143">Description</span></span> 
---|---|---
[<span data-ttu-id="aad71-144">CDS-lagerbehållningsposter</span><span class="sxs-lookup"><span data-stu-id="aad71-144">CDS inventory on-hand entries</span></span>](#145) | <span data-ttu-id="aad71-145">msdyn_inventoryonhandentries</span><span class="sxs-lookup"><span data-stu-id="aad71-145">msdyn_inventoryonhandentries</span></span> |
[<span data-ttu-id="aad71-146">CDS-lagerbehållningsbegäranden</span><span class="sxs-lookup"><span data-stu-id="aad71-146">CDS inventory on-hand requests</span></span>](#147) | <span data-ttu-id="aad71-147">msdyn_inventoryonhandrequests</span><span class="sxs-lookup"><span data-stu-id="aad71-147">msdyn_inventoryonhandrequests</span></span> |

[!include [banner](../../includes/dual-write-symbols.md)]

###  <a name="cds-inventory-on-hand-entries-msdyn_inventoryonhandentries"></a><a name="145"></a><span data-ttu-id="aad71-148">CDS-lagerbehållningsposter (msdyn_inventoryonhandentries)</span><span class="sxs-lookup"><span data-stu-id="aad71-148">CDS inventory on-hand entries (msdyn_inventoryonhandentries)</span></span>

<span data-ttu-id="aad71-149">Den här mallen synkroniserar data mellan Finance and Operations-appar och Dataverse.</span><span class="sxs-lookup"><span data-stu-id="aad71-149">This template synchronizes data between Finance and Operations apps and Dataverse.</span></span>

<span data-ttu-id="aad71-150">Finance and Operations-fält</span><span class="sxs-lookup"><span data-stu-id="aad71-150">Finance and Operations field</span></span> | <span data-ttu-id="aad71-151">Mappningstyp</span><span class="sxs-lookup"><span data-stu-id="aad71-151">Map type</span></span> | <span data-ttu-id="aad71-152">Customer Engagement-fält</span><span class="sxs-lookup"><span data-stu-id="aad71-152">Customer engagement field</span></span> | <span data-ttu-id="aad71-153">Standardvärde</span><span class="sxs-lookup"><span data-stu-id="aad71-153">Default value</span></span>
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

###  <a name="cds-inventory-on-hand-requests-msdyn_inventoryonhandrequests"></a><a name="147"></a><span data-ttu-id="aad71-154">CDS-lagerbehållningsbegäranden (msdyn_inventoryonhandrequests)</span><span class="sxs-lookup"><span data-stu-id="aad71-154">CDS inventory on-hand requests (msdyn_inventoryonhandrequests)</span></span>

<span data-ttu-id="aad71-155">Den här mallen synkroniserar data mellan Finance and Operations-appar och Dataverse.</span><span class="sxs-lookup"><span data-stu-id="aad71-155">This template synchronizes data between Finance and Operations apps and Dataverse.</span></span>

<span data-ttu-id="aad71-156">Finance and Operations-fält</span><span class="sxs-lookup"><span data-stu-id="aad71-156">Finance and Operations field</span></span> | <span data-ttu-id="aad71-157">Mappningstyp</span><span class="sxs-lookup"><span data-stu-id="aad71-157">Map type</span></span> | <span data-ttu-id="aad71-158">Customer Engagement-fält</span><span class="sxs-lookup"><span data-stu-id="aad71-158">Customer engagement field</span></span> | <span data-ttu-id="aad71-159">Standardvärde</span><span class="sxs-lookup"><span data-stu-id="aad71-159">Default value</span></span>
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