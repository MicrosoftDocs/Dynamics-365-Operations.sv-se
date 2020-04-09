---
title: Skapa momstransaktioner i dokument
description: Moms på dokument beräknas genom att ange en momsgrupp, och en artikelmomsgrupp på dokument.
author: twheeloc
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, TaxTmpWorkTrans
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bdc4b5c31d9a478a5226ae6b5e8c776de3b661dd
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3144845"
---
# <a name="create-sales-tax-transactions-on-documents"></a><span data-ttu-id="d54ef-103">Skapa momstransaktioner i dokument</span><span class="sxs-lookup"><span data-stu-id="d54ef-103">Create sales tax transactions on documents</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d54ef-104">Moms på dokument beräknas genom att ange en momsgrupp, och en artikelmomsgrupp på dokument.</span><span class="sxs-lookup"><span data-stu-id="d54ef-104">Sales tax on documents is calculated by providing a Sales tax group and an Item sales tax group on document lines.</span></span> <span data-ttu-id="d54ef-105">Dessa får sin standard från huvuddata men kan ändras manuellt om det behövs.</span><span class="sxs-lookup"><span data-stu-id="d54ef-105">These default from master data but can be changed manually if necessary.</span></span> <span data-ttu-id="d54ef-106">Den beräknade momsen kan kontrolleras på en rad och dokumentnivå.</span><span class="sxs-lookup"><span data-stu-id="d54ef-106">The calculated sales tax can be checked on a line and document level.</span></span> <span data-ttu-id="d54ef-107">I den här uppgiften används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="d54ef-107">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="d54ef-108">Gå till Leverantörsreskontra > Order > Alla försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="d54ef-108">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="d54ef-109">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="d54ef-109">Click New.</span></span>
3. <span data-ttu-id="d54ef-110">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Kundkonto.</span><span class="sxs-lookup"><span data-stu-id="d54ef-110">In the Customer account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="d54ef-111">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="d54ef-111">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="d54ef-112">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="d54ef-112">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="d54ef-113">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="d54ef-113">Click OK.</span></span>
7. <span data-ttu-id="d54ef-114">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="d54ef-114">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="d54ef-115">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="d54ef-115">In the Item number field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="d54ef-116">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="d54ef-116">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="d54ef-117">Ange ett tal i fältet Enhetspris.</span><span class="sxs-lookup"><span data-stu-id="d54ef-117">In the Unit price field, enter a number.</span></span>
11. <span data-ttu-id="d54ef-118">Expandera eller dölj avsnittet Raddetaljer.</span><span class="sxs-lookup"><span data-stu-id="d54ef-118">Expand or collapse the Line details section.</span></span>
12. <span data-ttu-id="d54ef-119">Klicka på fliken Inställningar.</span><span class="sxs-lookup"><span data-stu-id="d54ef-119">Click the Setup tab.</span></span>
13. <span data-ttu-id="d54ef-120">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelmomsgrupp.</span><span class="sxs-lookup"><span data-stu-id="d54ef-120">In the Item sales tax group field, click the drop-down button to open the lookup.</span></span>
14. <span data-ttu-id="d54ef-121">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="d54ef-121">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="d54ef-122">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="d54ef-122">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="d54ef-123">Klicka på Ekonomi.</span><span class="sxs-lookup"><span data-stu-id="d54ef-123">Click Financials.</span></span>
17. <span data-ttu-id="d54ef-124">Klicka på Moms.</span><span class="sxs-lookup"><span data-stu-id="d54ef-124">Click Sales tax.</span></span>
18. <span data-ttu-id="d54ef-125">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="d54ef-125">Click OK.</span></span>
19. <span data-ttu-id="d54ef-126">Klicka på Lägg till rad.</span><span class="sxs-lookup"><span data-stu-id="d54ef-126">Click Add line.</span></span>
20. <span data-ttu-id="d54ef-127">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="d54ef-127">In the list, mark the selected row.</span></span>
21. <span data-ttu-id="d54ef-128">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="d54ef-128">In the Item number field, click the drop-down button to open the lookup.</span></span>
22. <span data-ttu-id="d54ef-129">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="d54ef-129">In the list, find and select the desired record.</span></span>
23. <span data-ttu-id="d54ef-130">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="d54ef-130">In the list, click the link in the selected row.</span></span>
24. <span data-ttu-id="d54ef-131">Ange ett tal i fältet Enhetspris.</span><span class="sxs-lookup"><span data-stu-id="d54ef-131">In the Unit price field, enter a number.</span></span>
25. <span data-ttu-id="d54ef-132">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelmomsgrupp.</span><span class="sxs-lookup"><span data-stu-id="d54ef-132">In the Item sales tax group field, click the drop-down button to open the lookup.</span></span>
26. <span data-ttu-id="d54ef-133">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="d54ef-133">In the list, find and select the desired record.</span></span>
27. <span data-ttu-id="d54ef-134">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="d54ef-134">In the list, click the link in the selected row.</span></span>
28. <span data-ttu-id="d54ef-135">Klicka på Sälj i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="d54ef-135">On the Action Pane, click Sell.</span></span>
29. <span data-ttu-id="d54ef-136">Klicka på Moms.</span><span class="sxs-lookup"><span data-stu-id="d54ef-136">Click Sales tax.</span></span>
30. <span data-ttu-id="d54ef-137">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="d54ef-137">Click OK.</span></span>

