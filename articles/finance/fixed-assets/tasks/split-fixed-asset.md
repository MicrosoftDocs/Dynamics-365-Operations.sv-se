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
ms.openlocfilehash: 40703622bc8c7a21451d31e7606596c5edbe90f7
ms.sourcegitcommit: 51e626675b0130fa32a84ce2d9119b68ea928018
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4000303"
---
# <a name="split-a-fixed-asset"></a><span data-ttu-id="dc218-103">Dela en anläggningstillgång</span><span class="sxs-lookup"><span data-stu-id="dc218-103">Split a fixed asset</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="dc218-104">Det här avsnittet förklarar hur du delar en procentsats för en tillgångsförteckning till en ny tillgångsförteckning.</span><span class="sxs-lookup"><span data-stu-id="dc218-104">This topic explains how to split a percentage of one asset book to a new asset book.</span></span> <span data-ttu-id="dc218-105">Här används revisorrollen och USMF-demonstrationdata.</span><span class="sxs-lookup"><span data-stu-id="dc218-105">It uses the Accountant role and USMF demo data.</span></span>

## <a name="create-a-new-fixed-asset"></a><span data-ttu-id="dc218-106">Skapa en ny anläggningstillgång</span><span class="sxs-lookup"><span data-stu-id="dc218-106">Create a new fixed asset</span></span>

1. <span data-ttu-id="dc218-107">I navigeringsfönstret går du till **Moduler \> Anläggningstillgångar \> Anläggningstillgångar \> Anläggningstillgångar**.</span><span class="sxs-lookup"><span data-stu-id="dc218-107">In the navigation pane, go to **Modules \> Fixed assets \> Fixed assets \> Fixed assets**.</span></span>
2. <span data-ttu-id="dc218-108">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="dc218-108">Select **New**.</span></span>
3. <span data-ttu-id="dc218-109">Ange eller välj ett värde i fältet **Anläggningstillgångsgrupp.**</span><span class="sxs-lookup"><span data-stu-id="dc218-109">In the **Fixed asset group** field, enter or select a value.</span></span> <span data-ttu-id="dc218-110">Observera numret på anläggningstillgången som ska användas i delningsprocessen senare.</span><span class="sxs-lookup"><span data-stu-id="dc218-110">Note the fixed asset number to use in the split process later.</span></span>
4. <span data-ttu-id="dc218-111">I fältet **Namn** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="dc218-111">In the **Name** field, enter a value.</span></span>
5. <span data-ttu-id="dc218-112">Stäng formuläret.</span><span class="sxs-lookup"><span data-stu-id="dc218-112">Close the form.</span></span>

## <a name="split-a-fixed-asset"></a><span data-ttu-id="dc218-113">Dela en anläggningstillgång</span><span class="sxs-lookup"><span data-stu-id="dc218-113">Split a fixed asset</span></span>

<span data-ttu-id="dc218-114">Innan en helt avskriven tillgång delas upp, ska tillgångens bokningsstatus ändras manuellt från **stängd** till **öppen**.</span><span class="sxs-lookup"><span data-stu-id="dc218-114">Before a fully depreciated asset is split, the asset book status should be manually changed from **Closed** to **Open**.</span></span> <span data-ttu-id="dc218-115">Det här steget är obligatoriskt eftersom bokföringsstatus måste vara **öppen** om du måste bokföra transaktioner för tillgången (t.ex. för en avyttrande försäljning).</span><span class="sxs-lookup"><span data-stu-id="dc218-115">This step is required because the book status has to be **Open** if you must post transactions for the asset (for example, for a disposal sale).</span></span> <span data-ttu-id="dc218-116">När tillgångens bokningsstatus har ändrats följer du dessa steg för att dela upp tillgången.</span><span class="sxs-lookup"><span data-stu-id="dc218-116">After the asset book status is changed, follow these steps to split the asset.</span></span>

