---
title: Skapa ett autogiromedgivande för en kund
description: Den här uppgifthandbok visar hur du skapar ett autogiromedgivande och använder det på en faktura.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustTable, CustBankAccounts, BankAccountTable, CustPaymMode, CustDirectDebitMandate, BankAccountTableLookUp, SrsReportViewerForm,  LogisticsAddressCityLookup, CustFreeInvoice, CustTableLookup
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5ca5ff2290df2179004ca1cebd11f67fbb7a724e
ms.sourcegitcommit: cbcf344b3b552acca56c3e27606eac7f2f124afe
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/22/2019
ms.locfileid: "1916379"
---
# <a name="create-a-direct-debit-mandate-for-a-customer"></a><span data-ttu-id="9bbf1-103">Skapa ett autogiromedgivande för en kund</span><span class="sxs-lookup"><span data-stu-id="9bbf1-103">Create a direct debit mandate for a customer</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="9bbf1-104">Den här uppgifthandbok visar hur du skapar ett autogiromedgivande och använder det på en faktura.</span><span class="sxs-lookup"><span data-stu-id="9bbf1-104">This task guide demonstrates how to create a direct debit mandate and use it on an invoice.</span></span>


## <a name="create-a-bank-account"></a><span data-ttu-id="9bbf1-105">Skapa ett bankkonto</span><span class="sxs-lookup"><span data-stu-id="9bbf1-105">Create a bank account</span></span>
1. <span data-ttu-id="9bbf1-106">I **navigeringsfönstret** går du till **Moduler > Kundreskontra > Kunder > Alla kunder**.</span><span class="sxs-lookup"><span data-stu-id="9bbf1-106">In the **Navigation pane**, go to **Modules > Accounts receivable > Customers > All customers**.</span></span>
2. <span data-ttu-id="9bbf1-107">Välj en post i listan.</span><span class="sxs-lookup"><span data-stu-id="9bbf1-107">In the list, select a record.</span></span> <span data-ttu-id="9bbf1-108">Välj till exempel US-001</span><span class="sxs-lookup"><span data-stu-id="9bbf1-108">For example, select US-001</span></span>
3. <span data-ttu-id="9bbf1-109">Klicka på **Kund** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="9bbf1-109">On the Action Pane, click **Customer**.</span></span>
4. <span data-ttu-id="9bbf1-110">Klicka på **Bankkonton**.</span><span class="sxs-lookup"><span data-stu-id="9bbf1-110">Click **Bank accounts**.</span></span>
5. <span data-ttu-id="9bbf1-111">Klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="9bbf1-111">Click **New**.</span></span>
6. <span data-ttu-id="9bbf1-112">Ange ett värde i fältet **Bankkonto**.</span><span class="sxs-lookup"><span data-stu-id="9bbf1-112">In the **Bank account** field, type a value.</span></span>
7. <span data-ttu-id="9bbf1-113">Skriv ett värde i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="9bbf1-113">In the **Name** field, type a value.</span></span>
8. <span data-ttu-id="9bbf1-114">Ange ett värde i fältet **IBAN**.</span><span class="sxs-lookup"><span data-stu-id="9bbf1-114">In the **IBAN** field, type a value.</span></span>
9. <span data-ttu-id="9bbf1-115">Ange ett värde i fältet **Valuta**.</span><span class="sxs-lookup"><span data-stu-id="9bbf1-115">In the **Currency** field, type a value.</span></span>
10. <span data-ttu-id="9bbf1-116">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="9bbf1-116">Click **Save**.</span></span>
11. <span data-ttu-id="9bbf1-117">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="9bbf1-117">Close the page.</span></span>
12. <span data-ttu-id="9bbf1-118">I **Navigeringsfönstret**, gå till **Moduler > Kassa- och bankhantering > Bankkonton > Bankkonton**.</span><span class="sxs-lookup"><span data-stu-id="9bbf1-118">In the **Navigation pane**, go to **Modules > Cash and bank management > Bank accounts > Bank accounts**.</span></span>
13. <span data-ttu-id="9bbf1-119">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="9bbf1-119">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="9bbf1-120">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="9bbf1-120">In the list, click the link in the selected row.</span></span>
15. <span data-ttu-id="9bbf1-121">Klicka på **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="9bbf1-121">Click **Edit**.</span></span>
16. <span data-ttu-id="9bbf1-122">Expandera snabbfliken **Ytterligare identifiering**.</span><span class="sxs-lookup"><span data-stu-id="9bbf1-122">Expand the **Additional identification** fastTab.</span></span>
17. <span data-ttu-id="9bbf1-123">Ange ett värde i fältet **ID för direktdebitering**.</span><span class="sxs-lookup"><span data-stu-id="9bbf1-123">In the **Direct debit ID** field, type a value.</span></span>
18. <span data-ttu-id="9bbf1-124">Ange ett värde i fältet **IBAN**.</span><span class="sxs-lookup"><span data-stu-id="9bbf1-124">In the **IBAN** field, type a value.</span></span>
19. <span data-ttu-id="9bbf1-125">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="9bbf1-125">Close the page.</span></span>
20. <span data-ttu-id="9bbf1-126">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="9bbf1-126">Close the page.</span></span>

