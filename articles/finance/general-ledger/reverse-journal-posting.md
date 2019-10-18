---
title: Återför journalbokföring
description: I det här avsnittet beskrivs funktioner som gör att du kan återföra verifikationer från en verifikationstransaktionslista eller från ekonomiska journaler.
author: MikeFalkner
manager: AnnBe
ms.date: 08/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerTransVoucher, LedgerJournalTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5a5456e60f1f3cee5f83ac7f725f7e01ba5bd7a1
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/30/2019
ms.locfileid: "2248595"
---
# <a name="reverse-journal-posting"></a><span data-ttu-id="48a5d-103">Återför journalbokföring</span><span class="sxs-lookup"><span data-stu-id="48a5d-103">Reverse journal posting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="48a5d-104">I det här avsnittet beskrivs Dynamics 365 Finance-funktioner i Microsoft som gör att du kan återföra en hel journal eller återföra en eller flera verifikationer från verifikationstransaktionslistan oavsett ursprung.</span><span class="sxs-lookup"><span data-stu-id="48a5d-104">This topic describes capabilities Microsoft Dynamics 365 Finance that allows you to reverse an entire journal or reverse one or more vouchers from the voucher transaction list regardless of their origin.</span></span> 

## <a name="reversing-journals"></a><span data-ttu-id="48a5d-105">Återföra journaler</span><span class="sxs-lookup"><span data-stu-id="48a5d-105">Reversing journals</span></span>

<span data-ttu-id="48a5d-106">Du kan återföra journalrader individuellt.</span><span class="sxs-lookup"><span data-stu-id="48a5d-106">You can reverse journal lines individually.</span></span> <span data-ttu-id="48a5d-107">Med en omvänd journalbokföring kan du även återföra en hel redovisningsjournal.</span><span class="sxs-lookup"><span data-stu-id="48a5d-107">With reverse journal posting, you can also reverse an entire financial journal.</span></span> <span data-ttu-id="48a5d-108">För att återföra en journal:</span><span class="sxs-lookup"><span data-stu-id="48a5d-108">To reverse a journal:</span></span> 
- <span data-ttu-id="48a5d-109">Öppna redovisningsjournalen och filtrera på bokförda journaler</span><span class="sxs-lookup"><span data-stu-id="48a5d-109">Open the financial journal and filter on posted journals</span></span>
- <span data-ttu-id="48a5d-110">Klicka på menyn Återför högst upp på sidan.</span><span class="sxs-lookup"><span data-stu-id="48a5d-110">Click on the Reverse menu at the top of the page</span></span>
- <span data-ttu-id="48a5d-111">Det totala antalet verifikationer och verifikationsrader samt det totala beloppet för raderna som återförts visas.</span><span class="sxs-lookup"><span data-stu-id="48a5d-111">You will see the total number of vouchers and voucher lines as well as the total amount of the lines being reversed</span></span>
- <span data-ttu-id="48a5d-112">Välj Ja om du vill använda de befintliga transaktionsdatumen eller Nej om du vill ange ett nytt.</span><span class="sxs-lookup"><span data-stu-id="48a5d-112">Select Yes to use the existing transaction dates or No to enter a new one.</span></span> <span data-ttu-id="48a5d-113">I vissa fall kan perioden för den ursprungliga transaktionen stängas och du vill ange ett nytt transaktionsdatum för återföringen.</span><span class="sxs-lookup"><span data-stu-id="48a5d-113">In some cases, the period of the original transaction may be closed and you want to enter a new transaction date for the reversal.</span></span>
- <span data-ttu-id="48a5d-114">Om du har valt nej anger du ett transaktionsdatum för återföringen.</span><span class="sxs-lookup"><span data-stu-id="48a5d-114">If you selected No, enter a transaction date for the reversal.</span></span> 
- <span data-ttu-id="48a5d-115">Ange en kommentar som du vill lägga till i återföringstransaktionen</span><span class="sxs-lookup"><span data-stu-id="48a5d-115">Enter a comment that you want added to the reversal transaction</span></span>
- <span data-ttu-id="48a5d-116">Klicka på knappen Återför.</span><span class="sxs-lookup"><span data-stu-id="48a5d-116">Click the Reverse button</span></span>

<span data-ttu-id="48a5d-117">Transaktionerna kommer att återföras.</span><span class="sxs-lookup"><span data-stu-id="48a5d-117">The transactions will be reversed.</span></span> 

<span data-ttu-id="48a5d-118">Om antalet verifikationsrader överstiger 100 rader, kommer återföringsprocessen att köras med batch-processen.</span><span class="sxs-lookup"><span data-stu-id="48a5d-118">If the number of voucher lines exceeds 100 lines, the reversal process will be run using the batch process.</span></span> <span data-ttu-id="48a5d-119">Du kan granska resultatet av återföringen genom att visa kommentarerna i batch-jobbet som kördes.</span><span class="sxs-lookup"><span data-stu-id="48a5d-119">You can review the results of the reversal by viewing the comments in the batch job that was run.</span></span> <span data-ttu-id="48a5d-120">Alla fel kommer att anges i historiken för batchjobb.</span><span class="sxs-lookup"><span data-stu-id="48a5d-120">All failures will be noted in the batch job history.</span></span>

