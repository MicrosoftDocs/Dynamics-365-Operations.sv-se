---
title: Skapa och bearbeta avvikelser
description: Detta ämne beskriver hur du utför avvikelsehantering baserat på en befintlig kvalitetsorder.
author: perlynne
ms.date: 03/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 06a56a694f7a80d65cb46d08744e78d8361cee3b
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956216"
---
# <a name="create-and-process-nonconformances"></a><span data-ttu-id="23b57-103">Skapa och bearbeta avvikelser</span><span class="sxs-lookup"><span data-stu-id="23b57-103">Create and process nonconformances</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="23b57-104">Detta ämne beskriver hur du utför avvikelsehantering baserat på en befintlig kvalitetsorder.</span><span class="sxs-lookup"><span data-stu-id="23b57-104">This topic describes how to perform nonconformance management based on an existing quality order.</span></span> <span data-ttu-id="23b57-105">Vanligtvis utförs avvikelsehanteringen av en kvalitetsansvarig.</span><span class="sxs-lookup"><span data-stu-id="23b57-105">Typically, nonconformance management is done by a quality clerk.</span></span> <span data-ttu-id="23b57-106">En förutsättning är att du har en kvalitetsorder tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="23b57-106">As a prerequisite, you must have a quality order available.</span></span> <span data-ttu-id="23b57-107">(Mer information om hur du skapar en kvalitetsorder finns i [Inspektera kvaliteten på varorna](inspect-quality-goods.md) .)</span><span class="sxs-lookup"><span data-stu-id="23b57-107">(For information about how to create a quality order, see [Inspect the quality of goods](inspect-quality-goods.md).)</span></span>

<span data-ttu-id="23b57-108">Innan en användare kan bearbeta godkännandet av en avvikelse måste han eller hon tilldelas en medarbetare i fältet **Person** på sidan **Användare**.</span><span class="sxs-lookup"><span data-stu-id="23b57-108">Before a user can process the approval of a nonconformance, a worker must be assigned to them in the **Person** field on the **Users** page.</span></span> <span data-ttu-id="23b57-109">Innan användaren kan använda dokumentnoteringarna måste alternativet **Aktivera dokumenthantering** dessutom ställas in på *Ja* bland användarens alternativ.</span><span class="sxs-lookup"><span data-stu-id="23b57-109">Additionally, before the user can use the document notes, the **Enable document handling** option must be set to *Yes* in their user options.</span></span>

## <a name="create-a-nonconformance"></a><span data-ttu-id="23b57-110">Skapa en avvikelse</span><span class="sxs-lookup"><span data-stu-id="23b57-110">Create a nonconformance</span></span>

<span data-ttu-id="23b57-111">Gör så här om du vill skapa en avvikelse.</span><span class="sxs-lookup"><span data-stu-id="23b57-111">To create a nonconformance, follow these steps.</span></span>

1. <span data-ttu-id="23b57-112">Gå till **Lagerhantering \> Periodiska uppgifter \> Kvalitetshantering \> Avvikelser**.</span><span class="sxs-lookup"><span data-stu-id="23b57-112">Go to **Inventory management \> Periodic tasks \> Quality management \> Non conformances**.</span></span>
1. <span data-ttu-id="23b57-113">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="23b57-113">On the Action pane, select **New**.</span></span>
1. <span data-ttu-id="23b57-114">I dialogrutan **Skapa avvikelse** väljer du i fältet **Problemtyp** den typ av problem som hittats i samband med inspektion.</span><span class="sxs-lookup"><span data-stu-id="23b57-114">In the **Create non conformance** dialog box, in **Problem type** field, select the type of problem that was found during the inspection process.</span></span>
1. <span data-ttu-id="23b57-115">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="23b57-115">Select **OK**.</span></span>

## <a name="approve-or-reject-a-nonconformance"></a><span data-ttu-id="23b57-116">Godkänn eller avvisa en avvikelse</span><span class="sxs-lookup"><span data-stu-id="23b57-116">Approve or reject a nonconformance</span></span>

<span data-ttu-id="23b57-117">Om du vill godkänna eller avvisa en avvikelse följer du dessa steg:</span><span class="sxs-lookup"><span data-stu-id="23b57-117">To approve or reject a nonconformance, follow these steps.</span></span>

1. <span data-ttu-id="23b57-118">Gå till **Lagerhantering \> Periodiska uppgifter \> Kvalitetshantering \> Avvikelser**.</span><span class="sxs-lookup"><span data-stu-id="23b57-118">Go to **Inventory management \> Periodic tasks \> Quality management \> Non conformances**.</span></span>
1. <span data-ttu-id="23b57-119">Markera den avvikelse som du vill uppdatera i listan.</span><span class="sxs-lookup"><span data-stu-id="23b57-119">In the list, select the nonconformance that you want to update.</span></span>

    > [!NOTE]
    > <span data-ttu-id="23b57-120">Du kan bara lägga till en korrigering för avvikelser som är godkända.</span><span class="sxs-lookup"><span data-stu-id="23b57-120">You can add a correction only to nonconformances that are approved.</span></span>

