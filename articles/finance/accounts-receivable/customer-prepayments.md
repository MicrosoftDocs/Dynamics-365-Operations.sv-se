---
title: Kundförbetalningar
description: I det här avsnittet beskrivs hur du ställer in och bearbetar förskottsbetalningar från kunder (även kallade kunddepositioner).
author: roschlom
ms.date: 04/30/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustPosting, LedgerJournalTransCustPaym, CustParameters
audience: Application User
ms.reviewer: ''
ms.search.scope: Core, Operations
ms.custom: 24651
ms.assetid: cb82245e-8c02-429c-b36e-8db0e3e6f7e5
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: ''
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c3314803b994aed40e5b04d8546a45bd305d48b6
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6019430"
---
# <a name="customer-prepayments"></a><span data-ttu-id="a103f-103">Kundförbetalningar</span><span class="sxs-lookup"><span data-stu-id="a103f-103">Customer prepayments</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a103f-104">Kundens förskottsbetalningar används när du får en betalning från en kund, men det inte finns någon faktura som betalningen kan kvittas mot.</span><span class="sxs-lookup"><span data-stu-id="a103f-104">Customer prepayments are used when you receive a payment from a customer, but there is no invoice that the payment can be settled against.</span></span> <span data-ttu-id="a103f-105">Dessa typer av betalningar kallas också för kunddepositioner.</span><span class="sxs-lookup"><span data-stu-id="a103f-105">These types of payments are also referred to as customer deposits.</span></span>

<span data-ttu-id="a103f-106">Processen för inställning och arbete med förskottsbetalningar från kunder består av följande grundläggande steg.</span><span class="sxs-lookup"><span data-stu-id="a103f-106">The process of setting up and working with customer prepayments consists of the following basic steps.</span></span>

1. <span data-ttu-id="a103f-107">Skapa en bokföringsprofil för förskottsbetalningar.</span><span class="sxs-lookup"><span data-stu-id="a103f-107">Create a customer posting profile for prepayments.</span></span>
2. <span data-ttu-id="a103f-108">Ställ in parametern **Bokföringsprofil vid verifikation för förskottsbetalningsjournal**.</span><span class="sxs-lookup"><span data-stu-id="a103f-108">Set the **Posting profile with prepayment journal voucher** parameter.</span></span>
3. <span data-ttu-id="a103f-109">Skapa en kundbetalningsjournal och markera kryssrutan **Verifikation för förskottsbetalningsjournal** på varje rad.</span><span class="sxs-lookup"><span data-stu-id="a103f-109">Create a customer payment journal, and select the **Prepayment journal voucher** check box on each line.</span></span>
4. <span data-ttu-id="a103f-110">Bokför kundbetalningsjournalen.</span><span class="sxs-lookup"><span data-stu-id="a103f-110">Post the customer payment journal.</span></span>
5. <span data-ttu-id="a103f-111">När en faktura har genererats kvittar du förskottsbetalningen mot den genom att använda sidan **Kvitta öppna transaktioner**.</span><span class="sxs-lookup"><span data-stu-id="a103f-111">After an invoice is generated, settle the prepayment with it by using the **Settle open transactions** page.</span></span>

## <a name="create-a-customer-posting-profile-for-prepayments"></a><span data-ttu-id="a103f-112">Skapa en bokföringsprofil för förskottsbetalningar</span><span class="sxs-lookup"><span data-stu-id="a103f-112">Create a customer posting profile for prepayments</span></span>

<span data-ttu-id="a103f-113">När du accepterar förskottsbetalningar eller insättningar från dina kunder innan varor eller tjänster levereras, eller innan det finns en faktura i systemet, vill du vanligtvis bokföra kontanter som en skuld i stället för en tillgång i kontoplanen.</span><span class="sxs-lookup"><span data-stu-id="a103f-113">Typically, when you accept prepayments or deposits from your customers before goods or services are delivered, or before an invoice exists in your system, you will want to record the cash as a liability instead of an asset in your chart of accounts.</span></span> <span data-ttu-id="a103f-114">Kraven på att bokföra de här beloppen i redovisningen kan dock skilja sig åt, beroende på land eller region.</span><span class="sxs-lookup"><span data-stu-id="a103f-114">However, the requirements for recording these amounts in your general ledger might differ, depending on your country or region.</span></span> <span data-ttu-id="a103f-115">Rådgör därför med dina revisorer om eventuella lokala regler som gäller.</span><span class="sxs-lookup"><span data-stu-id="a103f-115">Therefore, be sure to consult your accountants about any local regulations that apply.</span></span>

