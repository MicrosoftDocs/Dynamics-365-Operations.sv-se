---
title: Numreringsdokument och verifikationer i kronologisk ordning
description: I detta ämne beskrivs hur du ställer in och använder kronologisk ordning för tillämpbara dokument och relaterade verifikationer.
author: ikond
manager: AnnBe
ms.date: 02/01/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: NumberSequenceGroup
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 401195
ms.search.region: Global
ms.author: ilyako
ms.search.validFrom: 2021-03-15
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 4a27b6fdd1e244fb0cb8c5fcefc484494aeb88bd
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5254541"
---
# <a name="numbering-documents-and-vouchers-chronologically"></a><span data-ttu-id="30c5d-103">Numreringsdokument och verifikationer i kronologisk ordning</span><span class="sxs-lookup"><span data-stu-id="30c5d-103">Numbering documents and vouchers chronologically</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="30c5d-104">I vissa länder finns ett juridiskt krav på att numrera dokument och relaterade verifikationer i kronologisk ordning.</span><span class="sxs-lookup"><span data-stu-id="30c5d-104">In some countries, there is a legal requirement to number documents and related vouchers in chronological order.</span></span> <span data-ttu-id="30c5d-105">Kronologin måste stödjas av perioder.</span><span class="sxs-lookup"><span data-stu-id="30c5d-105">The chronology must be supported by periods.</span></span> <span data-ttu-id="30c5d-106">Alla värden som hör till tidigare perioder måste vara mindre än de värden som tillhör senare perioder.</span><span class="sxs-lookup"><span data-stu-id="30c5d-106">All of the numbers that belong to earlier periods must be less than the numbers that belong to later periods.</span></span> <span data-ttu-id="30c5d-107">För att uppfylla detta krav har funktionen för kronologisk numrering implementerats.</span><span class="sxs-lookup"><span data-stu-id="30c5d-107">To meet this requirement, chronological numbering functionality has been implemented.</span></span> <span data-ttu-id="30c5d-108">I detta ämne beskrivs hur du konfigurerar och använder kronologisk ordning för tillämpbara dokument och relaterade verifikationer.</span><span class="sxs-lookup"><span data-stu-id="30c5d-108">This topic explains how to configure and use chronological numbers for applicable documents and related vouchers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="30c5d-109">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="30c5d-109">Prerequisites</span></span>

