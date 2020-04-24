---
title: Stäm av frakt i transporthantering
description: Det här avsnittet ger en beskrivning av fraktavstämningsprocessen.
author: MarkusFogelberg
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSAuditMaster, TMSFreightBillInvoiceReconcile, TMSFreightBillSummary, TMSFreightBillType, TMSFreightMatchReason, TMSInvoiceTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 89983
ms.assetid: bc34a9b1-0c11-4797-b463-25409cf98ca8
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0e1680572f1ba9816c9ec45ef52498cab1f45247
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3206229"
---
# <a name="reconcile-freight-in-transportation-management"></a><span data-ttu-id="3e924-103">Stäm av frakt i transporthantering</span><span class="sxs-lookup"><span data-stu-id="3e924-103">Reconcile freight in transportation management</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3e924-104">Det här avsnittet ger en beskrivning av fraktavstämningsprocessen.</span><span class="sxs-lookup"><span data-stu-id="3e924-104">This topic describes the freight reconciliation process.</span></span>

<span data-ttu-id="3e924-105">Fraktavstämning kan utföras manuellt eller ställas in för att utföras automatiskt.</span><span class="sxs-lookup"><span data-stu-id="3e924-105">Freight reconciliation can be done manually, or it can be set up to occur automatically.</span></span> <span data-ttu-id="3e924-106">Om du vill använda automatisk fraktavstämning måste du ställa in en granskningsmall där du kan definiera kriterierna som avgör vilka fraktväxlar som matchas automatiskt.</span><span class="sxs-lookup"><span data-stu-id="3e924-106">To use automatic freight reconciliation, you must set up an audit master where you can define criteria that determine which freight bills are matched automatically.</span></span>

## <a name="the-freight-reconciliation-process"></a><span data-ttu-id="3e924-107">Fraktavstämningsprocessen</span><span class="sxs-lookup"><span data-stu-id="3e924-107">The freight reconciliation process</span></span>
<span data-ttu-id="3e924-108">Fraktsatser beräknas med hjälp av tariffmotorer som kopplas till relevanta transportföretag.</span><span class="sxs-lookup"><span data-stu-id="3e924-108">Freight rates are calculated by the rate engine that is associated with the relevant shipping carrier.</span></span> <span data-ttu-id="3e924-109">När en last bekräftas genereras en fraktsedel och fraktsatser överförs till den.</span><span class="sxs-lookup"><span data-stu-id="3e924-109">When a load is confirmed, a freight bill is generated, and the freight rates are transferred to it.</span></span> <span data-ttu-id="3e924-110">Fraktsatser fördelas som tilläggsavgifter till det aktuella källdokumentet (inköpsorder, försäljningsorder och/eller överföringsorder) beroende på inställningarna som används för den vanliga faktureringsprocessen.</span><span class="sxs-lookup"><span data-stu-id="3e924-110">The freight rates are apportioned as miscellaneous charges to the relevant source document (purchase order, sales order, and/or transfer order), depending on the setup that is used for the regular billing process.</span></span> <span data-ttu-id="3e924-111">Fraktavstämningsprocessen (som också kallas matchande processen) kan starta så snart fraktfakturan inkommer från transportföretaget.</span><span class="sxs-lookup"><span data-stu-id="3e924-111">The freight reconciliation process (which is also known as the matching process) can start as soon as the freight invoice arrives from the shipping carrier.</span></span> <span data-ttu-id="3e924-112">Fakturan kan tas emot elektroniskt eller som pappersfaktura.</span><span class="sxs-lookup"><span data-stu-id="3e924-112">The invoice can be received electronically or on paper.</span></span> <span data-ttu-id="3e924-113">Om det är en pappersfaktura kan du generera en elektronisk faktura med hjälp av fraktsedeln som mall.</span><span class="sxs-lookup"><span data-stu-id="3e924-113">If the invoice is received on paper, you can generate an electronic invoice by using the freight bill as a template.</span></span> 

<span data-ttu-id="3e924-114">[![Fraktavstämningsprocess](./media/freight-reconcilation-process.jpg)](./media/freight-reconcilation-process.jpg)</span><span class="sxs-lookup"><span data-stu-id="3e924-114">[![Freight reconcilation process](./media/freight-reconcilation-process.jpg)](./media/freight-reconcilation-process.jpg)</span></span>

