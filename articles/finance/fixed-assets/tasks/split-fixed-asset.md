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
ms.openlocfilehash: 85ccf187e77faf338ac29452d823c3652b806a21
ms.sourcegitcommit: c69926b4285cb2ec2d9ce1ad72d1cb852024dd5e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3138125"
---
# <a name="split-a-fixed-asset"></a><span data-ttu-id="ddfff-103">Dela en anläggningstillgång</span><span class="sxs-lookup"><span data-stu-id="ddfff-103">Split a fixed asset</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ddfff-104">Det här avsnittet förklarar hur du delar en procentsats för en tillgångsförteckning till en ny tillgångsförteckning.</span><span class="sxs-lookup"><span data-stu-id="ddfff-104">This topic explains how to split a percentage of one asset book to a new asset book.</span></span> <span data-ttu-id="ddfff-105">Här används revisorrollen och USMF-demonstrationdata.</span><span class="sxs-lookup"><span data-stu-id="ddfff-105">It uses the Accountant role and USMF demo data.</span></span>


## <a name="create-a-new-fixed-asset"></a><span data-ttu-id="ddfff-106">Skapa en ny anläggningstillgång</span><span class="sxs-lookup"><span data-stu-id="ddfff-106">Create a new fixed asset</span></span>
1. <span data-ttu-id="ddfff-107">I navigeringsfönstret går du till **Moduler > Anläggningstillgångar > Anläggningstillgångar > Anläggningstillgångar**.</span><span class="sxs-lookup"><span data-stu-id="ddfff-107">In the navigation pane, go to **Modules > Fixed assets > Fixed assets > Fixed assets**.</span></span>
2. <span data-ttu-id="ddfff-108">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="ddfff-108">Select **New**.</span></span>
3. <span data-ttu-id="ddfff-109">Ange eller välj ett värde i fältet **Anläggningstillgångsgrupp.**</span><span class="sxs-lookup"><span data-stu-id="ddfff-109">In the **Fixed asset group** field, enter or select a value.</span></span> <span data-ttu-id="ddfff-110">Observera numret på anläggningstillgången som ska användas i delningsprocessen senare.</span><span class="sxs-lookup"><span data-stu-id="ddfff-110">Note the fixed asset number to use in the split process later.</span></span>  
4. <span data-ttu-id="ddfff-111">Skriv ett värde i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="ddfff-111">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="ddfff-112">Stäng formuläret.</span><span class="sxs-lookup"><span data-stu-id="ddfff-112">Close the form.</span></span>

## <a name="split-a-fixed-asset"></a><span data-ttu-id="ddfff-113">Dela en anläggningstillgång</span><span class="sxs-lookup"><span data-stu-id="ddfff-113">Split a fixed asset</span></span>
1. <span data-ttu-id="ddfff-114">Hitta och välj länken till den anläggningstillgång som ska delas i listan.</span><span class="sxs-lookup"><span data-stu-id="ddfff-114">In the list, find and select the link of the fixed asset to split.</span></span>
2. <span data-ttu-id="ddfff-115">Välj **Räkenskapsböcker**.</span><span class="sxs-lookup"><span data-stu-id="ddfff-115">Select **Books**.</span></span> <span data-ttu-id="ddfff-116">Välj räkenskapsboken för att dela till den nya tillgången.</span><span class="sxs-lookup"><span data-stu-id="ddfff-116">Select the book to split to the new asset.</span></span>  
3. <span data-ttu-id="ddfff-117">Välj **Funktioner**.</span><span class="sxs-lookup"><span data-stu-id="ddfff-117">Select **Functions**.</span></span>
4. <span data-ttu-id="ddfff-118">Välj **Dela anläggningstillgång**.</span><span class="sxs-lookup"><span data-stu-id="ddfff-118">Select **Split fixed asset**.</span></span>
5. <span data-ttu-id="ddfff-119">Ange eller välj ett värde i fältet **Till anläggningstillgång**.</span><span class="sxs-lookup"><span data-stu-id="ddfff-119">In the **To fixed asset** field, enter or select a value.</span></span>
6. <span data-ttu-id="ddfff-120">I fältet **Till räkenskapsbok** väljer du den nedrullningsbara knappen för att öppna sökningen.</span><span class="sxs-lookup"><span data-stu-id="ddfff-120">In the **To book** field, select the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="ddfff-121">I fältet **Transaktionsdatum**, ange ett datum.</span><span class="sxs-lookup"><span data-stu-id="ddfff-121">In the **Transaction date** field, enter a date.</span></span>
8. <span data-ttu-id="ddfff-122">Ange ett tal i fältet **Procent**.</span><span class="sxs-lookup"><span data-stu-id="ddfff-122">In the **Percent** field, enter a number.</span></span>
9. <span data-ttu-id="ddfff-123">Ange eller välj ett värde i fältet **Journalnamn**.</span><span class="sxs-lookup"><span data-stu-id="ddfff-123">In the **Journal name** field, enter or select a value.</span></span>
10. <span data-ttu-id="ddfff-124">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="ddfff-124">Select **OK**.</span></span>

## <a name="post-the-journal-transaction"></a><span data-ttu-id="ddfff-125">Bokför journaltransaktionen</span><span class="sxs-lookup"><span data-stu-id="ddfff-125">Post the journal transaction</span></span>
1. <span data-ttu-id="ddfff-126">I navigeringsfönstret går du till **Moduler > Anläggningstillgångar > Journalposter > Journal för anläggningstillgångar**.</span><span class="sxs-lookup"><span data-stu-id="ddfff-126">In the navigation pane, go to **Modules > Fixed assets > Journal entries > Fixed assets journal**.</span></span>
2. <span data-ttu-id="ddfff-127">Välj den journal som skapats med delningsprocessen i listan.</span><span class="sxs-lookup"><span data-stu-id="ddfff-127">In the list, select the journal created with the split process.</span></span>
3. <span data-ttu-id="ddfff-128">Markera **rader**</span><span class="sxs-lookup"><span data-stu-id="ddfff-128">Select **Lines**.</span></span>

    - <span data-ttu-id="ddfff-129">Kontrollera de skapade journalraderna.</span><span class="sxs-lookup"><span data-stu-id="ddfff-129">Verify the journal lines created.</span></span>  
    - <span data-ttu-id="ddfff-130">En anskaffningsjusteringstransaktion skapas för den ursprungliga tillgången för att minska värdet med procenten som angetts under delningsprocessen.</span><span class="sxs-lookup"><span data-stu-id="ddfff-130">An Acquisition adjustment transaction is created for the original asset to decrease the value by the percentage specified during the split process.</span></span>  
    - <span data-ttu-id="ddfff-131">En anskaffningstransaktion skapas för den nya tillgången för samma belopp.</span><span class="sxs-lookup"><span data-stu-id="ddfff-131">An Acquisition transaction is created for the new asset for the same amount.</span></span>  

4. <span data-ttu-id="ddfff-132">Vald **bokföring**</span><span class="sxs-lookup"><span data-stu-id="ddfff-132">Select **Post**.</span></span>

