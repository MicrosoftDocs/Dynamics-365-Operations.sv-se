---
title: Ställ in betalningsavgifter för TDS-myndighetsbetalningar
description: I det här avsnittet beskrivs hur du ställer in betalningsavgifter som debiteras för myndighetsbetalningar vid skatteavdrag vid källa (TDS).
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: b52331bb1c7a1bc2c764008112f3df9cc0385995
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023613"
---
# <a name="set-up-payment-fees-for-tds-authority-payments"></a><span data-ttu-id="0008b-103">Ställ in betalningsavgifter för TDS-myndighetsbetalningar</span><span class="sxs-lookup"><span data-stu-id="0008b-103">Set up payment fees for TDS authority payments</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0008b-104">I det här avsnittet beskrivs hur du ställer in betalningsavgifter som debiteras för myndighetsbetalningar vid skatteavdrag vid källa (TDS).</span><span class="sxs-lookup"><span data-stu-id="0008b-104">This topic explains how to set up payment fees that are charged for Tax Deducted at Source (TDS) authority payments.</span></span>

1. <span data-ttu-id="0008b-105">Gå till **Leverantörsreskontra \> Betalningsinställning \> Betalningsavgift**.</span><span class="sxs-lookup"><span data-stu-id="0008b-105">Go to **Accounts payable \> Payment setup \> Payment fee**.</span></span>

    <span data-ttu-id="0008b-106">[![Sidan Betalningsavgift](./media/apac-ind-TDS-28.png)](./media/apac-ind-TDS-28.png)</span><span class="sxs-lookup"><span data-stu-id="0008b-106">[![Payment fee page](./media/apac-ind-TDS-28.png)](./media/apac-ind-TDS-28.png)</span></span>

2. <span data-ttu-id="0008b-107">Välj **Ny** för att skapa en betalningsavgift och ange den information som krävs.</span><span class="sxs-lookup"><span data-stu-id="0008b-107">Select **New** to create a payment fee, and enter the required details.</span></span>
3. <span data-ttu-id="0008b-108">I fältet **Avgiftstyp** väljer du typ av betalningsavgift:</span><span class="sxs-lookup"><span data-stu-id="0008b-108">In the **Fee type** field, select the type of payment fee:</span></span>

    - <span data-ttu-id="0008b-109">**None**</span><span class="sxs-lookup"><span data-stu-id="0008b-109">**None**</span></span>
    - <span data-ttu-id="0008b-110">**Ränta** – Ränta debiteras på försenade betalningar som görs till TDS-myndigheten.</span><span class="sxs-lookup"><span data-stu-id="0008b-110">**Interest** – Interest is charged on late payments that are made to the TDS authority vendor.</span></span>
    - <span data-ttu-id="0008b-111">**Övrigt** – Övriga avgifter debiteras på försenade betalningar som görs till TDS-myndigheten.</span><span class="sxs-lookup"><span data-stu-id="0008b-111">**Others** – Other charges are charged on late payments that are made to the TDS authority vendor.</span></span>

    <span data-ttu-id="0008b-112">Om du väljer **Ränta** eller **Övrigt** ställs fältet **Avgift** automatiskt in på **Redovisning**.</span><span class="sxs-lookup"><span data-stu-id="0008b-112">If you select **Interest** or **Others**, the **Charge** field is automatically set to **Ledger**.</span></span>

4. <span data-ttu-id="0008b-113">Om du har valt **Ränta** eller **Övrigt** i fältet **Fälttyp**, i fältet **Huvudkonto**, väljer du huvudbokskonto för att bokföra ränta eller övrigt.</span><span class="sxs-lookup"><span data-stu-id="0008b-113">If you selected **Interest** or **Others** in the **Field type** field, in the **Main account** field, select the ledger account to post the interest or other charges to.</span></span>
5. <span data-ttu-id="0008b-114">Ange andra uppgifter som behövs.</span><span class="sxs-lookup"><span data-stu-id="0008b-114">Enter the other required details.</span></span>
6. <span data-ttu-id="0008b-115">I åtgärdsfönstret väljer du **Inställning av betalningsavgift** för att öppna sidan **Inställning av betalningsavgift**, där du kan ställa in betalningsavgifter för olika kombinationer av banker, betalningsmetoder, betalningsspecifikationer, valutor och datumintervall.</span><span class="sxs-lookup"><span data-stu-id="0008b-115">On the Action Pane, select **Payment fee setup** to open the **Payment fee setup** page, where you can set up payment fees for various combinations of banks, methods of payment, payment specifications, currencies, and date intervals.</span></span>

    <span data-ttu-id="0008b-116">[![Sidan Betalningsavgiftsinställning](./media/apac-ind-TDS-21.png)](./media/apac-ind-TDS-21.png)</span><span class="sxs-lookup"><span data-stu-id="0008b-116">[![Payment fee setup page](./media/apac-ind-TDS-21.png)](./media/apac-ind-TDS-21.png)</span></span>

