---
title: Kvitta TDS-betalningar till TDS-myndigheter och generera TDS challan
description: I det här avsnittet beskrivs hur du kvittar avdragna skatter vid källan (TDS) till leverantörer inom TDS-myndigheten.
author: kailiang
ms.date: 03/12/2021
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
ms.openlocfilehash: 5b77985a75d2930267cf94d6f218d53b47e6e705
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023605"
---
# <a name="settle-tds-payments-to-tds-authority-vendors-and-generate-tds-challan"></a><span data-ttu-id="afb36-103">Kvitta TDS-betalningar till TDS-myndigheter och generera TDS challan</span><span class="sxs-lookup"><span data-stu-id="afb36-103">Settle TDS payments to TDS authority vendors and generate TDS challan</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="afb36-104">I det här avsnittet beskrivs hur du kvittar avdragna skatter vid källan (TDS) till leverantörer inom TDS-myndigheten.</span><span class="sxs-lookup"><span data-stu-id="afb36-104">This topic explains how to settle Tax Deducted at Source (TDS) payments to TDS authority vendors.</span></span>

1. <span data-ttu-id="afb36-105">Gå till **leverantörsreskontra \> Betalningar \> Leverantörsbetalningsjournal**.</span><span class="sxs-lookup"><span data-stu-id="afb36-105">Go to **Accounts payable \> Payments \> Vendor payment journal**.</span></span>

    <span data-ttu-id="afb36-106">[![Sida för leverantörsbetalningsjournal](./media/apac-ind-TDS-51.png)](./media/apac-ind-TDS-51.png)</span><span class="sxs-lookup"><span data-stu-id="afb36-106">[![Vendor payment journal page](./media/apac-ind-TDS-51.png)](./media/apac-ind-TDS-51.png)</span></span>

2. <span data-ttu-id="afb36-107">På sidan **Leverantörsbetalningsjournal** väljer du **Ny** för att skapa en journalrad.</span><span class="sxs-lookup"><span data-stu-id="afb36-107">On the **Vendor payment journal** page, select **New** to create a journal line.</span></span>
3. <span data-ttu-id="afb36-108">I fältet **Konto** väljer du leverantör inom TDS-myndighet att kvitta TDS-betalning mot.</span><span class="sxs-lookup"><span data-stu-id="afb36-108">In the **Account** field, select the TDS authority vendor to settle TDS payments to.</span></span>
4. <span data-ttu-id="afb36-109">Välj **Kvittningstransaktioner** för att öppna sidan **Kvittningstransaktioner**, där du kan visa de kvittade TDS-transaktionerna för leverantören inom TDS-myndigheten.</span><span class="sxs-lookup"><span data-stu-id="afb36-109">Select **Settlement transactions** to open the **Settlement transactions** page, where you can view the settled TDS transactions for the TDS authority vendor.</span></span>

    <span data-ttu-id="afb36-110">De kvittade TDS-transaktionerna för en kvittningsperiod visas på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="afb36-110">The settled TDS transactions for a settlement period are shown in the following way:</span></span>

    - <span data-ttu-id="afb36-111">TDS-transaktioner där typen av bedömningskategori är **Företag** visas som en transaktionsrad.</span><span class="sxs-lookup"><span data-stu-id="afb36-111">TDS transactions where the nature of assessee category is **Company** are shown as one transaction line.</span></span>
    - <span data-ttu-id="afb36-112">TDS-transaktioner där typen av bedömningskategori är **HUF**, **Firma**, **Individ**, **AOP**, **BOI**, **Lokal myndighet** eller **Övrigt** visas som en transaktionsrad.</span><span class="sxs-lookup"><span data-stu-id="afb36-112">TDS transactions where the nature of assessee category is **HUF**, **Firm**, **Individual**, **AOP**, **BOI**, **Local authority**, or **Others** are shown as one transaction line.</span></span>
    - <span data-ttu-id="afb36-113">I fältet **Belopp** visas det totala TDS-belopp som ska betalas till leverantören inom TDS-myndigheten.</span><span class="sxs-lookup"><span data-stu-id="afb36-113">The **Amount** field shows the total TDS amount that is due to be paid to the TDS authority vendor.</span></span>

