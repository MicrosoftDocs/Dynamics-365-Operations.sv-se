--- 
title: Skapa fritextfakturor
description: "Det här avsnittet innehåller information om hur du skapar fritextfakturor."
author: mikefalkner
manager: AnnBe
ms.date: 08/24/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.translationtype: HT
ms.sourcegitcommit: f64292a1b3726ea9b43f959a44c4ed2a1f392484
ms.openlocfilehash: f6ee6fda0b52b8af7c253b7d22e470345a8a421f
ms.contentlocale: sv-se
ms.lasthandoff: 09/05/2018

---

# <a name="create-free-text-invoices"></a><span data-ttu-id="30d46-103">Skapa fritextfakturor</span><span class="sxs-lookup"><span data-stu-id="30d46-103">Create free text invoices</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="30d46-104">Det här avsnittet innehåller information om hur du skapar fritextfakturor.</span><span class="sxs-lookup"><span data-stu-id="30d46-104">This topic explains how to create free text invoices.</span></span> <span data-ttu-id="30d46-105">För den här proceduren använder du demonstrationsföretaget **USMF**.</span><span class="sxs-lookup"><span data-stu-id="30d46-105">For the procedure, use the **USMF** demo company.</span></span>

## <a name="create-a-free-text-invoice"></a><span data-ttu-id="30d46-106">Skapa en fritextfaktura</span><span class="sxs-lookup"><span data-stu-id="30d46-106">Create a free text invoice</span></span>

1. <span data-ttu-id="30d46-107">Gå till **Kundreskontra \> Fakturor \> Alla fritextfakturor**.</span><span class="sxs-lookup"><span data-stu-id="30d46-107">Go to **Accounts receivable \> Invoices \> All free text invoices**.</span></span>
2. <span data-ttu-id="30d46-108">Markera **Nytt**.</span><span class="sxs-lookup"><span data-stu-id="30d46-108">Select **New**.</span></span>
3. <span data-ttu-id="30d46-109">Välj ett värde i fältet **Kundkonto**.</span><span class="sxs-lookup"><span data-stu-id="30d46-109">In the **Customer account** field, select a value.</span></span>

    * <span data-ttu-id="30d46-110">Som standard används kontot som valts som kundkonto som fakturakonto.</span><span class="sxs-lookup"><span data-stu-id="30d46-110">By default, the account that is selected as the customer account is used as the invoice account.</span></span>
    * <span data-ttu-id="30d46-111">Om fakturan inte bokförts börjar redovisningsstatusen med **Pågår**.</span><span class="sxs-lookup"><span data-stu-id="30d46-111">If the invoice isn't posted, the accounting status starts with **In process**.</span></span>
    * <span data-ttu-id="30d46-112">Fakturanumret tilldelas när fakturan bokförs.</span><span class="sxs-lookup"><span data-stu-id="30d46-112">The invoice number will be assigned when the invoice is posted.</span></span>
    * <span data-ttu-id="30d46-113">Om du använder SEPA-debitering (Single Euro Payments Area) fylls autogiromedgivandet i automatiskt när du väljer kundkontot.</span><span class="sxs-lookup"><span data-stu-id="30d46-113">If you're using Single Euro Payments Area (SEPA) mandates, the direct debit mandate is automatically entered when you select the customer account.</span></span>

4. <span data-ttu-id="30d46-114">I fältet **Beskrivning** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="30d46-114">In the **Description** field, enter a value.</span></span>
5. <span data-ttu-id="30d46-115">I fältet **Huvudkonto** anger du ett kontonummer utan dimensioner.</span><span class="sxs-lookup"><span data-stu-id="30d46-115">In the **Main account** field, specify an account number that doesn't have dimensions.</span></span> <span data-ttu-id="30d46-116">Du anger dimensioner längre fram i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="30d46-116">You will enter dimensions later in this topic.</span></span>

    <span data-ttu-id="30d46-117">Du kan även ange ett eller flera tecken för huvudkontot och använda sökning för att hitta kontot.</span><span class="sxs-lookup"><span data-stu-id="30d46-117">You can also enter one or more characters for the main account, and use the lookup to find the account.</span></span>