## <a name="manual-reconciliation"></a><span data-ttu-id="3e924-115">Manuell avstämning</span><span class="sxs-lookup"><span data-stu-id="3e924-115">Manual reconciliation</span></span>
<span data-ttu-id="3e924-116">Om du stämmer av frakten manuellt måste du matcha varje fakturarad med fraktsedelns rad eller rader för lasten som faktureras.</span><span class="sxs-lookup"><span data-stu-id="3e924-116">If you're reconciling freight manually, you must match each invoice line with the freight bill line or lines for the load that is being invoiced.</span></span> <span data-ttu-id="3e924-117">Du utför den här matchningen på sidan **Fraktsedel och fakturamatchning**.</span><span class="sxs-lookup"><span data-stu-id="3e924-117">You do this matching on the **Freight bill and invoice matching** page.</span></span> <span data-ttu-id="3e924-118">Om beloppet på fakturaraden inte överensstämmer med beloppet på fraktsedeln måste du välja en orsak till avstämningsavvikelsen.</span><span class="sxs-lookup"><span data-stu-id="3e924-118">If the amount on the invoice line doesn’t match the freight bill amount, you must select a reconciliation reason for the difference.</span></span> <span data-ttu-id="3e924-119">Om det finns flera skäl för avstämning kan du dela upp omatchade belopp över dem.</span><span class="sxs-lookup"><span data-stu-id="3e924-119">If there are multiple reasons for reconciliation, you can split the unmatched amount across them.</span></span> <span data-ttu-id="3e924-120">Avstämningsorsaken avgör hur de avvikande beloppen bokförs i redovisningen.</span><span class="sxs-lookup"><span data-stu-id="3e924-120">The reconciliation reason determines how the difference amounts are posted in the general ledger.</span></span> <span data-ttu-id="3e924-121">När avstämningen av hela fakturabeloppet redovisas skickas den för godkännande och sedan bokförs.journalen.</span><span class="sxs-lookup"><span data-stu-id="3e924-121">When the reconciliation of the whole invoice amount is accounted for, it's submitted for approval, and then the journal is posted.</span></span> <span data-ttu-id="3e924-122">I bilden nedan visas hur du skapar en fraktfaktura och utför fraktavstämning.</span><span class="sxs-lookup"><span data-stu-id="3e924-122">The following illustration shows how to generate a freight invoice and do freight reconciliation.</span></span> 
<span data-ttu-id="3e924-123">[![Fraktavstämningsuppgifter](./media/processflowforfreightreconciliation.jpg)](./media/processflowforfreightreconciliation.jpg)</span><span class="sxs-lookup"><span data-stu-id="3e924-123">[![Freight reconcilation tasks](./media/processflowforfreightreconciliation.jpg)](./media/processflowforfreightreconciliation.jpg)</span></span>
## <a name="automatic-reconciliation"></a><span data-ttu-id="3e924-124">Automatisk avstämning</span><span class="sxs-lookup"><span data-stu-id="3e924-124">Automatic reconciliation</span></span>
<span data-ttu-id="3e924-125">Du måste ange tidsplanen för avstämning, fakturorna och vilket transportföretag som ska användas om du vill använda automatisk avstämning.</span><span class="sxs-lookup"><span data-stu-id="3e924-125">To use automatic reconciliation, you must specify the schedule for reconciliation, and the invoices and shipping carriers to use.</span></span> <span data-ttu-id="3e924-126">Matchningen av fakturarader och fraktsedlarna utförs enligt inställningarna för granskningsmallen och fraktsedelstypen.</span><span class="sxs-lookup"><span data-stu-id="3e924-126">The matching of the invoice lines and freight bills is done according to the setup of the audit master and freight bill type.</span></span> <span data-ttu-id="3e924-127">När du har kört automatisk avstämning måste du hantera alla fakturor som systemet inte kan matcha.</span><span class="sxs-lookup"><span data-stu-id="3e924-127">After you run the automatic reconciliation, you must handle any invoices that the system can't match.</span></span> <span data-ttu-id="3e924-128">Du måste sedan behandla dessa fakturor manuellt innan du kan bokföra alla fakturor för betalning.</span><span class="sxs-lookup"><span data-stu-id="3e924-128">You must then process these invoices manually before you can post all the invoices for payment.</span></span>



