---
title: Registrera inleverans av returnerade artiklar
description: "Du kan registrera inleverans av returnerade artiklar med formuläret Införselöversikt eller Registration."
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WMSArrivalOverview, InventTransRegister
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 2be628d312e623e8ea6d92eb5edce12334190d9e
ms.contentlocale: sv-se
ms.lasthandoff: 08/07/2018

---


# <a name="register-the-receipt-of-returned-items"></a><span data-ttu-id="e2050-103">Registrera inleverans av returnerade artiklar</span><span class="sxs-lookup"><span data-stu-id="e2050-103">Register the receipt of returned items</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="e2050-104">Du kan registrera inleverans av returnerade artiklar på två sätt.</span><span class="sxs-lookup"><span data-stu-id="e2050-104">There are two methods for registering the receipt of returned items.</span></span> <span data-ttu-id="e2050-105">Den första metoden är en lagerinleveransprocess som använder formuläret **Införselöversikt**.</span><span class="sxs-lookup"><span data-stu-id="e2050-105">The first method is a warehouse receiving process that uses the **Arrival overview** form.</span></span> <span data-ttu-id="e2050-106">Andra använder formuläret **Registrering**.</span><span class="sxs-lookup"><span data-stu-id="e2050-106">The second uses the **Registration** form.</span></span>

## <a name="register-the-receipt-of-returned-items-in-the-arrival-overview-form"></a><span data-ttu-id="e2050-107">Registrera inleverans av returnerade artiklar i formuläret Införselöversikt</span><span class="sxs-lookup"><span data-stu-id="e2050-107">Register the receipt of returned items in the Arrival overview form</span></span>

<span data-ttu-id="e2050-108">Du kan använda formuläret **Införselöversikt**för att identifiera en returleverans genom dess RMA-numret (Return Material Authorization).</span><span class="sxs-lookup"><span data-stu-id="e2050-108">You can use the **Arrival overview** form to identify a return shipment by its Return Material Authorization (RMA) number.</span></span> <span data-ttu-id="e2050-109">Om ett journalnamn definieras på fliken **Inställning**och journalrader som motsvarar de rader som väljs i formuläret **Införselöversikt** finns, skapas en ny journalrubrik när du klickar på **Starta införsel**.</span><span class="sxs-lookup"><span data-stu-id="e2050-109">If a journal name is defined on the **Setup** tab, and journal lines that correspond to the lines selected on the **Arrival overview** form exist, a new journal header is created when you click **Start arrival**.</span></span>

1.  <span data-ttu-id="e2050-110">Klicka på **Lagerhantering** \> **Periodisk** \> **Införselöversikt**.</span><span class="sxs-lookup"><span data-stu-id="e2050-110">Click **Inventory management** \> **Periodic** \> **Arrival overview**.</span></span>

2.  <span data-ttu-id="e2050-111">I fältet **inställningsnamn** väljer du **returorder**, och klickar sedan på **uppdatering**.</span><span class="sxs-lookup"><span data-stu-id="e2050-111">In the **Setup name** field, select **Return order**, and then click **Update**.</span></span>
    

    > [!TIP]
    > <P><span data-ttu-id="e2050-112">Du kan använda fälten <STRONG>Intervall</STRONG> för att begränsa sökresultatet.</span><span class="sxs-lookup"><span data-stu-id="e2050-112">You can use the <STRONG>Range</STRONG> fields to narrow the search results.</span></span> <span data-ttu-id="e2050-113">Du kan ange eller välja RMA-numret i fältet <STRONG>RMA-nummer</STRONG> för ett visst resultat.</span><span class="sxs-lookup"><span data-stu-id="e2050-113">You can type or select the RMA number in the <STRONG>RMA number</STRONG> field for an exact result.</span></span> <span data-ttu-id="e2050-114">Du kan ange och spara en uppsättning filter som ska begränsa vilka inkommande införsel som visas klickar du på fliken <STRONG>inställningar</STRONG>. Tillgängliga filtren är typer, lagerställen och dockningsstationer.</span><span class="sxs-lookup"><span data-stu-id="e2050-114">To define and save a set of filters that will restrict which incoming arrivals are displayed, click the <STRONG>Setup</STRONG> tab. The available filters include types, warehouses, and docks.</span></span></P>

    

    > [!WARNING]
    > <P><span data-ttu-id="e2050-115">Returneraordrar kan inte blandas med andra inleveranstyper i formuläret <STRONG>Införselöversikt</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="e2050-115">Return orders cannot be mixed with other arrival types in the <STRONG>Arrival overview</STRONG> form.</span></span> <span data-ttu-id="e2050-116">Därför kommer referensen alltid att vara försäljningsorder, men inga försäljningsorder-ID ska anges i journalrubriken.</span><span class="sxs-lookup"><span data-stu-id="e2050-116">Therefore, the reference will always be sales order, but no sales order ID will be specified on the journal header.</span></span></P>