1. <span data-ttu-id="dc218-117">Hitta och välj länken till den anläggningstillgång som ska delas i listan.</span><span class="sxs-lookup"><span data-stu-id="dc218-117">In the list, find and select the link of the fixed asset to split.</span></span>
2. <span data-ttu-id="dc218-118">Välj **Räkenskapsböcker**.</span><span class="sxs-lookup"><span data-stu-id="dc218-118">Select **Books**.</span></span> <span data-ttu-id="dc218-119">Välj räkenskapsboken för att dela till den nya tillgången.</span><span class="sxs-lookup"><span data-stu-id="dc218-119">Select the book to split to the new asset.</span></span>
3. <span data-ttu-id="dc218-120">Välj **Funktioner**.</span><span class="sxs-lookup"><span data-stu-id="dc218-120">Select **Functions**.</span></span>
4. <span data-ttu-id="dc218-121">Välj **Dela anläggningstillgång**.</span><span class="sxs-lookup"><span data-stu-id="dc218-121">Select **Split fixed asset**.</span></span>
5. <span data-ttu-id="dc218-122">Ange eller välj ett värde i fältet **Till anläggningstillgång**.</span><span class="sxs-lookup"><span data-stu-id="dc218-122">In the **To fixed asset** field, enter or select a value.</span></span>
6. <span data-ttu-id="dc218-123">I fältet **Till räkenskapsbok** väljer du den nedrullningsbara knappen för att öppna sökningen.</span><span class="sxs-lookup"><span data-stu-id="dc218-123">In the **To book** field, select the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="dc218-124">I fältet **Transaktionsdatum** , ange ett datum.</span><span class="sxs-lookup"><span data-stu-id="dc218-124">In the **Transaction date** field, enter a date.</span></span>
8. <span data-ttu-id="dc218-125">Ange ett tal i fältet **Procent**.</span><span class="sxs-lookup"><span data-stu-id="dc218-125">In the **Percent** field, enter a number.</span></span>
9. <span data-ttu-id="dc218-126">Ange eller välj ett värde i fältet **Journalnamn**.</span><span class="sxs-lookup"><span data-stu-id="dc218-126">In the **Journal name** field, enter or select a value.</span></span>
10. <span data-ttu-id="dc218-127">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="dc218-127">Select **OK**.</span></span>

## <a name="post-the-journal-transaction"></a><span data-ttu-id="dc218-128">Bokför journaltransaktionen</span><span class="sxs-lookup"><span data-stu-id="dc218-128">Post the journal transaction</span></span>

1. <span data-ttu-id="dc218-129">I navigeringsfönstret går du till **Moduler \> Anläggningstillgångar \> Journalposter \> Journal för anläggningstillgångar**.</span><span class="sxs-lookup"><span data-stu-id="dc218-129">In the navigation pane, go to **Modules \> Fixed assets \> Journal entries \> Fixed assets journal**.</span></span>
2. <span data-ttu-id="dc218-130">Välj den journal som skapats med delningsprocessen i listan.</span><span class="sxs-lookup"><span data-stu-id="dc218-130">In the list, select the journal created with the split process.</span></span>
3. <span data-ttu-id="dc218-131">Markera **rader**</span><span class="sxs-lookup"><span data-stu-id="dc218-131">Select **Lines**.</span></span>

    - <span data-ttu-id="dc218-132">Kontrollera de skapade journalraderna.</span><span class="sxs-lookup"><span data-stu-id="dc218-132">Verify the journal lines created.</span></span>
    - <span data-ttu-id="dc218-133">En anskaffningsjusteringstransaktion skapas för den ursprungliga tillgången för att minska värdet med procenten som angetts under delningsprocessen.</span><span class="sxs-lookup"><span data-stu-id="dc218-133">An Acquisition adjustment transaction is created for the original asset to decrease the value by the percentage specified during the split process.</span></span>
    - <span data-ttu-id="dc218-134">En anskaffningstransaktion skapas för den nya tillgången för samma belopp.</span><span class="sxs-lookup"><span data-stu-id="dc218-134">An Acquisition transaction is created for the new asset for the same amount.</span></span>

4. <span data-ttu-id="dc218-135">Vald **bokföring**</span><span class="sxs-lookup"><span data-stu-id="dc218-135">Select **Post**.</span></span>
