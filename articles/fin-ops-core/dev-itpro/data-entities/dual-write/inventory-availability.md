---
title: Lagertillgänglighet vid dubbelriktad skrivning
description: I det här avsnittet finns information om kontroll av lagertillgänglighet vid dubbelriktad skrivning.
author: yijialuan
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: 4d1022eec633bf0a9edb4d5b26982853cec836d7
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4457443"
---
# <a name="inventory-availability-in-dual-write"></a><span data-ttu-id="1555d-103">Lagertillgänglighet vid dubbelriktad skrivning</span><span class="sxs-lookup"><span data-stu-id="1555d-103">Inventory availability in dual-write</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1555d-104">Genom lagertillgänglighet kan du kontrollera lagret innan du lägger till en produkt sida **Offerter**, **Order** eller **Fakturor** i Microsoft Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="1555d-104">By using inventory availability, you can check your inventory before you add a product to the **Quotations**, **Orders**, or **Invoices** page in Microsoft Dynamics 365 Sales.</span></span> <span data-ttu-id="1555d-105">Till exempel är kontroll av lager och bestämning av ett uppfyllelsedatum är en viktig uppgift i processen [potentiell kund till pengar](dual-write-prospect-to-cash.md).</span><span class="sxs-lookup"><span data-stu-id="1555d-105">For example, you check inventory and determine a fulfillment date as one key task in the [prospect-to-cash](dual-write-prospect-to-cash.md) process.</span></span>

<span data-ttu-id="1555d-106">Om du inte har tillräckligt med lager kan du uppskatta ett leveransdatum med utgångspunkt i projekterade lagerinleveranser och utleveranser.</span><span class="sxs-lookup"><span data-stu-id="1555d-106">If you don't have enough inventory, you can estimate a delivery date, based on projected inventory receipts and issues.</span></span> <span data-ttu-id="1555d-107">Du kan också kontrollera produktens tillgängliga ATP-information, där du kan hitta kvantiteten för tillgängligt att lova i den fördefinierade tidsgränsen.</span><span class="sxs-lookup"><span data-stu-id="1555d-107">You can also check the product's available-to-promise (ATP) information, where you can find the ATP quantity in the predefined time fence.</span></span>

## <a name="on-hand-inventory"></a><span data-ttu-id="1555d-108">Lagerbehållning</span><span class="sxs-lookup"><span data-stu-id="1555d-108">On-hand inventory</span></span>

<span data-ttu-id="1555d-109">I Dynamics 365 Sales, en ny knapp **Lagerbehållning** har lagts till i rubriken på sidorna **Offerter**, **Order** och **Fakturor**.</span><span class="sxs-lookup"><span data-stu-id="1555d-109">In Dynamics 365 Sales, a new **On-hand Inventory** button has been added to the header of the **Quotes**, **Orders**, and **Invoices** pages.</span></span> <span data-ttu-id="1555d-110">När du klickar på knappen visas en dialogruta där du kan ange företaget och produkten som du vill kontrollera lagerbehållningen för.</span><span class="sxs-lookup"><span data-stu-id="1555d-110">When you select this button, a dialog box appears, where you can specify the company and the product that you want to check the on-hand inventory for.</span></span> <span data-ttu-id="1555d-111">I den här dialogrutan visas samma information som [lagerbehållning](../../../../supply-chain/inventory/tasks/check-availability-stock.md).</span><span class="sxs-lookup"><span data-stu-id="1555d-111">This dialog box shows the same information as [On-hand inventory](../../../../supply-chain/inventory/tasks/check-availability-stock.md).</span></span>

<span data-ttu-id="1555d-112">Dialogrutan returnerar lagerinformationen från Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="1555d-112">The dialog box returns the inventory information from Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="1555d-113">I den här information beskrivs följande kvantiteter:</span><span class="sxs-lookup"><span data-stu-id="1555d-113">This information includes the following quantities:</span></span>

- <span data-ttu-id="1555d-114">Lagerbehållning</span><span class="sxs-lookup"><span data-stu-id="1555d-114">On-hand quantity</span></span>
- <span data-ttu-id="1555d-115">Reserverad lagerbehållning</span><span class="sxs-lookup"><span data-stu-id="1555d-115">Reserved on-hand quantity</span></span>
- <span data-ttu-id="1555d-116">Tillgänglig lagerbehållning</span><span class="sxs-lookup"><span data-stu-id="1555d-116">Available on-hand quantity</span></span>
- <span data-ttu-id="1555d-117">Beställd kvantitet</span><span class="sxs-lookup"><span data-stu-id="1555d-117">Ordered quantity</span></span>
- <span data-ttu-id="1555d-118">Kvantitet som har beställts</span><span class="sxs-lookup"><span data-stu-id="1555d-118">On-order quantity</span></span>
- <span data-ttu-id="1555d-119">Reserverad beställd kvantitet</span><span class="sxs-lookup"><span data-stu-id="1555d-119">Reserved ordered quantity</span></span>
- <span data-ttu-id="1555d-120">Total tillgänglig kvantitet</span><span class="sxs-lookup"><span data-stu-id="1555d-120">Total available quantity</span></span>

## <a name="atp-information"></a><span data-ttu-id="1555d-121">Information om ATP</span><span class="sxs-lookup"><span data-stu-id="1555d-121">ATP information</span></span>

<span data-ttu-id="1555d-122">Vid försäljning har en ny knapp **ATP-information** har lagts till i radartikal på sidor **offerter**, **order** och **fakturor**.</span><span class="sxs-lookup"><span data-stu-id="1555d-122">In Sales, a new **ATP Information** button has been added to line items on the **Quotes**, **Orders**, and **Invoices** pages.</span></span> <span data-ttu-id="1555d-123">När du klickar på knappen visas en dialogruta där du kan ange företaget, produkten, lagerplats, lagerställe och orderkvantitet.</span><span class="sxs-lookup"><span data-stu-id="1555d-123">When you select this button, a dialog box appears, where you can specify the company, product, inventory site, inventory warehouse, and order quantity.</span></span> <span data-ttu-id="1555d-124">Den här dialogrutan har samma inställningar som beskrivs i [Orderlöfte](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations).</span><span class="sxs-lookup"><span data-stu-id="1555d-124">This dialog box has the same settings that are described in [Order promising](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations).</span></span>

<span data-ttu-id="1555d-125">Dialogrutan returnerar ATP-information från Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="1555d-125">The dialog box returns the ATP information from Supply Chain Management.</span></span> <span data-ttu-id="1555d-126">I den här information beskrivs följande kvantiteter:</span><span class="sxs-lookup"><span data-stu-id="1555d-126">This information includes the following quantities:</span></span>

- <span data-ttu-id="1555d-127">Kvantitet för ATP</span><span class="sxs-lookup"><span data-stu-id="1555d-127">ATP quantity</span></span>
- <span data-ttu-id="1555d-128">Inleveranskvantitet</span><span class="sxs-lookup"><span data-stu-id="1555d-128">Receipt quantity</span></span>
- <span data-ttu-id="1555d-129">Utleveranskvantitet</span><span class="sxs-lookup"><span data-stu-id="1555d-129">Issue quantity</span></span>
- <span data-ttu-id="1555d-130">Lagerbehållning</span><span class="sxs-lookup"><span data-stu-id="1555d-130">On-hand quantity</span></span>
