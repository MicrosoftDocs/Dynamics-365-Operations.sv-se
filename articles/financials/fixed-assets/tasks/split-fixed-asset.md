---
title: Dela en anläggningstillgång
description: Det här avsnittet förklarar hur du delar en procentsats för en tillgångsförteckning till en ny tillgångsförteckning.
author: saraschi2
manager: AnnBe
ms.date: 08/06/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, AssetBook, AssetSplit, AssetBookLookup, LedgerJournalTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a4e001a6fdf390c6211ba85aa327b60dcdf16d9e
ms.sourcegitcommit: a368682f9cf3897347d155f1a2d4b33e555cc2c4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/08/2019
ms.locfileid: "1867593"
---
# <a name="split-a-fixed-asset"></a><span data-ttu-id="b6c80-103">Dela en anläggningstillgång</span><span class="sxs-lookup"><span data-stu-id="b6c80-103">Split a fixed asset</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b6c80-104">Det här avsnittet förklarar hur du delar en procentsats för en tillgångsförteckning till en ny tillgångsförteckning.</span><span class="sxs-lookup"><span data-stu-id="b6c80-104">This topic explains how to split a percentage of one asset book to a new asset book.</span></span> <span data-ttu-id="b6c80-105">Här används revisorrollen och USMF-demonstrationdata.</span><span class="sxs-lookup"><span data-stu-id="b6c80-105">It uses the Accountant role and USMF demo data.</span></span>


## <a name="create-a-new-fixed-asset"></a><span data-ttu-id="b6c80-106">Skapa en ny anläggningstillgång</span><span class="sxs-lookup"><span data-stu-id="b6c80-106">Create a new fixed asset</span></span>
1. <span data-ttu-id="b6c80-107">I navigeringsfönstret går du till **Moduler > Anläggningstillgångar > Anläggningstillgångar > Anläggningstillgångar**.</span><span class="sxs-lookup"><span data-stu-id="b6c80-107">In the navigation pane, go to **Modules > Fixed assets > Fixed assets > Fixed assets**.</span></span>
2. <span data-ttu-id="b6c80-108">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="b6c80-108">Select **New**.</span></span>
3. <span data-ttu-id="b6c80-109">Ange eller välj ett värde i fältet **Anläggningstillgångsgrupp.**</span><span class="sxs-lookup"><span data-stu-id="b6c80-109">In the **Fixed asset group** field, enter or select a value.</span></span> <span data-ttu-id="b6c80-110">Observera numret på anläggningstillgången som ska användas i delningsprocessen senare.</span><span class="sxs-lookup"><span data-stu-id="b6c80-110">Note the fixed asset number to use in the split process later.</span></span>  
4. <span data-ttu-id="b6c80-111">Skriv ett värde i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="b6c80-111">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="b6c80-112">Stäng formuläret.</span><span class="sxs-lookup"><span data-stu-id="b6c80-112">Close the form.</span></span>

## <a name="split-a-fixed-asset"></a><span data-ttu-id="b6c80-113">Dela en anläggningstillgång</span><span class="sxs-lookup"><span data-stu-id="b6c80-113">Split a fixed asset</span></span>
1. <span data-ttu-id="b6c80-114">Hitta och välj länken till den anläggningstillgång som ska delas i listan.</span><span class="sxs-lookup"><span data-stu-id="b6c80-114">In the list, find and select the link of the fixed asset to split.</span></span>
2. <span data-ttu-id="b6c80-115">Välj **Räkenskapsböcker**.</span><span class="sxs-lookup"><span data-stu-id="b6c80-115">Select **Books**.</span></span> <span data-ttu-id="b6c80-116">Välj räkenskapsboken för att dela till den nya tillgången.</span><span class="sxs-lookup"><span data-stu-id="b6c80-116">Select the book to split to the new asset.</span></span>  
3. <span data-ttu-id="b6c80-117">Välj **Funktioner**.</span><span class="sxs-lookup"><span data-stu-id="b6c80-117">Select **Functions**.</span></span>
4. <span data-ttu-id="b6c80-118">Välj **Dela anläggningstillgång**.</span><span class="sxs-lookup"><span data-stu-id="b6c80-118">Select **Split fixed asset**.</span></span>
5. <span data-ttu-id="b6c80-119">Ange eller välj ett värde i fältet **Till anläggningstillgång**.</span><span class="sxs-lookup"><span data-stu-id="b6c80-119">In the **To fixed asset** field, enter or select a value.</span></span>
6. <span data-ttu-id="b6c80-120">I fältet **Till räkenskapsbok** väljer du den nedrullningsbara knappen för att öppna sökningen.</span><span class="sxs-lookup"><span data-stu-id="b6c80-120">In the **To book** field, select the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="b6c80-121">I fältet **Transaktionsdatum**, ange ett datum.</span><span class="sxs-lookup"><span data-stu-id="b6c80-121">In the **Transaction date** field, enter a date.</span></span>
8. <span data-ttu-id="b6c80-122">Ange ett tal i fältet **Procent**.</span><span class="sxs-lookup"><span data-stu-id="b6c80-122">In the **Percent** field, enter a number.</span></span>
9. <span data-ttu-id="b6c80-123">Ange eller välj ett värde i fältet **Journalnamn**.</span><span class="sxs-lookup"><span data-stu-id="b6c80-123">In the **Journal name** field, enter or select a value.</span></span>
10. <span data-ttu-id="b6c80-124">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="b6c80-124">Select **OK**.</span></span>

## <a name="post-the-journal-transaction"></a><span data-ttu-id="b6c80-125">Bokför journaltransaktionen</span><span class="sxs-lookup"><span data-stu-id="b6c80-125">Post the journal transaction</span></span>
1. <span data-ttu-id="b6c80-126">I navigeringsfönstret går du till **Moduler > Anläggningstillgångar > Journalposter > Journal för anläggningstillgångar**.</span><span class="sxs-lookup"><span data-stu-id="b6c80-126">In the navigation pane, go to **Modules > Fixed assets > Journal entries > Fixed assets journal**.</span></span>
2. <span data-ttu-id="b6c80-127">Välj den journal som skapats med delningsprocessen i listan.</span><span class="sxs-lookup"><span data-stu-id="b6c80-127">In the list, select the journal created with the split process.</span></span>
3. <span data-ttu-id="b6c80-128">Markera **rader**</span><span class="sxs-lookup"><span data-stu-id="b6c80-128">Select **Lines**.</span></span>

    - <span data-ttu-id="b6c80-129">Kontrollera de skapade journalraderna.</span><span class="sxs-lookup"><span data-stu-id="b6c80-129">Verify the journal lines created.</span></span>  
    - <span data-ttu-id="b6c80-130">En anskaffningsjusteringstransaktion skapas för den ursprungliga tillgången för att minska värdet med procenten som angetts under delningsprocessen.</span><span class="sxs-lookup"><span data-stu-id="b6c80-130">An Acquisition adjustment transaction is created for the original asset to decrease the value by the percentage specified during the split process.</span></span>  
    - <span data-ttu-id="b6c80-131">En anskaffningstransaktion skapas för den nya tillgången för samma belopp.</span><span class="sxs-lookup"><span data-stu-id="b6c80-131">An Acquisition transaction is created for the new asset for the same amount.</span></span>  

4. <span data-ttu-id="b6c80-132">Vald **bokföring**</span><span class="sxs-lookup"><span data-stu-id="b6c80-132">Select **Post**.</span></span>