5. <span data-ttu-id="afb36-114">Välj **Källskattetransaktioner** för att visa de olika TDS-transaktioner som ingår i kvittningsposten.</span><span class="sxs-lookup"><span data-stu-id="afb36-114">Select **Withholding tax transactions** to view the different TDS transactions that are included for the settlement record.</span></span> <span data-ttu-id="afb36-115">Du kan visa uppdelningen av varje TDS-transaktion som har inkluderats i kvittningsprocessen för kvittningsperioden på den här sidan.</span><span class="sxs-lookup"><span data-stu-id="afb36-115">You can view the split of each TDS transaction that has been included in the settlement process for the settlement period on this page.</span></span>
6. <span data-ttu-id="afb36-116">Under fliken **Översikt** markerar du kryssrutan **Markera** för TDS-transaktionerna som ska kvittas mot leverantören inom TDS-myndigheten.</span><span class="sxs-lookup"><span data-stu-id="afb36-116">On the **Overview** tab, select the **Mark** check box for the TDS transactions to settle to the TDS authority vendor.</span></span>

    <span data-ttu-id="afb36-117">Under fliken **Översikt** visas följande information för varje öppen TDS-transaktion:</span><span class="sxs-lookup"><span data-stu-id="afb36-117">The **Overview** tab shows the following information for each open TDS transaction:</span></span>

    - <span data-ttu-id="afb36-118">**Datum** – Datumet för TDS-transaktionen.</span><span class="sxs-lookup"><span data-stu-id="afb36-118">**Date** – The TDS transaction date.</span></span>
    - <span data-ttu-id="afb36-119">**Verfikation** – Verifikationsnumret.</span><span class="sxs-lookup"><span data-stu-id="afb36-119">**Voucher** – The voucher number.</span></span>
    - <span data-ttu-id="afb36-120">**Källa** – Modulen där TDS-transaktionen bokförs.</span><span class="sxs-lookup"><span data-stu-id="afb36-120">**Source** – The module that the TDS transaction is posted in.</span></span>
    - <span data-ttu-id="afb36-121">**Leverantör/kund** – Leverantörs- eller kundkontonumret som TDS dras från.</span><span class="sxs-lookup"><span data-stu-id="afb36-121">**Vendor/Customer** – The vendor or customer account number that the TDS is deducted from.</span></span>
    - <span data-ttu-id="afb36-122">**Namn på avdragsskapare/part** – Namnet på leverantören eller kunden som TDS dras av från.</span><span class="sxs-lookup"><span data-stu-id="afb36-122">**Name of deductee/party** – The name of the vendor or customer that the TDS is deducted from.</span></span>
    - <span data-ttu-id="afb36-123">**Typ av bedömare** – Typen av bedömningskategori som avdragsskaparen tillhör.</span><span class="sxs-lookup"><span data-stu-id="afb36-123">**Nature of assessee** – The nature of assessee category that the deductee belongs to.</span></span>
    - <span data-ttu-id="afb36-124">**Belopp** – Fakturabeloppet som TDS beräknades på.</span><span class="sxs-lookup"><span data-stu-id="afb36-124">**Amount** – The invoice amount that the TDS was calculated on.</span></span>
    - <span data-ttu-id="afb36-125">**Skattebelopp** – TDS-beloppet som har beräknats för transaktionen.</span><span class="sxs-lookup"><span data-stu-id="afb36-125">**Tax amount** – The TDS amount that was calculated for the transaction.</span></span>

    > [!NOTE]
    > <span data-ttu-id="afb36-126">Avmarkera kryssrutan **Markera** för TDS-transaktioner som inte ska kvittas mot leverantören i TDS-myndigheten.</span><span class="sxs-lookup"><span data-stu-id="afb36-126">Clear the **Mark** check box for any TDS transactions that should not be settled to the TDS authority vendor.</span></span>

    <span data-ttu-id="afb36-127">Under fliken **Allmänt** visar fältet **PAN** det permanenta kontonumret (PAN) för avdragsskaparen.</span><span class="sxs-lookup"><span data-stu-id="afb36-127">On the **General** tab, the **PAN** field shows the permanent account number (PAN) of the deductee.</span></span> <span data-ttu-id="afb36-128">I fältet **Datum** visas datumet för TDS-beräkningen och i fältet **Värde** visas den totala procentsats som användes för TDS-beräkningen.</span><span class="sxs-lookup"><span data-stu-id="afb36-128">The **Date** field shows the date of the TDS calculation, and the **Value** field shows the total percentage that was used for the TDS calculation.</span></span>

