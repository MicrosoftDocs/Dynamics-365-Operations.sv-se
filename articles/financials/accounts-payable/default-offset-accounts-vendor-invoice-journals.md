---
title: "Standardmotkonton för leverantörsfakturajournaler och fakturagodkännandejournaler"
description: 
author: ShivamPandey-msft
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 62093
ms.assetid: 553933ca-928d-4031-bb8c-f9cff458320b
ms.search.region: global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: c2b62eafc71b5d1ad4eaaf252efd1dcbb97b86f3
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="default-offset-accounts-for-vendor-invoice-journals-and-invoice-approval-journals"></a><span data-ttu-id="a047e-102">Standardmotkonton för leverantörsfakturajournaler och fakturagodkännandejournaler</span><span class="sxs-lookup"><span data-stu-id="a047e-102">Default offset accounts for vendor invoice journals and invoice approval journals</span></span>

[!include[banner](../includes/banner.md)]




<span data-ttu-id="a047e-103">Standardmotkonton används på följande sidor för leverantörsfakturajournaler:</span><span class="sxs-lookup"><span data-stu-id="a047e-103">Default offset accounts are used on the following vendor invoice journal pages:</span></span>

-   <span data-ttu-id="a047e-104">Fakturajournal</span><span class="sxs-lookup"><span data-stu-id="a047e-104">Invoice journal</span></span>
-   <span data-ttu-id="a047e-105">Fakturagodkännandejournal</span><span class="sxs-lookup"><span data-stu-id="a047e-105">Invoice approval journal</span></span>

