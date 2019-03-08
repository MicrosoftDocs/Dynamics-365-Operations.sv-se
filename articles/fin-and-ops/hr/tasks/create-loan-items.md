---
title: Skapa låneartiklar
description: Låneartiklar är poster som gör det enklare att spåra fysiska artiklar, till exempel telefoner eller datorer, som ditt företag lånar ut till arbetare.
author: kherr75
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HcmLoanType, DefaultDashboard, HcmLoanItem, HcmWorkerLookUp
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e17005bda302c58f5a6560fe9c4eda04e918c92f
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "341843"
---
# <a name="create-loan-items"></a><span data-ttu-id="48be4-103">Skapa låneartiklar</span><span class="sxs-lookup"><span data-stu-id="48be4-103">Create loan items</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="48be4-104">Låneartiklar är poster som gör det enklare att spåra fysiska artiklar, till exempel telefoner eller datorer, som ditt företag lånar ut till arbetare.</span><span class="sxs-lookup"><span data-stu-id="48be4-104">Loan items are records that help you track physical items, such as phones or computers, that your company lends to workers.</span></span> <span data-ttu-id="48be4-105">Varje fysisk artikel måste ha en motsvarande låneartikel.</span><span class="sxs-lookup"><span data-stu-id="48be4-105">Each physical item must have a corresponding loan item.</span></span> <span data-ttu-id="48be4-106">Varje låneartikelpost bör beskriva vad som lånas ut, vem som är ansvarig för lånet och antalet dagar som artikeln kan lånas ut.</span><span class="sxs-lookup"><span data-stu-id="48be4-106">Each loan item record should describe what is being loaned, who is responsible for the loan, and the number of days the item can be on loan.</span></span> <span data-ttu-id="48be4-107">Du kan skapa flera låneartiklar samtidigt, till exempel nycklar, passerkort eller uniformer.</span><span class="sxs-lookup"><span data-stu-id="48be4-107">You can create multiple loan items, such as keys, access cards, or uniforms, at the same time.</span></span> <span data-ttu-id="48be4-108">Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.</span><span class="sxs-lookup"><span data-stu-id="48be4-108">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-loan-types"></a><span data-ttu-id="48be4-109">Skapa lånetyper</span><span class="sxs-lookup"><span data-stu-id="48be4-109">Create Loan types</span></span>
1. <span data-ttu-id="48be4-110">Gå till Personal > Arbetare > Låneartiklar > Lånetyper.</span><span class="sxs-lookup"><span data-stu-id="48be4-110">Go to Human resources > Workers > Loan items > Loan types.</span></span>
2. <span data-ttu-id="48be4-111">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="48be4-111">Click New.</span></span>
3. <span data-ttu-id="48be4-112">Ange ett värde i fältet Lånetyp.</span><span class="sxs-lookup"><span data-stu-id="48be4-112">In the Loan type field, type a value.</span></span>
4. <span data-ttu-id="48be4-113">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="48be4-113">In the Description field, type a value.</span></span>
5. <span data-ttu-id="48be4-114">Ange det antal dagar med vilket artiklar som tilldelats till den här lånetypen får ha förfallit.</span><span class="sxs-lookup"><span data-stu-id="48be4-114">Enter the number of days that items assigned to this loan type can be overdue.</span></span> 
6. <span data-ttu-id="48be4-115">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="48be4-115">Click Save.</span></span>
7. <span data-ttu-id="48be4-116">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="48be4-116">Close the page.</span></span>
8. <span data-ttu-id="48be4-117">Uppdatera sidan.</span><span class="sxs-lookup"><span data-stu-id="48be4-117">Refresh the page.</span></span>

## <a name="create-loan-items"></a><span data-ttu-id="48be4-118">Skapa låneartiklar</span><span class="sxs-lookup"><span data-stu-id="48be4-118">Create Loan items</span></span>
1. <span data-ttu-id="48be4-119">Gå till Personal > Arbetare > Låneartiklar > Låneartiklar.</span><span class="sxs-lookup"><span data-stu-id="48be4-119">Go to Human resources > Workers > Loan items > Loan items.</span></span>
2. <span data-ttu-id="48be4-120">Klicka på Skapa flera låneartiklar.</span><span class="sxs-lookup"><span data-stu-id="48be4-120">Click Create loan items.</span></span>
3. <span data-ttu-id="48be4-121">I kvant. fältet anger du ett tal.</span><span class="sxs-lookup"><span data-stu-id="48be4-121">In the Qty. field, enter a number.</span></span>
4. <span data-ttu-id="48be4-122">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="48be4-122">In the Description field, type a value.</span></span>
5. <span data-ttu-id="48be4-123">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Lånetyp.</span><span class="sxs-lookup"><span data-stu-id="48be4-123">In the Loan type field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="48be4-124">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="48be4-124">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="48be4-125">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="48be4-125">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="48be4-126">Ange det antal dagar som artikeln kan lånas ut.</span><span class="sxs-lookup"><span data-stu-id="48be4-126">Enter the number of days the item can be on loan.</span></span>
    * <span data-ttu-id="48be4-127">Standardvärdet i fältet Planerad retur på sidan Lånad utrustning beräknas som dagens datum plus det här numret.</span><span class="sxs-lookup"><span data-stu-id="48be4-127">The default value for the Planned return field on the Loaned equipment page is calculated as the current date plus this number.</span></span>  
9. <span data-ttu-id="48be4-128">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Ansvarig person.</span><span class="sxs-lookup"><span data-stu-id="48be4-128">In the Person in charge field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="48be4-129">Klicka på Välj.</span><span class="sxs-lookup"><span data-stu-id="48be4-129">Click Select.</span></span>
11. <span data-ttu-id="48be4-130">Du måste ange ett nummer i fältet Startvärde.</span><span class="sxs-lookup"><span data-stu-id="48be4-130">In the Starting value field, enter a number.</span></span>
12. <span data-ttu-id="48be4-131">Ange ett nummer i fältet Intervall.</span><span class="sxs-lookup"><span data-stu-id="48be4-131">In the Interval field, enter a number.</span></span>
13. <span data-ttu-id="48be4-132">Ange ett värde i fältet Format.</span><span class="sxs-lookup"><span data-stu-id="48be4-132">In the Format field, type a value.</span></span>
    * <span data-ttu-id="48be4-133">Om det högsta startnumret för en låneartikel är 10 anger du till exempel två nummersymboler i fältet Format.</span><span class="sxs-lookup"><span data-stu-id="48be4-133">For example, if the starting number for a loan item is 10, enter two number symbols symbols in the Format field.</span></span>  
14. <span data-ttu-id="48be4-134">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="48be4-134">Click OK.</span></span>
15. <span data-ttu-id="48be4-135">Uppdatera sidan.</span><span class="sxs-lookup"><span data-stu-id="48be4-135">Refresh the page.</span></span>

