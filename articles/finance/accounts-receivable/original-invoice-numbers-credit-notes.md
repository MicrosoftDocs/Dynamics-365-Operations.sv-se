---
title: Referenser till ursprungliga fakturor i kreditfakturor
description: I detta ämne beskrivs hur du ställer in och skriver ut de ursprungliga fakturanumren på relaterade kreditfakturor.
author: ilkond
manager: AnnBe
ms.date: 01/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: ilyako
ms.search.validFrom: 2021-03-19
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 04a4fc96cb7de60052b17e36c33ad5d5be322be4
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5207361"
---
# <a name="references-to-original-invoices-in-credit-notes"></a><span data-ttu-id="ade4b-103">Referenser till ursprungliga fakturor i kreditfakturor</span><span class="sxs-lookup"><span data-stu-id="ade4b-103">References to original invoices in credit notes</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="ade4b-104">I vissa länder och regioner finns det ett juridiskt krav på att utskrivna kreditfakturor innehåller referenser till de ursprungliga fakturorna.</span><span class="sxs-lookup"><span data-stu-id="ade4b-104">In some countries and regions, there is a legal requirement that printed credit notes include references to the original invoices.</span></span> <span data-ttu-id="ade4b-105">I detta ämne beskrivs hur du ställer in och skriver ut de ursprungliga fakturanumren på relaterade kreditfakturor.</span><span class="sxs-lookup"><span data-stu-id="ade4b-105">This topic explains how to set up and print the original invoice numbers in related credit notes.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ade4b-106">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="ade4b-106">Prerequisites</span></span>