1. <span data-ttu-id="23b57-121">I åtgärdsfönstret väljer du **Funktioner \> Godkänn en avvikelse** om du vill godkänna avvikelsen, eller **Funktioner \> Vägra avvikelse** om du vill avisa den.</span><span class="sxs-lookup"><span data-stu-id="23b57-121">On the Action Pane, select **Functions \> Approve non conformance** to approve the nonconformance or **Functions \> Refuse non conformance** to reject it.</span></span> <span data-ttu-id="23b57-122">Du kan koppla godkända avvikelser till [relaterade funktioner](../quality-operations.md).</span><span class="sxs-lookup"><span data-stu-id="23b57-122">You can associate approved nonconformances with [related operations](../quality-operations.md).</span></span> <span data-ttu-id="23b57-123">På det här sättet kan du registrera arbete som utförs som en del av avvikelsehanteringen och bearbetningen av korrigeringshanteringen.</span><span class="sxs-lookup"><span data-stu-id="23b57-123">In this way, you can record work that is done as part of the nonconformance handling and the processing of correction handling.</span></span>
1. <span data-ttu-id="23b57-124">Du uppmanas att bekräfta ditt val.</span><span class="sxs-lookup"><span data-stu-id="23b57-124">You're prompted to confirm your selection.</span></span> <span data-ttu-id="23b57-125">Klicka på **Ja** när du vill fortsätta.</span><span class="sxs-lookup"><span data-stu-id="23b57-125">Select **Yes** to continue.</span></span>

## <a name="add-operations-and-other-details-to-nonconformances"></a><span data-ttu-id="23b57-126">Lägg till åtgärder och annan information till avvikelser</span><span class="sxs-lookup"><span data-stu-id="23b57-126">Add operations and other details to nonconformances</span></span>

<span data-ttu-id="23b57-127">När du har skapat en avvikelse kan du börja lägga till relaterade åtgärder och ange ytterligare information om dessa åtgärder.</span><span class="sxs-lookup"><span data-stu-id="23b57-127">After you've created a nonconformance, you can start to add related operations and specify additional information about those operations.</span></span> <span data-ttu-id="23b57-128">Du kan bara lägga till relaterade funktioner för avvikelser som är godkända.</span><span class="sxs-lookup"><span data-stu-id="23b57-128">You can add related operations only to nonconformances that are approved.</span></span>

<span data-ttu-id="23b57-129">Förutom den grundläggande informationen kan du lägga till följande information till en funktion:</span><span class="sxs-lookup"><span data-stu-id="23b57-129">Besides the basic information, you can add the following details to an operation:</span></span>

- <span data-ttu-id="23b57-130">**Artiklar** – Du kan skapa en lista över artiklar som förbrukas för att utföra korrigeringen.</span><span class="sxs-lookup"><span data-stu-id="23b57-130">**Items** – You can create a list of items that are consumed to perform the correction.</span></span> <span data-ttu-id="23b57-131">Artiklarna kan till exempel vara produkter som krävs för att reparera utrustning eller ingredienser som krävs för att omarbeta en färdig produkt.</span><span class="sxs-lookup"><span data-stu-id="23b57-131">For example, the items might be products that are required to repair equipment or ingredients that are required to rework a finished product.</span></span>
- <span data-ttu-id="23b57-132">**Kvalitetsavgifter** – Du kan skapa en lista med avgifter som uppstår eller debiteras externa källor.</span><span class="sxs-lookup"><span data-stu-id="23b57-132">**Quality charges** – You can create a list of charges that are incurred or billed out to external sources.</span></span>
- <span data-ttu-id="23b57-133">**Tidrapport** – Du kan skapa en logg över den tid som varje medarbetare ägnar åt funktionen.</span><span class="sxs-lookup"><span data-stu-id="23b57-133">**Timesheet** – You can create a log of the time that each worker spends on the operation.</span></span>

<span data-ttu-id="23b57-134">De återstående inställningarna är valfria.</span><span class="sxs-lookup"><span data-stu-id="23b57-134">The remaining settings are optional.</span></span> <span data-ttu-id="23b57-135">Kostnaden för respektive artikel, kvalitetsavgifter och tidrapporten summeras och visas i funktionen.</span><span class="sxs-lookup"><span data-stu-id="23b57-135">The cost for each item, quality charges, and the timesheet are summed and shown on the operation.</span></span> <span data-ttu-id="23b57-136">Du kan inte redigera fältet **Kostnad** direkt i funktionen.</span><span class="sxs-lookup"><span data-stu-id="23b57-136">You can't directly edit the **Cost** field on the operation.</span></span>

### <a name="create-an-operation-for-a-nonconformance"></a><span data-ttu-id="23b57-137">Skapa en funktion för en avvikelse</span><span class="sxs-lookup"><span data-stu-id="23b57-137">Create an operation for a nonconformance</span></span>

<span data-ttu-id="23b57-138">Gör så här om du vill skapa en funktion för en avvikelse:</span><span class="sxs-lookup"><span data-stu-id="23b57-138">To create an operation for a nonconformance, follow these steps.</span></span>

