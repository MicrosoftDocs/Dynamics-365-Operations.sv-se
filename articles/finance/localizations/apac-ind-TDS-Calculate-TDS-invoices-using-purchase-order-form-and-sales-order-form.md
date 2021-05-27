---
title: Beräkna TDS-fakturor med hjälp av inköpsorderformulär och försäljningsorderformulär
description: Det här ämnet visar en lista med stegen för beräkning av avdragen moms vid källan (TDS) på olika typer av fakturor.
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
ms.openlocfilehash: e7925206f3c060c6332de9d4972c8a7fb0066be2
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023588"
---
# <a name="calculate-tds-invoices-using-purchase-order-form-and-sales-order-form"></a><span data-ttu-id="bab4b-103">Beräkna TDS-fakturor med hjälp av inköpsorderformulär och försäljningsorderformulär</span><span class="sxs-lookup"><span data-stu-id="bab4b-103">Calculate TDS invoices using purchase order form and sales order form</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bab4b-104">Det här ämnet visar en lista med stegen för beräkning för avdragen moms vid källan (TDS) på olika typer av fakturor med sidorna **Inköpsorder**, **Inköpsjournal**, **Ramavtal** och **Försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="bab4b-104">This topic lists the steps for calculating Tax Deducted at Source (TDS) on various types of invoices using the **Purchase order**, **Purchase journal**, **Blanket order**, and **Sales order** pages.</span></span>

1. <span data-ttu-id="bab4b-105">Skapa en inköpsorder, inköpsjournal, inköpsramavtal eller en försäljningsorder med den sida som visas.</span><span class="sxs-lookup"><span data-stu-id="bab4b-105">Create a purchase order, purchase journal, purchase blanket order, or a sales order using the page listed.</span></span> <span data-ttu-id="bab4b-106">Ange den information som behövs.</span><span class="sxs-lookup"><span data-stu-id="bab4b-106">Enter the required details.</span></span>

2. <span data-ttu-id="bab4b-107">Välj fliken **Inställningar** vilken typ av bedömare leverantören eller kunden är.</span><span class="sxs-lookup"><span data-stu-id="bab4b-107">Select the **Setup** tab to view the nature of the assessee of the vendor or customer.</span></span> <span data-ttu-id="bab4b-108">Den här informationen visas i fältet **Typ av bedömare** under fältgruppen **Källskattegrupp**.</span><span class="sxs-lookup"><span data-stu-id="bab4b-108">This information is listed in the **Nature of assessee** field, under the **Withholding tax group** field group.</span></span>

3. <span data-ttu-id="bab4b-109">I fältet **TDS-grupp** visar eller modifierar du standard-TDS-gruppen som definierats för leverantören eller kunden.</span><span class="sxs-lookup"><span data-stu-id="bab4b-109">In the **TDS group** field, view or modify the default TDS group defined for the vendor or customer.</span></span>

   > [!NOTE]
   > <span data-ttu-id="bab4b-110">Fältet **TCS-grupp** är inte tillgängligt när du väljer en TDS-grupp i fältet **TDS-grupp**.</span><span class="sxs-lookup"><span data-stu-id="bab4b-110">The **TCS group** field isn't available when you select a TDS group in the **TDS group** field.</span></span> <span data-ttu-id="bab4b-111">TDS beräknas endast om kryssrutan **Beräkna källskatt** har markerats för leverantören eller kunden på sidan **Alla leverantörer** eller **Alla kunder**.</span><span class="sxs-lookup"><span data-stu-id="bab4b-111">TDS is calculated only if the **Calculate withholding tax** check box is selected for the vendor or customer on the **All vendors** or **All customers** page.</span></span>  

4. <span data-ttu-id="bab4b-112">Skapa artikelrader på fliken **Rader** och ange den information som krävs.</span><span class="sxs-lookup"><span data-stu-id="bab4b-112">Create item lines on the **Lines** tab and enter the required details.</span></span>

