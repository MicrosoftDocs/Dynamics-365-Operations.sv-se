---
title: "Ställa in och bearbeta återkommande fakturor"
description: "Det här avsnittet innehåller en beskrivning av hur du ställer in och bearbetar återkommande fakturor. Du kan använda återkommande fakturor om du måste fakturera kunder samma belopp regelbundet."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustInvoiceTemplate
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 14011
ms.assetid: 9cc37003-adf1-413d-b2b2-2badcf512e3b
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 5c5fbe1791161b8d06cd1539b1717ba8690a8e05
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="set-up-and-process-recurring-invoices"></a><span data-ttu-id="6a1a4-104">Ställa in och bearbeta återkommande fakturor</span><span class="sxs-lookup"><span data-stu-id="6a1a4-104">Set up and process recurring invoices</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="6a1a4-105">Det här avsnittet innehåller en beskrivning av hur du ställer in och bearbetar återkommande fakturor.</span><span class="sxs-lookup"><span data-stu-id="6a1a4-105">This article explains how to set up and process recurring invoices.</span></span> <span data-ttu-id="6a1a4-106">Du kan använda återkommande fakturor om du måste fakturera kunder samma belopp regelbundet.</span><span class="sxs-lookup"><span data-stu-id="6a1a4-106">You can use recurring invoices if you must invoice customers for the same amount on a regular basis.</span></span>

<a name="create-a-recurring-free-text-invoice-template"></a><span data-ttu-id="6a1a4-107">Skapa en fritextmall för återkommande fakturor</span><span class="sxs-lookup"><span data-stu-id="6a1a4-107">Create a recurring free text invoice template</span></span>
---------------------------------------------

<span data-ttu-id="6a1a4-108">Om du regelbundet vill fakturera kunder för samma tjänster måste du definiera en fritextfakturamall som kan återanvändas för att skapa fakturorna.</span><span class="sxs-lookup"><span data-stu-id="6a1a4-108">To invoice customers for the same services on a regular basis, you must define a free text invoice template that can be reused to create the invoices.</span></span> <span data-ttu-id="6a1a4-109">Mallen innehåller följande information:</span><span class="sxs-lookup"><span data-stu-id="6a1a4-109">This template contains the following information:</span></span>

-   <span data-ttu-id="6a1a4-110">Huvudinformation som momsgrupp, betalningsvillkor och betalningsmetod.</span><span class="sxs-lookup"><span data-stu-id="6a1a4-110">Header information, such as tax groups, terms of payment, and the method of payment</span></span>
-   <span data-ttu-id="6a1a4-111">Radinformation som beskrivning, intäktskonton, enhetspris och fakturabelopp.</span><span class="sxs-lookup"><span data-stu-id="6a1a4-111">Line information, such as the service description, revenue accounts, unit price, and invoice amount</span></span>
-   <span data-ttu-id="6a1a4-112">Avgifter för leverans eller hantering.</span><span class="sxs-lookup"><span data-stu-id="6a1a4-112">Charges for shipping or handling</span></span>
-   <span data-ttu-id="6a1a4-113">Redovisningsfördelningar tillsammans med information om ekonomisk dimension, exempelvis kostnadsställen och affärsenheter.</span><span class="sxs-lookup"><span data-stu-id="6a1a4-113">Accounting distributions together with financial dimension information, such as cost centers and business units</span></span>

<span data-ttu-id="6a1a4-114">I praktiken skapar du en faktura och sparar den som en mall.</span><span class="sxs-lookup"><span data-stu-id="6a1a4-114">In effect, you're creating an entire invoice and saving it as a template.</span></span> <span data-ttu-id="6a1a4-115">Du kan ställa in mallar på sidan **Återkommande fakturor**.</span><span class="sxs-lookup"><span data-stu-id="6a1a4-115">You can set up the templates using the **Recurring invoices** page.</span></span>

## <a name="assign-a-free-text-invoice-template-to-a-customer-and-enter-recurrence-details"></a><span data-ttu-id="6a1a4-116">Koppla en fritextfakturamall till en kund och ange återkommande detaljer</span><span class="sxs-lookup"><span data-stu-id="6a1a4-116">Assign a free text invoice template to a customer and enter recurrence details</span></span>
<span data-ttu-id="6a1a4-117">När mallen har skapats, måste du koppla mallen till de kunderna som du vill fakturera.</span><span class="sxs-lookup"><span data-stu-id="6a1a4-117">After the template is created, you must assign the template to the customers that you want to invoice.</span></span> <span data-ttu-id="6a1a4-118">Dessutom måste du ange när och hur ofta fakturan ska användas.</span><span class="sxs-lookup"><span data-stu-id="6a1a4-118">Additionally, you must specify when and how often the invoice will be used.</span></span> <span data-ttu-id="6a1a4-119">Du kan koppla mallar på fliken **Faktura** på sidan **Kunder**.</span><span class="sxs-lookup"><span data-stu-id="6a1a4-119">You can assign the templates on the **Invoice** tab of the **Customers** page.</span></span> <span data-ttu-id="6a1a4-120">Lägg till mallen i listan och uppdatera följande information:</span><span class="sxs-lookup"><span data-stu-id="6a1a4-120">Add the template to the list, and update the following information:</span></span>

