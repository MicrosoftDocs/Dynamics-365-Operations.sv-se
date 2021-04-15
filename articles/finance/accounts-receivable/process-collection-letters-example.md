---
title: Exempel på bearbeta kravbrev
description: I detta avsnitt finns ett exempel som visar processen med att skapa, skriva ut och bokföra kravbrev.
author: JodiChristiansen
manager: AnnBe
ms.date: 02/03/2021
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPosting, CustCollectionLetterNote
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-02-03
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: df4252513f9e3a02632561b4e465c98edc888ea7
ms.sourcegitcommit: 4ecc1bf82fbb04882d7ef5e1994ef3c07ef953dc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/08/2021
ms.locfileid: "5558321"
---
# <a name="process-collection-letters-example"></a><span data-ttu-id="d5d15-103">Exempel på bearbeta kravbrev</span><span class="sxs-lookup"><span data-stu-id="d5d15-103">Process collection letters example</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d5d15-104">I detta avsnitt finns ett exempel som visar processen med att skapa, skriva ut och bokföra kravbrev.</span><span class="sxs-lookup"><span data-stu-id="d5d15-104">This topic goes through an example that shows the process of creating, printing, and posting collection letters.</span></span> <span data-ttu-id="d5d15-105">Exemplet baseras på alternativet **Ignorera betalningar och kreditnotor vid beräkning av kravbrevskod** i Kredit och inkasso.</span><span class="sxs-lookup"><span data-stu-id="d5d15-105">The example is based on the **Ignore payments and credit memos when calculating collection letter code** option in Credit and collections.</span></span> <span data-ttu-id="d5d15-106">Data används i USMF demoföretaget och en ny kund, US-045.</span><span class="sxs-lookup"><span data-stu-id="d5d15-106">It uses data in the USMF demo company and a new customer, US-045.</span></span>

<span data-ttu-id="d5d15-107">Till att börja med **Kundreskontra \> Kunder \> Alla kunder**, välj **Ny** och ange sedan nödvändig information för att skapa kund US-045.</span><span class="sxs-lookup"><span data-stu-id="d5d15-107">To begin, go to **Accounts receivable \> Customers \> All customers**, select **New**, and then enter the required information to create customer US-045.</span></span>

<span data-ttu-id="d5d15-108">När du avslutar följer du dessa steg.</span><span class="sxs-lookup"><span data-stu-id="d5d15-108">When you've finished, follow these steps.</span></span>

1. <span data-ttu-id="d5d15-109">Gå till **Kredit och inkasso \> Kravbrev \> Ställ in sekvensen för kravbrev** och ställa in sekvensen för samlingsbrevet som visas i följande tabell som tilldelas kundbokföringsprofilen.</span><span class="sxs-lookup"><span data-stu-id="d5d15-109">Go to **Credit and collections \> Collection letter \> Setup collection letter sequence**, and set up the collection letter sequence as shown in the following table that is assigned to the customer posting profile.</span></span>

