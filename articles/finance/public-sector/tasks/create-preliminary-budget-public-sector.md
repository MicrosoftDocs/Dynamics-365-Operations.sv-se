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
ms.search.region: Global
ms.search.industry: Service industries
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 40371809f3855e57db4bc12f5466f7cef5cec600
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5235566"
---
# <a name="create-a-preliminary-budget-for-public-sector"></a><span data-ttu-id="23d74-103">Skapa en preliminär budget för offentliga sektorn</span><span class="sxs-lookup"><span data-stu-id="23d74-103">Create a preliminary budget for Public sector</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="23d74-104">Du kan skapa preliminära budgetregisterposter för en specifik budgetmodell och dimensionsvärden.</span><span class="sxs-lookup"><span data-stu-id="23d74-104">You can create preliminary budget register entries for a specific budget model and dimension values.</span></span> <span data-ttu-id="23d74-105">När den verkliga budgeten har godkänts kan du skapa registerposter för ursprunglig budget.</span><span class="sxs-lookup"><span data-stu-id="23d74-105">After the actual budget is approved, you can create original budget register entries.</span></span> <span data-ttu-id="23d74-106">Den här proceduren har skapats med hjälp av data för demoföretaget PSUS i partitionen för den offentliga sektorn.</span><span class="sxs-lookup"><span data-stu-id="23d74-106">This procedure was created using the PSUS demo company data in the public sector partition.</span></span>

1. <span data-ttu-id="23d74-107">Gå till Budgetering > Budgetregisterposter.</span><span class="sxs-lookup"><span data-stu-id="23d74-107">Go to Budgeting > Budget register entries.</span></span>
2. <span data-ttu-id="23d74-108">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="23d74-108">Click New.</span></span>
3. <span data-ttu-id="23d74-109">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Budgetmodell.</span><span class="sxs-lookup"><span data-stu-id="23d74-109">In the Budget model field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="23d74-110">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="23d74-110">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="23d74-111">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Budgetkod.</span><span class="sxs-lookup"><span data-stu-id="23d74-111">In the Budget code field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="23d74-112">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="23d74-112">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="23d74-113">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Orsakskod.</span><span class="sxs-lookup"><span data-stu-id="23d74-113">In the Reason code field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="23d74-114">Klicka på önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="23d74-114">In the list, click the desired record.</span></span>
9. <span data-ttu-id="23d74-115">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="23d74-115">Click Save.</span></span>
10. <span data-ttu-id="23d74-116">Klicka på Lägg till rad.</span><span class="sxs-lookup"><span data-stu-id="23d74-116">Click Add line.</span></span>
    * <span data-ttu-id="23d74-117">Valfritt: om du vill ändra datumet från det i rubriken, ange ett annat datum.</span><span class="sxs-lookup"><span data-stu-id="23d74-117">Optional: If you want to change the date from the one in the header, enter a new date.</span></span> <span data-ttu-id="23d74-118">Detta datum bestämmer vilken räkenskapsperiod budgeten ska registreras i.</span><span class="sxs-lookup"><span data-stu-id="23d74-118">This date determines the fiscal period that the budget will be recorded to.</span></span> <span data-ttu-id="23d74-119">Vid visning av uppgifthandboken, fyll i de andra fälten och klicka på "Lås upp" överst på sidan.</span><span class="sxs-lookup"><span data-stu-id="23d74-119">When viewing the task guide, to fill out other fields, click Unlock at the top of the page.</span></span>  
11. <span data-ttu-id="23d74-120">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Kontostruktur.</span><span class="sxs-lookup"><span data-stu-id="23d74-120">In the Account structure field, click the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="23d74-121">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="23d74-121">In the list, find and select the desired record.</span></span>
13. <span data-ttu-id="23d74-122">Ange önskade värden i fältet Dimensionsvärden.</span><span class="sxs-lookup"><span data-stu-id="23d74-122">In the Dimension values field, specify the desired values.</span></span>
14. <span data-ttu-id="23d74-123">I fältet Belopp, ange ett tal.</span><span class="sxs-lookup"><span data-stu-id="23d74-123">In the Amount field, enter a number.</span></span>
    * <span data-ttu-id="23d74-124">Du kan även ange en beloppstyp.</span><span class="sxs-lookup"><span data-stu-id="23d74-124">You can also enter an amount type.</span></span>  
15. <span data-ttu-id="23d74-125">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Valuta.</span><span class="sxs-lookup"><span data-stu-id="23d74-125">In the Currency field, click the drop-down button to open the lookup.</span></span>
16. <span data-ttu-id="23d74-126">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="23d74-126">In the list, find and select the desired record.</span></span>
17. <span data-ttu-id="23d74-127">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="23d74-127">Click Save.</span></span>
18. <span data-ttu-id="23d74-128">Klicka på Uppdatera budgetsaldon.</span><span class="sxs-lookup"><span data-stu-id="23d74-128">Click Update budget balances.</span></span>
19. <span data-ttu-id="23d74-129">Klicka på Uppdatera.</span><span class="sxs-lookup"><span data-stu-id="23d74-129">Click Update.</span></span>
    * <span data-ttu-id="23d74-130">Klicka på Meddelandeinformation i det blå fältet att se resultaten för uppdateringen.</span><span class="sxs-lookup"><span data-stu-id="23d74-130">To see the results of the update, click Message details on the blue bar.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]