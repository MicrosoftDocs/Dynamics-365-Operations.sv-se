---
title: TDS-beräkning på fakturor från sidan Fritextfaktura
description: I det här avsnittet beskrivs hur du beräknar skatteavdrag vid källan (TDS) på fakturor med hjälp av sidan Fritextfaktura.
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
ms.openlocfilehash: 7d551a8ba6ba9ca282fd9de3fa7d7c7303e394ed
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023604"
---
# <a name="tds-calculation-on-invoices-from-the-free-text-invoice-page"></a><span data-ttu-id="04b2b-103">TDS-beräkning på fakturor från sidan Fritextfaktura</span><span class="sxs-lookup"><span data-stu-id="04b2b-103">TDS calculation on invoices from the Free text invoice page</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="04b2b-104">I det här avsnittet beskrivs hur du beräknar skatteavdrag vid källan (TDS) på fakturor med hjälp av sidan **Fritextfaktura**.</span><span class="sxs-lookup"><span data-stu-id="04b2b-104">This topic explains how to calculate Tax Deducted at Source (TDS) on invoices by using the **Free text invoice** page.</span></span>

1. <span data-ttu-id="04b2b-105">Gå till **Kundreskontra \> Fakturor \> Alla fritextfakturor**.</span><span class="sxs-lookup"><span data-stu-id="04b2b-105">Go to **Accounts receivable \> Invoices \> All free text invoices**.</span></span>

    <span data-ttu-id="04b2b-106">[![Sidan Fritextfakturor](./media/apac-ind-TDS-57-1.png)](./media/apac-ind-TDS-57-1.png)</span><span class="sxs-lookup"><span data-stu-id="04b2b-106">[![Free text invoice page](./media/apac-ind-TDS-57-1.png)](./media/apac-ind-TDS-57-1.png)</span></span>

2. <span data-ttu-id="04b2b-107">Välj **Ny** för att skapa en fritextfaktura och ange den information som krävs.</span><span class="sxs-lookup"><span data-stu-id="04b2b-107">Select **New** to create a free text invoice, and enter the required details.</span></span>
3. <span data-ttu-id="04b2b-108">Välj fliken **Faktura**. I avsnittet **Källskattegrupp** visar fältet **Typ av bedömare** kundens typ av bedömningskategori.</span><span class="sxs-lookup"><span data-stu-id="04b2b-108">Select the **Invoice** tab. In the **Withholding tax group** section, the **Nature of assessee** field shows the nature of assessee category of the customer.</span></span>
4. <span data-ttu-id="04b2b-109">I fältet **TDS-grupp** granskar eller ändrar du standard-TDS-gruppen som definierats för kunden.</span><span class="sxs-lookup"><span data-stu-id="04b2b-109">In the **TDS group** field, review or change the default TDS group that is defined for the customer.</span></span>

    > [!NOTE]
    > <span data-ttu-id="04b2b-110">När du väljer ett värde i fältet **TDS-grupp** blir fältet **TCS-grupp** otillgängligt.</span><span class="sxs-lookup"><span data-stu-id="04b2b-110">When you select a value in the **TDS group** field, the **TCS group** field becomes unavailable.</span></span> <span data-ttu-id="04b2b-111">TDS beräknas endast om alternativet **Beräkna källskatt** har ställts in på **Ja** för kunden på sidan **Alla kunder**.</span><span class="sxs-lookup"><span data-stu-id="04b2b-111">TDS is calculated only if the **Calculate withholding tax** option is set to **Yes** for the customer on the **All customers** page.</span></span>

5. <span data-ttu-id="04b2b-112">Under fliken **Skatteinformation**, i avsnittet **Företagsinformation**, i fältet **Namn**, väljer du företagsnamnet för en alternativ adress som har konfigurerats för företaget.</span><span class="sxs-lookup"><span data-stu-id="04b2b-112">On the **Tax information** tab, in the **Company information** section, in the **Name** field, select the company name for an alternate address that has been set up for the company.</span></span>

    <span data-ttu-id="04b2b-113">I avsnittet **Källskatt** visar fältet **Skattekontonummer (TAN)** skattekontonumret (TAN) för det valda företaget.</span><span class="sxs-lookup"><span data-stu-id="04b2b-113">In the **Withholding tax** section, the **Tax Account Number (TAN)** field shows the tax account number (TAN) for the selected company.</span></span>

6. <span data-ttu-id="04b2b-114">Under fliken **Fakturarader** skapar du fakturarader och anger den information som krävs.</span><span class="sxs-lookup"><span data-stu-id="04b2b-114">On the **Invoice lines** tab, create invoice lines, and enter the required details.</span></span>

    <span data-ttu-id="04b2b-115">I avsnittet **Källskattegrupp** visar fältet **Skattekontonummer (TAN)** TAN, och fältet **TDS-grupp** visar TDS-gruppen.</span><span class="sxs-lookup"><span data-stu-id="04b2b-115">In the **Withholding tax group** section, the **Tax Account Number (TAN)** field shows the TAN, and the **TDS group** field shows the TDS group.</span></span>