7. <span data-ttu-id="afb36-129">Välj **Verifikation** för att visa verifikationsposterna för TDS-transaktionen.</span><span class="sxs-lookup"><span data-stu-id="afb36-129">Select **Voucher** to view the voucher entries for the TDS transaction.</span></span>
8. <span data-ttu-id="afb36-130">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="afb36-130">Close the page.</span></span>
10. <span data-ttu-id="afb36-131">Välj **Källskattekomponenter** för att öppna sidan **Källskattekomponenter**, där du kan visa TDS som beräknades per TDS-skattekomponent för en specifik TDS-skattekod.</span><span class="sxs-lookup"><span data-stu-id="afb36-131">Select **Withholding tax components** to open the **Withholding tax components** page, where you can view the TDS that was calculated per TDS tax component for a specific TDS tax code.</span></span>

    <span data-ttu-id="afb36-132">Under fliken **Översikt** visar fältet **Skattekomponent** den TDS-skattekomponent som användes för transaktionen.</span><span class="sxs-lookup"><span data-stu-id="afb36-132">On the **Overview** tab, the **Tax component** field shows the TDS tax component that was used for the transaction.</span></span> <span data-ttu-id="afb36-133">I fältet **Belopp** visas det TDS-belopp som beräknades för TDS-skattekomponenten, i basvalutan.</span><span class="sxs-lookup"><span data-stu-id="afb36-133">The **Amount** field shows the TDS amount that was calculated for the TDS tax component, in the base currency.</span></span> <span data-ttu-id="afb36-134">Fältet **Ackumulerat belopp** visar det totala TDS-beloppet som beräknades för TDS-skattekomponenten för alla kvittade transaktioner.</span><span class="sxs-lookup"><span data-stu-id="afb36-134">The **Accumulated amount** field shows the total TDS amount that was calculated for the TDS tax component for all settled transactions.</span></span>

    <span data-ttu-id="afb36-135">Under fliken **Belopp** visar avsnittet **Standardvaluta** det TDS-belopp som beräknades för TDS-skattekomponenten, i standardvalutan.</span><span class="sxs-lookup"><span data-stu-id="afb36-135">On the **Amount** tab, the **Default currency** section shows the TDS amount that was calculated for the TDS tax component, in the default currency.</span></span> <span data-ttu-id="afb36-136">I avsnittet **Sekundär valuta** visas beloppet i en sekundär valuta.</span><span class="sxs-lookup"><span data-stu-id="afb36-136">The **Secondary currency** section shows the amount in the secondary currency.</span></span>

