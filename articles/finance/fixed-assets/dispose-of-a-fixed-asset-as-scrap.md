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
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2019-08-14
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 371cc2efa64916698da8e4230825c3c949920698
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4447947"
---
# <a name="dispose-of-a-fixed-asset-as-scrap"></a><span data-ttu-id="a5f85-103">Kassering av avyttrade anläggningstillgångar</span><span class="sxs-lookup"><span data-stu-id="a5f85-103">Dispose of a fixed asset as scrap</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a5f85-104">Ämnet beskriver hur du eliminerar transaktioner för en anläggningstillgång som avsatts som kassation.</span><span class="sxs-lookup"><span data-stu-id="a5f85-104">The topic describes the process of eliminating transactions for a fixed asset that was disposed of as scrap.</span></span> <span data-ttu-id="a5f85-105">Transaktionstyperna som kan elimineras inkluderar en tillgångs anskaffningsvärde och ackumulerade avskrivningstransaktioner och andra transaktioner för anläggningstillgångar.</span><span class="sxs-lookup"><span data-stu-id="a5f85-105">The transaction types that can be eliminated include an asset's acquisition and accumulated depreciation transactions and other fixed asset transactions.</span></span> <span data-ttu-id="a5f85-106">Eliminering av dessa transaktioner påverkar balansräkningskonton, till exempel anskaffningsjustering, avskrivningsjustering, omvärdering, uppskrivningskonton och nedskrivningskonton.</span><span class="sxs-lookup"><span data-stu-id="a5f85-106">Elimination of these transactions affects balance sheet accounts, such as acquisition adjustment, depreciation adjustment, revaluation, write-up, and write-down accounts.</span></span>

| <span data-ttu-id="a5f85-107">Transaktion</span><span class="sxs-lookup"><span data-stu-id="a5f85-107">Transaction</span></span>                                         | <span data-ttu-id="a5f85-108">Debet (Dr.)</span><span class="sxs-lookup"><span data-stu-id="a5f85-108">Debit (Dr.)</span></span> | <span data-ttu-id="a5f85-109">Kredit (Cr.)</span><span class="sxs-lookup"><span data-stu-id="a5f85-109">Credit (Cr.)</span></span> |
|-----------------------------------------------------|-------------|--------------|
| <span data-ttu-id="a5f85-110">Dr. Ackumulerad avskrivning</span><span class="sxs-lookup"><span data-stu-id="a5f85-110">Dr. Accumulated depreciation</span></span>                        | <span data-ttu-id="a5f85-111">X</span><span class="sxs-lookup"><span data-stu-id="a5f85-111">X</span></span>           |              |
| <span data-ttu-id="a5f85-112">Cr. Anläggningstillgångars vinst/förlust</span><span class="sxs-lookup"><span data-stu-id="a5f85-112">Cr. Fixed assets gain/loss</span></span>                          |             | <span data-ttu-id="a5f85-113">X</span><span class="sxs-lookup"><span data-stu-id="a5f85-113">X</span></span>            |
| <span data-ttu-id="a5f85-114">Dr. Anläggningstillgångars vinst/förlust</span><span class="sxs-lookup"><span data-stu-id="a5f85-114">Dr. Fixed assets gain/loss</span></span>                          | <span data-ttu-id="a5f85-115">X</span><span class="sxs-lookup"><span data-stu-id="a5f85-115">X</span></span>           |              |
| <span data-ttu-id="a5f85-116">Cr. Konto för anskaffning av anläggningstillgång</span><span class="sxs-lookup"><span data-stu-id="a5f85-116">Cr. Fixed asset acquisition account</span></span>                 |             | <span data-ttu-id="a5f85-117">X</span><span class="sxs-lookup"><span data-stu-id="a5f85-117">X</span></span>            |
| <span data-ttu-id="a5f85-118">Dr. Anläggningstillgångars vinst/förlust (bokfört nettovärde \[NBV\])</span><span class="sxs-lookup"><span data-stu-id="a5f85-118">Dr. Fixed assets gain/loss (net book value \[NBV\])</span></span> | <span data-ttu-id="a5f85-119">X</span><span class="sxs-lookup"><span data-stu-id="a5f85-119">X</span></span>           |              |
| <span data-ttu-id="a5f85-120">Cr. Anläggningstillgångars vinst/förlust (NBV)</span><span class="sxs-lookup"><span data-stu-id="a5f85-120">Cr. Fixed assets gain/loss (NBV)</span></span>                    |             | <span data-ttu-id="a5f85-121">X</span><span class="sxs-lookup"><span data-stu-id="a5f85-121">X</span></span>            |

