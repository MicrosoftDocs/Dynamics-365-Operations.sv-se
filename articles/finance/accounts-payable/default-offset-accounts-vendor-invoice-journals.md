---
title: Standardmotkonton för leverantörsfaktura- och fakturagodkännandejournaler
description: Det här ämnet hjälper dig att bestämma var du bör tilldela standardkonton och motkonton för fakturajournaler.
author: abruer
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 62093
ms.assetid: 553933ca-928d-4031-bb8c-f9cff458320b
ms.search.region: global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c3b2ad808d5008d9a4b2d3ee975d15fa1ee13ed7
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "5003506"
---
# <a name="default-offset-accounts-for-vendor-invoice-and-invoice-approval-journals"></a><span data-ttu-id="f9a9c-103">Standardmotkonton för leverantörsfaktura- och fakturagodkännandejournaler</span><span class="sxs-lookup"><span data-stu-id="f9a9c-103">Default offset accounts for vendor invoice and invoice approval journals</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f9a9c-104">Standardmotkonton används på följande sidor för leverantörsfakturajournaler:</span><span class="sxs-lookup"><span data-stu-id="f9a9c-104">Default offset accounts are used on the following vendor invoice journal pages:</span></span>

-   <span data-ttu-id="f9a9c-105">Fakturajournal</span><span class="sxs-lookup"><span data-stu-id="f9a9c-105">Invoice journal</span></span>
-   <span data-ttu-id="f9a9c-106">Fakturagodkännandejournal</span><span class="sxs-lookup"><span data-stu-id="f9a9c-106">Invoice approval journal</span></span>

