---
title: Återför journalbokföring
description: I det här avsnittet beskrivs funktioner som gör att du kan återföra verifikationer från en verifikationstransaktionslista eller från ekonomiska journaler.
author: MikeFalkner
manager: AnnBe
ms.date: 10/08/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerTransVoucher, LedgerJournalTable
audience: Application User
ms.reviewer: roschloma
ms.search.scope: Core, Operations
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c5d1c58463c24dc6a40b036f0bb803316bbb65c2
ms.sourcegitcommit: f38302b9430f2ab3efe91d0a7beff946bc610e8f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/28/2020
ms.locfileid: "3091909"
---
# <a name="reverse-journal-posting"></a><span data-ttu-id="6fd4a-103">Återför journalbokföring</span><span class="sxs-lookup"><span data-stu-id="6fd4a-103">Reverse journal posting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6fd4a-104">I det här avsnittet beskrivs Microsoft Dynamics 365 Finance-funktioner som gör att du kan återföra en hel journal eller återföra en eller flera verifikationer från verifikationstransaktionslistan oavsett ursprung.</span><span class="sxs-lookup"><span data-stu-id="6fd4a-104">This topic describes capabilities Microsoft Dynamics 365 Finance that allows you to reverse an entire journal, or reverse one or more vouchers from the voucher transaction list, regardless of their origin.</span></span> 

## <a name="reversing-journals"></a><span data-ttu-id="6fd4a-105">Återföra journaler</span><span class="sxs-lookup"><span data-stu-id="6fd4a-105">Reversing journals</span></span>

<span data-ttu-id="6fd4a-106">Du kan återföra journalrader individuellt.</span><span class="sxs-lookup"><span data-stu-id="6fd4a-106">You can reverse journal lines individually.</span></span> <span data-ttu-id="6fd4a-107">Med en omvänd journalbokföring kan du även återföra en hel redovisningsjournal.</span><span class="sxs-lookup"><span data-stu-id="6fd4a-107">With reverse journal posting, you can also reverse an entire financial journal.</span></span> <span data-ttu-id="6fd4a-108">För att återföra en journal:</span><span class="sxs-lookup"><span data-stu-id="6fd4a-108">To reverse a journal:</span></span> 

- <span data-ttu-id="6fd4a-109">Öppna redovisningsjournalen och filtrera på bokförda journaler.</span><span class="sxs-lookup"><span data-stu-id="6fd4a-109">Open the financial journal and filter on posted journals.</span></span>
- <span data-ttu-id="6fd4a-110">Klicka på menyn **Återför** högst upp på sidan.</span><span class="sxs-lookup"><span data-stu-id="6fd4a-110">Select the **Reverse** menu at the top of the page.</span></span>
- <span data-ttu-id="6fd4a-111">Det totala antalet verifikationer och verifikationsrader samt det totala beloppet för raderna som återförts visas.</span><span class="sxs-lookup"><span data-stu-id="6fd4a-111">You will see the total number of vouchers and voucher lines as well as the total amount of the lines being reversed</span></span>
- <span data-ttu-id="6fd4a-112">Välj **Ja** om du vill använda de befintliga transaktionsdatumen eller **Nej** om du vill ange ett nytt.</span><span class="sxs-lookup"><span data-stu-id="6fd4a-112">Select **Yes** to use the existing transaction dates or **No** to enter a new one.</span></span> <span data-ttu-id="6fd4a-113">I vissa fall kan perioden för den ursprungliga transaktionen stängas och du måste ange ett nytt transaktionsdatum för återföringen.</span><span class="sxs-lookup"><span data-stu-id="6fd4a-113">In some cases, the period of the original transaction may be closed and you must enter a new transaction date for the reversal.</span></span>
- <span data-ttu-id="6fd4a-114">Om du har valt **nej** anger du ett transaktionsdatum för återföringen.</span><span class="sxs-lookup"><span data-stu-id="6fd4a-114">If you select **No**, enter a transaction date for the reversal.</span></span> 
- <span data-ttu-id="6fd4a-115">Ange en kommentar som du vill lägga till i återföringstransaktionen.</span><span class="sxs-lookup"><span data-stu-id="6fd4a-115">Enter a comment that you want added to the reversal transaction.</span></span>
- <span data-ttu-id="6fd4a-116">Välj knappen **Återför**.</span><span class="sxs-lookup"><span data-stu-id="6fd4a-116">Select the **Reverse** button.</span></span>

