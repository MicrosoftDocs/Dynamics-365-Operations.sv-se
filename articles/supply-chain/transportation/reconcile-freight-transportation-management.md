---
title: "Stäm av frakt i transporthantering"
description: "Den här artikeln ger en beskrivning av fraktavstämningsprocessen."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TMSAuditMaster, TMSFreightBillInvoiceReconcile, TMSFreightBillSummary, TMSFreightBillType, TMSFreightMatchReason, TMSInvoiceTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 89983
ms.assetid: bc34a9b1-0c11-4797-b463-25409cf98ca8
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 0e9dd669ff08c02a8bbb1f83e19dfa62298f317b
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="reconcile-freight-in-transportation-management"></a><span data-ttu-id="40008-103">Stäm av frakt i transporthantering</span><span class="sxs-lookup"><span data-stu-id="40008-103">Reconcile freight in transportation management</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="40008-104">Den här artikeln ger en beskrivning av fraktavstämningsprocessen.</span><span class="sxs-lookup"><span data-stu-id="40008-104">This article describes the freight reconciliation process.</span></span>

<span data-ttu-id="40008-105">Fraktavstämning kan utföras manuellt eller ställas in för att utföras automatiskt.</span><span class="sxs-lookup"><span data-stu-id="40008-105">Freight reconciliation can be done manually, or it can be set up to occur automatically.</span></span> <span data-ttu-id="40008-106">Om du vill använda automatisk fraktavstämning måste du ställa in en granskningsmall där du kan definiera kriterierna som avgör vilka fraktväxlar som matchas automatiskt.</span><span class="sxs-lookup"><span data-stu-id="40008-106">To use automatic freight reconciliation, you must set up an audit master where you can define criteria that determine which freight bills are matched automatically.</span></span>

## <a name="the-freight-reconciliation-process"></a><span data-ttu-id="40008-107">Fraktavstämningsprocessen</span><span class="sxs-lookup"><span data-stu-id="40008-107">The freight reconciliation process</span></span>
<span data-ttu-id="40008-108">Fraktsatser beräknas med hjälp av tariffmotorer som kopplas till relevanta transportföretag.</span><span class="sxs-lookup"><span data-stu-id="40008-108">Freight rates are calculated by the rate engine that is associated with the relevant shipping carrier.</span></span> <span data-ttu-id="40008-109">När en last bekräftas genereras en fraktsedel och fraktsatser överförs till den.</span><span class="sxs-lookup"><span data-stu-id="40008-109">When a load is confirmed, a freight bill is generated, and the freight rates are transferred to it.</span></span> <span data-ttu-id="40008-110">Fraktsatser fördelas som tilläggsavgifter till det aktuella källdokumentet (inköpsorder, försäljningsorder och/eller överföringsorder) beroende på inställningarna som används för den vanliga faktureringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="40008-110">The freight rates are apportioned as miscellaneous charges to the relevant source document (purchase order, sales order, and/or transfer order), depending on the setup that is used for the regular billing process.</span></span> <span data-ttu-id="40008-111">Fraktavstämningsprocessen (som också kallas matchande processen) kan starta så snart fraktfakturan inkommer från transportföretaget.</span><span class="sxs-lookup"><span data-stu-id="40008-111">The freight reconciliation process (which is also known as the matching process) can start as soon as the freight invoice arrives from the shipping carrier.</span></span> <span data-ttu-id="40008-112">Fakturan kan tas emot elektroniskt eller som pappersfaktura.</span><span class="sxs-lookup"><span data-stu-id="40008-112">The invoice can be received electronically or on paper.</span></span> <span data-ttu-id="40008-113">Om det är en pappersfaktura kan du generera en elektronisk faktura med hjälp av fraktsedeln som mall.</span><span class="sxs-lookup"><span data-stu-id="40008-113">If the invoice is received on paper, you can generate an electronic invoice by using the freight bill as a template.</span></span> 

<span data-ttu-id="40008-114">[![Fraktavstämningsprocess](./media/freight-reconcilation-process.jpg)](./media/freight-reconcilation-process.jpg)</span><span class="sxs-lookup"><span data-stu-id="40008-114">[![Freight reconcilation process](./media/freight-reconcilation-process.jpg)](./media/freight-reconcilation-process.jpg)</span></span>

