--- 
title: "Sätta in kundbetalningar"
description: "Insättning av kundbetalningar."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: dbf21bd5df70cd80e4fe3f2f5d699aa82b62423b
ms.contentlocale: sv-se
ms.lasthandoff: 08/29/2017

---
# <a name="deposit-customer-payments"></a><span data-ttu-id="38d78-103">Sätta in kundbetalningar</span><span class="sxs-lookup"><span data-stu-id="38d78-103">Deposit customer payments</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="38d78-104">Insättning av kundbetalningar.</span><span class="sxs-lookup"><span data-stu-id="38d78-104">Deposit customer payments.</span></span> <span data-ttu-id="38d78-105">I den här uppgiften används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="38d78-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="38d78-106">Gå till Kundreskontra > Betalningar > Betalningsjournal.</span><span class="sxs-lookup"><span data-stu-id="38d78-106">Go to Accounts receivable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="38d78-107">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="38d78-107">Click New.</span></span>
3. <span data-ttu-id="38d78-108">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Namn.</span><span class="sxs-lookup"><span data-stu-id="38d78-108">In the Name field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="38d78-109">Välj betalningsjournal.</span><span class="sxs-lookup"><span data-stu-id="38d78-109">Select the payment journal.</span></span> 
5. <span data-ttu-id="38d78-110">Klicka på Rader.</span><span class="sxs-lookup"><span data-stu-id="38d78-110">Click Lines.</span></span>
6. <span data-ttu-id="38d78-111">Ange kund som du har tagit emot en betalning för i fältet Konto.</span><span class="sxs-lookup"><span data-stu-id="38d78-111">In the Account field, select the Customer for whom you are recording the payment.</span></span>
7. <span data-ttu-id="38d78-112">Ange beloppet i fältet Kredit.</span><span class="sxs-lookup"><span data-stu-id="38d78-112">In the Credit field, enter the amount of the payment.</span></span>
    * <span data-ttu-id="38d78-113">Du kan välja att lämna beloppet mellanslag och har systemet att uppskatta, genom att välja fakturorna som har betalats.</span><span class="sxs-lookup"><span data-stu-id="38d78-113">You can choose to leave the amount blank, and have the system calculate it by selecting the invoices which were paid.</span></span>  
8. <span data-ttu-id="38d78-114">Skriv ett värde i fältet Betalningsreferens.</span><span class="sxs-lookup"><span data-stu-id="38d78-114">In the Payment reference field, type a value.</span></span>
    * <span data-ttu-id="38d78-115">Betalningsreferensen kan vara checknumret för en betalning som du anger.</span><span class="sxs-lookup"><span data-stu-id="38d78-115">The payment reference could be the check number for the payment you are entering.</span></span> <span data-ttu-id="38d78-116">Betalningsreferensen krävs endast om du markerar för att inkludera betalningen på ett insättningskvitto.</span><span class="sxs-lookup"><span data-stu-id="38d78-116">The payment reference is required in order to include the payment on a deposit slip.</span></span>  
9. <span data-ttu-id="38d78-117">Välj rutan Använd ett insättningskvitto.</span><span class="sxs-lookup"><span data-stu-id="38d78-117">Mark the box Use a deposit slip.</span></span>
    * <span data-ttu-id="38d78-118">Om betalningen ska tas med i insättning, ändrar den här inställningen till Ja.</span><span class="sxs-lookup"><span data-stu-id="38d78-118">If the payment should be included in the deposit, change this setting to Yes.</span></span>  
10. <span data-ttu-id="38d78-119">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="38d78-119">Click New.</span></span>
11. <span data-ttu-id="38d78-120">Välj kund för nästa betalning i fältet Konto.</span><span class="sxs-lookup"><span data-stu-id="38d78-120">In the Account field, select the Customer for the next payment.</span></span>
12. <span data-ttu-id="38d78-121">Ange betalningsbeloppet i fältet Kredit.</span><span class="sxs-lookup"><span data-stu-id="38d78-121">In the Credit field, enter the payment amount.</span></span>
13. <span data-ttu-id="38d78-122">Skriv ett värde i fältet Betalningsreferens.</span><span class="sxs-lookup"><span data-stu-id="38d78-122">In the Payment reference field, type a value.</span></span>
14. <span data-ttu-id="38d78-123">Välj rutan Använd ett insättningskvitto.</span><span class="sxs-lookup"><span data-stu-id="38d78-123">Mark the box Use a deposit slip.</span></span>
15. <span data-ttu-id="38d78-124">Klicka på Bokför.</span><span class="sxs-lookup"><span data-stu-id="38d78-124">Click Post.</span></span>
    * <span data-ttu-id="38d78-125">Betalningar måste bokföras, för insättningskvittot kan genereras.</span><span class="sxs-lookup"><span data-stu-id="38d78-125">Payments must be posted before the deposit slip can be generated.</span></span> <span data-ttu-id="38d78-126">Det garanterar att betalningarna inte ändras, efter insättningskvittot har skapats.</span><span class="sxs-lookup"><span data-stu-id="38d78-126">This is to ensure that the payments don't change after the deposit slip is generated.</span></span>  
16. <span data-ttu-id="38d78-127">Klicka på Funktioner.</span><span class="sxs-lookup"><span data-stu-id="38d78-127">Click Functions.</span></span>
17. <span data-ttu-id="38d78-128">Klicka på Insättningskvitto.</span><span class="sxs-lookup"><span data-stu-id="38d78-128">Click Deposit slip.</span></span>
18. <span data-ttu-id="38d78-129">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="38d78-129">Click OK.</span></span>
    * <span data-ttu-id="38d78-130">Den första sidan används för att skapa insättningskvittot.</span><span class="sxs-lookup"><span data-stu-id="38d78-130">The first page is used to create the deposit slip.</span></span>  
19. <span data-ttu-id="38d78-131">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="38d78-131">Click OK.</span></span>
    * <span data-ttu-id="38d78-132">I det andra steget är att skriva ut insättningskvittot, men steget krävs inte.</span><span class="sxs-lookup"><span data-stu-id="38d78-132">The second step is to print the deposit slip, but this step is not required.</span></span>  


