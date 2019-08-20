---
title: Ställ in och generera åldersfördelningsinformation för kundreskontra
description: I den här handboken får du hjälp med att ställa in en åldersfördelningsperioddefinition, ålderkundsaldon och vysaldon i ålderssaldolistan och samlingssidan.
author: mikefalkner
manager: AnnBe
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustVendReportInterval, CustAgingSnapshot, CustCollectionsPoolsListPage, CustCollections
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 77b5dd5feb16cc3bd6d64b6520cc47087c5b5224
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2019
ms.locfileid: "1834377"
---
# <a name="set-up-and-generate-accounts-receivable-aging-information"></a><span data-ttu-id="aad81-103">Ställ in och generera åldersfördelningsinformation för kundreskontra</span><span class="sxs-lookup"><span data-stu-id="aad81-103">Set up and generate accounts receivable aging information</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="aad81-104">I den här handboken får du hjälp med att ställa in en åldersfördelningsperioddefinition, ålderkundsaldon och vysaldon i ålderssaldolistan och samlingssidan.</span><span class="sxs-lookup"><span data-stu-id="aad81-104">This guide will help you set up an aging period definition, age customer balances, and view balances in the Aged balance list and the Collections page.</span></span> <span data-ttu-id="aad81-105">I den här registreringen används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="aad81-105">This recording uses the USMF demo company.</span></span>


## <a name="create-an-aging-period-definition"></a><span data-ttu-id="aad81-106">Skapa en åldersfördelningsperioddefinition</span><span class="sxs-lookup"><span data-stu-id="aad81-106">Create an aging period definition</span></span>
1. <span data-ttu-id="aad81-107">Gå till **Navigeringsfönster > Moduler > Kredit och inkasso > Inställningar > Definitioner för åldersfördelningsperiod**.</span><span class="sxs-lookup"><span data-stu-id="aad81-107">Go to **Navigation pane > Modules > Credit and collections > Setup > Aging period definitions**.</span></span>
2. <span data-ttu-id="aad81-108">Klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="aad81-108">Click **New**.</span></span>
3. <span data-ttu-id="aad81-109">Skriv ett värde i fältet **åldersfördelningsperiod**.</span><span class="sxs-lookup"><span data-stu-id="aad81-109">In the **Aging period definition** field, type a value.</span></span>
4. <span data-ttu-id="aad81-110">I fältet **Beskrivning** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="aad81-110">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="aad81-111">Infoga en ny åldersfördelningsperiod genom att klicka på **Lägg till nedan**.</span><span class="sxs-lookup"><span data-stu-id="aad81-111">Click **Add below** to insert a new aging period.</span></span>
6. <span data-ttu-id="aad81-112">Ange beskrivningen som ska visas på åldersrapporter i fältet **Period**.</span><span class="sxs-lookup"><span data-stu-id="aad81-112">In the **Period** field, enter the description to show on aging reports.</span></span>
7. <span data-ttu-id="aad81-113">Välj ett tal i fältet **Enhet**.</span><span class="sxs-lookup"><span data-stu-id="aad81-113">In the **Unit** field, enter a number.</span></span>
8. <span data-ttu-id="aad81-114">Markera ett alternativ i fältet **Intervall**.</span><span class="sxs-lookup"><span data-stu-id="aad81-114">In the **Interval** field, select an option.</span></span> <span data-ttu-id="aad81-115">Redovisningsperioden matchar perioden mot din redovisningskalender.</span><span class="sxs-lookup"><span data-stu-id="aad81-115">Ledger period matches the period to your ledger calendar.</span></span> <span data-ttu-id="aad81-116">Dag, vecka, månad, kvartal och år definierar storleken på intervallet efter datumtyp.</span><span class="sxs-lookup"><span data-stu-id="aad81-116">Day, week, month, quarter and years define the size of the interval by date type.</span></span> <span data-ttu-id="aad81-117">Obegränsat väljer Alla transaktioner, före eller efter den föregående perioden, beroende på om det är den första eller sista perioden.</span><span class="sxs-lookup"><span data-stu-id="aad81-117">Unlimited selects all transactions before or after the previous period, depending on whether it is the first or last period.</span></span>  
9. <span data-ttu-id="aad81-118">Markera ett alternativ i fältet **Åldersfördelningsindikator**.</span><span class="sxs-lookup"><span data-stu-id="aad81-118">In the **Aging indicator** field, select an option.</span></span>
10. <span data-ttu-id="aad81-119">Välj perioden högst upp i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="aad81-119">Select the period at the top of the grid.</span></span> <span data-ttu-id="aad81-120">Uppdatera beskrivningen för att beskriva den äldsta perioden i åldersfördelningsperioddefinitionen</span><span class="sxs-lookup"><span data-stu-id="aad81-120">Update the description to describe the oldest period in the aging period definition</span></span>
11. <span data-ttu-id="aad81-121">Ange den nya beskrivningen som ska visas på åldersfördelningsperioden i fältet **period**.</span><span class="sxs-lookup"><span data-stu-id="aad81-121">In the **Period** field, enter the new description of the aging period.</span></span>
12. <span data-ttu-id="aad81-122">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="aad81-122">Close the page.</span></span>

