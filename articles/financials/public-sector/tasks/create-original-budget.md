---
title: Skapa en ursprunglig budget och sedan återföra preliminära budgetposter i den offentliga sektorn
description: När du skapar en ursprunglig budgetpost och använder budgetmodellen och dimensionsvärden som innehåller preliminära budgetbelopp, kan de preliminära budgetbeloppen återföras.
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
ms.openlocfilehash: 9d1c34ac2bd94196b7bad599e9aca7ed942ae9c8
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1557223"
---
# <a name="create-an-original-budget-and-then-reverse-preliminary-budget-entries-in-the-public-sector"></a><span data-ttu-id="f1d8f-103">Skapa en ursprunglig budget och sedan återföra preliminära budgetposter i den offentliga sektorn</span><span class="sxs-lookup"><span data-stu-id="f1d8f-103">Create an original budget and then reverse preliminary budget entries in the public sector</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f1d8f-104">När du skapar en ursprunglig budgetpost och använder budgetmodellen och dimensionsvärden som innehåller preliminära budgetbelopp, kan de preliminära budgetbeloppen återföras.</span><span class="sxs-lookup"><span data-stu-id="f1d8f-104">When you create an original budget entry and use the budget model and dimension values that contain preliminary budget amounts, the preliminary budget amounts can be reversed.</span></span> <span data-ttu-id="f1d8f-105">Den här proceduren har skapats med hjälp av data för demoföretaget PSUS i partitionen för den offentliga sektorn.</span><span class="sxs-lookup"><span data-stu-id="f1d8f-105">This procedure was created using the PSUS demo company data in the public sector partition.</span></span>

1. <span data-ttu-id="f1d8f-106">Gå till Budgetering > Budgetregisterposter.</span><span class="sxs-lookup"><span data-stu-id="f1d8f-106">Go to Budgeting > Budget register entries.</span></span>
2. <span data-ttu-id="f1d8f-107">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="f1d8f-107">Click New.</span></span>
3. <span data-ttu-id="f1d8f-108">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Budgetmodell.</span><span class="sxs-lookup"><span data-stu-id="f1d8f-108">In the Budget model field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="f1d8f-109">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="f1d8f-109">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="f1d8f-110">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Budgetkod.</span><span class="sxs-lookup"><span data-stu-id="f1d8f-110">In the Budget code field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="f1d8f-111">Klicka på Ursprunglig budget i listan.</span><span class="sxs-lookup"><span data-stu-id="f1d8f-111">In the list, click Original budget.</span></span>
7. <span data-ttu-id="f1d8f-112">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="f1d8f-112">Click Save.</span></span>
8. <span data-ttu-id="f1d8f-113">Klicka på Lägg till rad.</span><span class="sxs-lookup"><span data-stu-id="f1d8f-113">Click Add line.</span></span>
9. <span data-ttu-id="f1d8f-114">Valfritt: om du vill ändra datumet från det i rubriken, ange ett annat datum.</span><span class="sxs-lookup"><span data-stu-id="f1d8f-114">Optional: If you want to change the date from the one in the header, enter a new date.</span></span> <span data-ttu-id="f1d8f-115">Detta datum bestämmer vilken räkenskapsperiod budgeten ska registreras i.</span><span class="sxs-lookup"><span data-stu-id="f1d8f-115">This date determines the fiscal period that the budget will be recorded to.</span></span>
10. <span data-ttu-id="f1d8f-116">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Kontostruktur.</span><span class="sxs-lookup"><span data-stu-id="f1d8f-116">In the Account structure field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="f1d8f-117">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="f1d8f-117">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="f1d8f-118">Ange önskade värden i fältet Dimensionsvärden.</span><span class="sxs-lookup"><span data-stu-id="f1d8f-118">In the Dimension values field, specify the desired values.</span></span>
13. <span data-ttu-id="f1d8f-119">I fältet Belopp, ange ett tal.</span><span class="sxs-lookup"><span data-stu-id="f1d8f-119">In the Amount field, enter a number.</span></span>
14. <span data-ttu-id="f1d8f-120">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Valuta.</span><span class="sxs-lookup"><span data-stu-id="f1d8f-120">In the Currency field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="f1d8f-121">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="f1d8f-121">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="f1d8f-122">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="f1d8f-122">Click Save.</span></span>
17. <span data-ttu-id="f1d8f-123">Klicka på Uppdatera budgetsaldon.</span><span class="sxs-lookup"><span data-stu-id="f1d8f-123">Click Update budget balances.</span></span>
    * <span data-ttu-id="f1d8f-124">Valfritt: du kan välja alternativet för att återföra preliminära budgetposter.</span><span class="sxs-lookup"><span data-stu-id="f1d8f-124">Optional: You can select the Reverse preliminary budget option.</span></span> <span data-ttu-id="f1d8f-125">Observera att du kan återföra alla preliminära budgetposter eller endast de preliminära budgetposter som har den budgetkod som du anger.</span><span class="sxs-lookup"><span data-stu-id="f1d8f-125">Note that you can reverse all preliminary budget entries, or only the preliminary budget entries that have the budget code that you specify.</span></span>  
    * <span data-ttu-id="f1d8f-126">Du kan göra ytterligare val genom att klicka på upplåsningsikonen högst upp på skärmen.</span><span class="sxs-lookup"><span data-stu-id="f1d8f-126">To make optional selections, click the Unlock icon at the top of the page.</span></span>  
18. <span data-ttu-id="f1d8f-127">Klicka på Uppdatera.</span><span class="sxs-lookup"><span data-stu-id="f1d8f-127">Click Update.</span></span>

