---
title: Sätta in kundbetalningar
description: Insättning av kundbetalningar.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransCustPaym, CustTableLookup
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f58cebce20e8516dc918e0bad1e020ffd7f791ee
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "313392"
---
# <a name="deposit-customer-payments"></a><span data-ttu-id="facca-103">Sätta in kundbetalningar</span><span class="sxs-lookup"><span data-stu-id="facca-103">Deposit customer payments</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="facca-104">Insättning av kundbetalningar.</span><span class="sxs-lookup"><span data-stu-id="facca-104">Deposit customer payments.</span></span> <span data-ttu-id="facca-105">I den här uppgiften används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="facca-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="facca-106">Gå till Kundreskontra > Betalningar > Betalningsjournal.</span><span class="sxs-lookup"><span data-stu-id="facca-106">Go to Accounts receivable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="facca-107">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="facca-107">Click New.</span></span>
3. <span data-ttu-id="facca-108">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="facca-108">In the Name field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="facca-109">Välj betalningsjournal.</span><span class="sxs-lookup"><span data-stu-id="facca-109">Select the payment journal.</span></span> 
5. <span data-ttu-id="facca-110">Klicka på Rader.</span><span class="sxs-lookup"><span data-stu-id="facca-110">Click Lines.</span></span>
6. <span data-ttu-id="facca-111">Ange kund som du har tagit emot en betalning för i fältet Konto.</span><span class="sxs-lookup"><span data-stu-id="facca-111">In the Account field, select the Customer for whom you are recording the payment.</span></span>
7. <span data-ttu-id="facca-112">Ange beloppet i fältet Kredit.</span><span class="sxs-lookup"><span data-stu-id="facca-112">In the Credit field, enter the amount of the payment.</span></span>
    * <span data-ttu-id="facca-113">Du kan välja att lämna beloppet mellanslag och har systemet att uppskatta, genom att välja fakturorna som har betalats.</span><span class="sxs-lookup"><span data-stu-id="facca-113">You can choose to leave the amount blank, and have the system calculate it by selecting the invoices which were paid.</span></span>  
8. <span data-ttu-id="facca-114">Skriv ett värde i fältet Betalningsreferens.</span><span class="sxs-lookup"><span data-stu-id="facca-114">In the Payment reference field, type a value.</span></span>
    * <span data-ttu-id="facca-115">Betalningsreferensen kan vara checknumret för en betalning som du anger.</span><span class="sxs-lookup"><span data-stu-id="facca-115">The payment reference could be the check number for the payment you are entering.</span></span> <span data-ttu-id="facca-116">Betalningsreferensen krävs endast om du markerar för att inkludera betalningen på ett insättningskvitto.</span><span class="sxs-lookup"><span data-stu-id="facca-116">The payment reference is required in order to include the payment on a deposit slip.</span></span>  
9. <span data-ttu-id="facca-117">Välj rutan Använd ett insättningskvitto.</span><span class="sxs-lookup"><span data-stu-id="facca-117">Mark the box Use a deposit slip.</span></span>
    * <span data-ttu-id="facca-118">Om betalningen ska tas med i insättning, ändrar den här inställningen till Ja.</span><span class="sxs-lookup"><span data-stu-id="facca-118">If the payment should be included in the deposit, change this setting to Yes.</span></span>  
10. <span data-ttu-id="facca-119">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="facca-119">Click New.</span></span>
11. <span data-ttu-id="facca-120">Välj kund för nästa betalning i fältet Konto.</span><span class="sxs-lookup"><span data-stu-id="facca-120">In the Account field, select the Customer for the next payment.</span></span>
12. <span data-ttu-id="facca-121">Ange betalningsbeloppet i fältet Kredit.</span><span class="sxs-lookup"><span data-stu-id="facca-121">In the Credit field, enter the payment amount.</span></span>
13. <span data-ttu-id="facca-122">Skriv ett värde i fältet Betalningsreferens.</span><span class="sxs-lookup"><span data-stu-id="facca-122">In the Payment reference field, type a value.</span></span>
14. <span data-ttu-id="facca-123">Välj rutan Använd ett insättningskvitto.</span><span class="sxs-lookup"><span data-stu-id="facca-123">Mark the box Use a deposit slip.</span></span>
15. <span data-ttu-id="facca-124">Klicka på Bokför.</span><span class="sxs-lookup"><span data-stu-id="facca-124">Click Post.</span></span>
    * <span data-ttu-id="facca-125">Betalningar måste bokföras, för insättningskvittot kan genereras.</span><span class="sxs-lookup"><span data-stu-id="facca-125">Payments must be posted before the deposit slip can be generated.</span></span> <span data-ttu-id="facca-126">Det garanterar att betalningarna inte ändras, efter insättningskvittot har skapats.</span><span class="sxs-lookup"><span data-stu-id="facca-126">This is to ensure that the payments don't change after the deposit slip is generated.</span></span>  
16. <span data-ttu-id="facca-127">Klicka på Funktioner.</span><span class="sxs-lookup"><span data-stu-id="facca-127">Click Functions.</span></span>
17. <span data-ttu-id="facca-128">Klicka på Insättningskvitto.</span><span class="sxs-lookup"><span data-stu-id="facca-128">Click Deposit slip.</span></span>
18. <span data-ttu-id="facca-129">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="facca-129">Click OK.</span></span>
    * <span data-ttu-id="facca-130">Den första sidan används för att skapa insättningskvittot.</span><span class="sxs-lookup"><span data-stu-id="facca-130">The first page is used to create the deposit slip.</span></span>  
19. <span data-ttu-id="facca-131">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="facca-131">Click OK.</span></span>
    * <span data-ttu-id="facca-132">I det andra steget är att skriva ut insättningskvittot, men steget krävs inte.</span><span class="sxs-lookup"><span data-stu-id="facca-132">The second step is to print the deposit slip, but this step is not required.</span></span>  

