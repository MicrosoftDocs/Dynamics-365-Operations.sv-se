---
title: Stäm av fraktsedel manuellt
description: I den här proceduren visas hur du stämmer av frakt manuellt.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLoadPlanningWorkbench, TMSFreightBillDetail, TMSInvoiceTable, TMSFreightBillInvoiceReconcile, TMSInvoiceJournal, LedgerJournalTable, LedgerJournalTransDaily
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ec17fc31df1daed943f9bc3f4cbe25a683c8ac7e
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/05/2020
ms.locfileid: "3026324"
---
# <a name="reconcile-freight-manually"></a><span data-ttu-id="6aee9-103">Stäm av fraktsedel manuellt</span><span class="sxs-lookup"><span data-stu-id="6aee9-103">Reconcile freight manually</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="6aee9-104">I den här proceduren visas hur du stämmer av frakt manuellt.</span><span class="sxs-lookup"><span data-stu-id="6aee9-104">This procedure shows how to reconcile freight manually.</span></span> <span data-ttu-id="6aee9-105">Detta görs normalt av en transportkoordinator.</span><span class="sxs-lookup"><span data-stu-id="6aee9-105">This is typically done by a transportation coordinator.</span></span> <span data-ttu-id="6aee9-106">Du kan använda den här proceduren i demonstrationsdataföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="6aee9-106">You can use this procedure in the USMF demo data company.</span></span>


## <a name="select-a-load-to-reconcile"></a><span data-ttu-id="6aee9-107">Välj en beläggning att stämma av</span><span class="sxs-lookup"><span data-stu-id="6aee9-107">Select a load to reconcile</span></span>
1. <span data-ttu-id="6aee9-108">Gå till Transporthantering > Planering > Workbench för lastplanering.</span><span class="sxs-lookup"><span data-stu-id="6aee9-108">Go to Transportation management > Planning > Load planning workbench.</span></span>
2. <span data-ttu-id="6aee9-109">Avmarkera kryssrutan Clear the Hide shipped and received.</span><span class="sxs-lookup"><span data-stu-id="6aee9-109">Clear the Hide shipped and received check box.</span></span> 
3. <span data-ttu-id="6aee9-110">Välj beläggningen som har beläggningen ID 00006 i listan.</span><span class="sxs-lookup"><span data-stu-id="6aee9-110">In the list, select the load that has load ID 00006.</span></span>

## <a name="create-a-carrier-invoice"></a><span data-ttu-id="6aee9-111">Skapa en transportföretagsfaktura</span><span class="sxs-lookup"><span data-stu-id="6aee9-111">Create a carrier invoice</span></span>
<span data-ttu-id="6aee9-112">Om du stämmer av frakten manuellt och inte får transportfakturor automatiskt, kan du skapa en faktura baserat på frakträkningen.</span><span class="sxs-lookup"><span data-stu-id="6aee9-112">If you reconcile freight manually and don’t receive carrier invoices automatically, you can create an invoice based on the freight bill.</span></span>  
1. <span data-ttu-id="6aee9-113">Klicka på Relaterad information.</span><span class="sxs-lookup"><span data-stu-id="6aee9-113">Click Related information.</span></span>
2. <span data-ttu-id="6aee9-114">Klicka på Freight bill details.</span><span class="sxs-lookup"><span data-stu-id="6aee9-114">Click Freight bill details.</span></span>
3. <span data-ttu-id="6aee9-115">Klicka på Generate freight bill invoice.</span><span class="sxs-lookup"><span data-stu-id="6aee9-115">Click Generate freight bill invoice.</span></span>
4. <span data-ttu-id="6aee9-116">Ange ett värde i fältet Faktura.</span><span class="sxs-lookup"><span data-stu-id="6aee9-116">In the Invoice field, type a value.</span></span>
5. <span data-ttu-id="6aee9-117">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="6aee9-117">Click OK.</span></span>

## <a name="reconcile-the-invoice"></a><span data-ttu-id="6aee9-118">Stäm av fakturan</span><span class="sxs-lookup"><span data-stu-id="6aee9-118">Reconcile the invoice</span></span>
<span data-ttu-id="6aee9-119">När du stämmer av en transportföretagsfaktura och en frakträkning görs detta rad för rad.</span><span class="sxs-lookup"><span data-stu-id="6aee9-119">When you reconcile a carrier invoice and a freight bill, this is done line by line.</span></span>  
1. <span data-ttu-id="6aee9-120">Klicka på Match freight bills and invoices.</span><span class="sxs-lookup"><span data-stu-id="6aee9-120">Click Match freight bills and invoices.</span></span>
2. <span data-ttu-id="6aee9-121">Expandera avsnittet Invoice details.</span><span class="sxs-lookup"><span data-stu-id="6aee9-121">Expand the Invoice details section.</span></span>
3. <span data-ttu-id="6aee9-122">Expandera avsnittet Unmatched freight bill details.</span><span class="sxs-lookup"><span data-stu-id="6aee9-122">Expand the Unmatched freight bill details section.</span></span>
4. <span data-ttu-id="6aee9-123">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="6aee9-123">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="6aee9-124">Klicka på Match.</span><span class="sxs-lookup"><span data-stu-id="6aee9-124">Click Match.</span></span>
6. <span data-ttu-id="6aee9-125">Expandera avsnittet Matched freight bill details.</span><span class="sxs-lookup"><span data-stu-id="6aee9-125">Expand the Matched freight bill details section.</span></span>

## <a name="submit-the-invoice-for-approval"></a><span data-ttu-id="6aee9-126">Skicka fakturan för godkännande</span><span class="sxs-lookup"><span data-stu-id="6aee9-126">Submit the invoice for approval</span></span>
1. <span data-ttu-id="6aee9-127">Klicka på Submit for approval.</span><span class="sxs-lookup"><span data-stu-id="6aee9-127">Click Submit for approval.</span></span>
2. <span data-ttu-id="6aee9-128">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="6aee9-128">Close the page.</span></span>
3. <span data-ttu-id="6aee9-129">Rensa kryssrutan Hide approved.</span><span class="sxs-lookup"><span data-stu-id="6aee9-129">Clear the Hide approved check box.</span></span> 
4. <span data-ttu-id="6aee9-130">Klicka på Vendor invoice journals.</span><span class="sxs-lookup"><span data-stu-id="6aee9-130">Click Vendor invoice journals.</span></span>
5. <span data-ttu-id="6aee9-131">Klicka för att följa länken i fältet Reference journal number.</span><span class="sxs-lookup"><span data-stu-id="6aee9-131">Click to follow the link in the Reference journal number field.</span></span>
6. <span data-ttu-id="6aee9-132">Klicka på Rader.</span><span class="sxs-lookup"><span data-stu-id="6aee9-132">Click Lines.</span></span>

