---
title: Dela en anläggningstillgång
description: Den här uppgiftsguiden delar en procentsats för en tillgångsförteckning till en ny tillgångsförteckning.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, AssetBook, AssetSplit, AssetBookLookup, LedgerJournalTable, LedgerJournalTransAsset
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6be9de64265a4d7b5c91af3ee8acfce80c78e0f1
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1566902"
---
# <a name="split-a-fixed-asset"></a><span data-ttu-id="0d1b1-103">Dela en anläggningstillgång</span><span class="sxs-lookup"><span data-stu-id="0d1b1-103">Split a fixed asset</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0d1b1-104">Den här uppgiftsguiden delar en procentsats för en tillgångsförteckning till en ny tillgångsförteckning.</span><span class="sxs-lookup"><span data-stu-id="0d1b1-104">This task guide will split a percentage of one asset book to a new asset book.</span></span>  <span data-ttu-id="0d1b1-105">Här används revisorrollen och USMF-demonstrationdata.</span><span class="sxs-lookup"><span data-stu-id="0d1b1-105">It uses the Accountant role and USMF demo data.</span></span>


## <a name="create-a-new-fixed-asset"></a><span data-ttu-id="0d1b1-106">Skapa en ny anläggningstillgång</span><span class="sxs-lookup"><span data-stu-id="0d1b1-106">Create a new fixed asset</span></span>
1. <span data-ttu-id="0d1b1-107">Gå till anläggningstillgångar > anläggningstillgångar > Fasta tillgångar.</span><span class="sxs-lookup"><span data-stu-id="0d1b1-107">Go to Fixed assets > Fixed assets > Fixed assets.</span></span>
2. <span data-ttu-id="0d1b1-108">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="0d1b1-108">Click New.</span></span>
3. <span data-ttu-id="0d1b1-109">I fältet Anläggningstillgångsgrupp, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="0d1b1-109">In the Fixed asset group field, enter or select a value.</span></span>
4. <span data-ttu-id="0d1b1-110">Observera numret på anläggningstillgången som ska användas i delningsprocessen senare.</span><span class="sxs-lookup"><span data-stu-id="0d1b1-110">Note the fixed asset number to use in the split process later.</span></span>
5. <span data-ttu-id="0d1b1-111">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="0d1b1-111">In the Name field, type a value.</span></span>
6. <span data-ttu-id="0d1b1-112">Stäng formuläret.</span><span class="sxs-lookup"><span data-stu-id="0d1b1-112">Close the form.</span></span>

## <a name="split-a-fixed-asset"></a><span data-ttu-id="0d1b1-113">Dela en anläggningstillgång</span><span class="sxs-lookup"><span data-stu-id="0d1b1-113">Split a fixed asset</span></span>
1. <span data-ttu-id="0d1b1-114">Hitta och välj den anläggningstillgång som ska delas i listan.</span><span class="sxs-lookup"><span data-stu-id="0d1b1-114">In the list, find and select the fixed asset to split.</span></span>
2. <span data-ttu-id="0d1b1-115">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="0d1b1-115">In the list, click the link in the selected row.</span></span>
3. <span data-ttu-id="0d1b1-116">Klicka på Books.</span><span class="sxs-lookup"><span data-stu-id="0d1b1-116">Click Books.</span></span>
    * <span data-ttu-id="0d1b1-117">Välj räkenskapsboken för att dela till den nya tillgången.</span><span class="sxs-lookup"><span data-stu-id="0d1b1-117">Select the book to split to the new asset.</span></span>  
4. <span data-ttu-id="0d1b1-118">Klicka på Funktioner.</span><span class="sxs-lookup"><span data-stu-id="0d1b1-118">Click Functions.</span></span>
5. <span data-ttu-id="0d1b1-119">Klicka på Dela anläggningstillgång.</span><span class="sxs-lookup"><span data-stu-id="0d1b1-119">Click Split fixed asset.</span></span>
6. <span data-ttu-id="0d1b1-120">Ange eller välj ett värde i fältet To fixed asset.</span><span class="sxs-lookup"><span data-stu-id="0d1b1-120">In the To fixed asset field, enter or select a value.</span></span>
7. <span data-ttu-id="0d1b1-121">I fältet To book klickar du på den nedrullningsbara knappen för att öppna sökningen.</span><span class="sxs-lookup"><span data-stu-id="0d1b1-121">In the To book field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="0d1b1-122">I fältet Transaktionsdatum, ange ett datum.</span><span class="sxs-lookup"><span data-stu-id="0d1b1-122">In the Transaction date field, enter a date.</span></span>
9. <span data-ttu-id="0d1b1-123">Ange ett tal i fältet Procent.</span><span class="sxs-lookup"><span data-stu-id="0d1b1-123">In the Percent field, enter a number.</span></span>
10. <span data-ttu-id="0d1b1-124">Ange eller välj ett värde i fältet Journal name.</span><span class="sxs-lookup"><span data-stu-id="0d1b1-124">In the Journal name field, enter or select a value.</span></span>
11. <span data-ttu-id="0d1b1-125">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="0d1b1-125">Click OK.</span></span>

## <a name="post-the-journal-transaction"></a><span data-ttu-id="0d1b1-126">Bokför journaltransaktionen</span><span class="sxs-lookup"><span data-stu-id="0d1b1-126">Post the journal transaction</span></span>
1. <span data-ttu-id="0d1b1-127">Gå till Anläggningstillgångar > Journalposter > Journal för anläggningstillgångar.</span><span class="sxs-lookup"><span data-stu-id="0d1b1-127">Go to Fixed assets > Journal entries > Fixed assets journal.</span></span>
2. <span data-ttu-id="0d1b1-128">Välj den journal som skapats med delningsprocessen i listan.</span><span class="sxs-lookup"><span data-stu-id="0d1b1-128">In the list, select the journal created with the split process.</span></span>
3. <span data-ttu-id="0d1b1-129">Klicka på Rader.</span><span class="sxs-lookup"><span data-stu-id="0d1b1-129">Click Lines.</span></span>
    * <span data-ttu-id="0d1b1-130">Kontrollera de skapade journalraderna.</span><span class="sxs-lookup"><span data-stu-id="0d1b1-130">Verify the journal lines created.</span></span>  <span data-ttu-id="0d1b1-131">En anskaffningsjusteringstransaktion skapas för den ursprungliga tillgången för att minska värdet med procenten som angetts under delningsprocessen.</span><span class="sxs-lookup"><span data-stu-id="0d1b1-131">An Acquisition adjustment transaction is created for the original asset to decrease the value by the percentage specified during the split process.</span></span>  <span data-ttu-id="0d1b1-132">En anskaffningstransaktion skapas för den nya tillgången för samma belopp.</span><span class="sxs-lookup"><span data-stu-id="0d1b1-132">An Acquisition transaction is created for the new asset for the same amount.</span></span>  
4. <span data-ttu-id="0d1b1-133">Klicka på Bokför.</span><span class="sxs-lookup"><span data-stu-id="0d1b1-133">Click Post.</span></span>

