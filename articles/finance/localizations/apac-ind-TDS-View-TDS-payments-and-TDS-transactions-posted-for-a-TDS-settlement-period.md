---
title: Visa bokförda TDS-betalningar och transaktioner för en TDS-kvittningsperiod
description: I det här avsnittet beskrivs hur du visar betalningar och transaktioner för skatteavdrag vid källan (TDS) som har bokförts för en kvittningsperiod.
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
ms.openlocfilehash: 2bada42073e46c69101e6d31f3328a2eeb95f880
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023591"
---
# <a name="view-posted-tds-payments-and-transactions-for-a-tds-settlement-period"></a><span data-ttu-id="38c55-103">Visa bokförda TDS-betalningar och transaktioner för en TDS-kvittningsperiod</span><span class="sxs-lookup"><span data-stu-id="38c55-103">View posted TDS payments and transactions for a TDS settlement period</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="38c55-104">I det här avsnittet beskrivs hur du visar betalningar och transaktioner för skatteavdrag vid källan (TDS) som har bokförts för en kvittningsperiod.</span><span class="sxs-lookup"><span data-stu-id="38c55-104">This topic explains how to view the Tax Deducted at Source (TDS) payments and transactions that were posted for a settlement period.</span></span>

1. <span data-ttu-id="38c55-105">Gå till **Skatt \> Indirekta skatter \> Källskatt \> Källskattekvittningsperioder**.</span><span class="sxs-lookup"><span data-stu-id="38c55-105">Go to **Tax \> Indirect taxes \> Withholding tax \> Withholding tax settlement periods**.</span></span>

    <span data-ttu-id="38c55-106">[![Sidan Källskattekvittningsperioder](./media/apac-ind-TDS-50.png)](./media/apac-ind-TDS-50.png)</span><span class="sxs-lookup"><span data-stu-id="38c55-106">[![Withholding tax settlement periods page](./media/apac-ind-TDS-50.png)](./media/apac-ind-TDS-50.png)</span></span>

2. <span data-ttu-id="38c55-107">På sidan **Källskattekvittningsperioder** väljer du **Källskattebetalningar** för att öppna sidan **Källskattebetalningar**, där du kan visa TDS-kvittningar som gjordes för en specifik TDS-kvittningsperiod.</span><span class="sxs-lookup"><span data-stu-id="38c55-107">On the **Withholding tax settlement periods** page, select **Withholding tax payments** to open the **Withholding tax payments** page, where you can view the TDS settlements that were made for a specific TDS settlement period.</span></span>

    <span data-ttu-id="38c55-108">Fliken **Översikt** visar följande information:</span><span class="sxs-lookup"><span data-stu-id="38c55-108">The **Overview** tab shows the following information:</span></span>

    - <span data-ttu-id="38c55-109">**Datum** – Datumet för TDS-kvittningen.</span><span class="sxs-lookup"><span data-stu-id="38c55-109">**Date** – The date of TDS settlement.</span></span>
    - <span data-ttu-id="38c55-110">**Verifiering** – Verifieringsnumret för TDS-kvittningstransaktionen.</span><span class="sxs-lookup"><span data-stu-id="38c55-110">**Voucher** – The voucher number of the TDS settlement transaction.</span></span>
    - <span data-ttu-id="38c55-111">**Skattetyp** – Skattetypen som kvittningsprocessen körs för.</span><span class="sxs-lookup"><span data-stu-id="38c55-111">**Tax type** – The tax type that the settlement process is run for.</span></span>
    - <span data-ttu-id="38c55-112">**Skattekontonummer (TAN)** – Skattekontonumret (TAN) för den kvittade TDS-transaktionen.</span><span class="sxs-lookup"><span data-stu-id="38c55-112">**Tax Account Number (TAN)** – The Tax Account Number (TAN) of the settled TDS transaction.</span></span>
    - <span data-ttu-id="38c55-113">**Kvittningsperiod** – Kvittningsperioden som TDS-kvittningsprocessen körs för.</span><span class="sxs-lookup"><span data-stu-id="38c55-113">**Settlement period** – The settlement period that the TDS settlement process is run for.</span></span>
    - <span data-ttu-id="38c55-114">**Från-datum** – Startdatumet för kvittningsperioden.</span><span class="sxs-lookup"><span data-stu-id="38c55-114">**From date** – The start date of the settlement period.</span></span>
    - <span data-ttu-id="38c55-115">**Till-datum** – Slutdatumet för kvittningsperioden.</span><span class="sxs-lookup"><span data-stu-id="38c55-115">**To date** – The end date of the settlement period.</span></span>
    - <span data-ttu-id="38c55-116">**Källskattebetalningsversion** – Versionen av källskattebetalning: **Original**, **Senaste korrigeringar** eller **Total lista**.</span><span class="sxs-lookup"><span data-stu-id="38c55-116">**Withholding tax payment version** – The version of the withholding tax payment: **Original**, **Latest corrections**, or **Total list**.</span></span>

5. <span data-ttu-id="38c55-117">Välj **Verifikation** för att visa verifikationsposterna för TDS-transaktionen.</span><span class="sxs-lookup"><span data-stu-id="38c55-117">Select **Voucher** to view the voucher entries for the TDS transaction.</span></span>
6. <span data-ttu-id="38c55-118">Välj **Källskattetransaktioner** för att visa informationen om TDS-transaktioner som kvittades för en specifik period under kvittningsperioden.</span><span class="sxs-lookup"><span data-stu-id="38c55-118">Select **Withholding tax transactions** to view the details of the TDS transactions that were settled for a specific period during a settlement period.</span></span> <span data-ttu-id="38c55-119">Välj **Verifikation** för att visa verifikationsposterna för TDS-transaktionen.</span><span class="sxs-lookup"><span data-stu-id="38c55-119">Select **Voucher** to view the voucher entries for the TDS transaction.</span></span> <span data-ttu-id="38c55-120">Välj **Källskattekomponenter** för att visa TDS som beräknades per TDS-skattekomponent för en specifik TDS-skattekod.</span><span class="sxs-lookup"><span data-stu-id="38c55-120">Select **Withholding tax components** to view the TDS that was calculated per TDS tax component for a specific TDS tax code.</span></span>
7. <span data-ttu-id="38c55-121">Stäng sidan **Källskattebetalningar** för att återgå till sidan **Källskattekvittningsperioder**.</span><span class="sxs-lookup"><span data-stu-id="38c55-121">Close the **Withholding tax payments** page to return to the **Withholding tax settlement periods** page.</span></span>
8. <span data-ttu-id="38c55-122">Välj **Källskattetransaktioner** för att visa informationen om TDS-transaktioner som kvittades för kvittningsperioden.</span><span class="sxs-lookup"><span data-stu-id="38c55-122">Select **Withholding tax transactions** to view the details of the TDS transactions that were settled for the settlement period.</span></span>
