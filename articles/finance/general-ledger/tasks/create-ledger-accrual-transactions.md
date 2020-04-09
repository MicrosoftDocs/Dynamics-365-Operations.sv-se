---
title: Skapa periodiseringtransaktioner i redovisningen
description: Stegen i den här guiden beskriver hur du genererar periodiseringstransaktioner för redovisning som baseras på periodiseringsscheman.
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransDaily, LedgerJournalTransAccrual, LedgerJournalTransAccrualTrans
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2112336045086d0eb3b2fb0018f33631528a05ec
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3145109"
---
# <a name="create-ledger-accrual-transactions"></a><span data-ttu-id="74da5-103">Skapa periodiseringtransaktioner i redovisningen</span><span class="sxs-lookup"><span data-stu-id="74da5-103">Create ledger accrual transactions</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="74da5-104">Stegen i den här guiden beskriver hur du genererar periodiseringstransaktioner för redovisning som baseras på periodiseringsscheman</span><span class="sxs-lookup"><span data-stu-id="74da5-104">This task guide steps through generating ledger accrual transactions that are based on accrual schemes</span></span>

1. <span data-ttu-id="74da5-105">Gå till Redovisning > Journalposter > Allmänna journaler.</span><span class="sxs-lookup"><span data-stu-id="74da5-105">Go to General ledger > Journal entries > General journals.</span></span>
2. <span data-ttu-id="74da5-106">I listan letar du upp och väljer önskad journal eller skapar en ny.</span><span class="sxs-lookup"><span data-stu-id="74da5-106">In the list, find and select the desired journal or create a new one.</span></span>
3. <span data-ttu-id="74da5-107">Klicka för att följa länken i fältet Journalbatchnummer.</span><span class="sxs-lookup"><span data-stu-id="74da5-107">Click to follow the link in the Journal batch number field.</span></span>
4. <span data-ttu-id="74da5-108">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="74da5-108">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="74da5-109">Ange önskade värden i fältet Konto.</span><span class="sxs-lookup"><span data-stu-id="74da5-109">In the Account field, specify the desired values.</span></span>
    * <span data-ttu-id="74da5-110">I det här exemplet definierar vi utgifterna för försäkringen.</span><span class="sxs-lookup"><span data-stu-id="74da5-110">In this example, we are defining the expense for the insurance.</span></span> <span data-ttu-id="74da5-111">Det blir ett periodiskt utgiftbelopp.</span><span class="sxs-lookup"><span data-stu-id="74da5-111">It will be come periodic expense amount.</span></span>  
6. <span data-ttu-id="74da5-112">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="74da5-112">In the Description field, type a value.</span></span>
7. <span data-ttu-id="74da5-113">Ange ett tal i fältet Debet.</span><span class="sxs-lookup"><span data-stu-id="74da5-113">In the Debit field, enter a number.</span></span>
8. <span data-ttu-id="74da5-114">Ange önskade värden i fältet Motkonto.</span><span class="sxs-lookup"><span data-stu-id="74da5-114">In the Offset account field, specify the desired values.</span></span>
9. <span data-ttu-id="74da5-115">Klicka på Funktioner.</span><span class="sxs-lookup"><span data-stu-id="74da5-115">Click Functions.</span></span>
10. <span data-ttu-id="74da5-116">Klicka på Periodiseringar.</span><span class="sxs-lookup"><span data-stu-id="74da5-116">Click Ledger accruals.</span></span>
11. <span data-ttu-id="74da5-117">I fältet Identifiering av periodisering öppnar du sökningen genom att klicka på den nedrullningsbara knappen.</span><span class="sxs-lookup"><span data-stu-id="74da5-117">In the Accrual identification field, click the drop-down button to open the lookup.</span></span>
12. <span data-ttu-id="74da5-118">I listan letar du upp och väljer det periodiseringsschema som du vill använda.</span><span class="sxs-lookup"><span data-stu-id="74da5-118">In the list, find and select the accural scheme you want to apply.</span></span>
13. <span data-ttu-id="74da5-119">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="74da5-119">In the list, click the link in the selected row.</span></span>
14. <span data-ttu-id="74da5-120">Ange ett datum i fältet Startdatum.</span><span class="sxs-lookup"><span data-stu-id="74da5-120">In the Start date field, enter a date.</span></span>
15. <span data-ttu-id="74da5-121">Klicka på Transaktioner.</span><span class="sxs-lookup"><span data-stu-id="74da5-121">Click Transactions.</span></span>
16. <span data-ttu-id="74da5-122">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="74da5-122">Close the page.</span></span>
17. <span data-ttu-id="74da5-123">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="74da5-123">Click OK.</span></span>
18. <span data-ttu-id="74da5-124">Klicka på Bokför.</span><span class="sxs-lookup"><span data-stu-id="74da5-124">Click Post.</span></span>

