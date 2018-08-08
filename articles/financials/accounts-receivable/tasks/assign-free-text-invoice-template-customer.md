--- 
title: "Tilldela en mall för fritextfaktura till en kund"
description: Denna uppgift visar hur du tilldelar en fritextfakturamall till en kund.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: e29122fa775385ca4d407ddbe190626d743da69b
ms.contentlocale: sv-se
ms.lasthandoff: 08/07/2018

---
# <a name="assign-a-free-text-invoice-template-to-a-customer"></a><span data-ttu-id="fbc98-103">Tilldela en mall för fritextfaktura till en kund</span><span class="sxs-lookup"><span data-stu-id="fbc98-103">Assign a free text invoice template to a customer</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="fbc98-104">Denna uppgift visar hur du tilldelar en fritextfakturamall till en kund.</span><span class="sxs-lookup"><span data-stu-id="fbc98-104">This task demonstrates how to assign a free text invoice template to a customer.</span></span> <span data-ttu-id="fbc98-105">I denna uppgift används USMF-demonstrationsföretaget och är avsett för den användare som ansvarar för hantering och bearbetning av kundreskontrafakturor.</span><span class="sxs-lookup"><span data-stu-id="fbc98-105">This task uses the USMF demo company and is intended for the user who is responsible for managing and processing A/R invoices.</span></span>

1. <span data-ttu-id="fbc98-106">Gå till Leverantörsreskontra > Kunder > Alla kunder.</span><span class="sxs-lookup"><span data-stu-id="fbc98-106">Go to Accounts receivable > Customers > All customers.</span></span>
2. <span data-ttu-id="fbc98-107">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="fbc98-107">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="fbc98-108">Klicka på Faktura i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="fbc98-108">On the Action Pane, click Invoice.</span></span>
4. <span data-ttu-id="fbc98-109">Klicka på återkommande fakturor.</span><span class="sxs-lookup"><span data-stu-id="fbc98-109">Click Recurring invoices.</span></span>
    * <span data-ttu-id="fbc98-110">Använd den här sidan för att tilldela fritextfakturamallar till kunder och ange hur ofta fakturor ska skickas till kunden.</span><span class="sxs-lookup"><span data-stu-id="fbc98-110">Use this page to assign free text invoice templates to customers and specify how frequently invoices will be sent to the customer.</span></span>  
5. <span data-ttu-id="fbc98-111">Klicka på Nytt för att tilldela en ny mall till kunden.</span><span class="sxs-lookup"><span data-stu-id="fbc98-111">Click New to assign a new template to the customer.</span></span>
6. <span data-ttu-id="fbc98-112">Välj den fritextfakturamall som du vill tilldela till kunden.</span><span class="sxs-lookup"><span data-stu-id="fbc98-112">Select the free text invoice template you want to assign to the customer.</span></span>
7. <span data-ttu-id="fbc98-113">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="fbc98-113">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="fbc98-114">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="fbc98-114">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="fbc98-115">Ange datumet när den första fakturan ska skapas.</span><span class="sxs-lookup"><span data-stu-id="fbc98-115">Enter the date when the first invoice will be generated.</span></span>
    * <span data-ttu-id="fbc98-116">Ange ett återkommande slutdatum.</span><span class="sxs-lookup"><span data-stu-id="fbc98-116">Enter a recurring end date.</span></span>  
    * <span data-ttu-id="fbc98-117">Välj något av följande: Inget slutdatum – Fakturor skapas utan tidsgräns tills mallen tas bort från kundkontot.</span><span class="sxs-lookup"><span data-stu-id="fbc98-117">Select one of the following: No end date – Invoices will be generated indefinitely until the template is removed from the customer account.</span></span>  <span data-ttu-id="fbc98-118">Faktureringsslutdatum – Välj det här alternativet för att ange för att ange det senaste datum då fakturan kan genereras.</span><span class="sxs-lookup"><span data-stu-id="fbc98-118">Billing end date – Select this option and enter the last date that the invoice can be generated.</span></span>  
    * <span data-ttu-id="fbc98-119">Maximalt ackumulerat belopp vid vilket skapandet av fakturor kommer att upphöra.</span><span class="sxs-lookup"><span data-stu-id="fbc98-119">Maximum cumulative amount after which invoice generation will stop.</span></span>  
    * <span data-ttu-id="fbc98-120">Ange det maximala ackumulerade belopp som kan uppnås med den valda mallen.</span><span class="sxs-lookup"><span data-stu-id="fbc98-120">Enter the maximum cumulative amount that can be reached using the selected template.</span></span> <span data-ttu-id="fbc98-121">Om du till exempel anger 1 000,00 och genererar månatliga fakturor för 100,00 styck, kommer fakturor att upphöra att skapas efter att den tionde fakturan har genererats.</span><span class="sxs-lookup"><span data-stu-id="fbc98-121">For example, if you enter 1,000.00 and generate monthly invoices for 100.00 each, invoices will stop generating after the tenth invoice is generated.</span></span>  
    * <span data-ttu-id="fbc98-122">Generera återkommande fakturor genom att använda förvalda värden antingen från sidan fritextfakturamall eller kundkontot.</span><span class="sxs-lookup"><span data-stu-id="fbc98-122">Generate recurring invoices by using the default values from either free text invoice template or the customer account.</span></span>  
    * <span data-ttu-id="fbc98-123">Välj om du vill använda fritextfakturamallen eller kundkontot för att bestämma standardvärdena för språk, bokföringsprofil, momsgrupp, artikelmomsgrupp, listkod, land/region för leveransen, valuta, betalningsvillkor, betalningsmetod, betalningsspecifikationer, betalningsplan, kassarabatt, ekonomiska dimensioner och gireringsblankett när fakturor skapas.</span><span class="sxs-lookup"><span data-stu-id="fbc98-123">Select whether to use the free text invoice template or the customer account to determine the default values for the language, posting profile, sales tax group, item sales tax group, list code, country/region for delivery, currency, terms of payment, method of payment, payment specification, payment schedule, cash discount, financial dimensions, and giro money transfer slip when invoices are created.</span></span>  