<span data-ttu-id="a047e-106">Använd följande register som hjälper dig att bestämma var du bör tilldela standardkonton och motkonton för fakturajournaler.</span><span class="sxs-lookup"><span data-stu-id="a047e-106">Use the following table to help decide where you should assign default accounts for invoice journals.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a047e-107">Ställ in standardkonton här</span><span class="sxs-lookup"><span data-stu-id="a047e-107">Set up default accounts here</span></span></th>
<th><span data-ttu-id="a047e-108">Där standardkonton tillhandahålls</span><span class="sxs-lookup"><span data-stu-id="a047e-108">Where default accounts are provided</span></span></th>
<th><span data-ttu-id="a047e-109">Hur detta alternativ påverkar bearbetning</span><span class="sxs-lookup"><span data-stu-id="a047e-109">How this option affects processing</span></span></th>
<th><span data-ttu-id="a047e-110">När du ska använda det här alternativet</span><span class="sxs-lookup"><span data-stu-id="a047e-110">When you should use this option</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="a047e-111"><strong>Leverantörsgrupp</strong> – Ställ in standardmotkonton för leverantörsgrupper på sidan <strong>Standardkontoinställning</strong>  som du öppnar från sidan <strong>Leverantörsgrupper</strong>.</span><span class="sxs-lookup"><span data-stu-id="a047e-111"><strong>Vendor group</strong> – Set up default offset accounts for vendor groups on the <strong>Default account setup</strong> page, which you can open from the <strong>Vendor groups</strong> page.</span></span></td>
<td><ul>
<li><span data-ttu-id="a047e-112">Leverantörskonto</span><span class="sxs-lookup"><span data-stu-id="a047e-112">Vendor account</span></span></li>
<li><span data-ttu-id="a047e-113">Journalposter för leverantörskonton i leverantörsgruppen, om standardkonton inte anges för leverantörskonton</span><span class="sxs-lookup"><span data-stu-id="a047e-113">Journal entries for vendor accounts in the vendor group, if default accounts aren’t specified for vendor accounts</span></span></li>
</ul></td>
<td><span data-ttu-id="a047e-114">Standardmotkontona för leverantörsgrupper visas som standardmotkonton för leverantörer på sidan <strong>Standardkontoinställning</strong>.</span><span class="sxs-lookup"><span data-stu-id="a047e-114">The default offset accounts for vendor groups are shown as default offset accounts for vendors on the <strong>Default account setup</strong> page.</span></span> <span data-ttu-id="a047e-115">Du kan öppna den här sidan från listsidan <strong>Alla leverantörer</strong>.</span><span class="sxs-lookup"><span data-stu-id="a047e-115">You can open this page from the <strong>All vendors</strong> list page.</span></span></td>
<td><span data-ttu-id="a047e-116">Använd det här alternativet om du vanligtvis betalar för samma typer av objekt från samma leverantörsgrupperna över tid.</span><span class="sxs-lookup"><span data-stu-id="a047e-116">Use this option if you typically pay for the same types of things from the same vendor groups over time.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a047e-117"><strong>Leverantörskonto</strong> – Ställ in standardmotkonton för leverantörskonton på sidan <strong>Standardkontoinställning</strong> som du öppnar från sidan <strong>Leverantörer</strong>.</span><span class="sxs-lookup"><span data-stu-id="a047e-117"><strong>Vendor account</strong> – Set up default accounts for vendor accounts on the <strong>Default account setup</strong> page, which you can open from the <strong>Vendors</strong> page.</span></span></td>
<td><span data-ttu-id="a047e-118">Journalposter för leverantörskontot</span><span class="sxs-lookup"><span data-stu-id="a047e-118">Journal entries for the vendor account</span></span></td>
<td><span data-ttu-id="a047e-119">Standardmotkontona för leverantörskonton visas som standardmotkonton för journalposter för leverantörskontot.</span><span class="sxs-lookup"><span data-stu-id="a047e-119">The default offset accounts for vendor accounts are shown as default offset accounts for journal entries for the vendor account.</span></span></td>
<td><span data-ttu-id="a047e-120">Använd det här alternativet om du vanligtvis betalar för samma typer av objekt från samma leverantörer över tid.</span><span class="sxs-lookup"><span data-stu-id="a047e-120">Use this option if you typically pay for the same types of things from the same vendors over time.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="a047e-121"><strong>Journalnamn</strong> – Ställ in standardmotkonton för journaler på sidan <strong>Journalnamn</strong>.</span><span class="sxs-lookup"><span data-stu-id="a047e-121"><strong>Journal names</strong> – Set up default offset accounts for journals on the <strong>Journal names</strong> page.</span></span> <span data-ttu-id="a047e-122">Välj alternativet <strong>Fast motkonto</strong>.</span><span class="sxs-lookup"><span data-stu-id="a047e-122">Select the <strong>Fixed offset account</strong> option.</span></span> <span data-ttu-id="a047e-123">Observera att du kan inte kan ange standardmotkonton för journalnamn om journaltypen av journalnamnen är <strong>Fakturaregister</strong> eller <strong>Godkänn</strong>.</span><span class="sxs-lookup"><span data-stu-id="a047e-123">Note that you can't specify default offset accounts on journal names if the journal type of the journal names is <strong>Invoice register</strong> or <strong>Approval</strong>.</span></span></td>
<td><ul>
<li><span data-ttu-id="a047e-124">Journalrubrik som använder journalnamnet</span><span class="sxs-lookup"><span data-stu-id="a047e-124">Journal header that uses the journal name</span></span></li>
<li><span data-ttu-id="a047e-125">Journalposter i journaler som använder journalnamn</span><span class="sxs-lookup"><span data-stu-id="a047e-125">Journal entries in journals that use the journal name</span></span></li>
</ul></td>
<td><span data-ttu-id="a047e-126">Om alternativet <strong>Fast motkonto</strong> på sidan <strong>Journalnamn</strong> har markerats, åsidosätter motkontot för journalnamnet standardmotkontot för leverantören eller leverantörsgruppen.</span><span class="sxs-lookup"><span data-stu-id="a047e-126">If the <strong>Fixed offset account</strong> option on the <strong>Journal names</strong> page is selected, the offset account for the journal name overrides the default offset account for the vendor or vendor group.</span></span></td>
<td><span data-ttu-id="a047e-127">Använd det här alternativet om du vill ställa in journaler för specifika kostnader och utgifter som debiteras specifika konton, oavsett vem leverantören eller leverantörsgruppen som de tillhör.</span><span class="sxs-lookup"><span data-stu-id="a047e-127">Use this option to set up journals for specific costs and expenses that are charged to specific accounts, regardless of the vendor or the vendor group that the vendor belongs to.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a047e-128"><strong>Journalnamn</strong> – Ställ in standardmotkonton för journaler på sidan <strong>Journalnamn</strong>.</span><span class="sxs-lookup"><span data-stu-id="a047e-128"><strong>Journal names</strong> – Set up default offset accounts for journals on the <strong>Journal names</strong> page.</span></span> <span data-ttu-id="a047e-129">Ta bort alternativet <strong>Fast motkonto</strong>.</span><span class="sxs-lookup"><span data-stu-id="a047e-129">Clear the <strong>Fixed offset account</strong> option.</span></span> <span data-ttu-id="a047e-130">Observera att du kan inte kan ange standardmotkonton för journalnamn om journaltypen av journalnamnen är <strong>Fakturaregister</strong> eller <strong>Godkänn</strong>.</span><span class="sxs-lookup"><span data-stu-id="a047e-130">Note that you can't specify default offset accounts on journal names if the journal type of the journal names is <strong>Invoice register</strong> or <strong>Approval</strong>.</span></span></td>
<td><ul>
<li><span data-ttu-id="a047e-131">Journalrubrik</span><span class="sxs-lookup"><span data-stu-id="a047e-131">Journal header</span></span></li>
<li><span data-ttu-id="a047e-132">Journalposter i journaler som använder journalnamn</span><span class="sxs-lookup"><span data-stu-id="a047e-132">Journal entries in journals that use the journal name</span></span></li>
</ul></td>
<td><span data-ttu-id="a047e-133">Dessa standardvärden används på sidor för journalrubriker och motkontot på sidan för journalrubriker används som en standardinställning på sidan för bokföringsorder.</span><span class="sxs-lookup"><span data-stu-id="a047e-133">These default entries are used on journal header pages, and the offset account on the journal header page is used as a default entry on the journal voucher pages.</span></span> <span data-ttu-id="a047e-134">Standardkonton från sidan <strong>Journalnamn</strong> används bara om standardkonton inte har ställts in för leverantörskontot.</span><span class="sxs-lookup"><span data-stu-id="a047e-134">Default accounts from the <strong>Journal names </strong>page are used only if default accounts aren’t set up for the vendor account.</span></span></td>
<td><span data-ttu-id="a047e-135">Använd det här alternativet om du vill ställa in standardkonton som ska användas när en standardleverantörmotkonto inte tilldelas.</span><span class="sxs-lookup"><span data-stu-id="a047e-135">Use this option to set up default accounts that are used when a default vendor offset account isn't assigned.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="a047e-136"><strong>Journalrubrik</strong> – Ställa in ett standardmotkonto för en journal som ska användas som ett standardvärde på sidan för bokföringsorder.</span><span class="sxs-lookup"><span data-stu-id="a047e-136"><strong>Journal header</strong> – Set up a default offset account for a journal as a default entry on the journal voucher pages.</span></span> <span data-ttu-id="a047e-137">Observera att du kan inte kan ange standardmotkonton för journalrubrik om journaltypen av journalnamnen är <strong>Fakturaregister</strong> eller <strong>Godkänn</strong>.</span><span class="sxs-lookup"><span data-stu-id="a047e-137">Note that you can't specify default offset accounts on the journal header if the journal type of the journal names is <strong>Invoice register</strong> or <strong>Approval</strong>.</span></span></td>
<td><span data-ttu-id="a047e-138">Journalposter i journalen</span><span class="sxs-lookup"><span data-stu-id="a047e-138">Journal entries in the journal</span></span></td>
<td><span data-ttu-id="a047e-139">Standardmotkontot för en journal används som standardposten på sidan för bokföringsordern.</span><span class="sxs-lookup"><span data-stu-id="a047e-139">The default offset account for a journal is used as the default entry on the journal voucher pages.</span></span></td>
<td><span data-ttu-id="a047e-140">Använd det här alternativet för att göra dataregistreringen snabbare, om de flesta poster i en journal har samma motkonto.</span><span class="sxs-lookup"><span data-stu-id="a047e-140">Use this option to help speed up data entry if most entries in a journal have the same offset account.</span></span></td>
</tr>
</tbody>
</table>






