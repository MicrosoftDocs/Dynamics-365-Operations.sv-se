---
title: Skapa en ursprunglig budget och sedan återföra preliminära budgetposter i den offentliga sektorn
description: Detta ämne ger information om hur du skapar och återför en ursprunglig budgetpost med hjälp av budgetmodells- och dimensionsvärden som har preliminära budgetbelopp.
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
ms.openlocfilehash: 0b11aeb377caf50808f661de25fcbbf90429d475
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5235075"
---
# <a name="create-an-original-budget-and-then-reverse-preliminary-budget-entries-in-the-public-sector"></a><span data-ttu-id="1d698-103">Skapa en ursprunglig budget och sedan återföra preliminära budgetposter i den offentliga sektorn</span><span class="sxs-lookup"><span data-stu-id="1d698-103">Create an original budget and then reverse preliminary budget entries in the public sector</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1d698-104">När du skapar en ursprunglig budgetpost och använder budgetmodellen och dimensionsvärden som innehåller preliminära budgetbelopp, kan de preliminära budgetbeloppen återföras.</span><span class="sxs-lookup"><span data-stu-id="1d698-104">When you create an original budget entry and use the budget model and dimension values that contain preliminary budget amounts, the preliminary budget amounts can be reversed.</span></span> <span data-ttu-id="1d698-105">Den här proceduren har skapats med hjälp av data för demoföretaget PSUS i partitionen för den offentliga sektorn.</span><span class="sxs-lookup"><span data-stu-id="1d698-105">This procedure was created using the PSUS demo company data in the public sector partition.</span></span>

1. <span data-ttu-id="1d698-106">Gå till Budgetering > Budgetregisterposter.</span><span class="sxs-lookup"><span data-stu-id="1d698-106">Go to Budgeting > Budget register entries.</span></span>
2. <span data-ttu-id="1d698-107">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="1d698-107">Click New.</span></span>
3. <span data-ttu-id="1d698-108">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Budgetmodell.</span><span class="sxs-lookup"><span data-stu-id="1d698-108">In the Budget model field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="1d698-109">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="1d698-109">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="1d698-110">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Budgetkod.</span><span class="sxs-lookup"><span data-stu-id="1d698-110">In the Budget code field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="1d698-111">Klicka på Ursprunglig budget i listan.</span><span class="sxs-lookup"><span data-stu-id="1d698-111">In the list, click Original budget.</span></span>
7. <span data-ttu-id="1d698-112">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="1d698-112">Click Save.</span></span>
8. <span data-ttu-id="1d698-113">Klicka på Lägg till rad.</span><span class="sxs-lookup"><span data-stu-id="1d698-113">Click Add line.</span></span>
9. <span data-ttu-id="1d698-114">Valfritt: om du vill ändra datumet från det i rubriken, ange ett annat datum.</span><span class="sxs-lookup"><span data-stu-id="1d698-114">Optional: If you want to change the date from the one in the header, enter a new date.</span></span> <span data-ttu-id="1d698-115">Detta datum bestämmer vilken räkenskapsperiod budgeten ska registreras i.</span><span class="sxs-lookup"><span data-stu-id="1d698-115">This date determines the fiscal period that the budget will be recorded to.</span></span>
10. <span data-ttu-id="1d698-116">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Kontostruktur.</span><span class="sxs-lookup"><span data-stu-id="1d698-116">In the Account structure field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="1d698-117">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="1d698-117">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="1d698-118">Ange önskade värden i fältet Dimensionsvärden.</span><span class="sxs-lookup"><span data-stu-id="1d698-118">In the Dimension values field, specify the desired values.</span></span>
13. <span data-ttu-id="1d698-119">I fältet Belopp, ange ett tal.</span><span class="sxs-lookup"><span data-stu-id="1d698-119">In the Amount field, enter a number.</span></span>
14. <span data-ttu-id="1d698-120">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Valuta.</span><span class="sxs-lookup"><span data-stu-id="1d698-120">In the Currency field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="1d698-121">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="1d698-121">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="1d698-122">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="1d698-122">Click Save.</span></span>
17. <span data-ttu-id="1d698-123">Klicka på Uppdatera budgetsaldon.</span><span class="sxs-lookup"><span data-stu-id="1d698-123">Click Update budget balances.</span></span>
    * <span data-ttu-id="1d698-124">Valfritt: du kan välja alternativet för att återföra preliminära budgetposter.</span><span class="sxs-lookup"><span data-stu-id="1d698-124">Optional: You can select the Reverse preliminary budget option.</span></span> <span data-ttu-id="1d698-125">Observera att du kan återföra alla preliminära budgetposter eller endast de preliminära budgetposter som har den budgetkod som du anger.</span><span class="sxs-lookup"><span data-stu-id="1d698-125">Note that you can reverse all preliminary budget entries, or only the preliminary budget entries that have the budget code that you specify.</span></span>  
    * <span data-ttu-id="1d698-126">Du kan göra ytterligare val genom att klicka på upplåsningsikonen högst upp på skärmen.</span><span class="sxs-lookup"><span data-stu-id="1d698-126">To make optional selections, click the Unlock icon at the top of the page.</span></span>  
18. <span data-ttu-id="1d698-127">Klicka på Uppdatera.</span><span class="sxs-lookup"><span data-stu-id="1d698-127">Click Update.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]