--- 
title: Skapa en fritextfaktura
description: "Den här artikeln visar hur du skapar en fritextfaktura."
author: mikefalkner
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
ms.author: mfalkner
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f69505f0c6137121cae92d42d052b244326c8436
ms.openlocfilehash: 2a611bdd4dd97109709ed355eb80471e27413744
ms.contentlocale: sv-se
ms.lasthandoff: 06/28/2018

---

# <a name="create-a-free-text-invoice"></a><span data-ttu-id="4f314-103">Skapa en fritextfaktura</span><span class="sxs-lookup"><span data-stu-id="4f314-103">Create a free text invoice</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4f314-104">Den här artikeln visar hur du skapar en fritextfaktura.</span><span class="sxs-lookup"><span data-stu-id="4f314-104">This article demonstrates how to create a free text invoice.</span></span> <span data-ttu-id="4f314-105">För den här proceduren använder du demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="4f314-105">For this procedure, use the USMF demo company.</span></span>

## <a name="create-a-free-text-invoice"></a><span data-ttu-id="4f314-106">Skapa en fritextfaktura</span><span class="sxs-lookup"><span data-stu-id="4f314-106">Create a free text invoice</span></span>

1. <span data-ttu-id="4f314-107">Gå till Kundreskontra > Fakturor > Alla fritextfakturor.</span><span class="sxs-lookup"><span data-stu-id="4f314-107">Go to Accounts receivable > Invoices > All free text invoices.</span></span>
2. <span data-ttu-id="4f314-108">Klicka på Ny.</span><span class="sxs-lookup"><span data-stu-id="4f314-108">Click New.</span></span>
3. <span data-ttu-id="4f314-109">Välj ett värde i fältet Kundkonto.</span><span class="sxs-lookup"><span data-stu-id="4f314-109">In the Customer account field, select a value.</span></span>
    * <span data-ttu-id="4f314-110">Fakturakontot blir som standard samma konto som används för kundkontot.</span><span class="sxs-lookup"><span data-stu-id="4f314-110">The invoice account will default to the same account used for the customer account.</span></span>   
    * <span data-ttu-id="4f314-111">Redovisningsstatusen börjar med Pågår om fakturan inte har bokförts.</span><span class="sxs-lookup"><span data-stu-id="4f314-111">The accounting status starts with In process if the invoice is not posted.</span></span>   
    * <span data-ttu-id="4f314-112">Fakturanumret tilldelas när fakturan bokförs.</span><span class="sxs-lookup"><span data-stu-id="4f314-112">The invoice number will be assigned when the invoice is posted.</span></span>  
    * <span data-ttu-id="4f314-113">Om du använder SEPA-fullmakter, fylls autogiromedgivandet i automatiskt med en fullmakt när du väljer kundkontot.</span><span class="sxs-lookup"><span data-stu-id="4f314-113">If you are using SEPA mandates, the direct debit mandate will be automatically populated with a mandate when you select the customer account.</span></span>  
4. <span data-ttu-id="4f314-114">Ange ett värde i fältet Beskrivning.</span><span class="sxs-lookup"><span data-stu-id="4f314-114">In the Description field, type a value.</span></span>
5. <span data-ttu-id="4f314-115">Ange ett kontonummer utan dimensioner i huvudkontofältet.</span><span class="sxs-lookup"><span data-stu-id="4f314-115">In the Main account field, specify an account number without dimensions.</span></span>
    * <span data-ttu-id="4f314-116">Du kan även ange ett eller flera tecken för huvudkontot och använda sökning för att hitta kontot.</span><span class="sxs-lookup"><span data-stu-id="4f314-116">You can also enter one or more characters for the main account and use the lookup to find your account.</span></span> <span data-ttu-id="4f314-117">Du anger dimensioner senare i den här handboken.</span><span class="sxs-lookup"><span data-stu-id="4f314-117">You will enter dimensions later on in this guide.</span></span>  
