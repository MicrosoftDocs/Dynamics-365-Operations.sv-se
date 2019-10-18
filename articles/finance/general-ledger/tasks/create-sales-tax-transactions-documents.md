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
ms.openlocfilehash: 653b93744f5b891655cade0cb669d34179fca9cd
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2186151"
---
# <a name="create-sales-tax-transactions-on-documents"></a><span data-ttu-id="4e9bd-103">Skapa momstransaktioner i dokument</span><span class="sxs-lookup"><span data-stu-id="4e9bd-103">Create sales tax transactions on documents</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4e9bd-104">Moms på dokument beräknas genom att ange en momsgrupp, och en artikelmomsgrupp på dokument.</span><span class="sxs-lookup"><span data-stu-id="4e9bd-104">Sales tax on documents is calculated by providing a Sales tax group and an Item sales tax group on document lines.</span></span> <span data-ttu-id="4e9bd-105">Dessa får sin standard från huvuddata men kan ändras manuellt om det behövs.</span><span class="sxs-lookup"><span data-stu-id="4e9bd-105">These default from master data but can be changed manually if necessary.</span></span> <span data-ttu-id="4e9bd-106">Den beräknade momsen kan kontrolleras på en rad och dokumentnivå.</span><span class="sxs-lookup"><span data-stu-id="4e9bd-106">The calculated sales tax can be checked on a line and document level.</span></span> <span data-ttu-id="4e9bd-107">I den här uppgiften används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="4e9bd-107">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="4e9bd-108">Gå till Leverantörsreskontra > Order > Alla försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="4e9bd-108">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="4e9bd-109">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="4e9bd-109">Click New.</span></span>
3. <span data-ttu-id="4e9bd-110">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Kundkonto.</span><span class="sxs-lookup"><span data-stu-id="4e9bd-110">In the Customer account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="4e9bd-111">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="4e9bd-111">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="4e9bd-112">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="4e9bd-112">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="4e9bd-113">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="4e9bd-113">Click OK.</span></span>
7. <span data-ttu-id="4e9bd-114">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="4e9bd-114">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="4e9bd-115">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="4e9bd-115">In the Item number field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="4e9bd-116">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="4e9bd-116">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="4e9bd-117">Ange ett tal i fältet Enhetspris.</span><span class="sxs-lookup"><span data-stu-id="4e9bd-117">In the Unit price field, enter a number.</span></span>
11. <span data-ttu-id="4e9bd-118">Expandera eller dölj avsnittet Raddetaljer.</span><span class="sxs-lookup"><span data-stu-id="4e9bd-118">Expand or collapse the Line details section.</span></span>
12. <span data-ttu-id="4e9bd-119">Klicka på fliken Inställningar.</span><span class="sxs-lookup"><span data-stu-id="4e9bd-119">Click the Setup tab.</span></span>
13. <span data-ttu-id="4e9bd-120">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelmomsgrupp.</span><span class="sxs-lookup"><span data-stu-id="4e9bd-120">In the Item sales tax group field, click the drop-down button to open the lookup.</span></span>
14. <span data-ttu-id="4e9bd-121">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="4e9bd-121">In the list, find and select the desired record.</span></span>
15. <span data-ttu-id="4e9bd-122">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="4e9bd-122">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="4e9bd-123">Klicka på Ekonomi.</span><span class="sxs-lookup"><span data-stu-id="4e9bd-123">Click Financials.</span></span>
17. <span data-ttu-id="4e9bd-124">Klicka på Moms.</span><span class="sxs-lookup"><span data-stu-id="4e9bd-124">Click Sales tax.</span></span>
18. <span data-ttu-id="4e9bd-125">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="4e9bd-125">Click OK.</span></span>
19. <span data-ttu-id="4e9bd-126">Klicka på Lägg till rad.</span><span class="sxs-lookup"><span data-stu-id="4e9bd-126">Click Add line.</span></span>
20. <span data-ttu-id="4e9bd-127">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="4e9bd-127">In the list, mark the selected row.</span></span>
21. <span data-ttu-id="4e9bd-128">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="4e9bd-128">In the Item number field, click the drop-down button to open the lookup.</span></span>
22. <span data-ttu-id="4e9bd-129">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="4e9bd-129">In the list, find and select the desired record.</span></span>
23. <span data-ttu-id="4e9bd-130">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="4e9bd-130">In the list, click the link in the selected row.</span></span>
24. <span data-ttu-id="4e9bd-131">Ange ett tal i fältet Enhetspris.</span><span class="sxs-lookup"><span data-stu-id="4e9bd-131">In the Unit price field, enter a number.</span></span>
25. <span data-ttu-id="4e9bd-132">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelmomsgrupp.</span><span class="sxs-lookup"><span data-stu-id="4e9bd-132">In the Item sales tax group field, click the drop-down button to open the lookup.</span></span>
26. <span data-ttu-id="4e9bd-133">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="4e9bd-133">In the list, find and select the desired record.</span></span>
27. <span data-ttu-id="4e9bd-134">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="4e9bd-134">In the list, click the link in the selected row.</span></span>
28. <span data-ttu-id="4e9bd-135">Klicka på Sälj i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="4e9bd-135">On the Action Pane, click Sell.</span></span>
29. <span data-ttu-id="4e9bd-136">Klicka på Moms.</span><span class="sxs-lookup"><span data-stu-id="4e9bd-136">Click Sales tax.</span></span>
30. <span data-ttu-id="4e9bd-137">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="4e9bd-137">Click OK.</span></span>

