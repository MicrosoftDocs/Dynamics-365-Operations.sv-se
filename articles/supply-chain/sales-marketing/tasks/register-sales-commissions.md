---
title: Registrera försäljningsprovisioner
description: I det här avsnittet beskrivs hur försäljningsprovision beräknas och registreras.
author: omulvad
manager: tfehr
ms.date: 08/06/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, SalesEditLines,  CustInvoiceJournal, CommissionTrans, LedgerTransVoucher
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5c6dbccc3e2c33c8dfec2373bd21c7bd217a889b
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3203249"
---
# <a name="register-sales-commissions"></a><span data-ttu-id="1b30a-103">Registrera försäljningsprovisioner</span><span class="sxs-lookup"><span data-stu-id="1b30a-103">Register sales commissions</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1b30a-104">I det här avsnittet beskrivs hur försäljningsprovision beräknas och registreras.</span><span class="sxs-lookup"><span data-stu-id="1b30a-104">This topic explains how sales commissions are calculated and registered.</span></span> <span data-ttu-id="1b30a-105">Du kan köra den här proceduren i demonstrationsföretaget USMF eller på dina egna data.</span><span class="sxs-lookup"><span data-stu-id="1b30a-105">You can run this procedure in demo data company USMF or on your own data.</span></span> <span data-ttu-id="1b30a-106">Innan du startar guiden kör du guiden ”Ställ in regler för försäljningsprovision” för att vara säker på att alla nödvändiga inställningar för provisionsberäkningen har gjorts.</span><span class="sxs-lookup"><span data-stu-id="1b30a-106">Before starting this guide, run the guide called "Set up sales commission rules" to make sure that you have all the necessary commission calculation setup.</span></span>

<span data-ttu-id="1b30a-107">Skriv upp kundnumren och artikelnumret du har valt för provisionsprocessen, och använd dem när du ska skapa en försäljningsorder i den här guiden.</span><span class="sxs-lookup"><span data-stu-id="1b30a-107">Take note of the customer and item numbers that you have chosen for the commission process and use them when asked to create a sales order in this guide.</span></span>


## <a name="invoice-a-sales-order-that-qualifies-a-salesperson-for-a-commission"></a><span data-ttu-id="1b30a-108">Fakturera en försäljningsorder som kvalificerar en säljare för provision</span><span class="sxs-lookup"><span data-stu-id="1b30a-108">Invoice a sales order that qualifies a salesperson for a commission</span></span>
1. <span data-ttu-id="1b30a-109">I navigeringsfönstret, gå till **Moduler > Försäljning och marknadsföring > Försäljningsorder > Alla försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="1b30a-109">In the navigation pane, go to **Modules > Sales and marketing > Sales orders > All sales orders**.</span></span>
2. <span data-ttu-id="1b30a-110">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="1b30a-110">Select **New**.</span></span>
3. <span data-ttu-id="1b30a-111">I fältet **Kundkonto** välj önskad post i den nedrullningsbara menyn.</span><span class="sxs-lookup"><span data-stu-id="1b30a-111">In the **Customer account** field, select the desired record from the drop-down menu.</span></span>
4. <span data-ttu-id="1b30a-112">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="1b30a-112">Select **OK**.</span></span>
5. <span data-ttu-id="1b30a-113">Välj **Alternativ** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="1b30a-113">On the Action Pane, select **Options**.</span></span>
6. <span data-ttu-id="1b30a-114">Välj **Byt visning**.</span><span class="sxs-lookup"><span data-stu-id="1b30a-114">Select **Change view**.</span></span>
7. <span data-ttu-id="1b30a-115">Välj **Huvudvy**.</span><span class="sxs-lookup"><span data-stu-id="1b30a-115">Select **Header view**.</span></span>
8. <span data-ttu-id="1b30a-116">Expandera avsnittet **Inställningar**.</span><span class="sxs-lookup"><span data-stu-id="1b30a-116">Expand the **Setup** section.</span></span>

    - <span data-ttu-id="1b30a-117">Värdet i fältet **Försäljningsgrupp** representerar en grupp med en eller flera säljare som det tilldelats.</span><span class="sxs-lookup"><span data-stu-id="1b30a-117">The value in the **Sales group** field represents a group with one or more sales representatives assigned to it.</span></span> <span data-ttu-id="1b30a-118">Människorna i gruppen är de som ska få provision när ordern är fakturerad enligt fördefinierade frekvenser och distribution.</span><span class="sxs-lookup"><span data-stu-id="1b30a-118">The people in the group are the ones who will receive commissions when the order is invoiced, as per predefined rates and distribution.</span></span>   
    - <span data-ttu-id="1b30a-119">Värdet kopieras från kund-kort, men du kan ändra det om du vill.</span><span class="sxs-lookup"><span data-stu-id="1b30a-119">The value is copied from the Customer card, but you can change it if you wish.</span></span>  
    - <span data-ttu-id="1b30a-120">Försäljningsgruppen finns också kopieras till kundorderraden.</span><span class="sxs-lookup"><span data-stu-id="1b30a-120">The Sales group is also copied to the sales order line.</span></span> <span data-ttu-id="1b30a-121">Du kan ändra den, så att den kan skilja sig från den i huvudet och/eller mellan raderna.</span><span class="sxs-lookup"><span data-stu-id="1b30a-121">You can change it so that it can differ from the one in the header and/or between lines.</span></span>  
    - <span data-ttu-id="1b30a-122">Värdet i fältet **Provisionsgrupp** representerar en grupp som du har skapat för en eller flera kunder i syfte att spåra provisioner.</span><span class="sxs-lookup"><span data-stu-id="1b30a-122">The value in the **Commission group** field represents a group that you have created for one or more customers with the purpose of tracking commissions.</span></span>   
    - <span data-ttu-id="1b30a-123">Värdet kopieras från kund-kort, men du kan ändra det om du vill.</span><span class="sxs-lookup"><span data-stu-id="1b30a-123">The value is copied from the Customer card, but you can change it if you wish.</span></span>   