1. <span data-ttu-id="23b57-139">Gå till **Lagerhantering \> Periodiska uppgifter \> Kvalitetshantering \> Avvikelser**.</span><span class="sxs-lookup"><span data-stu-id="23b57-139">Go to **Inventory management \> Periodic tasks \> Quality management \> Non conformances**.</span></span>
1. <span data-ttu-id="23b57-140">Markera den avvikelse som du vill uppdatera i listan.</span><span class="sxs-lookup"><span data-stu-id="23b57-140">In the list, select the nonconformance that you want to update.</span></span>

    > [!NOTE]
    > <span data-ttu-id="23b57-141">Du kan bara lägga till eller uppdatera funktioner för avvikelser som är godkända.</span><span class="sxs-lookup"><span data-stu-id="23b57-141">You can add or update operations only for nonconformances that are approved.</span></span>

1. <span data-ttu-id="23b57-142">Klicka på **Relaterade funktioner** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="23b57-142">On the Action Pane, select **Related operations**.</span></span>
1. <span data-ttu-id="23b57-143">På sidan **Relaterade funktioner** väljer du i åtgärdsfönstret **Ny** för att lägga till en rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="23b57-143">On the **Related operations** page, on the Action pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="23b57-144">Ange sedan följande fält för den nya raden:</span><span class="sxs-lookup"><span data-stu-id="23b57-144">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="23b57-145">**Åtgärd** – Välj koden för den åtgärd som ska utföras för avvikelsen.</span><span class="sxs-lookup"><span data-stu-id="23b57-145">**Operation** – Select the code of the operation that will be performed for the nonconformance.</span></span>
    - <span data-ttu-id="23b57-146">**Orsak** – Ange en detaljerad beskrivning som förklarar varför funktionen behövs.</span><span class="sxs-lookup"><span data-stu-id="23b57-146">**Reason** – Enter a detailed description that explains why the operation is required.</span></span>
    - <span data-ttu-id="23b57-147">**Försäljningsorder** – Om den valda funktionskoden är relaterad till försäljningsordertypen ska du välja den försäljningsorder som du kopplar funktionen till.</span><span class="sxs-lookup"><span data-stu-id="23b57-147">**Sales order** – If the selected operation code is related to the sales order type, select the sales order that you're linking the operation to.</span></span>
    - <span data-ttu-id="23b57-148">**Inköpsorder** – Om den valda funktionskoden är relaterad till inköpsordertypen ska du välja den inköpsorder som du kopplar funktionen till.</span><span class="sxs-lookup"><span data-stu-id="23b57-148">**Purchase order** – If the selected operation code is related to the purchase order type, select the purchase order that you're linking the operation to.</span></span>

1. <span data-ttu-id="23b57-149">Stäng sidorna.</span><span class="sxs-lookup"><span data-stu-id="23b57-149">Close the pages.</span></span>

### <a name="add-items-to-an-operation"></a><span data-ttu-id="23b57-150">Lägga till artiklar i en funktion</span><span class="sxs-lookup"><span data-stu-id="23b57-150">Add items to an operation</span></span>

<span data-ttu-id="23b57-151">Följ de här stegen om du vill lägga till artiklar i en funktion.</span><span class="sxs-lookup"><span data-stu-id="23b57-151">To add items to an operation, follow these steps.</span></span>

1. <span data-ttu-id="23b57-152">Gå till **Lagerhantering \> Periodiska uppgifter \> Kvalitetshantering \> Avvikelser**.</span><span class="sxs-lookup"><span data-stu-id="23b57-152">Go to **Inventory management \> Periodic tasks \> Quality management \> Non conformances**.</span></span>
1. <span data-ttu-id="23b57-153">Markera den avvikelse som du vill uppdatera i listan.</span><span class="sxs-lookup"><span data-stu-id="23b57-153">In the list, select the nonconformance that you want to update.</span></span>

    > [!NOTE]
    > <span data-ttu-id="23b57-154">Du kan bara lägga till eller uppdatera funktioner för avvikelser som är godkända.</span><span class="sxs-lookup"><span data-stu-id="23b57-154">You can add or update operations only for nonconformances that are approved.</span></span>