6. <span data-ttu-id="30d46-118">Välj snabbfliken **Radinformation** så att du kan lägga till dimensioner i huvudkontot.</span><span class="sxs-lookup"><span data-stu-id="30d46-118">Select the **Line details** FastTab to add dimensions to the main account.</span></span>
7. <span data-ttu-id="30d46-119">Välj fliken **Rad för ekonomisk dimension**.</span><span class="sxs-lookup"><span data-stu-id="30d46-119">Select the **Financial dimensions line** tab.</span></span>

    * <span data-ttu-id="30d46-120">Dimensionerna avser endast den valda raden.</span><span class="sxs-lookup"><span data-stu-id="30d46-120">The dimensions are for the selected line only.</span></span>
    * <span data-ttu-id="30d46-121">Momsgruppen fylls i av kunden.</span><span class="sxs-lookup"><span data-stu-id="30d46-121">The sales tax group is filled in from the customer.</span></span> <span data-ttu-id="30d46-122">Om kunden inte har någon momsgrupp, används momsgruppen från huvudkontot.</span><span class="sxs-lookup"><span data-stu-id="30d46-122">If the customer doesn't have a sales tax group, the sales tax group from the main account is used.</span></span>
    * <span data-ttu-id="30d46-123">Artikelmomsgruppen fylls i från huvudkontot.</span><span class="sxs-lookup"><span data-stu-id="30d46-123">The items sales tax group is filled in from the main account.</span></span> <span data-ttu-id="30d46-124">Om huvudkontot inte har en artikelmomsgrupp, används artikelmomsgruppen som anges i redovisningens momsparametrar.</span><span class="sxs-lookup"><span data-stu-id="30d46-124">If the main account doesn't have an item sales tax group, the item sales tax group that is specified in the sales tax parameters in General ledger is used.</span></span>

8. <span data-ttu-id="30d46-125">Valfritt: I fältet **Kvantitet** anger du ett nummer.</span><span class="sxs-lookup"><span data-stu-id="30d46-125">Optional: In the **Quantity** field, enter a number.</span></span>
9. <span data-ttu-id="30d46-126">Valfritt: Ange ett nummer i fältet **Enhetspris.**</span><span class="sxs-lookup"><span data-stu-id="30d46-126">Optional: In the **Unit price** field, enter a number.</span></span>

    <span data-ttu-id="30d46-127">Beloppet beräknas som kvantitet gånger enhetspriset.</span><span class="sxs-lookup"><span data-stu-id="30d46-127">The amount is calculated as the quantity times the unit price.</span></span> <span data-ttu-id="30d46-128">Du kan dock åsidosätta den beräkningen genom att ange ett belopp.</span><span class="sxs-lookup"><span data-stu-id="30d46-128">However, you can override that calculation by entering an amount.</span></span>

10. <span data-ttu-id="30d46-129">Välj **Moms** för att visa momsen som beräknas för den fakturan.</span><span class="sxs-lookup"><span data-stu-id="30d46-129">Select **Sales tax** to view the sales tax that is calculated for the invoice.</span></span>

    <span data-ttu-id="30d46-130">Visa momsbeloppen på den här sidan, eller så kan du åsidosätta beloppen på fliken **Justering**.</span><span class="sxs-lookup"><span data-stu-id="30d46-130">You can view the sales tax amounts on this page, or you can override the amounts on the **Adjustment** tab.</span></span>