<span data-ttu-id="a103f-116">I allmänhet är processen för att skapa en bokföringsprofil som kan användas för förskottsbetalningar densamma som processen för att skapa andra bokföringsprofiler.</span><span class="sxs-lookup"><span data-stu-id="a103f-116">In general, the process for creating a posting profile that can be used for prepayments is the same as the process for creating other posting profiles.</span></span> <span data-ttu-id="a103f-117">Den primära differensen är huvudkontot som du väljer i fältet **Sammanfattningskonto**.</span><span class="sxs-lookup"><span data-stu-id="a103f-117">The primary difference is the main account that you select in the **Summary account** field.</span></span> <span data-ttu-id="a103f-118">Mer information finns i [Bokföringsprofiler för kund](customer-posting-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="a103f-118">For more information, see [Customer posting profiles](customer-posting-profiles.md).</span></span>

## <a name="define-parameters-for-customer-prepayments"></a><span data-ttu-id="a103f-119">Definiera parametrar för förskottsbetalningar från kunder</span><span class="sxs-lookup"><span data-stu-id="a103f-119">Define parameters for customer prepayments</span></span>

<span data-ttu-id="a103f-120">Det finns två huvudparametrar för kundreskontra som du måste ta hänsyn till när du konfigurerar systemet för förskottsbetalningar från kunder.</span><span class="sxs-lookup"><span data-stu-id="a103f-120">There are two main Accounts receivable parameters that you must consider when you configure the system for customer prepayments.</span></span> <span data-ttu-id="a103f-121">Gör på följande sätt när du vill konfigurera parametrarna.</span><span class="sxs-lookup"><span data-stu-id="a103f-121">Follow these steps to configure the parameters.</span></span>

1. <span data-ttu-id="a103f-122">Gå till **Kundreskontra \> Inställningar \> Parametrar för kundreskontra**.</span><span class="sxs-lookup"><span data-stu-id="a103f-122">Go to **Accounts receivable \> Setup \> Accounts receivable parameters**.</span></span>
2. <span data-ttu-id="a103f-123">Valfritt: Under fliken **Redovisning och moms**, under fliken **Betalning**, ställer du in alternativet **Moms på verifikation för förskottsbetalningsjournal** på **Ja**.</span><span class="sxs-lookup"><span data-stu-id="a103f-123">Optional: On the **Ledger and sales tax** tab, on the **Payment** FastTab, set the **Sales tax on prepayment journal voucher** option to **Yes**.</span></span>
3. <span data-ttu-id="a103f-124">I fältet **Bokföringsprofil vid verifikation för förskottsbetalningsjournal** väljer du den bokföringsprofils som ska användas när förskottsbetalningar från kunder bokförs.</span><span class="sxs-lookup"><span data-stu-id="a103f-124">In the **Posting profile with prepayment journal voucher** field, select the customer posting profile to use when customer prepayments are posted.</span></span>
4. <span data-ttu-id="a103f-125">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="a103f-125">Close the page.</span></span>

## <a name="create-customer-prepayment-vouchers"></a><span data-ttu-id="a103f-126">Skapa verifikationer för förskottsbetalning från kund</span><span class="sxs-lookup"><span data-stu-id="a103f-126">Create customer prepayment vouchers</span></span>

<span data-ttu-id="a103f-127">När du skapar kundbetalningsjournalen måste du, för varje betalning, ställa in alternativet **verifikation för förskottsbetalningsjournal** på **Ja** på sidan **Kundbetalningsjournal**.</span><span class="sxs-lookup"><span data-stu-id="a103f-127">When you create the customer payment journal, for every prepayment, you must set the **Prepayment journal voucher** option to **Yes** on the **Customer payment journal** page.</span></span> <span data-ttu-id="a103f-128">Gör så här om du vill skapa en förskottsbetalning från kund.</span><span class="sxs-lookup"><span data-stu-id="a103f-128">Follow these steps to create a customer prepayment.</span></span>

1. <span data-ttu-id="a103f-129">Gå till **kundreskontra \> Betalningar \> Kundbetalningsjournal**.</span><span class="sxs-lookup"><span data-stu-id="a103f-129">Go to **Accounts receivable \> Payments \> Customer payment journal**.</span></span>
2. <span data-ttu-id="a103f-130">Välj **Ny** för att skapa en journal.</span><span class="sxs-lookup"><span data-stu-id="a103f-130">Select **New** to create a journal.</span></span>
3. <span data-ttu-id="a103f-131">I fältet **Nam** väljer du det journalnamn som ska användas.</span><span class="sxs-lookup"><span data-stu-id="a103f-131">In the **Name** field, select the journal name to use.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="a103f-132">Om du ställde in alternativet **Moms på verifikation för förskottsbetalningsjournal** på **Ja** i föregående procedur, måste du välja ett journalnamn där parametern **Belopp inkluderar moms** har valts.</span><span class="sxs-lookup"><span data-stu-id="a103f-132">If you set the **Sales tax on prepayment journal voucher** option to **Yes** in the previous procedure, you must select a journal name where the **Amount includes sales tax** parameter is selected.</span></span> 

4. <span data-ttu-id="a103f-133">Valfritt: I fältet **Beskrivning** anger du en detaljerad beskrivning.</span><span class="sxs-lookup"><span data-stu-id="a103f-133">Optional: In the **Description** field, enter a detailed description.</span></span>
5. <span data-ttu-id="a103f-134">Markera **rader**</span><span class="sxs-lookup"><span data-stu-id="a103f-134">Select **Lines**.</span></span>
6. <span data-ttu-id="a103f-135">Om det inte finns någon tom rad väljer du **Ny** för att skapa en rad.</span><span class="sxs-lookup"><span data-stu-id="a103f-135">If a blank line doesn't exist, select **New** to create a line.</span></span>
7. <span data-ttu-id="a103f-136">I fältet **Datum** anger du det datum då förskottsbetalningen ska bokföras.</span><span class="sxs-lookup"><span data-stu-id="a103f-136">In the **Date** field, enter the date when the prepayment should be posted.</span></span>
8. <span data-ttu-id="a103f-137">I fältet **Konto** väljer du kund för förskottsbetalning.</span><span class="sxs-lookup"><span data-stu-id="a103f-137">In the **Account** field, select the customer for the prepayment.</span></span>
9. <span data-ttu-id="a103f-138">Valfritt: I fältet **Beskrivning** anger du en detaljerad beskrivning av transaktionen.</span><span class="sxs-lookup"><span data-stu-id="a103f-138">Optional: In the **Description** field, enter a detailed description of the transaction.</span></span>
10. <span data-ttu-id="a103f-139">I fältet **Kredit** anger du beloppet på förskottsbetalningen.</span><span class="sxs-lookup"><span data-stu-id="a103f-139">In the **Credit** field, enter the amount of the prepayment.</span></span>
11. <span data-ttu-id="a103f-140">I fältet **Motkonto** väljer du motkonto för betalningen.</span><span class="sxs-lookup"><span data-stu-id="a103f-140">In the **Offset account** field, select the account to offset the payment to.</span></span> <span data-ttu-id="a103f-141">Välj till exempel det bank- eller huvudkonto som betalningen ska bokföras på.</span><span class="sxs-lookup"><span data-stu-id="a103f-141">For example, select the bank or main account to post the payment to.</span></span>
12. <span data-ttu-id="a103f-142">I fältet **Betalningsmetod** väljer du kundens betalningsmetod.</span><span class="sxs-lookup"><span data-stu-id="a103f-142">In the **Method of payment** field, select the customer's method of payment.</span></span>
13. <span data-ttu-id="a103f-143">Under fliken **Betalning** ställer du in alternativet **Verifikation för förskottsbetalningsjournal** på **Ja**.</span><span class="sxs-lookup"><span data-stu-id="a103f-143">On the **Payment** tab, set the **Prepayment journal voucher** option to **Yes**.</span></span>
14. <span data-ttu-id="a103f-144">Upprepa steg 7 till och med 13 för varje ytterligare förskottsbetalning som måste bokföras.</span><span class="sxs-lookup"><span data-stu-id="a103f-144">Repeat steps 7 through 13 for each additional prepayment that must be posted.</span></span>
15. <span data-ttu-id="a103f-145">Välj **Bokför** för att slutföra journalen.</span><span class="sxs-lookup"><span data-stu-id="a103f-145">Select **Post** to finalize the journal.</span></span>

## <a name="settle-prepayments-with-invoices"></a><span data-ttu-id="a103f-146">Kvitta förskottsbetalningar mot fakturor</span><span class="sxs-lookup"><span data-stu-id="a103f-146">Settle prepayments with invoices</span></span>

<span data-ttu-id="a103f-147">Du kan använda arbetsytan **Kundbetalningar** för att enkelt hitta och kvitta betalningar som inte har kvittats helt.</span><span class="sxs-lookup"><span data-stu-id="a103f-147">You can use the **Customer payments** workspace to easily find and settle payments that haven't been fully settled.</span></span>

1. <span data-ttu-id="a103f-148">På instrumentpanelen **Start** väljer du ikonen **Kundbetalningar**.</span><span class="sxs-lookup"><span data-stu-id="a103f-148">On the **Home** dashboard, select the **Customer payments** tile.</span></span>
2. <span data-ttu-id="a103f-149">I avsnittet **Kundtransaktioner**, under fliken **Ej kvittade betalningar**, söker du efter och väljer betalningen som ska kvittas.</span><span class="sxs-lookup"><span data-stu-id="a103f-149">In the **Customer transactions** section, on the **Payments not settled** tab, search for and select the payment to settle.</span></span>
3. <span data-ttu-id="a103f-150">Välj **Kvitta transaktioner**.</span><span class="sxs-lookup"><span data-stu-id="a103f-150">Select **Settle transactions**.</span></span>
4. <span data-ttu-id="a103f-151">Markera kryssrutan **Markera** för fakturan och betalningen som ska kvittas.</span><span class="sxs-lookup"><span data-stu-id="a103f-151">Select the **Mark** check box for the invoice and the payment that will be settled.</span></span>
5. <span data-ttu-id="a103f-152">Vald **bokföring**</span><span class="sxs-lookup"><span data-stu-id="a103f-152">Select **Post**.</span></span>

<span data-ttu-id="a103f-153">Mer information om hur du kvittar öppna transaktioner finns i [översikten över kvittningar](/cash-bank-management/settlement-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a103f-153">For more information about how to settle open transactions, see [Settlement overview](/cash-bank-management/settlement-overview.md).</span></span>
