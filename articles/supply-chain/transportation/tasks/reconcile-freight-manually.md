---
title: Stäm av fraktsedel manuellt
description: I den här proceduren visas hur du stämmer av frakt manuellt.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLoadPlanningWorkbench, TMSFreightBillDetail, TMSInvoiceTable, TMSFreightBillInvoiceReconcile, TMSInvoiceJournal, LedgerJournalTable, LedgerJournalTransDaily, TMSFBDetailReconcile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: becda50b5d176ceb350c471b154aed1842c31a3b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5247200"
---
# <a name="reconcile-freight-manually"></a><span data-ttu-id="e370d-103">Stäm av fraktsedel manuellt</span><span class="sxs-lookup"><span data-stu-id="e370d-103">Reconcile freight manually</span></span>

<span data-ttu-id="e370d-104">[!include [banner](../../includes/banner.md)]]</span><span class="sxs-lookup"><span data-stu-id="e370d-104">[!include [banner](../../includes/banner.md)]]</span></span>

<span data-ttu-id="e370d-105">I den här proceduren visas hur du stämmer av frakt manuellt.</span><span class="sxs-lookup"><span data-stu-id="e370d-105">This procedure shows how to reconcile freight manually.</span></span> <span data-ttu-id="e370d-106">Detta görs normalt av en transportkoordinator.</span><span class="sxs-lookup"><span data-stu-id="e370d-106">This is typically done by a transportation coordinator.</span></span> <span data-ttu-id="e370d-107">Du kan använda den här proceduren i demonstrationsdataföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="e370d-107">You can use this procedure in the USMF demo data company.</span></span>


## <a name="select-a-load-to-reconcile"></a><span data-ttu-id="e370d-108">Välj en beläggning att stämma av</span><span class="sxs-lookup"><span data-stu-id="e370d-108">Select a load to reconcile</span></span>
1. <span data-ttu-id="e370d-109">Gå till Transporthantering > Planering > Workbench för lastplanering.</span><span class="sxs-lookup"><span data-stu-id="e370d-109">Go to Transportation management > Planning > Load planning workbench.</span></span>
2. <span data-ttu-id="e370d-110">Avmarkera kryssrutan Clear the Hide shipped and received.</span><span class="sxs-lookup"><span data-stu-id="e370d-110">Clear the Hide shipped and received check box.</span></span> 
3. <span data-ttu-id="e370d-111">Välj beläggningen som har beläggningen ID 00006 i listan.</span><span class="sxs-lookup"><span data-stu-id="e370d-111">In the list, select the load that has load ID 00006.</span></span>

## <a name="create-a-carrier-invoice"></a><span data-ttu-id="e370d-112">Skapa en transportföretagsfaktura</span><span class="sxs-lookup"><span data-stu-id="e370d-112">Create a carrier invoice</span></span>
<span data-ttu-id="e370d-113">Om du stämmer av frakten manuellt och inte får transportfakturor automatiskt, kan du skapa en faktura baserat på frakträkningen.</span><span class="sxs-lookup"><span data-stu-id="e370d-113">If you reconcile freight manually and don't receive carrier invoices automatically, you can create an invoice based on the freight bill.</span></span>  
1. <span data-ttu-id="e370d-114">Klicka på Relaterad information.</span><span class="sxs-lookup"><span data-stu-id="e370d-114">Click Related information.</span></span>
2. <span data-ttu-id="e370d-115">Klicka på Freight bill details.</span><span class="sxs-lookup"><span data-stu-id="e370d-115">Click Freight bill details.</span></span>
3. <span data-ttu-id="e370d-116">Klicka på Generate freight bill invoice.</span><span class="sxs-lookup"><span data-stu-id="e370d-116">Click Generate freight bill invoice.</span></span>
4. <span data-ttu-id="e370d-117">Ange ett värde i fältet Faktura.</span><span class="sxs-lookup"><span data-stu-id="e370d-117">In the Invoice field, type a value.</span></span>
5. <span data-ttu-id="e370d-118">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="e370d-118">Click OK.</span></span>

## <a name="reconcile-the-invoice"></a><span data-ttu-id="e370d-119">Stäm av fakturan</span><span class="sxs-lookup"><span data-stu-id="e370d-119">Reconcile the invoice</span></span>
<span data-ttu-id="e370d-120">När du stämmer av en transportföretagsfaktura och en frakträkning görs detta rad för rad.</span><span class="sxs-lookup"><span data-stu-id="e370d-120">When you reconcile a carrier invoice and a freight bill, this is done line by line.</span></span>  
1. <span data-ttu-id="e370d-121">Klicka på Match freight bills and invoices.</span><span class="sxs-lookup"><span data-stu-id="e370d-121">Click Match freight bills and invoices.</span></span>
2. <span data-ttu-id="e370d-122">Expandera avsnittet Invoice details.</span><span class="sxs-lookup"><span data-stu-id="e370d-122">Expand the Invoice details section.</span></span>
3. <span data-ttu-id="e370d-123">Expandera avsnittet Unmatched freight bill details.</span><span class="sxs-lookup"><span data-stu-id="e370d-123">Expand the Unmatched freight bill details section.</span></span>
4. <span data-ttu-id="e370d-124">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="e370d-124">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="e370d-125">Klicka på Match.</span><span class="sxs-lookup"><span data-stu-id="e370d-125">Click Match.</span></span>
6. <span data-ttu-id="e370d-126">Expandera avsnittet Matched freight bill details.</span><span class="sxs-lookup"><span data-stu-id="e370d-126">Expand the Matched freight bill details section.</span></span>

## <a name="submit-the-invoice-for-approval"></a><span data-ttu-id="e370d-127">Skicka fakturan för godkännande</span><span class="sxs-lookup"><span data-stu-id="e370d-127">Submit the invoice for approval</span></span>
1. <span data-ttu-id="e370d-128">Klicka på Submit for approval.</span><span class="sxs-lookup"><span data-stu-id="e370d-128">Click Submit for approval.</span></span>
2. <span data-ttu-id="e370d-129">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="e370d-129">Close the page.</span></span>
3. <span data-ttu-id="e370d-130">Rensa kryssrutan Hide approved.</span><span class="sxs-lookup"><span data-stu-id="e370d-130">Clear the Hide approved check box.</span></span> 
4. <span data-ttu-id="e370d-131">Klicka på Vendor invoice journals.</span><span class="sxs-lookup"><span data-stu-id="e370d-131">Click Vendor invoice journals.</span></span>
5. <span data-ttu-id="e370d-132">Klicka för att följa länken i fältet Reference journal number.</span><span class="sxs-lookup"><span data-stu-id="e370d-132">Click to follow the link in the Reference journal number field.</span></span>
6. <span data-ttu-id="e370d-133">Klicka på Rader.</span><span class="sxs-lookup"><span data-stu-id="e370d-133">Click Lines.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]