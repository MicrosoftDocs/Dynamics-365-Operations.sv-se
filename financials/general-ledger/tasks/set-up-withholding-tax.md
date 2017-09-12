--- 
title: "Ställ in källskatt"
description: "Källskatt är en skatt på leverantörer som inte skapar momstransaktioner."
author: twheeloc
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: dc4c0745235052cb4145bc7083fef1a88c8bb5c9
ms.contentlocale: sv-se
ms.lasthandoff: 08/29/2017

---
# <a name="set-up-withholding-tax"></a><span data-ttu-id="ab8a8-103">Ställ in källskatt</span><span class="sxs-lookup"><span data-stu-id="ab8a8-103">Set up withholding tax</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ab8a8-104">Källskatt är en skatt på leverantörer som inte skapar momstransaktioner.</span><span class="sxs-lookup"><span data-stu-id="ab8a8-104">Withholding tax is a tax on vendors that does not create sales tax transactions.</span></span> <span data-ttu-id="ab8a8-105">Källskatt som beräknats på leverantörsbetalningar är en skuld.</span><span class="sxs-lookup"><span data-stu-id="ab8a8-105">Withholding tax that is calculated on vendor payments is a liability.</span></span> <span data-ttu-id="ab8a8-106">Därför är endast balansräkningskonton eller skuldkonton giltiga konton för bokföring av källskatt.</span><span class="sxs-lookup"><span data-stu-id="ab8a8-106">Therefore, only balance sheet accounts or liability accounts are valid accounts for posting withholding tax.</span></span> <span data-ttu-id="ab8a8-107">Den här uppgifthandboken visar hur du ställer in källskatt.</span><span class="sxs-lookup"><span data-stu-id="ab8a8-107">This task guide demonstrates how to set up withholding tax.</span></span>

1. <span data-ttu-id="ab8a8-108">Gå till Skatt > Indirekta skatter > Källskatt > Källskattekoder.</span><span class="sxs-lookup"><span data-stu-id="ab8a8-108">Go to Tax > Indirect taxes > Withholding tax > Withholding tax codes.</span></span>
2. <span data-ttu-id="ab8a8-109">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="ab8a8-109">Click New.</span></span>
3. <span data-ttu-id="ab8a8-110">I fältet Källskattekod, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="ab8a8-110">In the Withholding tax code field, type a value.</span></span>
4. <span data-ttu-id="ab8a8-111">Ange namnet på källskattekoden i fältet Källskattenamn.</span><span class="sxs-lookup"><span data-stu-id="ab8a8-111">In the Withholding tax name field, enter the name of the withholding tax code.</span></span>
5. <span data-ttu-id="ab8a8-112">Välj huvudkontot för bokföring av källskatteskulder i huvudkontofältet.</span><span class="sxs-lookup"><span data-stu-id="ab8a8-112">In the Main account field, select the main account for posting the withholding tax liability.</span></span>
6. <span data-ttu-id="ab8a8-113">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="ab8a8-113">Click Save.</span></span>
7. <span data-ttu-id="ab8a8-114">Klicka på Värden.</span><span class="sxs-lookup"><span data-stu-id="ab8a8-114">Click Values.</span></span>
8. <span data-ttu-id="ab8a8-115">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="ab8a8-115">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="ab8a8-116">Ange en procentsats som används för beräkning av källskatten i fältet Värde.</span><span class="sxs-lookup"><span data-stu-id="ab8a8-116">In the Value field, enter a percentage used for the calculation of the withholding tax.</span></span>
10. <span data-ttu-id="ab8a8-117">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="ab8a8-117">Click Save.</span></span>
11. <span data-ttu-id="ab8a8-118">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="ab8a8-118">Close the page.</span></span>
12. <span data-ttu-id="ab8a8-119">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="ab8a8-119">Click Save.</span></span>
13. <span data-ttu-id="ab8a8-120">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="ab8a8-120">Close the page.</span></span>
14. <span data-ttu-id="ab8a8-121">Gå till Skatt > Indirekta skatter > Källskatt > Källskattegrupper.</span><span class="sxs-lookup"><span data-stu-id="ab8a8-121">Go to Tax > Indirect taxes > Withholding tax > Withholding tax groups.</span></span>
15. <span data-ttu-id="ab8a8-122">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="ab8a8-122">Click New.</span></span>
16. <span data-ttu-id="ab8a8-123">Ange ID på källskattegruppen i fältet Källskattegrupp.</span><span class="sxs-lookup"><span data-stu-id="ab8a8-123">In the Withholding tax group field, enter the identifier of the withholding tax group.</span></span>
17. <span data-ttu-id="ab8a8-124">Ange namn på källskattegruppen i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="ab8a8-124">In the Description field, enter the name of the withholding tax group.</span></span>
18. <span data-ttu-id="ab8a8-125">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="ab8a8-125">In the list, mark the selected row.</span></span>
19. <span data-ttu-id="ab8a8-126">Välj källskattekoden i fältet Källskattekod.</span><span class="sxs-lookup"><span data-stu-id="ab8a8-126">In the Withholding tax code field, select the withholding tax code.</span></span>
20. <span data-ttu-id="ab8a8-127">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="ab8a8-127">In the list, click the link in the selected row.</span></span>
21. <span data-ttu-id="ab8a8-128">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="ab8a8-128">Click Save.</span></span>