- <span data-ttu-id="ade4b-107">I arbetsytan **Funktionshantering** aktiverar du funktionen **Kreditfaktureringslayout för försäljnings- och projektfakturerapporter**.</span><span class="sxs-lookup"><span data-stu-id="ade4b-107">In the **Feature management** workspace, turn on the **Credit invoicing layout for sales and project invoice reports** feature.</span></span> <span data-ttu-id="ade4b-108">Mer information finns i [Översikt för funktionshantering](../../fin-and-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ade4b-108">For more information, see [Feature management overview](../../fin-and-ops/get-started/feature-management/feature-management-overview.md).</span></span>
- <span data-ttu-id="ade4b-109">De utskriftsbara formaten för de nödvändiga dokumenten måste konfigureras i Utskriftshantering.</span><span class="sxs-lookup"><span data-stu-id="ade4b-109">The printable formats of the required documents must be configured in Print management.</span></span>

<span data-ttu-id="ade4b-110">Funktionerna som beskrivs i detta ämne gäller för följande dokument:</span><span class="sxs-lookup"><span data-stu-id="ade4b-110">The functionality that is described in this topic applies to the following documents:</span></span>

<span data-ttu-id="ade4b-111">**Kundreskontra**</span><span class="sxs-lookup"><span data-stu-id="ade4b-111">**Accounts receivable**</span></span>

- <span data-ttu-id="ade4b-112">Fritextkreditfaktura</span><span class="sxs-lookup"><span data-stu-id="ade4b-112">Free text credit note</span></span>
- <span data-ttu-id="ade4b-113">Kundkreditfaktura</span><span class="sxs-lookup"><span data-stu-id="ade4b-113">Customer credit note</span></span>

<span data-ttu-id="ade4b-114">**Projekthantering och redovisning**</span><span class="sxs-lookup"><span data-stu-id="ade4b-114">**Project management and accounting**</span></span>

- <span data-ttu-id="ade4b-115">Projekts kreditfaktura</span><span class="sxs-lookup"><span data-stu-id="ade4b-115">Project credit note</span></span>

## <a name="configure-accounts-receivable-parameters"></a><span data-ttu-id="ade4b-116">Konfigurera parametrar för kundreskontra</span><span class="sxs-lookup"><span data-stu-id="ade4b-116">Configure Accounts receivable parameters</span></span>

<span data-ttu-id="ade4b-117">Följ dessa steg om du vill ställa in parametern som styr huruvida referenser till de ursprungliga fakturorna skrivs ut i relaterade kreditfakturor.</span><span class="sxs-lookup"><span data-stu-id="ade4b-117">Follow these steps to set the parameter that controls whether references to the original invoices are printed in related credit notes.</span></span>

1. <span data-ttu-id="ade4b-118">Gå till **Kundreskontra** \> **Inställningar** \> **Parametrar för kundreskontra**.</span><span class="sxs-lookup"><span data-stu-id="ade4b-118">Go to **Accounts receivable** \> **Setup** \> **Accounts receivable parameters**.</span></span>
2. <span data-ttu-id="ade4b-119">I fliken **Uppdateringar**, på snabbfliken **Faktura**, anger du alternativet **Tillämpa layouten för kreditfakturor på rapporter för försäljnings- och projektfakturor** som **Ja**.</span><span class="sxs-lookup"><span data-stu-id="ade4b-119">On the **Updates** tab, on the **Invoice** FastTab, set the **Apply the credit invoicing layout into sales and project invoice reports** option to **Yes**.</span></span>

![Konfigurera parametrar för kundreskontra](media/original-invoice-number-in-credit-note.jpg)

## <a name="define-references-to-original-invoices"></a><span data-ttu-id="ade4b-121">Definiera referenser till ursprungliga fakturor</span><span class="sxs-lookup"><span data-stu-id="ade4b-121">Define references to original invoices</span></span>

<span data-ttu-id="ade4b-122">Använd följande procedurer för att definiera referenser till ursprungliga fakturor, baserat på dokumenttypen.</span><span class="sxs-lookup"><span data-stu-id="ade4b-122">Use the following procedures to define references to original invoices, based on the document type.</span></span>

### <a name="free-text-credit-note"></a><span data-ttu-id="ade4b-123">Fritextkreditfaktura</span><span class="sxs-lookup"><span data-stu-id="ade4b-123">Free text credit note</span></span>

1. <span data-ttu-id="ade4b-124">Gå till **Kundreskontra** \> **Fakturor** \> **Alla fritextfakturor**.</span><span class="sxs-lookup"><span data-stu-id="ade4b-124">Go to **Accounts receivable** \> **Invoices** \> **All free text invoices**.</span></span>
2. <span data-ttu-id="ade4b-125">Skapa en ny kreditfaktura eller välj en befintlig kreditfaktura.</span><span class="sxs-lookup"><span data-stu-id="ade4b-125">Create a new credit note, or select an existing credit note.</span></span>
3. <span data-ttu-id="ade4b-126">Öppna fakturan.</span><span class="sxs-lookup"><span data-stu-id="ade4b-126">Open the invoice.</span></span>
4. <span data-ttu-id="ade4b-127">I åtgärdsfönstret på fliken **Faktura** i gruppen **Funktioner** väljer du **Kreditfaktura**.</span><span class="sxs-lookup"><span data-stu-id="ade4b-127">On the Action Pane, on the **Invoice** tab, in the **Functions** group, select **Credit invoicing**.</span></span>
5. <span data-ttu-id="ade4b-128">Ange referensen till den ursprungliga fakturan och välj orsaken till korrigeringen.</span><span class="sxs-lookup"><span data-stu-id="ade4b-128">Enter the reference to the original invoice, and select the reason for the correction.</span></span>

![Definiera referensen för en fritextfaktura](media/reference-original-invoice-FTI.jpg)

### <a name="customer-credit-note"></a><span data-ttu-id="ade4b-130">Kundkreditfaktura</span><span class="sxs-lookup"><span data-stu-id="ade4b-130">Customer credit note</span></span>

1. <span data-ttu-id="ade4b-131">Gå till **Kundreskontra** \> **Order** \> **Alla försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="ade4b-131">Go to **Accounts receivable** \> **Orders** \> **All sales orders**.</span></span>
2. <span data-ttu-id="ade4b-132">Välj och öppna den fakturerade försäljningsorder som måste korrigeras.</span><span class="sxs-lookup"><span data-stu-id="ade4b-132">Select and open the invoiced sales order that must be corrected.</span></span>
3. <span data-ttu-id="ade4b-133">I åtgärdsfönstret, på fliken **Sälj** i gruppen **Kreditfaktura**, väljer du **Kreditfaktura**.</span><span class="sxs-lookup"><span data-stu-id="ade4b-133">On the Action Pane, on the **Sell** tab, in the **Credit note** group, select **Credit note**.</span></span>
4. <span data-ttu-id="ade4b-134">Ange orsaken till korrigeringen.</span><span class="sxs-lookup"><span data-stu-id="ade4b-134">Enter the reason for the correction.</span></span> <span data-ttu-id="ade4b-135">Referensen till den ursprungliga fakturan skapas automatiskt.</span><span class="sxs-lookup"><span data-stu-id="ade4b-135">The reference to the original invoice is automatically established.</span></span>

![Definiera referensen för en försäljningsorder](media/reference-original-invoice-SO.jpg)

### <a name="project-credit-note"></a><span data-ttu-id="ade4b-137">Projekts kreditfaktura</span><span class="sxs-lookup"><span data-stu-id="ade4b-137">Project credit note</span></span>

1. <span data-ttu-id="ade4b-138">Gå till **Projekthantering och redovisning** \> **Projektfakturor** \> **Projektfakturor**.</span><span class="sxs-lookup"><span data-stu-id="ade4b-138">Go to **Project management and accounting** \> **Project invoices** \> **Project invoices**.</span></span>
2. <span data-ttu-id="ade4b-139">Välj och öppna projektfakturan som måste korrigeras.</span><span class="sxs-lookup"><span data-stu-id="ade4b-139">Select and open the project invoice that must be corrected.</span></span>
3. <span data-ttu-id="ade4b-140">I åtgärdsfönstret, i fliken **Projektfaktura** i gruppen **Funktioner**, väljer du **Välj för kreditfaktura**.</span><span class="sxs-lookup"><span data-stu-id="ade4b-140">On the Action Pane, on the **Project invoice** tab, in the **Functions** group, select **Select for credit note**.</span></span>
4. <span data-ttu-id="ade4b-141">Välj **Kreditfaktura**.</span><span class="sxs-lookup"><span data-stu-id="ade4b-141">Select **Credit invoicing**.</span></span>
5. <span data-ttu-id="ade4b-142">Ange orsaken till korrigeringen.</span><span class="sxs-lookup"><span data-stu-id="ade4b-142">Enter the reason for the correction.</span></span> <span data-ttu-id="ade4b-143">Referensen till den ursprungliga fakturan skapas automatiskt.</span><span class="sxs-lookup"><span data-stu-id="ade4b-143">The reference to the original invoice is automatically established.</span></span>

![Definiera referensen för en projektfaktura](media/reference-original-invoice-project.jpg)

## <a name="printing-credit-notes"></a><span data-ttu-id="ade4b-145">Skriva ut kreditfakturor</span><span class="sxs-lookup"><span data-stu-id="ade4b-145">Printing credit notes</span></span>

<span data-ttu-id="ade4b-146">När du skriver ut fritext-, kund- och projektkreditfakturor kommer dessa att inkludera referensen till den ursprungliga fakturan och korrigeringsorsaken.</span><span class="sxs-lookup"><span data-stu-id="ade4b-146">When you print free text, customer, and project credit notes, they will include the reference to the original invoice and the correction reason.</span></span>

![Utskriven kreditfaktura](media/credit-note-FTI.jpg)

> [!NOTE]
> <span data-ttu-id="ade4b-148">Se till att dokumentens utskrivbara format är korrekt konfigurerade, med antagandet att referenser till ursprungliga fakturor skrivs ut.</span><span class="sxs-lookup"><span data-stu-id="ade4b-148">Make sure that the printable formats of the documents are correctly configured, on the assumption that references to original invoices will be printed.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]