## <a name="manual-reconciliation"></a><span data-ttu-id="40008-115">Manuell avstämning</span><span class="sxs-lookup"><span data-stu-id="40008-115">Manual reconciliation</span></span>
<span data-ttu-id="40008-116">Om du stämmer av frakten manuellt måste du matcha varje fakturarad med fraktsedelns rad eller rader för lasten som faktureras.</span><span class="sxs-lookup"><span data-stu-id="40008-116">If you're reconciling freight manually, you must match each invoice line with the freight bill line or lines for the load that is being invoiced.</span></span> <span data-ttu-id="40008-117">Du utför den här matchningen på sidan **Fraktsedel och fakturamatchning**.</span><span class="sxs-lookup"><span data-stu-id="40008-117">You do this matching on the **Freight bill and invoice matching** page.</span></span> <span data-ttu-id="40008-118">Om beloppet på fakturaraden inte överensstämmer med beloppet på fraktsedeln måste du välja en orsak till avstämningsavvikelsen.</span><span class="sxs-lookup"><span data-stu-id="40008-118">If the amount on the invoice line doesn’t match the freight bill amount, you must select a reconciliation reason for the difference.</span></span> <span data-ttu-id="40008-119">Om det finns flera skäl för avstämning kan du dela upp omatchade belopp över dem.</span><span class="sxs-lookup"><span data-stu-id="40008-119">If there are multiple reasons for reconciliation, you can split the unmatched amount across them.</span></span> <span data-ttu-id="40008-120">Avstämningsorsaken avgör hur de avvikande beloppen bokförs i redovisningen.</span><span class="sxs-lookup"><span data-stu-id="40008-120">The reconciliation reason determines how the difference amounts are posted in the general ledger.</span></span> <span data-ttu-id="40008-121">När avstämningen av hela fakturabeloppet redovisas skickas den för godkännande och sedan bokförs.journalen.</span><span class="sxs-lookup"><span data-stu-id="40008-121">When the reconciliation of the whole invoice amount is accounted for, it's submitted for approval, and then the journal is posted.</span></span> <span data-ttu-id="40008-122">Bilden nedan visar hur du genererar en fraktfaktura och utför fraktavstämning i Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="40008-122">The following illustration shows how to generate a freight invoice and do freight reconciliation in Microsoft Dynamics 365 for Finance and Operations.</span></span> 
<span data-ttu-id="40008-123">[![Fraktavstämningsuppgifter i Dynamics AX](./media/processflowforfreightreconciliation.jpg)](./media/processflowforfreightreconciliation.jpg)</span><span class="sxs-lookup"><span data-stu-id="40008-123">[![Freight reconcilation tasks in Dynamics AX](./media/processflowforfreightreconciliation.jpg)](./media/processflowforfreightreconciliation.jpg)</span></span>
## <a name="automatic-reconciliation"></a><span data-ttu-id="40008-124">Automatisk avstämning</span><span class="sxs-lookup"><span data-stu-id="40008-124">Automatic reconciliation</span></span>
<span data-ttu-id="40008-125">Du måste ange tidsplanen för avstämning, fakturorna och vilket transportföretag som ska användas om du vill använda automatisk avstämning.</span><span class="sxs-lookup"><span data-stu-id="40008-125">To use automatic reconciliation, you must specify the schedule for reconciliation, and the invoices and shipping carriers to use.</span></span> <span data-ttu-id="40008-126">Matchningen av fakturarader och fraktsedlarna utförs enligt inställningarna för granskningsmallen och fraktsedelstypen.</span><span class="sxs-lookup"><span data-stu-id="40008-126">The matching of the invoice lines and freight bills is done according to the setup of the audit master and freight bill type.</span></span> <span data-ttu-id="40008-127">När du har kört automatisk avstämning måste du hantera alla fakturor som systemet inte kan matcha.</span><span class="sxs-lookup"><span data-stu-id="40008-127">After you run the automatic reconciliation, you must handle any invoices that the system can't match.</span></span> <span data-ttu-id="40008-128">Du måste sedan behandla dessa fakturor manuellt innan du kan bokföra alla fakturor för betalning.</span><span class="sxs-lookup"><span data-stu-id="40008-128">You must then process these invoices manually before you can post all the invoices for payment.</span></span>