11. <span data-ttu-id="afb36-137">Stäng sidan **Källskattekomponenter**.</span><span class="sxs-lookup"><span data-stu-id="afb36-137">Close the **Withholding tax components** page.</span></span>
12. <span data-ttu-id="afb36-138">På sidan **Öppna transaktionsredigering**, i fältet **Belopp**, noterar du att det totala beloppet som ska kvittas mot leverantören inom TDS-myndigheten för kvittningsperioden har uppdaterats.</span><span class="sxs-lookup"><span data-stu-id="afb36-138">On the **Open transaction editing** page, in the **Amount** field, notice that the total amount to settle to the TDS authority vendor for the settlement period is updated.</span></span>
13. <span data-ttu-id="afb36-139">Om du vill kvitta TDS-transaktionerna för olika TDS-kvittningsperioder mot leverantören i TDS-myndigheten markerar du kryssrutan **Markera** för transaktionerna.</span><span class="sxs-lookup"><span data-stu-id="afb36-139">To settle the TDS transactions of different TDS settlement periods to the TDS authority vendor, select the **Mark** check box for the transactions.</span></span>
14. <span data-ttu-id="afb36-140">Stäng sidan **Öppna transaktionsredigering**.</span><span class="sxs-lookup"><span data-stu-id="afb36-140">Close the **Open transaction editing** page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="afb36-141">Om bara ett par transaktioner väljs för kvittning på sidan **Källskattetransaktioner** uppdateras det totala TDS-beloppet för de valda transaktionerna i fältet **Korrigering** på sidan **Öppna transaktionsredigering**.</span><span class="sxs-lookup"><span data-stu-id="afb36-141">If only a few transactions are selected for settlement on the **Withholding tax transactions** page, the total TDS amount of the selected transactions is updated in the **Correction** field on the **Open transaction editing** page.</span></span> <span data-ttu-id="afb36-142">Korrigeringsbeloppet uppdateras på journalraden på sidan **Journalverifikation** och sidan **Öppna transaktionsredigering** stängs.</span><span class="sxs-lookup"><span data-stu-id="afb36-142">The correction amount is updated on the journal line on the **Journal voucher** page, and the **Open transaction editing** page is closed.</span></span>

    <span data-ttu-id="afb36-143">På sidan **Journalverifikation** visar fältet **Debet** det totala beloppet som ska betalas till leverantören inom TDS-myndigheten.</span><span class="sxs-lookup"><span data-stu-id="afb36-143">On the **Journal voucher** page, the **Debit** field shows the total amount to pay to the TDS authority vendor.</span></span>

15. <span data-ttu-id="afb36-144">Ange detaljer för motkontot.</span><span class="sxs-lookup"><span data-stu-id="afb36-144">Enter the offset account details.</span></span>

    > [!NOTE]
    > <span data-ttu-id="afb36-145">Om TDS-transaktioner har olika skattekontonummer (TAN) skapas journalrader per TAN på sidan **Journalverifikation**.</span><span class="sxs-lookup"><span data-stu-id="afb36-145">If TDS transactions have different Tax Account Numbers (TANs), journal lines are created per TAN on the **Journal voucher** page.</span></span>

16. <span data-ttu-id="afb36-146">Under fliken **Betalningsavgift**, i fältet **Avgifts-ID**, väljer du ett avgifts-ID som har avgiftstypen **Ränta** eller **Övrigt** för att debitera betalningsavgiften för försenade betalningar som görs till leverantören inom TDS-myndigheten.</span><span class="sxs-lookup"><span data-stu-id="afb36-146">On the **Payment fee** tab, in the **Fee ID** field, select a fee ID that has a fee type of **Interest** or **Others** to charge the payment fee for delayed payments that are made to the TDS authority vendor.</span></span>

    <span data-ttu-id="afb36-147">Under fliken **Skatteinformation**, i avsnittet **Företagsinformation**, visar fältet **Namn** företagsnamnet.</span><span class="sxs-lookup"><span data-stu-id="afb36-147">On the **Tax information** tab, in the **Company information** section, the **Name** field shows the company name.</span></span> <span data-ttu-id="afb36-148">I avsnittet **Källskatt** visar fältet **Skattekontonummer (TAN)** det TAN som är kopplat till transaktionsraden.</span><span class="sxs-lookup"><span data-stu-id="afb36-148">In the **Withholding tax** section, the **Tax Account Number (TAN)** field shows the TAN that is attached to the transaction line.</span></span>

