--- 
title: "Huvudfakturadata i AP-system med hjälp av godkännandejournal"
description: "Den här uppgifthandboken visas hur du använder fakturaregister om du vill skapa fakturor och sedan använda godkännandejournalen för att uppdatera utgiftskontona."
author: abruer
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalTable, LedgerJournalTransInvoiceRegister, HcmWorkerLookUp, LedgerJournalTransApprove, LedgerJournalTransApproveFetchVouchers, LedgerTransVoucher
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 048eda77064b6aa3f666e998a8e551d2f7adc385
ms.contentlocale: sv-se
ms.lasthandoff: 09/14/2018

---
# <a name="key-invoice-data-into-ap-system-using-approval-journal"></a><span data-ttu-id="f64ae-103">Huvudfakturadata i AP-system med hjälp av godkännandejournal</span><span class="sxs-lookup"><span data-stu-id="f64ae-103">Key invoice data into AP system using approval journal</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f64ae-104">Den här uppgifthandboken visas hur du använder fakturaregister om du vill skapa fakturor och sedan använda godkännandejournalen för att uppdatera utgiftskontona.</span><span class="sxs-lookup"><span data-stu-id="f64ae-104">This task guide will show you how to use the invoice register to create invoices and then use the approval journal to update the expense accounts.</span></span>


## <a name="create-and-post-and-invoice"></a><span data-ttu-id="f64ae-105">Skapa och bokför och fakturera</span><span class="sxs-lookup"><span data-stu-id="f64ae-105">Create and post and invoice</span></span>
1. <span data-ttu-id="f64ae-106">Gå till Leverantörsreskontra > Fakturor > Fakturaregister.</span><span class="sxs-lookup"><span data-stu-id="f64ae-106">Go to Accounts payable > Invoices > Invoice register.</span></span>
2. <span data-ttu-id="f64ae-107">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="f64ae-107">Click New.</span></span>
3. <span data-ttu-id="f64ae-108">Välj namnet på det fakturaregister som du vill använda.</span><span class="sxs-lookup"><span data-stu-id="f64ae-108">Select the name of the invoice register that you want to use.</span></span>
4. <span data-ttu-id="f64ae-109">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="f64ae-109">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="f64ae-110">Klicka på på Rader om du vill öppna registret och ange utgiftsrader.</span><span class="sxs-lookup"><span data-stu-id="f64ae-110">Click on Lines to open the register and enter expense lines.</span></span>
6. <span data-ttu-id="f64ae-111">Välj en leverantör.</span><span class="sxs-lookup"><span data-stu-id="f64ae-111">Select a vendor.</span></span> <span data-ttu-id="f64ae-112">Ange eller välj US-104, till exempel</span><span class="sxs-lookup"><span data-stu-id="f64ae-112">For example, enter or select US-104</span></span>
7. <span data-ttu-id="f64ae-113">Ange ett värde i fältet Faktura.</span><span class="sxs-lookup"><span data-stu-id="f64ae-113">In the Invoice field, type a value.</span></span>
8. <span data-ttu-id="f64ae-114">Skriv ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="f64ae-114">In the Description field, type a value.</span></span>
9. <span data-ttu-id="f64ae-115">Välj ett tal i fältet Kredit.</span><span class="sxs-lookup"><span data-stu-id="f64ae-115">In the Credit field, enter a number.</span></span>
10. <span data-ttu-id="f64ae-116">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Godkänt av.</span><span class="sxs-lookup"><span data-stu-id="f64ae-116">In the Approved by field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="f64ae-117">Välj en godkännare och klicka sedan på Välj om du vill välja den godkännaren.</span><span class="sxs-lookup"><span data-stu-id="f64ae-117">Highlight an approver and click Select to select that approver.</span></span>
12. <span data-ttu-id="f64ae-118">Klicka på Bokför.</span><span class="sxs-lookup"><span data-stu-id="f64ae-118">Click Post.</span></span>
13. <span data-ttu-id="f64ae-119">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f64ae-119">Close the page.</span></span>
14. <span data-ttu-id="f64ae-120">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="f64ae-120">Close the page.</span></span>