<span data-ttu-id="30c5d-110">I arbetsytan Funktionshantering aktiverar du funktionen **Kronologisk numrering**.</span><span class="sxs-lookup"><span data-stu-id="30c5d-110">In the Feature management workspace, turn on the **Chronological numbering** feature.</span></span> <span data-ttu-id="30c5d-111">Mer information finns i [Översikt för funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="30c5d-111">For more information, see [Feature management overview](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span></span>

## <a name="configure-chronological-numbering"></a><span data-ttu-id="30c5d-112">Konfigurera kronologisk numrering</span><span class="sxs-lookup"><span data-stu-id="30c5d-112">Configure chronological numbering</span></span>

<span data-ttu-id="30c5d-113">Kronologisk numrering påverkar följande dokument.</span><span class="sxs-lookup"><span data-stu-id="30c5d-113">Chronological numbering affects the following documents.</span></span>

<span data-ttu-id="30c5d-114">**Kundreskontra**</span><span class="sxs-lookup"><span data-stu-id="30c5d-114">**Accounts receivable**</span></span>
- <span data-ttu-id="30c5d-115">Kundfaktura</span><span class="sxs-lookup"><span data-stu-id="30c5d-115">Customer invoice</span></span>
- <span data-ttu-id="30c5d-116">Verifikation av kundfaktura</span><span class="sxs-lookup"><span data-stu-id="30c5d-116">Customer invoice voucher</span></span>
- <span data-ttu-id="30c5d-117">Försäljningskreditfaktura</span><span class="sxs-lookup"><span data-stu-id="30c5d-117">Sales credit note</span></span>
- <span data-ttu-id="30c5d-118">Verifikation för försäljningskreditfaktura</span><span class="sxs-lookup"><span data-stu-id="30c5d-118">Sales credit note voucher</span></span>
- <span data-ttu-id="30c5d-119">Fritextfaktura</span><span class="sxs-lookup"><span data-stu-id="30c5d-119">Free text invoice</span></span>
- <span data-ttu-id="30c5d-120">Verifikation för fritextfaktura</span><span class="sxs-lookup"><span data-stu-id="30c5d-120">Free text invoice voucher</span></span>
- <span data-ttu-id="30c5d-121">Fritextkreditfaktura</span><span class="sxs-lookup"><span data-stu-id="30c5d-121">Free text credit note</span></span>
- <span data-ttu-id="30c5d-122">Verifikation för fritextkreditfaktura</span><span class="sxs-lookup"><span data-stu-id="30c5d-122">Free text credit note voucher</span></span>
- <span data-ttu-id="30c5d-123">Följesedel</span><span class="sxs-lookup"><span data-stu-id="30c5d-123">Packing slip</span></span>
- <span data-ttu-id="30c5d-124">Följesedelsverifikation</span><span class="sxs-lookup"><span data-stu-id="30c5d-124">Packing slip voucher</span></span>
- <span data-ttu-id="30c5d-125">Korrigeringsverifikation för följesedel</span><span class="sxs-lookup"><span data-stu-id="30c5d-125">Packing slip correction voucher</span></span>
- <span data-ttu-id="30c5d-126">Verifikation för räntefaktura</span><span class="sxs-lookup"><span data-stu-id="30c5d-126">Interest note voucher</span></span>
- <span data-ttu-id="30c5d-127">Verifikation för kravbrev</span><span class="sxs-lookup"><span data-stu-id="30c5d-127">Collection letter voucher</span></span>

<span data-ttu-id="30c5d-128">**Leverantörsreskontra**</span><span class="sxs-lookup"><span data-stu-id="30c5d-128">**Accounts payable**</span></span>
- <span data-ttu-id="30c5d-129">Fakturaverifikation</span><span class="sxs-lookup"><span data-stu-id="30c5d-129">Invoice voucher</span></span>
- <span data-ttu-id="30c5d-130">Verifikation för kreditfaktura</span><span class="sxs-lookup"><span data-stu-id="30c5d-130">Credit note voucher</span></span>
- <span data-ttu-id="30c5d-131">Produktinleveransverifikation</span><span class="sxs-lookup"><span data-stu-id="30c5d-131">Product receipt voucher</span></span>

<span data-ttu-id="30c5d-132">**Projekthantering**</span><span class="sxs-lookup"><span data-stu-id="30c5d-132">**Project management**</span></span>
- <span data-ttu-id="30c5d-133">Faktura</span><span class="sxs-lookup"><span data-stu-id="30c5d-133">Invoice</span></span>
- <span data-ttu-id="30c5d-134">Fakturaverifikation</span><span class="sxs-lookup"><span data-stu-id="30c5d-134">Invoice voucher</span></span>
- <span data-ttu-id="30c5d-135">Kreditfaktura</span><span class="sxs-lookup"><span data-stu-id="30c5d-135">Credit note</span></span>
- <span data-ttu-id="30c5d-136">Verifikation för kreditfaktura</span><span class="sxs-lookup"><span data-stu-id="30c5d-136">Credit note voucher</span></span> 

### <a name="define-number-sequences"></a><span data-ttu-id="30c5d-137">Definiera nummerserier</span><span class="sxs-lookup"><span data-stu-id="30c5d-137">Define number sequences</span></span>

<span data-ttu-id="30c5d-138">Om du vill definiera nummerserier går du till **Organisationsadministration** > **Nummerserier** > **Nummerserier**.</span><span class="sxs-lookup"><span data-stu-id="30c5d-138">To define number sequences, go to **Organization administration** > **Number sequences** > **Number sequences**.</span></span> <span data-ttu-id="30c5d-139">Du kan definiera så många nummerserier som krävs för att täcka de perioder som påverkas för erforderliga dokument.</span><span class="sxs-lookup"><span data-stu-id="30c5d-139">You can define as many number sequences as required to cover the affected periods for required documents.</span></span> 

<span data-ttu-id="30c5d-140">Ange ett företag för respektive nummerserie.</span><span class="sxs-lookup"><span data-stu-id="30c5d-140">Specify a company for each number sequence.</span></span> <span data-ttu-id="30c5d-141">Segmenten i nummerserierna måste definieras så att de ger kronologisk ordning för perioder.</span><span class="sxs-lookup"><span data-stu-id="30c5d-141">The segments of the number sequences must be defined so that they provide chronological order for periods.</span></span> <span data-ttu-id="30c5d-142">Till exempel kan segmentnamnen innehålla ett särskilt prefix som identifierar en viss period.</span><span class="sxs-lookup"><span data-stu-id="30c5d-142">For example, the segment names can contain a special prefix that identifies a specific period.</span></span>

![Konfigurera nummerserie](media/chrono-num-sequence.jpg)

### <a name="configure-number-sequence-groups"></a><span data-ttu-id="30c5d-144">Konfigurera nummerseriegrupper</span><span class="sxs-lookup"><span data-stu-id="30c5d-144">Configure number sequence groups</span></span>

<span data-ttu-id="30c5d-145">Om du vill konfigurera nummerseriegrupper går du till **Kundreskontra** > **Inställningar** > **Parametrar för kundreskontra**.</span><span class="sxs-lookup"><span data-stu-id="30c5d-145">To configure number sequence groups, go to **Accounts receivable** > **Setup** > **Accounts receivable parameters**.</span></span> <span data-ttu-id="30c5d-146">På fliken **Nummerserier** definierar du så många nummerseriegrupper som krävs för att täcka de perioder som påverkas.</span><span class="sxs-lookup"><span data-stu-id="30c5d-146">On the **Number sequences** tab, define as many number sequences groups as required to cover the affected periods.</span></span> 

<span data-ttu-id="30c5d-147">I avsnittet **Referens** väljer du, för respektive grupp, en av de dokumentreferenser som stöds. I fältet **Nummersekvenskod** refererar du sedan till en nummersekvens som tidigare skapats för relaterad period.</span><span class="sxs-lookup"><span data-stu-id="30c5d-147">For each group, in the **Reference** section, select one of the supported document references, and in the **Number sequence code** field, refer to a number sequence that was previously created for the related period.</span></span>

![Konfiguration av nummerseriegrupp](media/chrono-num-sequence-group.jpg)

<span data-ttu-id="30c5d-149">Konfigurera på samma sätt nummersekvensgrupper i modulerna **Leverantörsreskontra** och **Projekthantering och redovisning**.</span><span class="sxs-lookup"><span data-stu-id="30c5d-149">Similarly, configure number sequence groups in **Accounts payable** and **Project management and accounting** modules.</span></span>

### <a name="configure-number-sequence-groups-chronology"></a><span data-ttu-id="30c5d-150">Konfigurera kornologisk ordning för nummerseriegrupper</span><span class="sxs-lookup"><span data-stu-id="30c5d-150">Configure number sequence groups chronology</span></span>

<span data-ttu-id="30c5d-151">Om du vill konfigurera kornologisk ordning för nummerseriegrupper går du till **Organisationsadministration** > **Nummerserier** > **Kronologiska nummerseriegrupper**.</span><span class="sxs-lookup"><span data-stu-id="30c5d-151">To configure number sequence groups chronology, go to **Organization administration** > **Number sequences** > **Chronological number sequence groups**.</span></span> <span data-ttu-id="30c5d-152">Definiera tillämplighetsvillkor för nummerseriegrupper.</span><span class="sxs-lookup"><span data-stu-id="30c5d-152">Define the applicability conditions for number sequence groups.</span></span>

![Inställningar för kronologiska nummer](media/chrono-num-sequence-group-period.jpg)

| <span data-ttu-id="30c5d-154">Fält</span><span class="sxs-lookup"><span data-stu-id="30c5d-154">Field</span></span>            | <span data-ttu-id="30c5d-155">beskrivning</span><span class="sxs-lookup"><span data-stu-id="30c5d-155">Description</span></span>                                                                                                                                                                                                                                                                                                                                                                                   |
|---------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="30c5d-156">Giltighet</span><span class="sxs-lookup"><span data-stu-id="30c5d-156">Effective</span></span>  | <span data-ttu-id="30c5d-157">Startdatum för tillämplighet för nummerseriegrupp.</span><span class="sxs-lookup"><span data-stu-id="30c5d-157">The start date of number sequence group applicability.</span></span> |
| <span data-ttu-id="30c5d-158">Upphörande</span><span class="sxs-lookup"><span data-stu-id="30c5d-158">Expiration</span></span>      | <span data-ttu-id="30c5d-159">Slutdatum för tillämplighet för nummerseriegrupp.</span><span class="sxs-lookup"><span data-stu-id="30c5d-159">The end date of number sequence group applicability.</span></span> <span data-ttu-id="30c5d-160">Om inget slutdatum tillämpats väljer du **Aldrig**.</span><span class="sxs-lookup"><span data-stu-id="30c5d-160">If no end date is applied, select **Never**.</span></span> |
| <span data-ttu-id="30c5d-161">Nummerseriegrupp</span><span class="sxs-lookup"><span data-stu-id="30c5d-161">Number sequence group</span></span> | <span data-ttu-id="30c5d-162">Nummerseriegrupp som kommer att användas för att generera dokumentnummer under perioden.</span><span class="sxs-lookup"><span data-stu-id="30c5d-162">Number sequence group that will be used to generate document numbers during the period.</span></span> |
| <span data-ttu-id="30c5d-163">Ursprunglig nummerseriegrupp</span><span class="sxs-lookup"><span data-stu-id="30c5d-163">Original number sequence group</span></span> | <span data-ttu-id="30c5d-164">Denna nummerseriegruppkod används för ytterligare filtrering av fall där dokument redan har tilldelats en bestämd *permanent* nummerseriegrupp.</span><span class="sxs-lookup"><span data-stu-id="30c5d-164">This number sequence group code is used for additional filtering for the cases when documents already have a specific *permanent* number sequence group assigned.</span></span> <span data-ttu-id="30c5d-165">Ett tomt värde betraktas som ett specifikt värde.</span><span class="sxs-lookup"><span data-stu-id="30c5d-165">An empty value is considered a specific value.</span></span> <span data-ttu-id="30c5d-166">Om du behöver ignorera en preliminär tilldelad grupp använder du alternativet **Standard** för den här inställningen.</span><span class="sxs-lookup"><span data-stu-id="30c5d-166">If you need to ignore a preliminary assigned group, use the **Default** option for this setup.</span></span> |
| <span data-ttu-id="30c5d-167">Standardvärde</span><span class="sxs-lookup"><span data-stu-id="30c5d-167">Default</span></span> | <span data-ttu-id="30c5d-168">Om inställningen aktiveras ignorerar systemet den preliminära tilldelade dokumentnummerseriegruppen, och endast start- och slutdatum används för tillämplighetsanalys.</span><span class="sxs-lookup"><span data-stu-id="30c5d-168">If turned on, the system ignores the preliminary assigned document number sequence group and uses only the periods start and end dates for applicability analysis.</span></span> <span data-ttu-id="30c5d-169">Om den är inaktiverad använder systemet den fullständiga kombinationen **Giltig** + **Förfaller** + **Ursprunglig nummerseriegrupp** för urval.</span><span class="sxs-lookup"><span data-stu-id="30c5d-169">If turned off, the system uses the full combination **Effective** + **Expiration** + **Original number sequence group** for selection.</span></span> |

## <a name="document-posting"></a><span data-ttu-id="30c5d-170">Dokumentbokföring</span><span class="sxs-lookup"><span data-stu-id="30c5d-170">Document posting</span></span>
<span data-ttu-id="30c5d-171">När du bokför ett dokument tilldelas dokumentet lämplig nummerseriegrupp baserad på dokumentets bokföringsdatum, och används sedan för att skapa ett dokumentnummer baserat på den nummerserie som upptäckts.</span><span class="sxs-lookup"><span data-stu-id="30c5d-171">When you post a document, the appropriate number sequence group is assigned to the document, based on document's posting date, and then used to generate a document number based on the detected number sequence.</span></span> <span data-ttu-id="30c5d-172">Systemet visar ett meddelande om tilldelningar av nummerseriegrupper.</span><span class="sxs-lookup"><span data-stu-id="30c5d-172">The system provides a message regarding the number sequence group assignment.</span></span>

![Dokumentnummer](media/chrono-num-sequence-fti.jpg)

> [!NOTE]
> <span data-ttu-id="30c5d-174">För vissa länder finns det en specifik logik som redan har implementerats för dokumentnumrering.</span><span class="sxs-lookup"><span data-stu-id="30c5d-174">For some countries, there is a specific logic already implemented for document numbering.</span></span> <span data-ttu-id="30c5d-175">I det här fallet åsidosätter landsspecifik logik funktionen **Kronologisk numrering**.</span><span class="sxs-lookup"><span data-stu-id="30c5d-175">In this case, country-specific logic will override the **Chronological numbering** feature.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]