<span data-ttu-id="48a5d-121">Om antalet verifikationsrader är 100 rader eller färre, kommer återföringsprocessen att köras omedelbart.</span><span class="sxs-lookup"><span data-stu-id="48a5d-121">If the number of voucher lines is 100 lines or less, the reversal process will run immediately.</span></span> <span data-ttu-id="48a5d-122">Resultaten visas i en dialogruta som visar en verifikation som inte kan återföras och orsaken till varför den inte kunde återföras.</span><span class="sxs-lookup"><span data-stu-id="48a5d-122">The results will be presented in a dialog that shows any voucher that could not be reversed and the reason why it could not be reversed.</span></span> <span data-ttu-id="48a5d-123">Klicka på Ok för att stänga dialogrutan</span><span class="sxs-lookup"><span data-stu-id="48a5d-123">Click on Ok to close the dialog.</span></span>

## <a name="reversing-vouchers-from-the-voucher-transaction-list"></a><span data-ttu-id="48a5d-124">Återför verifikationer från listan med verifikationstransaktioner.</span><span class="sxs-lookup"><span data-stu-id="48a5d-124">Reversing vouchers from the voucher transaction list.</span></span> 

<span data-ttu-id="48a5d-125">Du kan även återföra verifikationer från **transaktionslistan för verifikationer** i alla redovisningstransaktioner.</span><span class="sxs-lookup"><span data-stu-id="48a5d-125">You can also reverse vouchers from the **Voucher transaction list** across all subledgers.</span></span> <span data-ttu-id="48a5d-126">Dessutom kan du återföra fler än en verifikation åt gången.</span><span class="sxs-lookup"><span data-stu-id="48a5d-126">In addition, you can reverse more than one voucher at a time.</span></span> 

<span data-ttu-id="48a5d-127">Så här återför du en eller flera verifikationer:</span><span class="sxs-lookup"><span data-stu-id="48a5d-127">To reverse one or more vouchers:</span></span> 
- <span data-ttu-id="48a5d-128">Klicka på menyn Återför högst upp på sidan.</span><span class="sxs-lookup"><span data-stu-id="48a5d-128">Click on the Reverse menu at the top of the page</span></span>
- <span data-ttu-id="48a5d-129">Det totala antalet verifikationer och verifikationsrader samt det totala beloppet för raderna som återförts visas.</span><span class="sxs-lookup"><span data-stu-id="48a5d-129">You will see the total number of vouchers and voucher lines as well as the total amount of the lines being reversed</span></span>
- <span data-ttu-id="48a5d-130">Välj Ja om du vill använda de befintliga transaktionsdatumen eller Nej om du vill ange ett nytt.</span><span class="sxs-lookup"><span data-stu-id="48a5d-130">Select Yes to use the existing transaction dates or No to enter a new one.</span></span> <span data-ttu-id="48a5d-131">I vissa fall kan perioden för den ursprungliga transaktionen stängas och du vill ange ett nytt transaktionsdatum för återföringen.</span><span class="sxs-lookup"><span data-stu-id="48a5d-131">In some cases, the period of the original transaction may be closed and you want to enter a new transaction date for the reversal.</span></span>
- <span data-ttu-id="48a5d-132">Om du har valt nej anger du ett transaktionsdatum för återföringen.</span><span class="sxs-lookup"><span data-stu-id="48a5d-132">If you selected No, enter a transaction date for the reversal.</span></span> 
- <span data-ttu-id="48a5d-133">Ange en kommentar som du vill lägga till i återföringstransaktionen</span><span class="sxs-lookup"><span data-stu-id="48a5d-133">Enter a comment that you want added to the reversal transaction</span></span>
- <span data-ttu-id="48a5d-134">Klicka på knappen Återför.</span><span class="sxs-lookup"><span data-stu-id="48a5d-134">Click the Reverse button</span></span>

<span data-ttu-id="48a5d-135">Transaktionerna kommer att återföras.</span><span class="sxs-lookup"><span data-stu-id="48a5d-135">The transactions will be reversed.</span></span> 

<span data-ttu-id="48a5d-136">Om antalet verifikationsrader överstiger 100 rader, kommer återföringsprocessen att köras med batch-processen.</span><span class="sxs-lookup"><span data-stu-id="48a5d-136">If the number of voucher lines exceeds 100 lines, the reversal process will be run using the batch process.</span></span> <span data-ttu-id="48a5d-137">Du kan granska resultatet av återföringen genom att visa kommentarerna i batch-jobbet som kördes.</span><span class="sxs-lookup"><span data-stu-id="48a5d-137">You can review the results of the reversal by viewing the comments in the batch job that was run.</span></span> <span data-ttu-id="48a5d-138">Alla fel kommer att anges i historiken för batchjobb.</span><span class="sxs-lookup"><span data-stu-id="48a5d-138">All failures will be noted in the batch job history.</span></span>

<span data-ttu-id="48a5d-139">Om antalet verifikationsrader är 100 rader eller färre, kommer återföringsprocessen att köras omedelbart.</span><span class="sxs-lookup"><span data-stu-id="48a5d-139">If the number of voucher lines is 100 lines or less, the reversal process will run immediately.</span></span> <span data-ttu-id="48a5d-140">Resultaten visas i en dialogruta som visar en verifikation som inte kan återföras och orsaken till varför den inte kunde återföras.</span><span class="sxs-lookup"><span data-stu-id="48a5d-140">The results will be presented in a dialog that shows any voucher that could not be reversed and the reason why it could not be reversed.</span></span> <span data-ttu-id="48a5d-141">Klicka på Ok för att stänga dialogrutan</span><span class="sxs-lookup"><span data-stu-id="48a5d-141">Click on Ok to close the dialog.</span></span>

