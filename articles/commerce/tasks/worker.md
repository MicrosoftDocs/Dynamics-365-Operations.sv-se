---
title: " Konfigurera en arbetare"
description: I den här proceduren visas hur du konfigurerar en medarbetare som en säljare som är berättigad till provision på försäljning i kassan.
author: jblucher
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CommissionSalesGroup, CommissionSalesMember, DirPartyLookup, HcmWorker
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fd437f549ffc1f8879ce3814ace1193040b280e1
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140688"
---
# <a name="configure-a-worker"></a><span data-ttu-id="e3a7b-103"> Konfigurera en arbetare</span><span class="sxs-lookup"><span data-stu-id="e3a7b-103">Configure a worker</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e3a7b-104">I den här proceduren visas hur du konfigurerar en medarbetare som en säljare som är berättigad till provision på försäljning i kassan.</span><span class="sxs-lookup"><span data-stu-id="e3a7b-104">This procedure demonstrates how to configure a worker as a sales representative who is eligible for commission on sales in POS.</span></span> <span data-ttu-id="e3a7b-105">I proceduren används demonstrationsföretaget USRT.</span><span class="sxs-lookup"><span data-stu-id="e3a7b-105">This procedure uses the USRT demo data company.</span></span>


## <a name="create-a-commission-sales-group-for-the-worker"></a><span data-ttu-id="e3a7b-106">Skapa en provisionsförsäljningsgrupp för arbetaren</span><span class="sxs-lookup"><span data-stu-id="e3a7b-106">Create a commission sales group for the worker</span></span>
1. <span data-ttu-id="e3a7b-107">Gå till Försäljning och marknadsföring > Provisioner > Säljgrupper.</span><span class="sxs-lookup"><span data-stu-id="e3a7b-107">Go to Sales and marketing > Commissions > Sales groups.</span></span>
    * <span data-ttu-id="e3a7b-108">Arbetare kan tilldelas en eller flera försäljningsgrupper.</span><span class="sxs-lookup"><span data-stu-id="e3a7b-108">Workers can be assigned to one or more sales groups.</span></span> <span data-ttu-id="e3a7b-109">I kassan kan du välja valfri försäljningsgrupp som innehåller arbetare från butikens adressbok.</span><span class="sxs-lookup"><span data-stu-id="e3a7b-109">In POS, you can choose any sales group that contains workers from the store's address book.</span></span>  
2. <span data-ttu-id="e3a7b-110">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="e3a7b-110">Click New.</span></span>
3. <span data-ttu-id="e3a7b-111">Ange ett värde i fältet Grupp.</span><span class="sxs-lookup"><span data-stu-id="e3a7b-111">In the Group field, type a value.</span></span>
4. <span data-ttu-id="e3a7b-112">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="e3a7b-112">In the Name field, type a value.</span></span>
5. <span data-ttu-id="e3a7b-113">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="e3a7b-113">Click Save.</span></span>
6. <span data-ttu-id="e3a7b-114">Klicka på Allmänt i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="e3a7b-114">On the Action Pane, click General.</span></span>
7. <span data-ttu-id="e3a7b-115">Klicka på Sales rep.</span><span class="sxs-lookup"><span data-stu-id="e3a7b-115">Click Sales rep.</span></span>
    * <span data-ttu-id="e3a7b-116">En försäljningsgrupp kan innehålla mer än en arbetare.</span><span class="sxs-lookup"><span data-stu-id="e3a7b-116">A sales group can contain more than one worker.</span></span> <span data-ttu-id="e3a7b-117">Provision kan delas mellan arbetare baserat på hur du definierar provisionsdelningen.</span><span class="sxs-lookup"><span data-stu-id="e3a7b-117">Commissions can be split between workers based on how you define the commission share.</span></span>  
8. <span data-ttu-id="e3a7b-118">Ange eller välj ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="e3a7b-118">In the Name field, enter or select a value.</span></span>
9. <span data-ttu-id="e3a7b-119">Ange ett värde i fältet Commission share.</span><span class="sxs-lookup"><span data-stu-id="e3a7b-119">In the Commission share field, enter a number.</span></span>
10. <span data-ttu-id="e3a7b-120">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="e3a7b-120">Click Save.</span></span>
11. <span data-ttu-id="e3a7b-121">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="e3a7b-121">Close the page.</span></span>
12. <span data-ttu-id="e3a7b-122">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="e3a7b-122">Close the page.</span></span>

## <a name="assign-the-workers-default-sales-group"></a><span data-ttu-id="e3a7b-123">Tilldela förvald försäljningsgrupp för arbetare</span><span class="sxs-lookup"><span data-stu-id="e3a7b-123">Assign the workers default sales group</span></span>
1. <span data-ttu-id="e3a7b-124">Gå till Butik och handel > Medarbetare > Alla arbetare.</span><span class="sxs-lookup"><span data-stu-id="e3a7b-124">Go to Retail and Commerce > Employees > Workers.</span></span>
2. <span data-ttu-id="e3a7b-125">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="e3a7b-125">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="e3a7b-126">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="e3a7b-126">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="e3a7b-127">Klicka på fliken Handel.</span><span class="sxs-lookup"><span data-stu-id="e3a7b-127">Click the Commerce tab.</span></span>
    * <span data-ttu-id="e3a7b-128">En arbetare kan tilldelas en förvald försäljningsgrupp.</span><span class="sxs-lookup"><span data-stu-id="e3a7b-128">A worker can be assigned to a default sales group.</span></span> <span data-ttu-id="e3a7b-129">Den förvalda försäljningsgruppen läggs automatiskt till i försäljningsrader i kassan om alternativet aktiveras i funktionsprofilen för butiken.</span><span class="sxs-lookup"><span data-stu-id="e3a7b-129">The default sales group will be automatically added to sales lines in POS if the option is enabled in the functionality profile for the store.</span></span>  
5. <span data-ttu-id="e3a7b-130">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="e3a7b-130">Click Edit.</span></span>
6. <span data-ttu-id="e3a7b-131">Ange eller välj ett värde i fältet Default group.</span><span class="sxs-lookup"><span data-stu-id="e3a7b-131">In the Default group field, enter or select a value.</span></span>
7. <span data-ttu-id="e3a7b-132">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="e3a7b-132">Click Save.</span></span>