1. <span data-ttu-id="23b57-155">Klicka på **Relaterade funktioner** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="23b57-155">On the Action Pane, select **Related operations**.</span></span>
1. <span data-ttu-id="23b57-156">På sidan **Relaterade åtgärder** markerar du den funktion som du vill lägga till artiklar i.</span><span class="sxs-lookup"><span data-stu-id="23b57-156">On the **Related operations** page, select the operation that you want to add items to.</span></span>
1. <span data-ttu-id="23b57-157">Klicka på **Artiklar** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="23b57-157">On the Action Pane, select **Items**.</span></span>
1. <span data-ttu-id="23b57-158">På sidan **Relaterade funktioner** väljer du i åtgärdsfönstret **Ny** för att lägga till en rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="23b57-158">On the **Related operations** page, on the Action pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="23b57-159">Ange sedan följande fält för den nya raden:</span><span class="sxs-lookup"><span data-stu-id="23b57-159">Then set the following fields for new row:</span></span>

    - <span data-ttu-id="23b57-160">**Artikelnummer** – Välj den produkt som ska förbrukas under den markerade funktionen.</span><span class="sxs-lookup"><span data-stu-id="23b57-160">**Item number** – Select the product that will be consumed as part of the selected operation.</span></span>
    - <span data-ttu-id="23b57-161">**Kvantitet** – Ange antalet artiklar som ska förbrukas.</span><span class="sxs-lookup"><span data-stu-id="23b57-161">**Quantity** – Enter the number of items that will be consumed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="23b57-162">Du kan visa kostnaden för artikeln i fältet **Kostnad** på fliken **Allmänt**. Kostnaden som visas kommer från kostnaden som ställs in på sidan **Frisläppt produkt**.</span><span class="sxs-lookup"><span data-stu-id="23b57-162">You can view the cost for the item in the **Cost** field on the **General** tab. The cost that is shown there comes from the cost that is set up on the **Released product** page.</span></span> <span data-ttu-id="23b57-163">Kostnaden kan inte uppdateras direkt på sidan **Relaterad funktionsartikel**.</span><span class="sxs-lookup"><span data-stu-id="23b57-163">The cost can't be updated directly on the **Related operation item** page.</span></span> <span data-ttu-id="23b57-164">Kostnaden för alla artiklar som läggs till på sidan **Relaterade funktionsartiklar** läggs till automatiskt i fältet **avgift** på sidan **Relaterade funktioner**.</span><span class="sxs-lookup"><span data-stu-id="23b57-164">The cost of all items that are added on the **Related operation items** page is automatically added to the **Cost** field on the **Related operations** page.</span></span>

1. <span data-ttu-id="23b57-165">Upprepa föregående steg för varje ytterligare artikel som du måste lägga till.</span><span class="sxs-lookup"><span data-stu-id="23b57-165">Repeat the previous step for each additional item that you must add.</span></span>
1. <span data-ttu-id="23b57-166">Stäng sidorna.</span><span class="sxs-lookup"><span data-stu-id="23b57-166">Close the pages.</span></span>

### <a name="add-quality-charges-to-an-operation"></a><span data-ttu-id="23b57-167">Lägg till kvalitetsavgifter för en funktion</span><span class="sxs-lookup"><span data-stu-id="23b57-167">Add quality charges to an operation</span></span>

<span data-ttu-id="23b57-168">Följ de här stegen om du vill lägga till kvalitetsavgifter i en funktion.</span><span class="sxs-lookup"><span data-stu-id="23b57-168">To add quality charges to an operation, follow these steps.</span></span>

1. <span data-ttu-id="23b57-169">Gå till **Lagerhantering \> Periodiska uppgifter \> Kvalitetshantering \> Avvikelser**.</span><span class="sxs-lookup"><span data-stu-id="23b57-169">Go to **Inventory management \> Periodic tasks \> Quality management \> Non conformances**.</span></span>
1. <span data-ttu-id="23b57-170">Markera den avvikelse som du vill uppdatera i listan.</span><span class="sxs-lookup"><span data-stu-id="23b57-170">In the list, select the nonconformance that you want to update.</span></span>

    > [!NOTE]
    > <span data-ttu-id="23b57-171">Du kan bara lägga till eller uppdatera funktioner för avvikelser som är godkända.</span><span class="sxs-lookup"><span data-stu-id="23b57-171">You can add or update operations only for nonconformances that are approved.</span></span>

1. <span data-ttu-id="23b57-172">Klicka på **Relaterade funktioner** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="23b57-172">On the Action Pane, select **Related operations**.</span></span>
1. <span data-ttu-id="23b57-173">På sidan **Relaterade funktioner** markerar du den funktion som du vill lägga till kvalitetsavgifter i.</span><span class="sxs-lookup"><span data-stu-id="23b57-173">On the **Related operations** page, select the operation that you want to add quality charges to.</span></span>
1. <span data-ttu-id="23b57-174">Välj **Kvalitetsavgifter** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="23b57-174">On the Action Pane, select **Quality charges**.</span></span>
1. <span data-ttu-id="23b57-175">På sidan **Relaterade funktionsavgifter** väljer du i åtgärdsfönstret **Ny** för att lägga till en rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="23b57-175">On the **Related operation charges** page, on the Action pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="23b57-176">Ange sedan följande fält för den nya raden:</span><span class="sxs-lookup"><span data-stu-id="23b57-176">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="23b57-177">**Debiteringskod** – Välj den kvalitetsavgift som du vill lägga till.</span><span class="sxs-lookup"><span data-stu-id="23b57-177">**Charges code** – Select the quality charge that you want to add.</span></span>
    - <span data-ttu-id="23b57-178">**Beskrivning** – Ange en detaljerad beskrivning av avgiften.</span><span class="sxs-lookup"><span data-stu-id="23b57-178">**Description** – Enter a detailed description of the charge.</span></span>
    - <span data-ttu-id="23b57-179">**avgiftsvärde** – Ange avgiftsbeloppet.</span><span class="sxs-lookup"><span data-stu-id="23b57-179">**Charges value** – Enter the amount of the charge.</span></span>

