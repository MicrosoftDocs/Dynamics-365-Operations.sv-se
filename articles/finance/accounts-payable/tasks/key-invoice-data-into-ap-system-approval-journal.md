---
title: Mata in fakturadata i leverantörsreskontra genom att använda en godkänd journal
description: Det här avsnittet visas hur du använder fakturaregister om du vill skapa fakturor och sedan använda godkännandejournalen för att uppdatera utgiftskontona.
author: abruer
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransInvoiceRegister, HcmWorkerLookUp, LedgerJournalTransApprove, LedgerJournalTransApproveFetchVouchers, LedgerTransVoucher
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fb690769a33f88e63ab8f54cec69a5e927fd324c
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2180030"
---
# <a name="key-invoice-data-into-accounts-payable-using-an-approval-journal"></a><span data-ttu-id="43b0b-103">Mata in fakturadata i leverantörsreskontra genom att använda en godkänd journal</span><span class="sxs-lookup"><span data-stu-id="43b0b-103">Key invoice data into accounts payable using an approval journal</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="43b0b-104">Det här avsnittet visas hur du använder fakturaregister om du vill skapa fakturor och sedan använda godkännandejournalen för att uppdatera utgiftskontona.</span><span class="sxs-lookup"><span data-stu-id="43b0b-104">This topic explains how to use the invoice register to create invoices and then use the approval journal to update the expense accounts.</span></span>

## <a name="create-and-post-and-invoice"></a><span data-ttu-id="43b0b-105">Skapa och bokför och fakturera</span><span class="sxs-lookup"><span data-stu-id="43b0b-105">Create and post and invoice</span></span>
1. <span data-ttu-id="43b0b-106">I navigeringsfönstret går du till **Moduler > Leverantörsreskontra > Fakturor > Fakturaregister**.</span><span class="sxs-lookup"><span data-stu-id="43b0b-106">In the navigation pan, go to **Modules > Accounts payable > Invoices > Invoice register**.</span></span>
2. <span data-ttu-id="43b0b-107">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="43b0b-107">Select **New**.</span></span>
3. <span data-ttu-id="43b0b-108">Välj namnet på det fakturaregister som du vill använda.</span><span class="sxs-lookup"><span data-stu-id="43b0b-108">Select the name of the invoice register that you want to use.</span></span>
4. <span data-ttu-id="43b0b-109">Välj **Rader** om du vill öppna registret och ange utgiftsrader.</span><span class="sxs-lookup"><span data-stu-id="43b0b-109">Select **Lines** to open the register and enter expense lines.</span></span>
5. <span data-ttu-id="43b0b-110">Välj en leverantör.</span><span class="sxs-lookup"><span data-stu-id="43b0b-110">Select a vendor.</span></span> <span data-ttu-id="43b0b-111">Ange eller välj `US-104`, till exempel</span><span class="sxs-lookup"><span data-stu-id="43b0b-111">For example, enter or select `US-104`.</span></span>
6. <span data-ttu-id="43b0b-112">Ange ett värde i fältet **Faktura**.</span><span class="sxs-lookup"><span data-stu-id="43b0b-112">In the **Invoice** field, type a value.</span></span>
7. <span data-ttu-id="43b0b-113">I fältet **Beskrivning** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="43b0b-113">In the **Description** field, type a value.</span></span>
8. <span data-ttu-id="43b0b-114">I fältet **Kredit** väljer du ett tal.</span><span class="sxs-lookup"><span data-stu-id="43b0b-114">In the **Credit** field, enter a number.</span></span>
9. <span data-ttu-id="43b0b-115">I fältet **Godkänd av** väljer du en godkännare i den nedrullningsbara menyn.</span><span class="sxs-lookup"><span data-stu-id="43b0b-115">In the **Approved by** field, select an approver from the drop-down menu.</span></span>
10. <span data-ttu-id="43b0b-116">Vald **bokföring**</span><span class="sxs-lookup"><span data-stu-id="43b0b-116">Select **Post**.</span></span>

## <a name="approve-an-invoice"></a><span data-ttu-id="43b0b-117">Godkänn en faktura</span><span class="sxs-lookup"><span data-stu-id="43b0b-117">Approve an invoice</span></span>
1. <span data-ttu-id="43b0b-118">I navigeringsfönstret går du till **Moduler > Leverantörsreskontra > Fakturor > Fakturagodkännande**.</span><span class="sxs-lookup"><span data-stu-id="43b0b-118">In the navigation pane, go to **Modules > Accounts payable > Invoices > Invoice approval**.</span></span>
2. <span data-ttu-id="43b0b-119">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="43b0b-119">Select **New**.</span></span>
3. <span data-ttu-id="43b0b-120">Välj namnet på fakturagodkännandejournalen som du vill använda.</span><span class="sxs-lookup"><span data-stu-id="43b0b-120">Select the name of the invoice approval journal that you want to use.</span></span>
4. <span data-ttu-id="43b0b-121">Klicka på **Rader** om du vill visa en sida där du kommer att vara i stånd till att välja fakturorna, som du vill godkänna.</span><span class="sxs-lookup"><span data-stu-id="43b0b-121">Select **Lines** to display a page where you will be able to select the invoices that you want to approve.</span></span>
5. <span data-ttu-id="43b0b-122">Välj **Sök efter verifikationer** om du vill visa alla fakturor som är klara för godkännande.</span><span class="sxs-lookup"><span data-stu-id="43b0b-122">Select **Find Vouchers** to display all of the invoices that are ready for approval.</span></span>
6. <span data-ttu-id="43b0b-123">Markera fakturan du skapat och klicka sedan på **Välj.**</span><span class="sxs-lookup"><span data-stu-id="43b0b-123">Mark the invoice that you created, then click **Select**.</span></span> <span data-ttu-id="43b0b-124">Verifikationerna, som du valde ovan, flyttas till listan när du har markerat dem.</span><span class="sxs-lookup"><span data-stu-id="43b0b-124">The vouchers that you selected above are moved to this list after you select them.</span></span>  
7. <span data-ttu-id="43b0b-125">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="43b0b-125">Select **OK**.</span></span>
8. <span data-ttu-id="43b0b-126">Välj **kontonummerfältet** om du vill lägga till ett utgiftskonto i fakturan.</span><span class="sxs-lookup"><span data-stu-id="43b0b-126">Select the **account number** field to add an expense account to the invoice.</span></span>
9. <span data-ttu-id="43b0b-127">Ange ett kontonummer och gå till nästa fält.</span><span class="sxs-lookup"><span data-stu-id="43b0b-127">Enter an account number and tab off of the field.</span></span> <span data-ttu-id="43b0b-128">Ange exempelvis `600120`.</span><span class="sxs-lookup"><span data-stu-id="43b0b-128">For example, enter `600120`.</span></span>
10. <span data-ttu-id="43b0b-129">Vald **bokföring**</span><span class="sxs-lookup"><span data-stu-id="43b0b-129">Select **Post**.</span></span>
11. <span data-ttu-id="43b0b-130">Välj **Verifikation** om du vill visa poster som bokfördes.</span><span class="sxs-lookup"><span data-stu-id="43b0b-130">Select **Voucher** to view the entries that were posted.</span></span> <span data-ttu-id="43b0b-131">Kontot för godkännande av pågående fakturor motbokas och ersätts med det verkliga utgiftskontot.</span><span class="sxs-lookup"><span data-stu-id="43b0b-131">The Invoice Pending Approval account is reversed and replaced with the actual expense account.</span></span>  

