---
title: Sätta in kundbetalningar
description: Insättning av kundbetalningar.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/18/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransCustPaym, CustTableLookup
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9221101581a6a130889b7c941ca228070a000c56
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "5003166"
---
# <a name="deposit-customer-payments"></a><span data-ttu-id="5f1e4-103">Sätta in kundbetalningar</span><span class="sxs-lookup"><span data-stu-id="5f1e4-103">Deposit customer payments</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="5f1e4-104">Insättning av kundbetalningar.</span><span class="sxs-lookup"><span data-stu-id="5f1e4-104">Deposit customer payments.</span></span> <span data-ttu-id="5f1e4-105">I den här uppgiften används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="5f1e4-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="5f1e4-106">Gå till **navigeringsfönstret > Moduler > Kundreskontra > Betalningar > Betalningsjournal**.</span><span class="sxs-lookup"><span data-stu-id="5f1e4-106">Go to **Navigation pane > Modules > Accounts receivable > Payments > Payment journal**.</span></span>
2. <span data-ttu-id="5f1e4-107">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="5f1e4-107">Select **New**.</span></span>
3. <span data-ttu-id="5f1e4-108">I fältet **Namn**, välj **CustPay** i den nedrullningsbara menyn.</span><span class="sxs-lookup"><span data-stu-id="5f1e4-108">In the **Name** field, select **CustPay** in the drop-down menu.</span></span>
4. <span data-ttu-id="5f1e4-109">Markera **rader**</span><span class="sxs-lookup"><span data-stu-id="5f1e4-109">Select **Lines**.</span></span>
5. <span data-ttu-id="5f1e4-110">Ange kund som du har tagit emot en betalning för i fältet **Konto**.</span><span class="sxs-lookup"><span data-stu-id="5f1e4-110">In the **Account** field, select the customer for whom you are recording the payment.</span></span>
6. <span data-ttu-id="5f1e4-111">Ange betalningens belopp i fältet **Kredit**.</span><span class="sxs-lookup"><span data-stu-id="5f1e4-111">In the **Credit** field, enter the amount of the payment.</span></span> <span data-ttu-id="5f1e4-112">Du kan välja att lämna beloppet mellanslag och har systemet att uppskatta, genom att välja fakturorna som har betalats.</span><span class="sxs-lookup"><span data-stu-id="5f1e4-112">You can choose to leave the amount blank, and have the system calculate it by selecting the invoices which were paid.</span></span>  
7. <span data-ttu-id="5f1e4-113">Skriv ett värde i fältet **Betalningsreferens**.</span><span class="sxs-lookup"><span data-stu-id="5f1e4-113">In the **Payment reference** field, type a value.</span></span> <span data-ttu-id="5f1e4-114">Betalningsreferensen kan vara checknumret för en betalning som du anger.</span><span class="sxs-lookup"><span data-stu-id="5f1e4-114">The payment reference could be the check number for the payment you are entering.</span></span> <span data-ttu-id="5f1e4-115">Betalningsreferensen krävs endast om du markerar för att inkludera betalningen på ett insättningskvitto.</span><span class="sxs-lookup"><span data-stu-id="5f1e4-115">The payment reference is required in order to include the payment on a deposit slip.</span></span>  
8. <span data-ttu-id="5f1e4-116">Välj rutan Använd ett insättningskvitto.</span><span class="sxs-lookup"><span data-stu-id="5f1e4-116">Mark the box Use a deposit slip.</span></span> <span data-ttu-id="5f1e4-117">Om betalningen ska tas med i insättning, ändrar den här inställningen till Ja.</span><span class="sxs-lookup"><span data-stu-id="5f1e4-117">If the payment should be included in the deposit, change this setting to Yes.</span></span>  
9. <span data-ttu-id="5f1e4-118">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="5f1e4-118">Select **New**.</span></span>
10. <span data-ttu-id="5f1e4-119">I fältet **Konto** välj kund för nästa betalning.</span><span class="sxs-lookup"><span data-stu-id="5f1e4-119">In the **Account** field, select the customer for the next payment.</span></span>
11. <span data-ttu-id="5f1e4-120">Ange betalningsbeloppet i fältet **Kredit**.</span><span class="sxs-lookup"><span data-stu-id="5f1e4-120">In the **Credit** field, enter the payment amount.</span></span>
12. <span data-ttu-id="5f1e4-121">Skriv ett värde i fältet **Betalningsreferens**.</span><span class="sxs-lookup"><span data-stu-id="5f1e4-121">In the **Payment reference** field, type a value.</span></span>
13. <span data-ttu-id="5f1e4-122">Välj rutan **Använd ett insättningskvitto**.</span><span class="sxs-lookup"><span data-stu-id="5f1e4-122">Mark the box **Use a deposit slip**.</span></span>
14. <span data-ttu-id="5f1e4-123">Vald **bokföring**</span><span class="sxs-lookup"><span data-stu-id="5f1e4-123">Select **Post**.</span></span> <span data-ttu-id="5f1e4-124">Betalningar måste bokföras, för insättningskvittot kan genereras.</span><span class="sxs-lookup"><span data-stu-id="5f1e4-124">Payments must be posted before the deposit slip can be generated.</span></span> <span data-ttu-id="5f1e4-125">Det garanterar att betalningarna inte ändras, efter insättningskvittot har skapats.</span><span class="sxs-lookup"><span data-stu-id="5f1e4-125">This is to ensure that the payments don't change after the deposit slip is generated.</span></span>  
15. <span data-ttu-id="5f1e4-126">Välj **Funktioner**.</span><span class="sxs-lookup"><span data-stu-id="5f1e4-126">Select **Functions**.</span></span>
16. <span data-ttu-id="5f1e4-127">Välj **Insättningskvitto**.</span><span class="sxs-lookup"><span data-stu-id="5f1e4-127">Select **Deposit slip**.</span></span>
17. <span data-ttu-id="5f1e4-128">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="5f1e4-128">Select **OK**.</span></span> <span data-ttu-id="5f1e4-129">Den första sidan används för att skapa insättningskvittot.</span><span class="sxs-lookup"><span data-stu-id="5f1e4-129">The first page is used to create the deposit slip.</span></span>  
18. <span data-ttu-id="5f1e4-130">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="5f1e4-130">Select **OK**.</span></span> <span data-ttu-id="5f1e4-131">I det andra steget är att skriva ut insättningskvittot, men steget krävs inte.</span><span class="sxs-lookup"><span data-stu-id="5f1e4-131">The second step is to print the deposit slip, but this step is not required.</span></span>  