-   <span data-ttu-id="6a1a4-121">Startdatum och eventuellt slutdatum för återkommande faktureringen.</span><span class="sxs-lookup"><span data-stu-id="6a1a4-121">The start date and, optionally, the end date for the recurring billing</span></span>
-   <span data-ttu-id="6a1a4-122">Hur ofta den återkommande faktureringen ska göras (exempelvis varje dag eller en gång i månaden).</span><span class="sxs-lookup"><span data-stu-id="6a1a4-122">The frequency of the recurring billing (for example, every day or once a month)</span></span>
-   <span data-ttu-id="6a1a4-123">Det maximala faktureringsbeloppet (om denna information krävs).</span><span class="sxs-lookup"><span data-stu-id="6a1a4-123">The maximum billing amount (if this information is required)</span></span>

<span data-ttu-id="6a1a4-124">En kund kan ha flera mallar med olika frekvenser.</span><span class="sxs-lookup"><span data-stu-id="6a1a4-124">A customer can have multiple templates that have different frequencies.</span></span>

## <a name="generate-the-recurring-invoices"></a><span data-ttu-id="6a1a4-125">Generera de återkommande fakturorna</span><span class="sxs-lookup"><span data-stu-id="6a1a4-125">Generate the recurring invoices</span></span>
<span data-ttu-id="6a1a4-126">På sidan **Återkommande fakturor** finns en uppgift som bearbetar återkommande fakturamallar.</span><span class="sxs-lookup"><span data-stu-id="6a1a4-126">On the **Recurring invoices** page, there is a task that processes recurring invoice templates.</span></span> <span data-ttu-id="6a1a4-127">Du anger fakturadatumet och vilken mall fakturorna ska genereras från.</span><span class="sxs-lookup"><span data-stu-id="6a1a4-127">You specify the invoice date and the template to generate the invoices from.</span></span> <span data-ttu-id="6a1a4-128">Fakturor skapas och kopplas till ett återkommande-id-nummer för varje grupp av fakturor som bearbetas.</span><span class="sxs-lookup"><span data-stu-id="6a1a4-128">Invoices will be generated and assigned a single recurrence ID number for each group of invoices that is processed.</span></span>
<span data-ttu-id="6a1a4-129">Bokföra återkommande fritextfakturor</span><span class="sxs-lookup"><span data-stu-id="6a1a4-129">Post recurring free text invoices</span></span>
---------------------------------

<span data-ttu-id="6a1a4-130">När återkommande fakturor har skapats, visas återkommande-id:na för fakturorna i en bokföringsuppgift på sidan **Återkommande fakturor**.</span><span class="sxs-lookup"><span data-stu-id="6a1a4-130">After recurring invoices are generated, the invoice recurrence IDs appear in a posting task on the **Recurring invoices** page.</span></span> <span data-ttu-id="6a1a4-131">Du kan visa alla av fakturor för ett återkommande-id genom att klicka på länken.</span><span class="sxs-lookup"><span data-stu-id="6a1a4-131">You can view all of the invoices for a recurrence ID by clicking the link.</span></span> <span data-ttu-id="6a1a4-132">När du granskar fakturorna för återkommande-id:t kan du ta bort enskilda fakturor.</span><span class="sxs-lookup"><span data-stu-id="6a1a4-132">During your review of the invoices for the recurrence ID, you can delete individual invoices.</span></span> <span data-ttu-id="6a1a4-133">Kundens inställningar för återkommande fakturor återställs för mallen, så att den kan genereras igen senare.</span><span class="sxs-lookup"><span data-stu-id="6a1a4-133">The customer's recurrence settings will be reset for that template, so that it can be regenerated later.</span></span> <span data-ttu-id="6a1a4-134">Du kan bokföra en, många eller alla fakturor för ett återkommande-id.</span><span class="sxs-lookup"><span data-stu-id="6a1a4-134">You can post one, many, or all of the invoices for a recurrence ID.</span></span> <span data-ttu-id="6a1a4-135">Om arbetsflöden är aktiva, måste du klicka på **Skicka** innan du kan bokföra fakturor.</span><span class="sxs-lookup"><span data-stu-id="6a1a4-135">If workflows are enabled, you must click **Submit** before you can post the invoices.</span></span>
<span data-ttu-id="6a1a4-136">Skriva ut återkommande fritextfakturor</span><span class="sxs-lookup"><span data-stu-id="6a1a4-136">Print recurring free text invoices</span></span>
----------------------------------

<span data-ttu-id="6a1a4-137">När återkommande fakturor bokförs kan du skriva ut fakturorna från sidan med en lista över fritextfakturor.</span><span class="sxs-lookup"><span data-stu-id="6a1a4-137">After recurring invoices are posted, you can print the invoices from the free text invoice list page.</span></span> <span data-ttu-id="6a1a4-138">Du kan skriva ut de fakturor som har valts, eller välja ett intervall med fakturor som ska skrivas ut.</span><span class="sxs-lookup"><span data-stu-id="6a1a4-138">You can print the invoices that are selected, or you can select a range of invoices to print.</span></span>




