---
title: Leveransplaner
description: Leveransplaner ger möjlighet att följa orderradkvantiteter när du använder flera leveranser för en enskild försäljningsorder, försäljningsoffert eller inköpsorder.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchDeliverySchedule, SalesDeliverySchedule, SalesQuotationDeliverySchedule, SalesQuotationDeliverySchedule
audience: Application User
ms.reviewer: kamaybac
ms.custom: 213984
ms.assetid: 44cac104-c36c-4371-a992-9178b3fd65e9
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3dbd66d499b5d5f9f8ef21c0ce3752031a5f4672
ms.sourcegitcommit: 74e47075eab2b0b28f82b0d57f439719847ecb01
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/07/2021
ms.locfileid: "6193792"
---
# <a name="delivery-schedules"></a><span data-ttu-id="02395-103">Leveransplaner</span><span class="sxs-lookup"><span data-stu-id="02395-103">Delivery schedules</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="02395-104">Leveransplaner ger möjlighet att följa orderradkvantiteter när du använder flera leveranser för en enskild försäljningsorder, försäljningsoffert eller inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="02395-104">Delivery schedules allow you to track order line quantity when you are using multiple deliveries for a single sales order, sales quotation, or purchase order.</span></span>

<span data-ttu-id="02395-105">Använd en leveransplan när den totala kvantiteten på en order- eller offertrad måste levereras i flera försändelser.</span><span class="sxs-lookup"><span data-stu-id="02395-105">Use a delivery schedule when the total quantity on an order or quotation line must be delivered in multiple shipments.</span></span> <span data-ttu-id="02395-106">Enskilda försändelser representeras av leveransrader.</span><span class="sxs-lookup"><span data-stu-id="02395-106">Individual shipments are represented by delivery lines.</span></span> <span data-ttu-id="02395-107">Två eller fler leveransrader utgör en leveransplan.</span><span class="sxs-lookup"><span data-stu-id="02395-107">Two or more delivery lines make up one delivery schedule.</span></span> <span data-ttu-id="02395-108">Leveransraderna kan ha andra leveransdatum, kvantiteter, leveranssätt och lagringsdimensioner, till exempel plats och lagerställe.</span><span class="sxs-lookup"><span data-stu-id="02395-108">The delivery lines can have different delivery dates, quantities, modes of delivery, and storage dimensions, such as site and warehouse.</span></span>  

<span data-ttu-id="02395-109">**Exempel på en leveransplan**</span><span class="sxs-lookup"><span data-stu-id="02395-109">**Example of a delivery schedule**</span></span>

| <span data-ttu-id="02395-110">Artikel</span><span class="sxs-lookup"><span data-stu-id="02395-110">Item</span></span>                              | <span data-ttu-id="02395-111">Värde</span><span class="sxs-lookup"><span data-stu-id="02395-111">Value</span></span>                                    |
|-----------------------------------|------------------------------------------|
| <span data-ttu-id="02395-112">Total order (den ursprungliga orderraden)</span><span class="sxs-lookup"><span data-stu-id="02395-112">Total order (original order line)</span></span> | <span data-ttu-id="02395-113">600 stolar</span><span class="sxs-lookup"><span data-stu-id="02395-113">600 chairs</span></span>                               |
| <span data-ttu-id="02395-114">Begärd leveransplan</span><span class="sxs-lookup"><span data-stu-id="02395-114">Requested delivery schedule</span></span>       | <span data-ttu-id="02395-115">100 stolar per månad</span><span class="sxs-lookup"><span data-stu-id="02395-115">100 chairs per month</span></span>                     |
| <span data-ttu-id="02395-116">Önskat tidsram för leverans</span><span class="sxs-lookup"><span data-stu-id="02395-116">Requested time frame for delivery</span></span> | <span data-ttu-id="02395-117">6 månader den första dagen i varje månad</span><span class="sxs-lookup"><span data-stu-id="02395-117">6 months, on the first day of each month</span></span> |

<span data-ttu-id="02395-118">I det här scenariot begär kunden leverans av 600 stolar i batchar med 100 stolar över en period i halvåret.</span><span class="sxs-lookup"><span data-stu-id="02395-118">In this scenario, the customer requests delivery of 600 chairs in batches of 100 chairs over a period of six months.</span></span> <span data-ttu-id="02395-119">Om du vill spåra leveranskraven skapar du en leveransplan.</span><span class="sxs-lookup"><span data-stu-id="02395-119">To keep track of the delivery requirements, you create a delivery schedule.</span></span> <span data-ttu-id="02395-120">På sidan leveransplan skapar du sex separata leveransrader.</span><span class="sxs-lookup"><span data-stu-id="02395-120">On the delivery schedule page, you create six separate delivery lines.</span></span> <span data-ttu-id="02395-121">Varje leveransrad innehåller 100 stolar och visar leveransdatum för dessa 100 stolar.</span><span class="sxs-lookup"><span data-stu-id="02395-121">Each delivery line contains 100 chairs and indicates the delivery date for those 100 chairs.</span></span> <span data-ttu-id="02395-122">I det här fallet motbokas varje rad på den första i månaden för sex månader i följd.</span><span class="sxs-lookup"><span data-stu-id="02395-122">In this case, each line is offset on the first of the month for six consecutive months.</span></span>  