|     <span data-ttu-id="d5d15-110">Kravbrevskod</span><span class="sxs-lookup"><span data-stu-id="d5d15-110">Collection   letter code</span></span>      |     <span data-ttu-id="d5d15-111">beskrivning</span><span class="sxs-lookup"><span data-stu-id="d5d15-111">Description</span></span>                           |     <span data-ttu-id="d5d15-112">Valuta</span><span class="sxs-lookup"><span data-stu-id="d5d15-112">Currency</span></span>      |     <span data-ttu-id="d5d15-113">Huvudkonto</span><span class="sxs-lookup"><span data-stu-id="d5d15-113">Main   account</span></span>        |     <span data-ttu-id="d5d15-114">Avgift i valuta</span><span class="sxs-lookup"><span data-stu-id="d5d15-114">Fee   in currency</span></span>     |     <span data-ttu-id="d5d15-115">Minimum över</span><span class="sxs-lookup"><span data-stu-id="d5d15-115">Minimum   over</span></span>        |     <span data-ttu-id="d5d15-116">Dagar block</span><span class="sxs-lookup"><span data-stu-id="d5d15-116">Days   Block</span></span>      |
|---------------------------------  |---------------------------------------    |-----------------  |-----------------------    |-------------------------- |-----------------------    |---------------------  |
|     <span data-ttu-id="d5d15-117">Kravbrev 1</span><span class="sxs-lookup"><span data-stu-id="d5d15-117">Collection   letter 1</span></span>         |     <span data-ttu-id="d5d15-118">Andra notifieringen med avgift</span><span class="sxs-lookup"><span data-stu-id="d5d15-118">Second   notification with fee</span></span>        |     <span data-ttu-id="d5d15-119">USD</span><span class="sxs-lookup"><span data-stu-id="d5d15-119">USD</span></span>           |                           |     <span data-ttu-id="d5d15-120">0,00</span><span class="sxs-lookup"><span data-stu-id="d5d15-120">0.00</span></span>                  |     <span data-ttu-id="d5d15-121">0,00</span><span class="sxs-lookup"><span data-stu-id="d5d15-121">0.00</span></span>                  |     <span data-ttu-id="d5d15-122">2</span><span class="sxs-lookup"><span data-stu-id="d5d15-122">2</span></span>                 |
|     <span data-ttu-id="d5d15-123">Kravbrev 2</span><span class="sxs-lookup"><span data-stu-id="d5d15-123">Collection   letter 2</span></span>         |     <span data-ttu-id="d5d15-124">Andra notifieringen med avgift</span><span class="sxs-lookup"><span data-stu-id="d5d15-124">Second   notification with fee</span></span>        |     <span data-ttu-id="d5d15-125">USC</span><span class="sxs-lookup"><span data-stu-id="d5d15-125">USC</span></span>           |     <span data-ttu-id="d5d15-126">403150</span><span class="sxs-lookup"><span data-stu-id="d5d15-126">403150</span></span>                |     <span data-ttu-id="d5d15-127">20.00</span><span class="sxs-lookup"><span data-stu-id="d5d15-127">20.00</span></span>                 |     <span data-ttu-id="d5d15-128">10,00</span><span class="sxs-lookup"><span data-stu-id="d5d15-128">10.00</span></span>                 |     <span data-ttu-id="d5d15-129">3</span><span class="sxs-lookup"><span data-stu-id="d5d15-129">3</span></span>                 |
|     <span data-ttu-id="d5d15-130">Grupp</span><span class="sxs-lookup"><span data-stu-id="d5d15-130">Collection</span></span>                    |     <span data-ttu-id="d5d15-131">Sista notifieringen med avgift</span><span class="sxs-lookup"><span data-stu-id="d5d15-131">Final   notification with fee</span></span>         |     <span data-ttu-id="d5d15-132">USD</span><span class="sxs-lookup"><span data-stu-id="d5d15-132">USD</span></span>           |     <span data-ttu-id="d5d15-133">403150</span><span class="sxs-lookup"><span data-stu-id="d5d15-133">403150</span></span>                |     <span data-ttu-id="d5d15-134">50.00</span><span class="sxs-lookup"><span data-stu-id="d5d15-134">50.00</span></span>                 |     <span data-ttu-id="d5d15-135">100.00</span><span class="sxs-lookup"><span data-stu-id="d5d15-135">100.00</span></span>                |     <span data-ttu-id="d5d15-136">15</span><span class="sxs-lookup"><span data-stu-id="d5d15-136">15</span></span>                |

<span data-ttu-id="d5d15-137">I följande illustration visas den information som finns i registret på det sätt som den skulle visas på sidan **Kravbrev**.</span><span class="sxs-lookup"><span data-stu-id="d5d15-137">The following illustration shows the information that's in the table as it would appear on the **Collection letters** page.</span></span> 