11. <span data-ttu-id="30d46-131">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="30d46-131">Select **OK**.</span></span>
12. <span data-ttu-id="30d46-132">Klicka på **Avgifter** om du vill lägga till en avgift i din faktura.</span><span class="sxs-lookup"><span data-stu-id="30d46-132">Select **Charges** to add a charge to the invoice.</span></span>
13. <span data-ttu-id="30d46-133">Ange ett värde i fältet **Kod för avgifter**.</span><span class="sxs-lookup"><span data-stu-id="30d46-133">In the **Charges code** field, enter a value.</span></span>
14. <span data-ttu-id="30d46-134">Ange ett nummer i fältet **Avgiftsvärde**.</span><span class="sxs-lookup"><span data-stu-id="30d46-134">In the **Charges value** field, enter a number.</span></span>
15. <span data-ttu-id="30d46-135">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="30d46-135">Close the page.</span></span>
16. <span data-ttu-id="30d46-136">Välj **Summor** för att visa sammanfattande fakturadetaljer och summor.</span><span class="sxs-lookup"><span data-stu-id="30d46-136">Select **Totals** to view a summary of the invoice details and totals.</span></span>
17. <span data-ttu-id="30d46-137">Välj **Nära**.</span><span class="sxs-lookup"><span data-stu-id="30d46-137">Select **Close**.</span></span>
18. <span data-ttu-id="30d46-138">Välj **Bokför** för att bokföra fakturan.</span><span class="sxs-lookup"><span data-stu-id="30d46-138">Select **Post** to post the invoice.</span></span> <span data-ttu-id="30d46-139">Du har fortfarande möjlighet att avbryta innan du bokför.</span><span class="sxs-lookup"><span data-stu-id="30d46-139">You will still have an opportunity to cancel before you actually post.</span></span>

    * <span data-ttu-id="30d46-140">DU kan ändra tidmätning för din fakturautskrift.</span><span class="sxs-lookup"><span data-stu-id="30d46-140">You can change the timing of invoice printing.</span></span> <span data-ttu-id="30d46-141">Välj **Aktuell** om du vill skriva ut fakturor när de uppdateras.</span><span class="sxs-lookup"><span data-stu-id="30d46-141">Select **Current** to print each invoice as it's updated.</span></span> <span data-ttu-id="30d46-142">Välj **Efter** om du vill skriva ut när alla fakturor har uppdaterats.</span><span class="sxs-lookup"><span data-stu-id="30d46-142">Select **After** to print after all invoices have been updated.</span></span>
    * <span data-ttu-id="30d46-143">Om du vill ändra hur kundens kreditgräns kontrolleras innan fakturan bokförs kan du ändra värdet i fältet **kreditgränstyp**.</span><span class="sxs-lookup"><span data-stu-id="30d46-143">To change how the customer's credit limit is verified before the invoice is posted, change the value in the **Credit limit type** field.</span></span>
    * <span data-ttu-id="30d46-144">Om du vill skriva ut fakturan, ange alternativet till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="30d46-144">To print the invoice, set the option to **Yes**.</span></span>
    * <span data-ttu-id="30d46-145">Om du vill bokföra fakturan, ange alternativet till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="30d46-145">To post the invoice, set the option to **Yes**.</span></span> <span data-ttu-id="30d46-146">Du kan skriva ut fakturan utan att bokföra den.</span><span class="sxs-lookup"><span data-stu-id="30d46-146">You can print the invoice without posting it.</span></span>

19. <span data-ttu-id="30d46-147">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="30d46-147">Select **OK**.</span></span>

## <a name="copy-lines"></a><span data-ttu-id="30d46-148">Kopiera rader</span><span class="sxs-lookup"><span data-stu-id="30d46-148">Copy lines</span></span>
<span data-ttu-id="30d46-149">För att kopiera rader på fritextfakturan, markera en eller flera rader och välj **Kopiera markerade rader**.</span><span class="sxs-lookup"><span data-stu-id="30d46-149">To copy lines on a free text invoice, select one or more lines, and then select **Copy selected lines**.</span></span> <span data-ttu-id="30d46-150">Du kan ange hur många kopior som du vill göra och du kan också kopiera anteckningar och bifogade filer.</span><span class="sxs-lookup"><span data-stu-id="30d46-150">You can specify the number of copies to make, and you can also copy notes and attachments.</span></span> <span data-ttu-id="30d46-151">Du kan antingen kopiera fördelningarna eller låta dem återskapas när du bokför.</span><span class="sxs-lookup"><span data-stu-id="30d46-151">You can either copy the distributions or let them be re-created when you post.</span></span>

<span data-ttu-id="30d46-152">När du kopierar rader kan du redigera informationen efter behov.</span><span class="sxs-lookup"><span data-stu-id="30d46-152">After you copy lines, you can edit the information as you require.</span></span>

## <a name="create-a-free-text-invoice-from-a-template"></a><span data-ttu-id="30d46-153">Skapa en fritextfaktura från en mall</span><span class="sxs-lookup"><span data-stu-id="30d46-153">Create a free text invoice from a template</span></span>
<span data-ttu-id="30d46-154">Du kan skapa en fritextfaktura från en mall.</span><span class="sxs-lookup"><span data-stu-id="30d46-154">You can create a free text invoice from a template.</span></span> <span data-ttu-id="30d46-155">När du väljer **Ny från mall** på fliken **Faktura** kan du välja ett mallnamn och kundkontot för den nya fritextfakturan.</span><span class="sxs-lookup"><span data-stu-id="30d46-155">When you select **New from template** on the **Invoice** tab, you can select a template name and the customer account for the new free text invoice.</span></span> <span data-ttu-id="30d46-156">Standardvärden, till exempel betalningsvillkor och betalningsmetod, kan fyllas i automatiskt från kunden, eller du kan använda de värden som sparades i mallen.</span><span class="sxs-lookup"><span data-stu-id="30d46-156">Default values, such as the terms of payment and method of payment, can be automatically filled in from the customer, or you can use the values that were saved in the template.</span></span>

<span data-ttu-id="30d46-157">En ny fritextfaktura skapas och du kan redigera värdena som du vill.</span><span class="sxs-lookup"><span data-stu-id="30d46-157">A new free text invoice is created, and you can edit the values as you require.</span></span>