7. <span data-ttu-id="0008b-117">På fliken **Översikt**, i fältet **Grupperingar**, anger du vilka banker som du ställer in betalningsavgiften för:</span><span class="sxs-lookup"><span data-stu-id="0008b-117">On the **Overview** tab, in the **Groupings** field, specify which banks you're setting up the payment fee for:</span></span>

    - <span data-ttu-id="0008b-118">**Tabell** – Avgiften är giltig för ett specifikt bankkonto.</span><span class="sxs-lookup"><span data-stu-id="0008b-118">**Table** – The fee is valid for a specific bank account.</span></span>
    - <span data-ttu-id="0008b-119">**Grupp** – Avgiften är giltig för en specifik grupp.</span><span class="sxs-lookup"><span data-stu-id="0008b-119">**Group** – The fee is valid for a specific bank group.</span></span>
    - <span data-ttu-id="0008b-120">**Alla** - Avgiften är giltig för alla bankkonton.</span><span class="sxs-lookup"><span data-stu-id="0008b-120">**All** – The fee is valid for all the bank accounts.</span></span>

8. <span data-ttu-id="0008b-121">Om du har valt **Tabell** eller **Grupp** i fältet **Grupperingar**, i fältet **Bankrelation**, väljer du det specifika bankkonto eller den specifika bankgrupp som du ställer in betalningsavgiften för.</span><span class="sxs-lookup"><span data-stu-id="0008b-121">If you selected **Table** or **Group** in the **Groupings** field, in the **Bank relation** field, select the specific bank account or bank group that you're setting up the payment fee for.</span></span>
9. <span data-ttu-id="0008b-122">I fältet **Betalningsmetod** väljer du betalningsmetod för betalning av avgifter.</span><span class="sxs-lookup"><span data-stu-id="0008b-122">In the **Method of payment** field, select the method of payment for the payment of fees.</span></span>
10. <span data-ttu-id="0008b-123">I fältet **Betalningsspecifikation** väljer eller anger du betalningsspecifikationskoden som genererades på sidan **Betalningsspecifikation**.</span><span class="sxs-lookup"><span data-stu-id="0008b-123">In the **Payment specification** field, select or enter the payment specification code that was generated on the **Payment specification** page.</span></span>
    - <span data-ttu-id="0008b-124">Betalningsspecifikationen används med överföringsbetalsätt av elektronisk fond.</span><span class="sxs-lookup"><span data-stu-id="0008b-124">The Payment specification is used with electronic fund transfer methods of payment.</span></span>
12. <span data-ttu-id="0008b-125">I fältet **Betalningsvaluta** väljer du den valuta som aktiverar avgiften.</span><span class="sxs-lookup"><span data-stu-id="0008b-125">In the **Payment currency** field, select the currency that activates the fee.</span></span> <span data-ttu-id="0008b-126">Endast transaktioner med den valda valutan kan aktivera avgiften.</span><span class="sxs-lookup"><span data-stu-id="0008b-126">Only transactions that use the selected currency can activate the fee.</span></span> <span data-ttu-id="0008b-127">Om du lämnar det här fältet tomt aktiveras avgiften av alla valutor.</span><span class="sxs-lookup"><span data-stu-id="0008b-127">If you leave this field blank, all currencies activate the fee.</span></span>
13. <span data-ttu-id="0008b-128">I fältet **Procentandel/belopp** väljer du beräkningsmetod.</span><span class="sxs-lookup"><span data-stu-id="0008b-128">In the **Percentage/Amount** field, select the calculation method.</span></span> <span data-ttu-id="0008b-129">Alternativen är **Belopp**, **Procent** och **Intervall**.</span><span class="sxs-lookup"><span data-stu-id="0008b-129">The options are **Amount**, **Percent**, and **Interval**.</span></span>
14. <span data-ttu-id="0008b-130">I fältet **Avgiftsbelopp** anger du avgiftsbeloppet som antingen en procentandel av betalningen eller som beloppet för en betalning.</span><span class="sxs-lookup"><span data-stu-id="0008b-130">In the **Fee amount** field, specify the fee amount as either a percentage of the payment or the amount for one payment.</span></span>
15. <span data-ttu-id="0008b-131">I fältet **Avgiftsvaluta** anger du valutakoden för avgiften.</span><span class="sxs-lookup"><span data-stu-id="0008b-131">In the **Fee currency** field, specify the currency code for the fee.</span></span>
16. <span data-ttu-id="0008b-132">Välj fliken **Allmänt** för att visa eller modifiera informationen för det valda bankkontot.</span><span class="sxs-lookup"><span data-stu-id="0008b-132">Select the **General** tab to view or modify the details for the selected bank account.</span></span>

    <span data-ttu-id="0008b-133">[![Fliken Allmänt](./media/apac-ind-TDS-22.png)](./media/apac-ind-TDS-22.png)</span><span class="sxs-lookup"><span data-stu-id="0008b-133">[![General tab](./media/apac-ind-TDS-22.png)](./media/apac-ind-TDS-22.png)</span></span>