> [!NOTE]
> <span data-ttu-id="a5f85-122">Vi rekommenderar att du samarbetar med företagets ekonomichef (CFO) eller controller för att identifiera de korrekta konton som ska användas för varje transaktionstyp och även för att verifiera att kasseringsprocessen och transaktionerna som den genererar uppdaterar dessa konton korrekt.</span><span class="sxs-lookup"><span data-stu-id="a5f85-122">We recommend that you work closely with your company's chief financial officer (CFO) or controller to identify the correct accounts that should be used for each transaction type, and also to verify that the disposal process and the transactions that it generates update those accounts correctly.</span></span>

<span data-ttu-id="a5f85-123">Innan du avyttrar en anläggningstillgång som kassation måste du skapa redovisningskonton som är kopplade till tillgångens anskaffningsvärde, avskrivning för aktuellt år, avskrivning för föregående år och till gångens NBV.</span><span class="sxs-lookup"><span data-stu-id="a5f85-123">Before you dispose of a fixed asset as scrap, you must create ledger accounts that are associated with the asset's acquisition value, depreciation for the current year, depreciation for previous years, and the asset's NBV.</span></span> <span data-ttu-id="a5f85-124">Transaktionstyperna för anläggningstillgången visas på sidan **Bokföringsprofil för anläggningstillgångar**.</span><span class="sxs-lookup"><span data-stu-id="a5f85-124">The fixed asset transaction types are listed on the **Fixed assets posting profile** page.</span></span> <span data-ttu-id="a5f85-125">Gå till **anläggningstillgångar \> inställningar \> bokföringsprofiler för anläggningstillgångar** och på snabbfliken **avyttrande** väljer du **kassation** i fältet ovanför rutnätet.</span><span class="sxs-lookup"><span data-stu-id="a5f85-125">Go to **Fixed assets \> Setup \> Fixed asset posting profiles**, and then, on the **Disposal** FastTab, select **Scrap** in the field above the grid.</span></span> <span data-ttu-id="a5f85-126">Följande bild visar listan över transaktionstyper för anläggningstillgångar på sidan **bokförings profiler för anläggningstillgångar**.</span><span class="sxs-lookup"><span data-stu-id="a5f85-126">The following illustration shows the list of fixed asset transaction types on the **Fixed asset posting profiles** page.</span></span>


<span data-ttu-id="a5f85-127">[![Avyttrande av en tillgång som kassation, figur 1](./media/Fixed_asset_Disposal_scrap_scenario_1.png)](./media/Fixed_asset_Disposal_scrap_scenario_1.png)</span><span class="sxs-lookup"><span data-stu-id="a5f85-127">[![Disposing of an asset as scap, Fig. 1](./media/Fixed_asset_Disposal_scrap_scenario_1.png)](./media/Fixed_asset_Disposal_scrap_scenario_1.png)</span></span>

<span data-ttu-id="a5f85-128">För följande exempel förvärvades en anläggningstillgång 1 januari 2018 och den kommer att kasseras den 31 mars 2019.</span><span class="sxs-lookup"><span data-stu-id="a5f85-128">For the following example, a fixed asset was acquired on January 1, 2018, and it will be scrapped on March 31, 2019.</span></span>

- <span data-ttu-id="a5f85-129">**Anskaffningspris** : 24 000,00 USD</span><span class="sxs-lookup"><span data-stu-id="a5f85-129">**Acquisition price:** 24,000.00 US dollars (USD)</span></span>
- <span data-ttu-id="a5f85-130">**Tjänstelivstid:** två år</span><span class="sxs-lookup"><span data-stu-id="a5f85-130">**Service life:** Two years</span></span>
- <span data-ttu-id="a5f85-131">**Avskrivningsmetod:** Linjär tjänstelivstid</span><span class="sxs-lookup"><span data-stu-id="a5f85-131">**Depreciation method:** Straight line service life</span></span>
- <span data-ttu-id="a5f85-132">**Avskrivningsbelopp:** 1 000,00 USD per månad</span><span class="sxs-lookup"><span data-stu-id="a5f85-132">**Depreciation amount:** 1,000.00 USD per month</span></span>

<span data-ttu-id="a5f85-133">NBV för en anläggningstillgång beräknas genom att använda följande formel:</span><span class="sxs-lookup"><span data-stu-id="a5f85-133">The NBV of a fixed asset is calculated by using the following formula:</span></span>

<span data-ttu-id="a5f85-134">Bokfört nettovärde = anskaffningspris – avskrivning</span><span class="sxs-lookup"><span data-stu-id="a5f85-134">Net book value = Acquisition price – Depreciation</span></span>

<span data-ttu-id="a5f85-135">I det här exemplet har anläggningstillgången förvärvats och avskrivits i 15 månader, från 2018 till mars 2019.</span><span class="sxs-lookup"><span data-stu-id="a5f85-135">In this example, the fixed asset was acquired and was depreciated for 15 months, from January 2018 through March 2019.</span></span> <span data-ttu-id="a5f85-136">Därför är tillgångens NBV 9 000,00 USD (24 000,00 USD – 15 000,00 USD).</span><span class="sxs-lookup"><span data-stu-id="a5f85-136">Therefore, the asset's NBV is 9,000.00 USD (24,000.00 USD – 15,000.00 USD).</span></span>