9. <span data-ttu-id="1b30a-124">Välj **Alternativ** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="1b30a-124">On the Action Pane, select **Options**.</span></span>
10. <span data-ttu-id="1b30a-125">Välj **Byt visning**.</span><span class="sxs-lookup"><span data-stu-id="1b30a-125">Select **Change view**.</span></span>
11. <span data-ttu-id="1b30a-126">Välj **Radvy**.</span><span class="sxs-lookup"><span data-stu-id="1b30a-126">Select **Line view**.</span></span>
12. <span data-ttu-id="1b30a-127">I den nedrullningsbara menyn i fältet **Artikelnummer** väljer du den artikel som du har ställt in för provisioner.</span><span class="sxs-lookup"><span data-stu-id="1b30a-127">In the drop down menu of the **Item number** field, select the item you have set up for commissions.</span></span> 
13. <span data-ttu-id="1b30a-128">Ange ett nummer i fältet **Kvantitet**.</span><span class="sxs-lookup"><span data-stu-id="1b30a-128">In the **Quantity** field, enter a number.</span></span> <span data-ttu-id="1b30a-129">Observera radens nettobelopp.</span><span class="sxs-lookup"><span data-stu-id="1b30a-129">Take note of the line's Net amount.</span></span> <span data-ttu-id="1b30a-130">Det representerar försäljningsintäkten, som i det här exemplet är grunden för provisionsberäkningen.</span><span class="sxs-lookup"><span data-stu-id="1b30a-130">It represents the sales revenue, which in this example is the basis for commission calculation.</span></span>  
14. <span data-ttu-id="1b30a-131">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="1b30a-131">Select **Save**.</span></span>
15. <span data-ttu-id="1b30a-132">Välj **Faktura** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="1b30a-132">On the Action Pane, select **Invoice**.</span></span>
16. <span data-ttu-id="1b30a-133">Välj **Faktura**.</span><span class="sxs-lookup"><span data-stu-id="1b30a-133">Select **Invoice**.</span></span>
17. <span data-ttu-id="1b30a-134">Expandera avsnittet **Parametrar**.</span><span class="sxs-lookup"><span data-stu-id="1b30a-134">Expand the **Parameters** section.</span></span>
18. <span data-ttu-id="1b30a-135">I fältet **Kvantitet**, välj **Alla**.</span><span class="sxs-lookup"><span data-stu-id="1b30a-135">In the **Quantity** field, select **All**.</span></span>
19. <span data-ttu-id="1b30a-136">Välj **Ja** i fältet **Bokför**.</span><span class="sxs-lookup"><span data-stu-id="1b30a-136">Select **Yes** in the **Posting** field.</span></span>
20. <span data-ttu-id="1b30a-137">Välj **OK** och välj **OK** i nästa ruta.</span><span class="sxs-lookup"><span data-stu-id="1b30a-137">Select **OK**, then select **OK** in the next pane.</span></span> <span data-ttu-id="1b30a-138">Den kan ta minut eller så att bokföra transaktionen.</span><span class="sxs-lookup"><span data-stu-id="1b30a-138">It may take a minute or so to post the transaction.</span></span> <span data-ttu-id="1b30a-139">Tillåt processen att slutföras och stäng inte sidan.</span><span class="sxs-lookup"><span data-stu-id="1b30a-139">Allow the processing to complete and don't close the page.</span></span>  

