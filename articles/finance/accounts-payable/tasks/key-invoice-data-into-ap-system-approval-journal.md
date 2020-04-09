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
ms.openlocfilehash: 788397b5c9a3f42e373f7cdad256c1ee3d058e57
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3143777"
---
# <a name="key-invoice-data-into-accounts-payable-using-an-approval-journal"></a><span data-ttu-id="49f50-103">Mata in fakturadata i leverantörsreskontra genom att använda en godkänd journal</span><span class="sxs-lookup"><span data-stu-id="49f50-103">Key invoice data into accounts payable using an approval journal</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="49f50-104">Det här avsnittet visas hur du använder fakturaregister om du vill skapa fakturor och sedan använda godkännandejournalen för att uppdatera utgiftskontona.</span><span class="sxs-lookup"><span data-stu-id="49f50-104">This topic explains how to use the invoice register to create invoices and then use the approval journal to update the expense accounts.</span></span>

## <a name="create-and-post-and-invoice"></a><span data-ttu-id="49f50-105">Skapa och bokför och fakturera</span><span class="sxs-lookup"><span data-stu-id="49f50-105">Create and post and invoice</span></span>
1. <span data-ttu-id="49f50-106">I navigeringsfönstret går du till **Moduler > Leverantörsreskontra > Fakturor > Fakturaregister**.</span><span class="sxs-lookup"><span data-stu-id="49f50-106">In the navigation pan, go to **Modules > Accounts payable > Invoices > Invoice register**.</span></span>
2. <span data-ttu-id="49f50-107">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="49f50-107">Select **New**.</span></span>
3. <span data-ttu-id="49f50-108">Välj namnet på det fakturaregister som du vill använda.</span><span class="sxs-lookup"><span data-stu-id="49f50-108">Select the name of the invoice register that you want to use.</span></span>
4. <span data-ttu-id="49f50-109">Välj **Rader** om du vill öppna registret och ange utgiftsrader.</span><span class="sxs-lookup"><span data-stu-id="49f50-109">Select **Lines** to open the register and enter expense lines.</span></span>
5. <span data-ttu-id="49f50-110">Välj en leverantör.</span><span class="sxs-lookup"><span data-stu-id="49f50-110">Select a vendor.</span></span> <span data-ttu-id="49f50-111">Ange eller välj `US-104`, till exempel</span><span class="sxs-lookup"><span data-stu-id="49f50-111">For example, enter or select `US-104`.</span></span>
6. <span data-ttu-id="49f50-112">Ange ett värde i fältet **Faktura**.</span><span class="sxs-lookup"><span data-stu-id="49f50-112">In the **Invoice** field, type a value.</span></span>
7. <span data-ttu-id="49f50-113">I fältet **Beskrivning** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="49f50-113">In the **Description** field, type a value.</span></span>
8. <span data-ttu-id="49f50-114">I fältet **Kredit** väljer du ett tal.</span><span class="sxs-lookup"><span data-stu-id="49f50-114">In the **Credit** field, enter a number.</span></span>
9. <span data-ttu-id="49f50-115">I fältet **Godkänd av** väljer du en godkännare i den nedrullningsbara menyn.</span><span class="sxs-lookup"><span data-stu-id="49f50-115">In the **Approved by** field, select an approver from the drop-down menu.</span></span>
10. <span data-ttu-id="49f50-116">Vald **bokföring**</span><span class="sxs-lookup"><span data-stu-id="49f50-116">Select **Post**.</span></span>

## <a name="approve-an-invoice"></a><span data-ttu-id="49f50-117">Godkänn en faktura</span><span class="sxs-lookup"><span data-stu-id="49f50-117">Approve an invoice</span></span>
1. <span data-ttu-id="49f50-118">I navigeringsfönstret går du till **Moduler > Leverantörsreskontra > Fakturor > Fakturagodkännande**.</span><span class="sxs-lookup"><span data-stu-id="49f50-118">In the navigation pane, go to **Modules > Accounts payable > Invoices > Invoice approval**.</span></span>
2. <span data-ttu-id="49f50-119">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="49f50-119">Select **New**.</span></span>
3. <span data-ttu-id="49f50-120">Välj namnet på fakturagodkännandejournalen som du vill använda.</span><span class="sxs-lookup"><span data-stu-id="49f50-120">Select the name of the invoice approval journal that you want to use.</span></span>
4. <span data-ttu-id="49f50-121">Klicka på **Rader** om du vill visa en sida där du kommer att vara i stånd till att välja fakturorna, som du vill godkänna.</span><span class="sxs-lookup"><span data-stu-id="49f50-121">Select **Lines** to display a page where you will be able to select the invoices that you want to approve.</span></span>
5. <span data-ttu-id="49f50-122">Välj **Sök efter verifikationer** om du vill visa alla fakturor som är klara för godkännande.</span><span class="sxs-lookup"><span data-stu-id="49f50-122">Select **Find Vouchers** to display all of the invoices that are ready for approval.</span></span>
6. <span data-ttu-id="49f50-123">Markera fakturan du skapat och klicka sedan på **Välj.**</span><span class="sxs-lookup"><span data-stu-id="49f50-123">Mark the invoice that you created, then click **Select**.</span></span> <span data-ttu-id="49f50-124">Verifikationerna, som du valde ovan, flyttas till listan när du har markerat dem.</span><span class="sxs-lookup"><span data-stu-id="49f50-124">The vouchers that you selected above are moved to this list after you select them.</span></span>  
7. <span data-ttu-id="49f50-125">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="49f50-125">Select **OK**.</span></span>
8. <span data-ttu-id="49f50-126">Välj **kontonummerfältet** om du vill lägga till ett utgiftskonto i fakturan.</span><span class="sxs-lookup"><span data-stu-id="49f50-126">Select the **account number** field to add an expense account to the invoice.</span></span>
9. <span data-ttu-id="49f50-127">Ange ett kontonummer och gå till nästa fält.</span><span class="sxs-lookup"><span data-stu-id="49f50-127">Enter an account number and tab off of the field.</span></span> <span data-ttu-id="49f50-128">Ange exempelvis `600120`.</span><span class="sxs-lookup"><span data-stu-id="49f50-128">For example, enter `600120`.</span></span>
10. <span data-ttu-id="49f50-129">Vald **bokföring**</span><span class="sxs-lookup"><span data-stu-id="49f50-129">Select **Post**.</span></span>
11. <span data-ttu-id="49f50-130">Välj **Verifikation** om du vill visa poster som bokfördes.</span><span class="sxs-lookup"><span data-stu-id="49f50-130">Select **Voucher** to view the entries that were posted.</span></span> <span data-ttu-id="49f50-131">Kontot för godkännande av pågående fakturor motbokas och ersätts med det verkliga utgiftskontot.</span><span class="sxs-lookup"><span data-stu-id="49f50-131">The Invoice Pending Approval account is reversed and replaced with the actual expense account.</span></span>  

