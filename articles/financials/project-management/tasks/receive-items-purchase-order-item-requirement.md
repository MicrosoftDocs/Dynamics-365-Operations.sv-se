---
title: Ta emot artiklar i inköpsorder från artikelbehov
description: Nedan beskrivs proceduren för att ta emot artiklar i en inköpsorder från ett artikelbehov.
author: KimANelson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage, ProjTable, ProjSalesItemReq, InventItemIdLookupSimple, PurchCreateFromSalesOrder, VendAccountItemLookup, PurchTable, PurchEditLines
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 26572a49426719fba520338a5eccd7e0af78890e
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1572383"
---
# <a name="receive-items-on-purchase-order-from-item-requirement"></a><span data-ttu-id="4c6aa-103">Ta emot artiklar i inköpsorder från artikelbehov</span><span class="sxs-lookup"><span data-stu-id="4c6aa-103">Receive items on purchase order from item requirement</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4c6aa-104">Nedan beskrivs proceduren för att ta emot artiklar i en inköpsorder från ett artikelbehov.</span><span class="sxs-lookup"><span data-stu-id="4c6aa-104">This procedure shows how to receive items on a purchase order from an item requirement.</span></span>

<span data-ttu-id="4c6aa-105">Genom att använda ett artikelbehov i stället för en artikeltransaktion kan du planera för inleverans precis innan artikeln verkligen används, skapa en inköpsorder, ta med artikeln i handelsavtalsramverket och ta med artikelbehovet i produktionsplaneringen.</span><span class="sxs-lookup"><span data-stu-id="4c6aa-105">By using an item requirement instead of an item transaction, you can plan for delivery just before the item is actually used, create a purchase order, include the item in the trade-agreement framework, and include the item requirement in production planning.</span></span> 

<span data-ttu-id="4c6aa-106">I den här uppgiften används datauppsättningen USSI.</span><span class="sxs-lookup"><span data-stu-id="4c6aa-106">This task uses the USSI data set.</span></span>

1. <span data-ttu-id="4c6aa-107">Gå till Projekthantering och redovisning > Projekt > Alla projekt.</span><span class="sxs-lookup"><span data-stu-id="4c6aa-107">Go to Project management and accounting > Projects > All projects.</span></span>
2. <span data-ttu-id="4c6aa-108">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="4c6aa-108">In the list, click the link in the selected row.</span></span>
3. <span data-ttu-id="4c6aa-109">Klicka på Plan i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="4c6aa-109">On the Action Pane, click Plan.</span></span>
4. <span data-ttu-id="4c6aa-110">Klicka på Artikelbehov.</span><span class="sxs-lookup"><span data-stu-id="4c6aa-110">Click Item requirements.</span></span>
5. <span data-ttu-id="4c6aa-111">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="4c6aa-111">Click New.</span></span>
6. <span data-ttu-id="4c6aa-112">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="4c6aa-112">In the list, mark the selected row.</span></span>
7. <span data-ttu-id="4c6aa-113">Ange eller välj ett värde i fältet Artikelnummer.</span><span class="sxs-lookup"><span data-stu-id="4c6aa-113">In the Item number field, enter or select a value.</span></span>
8. <span data-ttu-id="4c6aa-114">Ange ett tal i fältet Kvantitet.</span><span class="sxs-lookup"><span data-stu-id="4c6aa-114">In the Quantity field, enter a number.</span></span>
9. <span data-ttu-id="4c6aa-115">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="4c6aa-115">Click Save.</span></span>
10. <span data-ttu-id="4c6aa-116">Klicka på Hantera i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="4c6aa-116">On the Action Pane, click Manage.</span></span>
11. <span data-ttu-id="4c6aa-117">Klicka på Funktioner.</span><span class="sxs-lookup"><span data-stu-id="4c6aa-117">Click Functions.</span></span>
12. <span data-ttu-id="4c6aa-118">Klicka på Skapa inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="4c6aa-118">Click Create purchase order.</span></span>
13. <span data-ttu-id="4c6aa-119">Markera kryssrutan Inkludera.</span><span class="sxs-lookup"><span data-stu-id="4c6aa-119">Select the Include check box.</span></span>
14. <span data-ttu-id="4c6aa-120">Ange eller välj ett värde i fältet Leverantörskonto.</span><span class="sxs-lookup"><span data-stu-id="4c6aa-120">In the Vendor account field, enter or select a value.</span></span>
15. <span data-ttu-id="4c6aa-121">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="4c6aa-121">Click OK.</span></span>
16. <span data-ttu-id="4c6aa-122">Gå till leverantörsskulder > inköpsorder > Alla inköpsorder.</span><span class="sxs-lookup"><span data-stu-id="4c6aa-122">Go to Accounts payable > Purchase orders > All purchase orders.</span></span>
17. <span data-ttu-id="4c6aa-123">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="4c6aa-123">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="4c6aa-124">Klicka på Inköp i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="4c6aa-124">On the Action Pane, click Purchase.</span></span>
19. <span data-ttu-id="4c6aa-125">Klicka på Bekräfta.</span><span class="sxs-lookup"><span data-stu-id="4c6aa-125">Click Confirm.</span></span>
20. <span data-ttu-id="4c6aa-126">Klicka på Ta emot i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="4c6aa-126">On the Action Pane, click Receive.</span></span>
21. <span data-ttu-id="4c6aa-127">Klicka på Produktinleverans.</span><span class="sxs-lookup"><span data-stu-id="4c6aa-127">Click Product receipt.</span></span>
22. <span data-ttu-id="4c6aa-128">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="4c6aa-128">In the list, mark the selected row.</span></span>
23. <span data-ttu-id="4c6aa-129">Skriv ett värde i fältet Produktinleverans.</span><span class="sxs-lookup"><span data-stu-id="4c6aa-129">In the Product receipt field, type a value.</span></span>
24. <span data-ttu-id="4c6aa-130">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="4c6aa-130">Click OK.</span></span>

