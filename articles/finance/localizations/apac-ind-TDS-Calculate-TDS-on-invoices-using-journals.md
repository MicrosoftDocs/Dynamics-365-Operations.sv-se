---
title: Beräkna TDS på fakturor med journaler
description: Det här ämnet visar en lista med stegen för beräkning av avdragen moms vid källan (TDS) på journaler.
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
ms.openlocfilehash: d68e1b3a4dc31823ec56a525149f16bdc23c0883
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023612"
---
# <a name="calculate-tds-on-invoices-using-journals"></a><span data-ttu-id="ea67d-103">Beräkna TDS på fakturor med journaler</span><span class="sxs-lookup"><span data-stu-id="ea67d-103">Calculate TDS on invoices using journals</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ea67d-104">Det här ämnet visar en lista med stegen för beräkning av avdragen moms vid källan (TDS) på journaler.</span><span class="sxs-lookup"><span data-stu-id="ea67d-104">This topic lists the steps for calculating Tax Deducted at Source (TDS) on journals.</span></span>

<span data-ttu-id="ea67d-105">Börja med att öppna sidan **Allmänna journaler** (**Redovisning > Journalposter > Allmänna journaler**).</span><span class="sxs-lookup"><span data-stu-id="ea67d-105">Begin by opening the **General journals** page (**General ledger > Journal entries > General journals**).</span></span>

<span data-ttu-id="ea67d-106">[![Allmänna journaler](./media/apac-ind-TDS-57.png)](./media/apac-ind-TDS-57.png)</span><span class="sxs-lookup"><span data-stu-id="ea67d-106">[![General journals](./media/apac-ind-TDS-57.png)](./media/apac-ind-TDS-57.png)</span></span>

1. <span data-ttu-id="ea67d-107">Skapa journalrader med hjälp av journalformulären som visas i tabellen.</span><span class="sxs-lookup"><span data-stu-id="ea67d-107">Create journal lines using the journal forms that are listed in the table.</span></span> <span data-ttu-id="ea67d-108">Välj kontotyp och motkontotyp och ange transaktionsbeloppet.</span><span class="sxs-lookup"><span data-stu-id="ea67d-108">Select the account type and offset account type and enter the amount for the transaction.</span></span> 

   > [!NOTE]
   > <span data-ttu-id="ea67d-109">På sidan **Journal för fakturagodkännande** väljer du **Hitta verifikationer** och välj fakturor att beräkna TDS på.</span><span class="sxs-lookup"><span data-stu-id="ea67d-109">On the **Invoice approval journal** page, select **Find vouchers** and select invoices to calculate TDS on.</span></span> <span data-ttu-id="ea67d-110">Visa fakturor som skapats på sidan **Fakturaregister** eller sidan **Hitta verifikationer**.</span><span class="sxs-lookup"><span data-stu-id="ea67d-110">View the invoices created in the **Invoice register** page or the **Find vouchers** page.</span></span>  

2. <span data-ttu-id="ea67d-111">Under fliken **Allmänt** på sidan **Journalverifikation** visar eller modifierar du standard-TDS-gruppen som definierats för leverantören eller kunden i fältet **TDS-grupp**.</span><span class="sxs-lookup"><span data-stu-id="ea67d-111">On the **General** tab of the **Journal voucher** page, view or modify the default TDS group defined for the vendor or customer, in the **TDS group** field.</span></span> <span data-ttu-id="ea67d-112">TDS-beloppet som beräknas på journalrader baseras på formeln som definierats för TDS-momskoderna som listas i fältet **TDS-grupp**.</span><span class="sxs-lookup"><span data-stu-id="ea67d-112">The TDS amount that's calculated on journal lines is based on the formula defined for the TDS tax codes listed in the **TDS group** field.</span></span> 

   > [!NOTE]
   > <span data-ttu-id="ea67d-113">Fältet **Källskattegrupp** och fältet **TCS-grupp** blir otillgängligt när du väljer en TDS-grupp i fältet **TDS-grupp**.</span><span class="sxs-lookup"><span data-stu-id="ea67d-113">The **Withholding tax group**  field and the **TCS group** field become unavailable when you select a TDS group in the **TDS group** field.</span></span> <span data-ttu-id="ea67d-114">Fältet **Källskattegrupp** är endast tillgängligt på sidan **Allmän journal**.</span><span class="sxs-lookup"><span data-stu-id="ea67d-114">The **Withholding tax group** field is available only on the **General journal** page.</span></span> <span data-ttu-id="ea67d-115">TDS beräknas endast om kryssrutan **Beräkna källskatt** har markerats för leverantören eller kunden på sidan **Alla leverantörer** eller **Alla kunder**.</span><span class="sxs-lookup"><span data-stu-id="ea67d-115">TDS is calculated only if the **Calculate withholding tax** check box is selected for the vendor or customer on the **All vendors** or **All customers** pages.</span></span>   