6. <span data-ttu-id="4f314-118">Expandera snabbfliken Radinformation så att du kan lägga till dimensioner i huvudkontot.</span><span class="sxs-lookup"><span data-stu-id="4f314-118">Expand the Line details fasttab so you can add dimensions to your main account.</span></span>
7. <span data-ttu-id="4f314-119">Klicka på fliken Rad för ekonomisk dimension.</span><span class="sxs-lookup"><span data-stu-id="4f314-119">Click the Financial dimensions line tab.</span></span>
    * <span data-ttu-id="4f314-120">Dimensionerna avser endast den valda raden.</span><span class="sxs-lookup"><span data-stu-id="4f314-120">The dimensions are for the selected line only.</span></span>    
    * <span data-ttu-id="4f314-121">Momsgruppen fylls i från kunden.</span><span class="sxs-lookup"><span data-stu-id="4f314-121">The sales tax group is populated from the customer.</span></span> <span data-ttu-id="4f314-122">Om kunden inte har en momsgrupp, används momsgruppen från huvudkontot.</span><span class="sxs-lookup"><span data-stu-id="4f314-122">If the customer does not have a sales tax group, the sales tax group from the main account is used.</span></span>  
    * <span data-ttu-id="4f314-123">Artikelmomsgruppen fylls i från huvudkontot.</span><span class="sxs-lookup"><span data-stu-id="4f314-123">The items sales tax group is populated from the main account.</span></span> <span data-ttu-id="4f314-124">Om huvudkontot inte har en artikelmomsgrupp, används artikelmomsgruppen i redovisningens momsparametrar.</span><span class="sxs-lookup"><span data-stu-id="4f314-124">If the main account does not have an item sales tax group, then the item sales tax group in the General ledger sales tax parameters is used.</span></span>    
8. <span data-ttu-id="4f314-125">Ange ett tal i fältet Kvantitet.</span><span class="sxs-lookup"><span data-stu-id="4f314-125">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="4f314-126">Kvantiteten är valfri.</span><span class="sxs-lookup"><span data-stu-id="4f314-126">The quantity is optional.</span></span>  
9. <span data-ttu-id="4f314-127">Ange ett tal i fältet Enhetspris.</span><span class="sxs-lookup"><span data-stu-id="4f314-127">In the Unit price field, enter a number.</span></span>
    * <span data-ttu-id="4f314-128">Enhetspriset är valfritt.</span><span class="sxs-lookup"><span data-stu-id="4f314-128">The unit price is optional.</span></span>  
    * <span data-ttu-id="4f314-129">Beloppet beräknas som kvantitet gånger enhetspriset.</span><span class="sxs-lookup"><span data-stu-id="4f314-129">The amount is calculated as the quantity times the unit price.</span></span> <span data-ttu-id="4f314-130">Du kan dock åsidosätta den beräkningen och ange ett belopp.</span><span class="sxs-lookup"><span data-stu-id="4f314-130">However, you can override that calculation and enter an amount.</span></span>  
10. <span data-ttu-id="4f314-131">Om du vill visa moms som beräknats för din faktura klickar du på Moms.</span><span class="sxs-lookup"><span data-stu-id="4f314-131">Click on Sales tax to view the sales tax calculated for your invoice.</span></span>
    * <span data-ttu-id="4f314-132">Visa momsbeloppen på den här sidan, eller så kan du åsidosätta beloppen på fliken Justering.</span><span class="sxs-lookup"><span data-stu-id="4f314-132">View the sales tax amounts in this page or you can override the amounts on the Adjustment tab.</span></span>  