<span data-ttu-id="d5d15-138">[![Ställ in en kravbrevsserie](./media/Ignore-payments-creditmemos-1.PNG)](./media/Ignore-payments-creditmemos-1.PNG)</span><span class="sxs-lookup"><span data-stu-id="d5d15-138">[![Setting up a collection letter sequence](./media/Ignore-payments-creditmemos-1.PNG)](./media/Ignore-payments-creditmemos-1.PNG)</span></span>

 <span data-ttu-id="d5d15-139">Nu måste du ställa in de två parametrar som krävs för det här exemplet.</span><span class="sxs-lookup"><span data-stu-id="d5d15-139">You must now set the two parameters that are required for this example.</span></span>

2. <span data-ttu-id="d5d15-140">Gå till **Kredit och inkasso \> Inställningar \> Parametrar för kundreskontra** och följ dessa steg:</span><span class="sxs-lookup"><span data-stu-id="d5d15-140">Go to **Credit and collections \> Setup \> Accounts receivable parameters**, and follow these steps:</span></span>

    1. <span data-ttu-id="d5d15-141">På fliken **Inkasso**, ange alternativet **Ignorera betalningar och kreditnotor vid beräkning av kravbrevskod** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="d5d15-141">On the **Collections** tab, set the **Ignore payments and credit memos when calculating collection letter code** option to **Yes**.</span></span>
    2. <span data-ttu-id="d5d15-142">Se till att fältet **skapa kravbrev per** anges till **Kund**.</span><span class="sxs-lookup"><span data-stu-id="d5d15-142">Make sure that the **Create collection letter per** field is set to **Customer**.</span></span>

    <span data-ttu-id="d5d15-143">[![Ställa in kundreskontraparametrar för kreditsamlingar](./media/Ignore-payments-creditmemos-2.PNG)](./media/Ignore-payments-creditmemos-2.PNG)</span><span class="sxs-lookup"><span data-stu-id="d5d15-143">[![Setting Accounts receivable parameters for Credit collections](./media/Ignore-payments-creditmemos-2.PNG)](./media/Ignore-payments-creditmemos-2.PNG)</span></span>

3. <span data-ttu-id="d5d15-144">Gå till **Kundreskontra \> Fakturor \> Alla fritextfakturor**, välj **Ny** och gör följande steg:</span><span class="sxs-lookup"><span data-stu-id="d5d15-144">Go to **Accounts receivable \> Invoices \> All free text invoices**, select **New**, and then follow these steps:</span></span>

    1. <span data-ttu-id="d5d15-145">I fältet **kundkonto** välj **US-045**.</span><span class="sxs-lookup"><span data-stu-id="d5d15-145">In the **Customer account** field select **US-045**.</span></span>
    2. <span data-ttu-id="d5d15-146">I fältet **Fakturadatum**, ange **1/15/2021**.</span><span class="sxs-lookup"><span data-stu-id="d5d15-146">In the **Invoice date** field, enter **1/15/2021**.</span></span>
    3. <span data-ttu-id="d5d15-147">I fältet **Förfallodatum** anger du **1/16/2021**.</span><span class="sxs-lookup"><span data-stu-id="d5d15-147">In the **Due date** field, enter **1/16/2021**.</span></span>
    4. <span data-ttu-id="d5d15-148">På snabbfliken **Fakturarader** i fältet **Huvudkonto**, ange **401100**.</span><span class="sxs-lookup"><span data-stu-id="d5d15-148">On the **Invoice lines** FastTab, in the **Main account** field, enter **401100**.</span></span>
    5. <span data-ttu-id="d5d15-149">I fältet **Enhetspris** ange **500.00**.</span><span class="sxs-lookup"><span data-stu-id="d5d15-149">In the **Unit price** field, enter **500.00**.</span></span>
    6. <span data-ttu-id="d5d15-150">Vald **bokföring**</span><span class="sxs-lookup"><span data-stu-id="d5d15-150">Select **Post**.</span></span>

    <span data-ttu-id="d5d15-151">Du måste nu ange två kreditnotor för kunden.</span><span class="sxs-lookup"><span data-stu-id="d5d15-151">You must now enter two credit notes for the customer.</span></span>

