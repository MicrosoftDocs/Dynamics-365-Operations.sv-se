---
title: Ta emot artiklar i inköpsorder från artikelbehov
description: I det här avsnittet beskrivs proceduren för att ta emot artiklar i en inköpsorder från ett artikelbehov.
author: KimANelson
manager: AnnBe
ms.date: 08/06/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage, ProjTable, ProjSalesItemReq, InventItemIdLookupSimple, PurchCreateFromSalesOrder, VendAccountItemLookup, PurchTable, PurchEditLines
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7afdae65c5ae7e3196c6b9f142dd87aec39b5ea3
ms.sourcegitcommit: a368682f9cf3897347d155f1a2d4b33e555cc2c4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/08/2019
ms.locfileid: "1867305"
---
# <a name="receive-items-on-purchase-order-from-item-requirement"></a><span data-ttu-id="d957f-103">Ta emot artiklar i inköpsorder från artikelbehov</span><span class="sxs-lookup"><span data-stu-id="d957f-103">Receive items on purchase order from item requirement</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d957f-104">I det här avsnittet beskrivs proceduren för att ta emot artiklar i en inköpsorder från ett artikelbehov.</span><span class="sxs-lookup"><span data-stu-id="d957f-104">This topic explains how to receive items on a purchase order from an item requirement.</span></span>

<span data-ttu-id="d957f-105">Genom att använda ett artikelbehov i stället för en artikeltransaktion kan du planera för inleverans precis innan artikeln verkligen används, skapa en inköpsorder, ta med artikeln i handelsavtalsramverket och ta med artikelbehovet i produktionsplaneringen.</span><span class="sxs-lookup"><span data-stu-id="d957f-105">By using an item requirement instead of an item transaction, you can plan for delivery just before the item is actually used, create a purchase order, include the item in the trade-agreement framework, and include the item requirement in production planning.</span></span> 

<span data-ttu-id="d957f-106">I den här uppgiften används datauppsättningen USSI.</span><span class="sxs-lookup"><span data-stu-id="d957f-106">This task uses the USSI data set.</span></span>

1. <span data-ttu-id="d957f-107">I navigeringsfönstret, gå till **Moduler > Projekthantering och redovisning > Projekt > Alla projekt**.</span><span class="sxs-lookup"><span data-stu-id="d957f-107">In the navigation pane, go to **Modules > Project management and accounting > Projects > All projects**.</span></span>
2. <span data-ttu-id="d957f-108">Klicka på länken på önskad rad i listan.</span><span class="sxs-lookup"><span data-stu-id="d957f-108">In the list, select the link in the desired row.</span></span>
3. <span data-ttu-id="d957f-109">Klicka på **Plan** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="d957f-109">On the Action Pane, select **Plan**.</span></span>
4. <span data-ttu-id="d957f-110">Välj **Artikelbehov**.</span><span class="sxs-lookup"><span data-stu-id="d957f-110">Select **Item requirements**.</span></span>
5. <span data-ttu-id="d957f-111">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="d957f-111">Select **New**.</span></span>
6. <span data-ttu-id="d957f-112">På den nya raden ange eller välj ett värde i fältet **Artikelnummer**.</span><span class="sxs-lookup"><span data-stu-id="d957f-112">In the new row, enter or select a value in the **Item number** field.</span></span>
7. <span data-ttu-id="d957f-113">Ange ett nummer i fältet **Kvantitet**.</span><span class="sxs-lookup"><span data-stu-id="d957f-113">In the **Quantity** field, enter a number.</span></span>
8. <span data-ttu-id="d957f-114">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="d957f-114">Select **Save**.</span></span>
9. <span data-ttu-id="d957f-115">I åtgärdsfönstret klicka på **Hantera**.</span><span class="sxs-lookup"><span data-stu-id="d957f-115">On the Action Pane, select **Manage**.</span></span>
10. <span data-ttu-id="d957f-116">Välj **Funktioner**.</span><span class="sxs-lookup"><span data-stu-id="d957f-116">Select **Functions**.</span></span>
11. <span data-ttu-id="d957f-117">Välj **Skapa inköpsorder**.</span><span class="sxs-lookup"><span data-stu-id="d957f-117">Select **Create purchase order**.</span></span>
12. <span data-ttu-id="d957f-118">Markera kryssrutan **Inkludera alla**.</span><span class="sxs-lookup"><span data-stu-id="d957f-118">Select the **Include all** check box.</span></span>
13. <span data-ttu-id="d957f-119">I **leverantörskonto** fält, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="d957f-119">In the **Vendor account** field, enter or select a value.</span></span>
14. <span data-ttu-id="d957f-120">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="d957f-120">Select **OK**.</span></span>
15. <span data-ttu-id="d957f-121">I navigeringsfönstret går du till **Moduler > Leverantörsreskontra > Inköpsorder > Alla inköpsorder**.</span><span class="sxs-lookup"><span data-stu-id="d957f-121">In the navigation pane, go to **Modules > Accounts payable > Purchase orders > All purchase orders**.</span></span>
16. <span data-ttu-id="d957f-122">Klicka på länken på önskad rad i listan.</span><span class="sxs-lookup"><span data-stu-id="d957f-122">In the list, select the link in the desired row.</span></span>
17. <span data-ttu-id="d957f-123">I åtgärdsfönstret, välj **Inköp**.</span><span class="sxs-lookup"><span data-stu-id="d957f-123">On the Action Pane, select **Purchase**.</span></span>
18. <span data-ttu-id="d957f-124">Välj **Bekräfta**.</span><span class="sxs-lookup"><span data-stu-id="d957f-124">Select **Confirm**.</span></span>
19. <span data-ttu-id="d957f-125">Välj **Ta emot** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="d957f-125">On the Action Pane, select **Receive**.</span></span>
20. <span data-ttu-id="d957f-126">Välj **produktinleverans**</span><span class="sxs-lookup"><span data-stu-id="d957f-126">Select **Product receipt**.</span></span>
21. <span data-ttu-id="d957f-127">I fältet **Produktinleverans**, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="d957f-127">In the **Product receipt** field, type a value.</span></span>
22. <span data-ttu-id="d957f-128">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="d957f-128">Select **OK**.</span></span>

