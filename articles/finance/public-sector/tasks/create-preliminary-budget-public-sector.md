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
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 800b7009f023bd2a0d8437b81d82c0e9de770841
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2174384"
---
# <a name="create-a-preliminary-budget-for-public-sector"></a><span data-ttu-id="79a28-103">Skapa en preliminär budget för offentliga sektorn</span><span class="sxs-lookup"><span data-stu-id="79a28-103">Create a preliminary budget for Public sector</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="79a28-104">Du kan skapa preliminära budgetregisterposter för en specifik budgetmodell och dimensionsvärden.</span><span class="sxs-lookup"><span data-stu-id="79a28-104">You can create preliminary budget register entries for a specific budget model and dimension values.</span></span> <span data-ttu-id="79a28-105">När den verkliga budgeten har godkänts kan du skapa registerposter för ursprunglig budget.</span><span class="sxs-lookup"><span data-stu-id="79a28-105">After the actual budget is approved, you can create original budget register entries.</span></span> <span data-ttu-id="79a28-106">Den här proceduren har skapats med hjälp av data för demoföretaget PSUS i partitionen för den offentliga sektorn.</span><span class="sxs-lookup"><span data-stu-id="79a28-106">This procedure was created using the PSUS demo company data in the public sector partition.</span></span>

1. <span data-ttu-id="79a28-107">Gå till Budgetering > Budgetregisterposter.</span><span class="sxs-lookup"><span data-stu-id="79a28-107">Go to Budgeting > Budget register entries.</span></span>
2. <span data-ttu-id="79a28-108">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="79a28-108">Click New.</span></span>
3. <span data-ttu-id="79a28-109">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Budgetmodell.</span><span class="sxs-lookup"><span data-stu-id="79a28-109">In the Budget model field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="79a28-110">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="79a28-110">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="79a28-111">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Budgetkod.</span><span class="sxs-lookup"><span data-stu-id="79a28-111">In the Budget code field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="79a28-112">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="79a28-112">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="79a28-113">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Orsakskod.</span><span class="sxs-lookup"><span data-stu-id="79a28-113">In the Reason code field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="79a28-114">Klicka på önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="79a28-114">In the list, click the desired record.</span></span>
9. <span data-ttu-id="79a28-115">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="79a28-115">Click Save.</span></span>
10. <span data-ttu-id="79a28-116">Klicka på Lägg till rad.</span><span class="sxs-lookup"><span data-stu-id="79a28-116">Click Add line.</span></span>
    * <span data-ttu-id="79a28-117">Valfritt: om du vill ändra datumet från det i rubriken, ange ett annat datum.</span><span class="sxs-lookup"><span data-stu-id="79a28-117">Optional: If you want to change the date from the one in the header, enter a new date.</span></span> <span data-ttu-id="79a28-118">Detta datum bestämmer vilken räkenskapsperiod budgeten ska registreras i.</span><span class="sxs-lookup"><span data-stu-id="79a28-118">This date determines the fiscal period that the budget will be recorded to.</span></span> <span data-ttu-id="79a28-119">Vid visning av uppgifthandboken, fyll i de andra fälten och klicka på "Lås upp" överst på sidan.</span><span class="sxs-lookup"><span data-stu-id="79a28-119">When viewing the task guide, to fill out other fields, click Unlock at the top of the page.</span></span>  
11. <span data-ttu-id="79a28-120">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Kontostruktur.</span><span class="sxs-lookup"><span data-stu-id="79a28-120">In the Account structure field, click the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="79a28-121">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="79a28-121">In the list, find and select the desired record.</span></span>
13. <span data-ttu-id="79a28-122">Ange önskade värden i fältet Dimensionsvärden.</span><span class="sxs-lookup"><span data-stu-id="79a28-122">In the Dimension values field, specify the desired values.</span></span>
14. <span data-ttu-id="79a28-123">I fältet Belopp, ange ett tal.</span><span class="sxs-lookup"><span data-stu-id="79a28-123">In the Amount field, enter a number.</span></span>
    * <span data-ttu-id="79a28-124">Du kan även ange en beloppstyp.</span><span class="sxs-lookup"><span data-stu-id="79a28-124">You can also enter an amount type.</span></span>  
15. <span data-ttu-id="79a28-125">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Valuta.</span><span class="sxs-lookup"><span data-stu-id="79a28-125">In the Currency field, click the drop-down button to open the lookup.</span></span>
16. <span data-ttu-id="79a28-126">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="79a28-126">In the list, find and select the desired record.</span></span>
17. <span data-ttu-id="79a28-127">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="79a28-127">Click Save.</span></span>
18. <span data-ttu-id="79a28-128">Klicka på Uppdatera budgetsaldon.</span><span class="sxs-lookup"><span data-stu-id="79a28-128">Click Update budget balances.</span></span>
19. <span data-ttu-id="79a28-129">Klicka på Uppdatera.</span><span class="sxs-lookup"><span data-stu-id="79a28-129">Click Update.</span></span>
    * <span data-ttu-id="79a28-130">Klicka på Meddelandeinformation i det blå fältet att se resultaten för uppdateringen.</span><span class="sxs-lookup"><span data-stu-id="79a28-130">To see the results of the update, click Message details on the blue bar.</span></span>  

