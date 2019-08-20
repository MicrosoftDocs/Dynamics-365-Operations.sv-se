---
title: Bearbeta journal för redovisningsallokering
description: Använd sidan Bearbeta allokeringsbegäran för att skapa en allokeringsjournal som kan granskas och godkännas före bokföringen, eller bokföras direkt i redovisningen.
author: aprilolson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerAllocationRequest, LedgerJournalTable, LedgerJournalTransAllocation
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 087bd4f203e8762447e823b19076b79296a390d6
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2019
ms.locfileid: "1846377"
---
# <a name="process-ledger-allocation-journal"></a><span data-ttu-id="3b506-103">Bearbeta journal för redovisningsallokering</span><span class="sxs-lookup"><span data-stu-id="3b506-103">Process ledger allocation journal</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="3b506-104">Använd sidan Bearbeta allokeringsbegäran för att skapa en allokeringsjournal som kan granskas och godkännas före bokföringen, eller bokföras direkt i redovisningen.</span><span class="sxs-lookup"><span data-stu-id="3b506-104">Use the Process allocation request page to create an allocation journal that can be reviewed and approved before posting to General ledger, or posted directly to General ledger.</span></span> <span data-ttu-id="3b506-105">Innan du kan skapa en allokeringsjournal måste det finnas minst en aktiv redovisningsallokeringsregel.</span><span class="sxs-lookup"><span data-stu-id="3b506-105">Before you can create an allocations journal, there must be least one active Ledger allocation rule.</span></span> <span data-ttu-id="3b506-106">I den här uppgiften används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="3b506-106">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="3b506-107">Gå till Redovisning > Allokeringar > Bearbeta allokeringsbegäran.</span><span class="sxs-lookup"><span data-stu-id="3b506-107">Go to General ledger > Allocations > Process allocation request.</span></span>
2. <span data-ttu-id="3b506-108">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Regel.</span><span class="sxs-lookup"><span data-stu-id="3b506-108">In the Rule field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="3b506-109">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="3b506-109">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="3b506-110">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="3b506-110">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="3b506-111">Ange ett datum i fältet Från och med (datum).</span><span class="sxs-lookup"><span data-stu-id="3b506-111">In the As of date field, enter a date.</span></span>
    * <span data-ttu-id="3b506-112">Från och med-datumet är mycket viktigt när redovisningen är datakällan för regeln.</span><span class="sxs-lookup"><span data-stu-id="3b506-112">The As of Date is very important when the Ledger is the Data source for the rule.</span></span> <span data-ttu-id="3b506-113">Detta datum styr vilka redovisningssaldon som ska inkluderas för allokering.</span><span class="sxs-lookup"><span data-stu-id="3b506-113">This date controls which ledger balances to include for allocation.</span></span>     <span data-ttu-id="3b506-114">I fältet Noll urspr.belopp väljer du Stoppa.</span><span class="sxs-lookup"><span data-stu-id="3b506-114">In the Zero source field select Stop.</span></span> <span data-ttu-id="3b506-115">När du gör det stoppas allokeringsprocessen och ett meddelande visa som anger att ett nollbelopp har valts.</span><span class="sxs-lookup"><span data-stu-id="3b506-115">This will  Stop the allocation process and display a message that states that a zero source amount is selected.</span></span>  
6. <span data-ttu-id="3b506-116">Välj Enbart förslag i fältet Förslagsalternativ.</span><span class="sxs-lookup"><span data-stu-id="3b506-116">In the Proposal options field, select 'Proposal only'.</span></span>
    * <span data-ttu-id="3b506-117">Välj Enbart förslag för att granska och eventuellt godkänna resultatet i allokeringsjournalerna innan du bokför allokeringen i redovisningen.</span><span class="sxs-lookup"><span data-stu-id="3b506-117">Select Proposal only to review and optionally approve the result in Allocation journals prior to posting the allocation to General ledger.</span></span>  
7. <span data-ttu-id="3b506-118">Ange ett datum i fältet Datum för bokföring i huvudbok.</span><span class="sxs-lookup"><span data-stu-id="3b506-118">In the GL posting date field, enter a date.</span></span>
8. <span data-ttu-id="3b506-119">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="3b506-119">Click OK.</span></span>
9. <span data-ttu-id="3b506-120">Gå till Redovisning > Allokeringar > Allokeringsjournaler.</span><span class="sxs-lookup"><span data-stu-id="3b506-120">Go to General ledger > Allocations > Allocation journals.</span></span>
10. <span data-ttu-id="3b506-121">Klicka på Rader.</span><span class="sxs-lookup"><span data-stu-id="3b506-121">Click Lines.</span></span>
11. <span data-ttu-id="3b506-122">Klicka på Bokför.</span><span class="sxs-lookup"><span data-stu-id="3b506-122">Click Post.</span></span>
12. <span data-ttu-id="3b506-123">Klicka på Bokför.</span><span class="sxs-lookup"><span data-stu-id="3b506-123">Click Post.</span></span>