10. <span data-ttu-id="fbc98-124">Välj upprepningsmönstret.</span><span class="sxs-lookup"><span data-stu-id="fbc98-124">Select the recurrence pattern.</span></span>
    * <span data-ttu-id="fbc98-125">Dagligen – Ange det här alternativet och ange antalet dagar i fältet Per.</span><span class="sxs-lookup"><span data-stu-id="fbc98-125">Daily – Select this option and enter the number of days in the Per field.</span></span> <span data-ttu-id="fbc98-126">Om du till exempel anger 15, kommer en faktura skapas var 15:e dag för den här kunden.</span><span class="sxs-lookup"><span data-stu-id="fbc98-126">For example, if you enter 15, an invoice will be generated every 15 days for this customer.</span></span>  <span data-ttu-id="fbc98-127">Varje vecka - Välj det här alternativet och ange antalet veckor i fältet Per.</span><span class="sxs-lookup"><span data-stu-id="fbc98-127">Weekly - Select this option and enter the number of weeks in the Per field.</span></span> <span data-ttu-id="fbc98-128">Om du till exempel anger 2, kommer en faktura skapas varannan vecka för den här kunden.</span><span class="sxs-lookup"><span data-stu-id="fbc98-128">For example, if you enter 2, an invoice will be generated every two weeks for this customer.</span></span>  <span data-ttu-id="fbc98-129">Varje månad - Välj det här alternativet och ange antalet månader i fältet Per.</span><span class="sxs-lookup"><span data-stu-id="fbc98-129">Monthly - Select this option and enter the number of months in the Per field.</span></span> <span data-ttu-id="fbc98-130">Om du till exempel anger 6, kommer en faktura skapas var sjätte månad för den här kunden.</span><span class="sxs-lookup"><span data-stu-id="fbc98-130">For example, if you enter 6, an invoice will be generated every six months for this customer.</span></span>  <span data-ttu-id="fbc98-131">Årligen - Välj det här alternativet och ange antalet år i fältet Per.</span><span class="sxs-lookup"><span data-stu-id="fbc98-131">Yearly – Select this option and enter the number of years in the Per field.</span></span> <span data-ttu-id="fbc98-132">Om du till exempel anger 2, kommer en faktura skapas vartannat år för den här kunden.</span><span class="sxs-lookup"><span data-stu-id="fbc98-132">For example, if you enter 2, an invoice will be generated every two years for this customer.</span></span>  
11. <span data-ttu-id="fbc98-133">Ange ett tal i fältet Per.</span><span class="sxs-lookup"><span data-stu-id="fbc98-133">In the Per field, enter a number.</span></span>


