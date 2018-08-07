--- 
title: "Skapa en mall för fritextfaktura"
description: "Den här proceduren visar hur du skapar en mall för fritextfaktura."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 05/29/2018
ms.topic: article
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
ms.sourcegitcommit: d617302e020c21a7a7fb077e4ce9481b6c80b796
ms.openlocfilehash: 80eb886c70e3bfde3a9eff87be48498aa48d7234
ms.contentlocale: sv-se
ms.lasthandoff: 08/06/2018

---
# <a name="create-a-free-text-invoice-template"></a><span data-ttu-id="5ca1c-103">Skapa en mall för fritextfaktura</span><span class="sxs-lookup"><span data-stu-id="5ca1c-103">Create a free text invoice template</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5ca1c-104">För den här genomgången använder du demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="5ca1c-104">For this walkthrough, use the USMF demo company.</span></span> <span data-ttu-id="5ca1c-105">Proceduren är avsedd för den användare som ansvarar för hantering och bearbetning av kundreskontrafakturor.</span><span class="sxs-lookup"><span data-stu-id="5ca1c-105">This procedure is intended for the user who is responsible for managing and processing A/R invoices.</span></span>

## <a name="create-a-template"></a><span data-ttu-id="5ca1c-106">Skapa en mall</span><span class="sxs-lookup"><span data-stu-id="5ca1c-106">Create a template</span></span>

1. <span data-ttu-id="5ca1c-107">Gå till Kundreskontra > Fakturor > Återkommande fakturor > Mallar för fritextfaktura.</span><span class="sxs-lookup"><span data-stu-id="5ca1c-107">Go to Accounts receivable > Invoices > Recurring invoices > Free text invoice templates.</span></span>
    * <span data-ttu-id="5ca1c-108">Använd det här formuläret om du vill skapa fritextfakturamallar som kan innehålla fakturarader, avgifter, en redovisningsfördelning mall och information om redovisningskonto.</span><span class="sxs-lookup"><span data-stu-id="5ca1c-108">Use this form to create free text invoice templates that can include invoice lines, charges, an accounting distribution template, and ledger account information.</span></span>  
2. <span data-ttu-id="5ca1c-109">Klicka på Ny om du vill skapa en ny fritextfaktura.</span><span class="sxs-lookup"><span data-stu-id="5ca1c-109">Click 'New' to create a new free text invoice template.</span></span>
3. <span data-ttu-id="5ca1c-110">I fältet Mallnamn, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="5ca1c-110">In the Template name field, type a value.</span></span>
    * <span data-ttu-id="5ca1c-111">"Mallnamn" identifierar unikt en fritextfakturamall.</span><span class="sxs-lookup"><span data-stu-id="5ca1c-111">‘Template name’ uniquely identifies a free text invoice template.</span></span> <span data-ttu-id="5ca1c-112">Två mallar kan inte ha samma ”mallnamn".</span><span class="sxs-lookup"><span data-stu-id="5ca1c-112">No two templates can have the same ‘Template name’.</span></span>  
4. <span data-ttu-id="5ca1c-113">Ange en beskrivning av mallen i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="5ca1c-113">In the Description field, enter a description of the template.</span></span>
5. <span data-ttu-id="5ca1c-114">Expandera fakturaradfliken.</span><span class="sxs-lookup"><span data-stu-id="5ca1c-114">Expand the Invoice lines tab.</span></span>
6. <span data-ttu-id="5ca1c-115">Ange en beskrivning av fakturaraden i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="5ca1c-115">In the Description field, enter a description of the invoice line.</span></span>
7. <span data-ttu-id="5ca1c-116">Välj ett intäktskonto i huvudkontofältet.</span><span class="sxs-lookup"><span data-stu-id="5ca1c-116">In the Main account field, select a revenue account.</span></span>
    * <span data-ttu-id="5ca1c-117">Du kan välja mottransaktionskontot för en kundkredit för hela faktureringsbeloppet på sidan Kundbokföringsprofiler.</span><span class="sxs-lookup"><span data-stu-id="5ca1c-117">You can select the offset transaction account of a customer credit for the total invoice amount in the Customer posting profiles page.</span></span>  
8. <span data-ttu-id="5ca1c-118">I fältet Momsgrupp, öppna sökningen genom att klicka på den nedrullningsbara knappen.</span><span class="sxs-lookup"><span data-stu-id="5ca1c-118">In the Sales tax group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="5ca1c-119">Momsgruppen för den aktuella fakturaraden, som är standardmomsgruppen för kundkontot.</span><span class="sxs-lookup"><span data-stu-id="5ca1c-119">The sales tax group for the current invoice line is the default sales tax group for the customer account.</span></span>  
9. <span data-ttu-id="5ca1c-120">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="5ca1c-120">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="5ca1c-121">I fältet Artikelmomsgrupp väljer du artikelmomsgruppen för den aktuella fakturaraden.</span><span class="sxs-lookup"><span data-stu-id="5ca1c-121">In the Item tax group field, select the item sales tax group for the current invoice line.</span></span>
11. <span data-ttu-id="5ca1c-122">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="5ca1c-122">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="5ca1c-123">Ange eller visa pris per enhet för fakturaraden i fältet Enhetspris.</span><span class="sxs-lookup"><span data-stu-id="5ca1c-123">In the Unit price field, enter or view the price per unit for the invoice line</span></span>
    * <span data-ttu-id="5ca1c-124">Detta belopp multipliceras med värdet i fältet Kvantitet för att bestämma fakturaradbeloppet.</span><span class="sxs-lookup"><span data-stu-id="5ca1c-124">This amount is multiplied by the Quantity field to determine the invoice line amount.</span></span>  