16. <span data-ttu-id="0008b-134">I fältet **Minimum** anger du det minsta transaktionsbeloppet som aktiverar avgiften.</span><span class="sxs-lookup"><span data-stu-id="0008b-134">In the **Minimum** field, enter the minimum transaction amount that activates the fee.</span></span>
17. <span data-ttu-id="0008b-135">I fältet **Maximum** anger du det högsta transaktionsbeloppet som aktiverar avgiften.</span><span class="sxs-lookup"><span data-stu-id="0008b-135">In the **Maximum** field, enter the maximum transaction amount that activates the fee.</span></span>
18. <span data-ttu-id="0008b-136">I fälten **Från datum** och **Till datum** definierar du ett datumintervall för avgiftsberäkning.</span><span class="sxs-lookup"><span data-stu-id="0008b-136">In the **From date** and **To date** fields, define a date range for calculating fees.</span></span>
19. <span data-ttu-id="0008b-137">I fältet **Minsta avgift** anger du avgiftsbeloppet som antingen en procentandel av betalningen eller som beloppet för en betalning.</span><span class="sxs-lookup"><span data-stu-id="0008b-137">In the **Minimum fee** field, specify the amount of the fee as either a percentage of the payment or the amount for one payment.</span></span>
20. <span data-ttu-id="0008b-138">I fältet **Momsgrupp** väljer du den momsgrupp som ska användas för att beräkna moms för avgiften.</span><span class="sxs-lookup"><span data-stu-id="0008b-138">In the **Sales tax group** field, select the sales tax group to use to calculate the sales tax for the fee amount.</span></span>
21. <span data-ttu-id="0008b-139">I fältet **Momsgrupp för artikel** väljer du den momsgrupp för artikel som ska användas för att beräkna moms för artikeln för avgiften.</span><span class="sxs-lookup"><span data-stu-id="0008b-139">In the **Item sales tax group** field, select the item sales tax group to use to calculate the item sales tax for the fee amount.</span></span>
22. <span data-ttu-id="0008b-140">Välj fliken **Intervall**.</span><span class="sxs-lookup"><span data-stu-id="0008b-140">Select the **Interval** tab.</span></span> 

    <span data-ttu-id="0008b-141">[![Fliken Intervall](./media/apac-ind-TDS-23.png)](./media/apac-ind-TDS-23.png)</span><span class="sxs-lookup"><span data-stu-id="0008b-141">[![Interval tab](./media/apac-ind-TDS-23.png)](./media/apac-ind-TDS-23.png)</span></span>

23. <span data-ttu-id="0008b-142">I fältet **Dagar** anger du antalet dagar mellan bokföringsdatumet (diskonteringsdatumet) för betalningen och förfallodatumet för skuldsedeln.</span><span class="sxs-lookup"><span data-stu-id="0008b-142">In the **Days** field, enter the number of days between the posting date (discounting date) of the payment and the due date of the promissory note.</span></span>
24. <span data-ttu-id="0008b-143">I fältet **Procentandel/belopp** väljer du om specifikationen är en procentandel eller ett fast belopp.</span><span class="sxs-lookup"><span data-stu-id="0008b-143">In the **Percentage/Amount** field, select whether the specification is a percentage or a set amount.</span></span>
25. <span data-ttu-id="0008b-144">I fältet **Avgiftsbelopp** anger du avgiftsbeloppet som antingen en procentandel av betalningen eller som beloppet för en betalning.</span><span class="sxs-lookup"><span data-stu-id="0008b-144">In the **Fee amount** field, enter the amount of the fee as either a percentage of the payment or the amount for one payment.</span></span>
26. <span data-ttu-id="0008b-145">Stäng sidan **Inställning av betalningsavgift**.</span><span class="sxs-lookup"><span data-stu-id="0008b-145">Close the **Payment fee setup** page.</span></span>
27. <span data-ttu-id="0008b-146">Stäng sidan **Betalningsavgift**.</span><span class="sxs-lookup"><span data-stu-id="0008b-146">Close the **Payment fee** page.</span></span>