4. <span data-ttu-id="d5d15-152">Välj **Ny** och gör sedan följande:</span><span class="sxs-lookup"><span data-stu-id="d5d15-152">Select **New**, and then follow these steps:</span></span>

    1. <span data-ttu-id="d5d15-153">I fältet **kundkonto** välj **US-045**.</span><span class="sxs-lookup"><span data-stu-id="d5d15-153">In the **Customer account** field, select **US-045**.</span></span>
    2. <span data-ttu-id="d5d15-154">I fältet **Fakturadatum**, ange **1/15/2021**.</span><span class="sxs-lookup"><span data-stu-id="d5d15-154">In the **Invoice date** field, enter **1/15/2021**.</span></span>
    3. <span data-ttu-id="d5d15-155">I fältet **Förfallodatum** anger du **1/16/2021**.</span><span class="sxs-lookup"><span data-stu-id="d5d15-155">In the **Due date** field, enter **1/16/2021**.</span></span>
    4. <span data-ttu-id="d5d15-156">På snabbfliken **Fakturarader** i fältet **Huvudkonto**, ange **401100**.</span><span class="sxs-lookup"><span data-stu-id="d5d15-156">On the **Invoice lines** FastTab, in the **Main account** field, enter **401100**.</span></span>
    5. <span data-ttu-id="d5d15-157">I fältet **Enhetspris**, ange **-100,00**.</span><span class="sxs-lookup"><span data-stu-id="d5d15-157">In the **Unit price** field, enter **-100.00**.</span></span>
    6. <span data-ttu-id="d5d15-158">Vald **bokföring**</span><span class="sxs-lookup"><span data-stu-id="d5d15-158">Select **Post**.</span></span>

5. <span data-ttu-id="d5d15-159">Upprepa steg 4, men ange **-200,00** i fältet **Enhetspris**.</span><span class="sxs-lookup"><span data-stu-id="d5d15-159">Repeat step 4, but enter **-200.00** in the **Unit price** field.</span></span>
6. <span data-ttu-id="d5d15-160">Gå till **Kundreskontra \> Kunder \> Alla kunder** och välj kund **US-045**.</span><span class="sxs-lookup"><span data-stu-id="d5d15-160">Go to **Accounts receivable \> Customers \> All customers**, and select customer **US-045**.</span></span> <span data-ttu-id="d5d15-161">I åtgärdsfönstret väljer du sedan **Transaktioner \> Transaktioner** för att granska de kundtransaktioner som du publicerade tidigare.</span><span class="sxs-lookup"><span data-stu-id="d5d15-161">Then, on the Action Pane, select **Transactions \> Transactions** to review the customer transactions that you posted earlier.</span></span>

    <span data-ttu-id="d5d15-162">[![Granska bokförda kundtransaktioner](./media/Ignore-payments-creditmemos-3.PNG)](./media/Ignore-payments-creditmemos-3.PNG)</span><span class="sxs-lookup"><span data-stu-id="d5d15-162">[![Reviewing the posted customer transactions](./media/Ignore-payments-creditmemos-3.PNG)](./media/Ignore-payments-creditmemos-3.PNG)</span></span>

    <span data-ttu-id="d5d15-163">Du måste nu skapa kravbrev för kunden US-045.</span><span class="sxs-lookup"><span data-stu-id="d5d15-163">You must now create collection letters for customer US-045.</span></span>

