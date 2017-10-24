--- 
title: "Skapa en inköpsorder som omfattas av budget"
description: "Använd den här proceduren för att skapa en inköpsorder som ska kontrolleras med avseende budget."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 7cc024caa54db6629a1e573df295fe8333996647
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-purchase-order-governed-by-budget"></a><span data-ttu-id="50f28-103">Skapa en inköpsorder som omfattas av budget</span><span class="sxs-lookup"><span data-stu-id="50f28-103">Create a purchase order governed by budget</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="50f28-104">Använd den här proceduren för att skapa en inköpsorder som ska kontrolleras med avseende budget.</span><span class="sxs-lookup"><span data-stu-id="50f28-104">Use this procedure to create a purchase order that is checked for available budget.</span></span> <span data-ttu-id="50f28-105">I den här inspelningen används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="50f28-105">This recording uses the USMF demo data company.</span></span>


## <a name="review-the-budget-control-configuration"></a><span data-ttu-id="50f28-106">Granska budgetkontrollkonfigurationen</span><span class="sxs-lookup"><span data-stu-id="50f28-106">Review the budget control configuration</span></span>
1. <span data-ttu-id="50f28-107">Gå till Budgetering > Inställningar > Budgetkontroll > Budgetkontrollkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="50f28-107">Go to Budgeting > Setup > Budget control > Budget control configuration.</span></span>
2. <span data-ttu-id="50f28-108">Klicka på fliken Budgetmedel är tillgängliga.</span><span class="sxs-lookup"><span data-stu-id="50f28-108">Click the Budget funds available tab.</span></span>
3. <span data-ttu-id="50f28-109">Klicka på fliken Dokument och journaler.</span><span class="sxs-lookup"><span data-stu-id="50f28-109">Click the Documents and journals tab.</span></span>
4. <span data-ttu-id="50f28-110">Klicka på fliken Definiera budgetkontrollregler.</span><span class="sxs-lookup"><span data-stu-id="50f28-110">Click the Define budget control rules tab.</span></span>
5. <span data-ttu-id="50f28-111">Klicka på fliken Definiera budgetgrupper.</span><span class="sxs-lookup"><span data-stu-id="50f28-111">Click the Define budget groups tab.</span></span>
6. <span data-ttu-id="50f28-112">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="50f28-112">Close the page.</span></span>

## <a name="create-the-purchase-order-header"></a><span data-ttu-id="50f28-113">Skapa inköpsorderrubriken</span><span class="sxs-lookup"><span data-stu-id="50f28-113">Create the purchase order header</span></span>
1. <span data-ttu-id="50f28-114">Gå till Anskaffning och källa > Inköpsorder > Alla inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="50f28-114">Go to Procurement and sourcing > Purchase orders > All purchase orders.</span></span>
2. <span data-ttu-id="50f28-115">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="50f28-115">Click New.</span></span>
3. <span data-ttu-id="50f28-116">Ange eller välj ett värde i fältet Leverantörskonto.</span><span class="sxs-lookup"><span data-stu-id="50f28-116">In the Vendor account field, enter or select a value.</span></span>
4. <span data-ttu-id="50f28-117">Expandera avsnittet Allmänt.</span><span class="sxs-lookup"><span data-stu-id="50f28-117">Expand the General section.</span></span>
5. <span data-ttu-id="50f28-118">Ställ in datumet i fältet Redovisning till "2016-01-01".</span><span class="sxs-lookup"><span data-stu-id="50f28-118">In the Accounting date field, set the date to '2016-01-01'.</span></span>
6. <span data-ttu-id="50f28-119">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="50f28-119">Click OK.</span></span>

## <a name="add-a-purchase-order-line"></a><span data-ttu-id="50f28-120">Lägg till en inköpsorderrad</span><span class="sxs-lookup"><span data-stu-id="50f28-120">Add a purchase order line</span></span>
1. <span data-ttu-id="50f28-121">Ange eller välj ett värde i fältet Anskaffningskategori.</span><span class="sxs-lookup"><span data-stu-id="50f28-121">In the Procurement category field, enter or select a value.</span></span>
2. <span data-ttu-id="50f28-122">Ställ in kvantiteten till 2.</span><span class="sxs-lookup"><span data-stu-id="50f28-122">Set Quantity to '2'.</span></span>
3. <span data-ttu-id="50f28-123">Ange eller välj ett värde i fältet Enhet.</span><span class="sxs-lookup"><span data-stu-id="50f28-123">In the Unit field, enter or select a value.</span></span>
4. <span data-ttu-id="50f28-124">Ställ in Enhetspris till "10 000".</span><span class="sxs-lookup"><span data-stu-id="50f28-124">Set Unit price to '10000'.</span></span>
5. <span data-ttu-id="50f28-125">Klicka på Ekonomi.</span><span class="sxs-lookup"><span data-stu-id="50f28-125">Click Financials.</span></span>
6. <span data-ttu-id="50f28-126">Klicka på Fördela belopp.</span><span class="sxs-lookup"><span data-stu-id="50f28-126">Click Distribute amounts.</span></span>
7. <span data-ttu-id="50f28-127">Ange värdet "601300-001-023--" i fältet Redovisningskonto.</span><span class="sxs-lookup"><span data-stu-id="50f28-127">In the Ledger account field, specify the value '601300-001-023--'.</span></span>
8. <span data-ttu-id="50f28-128">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="50f28-128">Close the page.</span></span>

## <a name="perform-budget-checking"></a><span data-ttu-id="50f28-129">Utför budgetkontroll</span><span class="sxs-lookup"><span data-stu-id="50f28-129">Perform budget checking</span></span>
1. <span data-ttu-id="50f28-130">Klicka på Ekonomi.</span><span class="sxs-lookup"><span data-stu-id="50f28-130">Click Financials.</span></span>
2. <span data-ttu-id="50f28-131">Klicka på Utför budgetkontroll.</span><span class="sxs-lookup"><span data-stu-id="50f28-131">Click Perform budget checking.</span></span>
3. <span data-ttu-id="50f28-132">Klicka på Ekonomi.</span><span class="sxs-lookup"><span data-stu-id="50f28-132">Click Financials.</span></span>
4. <span data-ttu-id="50f28-133">Klicka på Fel eller varningar från budgetkontroll.</span><span class="sxs-lookup"><span data-stu-id="50f28-133">Click Budget check errors or warnings.</span></span>
5. <span data-ttu-id="50f28-134">Klicka på Stäng.</span><span class="sxs-lookup"><span data-stu-id="50f28-134">Click Close.</span></span>


