---
title: Tilldela en mall för fritextfaktura till en kund
description: Denna uppgift visar hur du tilldelar en fritextfakturamall till en kund.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/12/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustTable, CustRecurrenceInvoice
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fb5dd96cb71dcee6db97ad1074e7e75565ac4101
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4969638"
---
# <a name="assign-a-free-text-invoice-template-to-a-customer"></a><span data-ttu-id="28613-103">Tilldela en mall för fritextfaktura till en kund</span><span class="sxs-lookup"><span data-stu-id="28613-103">Assign a free text invoice template to a customer</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="28613-104">Denna uppgift visar hur du tilldelar en fritextfakturamall till en kund.</span><span class="sxs-lookup"><span data-stu-id="28613-104">This task demonstrates how to assign a free text invoice template to a customer.</span></span> <span data-ttu-id="28613-105">I denna uppgift används USMF-demonstrationsföretaget och är avsett för den användare som ansvarar för hantering och bearbetning av kundreskontrafakturor.</span><span class="sxs-lookup"><span data-stu-id="28613-105">This task uses the USMF demo company and is intended for the user who is responsible for managing and processing A/R invoices.</span></span>

1. <span data-ttu-id="28613-106">I **navigeringsfönstret** går du till **Moduler > Kundreskontra > Kunder > Alla kunder**.</span><span class="sxs-lookup"><span data-stu-id="28613-106">In the **Navigation pane**, go to **Modules > Accounts receivable > Customers > All customers**.</span></span>
2. <span data-ttu-id="28613-107">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="28613-107">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="28613-108">Klicka på **Faktura** i **åtgärdsfönstret**.</span><span class="sxs-lookup"><span data-stu-id="28613-108">On the **Action Pane**, click **Invoice**.</span></span>
4. <span data-ttu-id="28613-109">Klicka på **Återkommande fakturor**.</span><span class="sxs-lookup"><span data-stu-id="28613-109">Click **Recurring invoices**.</span></span> <span data-ttu-id="28613-110">Använd den här sidan för att tilldela fritextfakturamallar till kunder och ange hur ofta fakturor ska skickas till kunden.</span><span class="sxs-lookup"><span data-stu-id="28613-110">Use this page to assign free text invoice templates to customers and specify how frequently invoices will be sent to the customer.</span></span>  
5. <span data-ttu-id="28613-111">Klicka på **Ny** för att tilldela en ny mall till kunden.</span><span class="sxs-lookup"><span data-stu-id="28613-111">Click **New** to assign a new template to the customer.</span></span>
6. <span data-ttu-id="28613-112">I fältet **Mall**, välj den fritextfakturamall som du vill tilldela till kunden.</span><span class="sxs-lookup"><span data-stu-id="28613-112">In the **Template** field, select the free text invoice template you want to assign to the customer.</span></span>
7. <span data-ttu-id="28613-113">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="28613-113">In the list, find and select the desired record.</span></span>
8. <span data-ttu-id="28613-114">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="28613-114">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="28613-115">I fältet **Faktureringsstartdatum**, ange datumet när den första fakturan ska genereras.</span><span class="sxs-lookup"><span data-stu-id="28613-115">In the **Billing start date** field, enter the date when the first invoice will be generated.</span></span>
10. <span data-ttu-id="28613-116">I avsnittet **Avsluta upprepning** anger du ett slutdatum för upprepning.</span><span class="sxs-lookup"><span data-stu-id="28613-116">In the **Recurrence end** section, enter a recurring end date.</span></span>  
    * <span data-ttu-id="28613-117">Välj något av följande: Inget slutdatum – Fakturor skapas utan tidsgräns tills mallen tas bort från kundkontot.</span><span class="sxs-lookup"><span data-stu-id="28613-117">Select one of the following: No end date – Invoices will be generated indefinitely until the template is removed from the customer account.</span></span>
    * <span data-ttu-id="28613-118">Faktureringsslutdatum – Välj det här alternativet för att ange för att ange det senaste datum då fakturan kan genereras.</span><span class="sxs-lookup"><span data-stu-id="28613-118">Billing end date – Select this option and enter the last date that the invoice can be generated.</span></span>  
