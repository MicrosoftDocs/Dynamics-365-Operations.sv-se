---
title: Skapa ett autogiromedgivande för en kund
description: Den här uppgifthandbok visar hur du skapar ett autogiromedgivande och använder det på en faktura.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/29/2018
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
ms.openlocfilehash: 7c93a1aba6ca32e783a6ed6f005c72aab3e06978
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2019
ms.locfileid: "1843011"
---
# <a name="create-a-direct-debit-mandate-for-a-customer"></a><span data-ttu-id="f73e0-103">Skapa ett autogiromedgivande för en kund</span><span class="sxs-lookup"><span data-stu-id="f73e0-103">Create a direct debit mandate for a customer</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f73e0-104">Den här uppgifthandbok visar hur du skapar ett autogiromedgivande och använder det på en faktura.</span><span class="sxs-lookup"><span data-stu-id="f73e0-104">This task guide demonstrates how to create a direct debit mandate and use it on an invoice.</span></span>


## <a name="create-a-bank-account"></a><span data-ttu-id="f73e0-105">Skapa ett bankkonto</span><span class="sxs-lookup"><span data-stu-id="f73e0-105">Create a bank account</span></span>
1. <span data-ttu-id="f73e0-106">Gå till Leverantörsreskontra > Kunder > Alla kunder.</span><span class="sxs-lookup"><span data-stu-id="f73e0-106">Go to Accounts receivable > Customers > All customers.</span></span>
2. <span data-ttu-id="f73e0-107">Välj till exempel US-001</span><span class="sxs-lookup"><span data-stu-id="f73e0-107">For example, select US-001</span></span>
3. <span data-ttu-id="f73e0-108">Klicka på Kund i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="f73e0-108">On the Action Pane, click Customer.</span></span>
4. <span data-ttu-id="f73e0-109">Klicka på bankkonton.</span><span class="sxs-lookup"><span data-stu-id="f73e0-109">Click Bank accounts.</span></span>
5. <span data-ttu-id="f73e0-110">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="f73e0-110">Click New.</span></span>
6. <span data-ttu-id="f73e0-111">I fältet Bankkonto, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="f73e0-111">In the Bank account field, type a value.</span></span>
7. <span data-ttu-id="f73e0-112">Skriv ett värde i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="f73e0-112">In the Name field, type a value.</span></span>
8. <span data-ttu-id="f73e0-113">Ange ett värde i fältet IBAN.</span><span class="sxs-lookup"><span data-stu-id="f73e0-113">In the IBAN field, type a value.</span></span>
9. <span data-ttu-id="f73e0-114">Ange ett värde i fältet Valuta.</span><span class="sxs-lookup"><span data-stu-id="f73e0-114">In the Currency field, type a value.</span></span>
10. <span data-ttu-id="f73e0-115">Klicka på Spara.</span><span class="sxs-lookup"><span data-stu-id="f73e0-115">Click Save.</span></span>
11. <span data-ttu-id="f73e0-116">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f73e0-116">Close the page.</span></span>
12. <span data-ttu-id="f73e0-117">Gå till Kassa- och bankhantering > Bankkonton > Bankkonton.</span><span class="sxs-lookup"><span data-stu-id="f73e0-117">Go to Cash and bank management > Bank accounts > Bank accounts.</span></span>
13. <span data-ttu-id="f73e0-118">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="f73e0-118">In the list, find and select the desired record.</span></span>
14. <span data-ttu-id="f73e0-119">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="f73e0-119">In the list, click the link in the selected row.</span></span>
15. <span data-ttu-id="f73e0-120">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="f73e0-120">Click Edit.</span></span>
16. <span data-ttu-id="f73e0-121">Expandera avsnittet Additional identification section.</span><span class="sxs-lookup"><span data-stu-id="f73e0-121">Expand the Additional identification section.</span></span>
17. <span data-ttu-id="f73e0-122">I fältet för autogiro-ID anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="f73e0-122">In the Direct debit ID field, type a value.</span></span>
18. <span data-ttu-id="f73e0-123">Ange ett värde i fältet IBAN.</span><span class="sxs-lookup"><span data-stu-id="f73e0-123">In the IBAN field, type a value.</span></span>
19. <span data-ttu-id="f73e0-124">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f73e0-124">Close the page.</span></span>
20. <span data-ttu-id="f73e0-125">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f73e0-125">Close the page.</span></span>

## <a name="define-the-electronic-payment-method"></a><span data-ttu-id="f73e0-126">Definiera den elektroniska betalningsmetoden</span><span class="sxs-lookup"><span data-stu-id="f73e0-126">Define the electronic payment method</span></span>
1. <span data-ttu-id="f73e0-127">Gå till Kundreskontra > Betalningsinställning > Betalningsmetoder.</span><span class="sxs-lookup"><span data-stu-id="f73e0-127">Go to Accounts receivable > Payments setup > Methods of payment.</span></span>
2. <span data-ttu-id="f73e0-128">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="f73e0-128">Click New.</span></span>
3. <span data-ttu-id="f73e0-129">Skriv ett värde i fältet Betalningsmetod.</span><span class="sxs-lookup"><span data-stu-id="f73e0-129">In the Method of payment field, type a value.</span></span>
4. <span data-ttu-id="f73e0-130">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="f73e0-130">In the Description field, type a value.</span></span>
5. <span data-ttu-id="f73e0-131">Betalningstypen för en betalningsmetod med autogiromedgivande måste vara elektronisk betalning.</span><span class="sxs-lookup"><span data-stu-id="f73e0-131">The payment type for a direct debit mandate method of payment must be Electronic payment.</span></span>
6. <span data-ttu-id="f73e0-132">Välj Ja i fältet kräv medgivande.</span><span class="sxs-lookup"><span data-stu-id="f73e0-132">Select Yes in the Require mandate field.</span></span>
7. <span data-ttu-id="f73e0-133">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f73e0-133">Close the page.</span></span>

