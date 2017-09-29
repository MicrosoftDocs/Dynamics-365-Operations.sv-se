--- 
title: "Registrera inleverans av varor på en inköpsorder"
description: "Den här proceduren visar dig hur du registrerar inleverans av varor direkt i en inköpsorder."
author: FrankDahl
manager: AnnBe
ms.date: 08/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 9b2300a593c9e153ee598fa72e29907c82f2b79e
ms.contentlocale: sv-se
ms.lasthandoff: 08/29/2017

---
# <a name="record-the-receipt-of-goods-on-the-purchase-order"></a><span data-ttu-id="c98f9-103">Registrera inleverans av varor på en inköpsorder</span><span class="sxs-lookup"><span data-stu-id="c98f9-103">Record the receipt of goods on the purchase order</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c98f9-104">Den här proceduren visar dig hur du registrerar inleverans av varor direkt i en inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="c98f9-104">This procedure shows you how to record receipt of goods directly on a purchase order.</span></span> <span data-ttu-id="c98f9-105">Det går också att registrera produktinleveransen på lagret och bokföra den senare på inköpsordern.</span><span class="sxs-lookup"><span data-stu-id="c98f9-105">It’s also possible to register product receipt in the warehouse, and then later record it on the purchase order.</span></span> <span data-ttu-id="c98f9-106">Denna uppgift görs vanligtvis av en inköpsagent eller en leverantörsreskontrakoordinator.</span><span class="sxs-lookup"><span data-stu-id="c98f9-106">This task is typically done by a purchasing agent or an accounts payable coordinator.</span></span> <span data-ttu-id="c98f9-107">De exempel som visas i den här handboken kan användas i demoföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="c98f9-107">The example shown in this guide can be used in the USMF demo data company.</span></span> <span data-ttu-id="c98f9-108">Exemplet omfattar steg för att skapa en enda inköpsorder, så att du kan spela upp proceduren som en uppgiftsguide.</span><span class="sxs-lookup"><span data-stu-id="c98f9-108">The example includes steps to create a simple purchase order so that you can play the procedure as a task guide.</span></span> <span data-ttu-id="c98f9-109">Om du använder proceduren på dina egna data ska du börja med underuppgiften Registrera inleverans av varor.</span><span class="sxs-lookup"><span data-stu-id="c98f9-109">If you were using the procedure on your own data, you would start at the Record receipt of goods subtask.</span></span>


## <a name="prepare-a-new-purchase-order-for-receipt-of-goods"></a><span data-ttu-id="c98f9-110">Förbered en ny inköpsorder för inleverans av varor.</span><span class="sxs-lookup"><span data-stu-id="c98f9-110">Prepare a new purchase order for receipt of goods</span></span>
1. <span data-ttu-id="c98f9-111">Gå till Anskaffning och källa > Inköpsorder > Alla inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="c98f9-111">Go to Procurement and sourcing > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="c98f9-112">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="c98f9-112">Click New.</span></span>
3. <span data-ttu-id="c98f9-113">Ange "US-101" i fältet Leverantörskonto.</span><span class="sxs-lookup"><span data-stu-id="c98f9-113">In the Vendor account field, enter US-101.</span></span>
4. <span data-ttu-id="c98f9-114">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="c98f9-114">Click OK.</span></span>
5. <span data-ttu-id="c98f9-115">Ange ett artikelnummer i fältet M0001.</span><span class="sxs-lookup"><span data-stu-id="c98f9-115">In the Item number field, enter M0001.</span></span>
6. <span data-ttu-id="c98f9-116">Ange 5 i fältet Kvantitet.</span><span class="sxs-lookup"><span data-stu-id="c98f9-116">In the Quantity field, enter 5.</span></span>
7. <span data-ttu-id="c98f9-117">Klicka på Inköp i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="c98f9-117">On the Action Pane, click Purchase.</span></span>
8. <span data-ttu-id="c98f9-118">Klicka på Bekräfta.</span><span class="sxs-lookup"><span data-stu-id="c98f9-118">Click Confirm.</span></span>

## <a name="record-receipt-of-goods"></a><span data-ttu-id="c98f9-119">Registrera inleverans av varor</span><span class="sxs-lookup"><span data-stu-id="c98f9-119">Record receipt of goods</span></span>
1. <span data-ttu-id="c98f9-120">Klicka på Ta emot i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="c98f9-120">On the Action Pane, click Receive.</span></span>
2. <span data-ttu-id="c98f9-121">Klicka på Produktinleverans.</span><span class="sxs-lookup"><span data-stu-id="c98f9-121">Click Product receipt.</span></span>
    * <span data-ttu-id="c98f9-122">Fältet Kvantitet låter dig välja olika alternativ för den kvantitet som du vill ta emot.</span><span class="sxs-lookup"><span data-stu-id="c98f9-122">The Quantity field allows you to select different options for the quantity that you want to receive.</span></span> <span data-ttu-id="c98f9-123">Till exempel om en kvantitet tidigare har registrerats i lagerstället, kan du välja registrerad kvantitet.</span><span class="sxs-lookup"><span data-stu-id="c98f9-123">For example, if a quantity has previously been registered in the warehouse, you can select Registered quantity.</span></span>  <span data-ttu-id="c98f9-124">Använd värdet Beställd kvantitet för det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="c98f9-124">For this example, use the value Ordered quantity.</span></span>   
3. <span data-ttu-id="c98f9-125">I fältet Produktinleverans anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="c98f9-125">In the Product receipt field, type any value.</span></span>
    * <span data-ttu-id="c98f9-126">Det här fältet används för att ange en referens som ska användas som verifikation för produktinleveransjournalen.</span><span class="sxs-lookup"><span data-stu-id="c98f9-126">This field is used to enter a reference that will be used as voucher for the product receipt journal.</span></span>  
4. <span data-ttu-id="c98f9-127">Expandera avsnittet Rader.</span><span class="sxs-lookup"><span data-stu-id="c98f9-127">Expand the Lines section.</span></span>
5. <span data-ttu-id="c98f9-128">Ställ in kvantiteten på 4.</span><span class="sxs-lookup"><span data-stu-id="c98f9-128">Set Quantity to '4'.</span></span>
    * <span data-ttu-id="c98f9-129">Här kan du manuellt ange den kvantitet som har inlevererats för varje rad i ordern.</span><span class="sxs-lookup"><span data-stu-id="c98f9-129">Here you are able to manually specify the quantity that is being received for each line on the order.</span></span>  
6. <span data-ttu-id="c98f9-130">Komprimera avsnittet Rader.</span><span class="sxs-lookup"><span data-stu-id="c98f9-130">Collapse the Lines section.</span></span>
7. <span data-ttu-id="c98f9-131">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="c98f9-131">Click OK.</span></span>
    * <span data-ttu-id="c98f9-132">Varorna har nu registrerats som inlevererade på inköpsordern och en produktinleveransjournal har skapats som dokumentet för att återspegla detta.</span><span class="sxs-lookup"><span data-stu-id="c98f9-132">The goods have now been recorded as received on the purchase order, and a product receipt journal has been created as document to reflect this.</span></span> <span data-ttu-id="c98f9-133">Du kan använda åtgärden Produktinleverans om du vill granska journalerna som skapats med inköpsordern och se vad som har levererats och när.</span><span class="sxs-lookup"><span data-stu-id="c98f9-133">You can use the Product receipt action to review the journals created with the purchase order, and see what was received, and when.</span></span>  