<span data-ttu-id="a5f85-137">[![Exempel på avskrivning för anläggningstillgångar](./media/Fixed_asset_Disposal_scrap_scenario_2.png)](./media/Fixed_asset_Disposal_scrap_scenario_2.png)</span><span class="sxs-lookup"><span data-stu-id="a5f85-137">[![Fixed asset depreciation example](./media/Fixed_asset_Disposal_scrap_scenario_2.png)](./media/Fixed_asset_Disposal_scrap_scenario_2.png)</span></span>


<span data-ttu-id="a5f85-138">Om du vill skapa en avskrivningsjournal, gå till **Anläggningstillgångar \> Journalposter \> Journal för anläggningstillgångar** och välj sedan **Rader** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="a5f85-138">To create a disposal journal, go to **Fixed assets \> Journal entries \> Fixed assets journal**, and then, on the Action Pane, select **Lines**.</span></span> <span data-ttu-id="a5f85-139">Välj **avyttrande – kassation** och välj sedan ett anläggningstillgångs-ID.</span><span class="sxs-lookup"><span data-stu-id="a5f85-139">Select **Disposal – scrap**, and then select a fixed asset ID.</span></span> <span data-ttu-id="a5f85-140">Ange inte ett värde antingen i fältet **Debet** eller i fältet **Kredit** för att helt avyttra tillgången.</span><span class="sxs-lookup"><span data-stu-id="a5f85-140">To fully dispose of the asset, don't enter a value in either the **Debit** field or the **Credit** field.</span></span>

<span data-ttu-id="a5f85-141">[![Journal för anläggningstillgångar](./media/Fixed_asset_Disposal_scrap_scenario_3.png)](./media/Fixed_asset_Disposal_scrap_scenario_3.png)</span><span class="sxs-lookup"><span data-stu-id="a5f85-141">[![Fixed assets journal](./media/Fixed_asset_Disposal_scrap_scenario_3.png)](./media/Fixed_asset_Disposal_scrap_scenario_3.png)</span></span>

<span data-ttu-id="a5f85-142">Kassationstransaktionen för avyttrande av anläggningstillgångar ändrar fältvärdena i anläggningstillgångens förteckning på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="a5f85-142">The fixed asset disposal scrap transaction changes the field values for the fixed asset book in the following ways:</span></span>

- <span data-ttu-id="a5f85-143">I avsnittet **saldo** uppdateras fältet **status** till **kasserat**.</span><span class="sxs-lookup"><span data-stu-id="a5f85-143">In the **Balance** section, the **Status** field is updated to **Scrapped**.</span></span>
- <span data-ttu-id="a5f85-144">I avsnittet **Utleverans** är fältet **avyttringsdatum** inställt på det datum då tillgången kasserades.</span><span class="sxs-lookup"><span data-stu-id="a5f85-144">In the **Issue** section, the **Disposal date** field is set to the date when the asset was scrapped.</span></span>

<span data-ttu-id="a5f85-145">[![Detaljer om journal för anläggningstillgångar](./media/Fixed_asset_Disposal_scrap_scenario_4.png)](./media/Fixed_asset_Disposal_scrap_scenario_4.png)</span><span class="sxs-lookup"><span data-stu-id="a5f85-145">[![Fixed assets journal detail](./media/Fixed_asset_Disposal_scrap_scenario_4.png)](./media/Fixed_asset_Disposal_scrap_scenario_4.png)</span></span>

<span data-ttu-id="a5f85-146">Följande illustration visar saldot för anläggningstillgångar.</span><span class="sxs-lookup"><span data-stu-id="a5f85-146">The following illustration shows the fixed asset balance.</span></span>

<span data-ttu-id="a5f85-147">[![Saldo för anläggningstillgångar](./media/Fixed_asset_Disposal_scrap_scenario_5.png)](./media/Fixed_asset_Disposal_scrap_scenario_5.png)</span><span class="sxs-lookup"><span data-stu-id="a5f85-147">[![Fixed asset balance](./media/Fixed_asset_Disposal_scrap_scenario_5.png)](./media/Fixed_asset_Disposal_scrap_scenario_5.png)</span></span>

<span data-ttu-id="a5f85-148">Följande illustration visar den verifikation som bokförs.</span><span class="sxs-lookup"><span data-stu-id="a5f85-148">The following illustration shows the voucher that is posted.</span></span>

<span data-ttu-id="a5f85-149">[![Bokfört nettovärde](./media/Fixed_asset_Disposal_scrap_scenario_6.png)](./media/Fixed_asset_Disposal_scrap_scenario_6.png)</span><span class="sxs-lookup"><span data-stu-id="a5f85-149">[![Net book value](./media/Fixed_asset_Disposal_scrap_scenario_6.png)](./media/Fixed_asset_Disposal_scrap_scenario_6.png)</span></span>