## <a name="define-the-electronic-payment-method"></a><span data-ttu-id="9bbf1-127">Definiera den elektroniska betalningsmetoden</span><span class="sxs-lookup"><span data-stu-id="9bbf1-127">Define the electronic payment method</span></span>
1. <span data-ttu-id="9bbf1-128">I **navigeringsfönstret**, gå till **Moduler > Kundreskontra > Betalningsinställning > Betalningsmetoder**.</span><span class="sxs-lookup"><span data-stu-id="9bbf1-128">In the **Navigation pane**, go to **Modules > Accounts receivable > Payments setup > Methods of payment**.</span></span>
2. <span data-ttu-id="9bbf1-129">Klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="9bbf1-129">Click **New**.</span></span>
3. <span data-ttu-id="9bbf1-130">Skriv ett värde i fältet **Betalningsmetod**.</span><span class="sxs-lookup"><span data-stu-id="9bbf1-130">In the **Method of payment** field, type a value.</span></span>
4. <span data-ttu-id="9bbf1-131">I fältet **Beskrivning** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="9bbf1-131">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="9bbf1-132">Välj "Elektronisk betalning" i fältet **Betalningstyp**.</span><span class="sxs-lookup"><span data-stu-id="9bbf1-132">In the **Payment type** field, enter 'Electronic payment'.</span></span> <span data-ttu-id="9bbf1-133">Betalningstypen för en betalningsmetod med autogiromedgivande måste vara elektronisk betalning.</span><span class="sxs-lookup"><span data-stu-id="9bbf1-133">The payment type for a direct debit mandate method of payment must be Electronic payment.</span></span>
6. <span data-ttu-id="9bbf1-134">Välj Ja i fältet **Kräv medgivande**.</span><span class="sxs-lookup"><span data-stu-id="9bbf1-134">Select Yes in the **Require mandate** field.</span></span>
7. <span data-ttu-id="9bbf1-135">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="9bbf1-135">Close the page.</span></span>