<span data-ttu-id="6fd4a-117">Transaktionerna kommer att återföras.</span><span class="sxs-lookup"><span data-stu-id="6fd4a-117">The transactions will be reversed.</span></span> 

<span data-ttu-id="6fd4a-118">Om antalet verifikationer innehåller mer än 100 rader, kommer återföringsprocessen att köras med batch-processen.</span><span class="sxs-lookup"><span data-stu-id="6fd4a-118">If the voucher contains more than 100 lines, the reversal process will run using the batch process.</span></span> <span data-ttu-id="6fd4a-119">Du kan granska resultatet genom att visa kommentarerna i batch-jobbet.</span><span class="sxs-lookup"><span data-stu-id="6fd4a-119">You can review the results by viewing the comments in the batch job.</span></span> <span data-ttu-id="6fd4a-120">Alla transaktioner som inte kunde återföras visas i historiken för batchjobbet.</span><span class="sxs-lookup"><span data-stu-id="6fd4a-120">Any transactions that couldn't be reversed will be listed in the batch job history.</span></span>

<span data-ttu-id="6fd4a-121">Om verifikationen innehåller fler än 100 rader eller färre, kommer återföringsprocessen att köras omedelbart.</span><span class="sxs-lookup"><span data-stu-id="6fd4a-121">If the voucher contains 100 lines or fewer, the reversal process will run immediately.</span></span> <span data-ttu-id="6fd4a-122">Resultaten visas i en dialogruta som visar en verifikation som inte kan återföras och orsaken till varför den inte kunde återföras.</span><span class="sxs-lookup"><span data-stu-id="6fd4a-122">The results will be presented in a dialog box that shows any voucher that could not be reversed, along with the reason why it could not be reversed.</span></span> <span data-ttu-id="6fd4a-123">Välj **OK** för att stänga dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="6fd4a-123">Select **OK** to close the dialog box.</span></span>

## <a name="reversing-vouchers-from-the-voucher-transaction-list"></a><span data-ttu-id="6fd4a-124">Återför verifikationer från listan med verifikationstransaktioner.</span><span class="sxs-lookup"><span data-stu-id="6fd4a-124">Reversing vouchers from the voucher transaction list.</span></span> 

<span data-ttu-id="6fd4a-125">Du kan även återföra verifikationer från **transaktionslistan för verifikationer** i alla redovisningstransaktioner.</span><span class="sxs-lookup"><span data-stu-id="6fd4a-125">You can also reverse vouchers from the **Voucher transaction list** across all subledgers.</span></span> <span data-ttu-id="6fd4a-126">Dessutom kan du återföra fler än en verifikation åt gången.</span><span class="sxs-lookup"><span data-stu-id="6fd4a-126">In addition, you can reverse more than one voucher at a time.</span></span> 

<span data-ttu-id="6fd4a-127">Så här återför du en eller flera verifikationer:</span><span class="sxs-lookup"><span data-stu-id="6fd4a-127">To reverse one or more vouchers:</span></span> 