## <a name="age-the-balances"></a><span data-ttu-id="aad81-123">Åldersfördela saldon</span><span class="sxs-lookup"><span data-stu-id="aad81-123">Age the balances</span></span>
1. <span data-ttu-id="aad81-124">Gå till **Kredit och inkasso > Periodiska uppgifter > Åldersfördelade kundsaldon**.</span><span class="sxs-lookup"><span data-stu-id="aad81-124">Go to **Credit and collections > Periodic tasks > Age customer balances**.</span></span>
2. <span data-ttu-id="aad81-125">Välj **åldersfördelningsperioddefinitionen** som du skapade i fältet åldersfördelningsperioddefinition.</span><span class="sxs-lookup"><span data-stu-id="aad81-125">In the **Aging period definition** field, select the aging period definition that you created.</span></span>
    + <span data-ttu-id="aad81-126">Du kan ha en ögonblicksbild aktiv för varje åldersfördelningsperioddefinition.</span><span class="sxs-lookup"><span data-stu-id="aad81-126">You can have one active snapshot for each aging period definition.</span></span>  
    + <span data-ttu-id="aad81-127">Alla kunder bearbetas som standard.</span><span class="sxs-lookup"><span data-stu-id="aad81-127">All customers are processed by default.</span></span> <span data-ttu-id="aad81-128">Du kan använda det här valet för att beräkna en enskild samlingspool av kunder.</span><span class="sxs-lookup"><span data-stu-id="aad81-128">You can use this selection to calculate a single collections pool of customers.</span></span>  
    + <span data-ttu-id="aad81-129">Välj det datum från den transaktion som du ska använda för åldersfördelningen.</span><span class="sxs-lookup"><span data-stu-id="aad81-129">Select the date from the transaction that you will use for the aging.</span></span>  
    + <span data-ttu-id="aad81-130">Välj ”från och med”-datum för ålder.</span><span class="sxs-lookup"><span data-stu-id="aad81-130">Select an "as of" date for aging.</span></span> <span data-ttu-id="aad81-131">Standardinställningen är Idag, men om du ändrar detta fält till det valda datumet, ska du kunna plocka datum som du vill ha.</span><span class="sxs-lookup"><span data-stu-id="aad81-131">The default is today but, if you change this field to Selected date, you will be able to pick the date that you want.</span></span> <span data-ttu-id="aad81-132">Använd dagens datum för batchbearbetning.</span><span class="sxs-lookup"><span data-stu-id="aad81-132">For batch processing, use Today's date.</span></span>  
3. <span data-ttu-id="aad81-133">Expandera intervallet **företag**.</span><span class="sxs-lookup"><span data-stu-id="aad81-133">Expand the **Company** range.</span></span> <span data-ttu-id="aad81-134">Du kan välja företaget som ska inkluderas i ögonblicksbilden.</span><span class="sxs-lookup"><span data-stu-id="aad81-134">You can select the companies that will be included in the snapshot.</span></span> <span data-ttu-id="aad81-135">Som standard är det aktuella företaget valt.</span><span class="sxs-lookup"><span data-stu-id="aad81-135">The current company is selected by default.</span></span>
4. <span data-ttu-id="aad81-136">Börja bearbeta ögonblicksbilden genom att klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="aad81-136">Click **Ok** to process the snapshot.</span></span> <span data-ttu-id="aad81-137">Den kan dröja en tid, så vänta tills skjutreglaget försvinner och kontrollera meddelandecenter om det finns ett meddelande.</span><span class="sxs-lookup"><span data-stu-id="aad81-137">It will take some time so wait for the slider to disappear and check the message center for a message.</span></span>

## <a name="view-the-balances-on-the-aged-balances-list-and-on-the-collection-page"></a><span data-ttu-id="aad81-138">Visa saldo på åldersfördelningssaldolistan och på samlingssidan</span><span class="sxs-lookup"><span data-stu-id="aad81-138">View the balances on the Aged balances list and on the Collection page</span></span>
1. <span data-ttu-id="aad81-139">Gå till **Kredit och inkasso > Inkasso > Åldersfördelade saldon**.</span><span class="sxs-lookup"><span data-stu-id="aad81-139">Go to **Credit and collections > Collections > Aged balances**.</span></span> <span data-ttu-id="aad81-140">Listsidan innehåller saldon för kunden.</span><span class="sxs-lookup"><span data-stu-id="aad81-140">The list page shows the balances for the customer.</span></span> <span data-ttu-id="aad81-141">Åldersfördelningsikonen visas åldersfördelningsperioden för den äldsta transaktionen.</span><span class="sxs-lookup"><span data-stu-id="aad81-141">The aging icon shows the aging period for the oldest transaction.</span></span>  
2. <span data-ttu-id="aad81-142">Välj en kund med ett saldo.</span><span class="sxs-lookup"><span data-stu-id="aad81-142">Select a customer with a balance.</span></span>
3. <span data-ttu-id="aad81-143">Expandera faktarutan **åldersfördelning** om du vill visa åldersfördelningssaldon.</span><span class="sxs-lookup"><span data-stu-id="aad81-143">Expand the **Aging fact** box area to view the aged balances.</span></span> <span data-ttu-id="aad81-144">Åldersfördelningsperioddefinitionen för faktarutan hämtas från standardåldersfördelningsperioddefinitionen som anges i parametrarna.</span><span class="sxs-lookup"><span data-stu-id="aad81-144">The aging period definition for the fact box is taken from the default aging period definition specified in the parameters.</span></span> <span data-ttu-id="aad81-145">Du kan ändra detta med menyn Inkasso.</span><span class="sxs-lookup"><span data-stu-id="aad81-145">You can change it using the Collect menu.</span></span>  