## <a name="review-the-registered-sales-commissions"></a><span data-ttu-id="1b30a-140">Granska de registrerade försäljningsprovisionerna</span><span class="sxs-lookup"><span data-stu-id="1b30a-140">Review the registered sales commissions</span></span>
1. <span data-ttu-id="1b30a-141">I åtgärdsfönstret väljer du **Faktura**, och sedan **Faktura**.</span><span class="sxs-lookup"><span data-stu-id="1b30a-141">On the Action Pane, select **Invoice**, then select **Invoice** again.</span></span>
2. <span data-ttu-id="1b30a-142">I åtgärdsfönstret väljer du **Faktura**, och sedan **Provisionstransaktioner**.</span><span class="sxs-lookup"><span data-stu-id="1b30a-142">On the Action Pane, select **Invoice**, then select **Commission transactions**.</span></span>

    - <span data-ttu-id="1b30a-143">Fliken **Översikt** visar rader som representerar provisionsbelopp som betalas till säljarna som är associerade med fakturerad försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="1b30a-143">The **Overview** tab displays lines representing the commission amounts payable to sales representatives who are associated with the invoiced sales order.</span></span> <span data-ttu-id="1b30a-144">Vi tar en titt på detaljerna.</span><span class="sxs-lookup"><span data-stu-id="1b30a-144">Let's review the details.</span></span>  
    - <span data-ttu-id="1b30a-145">Om du använde guiden ”Ställ in regler för försäljningsprovision” när du ställde in gruppen **Provisionsförsäljning**, finns det två säljare som får provision och provisionen fördelas lika mellan dem.</span><span class="sxs-lookup"><span data-stu-id="1b30a-145">If you used the "Set up sales commission rules" guide to set up the **Commission sales** group, there are two sales people to receive a sales commissions, and the commission is split equally between them.</span></span>  
    - <span data-ttu-id="1b30a-146">I det här exemplet beräknas provisionens totala belopp som procent av försäljningsintäkten (nettobeloppet på orderraden).</span><span class="sxs-lookup"><span data-stu-id="1b30a-146">In this example, the total amount of the commission is calculated as a percentage of the sales revenue (the net amount of order line).</span></span>  
3. <span data-ttu-id="1b30a-147">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="1b30a-147">Close the page.</span></span>
4. <span data-ttu-id="1b30a-148">Välj **Verifikation**.</span><span class="sxs-lookup"><span data-stu-id="1b30a-148">Select **Voucher**.</span></span> <span data-ttu-id="1b30a-149">Du kan granska de verifikationstransaktionerna för provisionsbeloppen som har bokförts på de fördefinierade kontona för provisionsutgiften och provisionsskulden.</span><span class="sxs-lookup"><span data-stu-id="1b30a-149">You can review the voucher transactions for the commission amounts that have been posted to the predefined commission expense and commission payable accounts.</span></span>  