11. <span data-ttu-id="28613-119">I fältet **Högsta ackumulerat belopp** anger du det högsta ackumulerade belopp efter vilket fakturangenereringen ska stoppas.</span><span class="sxs-lookup"><span data-stu-id="28613-119">In the **Maximum cumulative amount** field, enter the maximum cumulative amount after which invoice generation will stop.</span></span> <span data-ttu-id="28613-120">Ange det maximala ackumulerade belopp som kan uppnås med den valda mallen.</span><span class="sxs-lookup"><span data-stu-id="28613-120">Enter the maximum cumulative amount that can be reached using the selected template.</span></span> <span data-ttu-id="28613-121">Om du till exempel anger 1 000,00 och genererar månatliga fakturor för 100,00 styck, kommer fakturor att upphöra att skapas efter att den tionde fakturan har genererats.</span><span class="sxs-lookup"><span data-stu-id="28613-121">For example, if you enter 1,000.00 and generate monthly invoices for 100.00 each, invoices will stop generating after the tenth invoice is generated.</span></span>  
12. <span data-ttu-id="28613-122">I avsnittet **Skapa återkommande fakturor genom att använda standardvärdena från** väljer du fritextfakturamallen eller kundkontot.</span><span class="sxs-lookup"><span data-stu-id="28613-122">In the **Generate recurring invoices by using the default values from** section, select either free text invoice template or the customer account.</span></span> <span data-ttu-id="28613-123">Välj om du vill använda fritextfakturamallen eller kundkontot för att bestämma standardvärdena för språk, bokföringsprofil, momsgrupp, artikelmomsgrupp, listkod, land/region för leveransen, valuta, betalningsvillkor, betalningsmetod, betalningsspecifikationer, betalningsplan, kassarabatt, ekonomiska dimensioner och gireringsblankett när fakturor skapas.</span><span class="sxs-lookup"><span data-stu-id="28613-123">Select whether to use the free text invoice template or the customer account to determine the default values for the language, posting profile, sales tax group, item sales tax group, list code, country/region for delivery, currency, terms of payment, method of payment, payment specification, payment schedule, cash discount, financial dimensions, and giro money transfer slip when invoices are created.</span></span>  
13. <span data-ttu-id="28613-124">I fältet **Upprepningsmönster**, välj upprepningsmönstret.</span><span class="sxs-lookup"><span data-stu-id="28613-124">In the **Recurrence pattern** field, select the recurrence pattern.</span></span>
    + <span data-ttu-id="28613-125">Dagligen – Ange det här alternativet och ange antalet dagar i fältet Per.</span><span class="sxs-lookup"><span data-stu-id="28613-125">Daily – Select this option and enter the number of days in the Per field.</span></span> <span data-ttu-id="28613-126">Om du till exempel anger 15, kommer en faktura skapas var 15:e dag för den här kunden.</span><span class="sxs-lookup"><span data-stu-id="28613-126">For example, if you enter 15, an invoice will be generated every 15 days for this customer.</span></span>
    + <span data-ttu-id="28613-127">Varje vecka – Välj det här alternativet och ange antalet veckor i fältet Per.</span><span class="sxs-lookup"><span data-stu-id="28613-127">Weekly - Select this option and enter the number of weeks in the Per field.</span></span> <span data-ttu-id="28613-128">Om du till exempel anger 2, kommer en faktura skapas varannan vecka för den här kunden.</span><span class="sxs-lookup"><span data-stu-id="28613-128">For example, if you enter 2, an invoice will be generated every two weeks for this customer.</span></span>
    + <span data-ttu-id="28613-129">Varje månad – Välj det här alternativet och ange antalet månader i fältet Per.</span><span class="sxs-lookup"><span data-stu-id="28613-129">Monthly - Select this option and enter the number of months in the Per field.</span></span> <span data-ttu-id="28613-130">Om du till exempel anger 6, kommer en faktura skapas var sjätte månad för den här kunden.</span><span class="sxs-lookup"><span data-stu-id="28613-130">For example, if you enter 6, an invoice will be generated every six months for this customer.</span></span>
    + <span data-ttu-id="28613-131">Årligen – Välj det här alternativet och ange antalet år i fältet Per.</span><span class="sxs-lookup"><span data-stu-id="28613-131">Yearly – Select this option and enter the number of years in the Per field.</span></span> <span data-ttu-id="28613-132">Om du till exempel anger 2, kommer en faktura skapas vartannat år för den här kunden.</span><span class="sxs-lookup"><span data-stu-id="28613-132">For example, if you enter 2, an invoice will be generated every two years for this customer.</span></span>  
14. <span data-ttu-id="28613-133">I fältet **Per**, ange en siffra.</span><span class="sxs-lookup"><span data-stu-id="28613-133">In the **Per** field, enter a number.</span></span>