<span data-ttu-id="02395-123">När du skapar en leveransplan, ändras typen för den ursprungliga orderraden automatiskt till **Orderrad med flera leveranser**.</span><span class="sxs-lookup"><span data-stu-id="02395-123">When you create a delivery schedule, the type of the original order line is automatically changed to **Order line with multiple deliveries**.</span></span> <span data-ttu-id="02395-124">En rad med den här typen kallas för en kommersiella rad och är markerade med en ikon.</span><span class="sxs-lookup"><span data-stu-id="02395-124">A line of this type is referred to as a commercial line and is marked by an icon.</span></span> <span data-ttu-id="02395-125">Leveransraden är markerad med en annan ikon.</span><span class="sxs-lookup"><span data-stu-id="02395-125">The delivery line is marked by a different icon.</span></span> <span data-ttu-id="02395-126">Om du ändrar en kvantitet på en leveransrad uppdateras den kommersiella raden till den totala kvantiteten för leveransplanen.</span><span class="sxs-lookup"><span data-stu-id="02395-126">If you change a quantity on a delivery line, the commercial line is updated to the total quantity of the delivery schedule.</span></span> <span data-ttu-id="02395-127">Om ett handelsavtal har definierat en total rabatt för ordern, garanterar leveransplanen att din order är berättigad till en total orderrabatt, även om ordern är uppdelad i separata leveranser.</span><span class="sxs-lookup"><span data-stu-id="02395-127">If a trade agreement has defined a total discount for the order, the delivery schedule ensures that your order is eligible for the total order discount, even when the order is split into separate deliveries.</span></span>  

<span data-ttu-id="02395-128">Order som har en leveransplan bearbetas mot leveransraderna.</span><span class="sxs-lookup"><span data-stu-id="02395-128">Orders that have a delivery schedule are processed against the delivery lines.</span></span> <span data-ttu-id="02395-129">Bearbetningen inkluderar bokföring av följesedlar, produktinleveranser och fakturering.</span><span class="sxs-lookup"><span data-stu-id="02395-129">Processing includes the posting of packing slips, product receipts, and invoicing.</span></span>  

<span data-ttu-id="02395-130">Dokumentera utskrifter av order och offerter som har en leveransplan Visa bara leveransraderna.</span><span class="sxs-lookup"><span data-stu-id="02395-130">Document printouts of orders and quotations that have a delivery schedule show only the delivery lines.</span></span> <span data-ttu-id="02395-131">De visar inte de ursprungliga raderna (kommersiella rader).</span><span class="sxs-lookup"><span data-stu-id="02395-131">They don't show the original lines (commercial lines).</span></span> <span data-ttu-id="02395-132">**Obs!** Dessutom visas bara leveransraderna när du genomför dessa åtgärder:</span><span class="sxs-lookup"><span data-stu-id="02395-132">**Note:** In addition, only the delivery lines are shown when you perform these actions:</span></span>

-   <span data-ttu-id="02395-133">Bokför</span><span class="sxs-lookup"><span data-stu-id="02395-133">Post</span></span>
-   <span data-ttu-id="02395-134">Kopiera sidor</span><span class="sxs-lookup"><span data-stu-id="02395-134">Copy pages</span></span>
-   <span data-ttu-id="02395-135">Bläddra i listasidor och rapporter</span><span class="sxs-lookup"><span data-stu-id="02395-135">Browse list pages and reports</span></span>

<span data-ttu-id="02395-136">När du bekräftar försäljningsofferter, visar de resulterande försäljningsorder hela leveransplanen, även orderraderna som har flera leveranser.</span><span class="sxs-lookup"><span data-stu-id="02395-136">When you confirm sales quotations, the resulting sales orders show the whole delivery schedule, even the order lines that have multiple deliveries.</span></span> <span data-ttu-id="02395-137">Dessutom visas hela leveransplanen på alla sidor, till exempel försäljningsorder, försäljningsofferter och inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="02395-137">In addition, the whole delivery schedule is shown on all the major pages, such as sales orders, sales quotations, and purchase orders.</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]