## <a name="approve-an-invoice"></a><span data-ttu-id="f64ae-121">Godkänn en faktura</span><span class="sxs-lookup"><span data-stu-id="f64ae-121">Approve an invoice</span></span>
1. <span data-ttu-id="f64ae-122">Gå till Leverantörsreskontra > Fakturor > Fakturagodkännande.</span><span class="sxs-lookup"><span data-stu-id="f64ae-122">Go to Accounts payable > Invoices > Invoice approval.</span></span>
2. <span data-ttu-id="f64ae-123">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="f64ae-123">Click New.</span></span>
3. <span data-ttu-id="f64ae-124">Välj namnet på fakturagodkännandejournalen som du vill använda.</span><span class="sxs-lookup"><span data-stu-id="f64ae-124">Select the name of the invoice approval journal that you want to use.</span></span>
4. <span data-ttu-id="f64ae-125">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="f64ae-125">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="f64ae-126">Klicka på Rader om du vill visa en sida där du kommer att vara i stånd till att välja fakturorna, som du vill godkänna.</span><span class="sxs-lookup"><span data-stu-id="f64ae-126">Click lines to display a page where you will be able to select the invoices that you want to approve.</span></span>
6. <span data-ttu-id="f64ae-127">Välj Sök efter verifikationer om du vill visa alla fakturor som är klara för godkännande.</span><span class="sxs-lookup"><span data-stu-id="f64ae-127">Select Find Vouchers to display all of the invoices that are ready for approval.</span></span>
7. <span data-ttu-id="f64ae-128">Välj den faktura som du själv har skapat.</span><span class="sxs-lookup"><span data-stu-id="f64ae-128">Mark the invoice that you created.</span></span>
8. <span data-ttu-id="f64ae-129">Klicka på Välj.</span><span class="sxs-lookup"><span data-stu-id="f64ae-129">Click Select.</span></span>
    * <span data-ttu-id="f64ae-130">Verifikationerna, som du valde ovan, flyttas till listan när du har markerat dem.</span><span class="sxs-lookup"><span data-stu-id="f64ae-130">The vouchers that you selected above are moved to this list after you select them.</span></span>  
9. <span data-ttu-id="f64ae-131">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="f64ae-131">Click OK.</span></span>
10. <span data-ttu-id="f64ae-132">Klicka på kontonummerfältet om du vill lägga till ett utgiftskonto i fakturan.</span><span class="sxs-lookup"><span data-stu-id="f64ae-132">Click on the account number field to add an expense account to the invoice.</span></span>
11. <span data-ttu-id="f64ae-133">Ange ett kontonummer och gå till nästa fält.</span><span class="sxs-lookup"><span data-stu-id="f64ae-133">Enter an account number and tab off of the field.</span></span> <span data-ttu-id="f64ae-134">Ange exempelvis 600120.</span><span class="sxs-lookup"><span data-stu-id="f64ae-134">For example, enter 600120.</span></span>
12. <span data-ttu-id="f64ae-135">Klicka på Bokför.</span><span class="sxs-lookup"><span data-stu-id="f64ae-135">Click Post.</span></span>
13. <span data-ttu-id="f64ae-136">Klicka på verifikationen om du vill visa poster som bokfördes.</span><span class="sxs-lookup"><span data-stu-id="f64ae-136">Click Voucher to view the entries that were posted.</span></span>
    * <span data-ttu-id="f64ae-137">Kontot för godkännande av pågående fakturor motbokas och ersätts med det verkliga utgiftskontot.</span><span class="sxs-lookup"><span data-stu-id="f64ae-137">The Invoice Pending Approval account is reversed and replaced with the actual expense account.</span></span>  


