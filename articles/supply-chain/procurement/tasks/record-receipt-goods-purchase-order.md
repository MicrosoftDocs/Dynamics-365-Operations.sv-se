---
title: Registrera inleverans av varor på en inköpsorder
description: Det häravsnittet visar dig hur du registrerar inleverans av varor direkt i en inköpsorder.
author: mkirknel
manager: tfehr
ms.date: 07/09/19
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder, InventItemIdLookupPurchase, PurchEditLines
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6365ccf4414e49bc1f22bcedb42f192c5c9a5ee8
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3207633"
---
# <a name="record-the-receipt-of-goods-on-the-purchase-order"></a><span data-ttu-id="73c26-103">Registrera inleverans av varor på en inköpsorder</span><span class="sxs-lookup"><span data-stu-id="73c26-103">Record the receipt of goods on the purchase order</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="73c26-104">Det häravsnittet visar dig hur du registrerar inleverans av varor direkt i en inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="73c26-104">This topic explains how to record receipt of goods directly on a purchase order.</span></span> <span data-ttu-id="73c26-105">Det går också att registrera produktinleveransen på lagret och bokföra den senare på inköpsordern.</span><span class="sxs-lookup"><span data-stu-id="73c26-105">It's also possible to register product receipt in the warehouse, and then later record it on the purchase order.</span></span> <span data-ttu-id="73c26-106">Denna uppgift görs vanligtvis av en inköpsagent eller en leverantörsreskontrakoordinator.</span><span class="sxs-lookup"><span data-stu-id="73c26-106">This task is typically done by a purchasing agent or an accounts payable coordinator.</span></span> <span data-ttu-id="73c26-107">De exempel som visas i den här handboken kan användas i demoföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="73c26-107">The example shown in this guide can be used in the USMF demo data company.</span></span> <span data-ttu-id="73c26-108">Exemplet omfattar steg för att skapa en enda inköpsorder, så att du kan spela upp proceduren som en uppgiftsguide.</span><span class="sxs-lookup"><span data-stu-id="73c26-108">The example includes steps to create a simple purchase order so that you can play the procedure as a task guide.</span></span> <span data-ttu-id="73c26-109">Om du använder proceduren på dina egna data ska du börja med underuppgiften **Registrera inleverans av varor**.</span><span class="sxs-lookup"><span data-stu-id="73c26-109">If you were using the procedure on your own data, you would start at the **Record receipt of goods** subtask.</span></span>


## <a name="prepare-a-new-purchase-order-for-receipt-of-goods"></a><span data-ttu-id="73c26-110">Förbered en ny inköpsorder för inleverans av varor.</span><span class="sxs-lookup"><span data-stu-id="73c26-110">Prepare a new purchase order for receipt of goods</span></span>
1. <span data-ttu-id="73c26-111">Gå till **Navigeringsfönster > Moduler > Anskaffning och källa > Inköpsorder > Alla inköpsorder**.</span><span class="sxs-lookup"><span data-stu-id="73c26-111">Go to **Navigation pane > Modules > Procurement and sourcing > Purchase orders > All purchase orders**.</span></span>
2. <span data-ttu-id="73c26-112">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="73c26-112">Select **New**.</span></span>
3. <span data-ttu-id="73c26-113">I fältet **Leverantörskonto** ange `US-101`.</span><span class="sxs-lookup"><span data-stu-id="73c26-113">In the **Vendor account** field, enter `US-101`.</span></span>
4. <span data-ttu-id="73c26-114">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="73c26-114">Select **OK**.</span></span>
5. <span data-ttu-id="73c26-115">I fältet **artikelnummer** anger du `M0001`.</span><span class="sxs-lookup"><span data-stu-id="73c26-115">In the **Item number** field, enter `M0001`.</span></span>
6. <span data-ttu-id="73c26-116">I fältet **Kvantitet** anger du `5`.</span><span class="sxs-lookup"><span data-stu-id="73c26-116">In the **Quantity** field, enter `5`.</span></span>
7. <span data-ttu-id="73c26-117">I åtgärdsfönstret, välj **Inköp**.</span><span class="sxs-lookup"><span data-stu-id="73c26-117">On the Action Pane, select **Purchase**.</span></span>
8. <span data-ttu-id="73c26-118">Välj **Bekräfta**.</span><span class="sxs-lookup"><span data-stu-id="73c26-118">Select **Confirm**.</span></span>