1. <span data-ttu-id="23b57-180">Upprepa föregående steg för varje ytterligare avgift som du måste lägga till.</span><span class="sxs-lookup"><span data-stu-id="23b57-180">Repeat the previous step for each additional charge that you must add.</span></span>
1. <span data-ttu-id="23b57-181">Stäng sidorna.</span><span class="sxs-lookup"><span data-stu-id="23b57-181">Close the pages.</span></span>

> [!NOTE]
> <span data-ttu-id="23b57-182">Beloppet i fältet **Avgiftsvärde** summeras automatiskt för samtliga kvalitetsavgifter och adderas till alla andra eventuella belopp i fältet **Kostnad** på sidan **Relaterade funktioner**.</span><span class="sxs-lookup"><span data-stu-id="23b57-182">The amount in the **Charges value** field is automatically summed for all quality charges and added to any other amounts in the **Cost** field on the **Related operations** page.</span></span>

### <a name="create-a-timesheet-on-an-operation"></a><span data-ttu-id="23b57-183">Skapa en tidrapport för en funktion</span><span class="sxs-lookup"><span data-stu-id="23b57-183">Create a timesheet on an operation</span></span>

<span data-ttu-id="23b57-184">Följ de här stegen om du vill lägga till en tidrapport i en funktion.</span><span class="sxs-lookup"><span data-stu-id="23b57-184">To add a timesheet to an operation, follow these steps.</span></span>

1. <span data-ttu-id="23b57-185">Gå till **Lagerhantering \> Periodiska uppgifter \> Kvalitetshantering \> Avvikelser**.</span><span class="sxs-lookup"><span data-stu-id="23b57-185">Go to **Inventory management \> Periodic tasks \> Quality management \> Non conformances**.</span></span>
1. <span data-ttu-id="23b57-186">Markera den avvikelse som du vill uppdatera i listan.</span><span class="sxs-lookup"><span data-stu-id="23b57-186">In the list, select the nonconformance that you want to update.</span></span>

    > [!NOTE]
    > <span data-ttu-id="23b57-187">Du kan bara lägga till eller uppdatera funktioner för avvikelser som är godkända.</span><span class="sxs-lookup"><span data-stu-id="23b57-187">You can add or update operations only for nonconformances that are approved.</span></span>

1. <span data-ttu-id="23b57-188">Klicka på **Relaterade funktioner** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="23b57-188">On the Action Pane, select **Related operations**.</span></span>
1. <span data-ttu-id="23b57-189">På sidan **Relaterade funktioner** markerar du den funktion som du vill lägga till en tidrapport i.</span><span class="sxs-lookup"><span data-stu-id="23b57-189">On the **Related operations** page, select the operation that you want to add a timesheet to.</span></span>
1. <span data-ttu-id="23b57-190">Klicka på **Tidrapport** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="23b57-190">On the Action Pane, select **Timesheet**.</span></span>
1. <span data-ttu-id="23b57-191">På sidan **Relaterade funktionstidrapporter** väljer du i åtgärdsfönstret **Ny** för att kunna lägga till en rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="23b57-191">On the **Related operation time sheets** page, on the Action pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="23b57-192">Ange sedan följande fält för den nya raden:</span><span class="sxs-lookup"><span data-stu-id="23b57-192">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="23b57-193">**Datum** – Ange det datum då arbetet utfördes.</span><span class="sxs-lookup"><span data-stu-id="23b57-193">**Date** – Specify the date when work was done.</span></span> <span data-ttu-id="23b57-194">Som standard är detta fält inställt på det aktuella datumet.</span><span class="sxs-lookup"><span data-stu-id="23b57-194">By default, this field is set to the current date.</span></span>
    - <span data-ttu-id="23b57-195">**Medarbetare** – Välj den medarbetare som utfört arbetet.</span><span class="sxs-lookup"><span data-stu-id="23b57-195">**Worker** – Select the worker who did the work.</span></span> <span data-ttu-id="23b57-196">Som standard ställs det här fältet in på den medarbetare som tilldelats den aktuella användaren.</span><span class="sxs-lookup"><span data-stu-id="23b57-196">By default, this field is set to the worker that is assigned to the current user.</span></span>
    - <span data-ttu-id="23b57-197">**Funktionstimmar** – Ange antalet timmar som har arbete pågick på den valda funktionen.</span><span class="sxs-lookup"><span data-stu-id="23b57-197">**Operation hours** – Enter the number of hours that were worked on the selected operation.</span></span>
    - <span data-ttu-id="23b57-198">**Fakturerades** – Markera den här kryssrutan om tiden har debiterats en kund eller leverantör på en faktura.</span><span class="sxs-lookup"><span data-stu-id="23b57-198">**Invoiced** – Select this check box if the time has been charged to a customer or vendor on an invoice.</span></span>

    > [!NOTE]
    > <span data-ttu-id="23b57-199">Du kan visa kostnaden i fältet **Kostnad** på fliken **Allmänt**. Kostnaden beräknas med den kurs som du definierar på sidan **Lagerhanteringsparametrar**.</span><span class="sxs-lookup"><span data-stu-id="23b57-199">You can view the cost in the **Cost** field on the **General** tab. The cost is calculated by using the rate that you define on the **Inventory management parameters** page.</span></span>

