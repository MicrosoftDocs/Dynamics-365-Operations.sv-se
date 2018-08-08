---
title: "Inköpsorder för ett projekt"
description: "Den här artikeln beskriver de olika metoder du kan använda för att skapa inköpsorder för ett projekt. Metoden som du använder, beror på syftet med inköpsordern och när inköpta artiklarna förbrukas och debiteras ett projekt."
author: KimANelson
manager: AnnBe
ms.date: 09/14/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProjTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 83972
ms.assetid: 247e4d72-610b-4fa5-9873-601ed0f4b2d6
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 767a1805e7a2609c5c28bed891b42f7c8c3aaffc
ms.contentlocale: sv-se
ms.lasthandoff: 08/07/2018

---

# <a name="purchase-orders-for-a-project"></a><span data-ttu-id="a736f-104">Inköpsorder för ett projekt</span><span class="sxs-lookup"><span data-stu-id="a736f-104">Purchase orders for a project</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a736f-105">Den här artikeln beskriver de olika metoder du kan använda för att skapa inköpsorder för ett projekt.</span><span class="sxs-lookup"><span data-stu-id="a736f-105">This article describes the various methods that you can use to create purchase orders for a project.</span></span> <span data-ttu-id="a736f-106">Metoden som du använder, beror på syftet med inköpsordern och när inköpta artiklarna förbrukas och debiteras ett projekt.</span><span class="sxs-lookup"><span data-stu-id="a736f-106">The method that you use depends on the purpose of the purchase order, and when the purchased items are consumed and charged to a project.</span></span>

<span data-ttu-id="a736f-107">I Microsoft Dynamics 365 for Finance and Operations kan du använda flera olika sätt för att skapa inköpsorder för ett projekt.</span><span class="sxs-lookup"><span data-stu-id="a736f-107">In Microsoft Dynamics 365 for Finance and Operations, you can use multiple methods to create purchase orders for a project.</span></span> <span data-ttu-id="a736f-108">Metoden som du använder, beror på syftet med inköpsordern, när de inköpta artiklarna förbrukas, och när inköpta artiklarna debiteras ett projekt.</span><span class="sxs-lookup"><span data-stu-id="a736f-108">The method that you use depends on the purpose of the purchase order, when the purchased items are consumed, and when the purchased items are charged to a project.</span></span>

### <a name="methods-for-creating-a-purchase-order"></a><span data-ttu-id="a736f-109">Metoder för att skapa en inköpsorder</span><span class="sxs-lookup"><span data-stu-id="a736f-109">Methods for creating a purchase order</span></span>

<span data-ttu-id="a736f-110">Du kan använda en av följande metoder för att skapa en inköpsorder i Projekthantering och redovisning.</span><span class="sxs-lookup"><span data-stu-id="a736f-110">You can use one of the following methods to create a purchase order in Project management and accounting.</span></span> <span data-ttu-id="a736f-111">Syftet med inköpsordern avgör när inköpsordern förbrukas och därmed när artiklar debiteras ett projekt.</span><span class="sxs-lookup"><span data-stu-id="a736f-111">The purpose of the purchase order determines when the purchase order is consumed and, therefore, when items are charged to a project.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a736f-112">Metod</span><span class="sxs-lookup"><span data-stu-id="a736f-112">Method</span></span></th>
<th><span data-ttu-id="a736f-113">Syfte</span><span class="sxs-lookup"><span data-stu-id="a736f-113">Purpose</span></span></th>
<th><span data-ttu-id="a736f-114">Förbrukning av artiklar</span><span class="sxs-lookup"><span data-stu-id="a736f-114">Consumption of items</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="a736f-115">Skapa en inköpsorder direkt från ett projekt.</span><span class="sxs-lookup"><span data-stu-id="a736f-115">Create a purchase order directly from a project.</span></span></td>
<td><span data-ttu-id="a736f-116">Använd den här metoden för att köpa artiklar från en extern leverantör för förbrukning i ett projekt.</span><span class="sxs-lookup"><span data-stu-id="a736f-116">Use this method to purchase items from an external vendor for consumption on a project.</span></span> <span data-ttu-id="a736f-117">Du kan skapa inköpsordern på två sätt:</span><span class="sxs-lookup"><span data-stu-id="a736f-117">You can create the purchase order in two ways:</span></span>
<ul>
<li><span data-ttu-id="a736f-118">Från själva projektet.</span><span class="sxs-lookup"><span data-stu-id="a736f-118">From the project itself.</span></span> <span data-ttu-id="a736f-119">I det här fallet har projektet redan definierats för inköpsordern.</span><span class="sxs-lookup"><span data-stu-id="a736f-119">In this case, the project is already defined for the purchase order.</span></span></li>
<li><span data-ttu-id="a736f-120">Genom att navigera till projektinköpsordern.</span><span class="sxs-lookup"><span data-stu-id="a736f-120">By navigating to the project purchase order.</span></span> <span data-ttu-id="a736f-121">Du måste välja både leverantören och projektet som inköpsordern ska skapas för.</span><span class="sxs-lookup"><span data-stu-id="a736f-121">You must select both the vendor and the project to create the purchase order for.</span></span></li>
</ul></td>
<td><span data-ttu-id="a736f-122">Artiklar förbrukas när leverantörsfakturan uppdateras.</span><span class="sxs-lookup"><span data-stu-id="a736f-122">Items are consumed when the vendor invoice is updated.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a736f-123">Skapa en inköpsorder från en försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="a736f-123">Create a purchase order from a sales order.</span></span></td>
<td><span data-ttu-id="a736f-124">Använd den här metoden för att köpa in artiklar när du skapar en försäljningsorder från ett projekt.</span><span class="sxs-lookup"><span data-stu-id="a736f-124">Use this method to purchase items when you create a sales order from a project.</span></span></td>
<td><span data-ttu-id="a736f-125">Artiklar förbrukas när försäljningsordern faktureras till kunden.</span><span class="sxs-lookup"><span data-stu-id="a736f-125">Items are consumed when the sales order is invoiced to the customer.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="a736f-126">Skapa en inköpsorder från ett artikelbehov.</span><span class="sxs-lookup"><span data-stu-id="a736f-126">Create a purchase order from an item requirement.</span></span></td>
<td><span data-ttu-id="a736f-127">Använd den här metoden för att köpa in artiklar när du skapar ett artikelbehov från ett projekt.</span><span class="sxs-lookup"><span data-stu-id="a736f-127">Use this method to purchase items when you create an item requirement from a project.</span></span></td>
<td><span data-ttu-id="a736f-128">Artiklar förbrukas när följesedeln för artikelbehov uppdateras.</span><span class="sxs-lookup"><span data-stu-id="a736f-128">Items are consumed when the item requirement packing slip is updated.</span></span></td>
</tr>
</tbody>
</table>

> [!NOTE] 
> <span data-ttu-id="a736f-129">När du uppdaterar leverantörsfakturan eller följesedeln uppmanas du att uppdatera följesedeln på artikelbehovet.</span><span class="sxs-lookup"><span data-stu-id="a736f-129">When you update the vendor invoice or packing slip, you're prompted to update the packing slip on the item requirement.</span></span>

<span data-ttu-id="a736f-130">Mer information finns i [ta emot artiklar på inköpsorder från ett artikelbehov](tasks/receive-items-purchase-order-item-requirement.md).</span><span class="sxs-lookup"><span data-stu-id="a736f-130">For more information, see [Receive items on purchase order from item requirement](tasks/receive-items-purchase-order-item-requirement.md).</span></span>


