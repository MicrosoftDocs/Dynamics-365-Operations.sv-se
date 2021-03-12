---
title: Bearbeta journal för redovisningsallokering
description: I det här avsnittet beskrivs hur du bearbetar en begäran om tilldelning i Dynamics 365 Finance.
author: aprilolson
manager: AnnBe
ms.date: 07/26/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerAllocationRequest, LedgerJournalTable, LedgerJournalTransAllocation
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0a7e8c3ef6fa85daec2a191b433b1ec4ece441ee
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4968489"
---
# <a name="process-ledger-allocation-journal"></a><span data-ttu-id="ba0bf-103">Bearbeta journal för redovisningsallokering</span><span class="sxs-lookup"><span data-stu-id="ba0bf-103">Process ledger allocation journal</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ba0bf-104">I det här avsnittet beskrivs hur du bearbetar en begäran om tilldelning.</span><span class="sxs-lookup"><span data-stu-id="ba0bf-104">This topic explains how to process an allocation request.</span></span> <span data-ttu-id="ba0bf-105">Använd sidan Bearbeta allokeringsbegäran för att skapa en allokeringsjournal som kan granskas och godkännas före bokföringen, eller bokföras direkt i redovisningen.</span><span class="sxs-lookup"><span data-stu-id="ba0bf-105">Use the Process allocation request page to create an allocation journal that can be reviewed and approved before posting to General ledger, or posted directly to General ledger.</span></span> <span data-ttu-id="ba0bf-106">Innan du kan skapa en allokeringsjournal måste det finnas minst en aktiv redovisningsallokeringsregel.</span><span class="sxs-lookup"><span data-stu-id="ba0bf-106">Before you can create an allocations journal, there must be least one active Ledger allocation rule.</span></span> <span data-ttu-id="ba0bf-107">I den här uppgiften används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="ba0bf-107">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="ba0bf-108">I navigeringsfönstret, gå till **Moduler > Redovisning > Allokeringar > Bearbeta allokeringsbegäran**.</span><span class="sxs-lookup"><span data-stu-id="ba0bf-108">In the navigation pane, go to **Modules > General ledger > Allocations > Process allocation request**.</span></span>
2. <span data-ttu-id="ba0bf-109">I fältet **Regel** väljer du önskad post i listrutan.</span><span class="sxs-lookup"><span data-stu-id="ba0bf-109">In the **Rule** field, select the desired record in the drop-down menu.</span></span>
3. <span data-ttu-id="ba0bf-110">Ange ett datum i fältet **Från och med (datum).**</span><span class="sxs-lookup"><span data-stu-id="ba0bf-110">In the **As of date** field, enter a date.</span></span>

    - <span data-ttu-id="ba0bf-111">**Från och med**-datumet är mycket viktigt när redovisningen är datakällan för regeln.</span><span class="sxs-lookup"><span data-stu-id="ba0bf-111">The **As of Date** is very important when the Ledger is the Data source for the rule.</span></span> <span data-ttu-id="ba0bf-112">Detta datum styr vilka redovisningssaldon som ska inkluderas för allokering.</span><span class="sxs-lookup"><span data-stu-id="ba0bf-112">This date controls which ledger balances to include for allocation.</span></span>  
    - <span data-ttu-id="ba0bf-113">I fältet **Noll urspr.belopp** väljer du **Stoppa**.</span><span class="sxs-lookup"><span data-stu-id="ba0bf-113">In the **Zero source** field select **Stop**.</span></span> <span data-ttu-id="ba0bf-114">När du gör det stoppas allokeringsprocessen och ett meddelande visa som anger att ett nollbelopp har valts.</span><span class="sxs-lookup"><span data-stu-id="ba0bf-114">This will stop the allocation process and display a message that states that a zero source amount is selected.</span></span>  

4. <span data-ttu-id="ba0bf-115">Välj **Enbart förslag** i fältet **Förslagsalternativ**.</span><span class="sxs-lookup"><span data-stu-id="ba0bf-115">In the **Proposal options** field, select **Proposal only**.</span></span> <span data-ttu-id="ba0bf-116">Välj **Enbart förslag** för att granska och eventuellt godkänna resultatet i allokeringsjournalerna innan du bokför allokeringen i redovisningen.</span><span class="sxs-lookup"><span data-stu-id="ba0bf-116">Select **Proposal only** to review and optionally approve the result in Allocation journals prior to posting the allocation to General ledger.</span></span>  
5. <span data-ttu-id="ba0bf-117">Ange ett datum i fältet Datum för bokföring i huvudbok.</span><span class="sxs-lookup"><span data-stu-id="ba0bf-117">In the GL posting date field, enter a date.</span></span>
6. <span data-ttu-id="ba0bf-118">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="ba0bf-118">Select **OK**.</span></span>
7. <span data-ttu-id="ba0bf-119">I navigeringsfönstret, gå till **Moduler > Redovisning > Allokeringar > Allokeringsjournaler**.</span><span class="sxs-lookup"><span data-stu-id="ba0bf-119">In the navigation pane, go to **Modules > General ledger > Allocations > Allocation journals**.</span></span>
8. <span data-ttu-id="ba0bf-120">Markera **rader**</span><span class="sxs-lookup"><span data-stu-id="ba0bf-120">Select **Lines**.</span></span>
9. <span data-ttu-id="ba0bf-121">Vald **bokföring**</span><span class="sxs-lookup"><span data-stu-id="ba0bf-121">Select **Post**.</span></span>
10. <span data-ttu-id="ba0bf-122">Vald **bokföring**</span><span class="sxs-lookup"><span data-stu-id="ba0bf-122">Select **Post**.</span></span>