7. <span data-ttu-id="d5d15-164">Gå till **Kredit och inkasso \> Kravbrev \> Skapa kravbrev** och följa dessa steg:</span><span class="sxs-lookup"><span data-stu-id="d5d15-164">Go to **Credit and collections \> Collection letter \> Create collection letters**, and follow these steps:</span></span>

    1. <span data-ttu-id="d5d15-165">Ställ in alternativen **Faktura** och **Kreditfaktura** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="d5d15-165">Set the **Invoice** and **Credit note** options to **Yes**.</span></span>

        <span data-ttu-id="d5d15-166">Som standard ska fältet **Kravbrev** anges till **Krav per kund**.</span><span class="sxs-lookup"><span data-stu-id="d5d15-166">By default, the **Collection letter** field should be set to **Collection per customer**.</span></span>

    2. <span data-ttu-id="d5d15-167">I fältet **datum för kravbrevet**, ange **1/19/2021**.</span><span class="sxs-lookup"><span data-stu-id="d5d15-167">In the **Collection letter date** field, enter **1/19/2021**.</span></span>
    3. <span data-ttu-id="d5d15-168">På snabbflikarna **Poster som ska ingå**, välj **Filter** och fältet **Kundkonto**, lägg till kund **US-045**.</span><span class="sxs-lookup"><span data-stu-id="d5d15-168">On the **Records to include** FastTab, select **Filter**, and then, in the **Customer account** field, add customer **US-045**.</span></span>
    4. <span data-ttu-id="d5d15-169">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="d5d15-169">Select **OK**.</span></span>
    5. <span data-ttu-id="d5d15-170">Välj **OK** för att skapa kravbrevet.</span><span class="sxs-lookup"><span data-stu-id="d5d15-170">Select **OK** to create collection letters.</span></span>

8. <span data-ttu-id="d5d15-171">Gå till **Kredit och inkasso \> Kravbrev \> Granska och bearbeta kravbrev** och följa dessa steg:</span><span class="sxs-lookup"><span data-stu-id="d5d15-171">Go to **Credit and collections \> Collection letter \> Review and process collection letters**, and follow these steps:</span></span>

    1. <span data-ttu-id="d5d15-172">Observera att kravbrevkoden på både rubriken och transaktionsraderna är **Kravbrev 1**, eftersom det här kravbrevet är det första kravbrevet i sekvensen.</span><span class="sxs-lookup"><span data-stu-id="d5d15-172">Notice that the collection letter code on both the header and the transaction lines is **Collection letter 1**, because this collection letter is the first collection letter in the sequence.</span></span> <span data-ttu-id="d5d15-173">(Om du vill visa transaktionsraderna måste du kanske välja snabbflik **transaktioner**.)</span><span class="sxs-lookup"><span data-stu-id="d5d15-173">(To view the transaction lines, you might have to select the **Transactions** FastTab.)</span></span>

   <span data-ttu-id="d5d15-174">[![Kontrollera att samma kravbrevskod visas på huvudet och på raderna](./media/Ignore-payments-creditmemos-4.PNG)](./media/Ignore-payments-creditmemos-4.PNG)</span><span class="sxs-lookup"><span data-stu-id="d5d15-174">[![Verifying that the same collection letter code appears on the header and the lines](./media/Ignore-payments-creditmemos-4.PNG)](./media/Ignore-payments-creditmemos-4.PNG)</span></span>

    2. <span data-ttu-id="d5d15-175">Klicka på **Bokföra** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="d5d15-175">On the Action Pane, select **Post**.</span></span>
    3. <span data-ttu-id="d5d15-176">I fältet **Bokföringsdatum**, ange **1/19/2021**.</span><span class="sxs-lookup"><span data-stu-id="d5d15-176">In the **Posting date** field, enter **1/19/2021**.</span></span>

    <span data-ttu-id="d5d15-177">Du måste nu skapa kravbrev igen för kunden US-045.</span><span class="sxs-lookup"><span data-stu-id="d5d15-177">You must now create collection letters again for customer US-045.</span></span>

