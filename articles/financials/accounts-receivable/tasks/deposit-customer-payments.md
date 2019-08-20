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
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: afbf74d1cf3dc87e97dda0873115b5c7fa49ca3d
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2019
ms.locfileid: "1834473"
---
# <a name="deposit-customer-payments"></a><span data-ttu-id="579b9-103">Sätta in kundbetalningar</span><span class="sxs-lookup"><span data-stu-id="579b9-103">Deposit customer payments</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="579b9-104">Insättning av kundbetalningar.</span><span class="sxs-lookup"><span data-stu-id="579b9-104">Deposit customer payments.</span></span> <span data-ttu-id="579b9-105">I den här uppgiften används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="579b9-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="579b9-106">Gå till Kundreskontra > Betalningar > Betalningsjournal.</span><span class="sxs-lookup"><span data-stu-id="579b9-106">Go to Accounts receivable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="579b9-107">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="579b9-107">Click New.</span></span>
3. <span data-ttu-id="579b9-108">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="579b9-108">In the Name field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="579b9-109">Välj betalningsjournal.</span><span class="sxs-lookup"><span data-stu-id="579b9-109">Select the payment journal.</span></span> 
5. <span data-ttu-id="579b9-110">Klicka på Rader.</span><span class="sxs-lookup"><span data-stu-id="579b9-110">Click Lines.</span></span>
6. <span data-ttu-id="579b9-111">Ange kund som du har tagit emot en betalning för i fältet Konto.</span><span class="sxs-lookup"><span data-stu-id="579b9-111">In the Account field, select the Customer for whom you are recording the payment.</span></span>
7. <span data-ttu-id="579b9-112">Ange beloppet i fältet Kredit.</span><span class="sxs-lookup"><span data-stu-id="579b9-112">In the Credit field, enter the amount of the payment.</span></span>
    * <span data-ttu-id="579b9-113">Du kan välja att lämna beloppet mellanslag och har systemet att uppskatta, genom att välja fakturorna som har betalats.</span><span class="sxs-lookup"><span data-stu-id="579b9-113">You can choose to leave the amount blank, and have the system calculate it by selecting the invoices which were paid.</span></span>  
8. <span data-ttu-id="579b9-114">Skriv ett värde i fältet Betalningsreferens.</span><span class="sxs-lookup"><span data-stu-id="579b9-114">In the Payment reference field, type a value.</span></span>
    * <span data-ttu-id="579b9-115">Betalningsreferensen kan vara checknumret för en betalning som du anger.</span><span class="sxs-lookup"><span data-stu-id="579b9-115">The payment reference could be the check number for the payment you are entering.</span></span> <span data-ttu-id="579b9-116">Betalningsreferensen krävs endast om du markerar för att inkludera betalningen på ett insättningskvitto.</span><span class="sxs-lookup"><span data-stu-id="579b9-116">The payment reference is required in order to include the payment on a deposit slip.</span></span>  
9. <span data-ttu-id="579b9-117">Välj rutan Använd ett insättningskvitto.</span><span class="sxs-lookup"><span data-stu-id="579b9-117">Mark the box Use a deposit slip.</span></span>
    * <span data-ttu-id="579b9-118">Om betalningen ska tas med i insättning, ändrar den här inställningen till Ja.</span><span class="sxs-lookup"><span data-stu-id="579b9-118">If the payment should be included in the deposit, change this setting to Yes.</span></span>  
10. <span data-ttu-id="579b9-119">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="579b9-119">Click New.</span></span>
11. <span data-ttu-id="579b9-120">Välj kund för nästa betalning i fältet Konto.</span><span class="sxs-lookup"><span data-stu-id="579b9-120">In the Account field, select the Customer for the next payment.</span></span>
12. <span data-ttu-id="579b9-121">Ange betalningsbeloppet i fältet Kredit.</span><span class="sxs-lookup"><span data-stu-id="579b9-121">In the Credit field, enter the payment amount.</span></span>
13. <span data-ttu-id="579b9-122">Skriv ett värde i fältet Betalningsreferens.</span><span class="sxs-lookup"><span data-stu-id="579b9-122">In the Payment reference field, type a value.</span></span>
14. <span data-ttu-id="579b9-123">Välj rutan Använd ett insättningskvitto.</span><span class="sxs-lookup"><span data-stu-id="579b9-123">Mark the box Use a deposit slip.</span></span>
15. <span data-ttu-id="579b9-124">Klicka på Bokför.</span><span class="sxs-lookup"><span data-stu-id="579b9-124">Click Post.</span></span>
    * <span data-ttu-id="579b9-125">Betalningar måste bokföras, för insättningskvittot kan genereras.</span><span class="sxs-lookup"><span data-stu-id="579b9-125">Payments must be posted before the deposit slip can be generated.</span></span> <span data-ttu-id="579b9-126">Det garanterar att betalningarna inte ändras, efter insättningskvittot har skapats.</span><span class="sxs-lookup"><span data-stu-id="579b9-126">This is to ensure that the payments don't change after the deposit slip is generated.</span></span>  
16. <span data-ttu-id="579b9-127">Klicka på Funktioner.</span><span class="sxs-lookup"><span data-stu-id="579b9-127">Click Functions.</span></span>
17. <span data-ttu-id="579b9-128">Klicka på Insättningskvitto.</span><span class="sxs-lookup"><span data-stu-id="579b9-128">Click Deposit slip.</span></span>
18. <span data-ttu-id="579b9-129">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="579b9-129">Click OK.</span></span>
    * <span data-ttu-id="579b9-130">Den första sidan används för att skapa insättningskvittot.</span><span class="sxs-lookup"><span data-stu-id="579b9-130">The first page is used to create the deposit slip.</span></span>  
19. <span data-ttu-id="579b9-131">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="579b9-131">Click OK.</span></span>
    * <span data-ttu-id="579b9-132">I det andra steget är att skriva ut insättningskvittot, men steget krävs inte.</span><span class="sxs-lookup"><span data-stu-id="579b9-132">The second step is to print the deposit slip, but this step is not required.</span></span>  

