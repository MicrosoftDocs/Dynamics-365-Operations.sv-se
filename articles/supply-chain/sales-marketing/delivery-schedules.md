---
title: Leveransplaner
description: "Leveransplaner ger möjlighet att följa orderradkvantiteter när du använder flera leveranser för en enskild försäljningsorder, försäljningsoffert eller inköpsorder."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchDeliverySchedule, SalesDeliverySchedule, SalesQuotationDeliverySchedule
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 213984
ms.assetid: 44cac104-c36c-4371-a992-9178b3fd65e9
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 84ae84a567e5f45bc0b20538d04917c6feb21336
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="delivery-schedules"></a><span data-ttu-id="f59ef-103">Leveransplaner</span><span class="sxs-lookup"><span data-stu-id="f59ef-103">Delivery schedules</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="f59ef-104">Leveransplaner ger möjlighet att följa orderradkvantiteter när du använder flera leveranser för en enskild försäljningsorder, försäljningsoffert eller inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="f59ef-104">Delivery schedules allow you to track order line quantity when you are using multiple deliveries for a single sales order, sales quotation, or purchase order.</span></span>

<span data-ttu-id="f59ef-105">Använd en leveransplan när den totala kvantiteten på en order- eller offertrad måste levereras i flera försändelser.</span><span class="sxs-lookup"><span data-stu-id="f59ef-105">Use a delivery schedule when the total quantity on an order or quotation line must be delivered in multiple shipments.</span></span> <span data-ttu-id="f59ef-106">Enskilda försändelser representeras av leveransrader.</span><span class="sxs-lookup"><span data-stu-id="f59ef-106">Individual shipments are represented by delivery lines.</span></span> <span data-ttu-id="f59ef-107">Två eller fler leveransrader utgör en leveransplan.</span><span class="sxs-lookup"><span data-stu-id="f59ef-107">Two or more delivery lines make up one delivery schedule.</span></span> <span data-ttu-id="f59ef-108">Leveransraderna kan ha andra leveransdatum, kvantiteter, leveranssätt och lagringsdimensioner, till exempel plats och lagerställe.</span><span class="sxs-lookup"><span data-stu-id="f59ef-108">The delivery lines can have different delivery dates, quantities, modes of delivery, and storage dimensions, such as site and warehouse.</span></span>  

<span data-ttu-id="f59ef-109">**Exempel på en leveransplan**</span><span class="sxs-lookup"><span data-stu-id="f59ef-109">**Example of a delivery schedule**</span></span>

|                                   |                                          |
|-----------------------------------|------------------------------------------|
| <span data-ttu-id="f59ef-110">Total order (den ursprungliga orderraden)</span><span class="sxs-lookup"><span data-stu-id="f59ef-110">Total order (original order line)</span></span> | <span data-ttu-id="f59ef-111">600 stolar</span><span class="sxs-lookup"><span data-stu-id="f59ef-111">600 chairs</span></span>                               |
| <span data-ttu-id="f59ef-112">Begärd leveransplan</span><span class="sxs-lookup"><span data-stu-id="f59ef-112">Requested delivery schedule</span></span>       | <span data-ttu-id="f59ef-113">100 stolar per månad</span><span class="sxs-lookup"><span data-stu-id="f59ef-113">100 chairs per month</span></span>                     |
| <span data-ttu-id="f59ef-114">Önskat tidsram för leverans</span><span class="sxs-lookup"><span data-stu-id="f59ef-114">Requested time frame for delivery</span></span> | <span data-ttu-id="f59ef-115">6 månader den första dagen i varje månad</span><span class="sxs-lookup"><span data-stu-id="f59ef-115">6 months, on the first day of each month</span></span> |

<span data-ttu-id="f59ef-116">I det här scenariot begär kunden leverans av 600 stolar i batchar med 100 stolar över en period i halvåret.</span><span class="sxs-lookup"><span data-stu-id="f59ef-116">In this scenario, the customer requests delivery of 600 chairs in batches of 100 chairs over a period of six months.</span></span> <span data-ttu-id="f59ef-117">Om du vill spåra leveranskraven skapar du en leveransplan.</span><span class="sxs-lookup"><span data-stu-id="f59ef-117">To keep track of the delivery requirements, you create a delivery schedule.</span></span> <span data-ttu-id="f59ef-118">På sidan leveransplan skapar du sex separata leveransrader.</span><span class="sxs-lookup"><span data-stu-id="f59ef-118">On the delivery schedule page, you create six separate delivery lines.</span></span> <span data-ttu-id="f59ef-119">Varje leveransrad innehåller 100 stolar och visar leveransdatum för dessa 100 stolar.</span><span class="sxs-lookup"><span data-stu-id="f59ef-119">Each delivery line contains 100 chairs and indicates the delivery date for those 100 chairs.</span></span> <span data-ttu-id="f59ef-120">I det här fallet motbokas varje rad på den första i månaden för sex månader i följd.</span><span class="sxs-lookup"><span data-stu-id="f59ef-120">In this case, each line is offset on the first of the month for six consecutive months.</span></span>  

