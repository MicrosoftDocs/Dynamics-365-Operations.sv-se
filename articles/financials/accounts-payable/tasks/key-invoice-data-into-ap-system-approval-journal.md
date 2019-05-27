---
title: Huvudfakturadata i AP-system med hjälp av godkännandejournal
description: Den här uppgifthandboken visas hur du använder fakturaregister om du vill skapa fakturor och sedan använda godkännandejournalen för att uppdatera utgiftskontona.
author: abruer
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransInvoiceRegister, HcmWorkerLookUp, LedgerJournalTransApprove, LedgerJournalTransApproveFetchVouchers, LedgerTransVoucher
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 048eda77064b6aa3f666e998a8e551d2f7adc385
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1550384"
---
# <a name="key-invoice-data-into-ap-system-using-approval-journal"></a><span data-ttu-id="ec235-103">Huvudfakturadata i AP-system med hjälp av godkännandejournal</span><span class="sxs-lookup"><span data-stu-id="ec235-103">Key invoice data into AP system using approval journal</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ec235-104">Den här uppgifthandboken visas hur du använder fakturaregister om du vill skapa fakturor och sedan använda godkännandejournalen för att uppdatera utgiftskontona.</span><span class="sxs-lookup"><span data-stu-id="ec235-104">This task guide will show you how to use the invoice register to create invoices and then use the approval journal to update the expense accounts.</span></span>


## <a name="create-and-post-and-invoice"></a><span data-ttu-id="ec235-105">Skapa och bokför och fakturera</span><span class="sxs-lookup"><span data-stu-id="ec235-105">Create and post and invoice</span></span>
1. <span data-ttu-id="ec235-106">Gå till Leverantörsreskontra > Fakturor > Fakturaregister.</span><span class="sxs-lookup"><span data-stu-id="ec235-106">Go to Accounts payable > Invoices > Invoice register.</span></span>
2. <span data-ttu-id="ec235-107">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="ec235-107">Click New.</span></span>
3. <span data-ttu-id="ec235-108">Välj namnet på det fakturaregister som du vill använda.</span><span class="sxs-lookup"><span data-stu-id="ec235-108">Select the name of the invoice register that you want to use.</span></span>
4. <span data-ttu-id="ec235-109">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="ec235-109">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="ec235-110">Klicka på på Rader om du vill öppna registret och ange utgiftsrader.</span><span class="sxs-lookup"><span data-stu-id="ec235-110">Click on Lines to open the register and enter expense lines.</span></span>
6. <span data-ttu-id="ec235-111">Välj en leverantör.</span><span class="sxs-lookup"><span data-stu-id="ec235-111">Select a vendor.</span></span> <span data-ttu-id="ec235-112">Ange eller välj US-104, till exempel</span><span class="sxs-lookup"><span data-stu-id="ec235-112">For example, enter or select US-104</span></span>
7. <span data-ttu-id="ec235-113">Ange ett värde i fältet Faktura.</span><span class="sxs-lookup"><span data-stu-id="ec235-113">In the Invoice field, type a value.</span></span>
8. <span data-ttu-id="ec235-114">Skriv ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="ec235-114">In the Description field, type a value.</span></span>
9. <span data-ttu-id="ec235-115">Välj ett tal i fältet Kredit.</span><span class="sxs-lookup"><span data-stu-id="ec235-115">In the Credit field, enter a number.</span></span>
10. <span data-ttu-id="ec235-116">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Godkänt av.</span><span class="sxs-lookup"><span data-stu-id="ec235-116">In the Approved by field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="ec235-117">Välj en godkännare och klicka sedan på Välj om du vill välja den godkännaren.</span><span class="sxs-lookup"><span data-stu-id="ec235-117">Highlight an approver and click Select to select that approver.</span></span>
12. <span data-ttu-id="ec235-118">Klicka på Bokför.</span><span class="sxs-lookup"><span data-stu-id="ec235-118">Click Post.</span></span>
13. <span data-ttu-id="ec235-119">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="ec235-119">Close the page.</span></span>
14. <span data-ttu-id="ec235-120">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="ec235-120">Close the page.</span></span>

