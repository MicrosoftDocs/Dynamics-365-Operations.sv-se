---
title: Stäm av fraktsedel manuellt
description: I den här proceduren visas hur du stämmer av frakt manuellt.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLoadPlanningWorkbench, TMSFreightBillDetail, TMSInvoiceTable, TMSFreightBillInvoiceReconcile, TMSInvoiceJournal, LedgerJournalTable, LedgerJournalTransDaily, TMSFBDetailReconcile
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0a0a5450697a09e5e54e74b35b2576eb6bbd4cdf
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5838524"
---
# <a name="reconcile-freight-manually"></a><span data-ttu-id="f1986-103">Stäm av fraktsedel manuellt</span><span class="sxs-lookup"><span data-stu-id="f1986-103">Reconcile freight manually</span></span>

<span data-ttu-id="f1986-104">[!include [banner](../../includes/banner.md)]]</span><span class="sxs-lookup"><span data-stu-id="f1986-104">[!include [banner](../../includes/banner.md)]]</span></span>

<span data-ttu-id="f1986-105">I den här proceduren visas hur du stämmer av frakt manuellt.</span><span class="sxs-lookup"><span data-stu-id="f1986-105">This procedure shows how to reconcile freight manually.</span></span> <span data-ttu-id="f1986-106">Detta görs normalt av en transportkoordinator.</span><span class="sxs-lookup"><span data-stu-id="f1986-106">This is typically done by a transportation coordinator.</span></span> <span data-ttu-id="f1986-107">Du kan använda den här proceduren i demonstrationsdataföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="f1986-107">You can use this procedure in the USMF demo data company.</span></span>


## <a name="select-a-load-to-reconcile"></a><span data-ttu-id="f1986-108">Välj en beläggning att stämma av</span><span class="sxs-lookup"><span data-stu-id="f1986-108">Select a load to reconcile</span></span>
1. <span data-ttu-id="f1986-109">Gå till Transporthantering > Planering > Workbench för lastplanering.</span><span class="sxs-lookup"><span data-stu-id="f1986-109">Go to Transportation management > Planning > Load planning workbench.</span></span>
2. <span data-ttu-id="f1986-110">Avmarkera kryssrutan Clear the Hide shipped and received.</span><span class="sxs-lookup"><span data-stu-id="f1986-110">Clear the Hide shipped and received check box.</span></span> 
3. <span data-ttu-id="f1986-111">Välj beläggningen som har beläggningen ID 00006 i listan.</span><span class="sxs-lookup"><span data-stu-id="f1986-111">In the list, select the load that has load ID 00006.</span></span>

## <a name="create-a-carrier-invoice"></a><span data-ttu-id="f1986-112">Skapa en transportföretagsfaktura</span><span class="sxs-lookup"><span data-stu-id="f1986-112">Create a carrier invoice</span></span>
<span data-ttu-id="f1986-113">Om du stämmer av frakten manuellt och inte får transportfakturor automatiskt, kan du skapa en faktura baserat på frakträkningen.</span><span class="sxs-lookup"><span data-stu-id="f1986-113">If you reconcile freight manually and don't receive carrier invoices automatically, you can create an invoice based on the freight bill.</span></span>  
1. <span data-ttu-id="f1986-114">Klicka på Relaterad information.</span><span class="sxs-lookup"><span data-stu-id="f1986-114">Click Related information.</span></span>
2. <span data-ttu-id="f1986-115">Klicka på Freight bill details.</span><span class="sxs-lookup"><span data-stu-id="f1986-115">Click Freight bill details.</span></span>
3. <span data-ttu-id="f1986-116">Klicka på Generate freight bill invoice.</span><span class="sxs-lookup"><span data-stu-id="f1986-116">Click Generate freight bill invoice.</span></span>
4. <span data-ttu-id="f1986-117">Ange ett värde i fältet Faktura.</span><span class="sxs-lookup"><span data-stu-id="f1986-117">In the Invoice field, type a value.</span></span>
5. <span data-ttu-id="f1986-118">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="f1986-118">Click OK.</span></span>

## <a name="reconcile-the-invoice"></a><span data-ttu-id="f1986-119">Stäm av fakturan</span><span class="sxs-lookup"><span data-stu-id="f1986-119">Reconcile the invoice</span></span>
<span data-ttu-id="f1986-120">När du stämmer av en transportföretagsfaktura och en frakträkning görs detta rad för rad.</span><span class="sxs-lookup"><span data-stu-id="f1986-120">When you reconcile a carrier invoice and a freight bill, this is done line by line.</span></span>  
1. <span data-ttu-id="f1986-121">Klicka på Match freight bills and invoices.</span><span class="sxs-lookup"><span data-stu-id="f1986-121">Click Match freight bills and invoices.</span></span>
2. <span data-ttu-id="f1986-122">Expandera avsnittet Invoice details.</span><span class="sxs-lookup"><span data-stu-id="f1986-122">Expand the Invoice details section.</span></span>
3. <span data-ttu-id="f1986-123">Expandera avsnittet Unmatched freight bill details.</span><span class="sxs-lookup"><span data-stu-id="f1986-123">Expand the Unmatched freight bill details section.</span></span>
4. <span data-ttu-id="f1986-124">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="f1986-124">In the list, mark the selected row.</span></span>
5. <span data-ttu-id="f1986-125">Klicka på Match.</span><span class="sxs-lookup"><span data-stu-id="f1986-125">Click Match.</span></span>
6. <span data-ttu-id="f1986-126">Expandera avsnittet Matched freight bill details.</span><span class="sxs-lookup"><span data-stu-id="f1986-126">Expand the Matched freight bill details section.</span></span>

## <a name="submit-the-invoice-for-approval"></a><span data-ttu-id="f1986-127">Skicka fakturan för godkännande</span><span class="sxs-lookup"><span data-stu-id="f1986-127">Submit the invoice for approval</span></span>
1. <span data-ttu-id="f1986-128">Klicka på Submit for approval.</span><span class="sxs-lookup"><span data-stu-id="f1986-128">Click Submit for approval.</span></span>
2. <span data-ttu-id="f1986-129">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f1986-129">Close the page.</span></span>
3. <span data-ttu-id="f1986-130">Rensa kryssrutan Hide approved.</span><span class="sxs-lookup"><span data-stu-id="f1986-130">Clear the Hide approved check box.</span></span> 
4. <span data-ttu-id="f1986-131">Klicka på Vendor invoice journals.</span><span class="sxs-lookup"><span data-stu-id="f1986-131">Click Vendor invoice journals.</span></span>
5. <span data-ttu-id="f1986-132">Klicka för att följa länken i fältet Reference journal number.</span><span class="sxs-lookup"><span data-stu-id="f1986-132">Click to follow the link in the Reference journal number field.</span></span>
6. <span data-ttu-id="f1986-133">Klicka på Rader.</span><span class="sxs-lookup"><span data-stu-id="f1986-133">Click Lines.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]