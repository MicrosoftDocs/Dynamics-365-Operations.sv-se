---
title: Skapa en preliminär budget för offentliga sektorn
description: Du kan skapa preliminära budgetregisterposter för en specifik budgetmodell och dimensionsvärden.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BudgetTransaction, BudgetAccountStructureLookup, BudgetTransactionMultiPost
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 98968b0025ff5c3b9723dc6cc8a8eae799a4eb43
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1557198"
---
# <a name="create-a-preliminary-budget-for-public-sector"></a><span data-ttu-id="bba47-103">Skapa en preliminär budget för offentliga sektorn</span><span class="sxs-lookup"><span data-stu-id="bba47-103">Create a preliminary budget for Public sector</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="bba47-104">Du kan skapa preliminära budgetregisterposter för en specifik budgetmodell och dimensionsvärden.</span><span class="sxs-lookup"><span data-stu-id="bba47-104">You can create preliminary budget register entries for a specific budget model and dimension values.</span></span> <span data-ttu-id="bba47-105">När den verkliga budgeten har godkänts kan du skapa registerposter för ursprunglig budget.</span><span class="sxs-lookup"><span data-stu-id="bba47-105">After the actual budget is approved, you can create original budget register entries.</span></span> <span data-ttu-id="bba47-106">Den här proceduren har skapats med hjälp av data för demoföretaget PSUS i partitionen för den offentliga sektorn.</span><span class="sxs-lookup"><span data-stu-id="bba47-106">This procedure was created using the PSUS demo company data in the public sector partition.</span></span>

1. <span data-ttu-id="bba47-107">Gå till Budgetering > Budgetregisterposter.</span><span class="sxs-lookup"><span data-stu-id="bba47-107">Go to Budgeting > Budget register entries.</span></span>
2. <span data-ttu-id="bba47-108">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="bba47-108">Click New.</span></span>
3. <span data-ttu-id="bba47-109">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Budgetmodell.</span><span class="sxs-lookup"><span data-stu-id="bba47-109">In the Budget model field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="bba47-110">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="bba47-110">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="bba47-111">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Budgetkod.</span><span class="sxs-lookup"><span data-stu-id="bba47-111">In the Budget code field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="bba47-112">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="bba47-112">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="bba47-113">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Orsakskod.</span><span class="sxs-lookup"><span data-stu-id="bba47-113">In the Reason code field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="bba47-114">Klicka på önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="bba47-114">In the list, click the desired record.</span></span>
9. <span data-ttu-id="bba47-115">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="bba47-115">Click Save.</span></span>
10. <span data-ttu-id="bba47-116">Klicka på Lägg till rad.</span><span class="sxs-lookup"><span data-stu-id="bba47-116">Click Add line.</span></span>
    * <span data-ttu-id="bba47-117">Valfritt: om du vill ändra datumet från det i rubriken, ange ett annat datum.</span><span class="sxs-lookup"><span data-stu-id="bba47-117">Optional: If you want to change the date from the one in the header, enter a new date.</span></span> <span data-ttu-id="bba47-118">Detta datum bestämmer vilken räkenskapsperiod budgeten ska registreras i.</span><span class="sxs-lookup"><span data-stu-id="bba47-118">This date determines the fiscal period that the budget will be recorded to.</span></span> <span data-ttu-id="bba47-119">Vid visning av uppgifthandboken, fyll i de andra fälten och klicka på "Lås upp" överst på sidan.</span><span class="sxs-lookup"><span data-stu-id="bba47-119">When viewing the task guide, to fill out other fields, click Unlock at the top of the page.</span></span>  
11. <span data-ttu-id="bba47-120">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Kontostruktur.</span><span class="sxs-lookup"><span data-stu-id="bba47-120">In the Account structure field, click the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="bba47-121">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="bba47-121">In the list, find and select the desired record.</span></span>
13. <span data-ttu-id="bba47-122">Ange önskade värden i fältet Dimensionsvärden.</span><span class="sxs-lookup"><span data-stu-id="bba47-122">In the Dimension values field, specify the desired values.</span></span>
14. <span data-ttu-id="bba47-123">I fältet Belopp, ange ett tal.</span><span class="sxs-lookup"><span data-stu-id="bba47-123">In the Amount field, enter a number.</span></span>
    * <span data-ttu-id="bba47-124">Du kan även ange en beloppstyp.</span><span class="sxs-lookup"><span data-stu-id="bba47-124">You can also enter an amount type.</span></span>  
15. <span data-ttu-id="bba47-125">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Valuta.</span><span class="sxs-lookup"><span data-stu-id="bba47-125">In the Currency field, click the drop-down button to open the lookup.</span></span>
16. <span data-ttu-id="bba47-126">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="bba47-126">In the list, find and select the desired record.</span></span>
17. <span data-ttu-id="bba47-127">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="bba47-127">Click Save.</span></span>
18. <span data-ttu-id="bba47-128">Klicka på Uppdatera budgetsaldon.</span><span class="sxs-lookup"><span data-stu-id="bba47-128">Click Update budget balances.</span></span>
19. <span data-ttu-id="bba47-129">Klicka på Uppdatera.</span><span class="sxs-lookup"><span data-stu-id="bba47-129">Click Update.</span></span>
    * <span data-ttu-id="bba47-130">Klicka på Meddelandeinformation i det blå fältet att se resultaten för uppdateringen.</span><span class="sxs-lookup"><span data-stu-id="bba47-130">To see the results of the update, click Message details on the blue bar.</span></span>  