9. <span data-ttu-id="d5d15-178">Gå till **Kredit och inkasso \> Kravbrev \> Skapa kravbrev** och följa dessa steg:</span><span class="sxs-lookup"><span data-stu-id="d5d15-178">Go to **Credit and collections \> Collection letter \> Create collection letters**, and follow these steps:</span></span>

    1. <span data-ttu-id="d5d15-179">Ställ in alternativen **Faktura** och **Kreditfaktura** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="d5d15-179">Set the **Invoice** and **Credit note** options to **Yes**.</span></span>

        <span data-ttu-id="d5d15-180">Som standard ska fältet **Kravbrev** anges till **Krav per kund**.</span><span class="sxs-lookup"><span data-stu-id="d5d15-180">By default, the **Collection letter** field should be set to **Collection per customer**.</span></span>

    2. <span data-ttu-id="d5d15-181">I fältet **datum för kravbrevet**, ange **1/23/2021**.</span><span class="sxs-lookup"><span data-stu-id="d5d15-181">In the **Collection letter date** field, enter **1/23/2021**.</span></span>
    3. <span data-ttu-id="d5d15-182">På snabbflikarna **Poster som ska ingå**, välj **Filter** och fältet **Kundkonto**, lägg till kund **US-045**.</span><span class="sxs-lookup"><span data-stu-id="d5d15-182">On the **Records to include** FastTab, select **Filter**, and then, in the **Customer account** field, add customer **US-045**.</span></span>
    4. <span data-ttu-id="d5d15-183">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="d5d15-183">Select **OK**.</span></span>
    5. <span data-ttu-id="d5d15-184">Välj **OK** för att skapa kravbrevet.</span><span class="sxs-lookup"><span data-stu-id="d5d15-184">Select **OK** to create collection letters.</span></span>

10. <span data-ttu-id="d5d15-185">Gå till **Kredit och inkasso \> Kravbrev \> Granska och bearbeta kravbrev** och följa dessa steg:</span><span class="sxs-lookup"><span data-stu-id="d5d15-185">Go to **Credit and collections \> Collection letter \> Review and process collection letters**, and follow these steps:</span></span>

    1. <span data-ttu-id="d5d15-186">Lägg märke till att kravbrevskoden i rubriken **Kravbrev 1**.</span><span class="sxs-lookup"><span data-stu-id="d5d15-186">Notice that the collection letter code on the header is **Collection letter 1**.</span></span> <span data-ttu-id="d5d15-187">Koden på transaktionsraderna är dock **Kravbrev 2**.</span><span class="sxs-lookup"><span data-stu-id="d5d15-187">However, the code on the transaction lines is **Collection letter 2**.</span></span>

   <span data-ttu-id="d5d15-188">[![Kontrollerar att olika kravbrevskoder visas på huvudet och på raderna](./media/Ignore-payments-creditmemos-5.PNG)](./media/Ignore-payments-creditmemos-5.PNG)</span><span class="sxs-lookup"><span data-stu-id="d5d15-188">[![Verifies that different collection letter codes appear on the header and the lines](./media/Ignore-payments-creditmemos-5.PNG)](./media/Ignore-payments-creditmemos-5.PNG)</span></span>

  <span data-ttu-id="d5d15-189">Koderna skiljer sig åt eftersom alternativet **Ignorera betalningar och kreditnotor vid beräkning av kravbrevskod** är **Ja**.</span><span class="sxs-lookup"><span data-stu-id="d5d15-189">The codes differ because the **Ignore payments and credit memos when calculating collection letter code** option is to **Yes**.</span></span>

  2. <span data-ttu-id="d5d15-190">Bokför inte detta kravbrevet.</span><span class="sxs-lookup"><span data-stu-id="d5d15-190">Don't post this collection letter.</span></span>

