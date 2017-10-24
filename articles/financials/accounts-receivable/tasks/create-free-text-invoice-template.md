--- 
title: "Skapa en mall för fritextfaktura"
description: "I den här registreringen används demonstrationsföretaget USMF."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/11/2016
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
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: e9c9811b348d81cd735c5b75ca48e0a56a8d52be
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-free-text-invoice-template"></a><span data-ttu-id="4364b-103">Skapa en mall för fritextfaktura</span><span class="sxs-lookup"><span data-stu-id="4364b-103">Create a free text invoice template</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4364b-104">I den här registreringen används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="4364b-104">This recording uses the USMF demo company.</span></span> <span data-ttu-id="4364b-105">Inspelningen är avsedd för den användare som ansvarar för hantering och bearbetning av kundreskontrafakturor.</span><span class="sxs-lookup"><span data-stu-id="4364b-105">The recording is intended for the user who is responsible for managing and processing A/R invoices.</span></span>

1. <span data-ttu-id="4364b-106">Gå till Kundreskontra > Fakturor > Återkommande fakturor > Mallar för fritextfaktura.</span><span class="sxs-lookup"><span data-stu-id="4364b-106">Go to Accounts receivable > Invoices > Recurring invoices > Free text invoice templates.</span></span>
    * <span data-ttu-id="4364b-107">Använd det här formuläret om du vill skapa fritextfakturamallar som kan innehålla fakturarader, avgifter, en redovisningsfördelning mall och information om redovisningskonto.</span><span class="sxs-lookup"><span data-stu-id="4364b-107">Use this form to create free text invoice templates that can include invoice lines, charges, an accounting distribution template, and ledger account information.</span></span>  
2. <span data-ttu-id="4364b-108">Klicka på Ny om du vill skapa en ny fritextfaktura.</span><span class="sxs-lookup"><span data-stu-id="4364b-108">Click 'New' to create a new free text invoice template.</span></span>
3. <span data-ttu-id="4364b-109">I fältet Mallnamn, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="4364b-109">In the Template name field, type a value.</span></span>
    * <span data-ttu-id="4364b-110">"Mallnamn" identifierar unikt en fritextfakturamall.</span><span class="sxs-lookup"><span data-stu-id="4364b-110">‘Template name’ uniquely identifies a free text invoice template.</span></span> <span data-ttu-id="4364b-111">Två mallar kan inte ha samma ”mallnamn".</span><span class="sxs-lookup"><span data-stu-id="4364b-111">No two templates can have the same ‘Template name’.</span></span>  
4. <span data-ttu-id="4364b-112">Ange en beskrivning av mallen i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="4364b-112">In the Description field, enter a description of the template.</span></span>
5. <span data-ttu-id="4364b-113">Expandera fakturaradfliken.</span><span class="sxs-lookup"><span data-stu-id="4364b-113">Expand the Invoice lines tab.</span></span>
6. <span data-ttu-id="4364b-114">Ange en beskrivning av fakturaraden i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="4364b-114">In the Description field, enter a description of the invoice line.</span></span>
7. <span data-ttu-id="4364b-115">Välj ett intäktskonto i huvudkontofältet.</span><span class="sxs-lookup"><span data-stu-id="4364b-115">In the Main account field, select a revenue account.</span></span>
    * <span data-ttu-id="4364b-116">Du kan välja mottransaktionskontot för en kundkredit för hela faktureringsbeloppet på sidan Kundbokföringsprofiler.</span><span class="sxs-lookup"><span data-stu-id="4364b-116">You can select the offset transaction account of a customer credit for the total invoice amount in the Customer posting profiles page.</span></span>  
8. <span data-ttu-id="4364b-117">I fältet Momsgrupp, öppna sökningen genom att klicka på den nedrullningsbara knappen.</span><span class="sxs-lookup"><span data-stu-id="4364b-117">In the Sales tax group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="4364b-118">Momsgruppen för den aktuella fakturaraden, som är standardmomsgruppen för kundkontot.</span><span class="sxs-lookup"><span data-stu-id="4364b-118">The sales tax group for the current invoice line is the default sales tax group for the customer account.</span></span>  
9. <span data-ttu-id="4364b-119">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="4364b-119">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="4364b-120">I fältet Artikelmomsgrupp väljer du artikelmomsgruppen för den aktuella fakturaraden.</span><span class="sxs-lookup"><span data-stu-id="4364b-120">In the Item tax group field, select the item sales tax group for the current invoice line.</span></span>
11. <span data-ttu-id="4364b-121">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="4364b-121">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="4364b-122">Ange eller visa pris per enhet för fakturaraden i fältet Enhetspris.</span><span class="sxs-lookup"><span data-stu-id="4364b-122">In the Unit price field, enter or view the price per unit for the invoice line</span></span>
    * <span data-ttu-id="4364b-123">Detta belopp multipliceras med värdet i fältet Kvantitet för att bestämma fakturaradbeloppet.</span><span class="sxs-lookup"><span data-stu-id="4364b-123">This amount is multiplied by the Quantity field to determine the invoice line amount.</span></span>  