11. <span data-ttu-id="4f314-133">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="4f314-133">Click OK.</span></span>
12. <span data-ttu-id="4f314-134">Klicka på Avgifter om du vill lägga till en avgift i din faktura.</span><span class="sxs-lookup"><span data-stu-id="4f314-134">Click Charges to add a charge to your invoice.</span></span> 
13. <span data-ttu-id="4f314-135">I fältet Kod för avgifter, skriv ett värde.</span><span class="sxs-lookup"><span data-stu-id="4f314-135">In the Charges code field, type a value.</span></span>
14. <span data-ttu-id="4f314-136">I fältet Avgiftsvärde, ange ett värde.</span><span class="sxs-lookup"><span data-stu-id="4f314-136">In the Charges value field, enter a number.</span></span>
15. <span data-ttu-id="4f314-137">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="4f314-137">Close the page.</span></span>
16. <span data-ttu-id="4f314-138">Klicka på Summor för att visa sammanfattande fakturadetaljer och summor.</span><span class="sxs-lookup"><span data-stu-id="4f314-138">Click Totals to view the summary invoice details and totals.</span></span>
17. <span data-ttu-id="4f314-139">Klicka på Stäng.</span><span class="sxs-lookup"><span data-stu-id="4f314-139">Click Close.</span></span>
18. <span data-ttu-id="4f314-140">Klicka på Bokför när du vill bokföra fakturan.</span><span class="sxs-lookup"><span data-stu-id="4f314-140">Click Post to post the invoice.</span></span> <span data-ttu-id="4f314-141">Du kan avbryta innan du bokför.</span><span class="sxs-lookup"><span data-stu-id="4f314-141">You will be able to cancel before you post.</span></span>
    * <span data-ttu-id="4f314-142">Om du vill ändra timing på din fakturautskrift: Välj Aktuell om du vill skriva ut fakturor när de uppdateras eller välj Efter om du vill skriva ut när alla fakturor har uppdaterats.</span><span class="sxs-lookup"><span data-stu-id="4f314-142">To change the timing of your invoice printing:  Select Current to print each invoice as it is updated   or  Select After to print after all invoices have been updated.</span></span>  
    * <span data-ttu-id="4f314-143">Om du vill ändra hur kundens kreditgräns kontrolleras innan bokföring, ändra kreditgränstypen.</span><span class="sxs-lookup"><span data-stu-id="4f314-143">If you want to change how the customer's credit limit is checked before posting, change the Credit limit type.</span></span>  
    * <span data-ttu-id="4f314-144">Välj Ja om du vill skriva ut fakturan.</span><span class="sxs-lookup"><span data-stu-id="4f314-144">If you want to print the invoice, select Yes.</span></span>  
    * <span data-ttu-id="4f314-145">Välj Ja om du vill bokföra fakturan.</span><span class="sxs-lookup"><span data-stu-id="4f314-145">If you want to post the invoice, select Yes.</span></span> <span data-ttu-id="4f314-146">Du kan skriva ut fakturan utan bokföring.</span><span class="sxs-lookup"><span data-stu-id="4f314-146">You can print the invoice without posting.</span></span>  
19. <span data-ttu-id="4f314-147">Klicka på OK.</span><span class="sxs-lookup"><span data-stu-id="4f314-147">Click OK.</span></span>

## <a name="copy-lines"></a><span data-ttu-id="4f314-148">Kopiera rader</span><span class="sxs-lookup"><span data-stu-id="4f314-148">Copy lines</span></span>
<span data-ttu-id="4f314-149">För att kopiera rader på fritextfakturan, markera en eller flera rader och välj Kopiera markerade rader.</span><span class="sxs-lookup"><span data-stu-id="4f314-149">To copy lines on the free text invoice, select one or more lines and then click Copy selected lines.</span></span> <span data-ttu-id="4f314-150">Du kan ange hur många kopior som du vill göra och du kan också kopiera anteckningar och bifogade filer.</span><span class="sxs-lookup"><span data-stu-id="4f314-150">You can specify the number of copies that you want to make, and you can also copy notes and attachments.</span></span> <span data-ttu-id="4f314-151">Du kan kopiera fördelningarna eller låta dem återskapas när du bokför.</span><span class="sxs-lookup"><span data-stu-id="4f314-151">You can copy the distributions or allow them to be recreated when you post.</span></span> <span data-ttu-id="4f314-152">När du kopierar rader kan du redigera informationen efter behov.</span><span class="sxs-lookup"><span data-stu-id="4f314-152">Once you copy the lines, you can edit the information as needed.</span></span> 

## <a name="create-a-free-text-invoice-from-a-template"></a><span data-ttu-id="4f314-153">Skapa en fritextfaktura från en mall</span><span class="sxs-lookup"><span data-stu-id="4f314-153">Create a free text invoice from a template</span></span>
<span data-ttu-id="4f314-154">Du kan skapa en fritextfaktura från en mall.</span><span class="sxs-lookup"><span data-stu-id="4f314-154">You can create a free text invoice from a template.</span></span> <span data-ttu-id="4f314-155">När du väljer Ny från mall på fliken Faktura kan du välja ett mallnamn och kundkontot för den nya fritextfakturan.</span><span class="sxs-lookup"><span data-stu-id="4f314-155">When you select New from template from the Invoice tab, you can select a template name and the customer account for the new free text invoice.</span></span> <span data-ttu-id="4f314-156">Du kan också välja standardvärden såsom betalningsvillkor och betalningsmetod från kunden eller använda värden som sparats med mallen.</span><span class="sxs-lookup"><span data-stu-id="4f314-156">You can also choose to default values such as the terms of payment and method of payment from the customer or use the values that were saved with the template.</span></span> <span data-ttu-id="4f314-157">En ny fritextfaktura skapas och du kan redigera värdena i den fakturan.</span><span class="sxs-lookup"><span data-stu-id="4f314-157">A new free text invoice will be created and you can edit the values in that invoice.</span></span> 