1. <span data-ttu-id="23b57-200">Upprepa föregående steg för varje ytterligare tidrapportrad som du måste lägga till.</span><span class="sxs-lookup"><span data-stu-id="23b57-200">Repeat the previous step for each additional timesheet line that you must add.</span></span>
1. <span data-ttu-id="23b57-201">Stäng sidorna.</span><span class="sxs-lookup"><span data-stu-id="23b57-201">Close the pages.</span></span>

> [!NOTE]
> <span data-ttu-id="23b57-202">Beloppet i fältet **Kostnad** summeras automatiskt för samtliga tidrapportrader och adderas till alla andra eventuella belopp i fältet **Kostnad** på sidan **Relaterade funktioner**.</span><span class="sxs-lookup"><span data-stu-id="23b57-202">The amount in the **Cost** field is summed for all timesheet lines and added to any other amounts in the **Cost** field on the **Related operations** page.</span></span>

## <a name="add-a-correction-to-a-nonconformance"></a><span data-ttu-id="23b57-203">Lägg till en korrigering av en avvikelse</span><span class="sxs-lookup"><span data-stu-id="23b57-203">Add a correction to a nonconformance</span></span>

<span data-ttu-id="23b57-204">Om du vill lägga till en korrigering i en avvikelse gör du följande:</span><span class="sxs-lookup"><span data-stu-id="23b57-204">To add a correction to a nonconformance, follow these steps.</span></span>

1. <span data-ttu-id="23b57-205">Gå till **Lagerhantering \> Periodiska uppgifter \> Kvalitetshantering \> Avvikelser**.</span><span class="sxs-lookup"><span data-stu-id="23b57-205">Go to **Inventory management \> Periodic tasks \> Quality management \> Non conformances**.</span></span>
1. <span data-ttu-id="23b57-206">Markera den avvikelse som du vill uppdatera i listan.</span><span class="sxs-lookup"><span data-stu-id="23b57-206">In the list, select the nonconformance that you want to update.</span></span>

    > [!NOTE]
    > <span data-ttu-id="23b57-207">Du kan bara lägga till en korrigering för avvikelser som är godkända.</span><span class="sxs-lookup"><span data-stu-id="23b57-207">You can add a correction only to nonconformances that are approved.</span></span>

1. <span data-ttu-id="23b57-208">I åtgärdsfönstret väljer du **Korrigeringar**.</span><span class="sxs-lookup"><span data-stu-id="23b57-208">On the Action Pane, select **Corrections**.</span></span>
1. <span data-ttu-id="23b57-209">I åtgärdsfönstret på sidan **Korrigeringar** väljer du **Ny** för att lägga till en rad i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="23b57-209">On the **Corrections** page, on the Action Pane, select **New** to add a row to the grid.</span></span> <span data-ttu-id="23b57-210">Ange sedan följande fält för den nya raden:</span><span class="sxs-lookup"><span data-stu-id="23b57-210">Then set the following fields for the new row:</span></span>

    - <span data-ttu-id="23b57-211">**Diagnos** – Välj den diagnostyp som identifierar den typ av korrigering som du skapar.</span><span class="sxs-lookup"><span data-stu-id="23b57-211">**Diagnostic** – Select the diagnostic type that identifies the type of correction that you're creating.</span></span>
    - <span data-ttu-id="23b57-212">**Medarbetare** – Välj den person som är ansvarig för korrigeringen.</span><span class="sxs-lookup"><span data-stu-id="23b57-212">**Worker** – Select the person who is responsible for the correction.</span></span>
    - <span data-ttu-id="23b57-213">**Korrigeringsprioritet** – Välj ett alternativ för att ange hur korrigeringen ska prioriteras (*Låg*, *Normal* eller *Hög*).</span><span class="sxs-lookup"><span data-stu-id="23b57-213">**Correction priority** – Select an option to indicate how the correction should be prioritized (*Low*, *Normal*, or *High*).</span></span>
    - <span data-ttu-id="23b57-214">**Begärt datum** – Ange det datum då korrigeringsåtgärden begärdes.</span><span class="sxs-lookup"><span data-stu-id="23b57-214">**Requested date** – Enter the date when the corrective action was requested.</span></span>
    - <span data-ttu-id="23b57-215">**Planerat datum** – Ange det datum då korrigeringen förväntas vara slutförd.</span><span class="sxs-lookup"><span data-stu-id="23b57-215">**Planned date** – Enter the date when the correction is expected to be completed.</span></span>
    - <span data-ttu-id="23b57-216">**Kortsiktig lösning** – Markera den här kryssrutan om korrigeringsåtgärden endast korrigerar avvikelsen under en kort tid.</span><span class="sxs-lookup"><span data-stu-id="23b57-216">**Short term solution** – Select this check box if the corrective action corrects the nonconformance only for a short time.</span></span>