5. <span data-ttu-id="bab4b-113">Välj fliken **Inställningar** (radnivå) för att visa eller ändra TDS-gruppen som definierats på rubriknivå.</span><span class="sxs-lookup"><span data-stu-id="bab4b-113">Select the **Setup** tab (line-level) to view or change the TDS group defined at the header-level.</span></span> <span data-ttu-id="bab4b-114">TDS-gruppen visas i fältet **TDS-grupp**, som är under fältgruppen **Källskattegrupp**.</span><span class="sxs-lookup"><span data-stu-id="bab4b-114">The TDS group is displayed in the **TDS group** field, which is under the **Withholding tax group** field group.</span></span>

6. <span data-ttu-id="bab4b-115">Välj fliken **Skatteinformation** och välj alternativa adresser som har konfigurerats för företagsnamnet som visas i fältet.</span><span class="sxs-lookup"><span data-stu-id="bab4b-115">Select the **Tax information** tab and select alternate addresses that are set up for the company name that's displayed in this field.</span></span> <span data-ttu-id="bab4b-116">Företagsnamnet visas i fältet **Namn**, som är under fältgruppen **Företagsinformation**.</span><span class="sxs-lookup"><span data-stu-id="bab4b-116">The company name is displayed in the **Name** field, which is under the **Company information** field group.</span></span> 

   <span data-ttu-id="bab4b-117">TAN för det valda företagsnamnet visas i fältet **Skattekontonummer** (**TAN**), under fältgruppen **Källskatt**.</span><span class="sxs-lookup"><span data-stu-id="bab4b-117">The TAN of the selected company name is displayed in the **Tax Account Number** (**TAN**) field, under the **Withholding tax** field group.</span></span> 

7. <span data-ttu-id="bab4b-118">Välj **Källskatt** för att öppna sidan **Temporära källskattetransaktioner**.</span><span class="sxs-lookup"><span data-stu-id="bab4b-118">Select **Withholding tax** to open the **Temporary withholding tax transactions** page.</span></span> <span data-ttu-id="bab4b-119">Visa följande fält i det övre fönstret på sidan **Temporära källskattetransaktioner**.</span><span class="sxs-lookup"><span data-stu-id="bab4b-119">View the following fields on the upper pane of the **Temporary withholding tax transactions** page.</span></span>

   - <span data-ttu-id="bab4b-120">**Total källskatt** - Total TDS beräknad för transaktionen för TDS-gruppen.</span><span class="sxs-lookup"><span data-stu-id="bab4b-120">**Withholding** **tax** **amount** **in** **total** - The total TDS calculated for the transaction for the TDS group.</span></span>

   - <span data-ttu-id="bab4b-121">**Värde** – Den totala procentsatsen som används för att beräkna TDS för transaktionen.</span><span class="sxs-lookup"><span data-stu-id="bab4b-121">**Value** - The total percentage used to calculate TDS for the transaction.</span></span> <span data-ttu-id="bab4b-122">Den totala procentsatsen baseras på formeln som definieras för TDS-momskoder som är kopplade till TDS-gruppen.</span><span class="sxs-lookup"><span data-stu-id="bab4b-122">The total percentage is based on the formula that is defined for TDS tax codes attached to the TDS group.</span></span>

   - <span data-ttu-id="bab4b-123">**AJusterat totalt källskattebelopp** - Det totala justerade TDS-beloppet för alla momskoder i TDS-gruppen.</span><span class="sxs-lookup"><span data-stu-id="bab4b-123">**Adjusted withholding tax amount in total** - The total adjusted TDS amount for all tax codes in the TDS group.</span></span>

   - <span data-ttu-id="bab4b-124">**TDS** – Om detta väljs kopplas en TDS-grupp till transaktionen.</span><span class="sxs-lookup"><span data-stu-id="bab4b-124">**TDS** - If selected, a TDS group is attached to the transaction.</span></span>

