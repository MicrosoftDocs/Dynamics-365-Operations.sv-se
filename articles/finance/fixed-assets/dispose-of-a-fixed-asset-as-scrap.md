---
title: Kassering av avyttrade anläggningstillgångar
description: Ämnet beskriver hur du eliminerar transaktioner för en anläggningstillgång som avsatts som kassation.
author: moaamer
manager: Ann Beebe
ms.date: 08/14/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2019-08-14
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 4dee4468079a9ad500f513900cec090acf6026ce
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4969138"
---
# <a name="dispose-of-a-fixed-asset-as-scrap"></a><span data-ttu-id="915be-103">Kassering av avyttrade anläggningstillgångar</span><span class="sxs-lookup"><span data-stu-id="915be-103">Dispose of a fixed asset as scrap</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="915be-104">Ämnet beskriver hur du eliminerar transaktioner för en anläggningstillgång som avsatts som kassation.</span><span class="sxs-lookup"><span data-stu-id="915be-104">The topic describes the process of eliminating transactions for a fixed asset that was disposed of as scrap.</span></span> <span data-ttu-id="915be-105">Transaktionstyperna som kan elimineras inkluderar en tillgångs anskaffningsvärde och ackumulerade avskrivningstransaktioner och andra transaktioner för anläggningstillgångar.</span><span class="sxs-lookup"><span data-stu-id="915be-105">The transaction types that can be eliminated include an asset's acquisition and accumulated depreciation transactions and other fixed asset transactions.</span></span> <span data-ttu-id="915be-106">Eliminering av dessa transaktioner påverkar balansräkningskonton, till exempel anskaffningsjustering, avskrivningsjustering, omvärdering, uppskrivningskonton och nedskrivningskonton.</span><span class="sxs-lookup"><span data-stu-id="915be-106">Elimination of these transactions affects balance sheet accounts, such as acquisition adjustment, depreciation adjustment, revaluation, write-up, and write-down accounts.</span></span>

| <span data-ttu-id="915be-107">Transaktion</span><span class="sxs-lookup"><span data-stu-id="915be-107">Transaction</span></span>                                         | <span data-ttu-id="915be-108">Debet (Dr.)</span><span class="sxs-lookup"><span data-stu-id="915be-108">Debit (Dr.)</span></span> | <span data-ttu-id="915be-109">Kredit (Cr.)</span><span class="sxs-lookup"><span data-stu-id="915be-109">Credit (Cr.)</span></span> |
|-----------------------------------------------------|-------------|--------------|
| <span data-ttu-id="915be-110">Dr. Ackumulerad avskrivning</span><span class="sxs-lookup"><span data-stu-id="915be-110">Dr. Accumulated depreciation</span></span>                        | <span data-ttu-id="915be-111">X</span><span class="sxs-lookup"><span data-stu-id="915be-111">X</span></span>           |              |
| <span data-ttu-id="915be-112">Cr. Anläggningstillgångars vinst/förlust</span><span class="sxs-lookup"><span data-stu-id="915be-112">Cr. Fixed assets gain/loss</span></span>                          |             | <span data-ttu-id="915be-113">X</span><span class="sxs-lookup"><span data-stu-id="915be-113">X</span></span>            |
| <span data-ttu-id="915be-114">Dr. Anläggningstillgångars vinst/förlust</span><span class="sxs-lookup"><span data-stu-id="915be-114">Dr. Fixed assets gain/loss</span></span>                          | <span data-ttu-id="915be-115">X</span><span class="sxs-lookup"><span data-stu-id="915be-115">X</span></span>           |              |
| <span data-ttu-id="915be-116">Cr. Konto för anskaffning av anläggningstillgång</span><span class="sxs-lookup"><span data-stu-id="915be-116">Cr. Fixed asset acquisition account</span></span>                 |             | <span data-ttu-id="915be-117">X</span><span class="sxs-lookup"><span data-stu-id="915be-117">X</span></span>            |
| <span data-ttu-id="915be-118">Dr. Anläggningstillgångars vinst/förlust (bokfört nettovärde \[NBV\])</span><span class="sxs-lookup"><span data-stu-id="915be-118">Dr. Fixed assets gain/loss (net book value \[NBV\])</span></span> | <span data-ttu-id="915be-119">X</span><span class="sxs-lookup"><span data-stu-id="915be-119">X</span></span>           |              |
| <span data-ttu-id="915be-120">Cr. Anläggningstillgångars vinst/förlust (NBV)</span><span class="sxs-lookup"><span data-stu-id="915be-120">Cr. Fixed assets gain/loss (NBV)</span></span>                    |             | <span data-ttu-id="915be-121">X</span><span class="sxs-lookup"><span data-stu-id="915be-121">X</span></span>            |