11. <span data-ttu-id="d5d15-191">Gå till **Kredit och inkasso \> Inställningar \> Parametrar för kundreskontra** och fliken **Inkasso**, ange **Ignorera betalningar och kreditnotor vid beräkning av kravbrevskod** till **Nej**.</span><span class="sxs-lookup"><span data-stu-id="d5d15-191">Go to **Credit and collections \> Setup \> Accounts receivable parameters**, and then, on the **Collections** tab, set the **Ignore payments and credit memos when calculating collection letter code** option to **No**.</span></span>

    <span data-ttu-id="d5d15-192">[![Ställa in alternativet ignorera betalningar och kreditnotor när du beräknar kravbrevskod till Nej](./media/Ignore-payments-creditmemos-6.PNG)](./media/Ignore-payments-creditmemos-6.PNG)</span><span class="sxs-lookup"><span data-stu-id="d5d15-192">[![Setting the Ignore payments and credit memos when calculating collection letter code option to No](./media/Ignore-payments-creditmemos-6.PNG)](./media/Ignore-payments-creditmemos-6.PNG)</span></span>

    <span data-ttu-id="d5d15-193">Du måste nu skapa kravbrev igen för kunden US-045.</span><span class="sxs-lookup"><span data-stu-id="d5d15-193">You must now create collection letters again for customer US-045.</span></span>

12. <span data-ttu-id="d5d15-194">Gå till **Kredit och inkasso \> Kravbrev \> Skapa kravbrev** och följa dessa steg:</span><span class="sxs-lookup"><span data-stu-id="d5d15-194">Go to **Credit and collections \> Collection letter \> Create collection letters**, and follow these steps:</span></span>

    1. <span data-ttu-id="d5d15-195">Ställ in alternativen **Faktura** och **Kreditfaktura** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="d5d15-195">Set the **Invoice** and **Credit note** options to **Yes**.</span></span>

        <span data-ttu-id="d5d15-196">Som standard ska fältet **Kravbrev** anges till **Krav per kund**.</span><span class="sxs-lookup"><span data-stu-id="d5d15-196">By default, the **Collection letter** field should be set to **Collection per customer**.</span></span>

    2. <span data-ttu-id="d5d15-197">I fältet **datum för kravbrevet**, ange **1/23/2021**.</span><span class="sxs-lookup"><span data-stu-id="d5d15-197">In the **Collection letter date** field, enter **1/23/2021**.</span></span>
    3. <span data-ttu-id="d5d15-198">På snabbflikarna **Poster som ska ingå**, välj **Filter** och fältet **Kundkonto**, lägg till kund **US-045**.</span><span class="sxs-lookup"><span data-stu-id="d5d15-198">On the **Records to include** FastTab, select **Filter**, and then, in the **Customer account** field, add customer **US-045**.</span></span>
    4. <span data-ttu-id="d5d15-199">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="d5d15-199">Select **OK**.</span></span>
    5. <span data-ttu-id="d5d15-200">Välj **OK** för att skapa kravbrevet.</span><span class="sxs-lookup"><span data-stu-id="d5d15-200">Select **OK** to create collection letters.</span></span>

13. <span data-ttu-id="d5d15-201">Gå till **Kredit och inkasso \> Kravbrev \> Granska och bearbeta kravbrev** och märker att kravbrevkoden på både rubriken och transaktionsraderna är **Kravbrev 2**.</span><span class="sxs-lookup"><span data-stu-id="d5d15-201">Go to **Credit and collections \> Collection letter \> Review and process collection letters**, and notice that the collection letter code on both the header and the transaction lines is **Collection letter 2**.</span></span>

    <span data-ttu-id="d5d15-202">[![Visa igen att samma kravbrevskod visas på huvudet och på raderna](./media/Ignore-payments-creditmemos-7.PNG)](./media/Ignore-payments-creditmemos-7.PNG)</span><span class="sxs-lookup"><span data-stu-id="d5d15-202">[![Showing again that the same collection letter code appears on the header and the lines](./media/Ignore-payments-creditmemos-7.PNG)](./media/Ignore-payments-creditmemos-7.PNG)</span></span>

    <span data-ttu-id="d5d15-203">Samma kod visas på båda platserna eftersom alternativet **Ignorera betalningar och kreditnotor vid beräkning av kravbrevskod** anges **Nej**.</span><span class="sxs-lookup"><span data-stu-id="d5d15-203">The same code appears in both places because the **Ignore payments and credit memos when calculating collection letter code** option is now set to **No**.</span></span>