<span data-ttu-id="f9a9c-107">Använd följande register som hjälper dig att bestämma var du bör tilldela standardkonton och motkonton för fakturajournaler.</span><span class="sxs-lookup"><span data-stu-id="f9a9c-107">Use the following table to help decide where you should assign default accounts for invoice journals.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f9a9c-108">Ställ in standardkonton här</span><span class="sxs-lookup"><span data-stu-id="f9a9c-108">Set up default accounts here</span></span></th>
<th><span data-ttu-id="f9a9c-109">Där standardkonton tillhandahålls</span><span class="sxs-lookup"><span data-stu-id="f9a9c-109">Where default accounts are provided</span></span></th>
<th><span data-ttu-id="f9a9c-110">Hur detta alternativ påverkar bearbetning</span><span class="sxs-lookup"><span data-stu-id="f9a9c-110">How this option affects processing</span></span></th>
<th><span data-ttu-id="f9a9c-111">När du ska använda det här alternativet</span><span class="sxs-lookup"><span data-stu-id="f9a9c-111">When you should use this option</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="f9a9c-112"><strong>Leverantörsgrupp</strong> – Ställ in standardmotkonton för leverantörsgrupper på sidan <strong>Standardkontoinställning</strong>  som du öppnar från sidan <strong>Leverantörsgrupper</strong>.</span><span class="sxs-lookup"><span data-stu-id="f9a9c-112"><strong>Vendor group</strong> – Set up default offset accounts for vendor groups on the <strong>Default account setup</strong> page, which you can open from the <strong>Vendor groups</strong> page.</span></span></td>
<td><ul>
<li><span data-ttu-id="f9a9c-113">Leverantörskonto</span><span class="sxs-lookup"><span data-stu-id="f9a9c-113">Vendor account</span></span></li>
<li><span data-ttu-id="f9a9c-114">Journalposter för leverantörskonton i leverantörsgruppen, om standardkonton inte anges för leverantörskonton</span><span class="sxs-lookup"><span data-stu-id="f9a9c-114">Journal entries for vendor accounts in the vendor group, if default accounts aren’t specified for vendor accounts</span></span></li>
</ul></td>
<td><span data-ttu-id="f9a9c-115">Standardmotkontona för leverantörsgrupper visas som standardmotkonton för leverantörer på sidan <strong>Standardkontoinställning</strong>.</span><span class="sxs-lookup"><span data-stu-id="f9a9c-115">The default offset accounts for vendor groups are shown as default offset accounts for vendors on the <strong>Default account setup</strong> page.</span></span> <span data-ttu-id="f9a9c-116">Du kan öppna den här sidan från listsidan <strong>Alla leverantörer</strong>.</span><span class="sxs-lookup"><span data-stu-id="f9a9c-116">You can open this page from the <strong>All vendors</strong> list page.</span></span></td>
<td><span data-ttu-id="f9a9c-117">Använd det här alternativet om du vanligtvis betalar för samma typer av objekt från samma leverantörsgrupperna över tid.</span><span class="sxs-lookup"><span data-stu-id="f9a9c-117">Use this option if you typically pay for the same types of things from the same vendor groups over time.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f9a9c-118"><strong>Leverantörskonto</strong> – Ställ in standardmotkonton för leverantörskonton på sidan <strong>Standardkontoinställning</strong> som du öppnar från sidan <strong>Leverantörer</strong>.</span><span class="sxs-lookup"><span data-stu-id="f9a9c-118"><strong>Vendor account</strong> – Set up default accounts for vendor accounts on the <strong>Default account setup</strong> page, which you can open from the <strong>Vendors</strong> page.</span></span></td>
<td><span data-ttu-id="f9a9c-119">Journalposter för leverantörskontot</span><span class="sxs-lookup"><span data-stu-id="f9a9c-119">Journal entries for the vendor account</span></span></td>
<td><span data-ttu-id="f9a9c-120">Standardmotkontona för leverantörskonton visas som standardmotkonton för journalposter för leverantörskontot.</span><span class="sxs-lookup"><span data-stu-id="f9a9c-120">The default offset accounts for vendor accounts are shown as default offset accounts for journal entries for the vendor account.</span></span></td>
<td><span data-ttu-id="f9a9c-121">Använd det här alternativet om du vanligtvis betalar för samma typer av objekt från samma leverantörer över tid.</span><span class="sxs-lookup"><span data-stu-id="f9a9c-121">Use this option if you typically pay for the same types of things from the same vendors over time.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f9a9c-122"><strong>Journalnamn</strong> – Ställ in standardmotkonton för journaler på sidan <strong>Journalnamn</strong>.</span><span class="sxs-lookup"><span data-stu-id="f9a9c-122"><strong>Journal names</strong> – Set up default offset accounts for journals on the <strong>Journal names</strong> page.</span></span> <span data-ttu-id="f9a9c-123">Välj alternativet <strong>Fast motkonto</strong>.</span><span class="sxs-lookup"><span data-stu-id="f9a9c-123">Select the <strong>Fixed offset account</strong> option.</span></span> <span data-ttu-id="f9a9c-124">Observera att du kan inte kan ange standardmotkonton för journalnamn om journaltypen av journalnamnen är <strong>Fakturaregister</strong> eller <strong>Godkänn</strong>.</span><span class="sxs-lookup"><span data-stu-id="f9a9c-124">Note that you can&#39;t specify default offset accounts on journal names if the journal type of the journal names is <strong>Invoice register</strong> or <strong>Approval</strong>.</span></span></td>
<td><ul>
<li><span data-ttu-id="f9a9c-125">Journalrubrik som använder journalnamnet</span><span class="sxs-lookup"><span data-stu-id="f9a9c-125">Journal header that uses the journal name</span></span></li>
<li><span data-ttu-id="f9a9c-126">Journalposter i journaler som använder journalnamn</span><span class="sxs-lookup"><span data-stu-id="f9a9c-126">Journal entries in journals that use the journal name</span></span></li>
</ul></td>
<td><span data-ttu-id="f9a9c-127">Om alternativet <strong>Fast motkonto</strong> på sidan <strong>Journalnamn</strong> har markerats, åsidosätter motkontot för journalnamnet standardmotkontot för leverantören eller leverantörsgruppen.</span><span class="sxs-lookup"><span data-stu-id="f9a9c-127">If the <strong>Fixed offset account</strong> option on the <strong>Journal names</strong> page is selected, the offset account for the journal name overrides the default offset account for the vendor or vendor group.</span></span></td>
<td><span data-ttu-id="f9a9c-128">Använd det här alternativet om du vill ställa in journaler för specifika kostnader och utgifter som debiteras specifika konton, oavsett vem leverantören eller leverantörsgruppen som de tillhör.</span><span class="sxs-lookup"><span data-stu-id="f9a9c-128">Use this option to set up journals for specific costs and expenses that are charged to specific accounts, regardless of the vendor or the vendor group that the vendor belongs to.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="f9a9c-129"><strong>Journalnamn</strong> – Ställ in standardmotkonton för journaler på sidan <strong>Journalnamn</strong>.</span><span class="sxs-lookup"><span data-stu-id="f9a9c-129"><strong>Journal names</strong> – Set up default offset accounts for journals on the <strong>Journal names</strong> page.</span></span> <span data-ttu-id="f9a9c-130">Ta bort alternativet <strong>Fast motkonto</strong>.</span><span class="sxs-lookup"><span data-stu-id="f9a9c-130">Clear the <strong>Fixed offset account</strong> option.</span></span> <span data-ttu-id="f9a9c-131">Observera att du kan inte kan ange standardmotkonton för journalnamn om journaltypen av journalnamnen är <strong>Fakturaregister</strong> eller <strong>Godkänn</strong>.</span><span class="sxs-lookup"><span data-stu-id="f9a9c-131">Note that you can&#39;t specify default offset accounts on journal names if the journal type of the journal names is <strong>Invoice register</strong> or <strong>Approval</strong>.</span></span></td>
<td><ul>
<li><span data-ttu-id="f9a9c-132">Journalrubrik</span><span class="sxs-lookup"><span data-stu-id="f9a9c-132">Journal header</span></span></li>
<li><span data-ttu-id="f9a9c-133">Journalposter i journaler som använder journalnamn</span><span class="sxs-lookup"><span data-stu-id="f9a9c-133">Journal entries in journals that use the journal name</span></span></li>
</ul></td>
<td><span data-ttu-id="f9a9c-134">Dessa standardvärden används på sidor för journalrubriker och motkontot på sidan för journalrubriker används som en standardinställning på sidan för bokföringsorder.</span><span class="sxs-lookup"><span data-stu-id="f9a9c-134">These default entries are used on journal header pages, and the offset account on the journal header page is used as a default entry on the journal voucher pages.</span></span> <span data-ttu-id="f9a9c-135">Standardkonton från sidan <strong>Journalnamn</strong> används bara om standardkonton inte har ställts in för leverantörskontot.</span><span class="sxs-lookup"><span data-stu-id="f9a9c-135">Default accounts from the <strong>Journal names </strong>page are used only if default accounts aren’t set up for the vendor account.</span></span></td>
<td><span data-ttu-id="f9a9c-136">Använd det här alternativet om du vill ställa in standardkonton som ska användas när ett standardleverantörmotkonto inte tilldelas.</span><span class="sxs-lookup"><span data-stu-id="f9a9c-136">Use this option to set up default accounts that are used when a default vendor offset account isn&#39;t assigned.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="f9a9c-137"><strong>Journalrubrik</strong> – Ställa in ett standardmotkonto för en journal som ska användas som ett standardvärde på sidan för bokföringsorder.</span><span class="sxs-lookup"><span data-stu-id="f9a9c-137"><strong>Journal header</strong> – Set up a default offset account for a journal as a default entry on the journal voucher pages.</span></span> <span data-ttu-id="f9a9c-138">Observera att du kan inte kan ange standardmotkonton för journalrubrik om journaltypen av journalnamnen är <strong>Fakturaregister</strong> eller <strong>Godkänn</strong>.</span><span class="sxs-lookup"><span data-stu-id="f9a9c-138">Note that you can&#39;t specify default offset accounts on the journal header if the journal type of the journal names is <strong>Invoice register</strong> or <strong>Approval</strong>.</span></span></td>
<td><span data-ttu-id="f9a9c-139">Journalposter i journalen</span><span class="sxs-lookup"><span data-stu-id="f9a9c-139">Journal entries in the journal</span></span></td>
<td><span data-ttu-id="f9a9c-140">Standardmotkontot för en journal används som standardposten på sidan för bokföringsordern.</span><span class="sxs-lookup"><span data-stu-id="f9a9c-140">The default offset account for a journal is used as the default entry on the journal voucher pages.</span></span></td>
<td><span data-ttu-id="f9a9c-141">Använd det här alternativet för att göra dataregistreringen snabbare, om de flesta poster i en journal har samma motkonto.</span><span class="sxs-lookup"><span data-stu-id="f9a9c-141">Use this option to help speed up data entry if most entries in a journal have the same offset account.</span></span></td>
</tr>
</tbody>
</table>





