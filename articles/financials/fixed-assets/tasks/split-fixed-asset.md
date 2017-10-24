--- 
title: "Dela en anläggningstillgång"
description: "Den här uppgiftsguiden delar en procentsats för en tillgångsförteckning till en ny tillgångsförteckning."
author: saraschi2
manager: AnnBe
ms.date: 10/19/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: b4c1b39bcae1fa3830f3a217d1ad89e84cd72134
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="split-a-fixed-asset"></a><span data-ttu-id="60e26-103">Dela en anläggningstillgång</span><span class="sxs-lookup"><span data-stu-id="60e26-103">Split a fixed asset</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="60e26-104">Den här uppgiftsguiden delar en procentsats för en tillgångsförteckning till en ny tillgångsförteckning.</span><span class="sxs-lookup"><span data-stu-id="60e26-104">This task guide will split a percentage of one asset book to a new asset book.</span></span>  <span data-ttu-id="60e26-105">Här används revisorrollen och USMF-demonstrationdata.</span><span class="sxs-lookup"><span data-stu-id="60e26-105">It uses the Accountant role and USMF demo data.</span></span>


## <a name="create-a-new-fixed-asset"></a><span data-ttu-id="60e26-106">Skapa en ny anläggningstillgång</span><span class="sxs-lookup"><span data-stu-id="60e26-106">Create a new fixed asset</span></span>
1. <span data-ttu-id="60e26-107">Gå till anläggningstillgångar > anläggningstillgångar > Fasta tillgångar.</span><span class="sxs-lookup"><span data-stu-id="60e26-107">Go to Fixed assets > Fixed assets > Fixed assets.</span></span>
2. <span data-ttu-id="60e26-108">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="60e26-108">Click New.</span></span>
3. <span data-ttu-id="60e26-109">I fältet Anläggningstillgångsgrupp, ange eller välj ett värde.</span><span class="sxs-lookup"><span data-stu-id="60e26-109">In the Fixed asset group field, enter or select a value.</span></span>
4. <span data-ttu-id="60e26-110">Observera numret på anläggningstillgången som ska användas i delningsprocessen senare.</span><span class="sxs-lookup"><span data-stu-id="60e26-110">Note the fixed asset number to use in the split process later.</span></span>
5. <span data-ttu-id="60e26-111">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="60e26-111">In the Name field, type a value.</span></span>
6. <span data-ttu-id="60e26-112">Stäng formuläret.</span><span class="sxs-lookup"><span data-stu-id="60e26-112">Close the form.</span></span>

## <a name="split-a-fixed-asset"></a><span data-ttu-id="60e26-113">Dela en anläggningstillgång</span><span class="sxs-lookup"><span data-stu-id="60e26-113">Split a fixed asset</span></span>
1. <span data-ttu-id="60e26-114">Hitta och välj den anläggningstillgång som ska delas i listan.</span><span class="sxs-lookup"><span data-stu-id="60e26-114">In the list, find and select the fixed asset to split.</span></span>
2. <span data-ttu-id="60e26-115">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="60e26-115">In the list, click the link in the selected row.</span></span>
3. <span data-ttu-id="60e26-116">Klicka på Books.</span><span class="sxs-lookup"><span data-stu-id="60e26-116">Click Books.</span></span>
    * <span data-ttu-id="60e26-117">Välj räkenskapsboken för att dela till den nya tillgången.</span><span class="sxs-lookup"><span data-stu-id="60e26-117">Select the book to split to the new asset.</span></span>  
4. <span data-ttu-id="60e26-118">Klicka på Funktioner.</span><span class="sxs-lookup"><span data-stu-id="60e26-118">Click Functions.</span></span>
5. <span data-ttu-id="60e26-119">Klicka på Dela anläggningstillgång.</span><span class="sxs-lookup"><span data-stu-id="60e26-119">Click Split fixed asset.</span></span>
6. <span data-ttu-id="60e26-120">Ange eller välj ett värde i fältet To fixed asset.</span><span class="sxs-lookup"><span data-stu-id="60e26-120">In the To fixed asset field, enter or select a value.</span></span>
7. <span data-ttu-id="60e26-121">I fältet To book klickar du på den nedrullningsbara knappen för att öppna sökningen.</span><span class="sxs-lookup"><span data-stu-id="60e26-121">In the To book field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="60e26-122">I fältet Transaktionsdatum, ange ett datum.</span><span class="sxs-lookup"><span data-stu-id="60e26-122">In the Transaction date field, enter a date.</span></span>
9. <span data-ttu-id="60e26-123">Ange ett tal i fältet Procent.</span><span class="sxs-lookup"><span data-stu-id="60e26-123">In the Percent field, enter a number.</span></span>
10. <span data-ttu-id="60e26-124">Ange eller välj ett värde i fältet Journal name.</span><span class="sxs-lookup"><span data-stu-id="60e26-124">In the Journal name field, enter or select a value.</span></span>
11. <span data-ttu-id="60e26-125">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="60e26-125">Click OK.</span></span>

## <a name="post-the-journal-transaction"></a><span data-ttu-id="60e26-126">Bokför journaltransaktionen</span><span class="sxs-lookup"><span data-stu-id="60e26-126">Post the journal transaction</span></span>
1. <span data-ttu-id="60e26-127">Gå till Anläggningstillgångar > Journalposter > Journal för anläggningstillgångar.</span><span class="sxs-lookup"><span data-stu-id="60e26-127">Go to Fixed assets > Journal entries > Fixed assets journal.</span></span>
2. <span data-ttu-id="60e26-128">Välj den journal som skapats med delningsprocessen i listan.</span><span class="sxs-lookup"><span data-stu-id="60e26-128">In the list, select the journal created with the split process.</span></span>
3. <span data-ttu-id="60e26-129">Klicka på Rader.</span><span class="sxs-lookup"><span data-stu-id="60e26-129">Click Lines.</span></span>
    * <span data-ttu-id="60e26-130">Kontrollera de skapade journalraderna.</span><span class="sxs-lookup"><span data-stu-id="60e26-130">Verify the journal lines created.</span></span>  <span data-ttu-id="60e26-131">En anskaffningsjusteringstransaktion skapas för den ursprungliga tillgången för att minska värdet med procenten som angetts under delningsprocessen.</span><span class="sxs-lookup"><span data-stu-id="60e26-131">An Acquisition adjustment transaction is created for the original asset to decrease the value by the percentage specified during the split process.</span></span>  <span data-ttu-id="60e26-132">En anskaffningstransaktion skapas för den nya tillgången för samma belopp.</span><span class="sxs-lookup"><span data-stu-id="60e26-132">An Acquisition transaction is created for the new asset for the same amount.</span></span>  
4. <span data-ttu-id="60e26-133">Klicka på Bokför.</span><span class="sxs-lookup"><span data-stu-id="60e26-133">Click Post.</span></span>