17. <span data-ttu-id="afb36-149">Validera och bokför journalen.</span><span class="sxs-lookup"><span data-stu-id="afb36-149">Validate and post the journal.</span></span>
18. <span data-ttu-id="afb36-150">Välj **Källskatt \> Challan-information** för att ange challan-uppgifter för transaktionen.</span><span class="sxs-lookup"><span data-stu-id="afb36-150">Select **Withholding tax \> Challan information** to enter the challan details for the transaction.</span></span>

    <span data-ttu-id="afb36-151">I fältet **Verifikation** visas verifikationsnumret för transaktionen.</span><span class="sxs-lookup"><span data-stu-id="afb36-151">The **Voucher** field shows the voucher number of the transaction.</span></span>
    
19. <span data-ttu-id="afb36-152">Markera kryssrutan **TDS som sätts in genom bokföringspost** om TDS-beloppet sätts in genom bokföring.</span><span class="sxs-lookup"><span data-stu-id="afb36-152">Select the **TDS deposited by book entry** check box if the TDS amount is deposited by using book entry.</span></span>
20. <span data-ttu-id="afb36-153">I fältet **Challan-nummer** anger du challan-numret som används för att genomföra betalningen till leverantören inom TDS-myndigheten.</span><span class="sxs-lookup"><span data-stu-id="afb36-153">In the **Challan number** field, enter the challan number that is used to make the payment to the TDS authority vendor.</span></span>
21. <span data-ttu-id="afb36-154">I fältet **Datum** anger du challan-datum.</span><span class="sxs-lookup"><span data-stu-id="afb36-154">In the **Date** field, enter the challan date.</span></span>
22. <span data-ttu-id="afb36-155">I fältet **Banknamn** väljer du namnet på banken som TDS-beloppet som ska betalas till leverantören inom TDS-myndigheten ska sättas in på.</span><span class="sxs-lookup"><span data-stu-id="afb36-155">In the **Bank name** field, select the name of the bank that the TDS amount that is payable to the TDS authority vendor should be deposited to.</span></span> <span data-ttu-id="afb36-156">Det här fältet visar alla bankkonton som har ställts in för TDS-myndighetens leverantör i **Leverantörsreskontra \> Alla leverantörer \> Konfigurera \> Bankkonton**.</span><span class="sxs-lookup"><span data-stu-id="afb36-156">This field lists all the bank accounts that were set up for the TDS authority vendor at **Accounts payable \> All vendors \> Set up \> Bank accounts**.</span></span>
23. <span data-ttu-id="afb36-157">I fältet **BSR-kod** anger du BSR-koden (Basic Statistical Return) för banken.</span><span class="sxs-lookup"><span data-stu-id="afb36-157">In the **BSR code** field, enter the Basic Statistical Return (BSR) code of the bank.</span></span>
24. <span data-ttu-id="afb36-158">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="afb36-158">Close the page.</span></span>

### <a name="example"></a><span data-ttu-id="afb36-159">Exempel</span><span class="sxs-lookup"><span data-stu-id="afb36-159">Example</span></span>

<span data-ttu-id="afb36-160">Perioden 2009/04/01 kvittas för TDS-komponentgruppen **Hyra** med hjälp av den periodiska TDS-kvittningsprocessen.</span><span class="sxs-lookup"><span data-stu-id="afb36-160">The period 04/01/2009 is settled for the **Rent** TDS component group by using the periodic TDS settlement process.</span></span> <span data-ttu-id="afb36-161">Det totala TDS-beloppet 141 625,00 bokförs på TDS-leverantörsmyndighetskontot för TDS-kvittningsperioden.</span><span class="sxs-lookup"><span data-stu-id="afb36-161">The total TDS amount of 141,625.00 is posted to the TDS vendor authority account for the TDS settlement period.</span></span> <span data-ttu-id="afb36-162">Du kan visa beloppet i fältet **Belopp** på sidan **Öppna transaktionsredigering** för leverantören inom TDS-myndigheten.</span><span class="sxs-lookup"><span data-stu-id="afb36-162">You can view this amount in the **Amount** field on the **Open transaction editing** page for the TDS authority vendor.</span></span>