## <a name="add-a-direct-debit-mandate-to-a-customer"></a><span data-ttu-id="f73e0-134">Lägg till ett autogiromedgivande till en kund.</span><span class="sxs-lookup"><span data-stu-id="f73e0-134">Add a direct debit mandate to a customer.</span></span>
1. <span data-ttu-id="f73e0-135">Gå till Leverantörsreskontra > Kunder > Alla kunder.</span><span class="sxs-lookup"><span data-stu-id="f73e0-135">Go to Accounts receivable > Customers > All customers.</span></span>
2. <span data-ttu-id="f73e0-136">Välj till exempel US-001</span><span class="sxs-lookup"><span data-stu-id="f73e0-136">For example, select US-001</span></span>
3. <span data-ttu-id="f73e0-137">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="f73e0-137">Click Edit.</span></span>
4. <span data-ttu-id="f73e0-138">Expandera avsnittet Standardvärden för betalningar.</span><span class="sxs-lookup"><span data-stu-id="f73e0-138">Expand the Payment defaults section.</span></span>
5. <span data-ttu-id="f73e0-139">Ange eller välj ett värde i fältet Betalningsmetod.</span><span class="sxs-lookup"><span data-stu-id="f73e0-139">In the Method of payment field, enter or select a value.</span></span>
6. <span data-ttu-id="f73e0-140">Expandera avsnittet Standardvärden för betalningar.</span><span class="sxs-lookup"><span data-stu-id="f73e0-140">Expand the Payment defaults section.</span></span>
7. <span data-ttu-id="f73e0-141">Expandera avsnittet Autogiromedgivanden.</span><span class="sxs-lookup"><span data-stu-id="f73e0-141">Expand the Direct debit mandates section.</span></span>
8. <span data-ttu-id="f73e0-142">Klicka på Lägg till.</span><span class="sxs-lookup"><span data-stu-id="f73e0-142">Click Add.</span></span>
9. <span data-ttu-id="f73e0-143">Ange eller välj ett värde i fältet Bankkonto.</span><span class="sxs-lookup"><span data-stu-id="f73e0-143">In the Bank account field, enter or select a value.</span></span>
10. <span data-ttu-id="f73e0-144">Ange eller välj ett värde i fältet Creditor bank account.</span><span class="sxs-lookup"><span data-stu-id="f73e0-144">In the Creditor bank account field, enter or select a value.</span></span>
11. <span data-ttu-id="f73e0-145">Ange det antal betalningar som du förväntar dig att bearbeta för detta medgivande.</span><span class="sxs-lookup"><span data-stu-id="f73e0-145">Enter the number of payments that you expect to process for this mandate.</span></span>
12. <span data-ttu-id="f73e0-146">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="f73e0-146">Click OK.</span></span>
13. <span data-ttu-id="f73e0-147">Klicka på Skriv ut.</span><span class="sxs-lookup"><span data-stu-id="f73e0-147">Click Print.</span></span>
14. <span data-ttu-id="f73e0-148">Klicka på Medgivanderapport.</span><span class="sxs-lookup"><span data-stu-id="f73e0-148">Click Mandate report.</span></span>
15. <span data-ttu-id="f73e0-149">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f73e0-149">Close the page.</span></span>
16. <span data-ttu-id="f73e0-150">Klicka på Redigera.</span><span class="sxs-lookup"><span data-stu-id="f73e0-150">Click Edit.</span></span>
17. <span data-ttu-id="f73e0-151">I fältet Datum för undertecknande, ange ett datum.</span><span class="sxs-lookup"><span data-stu-id="f73e0-151">In the Signature date field, enter a date.</span></span>
18. <span data-ttu-id="f73e0-152">Klicka på Ja.</span><span class="sxs-lookup"><span data-stu-id="f73e0-152">Click Yes.</span></span>
19. <span data-ttu-id="f73e0-153">Ange platsen där medgivandet signerades.</span><span class="sxs-lookup"><span data-stu-id="f73e0-153">Enter the location where the mandate was signed.</span></span>
20. <span data-ttu-id="f73e0-154">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="f73e0-154">Click OK.</span></span>
21. <span data-ttu-id="f73e0-155">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f73e0-155">Close the page.</span></span>

## <a name="create-a-free-text-invoice-with-mandate"></a><span data-ttu-id="f73e0-156">Skapa en fritextfaktura med fullmakt</span><span class="sxs-lookup"><span data-stu-id="f73e0-156">Create a free text invoice with mandate</span></span>
1. <span data-ttu-id="f73e0-157">Gå till Kundreskontra > Fakturor > Alla fritextfakturor.</span><span class="sxs-lookup"><span data-stu-id="f73e0-157">Go to Accounts receivable > Invoices > All free text invoices.</span></span>
2. <span data-ttu-id="f73e0-158">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="f73e0-158">Click New.</span></span>
3. <span data-ttu-id="f73e0-159">Välj kunden som du lagt till medgivande för.</span><span class="sxs-lookup"><span data-stu-id="f73e0-159">Select the customer that you added the mandate to.</span></span>
4. <span data-ttu-id="f73e0-160">Ange eller välj ett värde i fältet Autogiromedgivande-ID.</span><span class="sxs-lookup"><span data-stu-id="f73e0-160">In the Direct debit mandate ID field, enter or select a value.</span></span>