> [!NOTE]
> <span data-ttu-id="915be-122">Vi rekommenderar att du samarbetar med företagets ekonomichef (CFO) eller controller för att identifiera de korrekta konton som ska användas för varje transaktionstyp och även för att verifiera att kasseringsprocessen och transaktionerna som den genererar uppdaterar dessa konton korrekt.</span><span class="sxs-lookup"><span data-stu-id="915be-122">We recommend that you work closely with your company's chief financial officer (CFO) or controller to identify the correct accounts that should be used for each transaction type, and also to verify that the disposal process and the transactions that it generates update those accounts correctly.</span></span>

<span data-ttu-id="915be-123">Innan du avyttrar en anläggningstillgång som kassation måste du skapa redovisningskonton som är kopplade till tillgångens anskaffningsvärde, avskrivning för aktuellt år, avskrivning för föregående år och till gångens NBV.</span><span class="sxs-lookup"><span data-stu-id="915be-123">Before you dispose of a fixed asset as scrap, you must create ledger accounts that are associated with the asset's acquisition value, depreciation for the current year, depreciation for previous years, and the asset's NBV.</span></span> <span data-ttu-id="915be-124">Transaktionstyperna för anläggningstillgången visas på sidan **Bokföringsprofil för anläggningstillgångar**.</span><span class="sxs-lookup"><span data-stu-id="915be-124">The fixed asset transaction types are listed on the **Fixed assets posting profile** page.</span></span> <span data-ttu-id="915be-125">Gå till **anläggningstillgångar \> inställningar \> bokföringsprofiler för anläggningstillgångar** och på snabbfliken **avyttrande** väljer du **kassation** i fältet ovanför rutnätet.</span><span class="sxs-lookup"><span data-stu-id="915be-125">Go to **Fixed assets \> Setup \> Fixed asset posting profiles**, and then, on the **Disposal** FastTab, select **Scrap** in the field above the grid.</span></span> <span data-ttu-id="915be-126">Följande bild visar listan över transaktionstyper för anläggningstillgångar på sidan **bokförings profiler för anläggningstillgångar**.</span><span class="sxs-lookup"><span data-stu-id="915be-126">The following illustration shows the list of fixed asset transaction types on the **Fixed asset posting profiles** page.</span></span>


<span data-ttu-id="915be-127">[![Avyttrande av en tillgång som kassation, figur 1](./media/Fixed_asset_Disposal_scrap_scenario_1.png)](./media/Fixed_asset_Disposal_scrap_scenario_1.png)</span><span class="sxs-lookup"><span data-stu-id="915be-127">[![Disposing of an asset as scap, Fig. 1](./media/Fixed_asset_Disposal_scrap_scenario_1.png)](./media/Fixed_asset_Disposal_scrap_scenario_1.png)</span></span>

<span data-ttu-id="915be-128">För följande exempel förvärvades en anläggningstillgång 1 januari 2018 och den kommer att kasseras den 31 mars 2019.</span><span class="sxs-lookup"><span data-stu-id="915be-128">For the following example, a fixed asset was acquired on January 1, 2018, and it will be scrapped on March 31, 2019.</span></span>

- <span data-ttu-id="915be-129">**Anskaffningspris** : 24 000,00 USD</span><span class="sxs-lookup"><span data-stu-id="915be-129">**Acquisition price:** 24,000.00 US dollars (USD)</span></span>
- <span data-ttu-id="915be-130">**Tjänstelivstid:** två år</span><span class="sxs-lookup"><span data-stu-id="915be-130">**Service life:** Two years</span></span>
- <span data-ttu-id="915be-131">**Avskrivningsmetod:** Linjär tjänstelivstid</span><span class="sxs-lookup"><span data-stu-id="915be-131">**Depreciation method:** Straight line service life</span></span>
- <span data-ttu-id="915be-132">**Avskrivningsbelopp:** 1 000,00 USD per månad</span><span class="sxs-lookup"><span data-stu-id="915be-132">**Depreciation amount:** 1,000.00 USD per month</span></span>

<span data-ttu-id="915be-133">NBV för en anläggningstillgång beräknas genom att använda följande formel:</span><span class="sxs-lookup"><span data-stu-id="915be-133">The NBV of a fixed asset is calculated by using the following formula:</span></span>

<span data-ttu-id="915be-134">Bokfört nettovärde = anskaffningspris – avskrivning</span><span class="sxs-lookup"><span data-stu-id="915be-134">Net book value = Acquisition price – Depreciation</span></span>

<span data-ttu-id="915be-135">I det här exemplet har anläggningstillgången förvärvats och avskrivits i 15 månader, från 2018 till mars 2019.</span><span class="sxs-lookup"><span data-stu-id="915be-135">In this example, the fixed asset was acquired and was depreciated for 15 months, from January 2018 through March 2019.</span></span> <span data-ttu-id="915be-136">Därför är tillgångens NBV 9 000,00 USD (24 000,00 USD – 15 000,00 USD).</span><span class="sxs-lookup"><span data-stu-id="915be-136">Therefore, the asset's NBV is 9,000.00 USD (24,000.00 USD – 15,000.00 USD).</span></span>