<span data-ttu-id="afb36-163">Om du väljer **Källskattetransaktioner** för att visa de olika TDS-transaktionerna som kvittades för perioden, visas följande information.</span><span class="sxs-lookup"><span data-stu-id="afb36-163">If you select **Withholding tax transactions** to view the different TDS transactions that were settled for the period, the following information is shown.</span></span>

| <span data-ttu-id="afb36-164">TDS-belopp</span><span class="sxs-lookup"><span data-stu-id="afb36-164">TDS amount</span></span> |
|------------|
| <span data-ttu-id="afb36-165">16,995.00</span><span class="sxs-lookup"><span data-stu-id="afb36-165">16,995.00</span></span>  |
| <span data-ttu-id="afb36-166">22,660.00</span><span class="sxs-lookup"><span data-stu-id="afb36-166">22,660.00</span></span>  |
| <span data-ttu-id="afb36-167">28,325.00</span><span class="sxs-lookup"><span data-stu-id="afb36-167">28,325.00</span></span>  |
| <span data-ttu-id="afb36-168">16,995.00</span><span class="sxs-lookup"><span data-stu-id="afb36-168">16,995.00</span></span>  |
| <span data-ttu-id="afb36-169">28,325.00</span><span class="sxs-lookup"><span data-stu-id="afb36-169">28,325.00</span></span>  |
| <span data-ttu-id="afb36-170">16,995.00</span><span class="sxs-lookup"><span data-stu-id="afb36-170">16,995.00</span></span>  |
| <span data-ttu-id="afb36-171">11,330.00</span><span class="sxs-lookup"><span data-stu-id="afb36-171">11,330.00</span></span>  |

<span data-ttu-id="afb36-172">För ett specfikt TDS-belopp kan du välja **Källskattekomponenter** för att visa TDS som beräknades per TDS-skattekomponent för en specifik TDS-skattekod.</span><span class="sxs-lookup"><span data-stu-id="afb36-172">For a specific TDS amount, you can select **Withholding tax components** to view the TDS that was calculated per TDS tax component for a specific TDS tax code.</span></span> <span data-ttu-id="afb36-173">I det här exemplet väljer du **Källskattekomponenter** för TDS-beloppet 16 995,00.</span><span class="sxs-lookup"><span data-stu-id="afb36-173">For this example, you select **Withholding tax components** for the TDS amount 16,995.00.</span></span> <span data-ttu-id="afb36-174">Skattebeloppet som beräknades per komponent för transaktionen visas.</span><span class="sxs-lookup"><span data-stu-id="afb36-174">The tax amount that was calculated per component for the transaction is shown.</span></span>

| <span data-ttu-id="afb36-175">Momskomponent</span><span class="sxs-lookup"><span data-stu-id="afb36-175">Tax component</span></span> | <span data-ttu-id="afb36-176">Mängd</span><span class="sxs-lookup"><span data-stu-id="afb36-176">Amount</span></span>    | <span data-ttu-id="afb36-177">Ackumulerat belopp</span><span class="sxs-lookup"><span data-stu-id="afb36-177">Accumulated amount</span></span> |
|---------------|-----------|--------------------|
| <span data-ttu-id="afb36-178">TDS</span><span class="sxs-lookup"><span data-stu-id="afb36-178">TDS</span></span>           | <span data-ttu-id="afb36-179">1,5000.00</span><span class="sxs-lookup"><span data-stu-id="afb36-179">1,5000.00</span></span> | <span data-ttu-id="afb36-180">125,000.00</span><span class="sxs-lookup"><span data-stu-id="afb36-180">125,000.00</span></span>         |
| <span data-ttu-id="afb36-181">Tillägg</span><span class="sxs-lookup"><span data-stu-id="afb36-181">Surcharge</span></span>     | <span data-ttu-id="afb36-182">1,500.00</span><span class="sxs-lookup"><span data-stu-id="afb36-182">1,500.00</span></span>  | <span data-ttu-id="afb36-183">12,500.00</span><span class="sxs-lookup"><span data-stu-id="afb36-183">12,500.00</span></span>          |
| <span data-ttu-id="afb36-184">PE-Cess</span><span class="sxs-lookup"><span data-stu-id="afb36-184">PE-Cess</span></span>       | <span data-ttu-id="afb36-185">330.00</span><span class="sxs-lookup"><span data-stu-id="afb36-185">330.00</span></span>    | <span data-ttu-id="afb36-186">2,750.00</span><span class="sxs-lookup"><span data-stu-id="afb36-186">2,750.00</span></span>           |
| <span data-ttu-id="afb36-187">SHE Cess</span><span class="sxs-lookup"><span data-stu-id="afb36-187">SHE Cess</span></span>      | <span data-ttu-id="afb36-188">165.00</span><span class="sxs-lookup"><span data-stu-id="afb36-188">165.00</span></span>    | <span data-ttu-id="afb36-189">1,375.00</span><span class="sxs-lookup"><span data-stu-id="afb36-189">1,375.00</span></span>           |

