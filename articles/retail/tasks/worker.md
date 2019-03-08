---
title: " Konfigurera en arbetare"
description: I den här proceduren visas hur du konfigurerar en detaljhandelsmedarbetare som en säljare som är berättigad till provision på försäljning i kassan.
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
ms.openlocfilehash: 797640b487884fc487582addea274007e4ba7a7d
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "362543"
---
# <a name="configure-a-worker"></a><span data-ttu-id="89cc4-103"> Konfigurera en arbetare</span><span class="sxs-lookup"><span data-stu-id="89cc4-103">Configure a worker</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="89cc4-104">I den här proceduren visas hur du konfigurerar en detaljhandelsmedarbetare som en säljare som är berättigad till provision på försäljning i kassan.</span><span class="sxs-lookup"><span data-stu-id="89cc4-104">This procedure demonstrates how to configure a retail worker as a sales representative who is eligible for commission on sales in POS.</span></span> <span data-ttu-id="89cc4-105">I proceduren används demonstrationsföretaget USRT.</span><span class="sxs-lookup"><span data-stu-id="89cc4-105">This procedure uses the USRT demo data company.</span></span>


## <a name="create-a-commission-sales-group-for-the-worker"></a><span data-ttu-id="89cc4-106">Skapa en provisionsförsäljningsgrupp för arbetaren</span><span class="sxs-lookup"><span data-stu-id="89cc4-106">Create a commission sales group for the worker</span></span>
1. <span data-ttu-id="89cc4-107">Gå till Försäljning och marknadsföring > Provisioner > Säljgrupper.</span><span class="sxs-lookup"><span data-stu-id="89cc4-107">Go to Sales and marketing > Commissions > Sales groups.</span></span>
    * <span data-ttu-id="89cc4-108">Arbetare kan tilldelas en eller flera försäljningsgrupper.</span><span class="sxs-lookup"><span data-stu-id="89cc4-108">Workers can be assigned to one or more sales groups.</span></span> <span data-ttu-id="89cc4-109">I kassan kan du välja valfri försäljningsgrupp som innehåller arbetare från butikens adressbok.</span><span class="sxs-lookup"><span data-stu-id="89cc4-109">In POS, you can choose any sales group that contains workers from the store's address book.</span></span>  
2. <span data-ttu-id="89cc4-110">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="89cc4-110">Click New.</span></span>
3. <span data-ttu-id="89cc4-111">Ange ett värde i fältet Grupp.</span><span class="sxs-lookup"><span data-stu-id="89cc4-111">In the Group field, type a value.</span></span>
4. <span data-ttu-id="89cc4-112">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="89cc4-112">In the Name field, type a value.</span></span>
5. <span data-ttu-id="89cc4-113">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="89cc4-113">Click Save.</span></span>
6. <span data-ttu-id="89cc4-114">Klicka på Allmänt i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="89cc4-114">On the Action Pane, click General.</span></span>
7. <span data-ttu-id="89cc4-115">Klicka på Sales rep.</span><span class="sxs-lookup"><span data-stu-id="89cc4-115">Click Sales rep.</span></span>
    * <span data-ttu-id="89cc4-116">En försäljningsgrupp kan innehålla mer än en arbetare.</span><span class="sxs-lookup"><span data-stu-id="89cc4-116">A sales group can contain more than one worker.</span></span> <span data-ttu-id="89cc4-117">Provision kan delas mellan arbetare baserat på hur du definierar provisionsdelningen.</span><span class="sxs-lookup"><span data-stu-id="89cc4-117">Commissions can be split between workers based on how you define the commission share.</span></span>  
8. <span data-ttu-id="89cc4-118">Ange eller välj ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="89cc4-118">In the Name field, enter or select a value.</span></span>
9. <span data-ttu-id="89cc4-119">Ange ett värde i fältet Commission share.</span><span class="sxs-lookup"><span data-stu-id="89cc4-119">In the Commission share field, enter a number.</span></span>
10. <span data-ttu-id="89cc4-120">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="89cc4-120">Click Save.</span></span>
11. <span data-ttu-id="89cc4-121">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="89cc4-121">Close the page.</span></span>
12. <span data-ttu-id="89cc4-122">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="89cc4-122">Close the page.</span></span>

## <a name="assign-the-workers-default-sales-group"></a><span data-ttu-id="89cc4-123">Tilldela förvald försäljningsgrupp för arbetare</span><span class="sxs-lookup"><span data-stu-id="89cc4-123">Assign the workers default sales group</span></span>
1. <span data-ttu-id="89cc4-124">Gå till Butik och handel > Medarbetare > Alla arbetare.</span><span class="sxs-lookup"><span data-stu-id="89cc4-124">Go to Retail and commerce > Employees > Workers.</span></span>
2. <span data-ttu-id="89cc4-125">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="89cc4-125">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="89cc4-126">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="89cc4-126">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="89cc4-127">Klicka på fliken Butik.</span><span class="sxs-lookup"><span data-stu-id="89cc4-127">Click the Retail tab.</span></span>
    * <span data-ttu-id="89cc4-128">En arbetare kan tilldelas en förvald försäljningsgrupp.</span><span class="sxs-lookup"><span data-stu-id="89cc4-128">A worker can be assigned to a default sales group.</span></span> <span data-ttu-id="89cc4-129">Den förvalda försäljningsgruppen läggs automatiskt till i försäljningsrader i kassan om alternativet aktiveras i funktionsprofilen för butiken.</span><span class="sxs-lookup"><span data-stu-id="89cc4-129">The default sales group will be automatically added to sales lines in POS if the option is enabled in the functionality profile for the store.</span></span>  
5. <span data-ttu-id="89cc4-130">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="89cc4-130">Click Edit.</span></span>
6. <span data-ttu-id="89cc4-131">Ange eller välj ett värde i fältet Default group.</span><span class="sxs-lookup"><span data-stu-id="89cc4-131">In the Default group field, enter or select a value.</span></span>
7. <span data-ttu-id="89cc4-132">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="89cc4-132">Click Save.</span></span>