- <span data-ttu-id="6fd4a-128">Klicka på menyn **Återför** högst upp på sidan.</span><span class="sxs-lookup"><span data-stu-id="6fd4a-128">Select the **Reverse** menu at the top of the page</span></span>
- <span data-ttu-id="6fd4a-129">Det totala antalet verifikationer och verifikationsrader samt det totala beloppet för raderna som återförts visas.</span><span class="sxs-lookup"><span data-stu-id="6fd4a-129">You will see the total number of vouchers and voucher lines as well as the total amount of the lines being reversed.</span></span>
- <span data-ttu-id="6fd4a-130">Välj **Ja** om du vill använda de befintliga transaktionsdatumen eller **Nej** om du vill ange ett nytt.</span><span class="sxs-lookup"><span data-stu-id="6fd4a-130">Select **Yes** to use the existing transaction dates or **No** to enter a new one.</span></span> <span data-ttu-id="6fd4a-131">I vissa fall kan perioden för den ursprungliga transaktionen stängas och du måste ange ett nytt transaktionsdatum för att återföra den.</span><span class="sxs-lookup"><span data-stu-id="6fd4a-131">In some cases, the period of the original transaction may be closed and you must enter a new transaction date to reverse it.</span></span>
- <span data-ttu-id="6fd4a-132">Om du har valt **nej** anger du ett transaktionsdatum för återföringen.</span><span class="sxs-lookup"><span data-stu-id="6fd4a-132">If you select **No**, enter a transaction date for the reversal.</span></span> 
- <span data-ttu-id="6fd4a-133">Ange en kommentar som beskriver återföringstransaktionen.</span><span class="sxs-lookup"><span data-stu-id="6fd4a-133">Enter a comment to describe the reversal transaction.</span></span>
- <span data-ttu-id="6fd4a-134">Välj knappen **Återför**.</span><span class="sxs-lookup"><span data-stu-id="6fd4a-134">Select the **Reverse** button.</span></span>

<span data-ttu-id="6fd4a-135">Transaktionerna kommer att återföras.</span><span class="sxs-lookup"><span data-stu-id="6fd4a-135">The transactions will be reversed.</span></span> 

<span data-ttu-id="6fd4a-136">Om det finns fler än 100 verifikationsrader, kommer återföringsprocessen att köras med batch-processen.</span><span class="sxs-lookup"><span data-stu-id="6fd4a-136">If there are more than 100 voucher lines, the reversal process will run using the batch process.</span></span> <span data-ttu-id="6fd4a-137">Du kan granska resultatet genom att visa kommentarerna i batch-jobbet.</span><span class="sxs-lookup"><span data-stu-id="6fd4a-137">You can review the results by viewing the comments in the batch job.</span></span> <span data-ttu-id="6fd4a-138">Alla transaktioner som inte kunde återföras antecknas i historiken för batchjobbet.</span><span class="sxs-lookup"><span data-stu-id="6fd4a-138">Any transactions that couldn't be reversed will be noted in the batch job history.</span></span>

<span data-ttu-id="6fd4a-139">Om antalet verifikationsrader är 100 rader eller färre, kommer återföringsprocessen att köras omedelbart.</span><span class="sxs-lookup"><span data-stu-id="6fd4a-139">If the number of voucher lines is 100 lines or fewer, the reversal process will run immediately.</span></span> <span data-ttu-id="6fd4a-140">Resultaten visas i en dialogruta som visar en verifikation som inte kan återföras och orsaken till varför.</span><span class="sxs-lookup"><span data-stu-id="6fd4a-140">The results will display in a dialog box that shows any voucher that couldn't be reversed, along with the reason why.</span></span> <span data-ttu-id="6fd4a-141">Välj **OK** för att stänga dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="6fd4a-141">Select **OK** to close the dialog box.</span></span>

<span data-ttu-id="6fd4a-142">Transaktioner kan bara återföras om de uppfyller affärsreglerna för att återföra dem.</span><span class="sxs-lookup"><span data-stu-id="6fd4a-142">Transactions can be reversed only if they meet the business rules for reversing them.</span></span> <span data-ttu-id="6fd4a-143">Leverantörsbetalningar kan inte återföras med funktionen som beskrivs i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="6fd4a-143">Vendor payments cannot be reversed using the capability described in this topic.</span></span> <span data-ttu-id="6fd4a-144">Leverantörsbetalningar måste återföras genom att följa stegen i [återför en leverantörsbetalning](https://docs.microsoft.com/dynamics365/finance/accounts-payable/reverse-vendor-payment).</span><span class="sxs-lookup"><span data-stu-id="6fd4a-144">Vendor payments must be reversed by following the steps listed in [Reverse a vendor payment](https://docs.microsoft.com/dynamics365/finance/accounts-payable/reverse-vendor-payment).</span></span>