7. <span data-ttu-id="04b2b-116">Välj **Källskatt** för att öppna sidan **Temporära källskattetransaktioner**.</span><span class="sxs-lookup"><span data-stu-id="04b2b-116">Select **Withholding tax** to open the **Temporary withholding tax transactions** page.</span></span> <span data-ttu-id="04b2b-117">Den övre delen av den här sidan har följande fält:</span><span class="sxs-lookup"><span data-stu-id="04b2b-117">The upper part of this page has the following fields:</span></span>

    - <span data-ttu-id="04b2b-118">**Totalt källskattebelopp** – Total TDS beräknad för transaktionen för TDS-gruppen.</span><span class="sxs-lookup"><span data-stu-id="04b2b-118">**Withholding tax amount in total** – The total TDS that was calculated for the transaction for the TDS group.</span></span>
    - <span data-ttu-id="04b2b-119">**Värde** – Den totala procentsatsen som används för att beräkna TDS för transaktionen.</span><span class="sxs-lookup"><span data-stu-id="04b2b-119">**Value** – The total percentage that was used to calculate TDS for the transaction.</span></span> <span data-ttu-id="04b2b-120">Den totala procentsatsen baseras på formeln som definieras för TDS-skattekoder som är kopplade till TDS-gruppen.</span><span class="sxs-lookup"><span data-stu-id="04b2b-120">The total percentage is based on the formula that is defined for the TDS tax codes and attached to the TDS group.</span></span>
    - <span data-ttu-id="04b2b-121">**Justerat totalt källskattebelopp** – Det totala justerade TDS-beloppet för alla momskoder i TDS-gruppen.</span><span class="sxs-lookup"><span data-stu-id="04b2b-121">**Adjusted withholding tax amount in total** – The total adjusted TDS amount for all tax codes in the TDS group.</span></span>
    - <span data-ttu-id="04b2b-122">**TDS** – En markerad kryssruta anger att en TDS-grupp är kopplad till transaktionen.</span><span class="sxs-lookup"><span data-stu-id="04b2b-122">**TDS** – A selected checkbox indicates that a TDS group is attached to the transaction.</span></span>

    <span data-ttu-id="04b2b-123">Fälten under flikarna **Översikt**, **Allmänt** och **Justering** visar det beräknade TDS-beloppet och information om justerat TDS-belopp för varje TDS-skattekod som är kopplad till TDS-gruppen.</span><span class="sxs-lookup"><span data-stu-id="04b2b-123">The fields on the **Overview**, **General**, and **Adjustment** tabs show the calculated TDS amount and details of the adjusted TDS amount for each TDS tax code that is attached to the TDS group.</span></span>

8. <span data-ttu-id="04b2b-124">Välj **Tröskel** för att öppna sidan **Tröskel**, där du kan granska tröskelgränsen som har definierats för TDS-skattekomponenten som är kopplad till en specifik TDS-skattekod.</span><span class="sxs-lookup"><span data-stu-id="04b2b-124">Select **Threshold** to open the **Threshold** page, where you can review the threshold limit that is defined for the TDS tax component that is attached to a specific TDS tax code.</span></span>
9. <span data-ttu-id="04b2b-125">Välj **Formeldesigner** för att öppna sidan **Formeldesigner**, där du kan granska formeln som definierats för en specifik TDS-skattekod.</span><span class="sxs-lookup"><span data-stu-id="04b2b-125">Select **Formula designer** to open the **Formula designer** page, where you can review the formula that is defined for a specific TDS tax code.</span></span>
10. <span data-ttu-id="04b2b-126">Bokför fritextfakturan.</span><span class="sxs-lookup"><span data-stu-id="04b2b-126">Post the free text invoice.</span></span> <span data-ttu-id="04b2b-127">Det TDS-belopp som beräknas på fritextfakturor bokförs på det kundreskontrakonto som har definierats för varje TDS-momskod i TDS-gruppen.</span><span class="sxs-lookup"><span data-stu-id="04b2b-127">The TDS amount that is calculated for the free text invoice is posted to the receivable account that is defined for each TDS tax code in the TDS group.</span></span> <span data-ttu-id="04b2b-128">Kundreskontrakontona för TDS-skattekoder definieras på sidan **Källskattekoder**.</span><span class="sxs-lookup"><span data-stu-id="04b2b-128">The receivable accounts for TDS tax codes are defined on the **Withholding tax codes** page.</span></span>
11. <span data-ttu-id="04b2b-129">Välj **Bokförd källskatt** för att öppna sidan **Källskattetransaktioner**.</span><span class="sxs-lookup"><span data-stu-id="04b2b-129">Select **Posted withholding tax** to open the **Withholding tax transactions** page.</span></span> <span data-ttu-id="04b2b-130">I fältet **Värde** visas den totala procentsatsen som användes för att beräkna TDS för transaktionen.</span><span class="sxs-lookup"><span data-stu-id="04b2b-130">The **Value** field shows the total percentage that was used to calculate TDS for the transaction.</span></span>

    <span data-ttu-id="04b2b-131">Fälten under flikarna **Översikt**, **Allmänt** och **Belopp** visar TDS-beloppen som beräknats på fakturaraderna.</span><span class="sxs-lookup"><span data-stu-id="04b2b-131">The fields on the **Overview**, **General**, and **Amount** tabs show the TDS amounts that were calculated on the invoice lines.</span></span>

12. <span data-ttu-id="04b2b-132">Granska TDS-beräkningsinformation för varje TDS-skattekod som är kopplad till TDS-gruppen.</span><span class="sxs-lookup"><span data-stu-id="04b2b-132">Review the TDS calculation information for each TDS tax code that is attached to the TDS group.</span></span>