<span data-ttu-id="f59ef-121">När du skapar en leveransplan, ändras typen för den ursprungliga orderraden automatiskt till **Orderrad med flera leveranser**.</span><span class="sxs-lookup"><span data-stu-id="f59ef-121">When you create a delivery schedule, the type of the original order line is automatically changed to **Order line with multiple deliveries**.</span></span> <span data-ttu-id="f59ef-122">En rad med den här typen kallas för en kommersiella rad och är markerade med en ikon.</span><span class="sxs-lookup"><span data-stu-id="f59ef-122">A line of this type is referred to as a commercial line and is marked by an icon.</span></span> <span data-ttu-id="f59ef-123">Leveransraden är markerad med en annan ikon.</span><span class="sxs-lookup"><span data-stu-id="f59ef-123">The delivery line is marked by a different icon.</span></span> <span data-ttu-id="f59ef-124">Om du ändrar en kvantitet på en leveransrad uppdateras den kommersiella raden till den totala kvantiteten för leveransplanen.</span><span class="sxs-lookup"><span data-stu-id="f59ef-124">If you change a quantity on a delivery line, the commercial line is updated to the total quantity of the delivery schedule.</span></span> <span data-ttu-id="f59ef-125">Om ett handelsavtal har definierat en total rabatt för ordern, garanterar leveransplanen att din order är berättigad till en total orderrabatt, även om ordern är uppdelad i separata leveranser.</span><span class="sxs-lookup"><span data-stu-id="f59ef-125">If a trade agreement has defined a total discount for the order, the delivery schedule ensures that your order is eligible for the total order discount, even when the order is split into separate deliveries.</span></span>  

<span data-ttu-id="f59ef-126">Order som har en leveransplan bearbetas mot leveransraderna.</span><span class="sxs-lookup"><span data-stu-id="f59ef-126">Orders that have a delivery schedule are processed against the delivery lines.</span></span> <span data-ttu-id="f59ef-127">Bearbetningen inkluderar bokföring av följesedlar, produktinleveranser och fakturering.</span><span class="sxs-lookup"><span data-stu-id="f59ef-127">Processing includes the posting of packing slips, product receipts, and invoicing.</span></span>  

<span data-ttu-id="f59ef-128">Dokumentera utskrifter av order och offerter som har en leveransplan Visa bara leveransraderna.</span><span class="sxs-lookup"><span data-stu-id="f59ef-128">Document printouts of orders and quotations that have a delivery schedule show only the delivery lines.</span></span> <span data-ttu-id="f59ef-129">De visar inte de ursprungliga raderna (kommersiella rader).</span><span class="sxs-lookup"><span data-stu-id="f59ef-129">They don't show the original lines (commercial lines).</span></span> <span data-ttu-id="f59ef-130">**Obs!** Dessutom visas bara leveransraderna när du genomför dessa åtgärder:</span><span class="sxs-lookup"><span data-stu-id="f59ef-130">**Note:** In addition, only the delivery lines are shown when you perform these actions:</span></span>

-   <span data-ttu-id="f59ef-131">Bokför</span><span class="sxs-lookup"><span data-stu-id="f59ef-131">Post</span></span>
-   <span data-ttu-id="f59ef-132">Kopiera sidor</span><span class="sxs-lookup"><span data-stu-id="f59ef-132">Copy pages</span></span>
-   <span data-ttu-id="f59ef-133">Bläddra i listasidor och rapporter</span><span class="sxs-lookup"><span data-stu-id="f59ef-133">Browse list pages and reports</span></span>

<span data-ttu-id="f59ef-134">När du bekräftar försäljningsofferter, visar de resulterande försäljningsorder hela leveransplanen, även orderraderna som har flera leveranser.</span><span class="sxs-lookup"><span data-stu-id="f59ef-134">When you confirm sales quotations, the resulting sales orders show the whole delivery schedule, even the order lines that have multiple deliveries.</span></span> <span data-ttu-id="f59ef-135">Dessutom visas hela leveransplanen på alla sidor, till exempel försäljningsorder, försäljningsofferter och inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="f59ef-135">In addition, the whole delivery schedule is shown on all the major pages, such as sales orders, sales quotations, and purchase orders.</span></span>