1. <span data-ttu-id="23b57-217">Stäng sidorna.</span><span class="sxs-lookup"><span data-stu-id="23b57-217">Close the pages.</span></span>

## <a name="mark-a-correction-as-completed"></a><span data-ttu-id="23b57-218">Markera en korrigering som slutförd</span><span class="sxs-lookup"><span data-stu-id="23b57-218">Mark a correction as completed</span></span>

<span data-ttu-id="23b57-219">Om du vill markera en avvikelse som slutförd gör du följande:</span><span class="sxs-lookup"><span data-stu-id="23b57-219">To mark a nonconformance correction as completed, follow these steps.</span></span>

1. <span data-ttu-id="23b57-220">Gå till **Lagerhantering \> Periodiska uppgifter \> Kvalitetshantering \> Avvikelser**.</span><span class="sxs-lookup"><span data-stu-id="23b57-220">Go to **Inventory management \> Periodic tasks \> Quality management \> Non conformances**.</span></span>
1. <span data-ttu-id="23b57-221">Markera den avvikelse som du vill uppdatera i listan.</span><span class="sxs-lookup"><span data-stu-id="23b57-221">In the list, select the nonconformance that you want to update.</span></span>

    > [!NOTE]
    > <span data-ttu-id="23b57-222">Du kan bara lägga till en korrigering för avvikelser som är godkända.</span><span class="sxs-lookup"><span data-stu-id="23b57-222">You can add a correction only to nonconformances that are approved.</span></span>

1. <span data-ttu-id="23b57-223">I åtgärdsfönstret väljer du **Korrigeringar**.</span><span class="sxs-lookup"><span data-stu-id="23b57-223">On the Action Pane, select **Corrections**.</span></span>
1. <span data-ttu-id="23b57-224">På sidan **Korrigeringar** i rutnätet väljer du den korrigering som du vill markera som slutförd.</span><span class="sxs-lookup"><span data-stu-id="23b57-224">On the **Corrections** page, in the grid, select the correction that you want to mark as completed.</span></span>
1. <span data-ttu-id="23b57-225">Välj **Markera som slutförd** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="23b57-225">On the Action Pane, select **Mark complete**.</span></span>
1. <span data-ttu-id="23b57-226">Du uppmanas att bekräfta ditt val.</span><span class="sxs-lookup"><span data-stu-id="23b57-226">You're prompted to confirm your selection.</span></span> <span data-ttu-id="23b57-227">Välj **OK** om du vill fortsätta.</span><span class="sxs-lookup"><span data-stu-id="23b57-227">Select **OK** to continue.</span></span> <span data-ttu-id="23b57-228">**Slutförandedatum och -tid** ställs in på aktuellt datum och aktuell tid, och kryssrutan **Slutförd** markeras.</span><span class="sxs-lookup"><span data-stu-id="23b57-228">The **Completion date and time** field is set to the current date and time, and the **Completed** check box is selected.</span></span>
1. <span data-ttu-id="23b57-229">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="23b57-229">Close the page.</span></span>

## <a name="reopen-a-completed-correction"></a><span data-ttu-id="23b57-230">Öppna upp en slutförd korrigering på nytt</span><span class="sxs-lookup"><span data-stu-id="23b57-230">Reopen a completed correction</span></span>

<span data-ttu-id="23b57-231">Gör så här om du vill öppna upp en slutförd korrigering på nytt:</span><span class="sxs-lookup"><span data-stu-id="23b57-231">To reopen a completed correction, follow these steps.</span></span>

1. <span data-ttu-id="23b57-232">Gå till **Lagerhantering \> Periodiska uppgifter \> Kvalitetshantering \> Avvikelser**.</span><span class="sxs-lookup"><span data-stu-id="23b57-232">Go to **Inventory management \> Periodic tasks \> Quality management \> Non conformances**.</span></span>
1. <span data-ttu-id="23b57-233">Markera den avvikelse som du vill uppdatera i listan.</span><span class="sxs-lookup"><span data-stu-id="23b57-233">In the list, select the nonconformance that you want to update.</span></span>
1. <span data-ttu-id="23b57-234">I åtgärdsfönstret väljer du **Korrigeringar**.</span><span class="sxs-lookup"><span data-stu-id="23b57-234">On the Action pane, select **Corrections**.</span></span>
1. <span data-ttu-id="23b57-235">På sidan **Korrigeringar** i rutnätet väljer du den korrigering som du vill öppna på nytt.</span><span class="sxs-lookup"><span data-stu-id="23b57-235">On the **Corrections** page, in the grid, select the correction that you want to reopen.</span></span>
1. <span data-ttu-id="23b57-236">Välj **Öppna på nytt** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="23b57-236">On the Action Pane, select **Reopen**.</span></span>
1. <span data-ttu-id="23b57-237">Du uppmanas att bekräfta ditt val.</span><span class="sxs-lookup"><span data-stu-id="23b57-237">You're prompted to confirm your selection.</span></span> <span data-ttu-id="23b57-238">Välj **OK** om du vill fortsätta.</span><span class="sxs-lookup"><span data-stu-id="23b57-238">Select **OK** to continue.</span></span> <span data-ttu-id="23b57-239">Värdet rensas från fältet **Slutförandedatum och -tid**, och kryssrutan **Slutförd** avmarkeras.</span><span class="sxs-lookup"><span data-stu-id="23b57-239">The value is cleared from the **Completion date and time** field, and the **Completed** check box is cleared.</span></span>
1. <span data-ttu-id="23b57-240">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="23b57-240">Close the page.</span></span>

