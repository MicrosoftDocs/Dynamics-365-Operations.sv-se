--- 
title: Skapa en fritextfaktura
description: "Den här uppgifthandboken visar hur du skapar en fritextfaktura."
author: mikefalkner
manager: AnnBe
ms.date: 10/26/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: ca7c0f46f0cab298580e37c236bd10e4325e011b
ms.contentlocale: sv-se
ms.lasthandoff: 04/13/2018

---
# <a name="create-a-free-text-invoice"></a><span data-ttu-id="a6755-103">Skapa en fritextfaktura</span><span class="sxs-lookup"><span data-stu-id="a6755-103">Create a free text invoice</span></span>

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a6755-104">Den här uppgifthandboken visar hur du skapar en fritextfaktura.</span><span class="sxs-lookup"><span data-stu-id="a6755-104">This task guide demonstrates creating a free text invoice.</span></span> <span data-ttu-id="a6755-105">I den här uppgiften används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="a6755-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="a6755-106">Gå till Kundreskontra > Fakturor > Alla fritextfakturor.</span><span class="sxs-lookup"><span data-stu-id="a6755-106">Go to Accounts receivable > Invoices > All free text invoices.</span></span>
2. <span data-ttu-id="a6755-107">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="a6755-107">Click New.</span></span>
3. <span data-ttu-id="a6755-108">Välj ett värde i fältet Kundkonto.</span><span class="sxs-lookup"><span data-stu-id="a6755-108">In the Customer account field, select a value.</span></span>
    * <span data-ttu-id="a6755-109">Fakturakontot blir som standard samma konto som används för kundkontot.</span><span class="sxs-lookup"><span data-stu-id="a6755-109">The invoice account will default to the same account used for the customer account.</span></span>   
    * <span data-ttu-id="a6755-110">Redovisningsstatusen börjar med Pågår om fakturan inte har bokförts.</span><span class="sxs-lookup"><span data-stu-id="a6755-110">The accounting status starts with In process if the invoice is not posted.</span></span>   
    * <span data-ttu-id="a6755-111">Fakturanumret tilldelas när fakturan bokförs.</span><span class="sxs-lookup"><span data-stu-id="a6755-111">The invoice number will be assigned when the invoice is posted.</span></span>  
    * <span data-ttu-id="a6755-112">Om du använder SEPA-fullmakter, fylls autogiromedgivandet i automatiskt med en fullmakt när du väljer kundkontot.</span><span class="sxs-lookup"><span data-stu-id="a6755-112">If you are using SEPA mandates, the direct debit mandate will be automatically populated with a mandate when you select the customer account.</span></span>  
4. <span data-ttu-id="a6755-113">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="a6755-113">In the Description field, type a value.</span></span>
5. <span data-ttu-id="a6755-114">Ange ett kontonummer utan dimensioner i huvudkontofältet.</span><span class="sxs-lookup"><span data-stu-id="a6755-114">In the Main account field, specify an account number without dimensions.</span></span>
    * <span data-ttu-id="a6755-115">Du kan även ange ett eller flera tecken för huvudkontot och använda sökning för att hitta kontot.</span><span class="sxs-lookup"><span data-stu-id="a6755-115">You can also enter one or more characters for the main account and use the lookup to find your account.</span></span> <span data-ttu-id="a6755-116">Du anger dimensioner senare i den här handboken.</span><span class="sxs-lookup"><span data-stu-id="a6755-116">You will enter dimensions later on in this guide.</span></span>  
6. <span data-ttu-id="a6755-117">Expandera snabbfliken Radinformation så att du kan lägga till dimensioner i huvudkontot.</span><span class="sxs-lookup"><span data-stu-id="a6755-117">Expand the Line details fasttab so you can add dimensions to your main account.</span></span>
7. <span data-ttu-id="a6755-118">Klicka på fliken Rad för ekonomisk dimension.</span><span class="sxs-lookup"><span data-stu-id="a6755-118">Click the Financial dimensions line tab.</span></span>
    * <span data-ttu-id="a6755-119">Dimensionerna avser endast den valda raden.</span><span class="sxs-lookup"><span data-stu-id="a6755-119">The dimensions are for the selected line only.</span></span>    
    * <span data-ttu-id="a6755-120">Momsgruppen fylls i från kunden.</span><span class="sxs-lookup"><span data-stu-id="a6755-120">The sales tax group is populated from the customer.</span></span> <span data-ttu-id="a6755-121">Om kunden inte har en momsgrupp, används momsgruppen från huvudkontot.</span><span class="sxs-lookup"><span data-stu-id="a6755-121">If the customer does not have a sales tax group, the sales tax group from the main account is used.</span></span>  
    * <span data-ttu-id="a6755-122">Artikelmomsgruppen fylls i från huvudkontot.</span><span class="sxs-lookup"><span data-stu-id="a6755-122">The items sales tax group is populated from the main account.</span></span> <span data-ttu-id="a6755-123">Om huvudkontot inte har en artikelmomsgrupp, används artikelmomsgruppen i redovisningens momsparametrar.</span><span class="sxs-lookup"><span data-stu-id="a6755-123">If the main account does not have an item sales tax group, then the item sales tax group in the General ledger sales tax parameters is used.</span></span>    