## <a name="approve-an-invoice"></a><span data-ttu-id="ec235-121">Godkänn en faktura</span><span class="sxs-lookup"><span data-stu-id="ec235-121">Approve an invoice</span></span>
1. <span data-ttu-id="ec235-122">Gå till Leverantörsreskontra > Fakturor > Fakturagodkännande.</span><span class="sxs-lookup"><span data-stu-id="ec235-122">Go to Accounts payable > Invoices > Invoice approval.</span></span>
2. <span data-ttu-id="ec235-123">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="ec235-123">Click New.</span></span>
3. <span data-ttu-id="ec235-124">Välj namnet på fakturagodkännandejournalen som du vill använda.</span><span class="sxs-lookup"><span data-stu-id="ec235-124">Select the name of the invoice approval journal that you want to use.</span></span>
4. <span data-ttu-id="ec235-125">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="ec235-125">In the list, click the link in the selected row.</span></span>
5. <span data-ttu-id="ec235-126">Klicka på Rader om du vill visa en sida där du kommer att vara i stånd till att välja fakturorna, som du vill godkänna.</span><span class="sxs-lookup"><span data-stu-id="ec235-126">Click lines to display a page where you will be able to select the invoices that you want to approve.</span></span>
6. <span data-ttu-id="ec235-127">Välj Sök efter verifikationer om du vill visa alla fakturor som är klara för godkännande.</span><span class="sxs-lookup"><span data-stu-id="ec235-127">Select Find Vouchers to display all of the invoices that are ready for approval.</span></span>
7. <span data-ttu-id="ec235-128">Välj den faktura som du själv har skapat.</span><span class="sxs-lookup"><span data-stu-id="ec235-128">Mark the invoice that you created.</span></span>
8. <span data-ttu-id="ec235-129">Klicka på Välj.</span><span class="sxs-lookup"><span data-stu-id="ec235-129">Click Select.</span></span>
    * <span data-ttu-id="ec235-130">Verifikationerna, som du valde ovan, flyttas till listan när du har markerat dem.</span><span class="sxs-lookup"><span data-stu-id="ec235-130">The vouchers that you selected above are moved to this list after you select them.</span></span>  
9. <span data-ttu-id="ec235-131">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="ec235-131">Click OK.</span></span>
10. <span data-ttu-id="ec235-132">Klicka på kontonummerfältet om du vill lägga till ett utgiftskonto i fakturan.</span><span class="sxs-lookup"><span data-stu-id="ec235-132">Click on the account number field to add an expense account to the invoice.</span></span>
11. <span data-ttu-id="ec235-133">Ange ett kontonummer och gå till nästa fält.</span><span class="sxs-lookup"><span data-stu-id="ec235-133">Enter an account number and tab off of the field.</span></span> <span data-ttu-id="ec235-134">Ange exempelvis 600120.</span><span class="sxs-lookup"><span data-stu-id="ec235-134">For example, enter 600120.</span></span>
12. <span data-ttu-id="ec235-135">Klicka på Bokför.</span><span class="sxs-lookup"><span data-stu-id="ec235-135">Click Post.</span></span>
13. <span data-ttu-id="ec235-136">Klicka på verifikationen om du vill visa poster som bokfördes.</span><span class="sxs-lookup"><span data-stu-id="ec235-136">Click Voucher to view the entries that were posted.</span></span>
    * <span data-ttu-id="ec235-137">Kontot för godkännande av pågående fakturor motbokas och ersätts med det verkliga utgiftskontot.</span><span class="sxs-lookup"><span data-stu-id="ec235-137">The Invoice Pending Approval account is reversed and replaced with the actual expense account.</span></span>  