3.  <span data-ttu-id="e2050-117">I rutnätet **Inleveranser**, leta upp den rad som matchar den returnerade artikeln och markera rutan i kolumnen **Välj för införsel**.</span><span class="sxs-lookup"><span data-stu-id="e2050-117">In the **Receipts** grid, locate the line that matches the item being returned, and then select the check box in the **Select for arrival** column.</span></span>

4.  <span data-ttu-id="e2050-118">Om du vill undanta vissa rader från returinleveransen, t.ex. artiklar från den ursprungliga ordern som inte har inkluderats i returen, avmarkerar du motsvarande kryssrutor **Välj för införsel** i tabellen **Rader** i den nedre delen av formuläret.</span><span class="sxs-lookup"><span data-stu-id="e2050-118">To exclude certain lines from the return receipt, such as items from the original order that were not included in the return shipment, clear the associated **Select for arrival** check boxes in the **Lines** table in the lower part of the form.</span></span>

5.  <span data-ttu-id="e2050-119">Klicka på **Start införsel** om du vill skapa en införseljournal.</span><span class="sxs-lookup"><span data-stu-id="e2050-119">Click the **Start arrival** button to create an arrival journal.</span></span>
    

    > [!NOTE]
    > <P><span data-ttu-id="e2050-120">Du kan markera flera returorder och inkludera dem alla i en enda inleveransprocess.</span><span class="sxs-lookup"><span data-stu-id="e2050-120">You can select multiple return orders and include them all in a single arrival process.</span></span> <span data-ttu-id="e2050-121">Varje returorderrad kopieras till motsvarande journalrad för artikelinleverans.</span><span class="sxs-lookup"><span data-stu-id="e2050-121">Each return order line will be copied into a corresponding item arrival journal line.</span></span></P>

    

    > [!NOTE]
    > <P><span data-ttu-id="e2050-122">Du kan också manuellt skapa en införseljournal med hjälp av formuläret <STRONG>Artikelinförsel</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="e2050-122">You can also manually create an arrival journal by using the <STRONG>Item arrival</STRONG> form.</span></span> 



6.  <span data-ttu-id="e2050-123">Klicka på **Lagerhantering** \> **Journaler** \> **Artikelinförsel** \> **Artikelinförsel**.</span><span class="sxs-lookup"><span data-stu-id="e2050-123">Click **Inventory management** \> **Journals** \> **Item arrival** \> **Item arrival**.</span></span>

7.  <span data-ttu-id="e2050-124">Välj införseljournalen som du just skapat, och klicka sedan på **Rader** för att öppna formuläret **Journalrader, platser**.</span><span class="sxs-lookup"><span data-stu-id="e2050-124">Select the arrival journal that you just created and then click **Lines** to open the **Journal lines, locations** form.</span></span>

8.  <span data-ttu-id="e2050-125">På fliken**Allmänt**, justera antalet i fältet **Kvantitet** om det behövs, och sedan tilldela en dispositionskod i fältet **Dispositionskod**.</span><span class="sxs-lookup"><span data-stu-id="e2050-125">On the **General** tab, adjust the number in the **Quantity** field, if it is required, and then assign a disposition code in the **Disposition code** field.</span></span>
    
    <span data-ttu-id="e2050-126">Alternativt kan du välja kryssrutan **Karantänhantering** om du vill att de returnerade artiklarna som skickas via en inspektionprocess i samband med en karantänorder.</span><span class="sxs-lookup"><span data-stu-id="e2050-126">Alternatively, you can select the **Quarantine management** check box to have the returned items sent through an inspection process in the context of a quarantine order.</span></span>
    

    > [!NOTE]
    > <P><span data-ttu-id="e2050-127">Om du skickar de returnerade artiklarna genom karantän, kan du inte ange en dispositionskod.</span><span class="sxs-lookup"><span data-stu-id="e2050-127">If you send the returned items through quarantine, you cannot specify a disposition code.</span></span></P>