13. <span data-ttu-id="4364b-124">Lägg till en ny rad i fritextfakturamallen.</span><span class="sxs-lookup"><span data-stu-id="4364b-124">Add a new line to free text invoice template.</span></span>
14. <span data-ttu-id="4364b-125">Ange en beskrivning av fakturaraden i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="4364b-125">In the Description field, enter a description of the invoice line.</span></span>
15. <span data-ttu-id="4364b-126">Välj ett intäktskonto i huvudkontofältet.</span><span class="sxs-lookup"><span data-stu-id="4364b-126">In the Main account field, select a revenue account.</span></span>
    * <span data-ttu-id="4364b-127">Du kan välja mottransaktionskontot för en kundkredit för hela faktureringsbeloppet på sidan Kundbokföringsprofiler.</span><span class="sxs-lookup"><span data-stu-id="4364b-127">You can select the offset transaction account of a customer credit for the total invoice amount in the Customer posting profiles page.</span></span>  
16. <span data-ttu-id="4364b-128">I fältet Momsgrupp, öppna sökningen genom att klicka på den nedrullningsbara knappen.</span><span class="sxs-lookup"><span data-stu-id="4364b-128">In the Sales tax group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="4364b-129">Momsgruppen för den aktuella fakturaraden, som är standardmomsgruppen för kundkontot.</span><span class="sxs-lookup"><span data-stu-id="4364b-129">The sales tax group for the current invoice line is the default sales tax group for the customer account.</span></span>  
17. <span data-ttu-id="4364b-130">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="4364b-130">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="4364b-131">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelmomsgrupp.</span><span class="sxs-lookup"><span data-stu-id="4364b-131">In the Item sales tax group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="4364b-132">Artikelmomsgruppen för den aktuella fakturaraden.</span><span class="sxs-lookup"><span data-stu-id="4364b-132">The item sales tax group for the current invoice line.</span></span>  
19. <span data-ttu-id="4364b-133">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="4364b-133">In the list, click the link in the selected row.</span></span>
20. <span data-ttu-id="4364b-134">Ange eller visa antalet enheter för fakturaraden.</span><span class="sxs-lookup"><span data-stu-id="4364b-134">Enter or view the number of units for the invoice line</span></span>
    * <span data-ttu-id="4364b-135">Detta nummer multipliceras med värdet i fältet Enhetspris för att bestämma fakturaradbeloppet.</span><span class="sxs-lookup"><span data-stu-id="4364b-135">This number is multiplied by the value in the Unit price field to determine the invoice line amount.</span></span>  
21. <span data-ttu-id="4364b-136">Ange eller visa priset per enhet för fakturaraden.</span><span class="sxs-lookup"><span data-stu-id="4364b-136">Enter or view the price per unit for the invoice line.</span></span> 
    * <span data-ttu-id="4364b-137">Detta belopp multipliceras med värdet i fältet Kvantitet för att bestämma fakturaradbeloppet.</span><span class="sxs-lookup"><span data-stu-id="4364b-137">This amount is multiplied by the value in the Quantity field to determine the invoice line amount.</span></span>  
22. <span data-ttu-id="4364b-138">Visa och ändra redovisningsfördelningarna för en enskild rad, och alla underordnade.</span><span class="sxs-lookup"><span data-stu-id="4364b-138">View and modify the accounting distributions for an individual line and any child lines.</span></span>
    * <span data-ttu-id="4364b-139">Redovisningsfördelningar definierar hur ett belopp ska redovisas, till exempel hur intäkten, momsen eller avgifterna ska redovisas på en fritextfaktura.</span><span class="sxs-lookup"><span data-stu-id="4364b-139">Accounting distributions define how an amount will be accounted for, such as how the revenue, tax, or charges will be accounted for on a free text invoice.</span></span>  
23. <span data-ttu-id="4364b-140">Uppdatera redovisningsfördelningarna för fakturaraden.</span><span class="sxs-lookup"><span data-stu-id="4364b-140">Update the accounting distributions for the selected invoice line.</span></span>
24. <span data-ttu-id="4364b-141">Klicka på Stäng.</span><span class="sxs-lookup"><span data-stu-id="4364b-141">Click Close.</span></span>