## <a name="add-a-direct-debit-mandate-to-a-customer"></a><span data-ttu-id="9bbf1-136">Lägg till ett autogiromedgivande till en kund.</span><span class="sxs-lookup"><span data-stu-id="9bbf1-136">Add a direct debit mandate to a customer.</span></span>
1. <span data-ttu-id="9bbf1-137">I **navigeringsfönstret** går du till **Moduler > Kundreskontra > Kunder > Alla kunder**.</span><span class="sxs-lookup"><span data-stu-id="9bbf1-137">In the **Navigation pane**, go to **Modules > Accounts receivable > Customers > All customers**.</span></span>
2. <span data-ttu-id="9bbf1-138">Välj en post i listan.</span><span class="sxs-lookup"><span data-stu-id="9bbf1-138">In the list, select a record.</span></span> <span data-ttu-id="9bbf1-139">Välj till exempel US-001</span><span class="sxs-lookup"><span data-stu-id="9bbf1-139">For example, select US-001</span></span>
3. <span data-ttu-id="9bbf1-140">Klicka på **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="9bbf1-140">Click **Edit**.</span></span>
4. <span data-ttu-id="9bbf1-141">Expandera snabbfliken **Standardvärden för betalningar**.</span><span class="sxs-lookup"><span data-stu-id="9bbf1-141">Expand the **Payment defaults** fastTab.</span></span>
5. <span data-ttu-id="9bbf1-142">I fältet **Betalningsmetod** anger du eller väljer ett värde.</span><span class="sxs-lookup"><span data-stu-id="9bbf1-142">In the **Method of payment** field, enter or select a value.</span></span>
6. <span data-ttu-id="9bbf1-143">Expandera snabbfliken **Standardvärden för betalningar**.</span><span class="sxs-lookup"><span data-stu-id="9bbf1-143">Expand the **Payment defaults** fastTab.</span></span>
7. <span data-ttu-id="9bbf1-144">Expandera snabbfliken **Autogiromedgivanden**.</span><span class="sxs-lookup"><span data-stu-id="9bbf1-144">Expand the **Direct debit mandates** fastTab.</span></span>
8. <span data-ttu-id="9bbf1-145">Klicka på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="9bbf1-145">Click **Add**.</span></span>
9. <span data-ttu-id="9bbf1-146">I fältet **Bankkonto** anger du eller väljer ett värde.</span><span class="sxs-lookup"><span data-stu-id="9bbf1-146">In the **Bank account** field, enter or select a value.</span></span>
10. <span data-ttu-id="9bbf1-147">Ange eller välj ett värde i fältet **Betalningsmottagarens bankkonto**.</span><span class="sxs-lookup"><span data-stu-id="9bbf1-147">In the **Creditor bank account** field, enter or select a value.</span></span>
11. <span data-ttu-id="9bbf1-148">I fältet **Betalningsfrekvens**, ange det antal betalningar som du förväntar dig att bearbeta för detta medgivande.</span><span class="sxs-lookup"><span data-stu-id="9bbf1-148">In the **Payment frequency** field, enter the number of payments that you expect to process for this mandate.</span></span>
12. <span data-ttu-id="9bbf1-149">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="9bbf1-149">Click **OK**.</span></span>
13. <span data-ttu-id="9bbf1-150">Klicka på **Skriv ut**.</span><span class="sxs-lookup"><span data-stu-id="9bbf1-150">Click **Print**.</span></span>
14. <span data-ttu-id="9bbf1-151">Klicka på **Medgivanderapport**.</span><span class="sxs-lookup"><span data-stu-id="9bbf1-151">Click **Mandate report**.</span></span>
15. <span data-ttu-id="9bbf1-152">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="9bbf1-152">Close the page.</span></span>
16. <span data-ttu-id="9bbf1-153">Klicka på **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="9bbf1-153">Click **Edit**.</span></span>
17. <span data-ttu-id="9bbf1-154">Ange ett datum i fältet **Datum för undertecknande**.</span><span class="sxs-lookup"><span data-stu-id="9bbf1-154">In the **Signature date** field, enter a date.</span></span>
18. <span data-ttu-id="9bbf1-155">Klicka på **Ja**.</span><span class="sxs-lookup"><span data-stu-id="9bbf1-155">Click **Yes**.</span></span>
19. <span data-ttu-id="9bbf1-156">Ange platsen där medgivandet signerades.</span><span class="sxs-lookup"><span data-stu-id="9bbf1-156">Enter the location where the mandate was signed.</span></span>
20. <span data-ttu-id="9bbf1-157">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="9bbf1-157">Click **OK**.</span></span>
21. <span data-ttu-id="9bbf1-158">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="9bbf1-158">Close the page.</span></span>

## <a name="create-a-free-text-invoice-with-mandate"></a><span data-ttu-id="9bbf1-159">Skapa en fritextfaktura med fullmakt</span><span class="sxs-lookup"><span data-stu-id="9bbf1-159">Create a free text invoice with mandate</span></span>
1. <span data-ttu-id="9bbf1-160">I **navigeringsfönstret** går du till **Moduler > Kundreskontra > Fakturor > Alla fritextfakturor**.</span><span class="sxs-lookup"><span data-stu-id="9bbf1-160">In the **Navigation pane**, go to **Modules > Accounts receivable > Invoices > All free text invoices**.</span></span>
2. <span data-ttu-id="9bbf1-161">Klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="9bbf1-161">Click **New**.</span></span>
3. <span data-ttu-id="9bbf1-162">Välj kunden som du lagt till medgivande för.</span><span class="sxs-lookup"><span data-stu-id="9bbf1-162">Select the customer that you added the mandate to.</span></span>
4. <span data-ttu-id="9bbf1-163">Ange eller välj ett värde i fältet **Autogiromedgivande-ID**.</span><span class="sxs-lookup"><span data-stu-id="9bbf1-163">In the **Direct debit mandate ID** field, enter or select a value.</span></span>