<span data-ttu-id="afb36-190">Om du endast har valt TDS-beloppen 16 995,00, 22 660,00 och 28 325,00 för kvittning på sidan **Källskattetransaktioner**, visas det totala kvittningsbeloppet som **67 980,00** i fältet **Korrigering** på sidan **Öppna transaktionsredigering**.</span><span class="sxs-lookup"><span data-stu-id="afb36-190">If you selected only the TDS amounts 16,995.00, 22,660.00, and 2,8325.00 for settlement on the **Withholding tax transactions** page, the total amount for settlement is shown as **67,980.00** in the **Correction** field on the **Open transaction editing** page.</span></span> <span data-ttu-id="afb36-191">Om den här transaktionen markeras för kvittning och sidan **Öppna transaktionsredigering** är stängd, visas beloppet **67 980,00** i fältet **Debet** på sidan **Journalverifikation**.</span><span class="sxs-lookup"><span data-stu-id="afb36-191">If this transaction is marked for settlement, and the **Open transaction editing** page is closed, the amount **67,980.00** is shown in the **Debit** field on the **Journal voucher** page.</span></span>

<span data-ttu-id="afb36-192">Du kan nu bokföra journalen och generera TDS-challan.</span><span class="sxs-lookup"><span data-stu-id="afb36-192">You can now post the journal and generate the TDS challan.</span></span>

### <a name="adjustment-of-advance-payments-that-are-made-to-tds-authority-vendors"></a><span data-ttu-id="afb36-193">Justering av förskottsbetalningar som görs till leverantörer inom TDS-myndigheter</span><span class="sxs-lookup"><span data-stu-id="afb36-193">Adjustment of advance payments that are made to TDS authority vendors</span></span>

<span data-ttu-id="afb36-194">yOm du vill justera en förskottsbetalning som gjorts till TDS-myndigheten till en faktisk betalning, går du till **Leverantörsreskontra \> Leverantörer \> Alla leverantörer \> Transaktionsredigering**.</span><span class="sxs-lookup"><span data-stu-id="afb36-194">To adjust an advance payment that was made to the TDS authority vendor to an actual payment, go to **Accounts payable \> Vendors \> All vendors \> Transactions editing**.</span></span> <span data-ttu-id="afb36-195">Om den faktiska betalningen som görs överskrider förskottsbetalningen genereras två challan-nummer för transaktionen.</span><span class="sxs-lookup"><span data-stu-id="afb36-195">If the actual payment that is made exceeds the advance payment, two challan numbers are generated for the transaction.</span></span> <span data-ttu-id="afb36-196">Det är dock endast det första challan-numret som visas i TDS-frågan.</span><span class="sxs-lookup"><span data-stu-id="afb36-196">However, only the first challan number is shown in the TDS inquiry.</span></span>