<span data-ttu-id="bab4b-125">Fälten under flikarna **Översikt**, **Allmänt** och **Justering** på sidan **Temporära källskattetransaktioner** visar det beräknade TDS-beloppet och justerad TDS-beloppinformation för varje TDS-momskod som är kopplad till TDS-gruppen.</span><span class="sxs-lookup"><span data-stu-id="bab4b-125">The fields on the **Overview**, **General**, and **Adjustment** tabs on the **Temporary withholding tax transactions** page display the calculated TDS amount and adjusted TDS amount details for each TDS tax code attached to the TDS group.</span></span>

8. <span data-ttu-id="bab4b-126">Välj **Tröskel** för att öppna sidan **Tröskel**.</span><span class="sxs-lookup"><span data-stu-id="bab4b-126">Select **Threshold** to open the **Threshold** page.</span></span> <span data-ttu-id="bab4b-127">Visa den tröskelgräns som har definierats för den TDS-momskomponent som är kopplad till en specifik TDS-momskod på den här sidan.</span><span class="sxs-lookup"><span data-stu-id="bab4b-127">View the threshold limit defined for the TDS tax component attached to a specific TDS tax code on this page.</span></span>

9. <span data-ttu-id="bab4b-128">Välj **Formeldesigner** för att öppna sidan **Formeldesigner**.</span><span class="sxs-lookup"><span data-stu-id="bab4b-128">Select **Formula designer** to open the **Formula designer** page.</span></span> <span data-ttu-id="bab4b-129">Visa formeln som definieras för en specifik TDS-momskod på den här sidan.</span><span class="sxs-lookup"><span data-stu-id="bab4b-129">View the formula that is defined for a specific TDS tax code on this page.</span></span> 

10. <span data-ttu-id="bab4b-130">Bokför fakturan.</span><span class="sxs-lookup"><span data-stu-id="bab4b-130">Post the invoice.</span></span> <span data-ttu-id="bab4b-131">TDS-beloppet som beräknas på inköpsfakturor bokförs på leverantörsreskontrakontot och TDS-beloppet som beräknas på försäljningsfakturor bokförs på kundreskontrakontot som har definierats för varje TDS-momskod i TDS-gruppen.</span><span class="sxs-lookup"><span data-stu-id="bab4b-131">The TDS amount calculated on purchase invoices is posted to the payable account and the TDS amount calculated on sales invoices is posted to the receivable account that is defined for each TDS tax code in the TDS group.</span></span> <span data-ttu-id="bab4b-132">Leverantörsreskontrakontona och kundreskontrakontona för TDS-skattekoder definieras på sidan **Källskattekoder**.</span><span class="sxs-lookup"><span data-stu-id="bab4b-132">The payable accounts or receivable accounts for TDS tax codes are defined on the **Withholding tax codes** page.</span></span>

11. <span data-ttu-id="bab4b-133">Välj knappen **Fråga** **> Faktura > Bokförd källskatt** för att öppna sidan **Källskattetransaktioner**.</span><span class="sxs-lookup"><span data-stu-id="bab4b-133">Select **Inquiry** button **> Invoice > Posted withholding tax** button to open the **Withholding tax transactions** page.</span></span> <span data-ttu-id="bab4b-134">Du kan visa den totala procentsatsen som används för att beräkna TDS för transaktionen i fältet **Värde**.</span><span class="sxs-lookup"><span data-stu-id="bab4b-134">You can view the total percentage used to calculate TDS for the transaction in the **Value** field.</span></span>

<span data-ttu-id="bab4b-135">Fälten under flikarna **Översikt**, **Allmänt** och **Belopp** på sidan **Källskattetransaktioner** visar informationen för TDS som beräknats för transaktionen.</span><span class="sxs-lookup"><span data-stu-id="bab4b-135">The fields on the **Overview**, **General**, and **Amount** tabs on the **Withholding tax transactions** page display the information of TDS calculated for the transaction.</span></span> <span data-ttu-id="bab4b-136">Visa TDS-beräkningsinformation för varje TDS-momskod som är kopplad till TDS-gruppen.</span><span class="sxs-lookup"><span data-stu-id="bab4b-136">View the TDS calculation information for each TDS tax code attached to the TDS group.</span></span>