13. <span data-ttu-id="5ca1c-125">Lägg till en ny rad i fritextfakturamallen.</span><span class="sxs-lookup"><span data-stu-id="5ca1c-125">Add a new line to free text invoice template.</span></span>
14. <span data-ttu-id="5ca1c-126">Ange en beskrivning av fakturaraden i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="5ca1c-126">In the Description field, enter a description of the invoice line.</span></span>
15. <span data-ttu-id="5ca1c-127">Välj ett intäktskonto i huvudkontofältet.</span><span class="sxs-lookup"><span data-stu-id="5ca1c-127">In the Main account field, select a revenue account.</span></span>
    * <span data-ttu-id="5ca1c-128">Du kan välja mottransaktionskontot för en kundkredit för hela faktureringsbeloppet på sidan Kundbokföringsprofiler.</span><span class="sxs-lookup"><span data-stu-id="5ca1c-128">You can select the offset transaction account of a customer credit for the total invoice amount in the Customer posting profiles page.</span></span>  
16. <span data-ttu-id="5ca1c-129">I fältet Momsgrupp, öppna sökningen genom att klicka på den nedrullningsbara knappen.</span><span class="sxs-lookup"><span data-stu-id="5ca1c-129">In the Sales tax group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="5ca1c-130">Momsgruppen för den aktuella fakturaraden, som är standardmomsgruppen för kundkontot.</span><span class="sxs-lookup"><span data-stu-id="5ca1c-130">The sales tax group for the current invoice line is the default sales tax group for the customer account.</span></span>  
17. <span data-ttu-id="5ca1c-131">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="5ca1c-131">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="5ca1c-132">Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelmomsgrupp.</span><span class="sxs-lookup"><span data-stu-id="5ca1c-132">In the Item sales tax group field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="5ca1c-133">Artikelmomsgruppen för den aktuella fakturaraden.</span><span class="sxs-lookup"><span data-stu-id="5ca1c-133">The item sales tax group for the current invoice line.</span></span>  
19. <span data-ttu-id="5ca1c-134">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="5ca1c-134">In the list, click the link in the selected row.</span></span>
20. <span data-ttu-id="5ca1c-135">Ange eller visa antalet enheter för fakturaraden.</span><span class="sxs-lookup"><span data-stu-id="5ca1c-135">Enter or view the number of units for the invoice line</span></span>
    * <span data-ttu-id="5ca1c-136">Detta nummer multipliceras med värdet i fältet Enhetspris för att bestämma fakturaradbeloppet.</span><span class="sxs-lookup"><span data-stu-id="5ca1c-136">This number is multiplied by the value in the Unit price field to determine the invoice line amount.</span></span>  
21. <span data-ttu-id="5ca1c-137">Ange eller visa priset per enhet för fakturaraden.</span><span class="sxs-lookup"><span data-stu-id="5ca1c-137">Enter or view the price per unit for the invoice line.</span></span> 
    * <span data-ttu-id="5ca1c-138">Detta belopp multipliceras med värdet i fältet Kvantitet för att bestämma fakturaradbeloppet.</span><span class="sxs-lookup"><span data-stu-id="5ca1c-138">This amount is multiplied by the value in the Quantity field to determine the invoice line amount.</span></span>  
22. <span data-ttu-id="5ca1c-139">Visa och ändra redovisningsfördelningarna för en enskild rad, och alla underordnade.</span><span class="sxs-lookup"><span data-stu-id="5ca1c-139">View and modify the accounting distributions for an individual line and any child lines.</span></span>
    * <span data-ttu-id="5ca1c-140">Redovisningsfördelningar definierar hur ett belopp ska redovisas, till exempel hur intäkten, momsen eller avgifterna ska redovisas på en fritextfaktura.</span><span class="sxs-lookup"><span data-stu-id="5ca1c-140">Accounting distributions define how an amount will be accounted for, such as how the revenue, tax, or charges will be accounted for on a free text invoice.</span></span>  
23. <span data-ttu-id="5ca1c-141">Uppdatera redovisningsfördelningarna för fakturaraden.</span><span class="sxs-lookup"><span data-stu-id="5ca1c-141">Update the accounting distributions for the selected invoice line.</span></span>
24. <span data-ttu-id="5ca1c-142">Klicka på Stäng.</span><span class="sxs-lookup"><span data-stu-id="5ca1c-142">Click Close.</span></span>

## <a name="save-a-free-text-invoice-as-a-template"></a><span data-ttu-id="5ca1c-143">Spara en fritextfaktura som en mall</span><span class="sxs-lookup"><span data-stu-id="5ca1c-143">Save a free text invoice as a template</span></span>
<span data-ttu-id="5ca1c-144">Du kan också spara en befintlig fritextfaktura som en mall.</span><span class="sxs-lookup"><span data-stu-id="5ca1c-144">You can also save an existing free text invoice as a template.</span></span> <span data-ttu-id="5ca1c-145">När du väljer Spara till mall på fliken Faktura, ange ett namn och en beskrivning för mallen.</span><span class="sxs-lookup"><span data-stu-id="5ca1c-145">When you select Save to template from the Invoice tab, provide a name and a description for the template.</span></span> <span data-ttu-id="5ca1c-146">Om det finns redan en mall med namnet, visas ett meddelande om att en mall med samma namn redan finns.</span><span class="sxs-lookup"><span data-stu-id="5ca1c-146">If a template with the name already exists, you will see a notification that a template with that name already exists.</span></span> <span data-ttu-id="5ca1c-147">Du kan fortfarande klicka på Ok om du vill ersätta den.</span><span class="sxs-lookup"><span data-stu-id="5ca1c-147">You can still click on Ok to replace it.</span></span> 