## <a name="record-receipt-of-goods"></a><span data-ttu-id="73c26-119">Registrera inleverans av varor</span><span class="sxs-lookup"><span data-stu-id="73c26-119">Record receipt of goods</span></span>
1. <span data-ttu-id="73c26-120">Välj **Ta emot** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="73c26-120">On the Action Pane, select **Receive**.</span></span>
2. <span data-ttu-id="73c26-121">Välj **produktinleverans**</span><span class="sxs-lookup"><span data-stu-id="73c26-121">Select **Product receipt**.</span></span> <span data-ttu-id="73c26-122">Fältet **Kvantitet** låter dig välja olika alternativ för den kvantitet som du vill ta emot.</span><span class="sxs-lookup"><span data-stu-id="73c26-122">The **Quantity** field allows you to select different options for the quantity that you want to receive.</span></span> <span data-ttu-id="73c26-123">Till exempel om en kvantitet tidigare har registrerats i lagerstället, kan du välja **registrerad kvantitet**.</span><span class="sxs-lookup"><span data-stu-id="73c26-123">For example, if a quantity has previously been registered in the warehouse, you can select **Registered quantity**.</span></span> <span data-ttu-id="73c26-124">Använd värdet **Beställd kvantitet** för det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="73c26-124">For this example, use the value **Ordered quantity**.</span></span>
3. <span data-ttu-id="73c26-125">Expandera valet **Översikt**.</span><span class="sxs-lookup"><span data-stu-id="73c26-125">Expand the **Overview** section.</span></span>
4. <span data-ttu-id="73c26-126">I fältet **Produktinleverans** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="73c26-126">In the **Product receipt** field, type any value.</span></span> <span data-ttu-id="73c26-127">Det här fältet används för att ange en referens som ska användas som verifikation för produktinleveransjournalen.</span><span class="sxs-lookup"><span data-stu-id="73c26-127">This field is used to enter a reference that will be used as voucher for the product receipt journal.</span></span>  
5. <span data-ttu-id="73c26-128">Expandera avsnittet **Rader**.</span><span class="sxs-lookup"><span data-stu-id="73c26-128">Expand the **Lines** section.</span></span>
6. <span data-ttu-id="73c26-129">Ställ in **kvantiteten** på 4.</span><span class="sxs-lookup"><span data-stu-id="73c26-129">Set **Quantity** to '4'.</span></span> <span data-ttu-id="73c26-130">Här kan du manuellt ange den kvantitet som har inlevererats för varje rad i ordern.</span><span class="sxs-lookup"><span data-stu-id="73c26-130">Here you are able to manually specify the quantity that is being received for each line on the order.</span></span>  
7. <span data-ttu-id="73c26-131">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="73c26-131">Select **OK**.</span></span> <span data-ttu-id="73c26-132">Varorna har nu registrerats som inlevererade på inköpsordern och en produktinleveransjournal har skapats som dokumentet för att återspegla detta.</span><span class="sxs-lookup"><span data-stu-id="73c26-132">The goods have now been recorded as received on the purchase order, and a product receipt journal has been created as document to reflect this.</span></span> <span data-ttu-id="73c26-133">Du kan använda åtgärden Produktinleverans om du vill granska journalerna som skapats med inköpsordern och se vad som har levererats och när.</span><span class="sxs-lookup"><span data-stu-id="73c26-133">You can use the Product receipt action to review the journals created with the purchase order, and see what was received, and when.</span></span>  