<span data-ttu-id="23b57-241">Du kan nu göra ytterligare redigeringar eller uppdateringar av korrigeringen.</span><span class="sxs-lookup"><span data-stu-id="23b57-241">You can now make additional edits or updates to the correction.</span></span> <span data-ttu-id="23b57-242">När du är klar kan du markera korrigeringen som slutförd igen.</span><span class="sxs-lookup"><span data-stu-id="23b57-242">When you've finished, you can mark the correction as completed again.</span></span>

## <a name="close-a-nonconformance"></a><span data-ttu-id="23b57-243">Stäng en avvikelse</span><span class="sxs-lookup"><span data-stu-id="23b57-243">Close a nonconformance</span></span>

<span data-ttu-id="23b57-244">Gör så här om du vill stänga en avvikelse.</span><span class="sxs-lookup"><span data-stu-id="23b57-244">To close a nonconformance, follow these steps.</span></span>

1. <span data-ttu-id="23b57-245">Gå till **Lagerhantering \> Periodiska uppgifter \> Kvalitetshantering \> Kvalitetsorder**.</span><span class="sxs-lookup"><span data-stu-id="23b57-245">Go to **Inventory management \> Periodic tasks \> Quality management \> Quality orders**.</span></span>
1. <span data-ttu-id="23b57-246">Välj en kvalitetsorder i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="23b57-246">Select a quality order in the grid.</span></span>
1. <span data-ttu-id="23b57-247">I åtgärdsfönstret väljer du **Frågor \> Avvikelser**.</span><span class="sxs-lookup"><span data-stu-id="23b57-247">On the Action Pane, select **Inquiries \> Non conformances**.</span></span>
1. <span data-ttu-id="23b57-248">På sidan **Avvikelser** markerar du avsedd avvikelse i rutnätet.</span><span class="sxs-lookup"><span data-stu-id="23b57-248">On the **Non conformances** page, select the target nonconformance in the grid.</span></span>
1. <span data-ttu-id="23b57-249">I åtgärdsfönstret väljer du **Funktioner \> Stäng avvikelse**.</span><span class="sxs-lookup"><span data-stu-id="23b57-249">On the Action Pane, select **Functions \> Close non conformance**.</span></span>
1. <span data-ttu-id="23b57-250">Du uppmanas att bekräfta ditt val.</span><span class="sxs-lookup"><span data-stu-id="23b57-250">You're prompted to confirm your selection.</span></span> <span data-ttu-id="23b57-251">Klicka på **Ja** när du vill fortsätta.</span><span class="sxs-lookup"><span data-stu-id="23b57-251">Select **Yes** to continue.</span></span>
1. <span data-ttu-id="23b57-252">Stäng sidorna.</span><span class="sxs-lookup"><span data-stu-id="23b57-252">Close the pages.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="23b57-253">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="23b57-253">Additional resources</span></span>

- [<span data-ttu-id="23b57-254">Kvalitetshantering – översikt</span><span class="sxs-lookup"><span data-stu-id="23b57-254">Quality management overview</span></span>](../quality-management-processes.md)
- [<span data-ttu-id="23b57-255">Aktivera kvalitets- och avvikelsehantering</span><span class="sxs-lookup"><span data-stu-id="23b57-255">Enable quality and nonconformance management</span></span>](../enable-quality-management.md)
- [<span data-ttu-id="23b57-256">Medarbetare som ansvarar för godkännande av avvikelse</span><span class="sxs-lookup"><span data-stu-id="23b57-256">Workers responsible for approving nonconformances</span></span>](../quality-responsible-workers.md)
- [<span data-ttu-id="23b57-257">Karantänzoner för avvikelser</span><span class="sxs-lookup"><span data-stu-id="23b57-257">Quarantine zones for nonconformances</span></span>](../quality-quarantine-zones.md)
- [<span data-ttu-id="23b57-258">Diagnostyper för avvikelser</span><span class="sxs-lookup"><span data-stu-id="23b57-258">Diagnostic types for nonconformances</span></span>](../quality-diagnostic-types.md)
- [<span data-ttu-id="23b57-259">Kvalitetsavgifter avvikelser</span><span class="sxs-lookup"><span data-stu-id="23b57-259">Quality charges for nonconformances</span></span>](../quality-charges.md)
- [<span data-ttu-id="23b57-260">Funktioner för avvikelser</span><span class="sxs-lookup"><span data-stu-id="23b57-260">Operations for nonconformances</span></span>](../quality-operations.md)
- [<span data-ttu-id="23b57-261">Kvalitetsstyrning för lagerprocesser</span><span class="sxs-lookup"><span data-stu-id="23b57-261">Quality management for warehouse processes</span></span>](../quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