<span data-ttu-id="915be-137">[![Exempel på avskrivning för anläggningstillgångar](./media/Fixed_asset_Disposal_scrap_scenario_2.png)](./media/Fixed_asset_Disposal_scrap_scenario_2.png)</span><span class="sxs-lookup"><span data-stu-id="915be-137">[![Fixed asset depreciation example](./media/Fixed_asset_Disposal_scrap_scenario_2.png)](./media/Fixed_asset_Disposal_scrap_scenario_2.png)</span></span>


<span data-ttu-id="915be-138">Om du vill skapa en avskrivningsjournal, gå till **Anläggningstillgångar \> Journalposter \> Journal för anläggningstillgångar** och välj sedan **Rader** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="915be-138">To create a disposal journal, go to **Fixed assets \> Journal entries \> Fixed assets journal**, and then, on the Action Pane, select **Lines**.</span></span> <span data-ttu-id="915be-139">Välj **avyttrande – kassation** och välj sedan ett anläggningstillgångs-ID.</span><span class="sxs-lookup"><span data-stu-id="915be-139">Select **Disposal – scrap**, and then select a fixed asset ID.</span></span> <span data-ttu-id="915be-140">Ange inte ett värde antingen i fältet **Debet** eller i fältet **Kredit** för att helt avyttra tillgången.</span><span class="sxs-lookup"><span data-stu-id="915be-140">To fully dispose of the asset, don't enter a value in either the **Debit** field or the **Credit** field.</span></span>

<span data-ttu-id="915be-141">[![Journal för anläggningstillgångar](./media/Fixed_asset_Disposal_scrap_scenario_3.png)](./media/Fixed_asset_Disposal_scrap_scenario_3.png)</span><span class="sxs-lookup"><span data-stu-id="915be-141">[![Fixed assets journal](./media/Fixed_asset_Disposal_scrap_scenario_3.png)](./media/Fixed_asset_Disposal_scrap_scenario_3.png)</span></span>

<span data-ttu-id="915be-142">Kassationstransaktionen för avyttrande av anläggningstillgångar ändrar fältvärdena i anläggningstillgångens förteckning på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="915be-142">The fixed asset disposal scrap transaction changes the field values for the fixed asset book in the following ways:</span></span>

- <span data-ttu-id="915be-143">I avsnittet **saldo** uppdateras fältet **status** till **kasserat**.</span><span class="sxs-lookup"><span data-stu-id="915be-143">In the **Balance** section, the **Status** field is updated to **Scrapped**.</span></span>
- <span data-ttu-id="915be-144">I avsnittet **Utleverans** är fältet **avyttringsdatum** inställt på det datum då tillgången kasserades.</span><span class="sxs-lookup"><span data-stu-id="915be-144">In the **Issue** section, the **Disposal date** field is set to the date when the asset was scrapped.</span></span>

<span data-ttu-id="915be-145">[![Detaljer om journal för anläggningstillgångar](./media/Fixed_asset_Disposal_scrap_scenario_4.png)](./media/Fixed_asset_Disposal_scrap_scenario_4.png)</span><span class="sxs-lookup"><span data-stu-id="915be-145">[![Fixed assets journal detail](./media/Fixed_asset_Disposal_scrap_scenario_4.png)](./media/Fixed_asset_Disposal_scrap_scenario_4.png)</span></span>

<span data-ttu-id="915be-146">Följande illustration visar saldot för anläggningstillgångar.</span><span class="sxs-lookup"><span data-stu-id="915be-146">The following illustration shows the fixed asset balance.</span></span>

<span data-ttu-id="915be-147">[![Saldo för anläggningstillgångar](./media/Fixed_asset_Disposal_scrap_scenario_5.png)](./media/Fixed_asset_Disposal_scrap_scenario_5.png)</span><span class="sxs-lookup"><span data-stu-id="915be-147">[![Fixed asset balance](./media/Fixed_asset_Disposal_scrap_scenario_5.png)](./media/Fixed_asset_Disposal_scrap_scenario_5.png)</span></span>

<span data-ttu-id="915be-148">Följande illustration visar den verifikation som bokförs.</span><span class="sxs-lookup"><span data-stu-id="915be-148">The following illustration shows the voucher that is posted.</span></span>

<span data-ttu-id="915be-149">[![Bokfört nettovärde](./media/Fixed_asset_Disposal_scrap_scenario_6.png)](./media/Fixed_asset_Disposal_scrap_scenario_6.png)</span><span class="sxs-lookup"><span data-stu-id="915be-149">[![Net book value](./media/Fixed_asset_Disposal_scrap_scenario_6.png)](./media/Fixed_asset_Disposal_scrap_scenario_6.png)</span></span>
