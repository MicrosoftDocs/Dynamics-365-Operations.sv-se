--- 
title: "Ställ in policyer för lagerarbete "
description: "Lagerställeprocesser inkluderar inte alltid lagerarbete."
author: johanhoffmann
manager: AnnBe
ms.date: 06/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: b7d579ca7e2b9ca8cbead74b2c2ababfd142f171
ms.contentlocale: sv-se
ms.lasthandoff: 08/29/2017

---
# <a name="set-up-warehouse-work-policies"></a><span data-ttu-id="8a7fe-103">Ställ in policyer för lagerarbete </span><span class="sxs-lookup"><span data-stu-id="8a7fe-103">Set up warehouse work policies</span></span> 

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="8a7fe-104">Lagerställeprocesser inkluderar inte alltid lagerarbete.</span><span class="sxs-lookup"><span data-stu-id="8a7fe-104">Warehouse processes don’t always include warehouse work.</span></span> <span data-ttu-id="8a7fe-105">Genom att definiera en arbetspolicy kan du förhindra skapande av arbete för råmaterialhämtning och inlagring av färdiga varor för en uppsättning av produkter på specifika platser.</span><span class="sxs-lookup"><span data-stu-id="8a7fe-105">By defining a work policy, you can prevent the creation of work for raw material picking and put-away of finished goods for a set of products at specific locations.</span></span> <span data-ttu-id="8a7fe-106">Det USMF-demonstrationsdataföretag användes för att skapa den här registreringen.</span><span class="sxs-lookup"><span data-stu-id="8a7fe-106">The USMF demo data company was used to create this recording.</span></span> <span data-ttu-id="8a7fe-107">Den här uppgiftsguiden kräver Dynamics AX program 7.0.1 eller senare.</span><span class="sxs-lookup"><span data-stu-id="8a7fe-107">This task guide requires Dynamics AX application 7.0.1 or later.</span></span>

1. <span data-ttu-id="8a7fe-108">Gå till Lagerstyrning > Inställningar > Arbete > Arbetspolicyer.</span><span class="sxs-lookup"><span data-stu-id="8a7fe-108">Go to Warehouse management > Setup > Work > Work policies.</span></span>
2. <span data-ttu-id="8a7fe-109">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="8a7fe-109">Click New.</span></span>
3. <span data-ttu-id="8a7fe-110">Skriv in "Inget inlagrat arbete" i fältet Namn på arbetspolicy.</span><span class="sxs-lookup"><span data-stu-id="8a7fe-110">In the Work policy name field, type 'No put-away work'.</span></span>
4. <span data-ttu-id="8a7fe-111">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="8a7fe-111">Click Save.</span></span>
5. <span data-ttu-id="8a7fe-112">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="8a7fe-112">Click Add.</span></span>
6. <span data-ttu-id="8a7fe-113">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="8a7fe-113">In the list, mark the selected row.</span></span>
7. <span data-ttu-id="8a7fe-114">Skriv in "Plats för slutförda varor" i fältet Typ av arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="8a7fe-114">In the Work order type field, select 'Finished goods put away'.</span></span>
8. <span data-ttu-id="8a7fe-115">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="8a7fe-115">Click Add.</span></span>
9. <span data-ttu-id="8a7fe-116">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="8a7fe-116">In the list, mark the selected row.</span></span>
10. <span data-ttu-id="8a7fe-117">Välj ”Plats för samprodukt och biprodukt” i fältet Typ arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="8a7fe-117">In the Work order type field, select 'Co-product and by-product put away'.</span></span>
11. <span data-ttu-id="8a7fe-118">Visa avsnittet Lagerplatser.</span><span class="sxs-lookup"><span data-stu-id="8a7fe-118">Expand the Inventory locations section.</span></span>
12. <span data-ttu-id="8a7fe-119">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="8a7fe-119">Click Add.</span></span>
13. <span data-ttu-id="8a7fe-120">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="8a7fe-120">In the list, mark the selected row.</span></span>
14. <span data-ttu-id="8a7fe-121">Ange ”51" i lagerställets lista.</span><span class="sxs-lookup"><span data-stu-id="8a7fe-121">In the Warehouse list, enter '51'.</span></span>
15. <span data-ttu-id="8a7fe-122">Ange eller välj "001" i fältet Plats.</span><span class="sxs-lookup"><span data-stu-id="8a7fe-122">In the Location field, enter or select '001'.</span></span>
16. <span data-ttu-id="8a7fe-123">Expandera avsnittet Produkter.</span><span class="sxs-lookup"><span data-stu-id="8a7fe-123">Expand the Products section.</span></span>
17. <span data-ttu-id="8a7fe-124">Välj "Markerad" i fältet Produktval.</span><span class="sxs-lookup"><span data-stu-id="8a7fe-124">In the Product selection field, select 'Selected'.</span></span>
18. <span data-ttu-id="8a7fe-125">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="8a7fe-125">Click Add.</span></span>
19. <span data-ttu-id="8a7fe-126">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="8a7fe-126">In the list, mark the selected row.</span></span>
20. <span data-ttu-id="8a7fe-127">Ange eller välj "L0101" i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="8a7fe-127">In the Item number field, enter or select 'L0101'.</span></span>
21. <span data-ttu-id="8a7fe-128">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="8a7fe-128">Click Save.</span></span>