8. <span data-ttu-id="a6755-124">Ange ett tal i fältet Kvantitet.</span><span class="sxs-lookup"><span data-stu-id="a6755-124">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="a6755-125">Kvantiteten är valfri.</span><span class="sxs-lookup"><span data-stu-id="a6755-125">The quantity is optional.</span></span>  
9. <span data-ttu-id="a6755-126">Ange ett tal i fältet Enhetspris.</span><span class="sxs-lookup"><span data-stu-id="a6755-126">In the Unit price field, enter a number.</span></span>
    * <span data-ttu-id="a6755-127">Enhetspriset är valfritt.</span><span class="sxs-lookup"><span data-stu-id="a6755-127">The unit price is optional.</span></span>  
    * <span data-ttu-id="a6755-128">Beloppet beräknas som kvantitet gånger enhetspriset.</span><span class="sxs-lookup"><span data-stu-id="a6755-128">The amount is calculated as the quantity times the unit price.</span></span> <span data-ttu-id="a6755-129">Du kan dock åsidosätta den beräkningen och ange ett belopp.</span><span class="sxs-lookup"><span data-stu-id="a6755-129">However, you can override that calculation and enter an amount.</span></span>  
10. <span data-ttu-id="a6755-130">Om du vill visa moms som beräknats för din faktura klickar du på Moms.</span><span class="sxs-lookup"><span data-stu-id="a6755-130">Click on Sales tax to view the sales tax calculated for your invoice.</span></span>
    * <span data-ttu-id="a6755-131">Visa momsbeloppen på den här sidan, eller så kan du åsidosätta beloppen på fliken Justering.</span><span class="sxs-lookup"><span data-stu-id="a6755-131">View the sales tax amounts in this page or you can override the amounts on the Adjustment tab.</span></span>  
11. <span data-ttu-id="a6755-132">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="a6755-132">Click OK.</span></span>
12. <span data-ttu-id="a6755-133">Klicka på Avgifter om du vill lägga till en avgift i din faktura.</span><span class="sxs-lookup"><span data-stu-id="a6755-133">Click Charges to add a charge to your invoice.</span></span> 
13. <span data-ttu-id="a6755-134">I fältet Kod för avgifter, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="a6755-134">In the Charges code field, type a value.</span></span>
14. <span data-ttu-id="a6755-135">I fältet Avgiftsvärde, ange ett värde.</span><span class="sxs-lookup"><span data-stu-id="a6755-135">In the Charges value field, enter a number.</span></span>
15. <span data-ttu-id="a6755-136">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="a6755-136">Close the page.</span></span>
16. <span data-ttu-id="a6755-137">Klicka på Summor för att visa sammanfattande fakturadetaljer och summor.</span><span class="sxs-lookup"><span data-stu-id="a6755-137">Click Totals to view the summary invoice details and totals.</span></span>
17. <span data-ttu-id="a6755-138">Klicka på Stäng.</span><span class="sxs-lookup"><span data-stu-id="a6755-138">Click Close.</span></span>
18. <span data-ttu-id="a6755-139">Klicka på Bokför när du vill bokföra fakturan.</span><span class="sxs-lookup"><span data-stu-id="a6755-139">Click Post to post the invoice.</span></span> <span data-ttu-id="a6755-140">Du kan avbryta innan du bokför.</span><span class="sxs-lookup"><span data-stu-id="a6755-140">You will be able to cancel before you post.</span></span>
    * <span data-ttu-id="a6755-141">Om du vill ändra timing på din fakturautskrift: Välj Aktuell om du vill skriva ut fakturor när de uppdateras eller välj Efter om du vill skriva ut när alla fakturor har uppdaterats.</span><span class="sxs-lookup"><span data-stu-id="a6755-141">To change the timing of your invoice printing:  Select Current to print each invoice as it is updated   or  Select After to print after all invoices have been updated.</span></span>  
    * <span data-ttu-id="a6755-142">Om du vill ändra hur kundens kreditgräns kontrolleras innan bokföring, ändra kreditgränstypen.</span><span class="sxs-lookup"><span data-stu-id="a6755-142">If you want to change how the customer's credit limit is checked before posting, change the Credit limit type.</span></span>  
    * <span data-ttu-id="a6755-143">Välj Ja om du vill skriva ut fakturan.</span><span class="sxs-lookup"><span data-stu-id="a6755-143">If you want to print the invoice, select Yes.</span></span>  
    * <span data-ttu-id="a6755-144">Välj Ja om du vill bokföra fakturan.</span><span class="sxs-lookup"><span data-stu-id="a6755-144">If you want to post the invoice, select Yes.</span></span> <span data-ttu-id="a6755-145">Du kan skriva ut fakturan utan bokföring.</span><span class="sxs-lookup"><span data-stu-id="a6755-145">You can print the invoice without posting.</span></span>  
19. <span data-ttu-id="a6755-146">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="a6755-146">Click OK.</span></span>