3. <span data-ttu-id="ea67d-116">Välj fliken **Skatteinformation**. Välj alternativa adresser för ett företag som har konfigurerats för företaget i fältet, om så krävs.</span><span class="sxs-lookup"><span data-stu-id="ea67d-116">Select the **Tax information** tab. Select the alternate addresses of a company that's set up for the company in this field, if required.</span></span> <span data-ttu-id="ea67d-117">Du kan visa företagsnamnet visas i fältet **Namn**, som är under fältgruppen **Företagsinformation**.</span><span class="sxs-lookup"><span data-stu-id="ea67d-117">You can view the company name in the **Name** field, which is under the **Company information** field group.</span></span> 

4. <span data-ttu-id="ea67d-118">Visa leverantörens eller kundens bedömningskategori i fältet **Typ av bedömare**, som är under fältgruppen **Källskatt**.</span><span class="sxs-lookup"><span data-stu-id="ea67d-118">View the nature of assessee category of the vendor or customer in the **Nature of assessee** field, which is under the **Withholding tax** field group.</span></span> <span data-ttu-id="ea67d-119">I fältet **Skattekontonummer** (**TAN**) visas TAN för det företagsnamn som visas.</span><span class="sxs-lookup"><span data-stu-id="ea67d-119">In the **Tax Account Number** (**TAN**) field, view the TAN of the selected company name that's displayed.</span></span>  

5. <span data-ttu-id="ea67d-120">Välj **Källskatt** i menyn **Källskatt** för att öppna sidan **Temporära källskattetransaktioner**.</span><span class="sxs-lookup"><span data-stu-id="ea67d-120">Select **Withholding tax** in **Withholding tax** menu to open the **Temporary withholding tax transactions** page.</span></span> <span data-ttu-id="ea67d-121">Följande fält visas i det övre fönstret på sidan **Temporära källskattetransaktioner**.</span><span class="sxs-lookup"><span data-stu-id="ea67d-121">The following fields are displayed on the upper pane of the **Temporary withholding tax transactions** page.</span></span>

   - <span data-ttu-id="ea67d-122">**Total källskattebelopp** - Total TDS beräknad för transaktionen för TDS-gruppen.</span><span class="sxs-lookup"><span data-stu-id="ea67d-122">**Withholding tax amount in total** - The total TDS calculated for the transaction for the TDS group.</span></span>

   - <span data-ttu-id="ea67d-123">**Värde** – Den totala procentsatsen som används för att beräkna TDS för transaktionen.</span><span class="sxs-lookup"><span data-stu-id="ea67d-123">**Value** - The total percentage used to calculate TDS for the transaction.</span></span> <span data-ttu-id="ea67d-124">Den totala procentsatsen baseras på formeln som definieras för TDS-momskoder som är kopplade till TDS-gruppen.</span><span class="sxs-lookup"><span data-stu-id="ea67d-124">The total percentage is based on the formula that is defined for TDS tax codes attached to the TDS group.</span></span>

   - <span data-ttu-id="ea67d-125">**AJusterat totalt källskattebelopp** - Det totala justerade TDS-beloppet för alla momskoder i TDS-gruppen.</span><span class="sxs-lookup"><span data-stu-id="ea67d-125">**Adjusted withholding tax amount in total** - The total adjusted TDS amount for all tax codes in the TDS group.</span></span>

   - <span data-ttu-id="ea67d-126">**TDS** – Om detta väljs kopplas en TDS-grupp till transaktionen.</span><span class="sxs-lookup"><span data-stu-id="ea67d-126">**TDS** - If selected, a TDS group is attached to the transaction.</span></span>

  <span data-ttu-id="ea67d-127">Fälten under flikarna **Översikt**, **Allmänt** och **Justering** på sidan **Temporära källskattetransaktioner** visar det beräknade TDS-beloppet och justerad TDS-beloppinformation för varje TDS-momskod som är kopplad till TDS-gruppen.</span><span class="sxs-lookup"><span data-stu-id="ea67d-127">The fields on the **Overview**, **General**, and **Adjustment** tabs on the **Temporary withholding tax transactions** page display the calculated TDS amount and adjusted TDS amount details for each TDS tax code attached to the TDS group.</span></span>