9.  <span data-ttu-id="e2050-128">Klicka på knappen **Validera**.</span><span class="sxs-lookup"><span data-stu-id="e2050-128">Click the **Validate** button.</span></span>

10. <span data-ttu-id="e2050-129">Om det inte finns några fel i valideringsprocessen klickar du på **Bokföra**.</span><span class="sxs-lookup"><span data-stu-id="e2050-129">If there are no errors in the validation process, click **Post**.</span></span>

## <a name="register-the-receipt-of-returned-items-in-the-registration-form"></a><span data-ttu-id="e2050-130">Registrera inleverans av returnerade artiklar i formuläret Registrering</span><span class="sxs-lookup"><span data-stu-id="e2050-130">Register the receipt of returned items in the Registration form</span></span>

<span data-ttu-id="e2050-131">Ett alternativ till att använda formuläret **Införselöversikt** kan du använda formuläret **Registrering** om du vill registrera inleverans av returnerade artiklar.</span><span class="sxs-lookup"><span data-stu-id="e2050-131">As an alternative to using the **Arrival overview** form, you can use the **Registration** form to register the arrival of returned items.</span></span>

1.  <span data-ttu-id="e2050-132">Klicka på **Försäljning och marknadsföring** \> **Returorder** \> **Alla returorder** \> **Alla försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="e2050-132">Click **Sales and marketing** \> **Common** \> **Return orders** \> **All return orders**.</span></span> <span data-ttu-id="e2050-133">Skapa en ny returorder eller öppna returordern från listan.</span><span class="sxs-lookup"><span data-stu-id="e2050-133">Create a new return order or open the return order from the list.</span></span> <span data-ttu-id="e2050-134">På snabbfliken **Rader**, välj returorderrad.</span><span class="sxs-lookup"><span data-stu-id="e2050-134">On the **Lines** FastTab, select the return order line.</span></span> <span data-ttu-id="e2050-135">Klicka på **uppdatera**, och klicka sedan på **registrering**.</span><span class="sxs-lookup"><span data-stu-id="e2050-135">Click **Update line**, and then click **Registration**.</span></span>

2.  <span data-ttu-id="e2050-136">Tilldela en dispositionskod i fältet **Dispositionskod** och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="e2050-136">Assign a disposition code in the **Disposition code** field, and then click **OK**.</span></span>
    

    > [!NOTE]
    > <P><span data-ttu-id="e2050-137">Det går inte att skicka artikeln för inspektion som en karantänorder med hjälp av formuläret <STRONG>Registrering</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="e2050-137">It is not possible to send the item for inspection as a quarantine order using the <STRONG>Registration</STRONG> form.</span></span></P>



3.  <span data-ttu-id="e2050-138">I rutnätet **transaktioner**, välj den transaktion som ska registreras.</span><span class="sxs-lookup"><span data-stu-id="e2050-138">In the **Transactions** grid, select the transaction to be registered.</span></span>

4.  <span data-ttu-id="e2050-139">I rutnätet **registrera nu** klickar du på **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="e2050-139">In the **Register now** grid, click **Add**.</span></span> <span data-ttu-id="e2050-140">Upprepa de tidigare två stegen tills alla returnerade artiklar visas i **Registrera nu**.</span><span class="sxs-lookup"><span data-stu-id="e2050-140">Repeat the previous two steps until all of the returned items appear in the **Register now** grid.</span></span>

5.  <span data-ttu-id="e2050-141">Klicka på **Bokför alla**</span><span class="sxs-lookup"><span data-stu-id="e2050-141">Click **Post all**.</span></span>

## <a name="see-also"></a><span data-ttu-id="e2050-142">Se även</span><span class="sxs-lookup"><span data-stu-id="e2050-142">See also</span></span>

<span data-ttu-id="e2050-143">[Införselöversikt (formulär)](https://technet.microsoft.com/en-us/library/hh227654\(v=ax.60\))</span><span class="sxs-lookup"><span data-stu-id="e2050-143">[Arrival overview (form)](https://technet.microsoft.com/en-us/library/hh227654\(v=ax.60\))</span></span>

  