6. <span data-ttu-id="ea67d-128">Välj **Tröskel** för att öppna sidan **Tröskel**.</span><span class="sxs-lookup"><span data-stu-id="ea67d-128">Select **Threshold** to open the **Threshold** page.</span></span> <span data-ttu-id="ea67d-129">Visa den tröskelgräns och det undantag som har definierats för den TDS-momskomponent som är kopplad till en specifik TDS-momskod på den här sidan.</span><span class="sxs-lookup"><span data-stu-id="ea67d-129">View the threshold limit and exception threshold limit defined for the TDS tax component attached to a specific TDS tax code on this page.</span></span>

   <span data-ttu-id="ea67d-130">Välj **Formeldesigner** för att öppna formuläret **Formeldesigner**.</span><span class="sxs-lookup"><span data-stu-id="ea67d-130">Select **Formula designer** to open the **Formula designer** form.</span></span> <span data-ttu-id="ea67d-131">Visa formeln som definieras för en specifik TDS-momskod på den här sidan.</span><span class="sxs-lookup"><span data-stu-id="ea67d-131">View the formula defined for a specific TDS tax code in this page.</span></span> <span data-ttu-id="ea67d-132">Stäng sidorna **Formeldesigner** och **Temporära källskattetransaktioner** för att återgå till sidan **Journalverifikation**.</span><span class="sxs-lookup"><span data-stu-id="ea67d-132">Close the **Formula designer** and **Temporary withholding tax transactions** pages to return to the **Journal voucher** page.</span></span>

8. <span data-ttu-id="ea67d-133">Ange andra uppgifter som behövs.</span><span class="sxs-lookup"><span data-stu-id="ea67d-133">Enter the other required details.</span></span> <span data-ttu-id="ea67d-134">Validera och bokför journalen.</span><span class="sxs-lookup"><span data-stu-id="ea67d-134">Validate and post the journal.</span></span> <span data-ttu-id="ea67d-135">Det TDS-belopp som beräknas på inköpsfakturor bokförs på leverantörsreskontrakontot.</span><span class="sxs-lookup"><span data-stu-id="ea67d-135">The TDS amount that's calculated on purchase invoices is posted to the payable account.</span></span> <span data-ttu-id="ea67d-136">Det TDS-belopp som beräknas på försäljningsfakturor bokförs på det kundreskontrakonto som har definierats för varje TDS-momskod i TDS-gruppen.</span><span class="sxs-lookup"><span data-stu-id="ea67d-136">The TDS amount that's calculated on sales invoices is posted to the receivable account that is defined for each TDS tax code in the TDS group.</span></span> <span data-ttu-id="ea67d-137">Leverantörsreskontrakontona och kundreskontrakontona för TDS-skattekoder definieras på sidan **Källskattekoder**.</span><span class="sxs-lookup"><span data-stu-id="ea67d-137">The payable accounts or receivable accounts for TDS tax codes are defined on the **Withholding tax codes** page.</span></span>

9. <span data-ttu-id="ea67d-138">Välj **Bokförd källskatt** för att öppna sidan **Källskattetransaktioner**.</span><span class="sxs-lookup"><span data-stu-id="ea67d-138">Select **Posted withholding tax** to open the **Withholding** **tax** **transactions** page.</span></span> <span data-ttu-id="ea67d-139">I fältet **Värde** visas den totala procentsats som användes för att beräkna TDS för transaktionen.</span><span class="sxs-lookup"><span data-stu-id="ea67d-139">In the **Value** field, the total percentage used to calculate TDS for the transaction is displayed.</span></span>

   <span data-ttu-id="ea67d-140">Fälten under flikarna **Översikt**, **Allmänt** och **Belopp** på sidan Källskattetransaktioner visar det beräknade TDS-beloppet och justerad TDS-beloppinformation för varje TDS-momskod som är kopplad till TDS-gruppen.</span><span class="sxs-lookup"><span data-stu-id="ea67d-140">The fields on the **Overview**, **General**, and **Amount** tabs in the Withholding tax transactions page display the calculated TDS amount and adjusted TDS amount details for each TDS tax code attached to the TDS group.</span></span>
