---
title: Visa skuld-, tillgångs- och utgiftstransaktioner
description: I det här ännet beskrivs hur du visar transaktioner för en leasad tillgång. Dessa transaktioner inkluderar leasingskuldtransaktioner och för verkställighetskostnadstransaktioner som har bokförts.
author: moaamer
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 6dbb5de75780091d3392e413e3a2415067ac6dda
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5827492"
---
# <a name="view-liability-asset-and-expense-transactions"></a><span data-ttu-id="9c6b7-104">Visa skuld-, tillgångs- och utgiftstransaktioner</span><span class="sxs-lookup"><span data-stu-id="9c6b7-104">View liability, asset, and expense transactions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9c6b7-105">I det här ännet beskrivs hur du visar transaktioner för en leasad tillgång.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-105">This topic explains how to view transactions for a leased asset.</span></span> <span data-ttu-id="9c6b7-106">Dessa transaktioner inkluderar leasingskuldtransaktioner och för verkställighetskostnadstransaktioner som har bokförts.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-106">These transactions include lease liability transactions and executory expense transactions that have been posted.</span></span> <span data-ttu-id="9c6b7-107">De bokförda värdena för skulden och ROU-tillgången används i flera rapporter.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-107">The carrying values of the liability and right-of-use (ROU) asset are used on several reports.</span></span> <span data-ttu-id="9c6b7-108">De används också för att beräkna justeringsvärden.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-108">They are also used to calculate adjustment values.</span></span>

## <a name="liability-transactions"></a><span data-ttu-id="9c6b7-109">Skuldtransaktioner</span><span class="sxs-lookup"><span data-stu-id="9c6b7-109">Liability transactions</span></span>

<span data-ttu-id="9c6b7-110">Om du vill visa leasingskuldtransaktionerna väljer du en leasing på sidan **Sammanfattning av leasing** och väljer sedan **Böcker** för att öppna de böcker som är kopplade till leasingposten.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-110">To view the lease liability transactions, select a lease on the **Lease summary** page, and then select **Books** to open the books that are attached to the lease record.</span></span> <span data-ttu-id="9c6b7-111">Efter att ett första redovisningstillfälle, en faktura eller en räntejournal har bokförts väljer du **Skuldtransaktioner**.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-111">After an initial recognition, an invoice, or an interest journal has been posted, select **Liability transactions**.</span></span>

<span data-ttu-id="9c6b7-112">På sidan **Skuldtransaktioner** visas de transaktioner som antingen ökar eller minskar leasingskulden.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-112">The **Liability transactions** page shows the transactions that either increase or decrease the lease liability.</span></span> <span data-ttu-id="9c6b7-113">Negativa belopp på den här sidan representerar kredittransaktioner i standardprogrammet.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-113">Negative amounts on this page represent credit transactions in the standard application.</span></span> <span data-ttu-id="9c6b7-114">Eventuella upplupna räntor redovisas som negativa värden och ökar den totala leasingskulden.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-114">Any interest accruals are shown as negative values and increase the total lease liability.</span></span> <span data-ttu-id="9c6b7-115">Eventuella leasingjusteringar visas som positiva eller negativa värden, beroende på leasingbokens art och verkan.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-115">Any lease adjustments are shown as positive or negative values, depending on the nature and impact of the lease book.</span></span> <span data-ttu-id="9c6b7-116">Det aktuella nettosaldot för leasingskulden för vald leasing visas längst ned till vänster på sidan.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-116">The current net total balance of the lease liability for the selected lease is shown at the bottom left of the page.</span></span>

## <a name="asset-transactions"></a><span data-ttu-id="9c6b7-117">Tillgångstransaktioner</span><span class="sxs-lookup"><span data-stu-id="9c6b7-117">Asset transactions</span></span>

<span data-ttu-id="9c6b7-118">Om du vill visa leasingtillgångstransaktionerna väljer du en leasing på sidan **Sammanfattning av leasing** och väljer sedan **Böcker** för att öppna de leasingböcker som är kopplade till leasingposten.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-118">To view the lease asset transactions, select a lease on the **Lease summary** page, and then select **Books** to open the lease books that are attached to the lease record.</span></span> <span data-ttu-id="9c6b7-119">Välj sedan **Transaktioner för tillgångar**.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-119">Then select **Asset transactions**.</span></span>

<span data-ttu-id="9c6b7-120">På sidan **Transaktion för tillgångar** visas de transaktioner som antingen ökar eller minskar leasingtillgången och ackumulerade avskrivningskonton.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-120">The **Asset transaction** page shows the transactions that either increase or decrease the lease asset and accumulated depreciation accounts.</span></span> <span data-ttu-id="9c6b7-121">Debet visas som positiva värden och kredit visas som negativa värden, som på sidan **Skuldtransaktioner**.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-121">Debits are shown as positive values, and credits are shown as negative values, as on the **Liability transactions** page.</span></span> <span data-ttu-id="9c6b7-122">Den bokförda initiala redovisningen och nästa ackumulerade avskrivning visas längst ned till vänster på sidan som tillgångssaldot.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-122">The posted initial recognition and the next of accumulated depreciation are shown at the bottom left of the page as the asset balance.</span></span> 

## <a name="expenses-transactions"></a><span data-ttu-id="9c6b7-123">Utgiftstransaktioner</span><span class="sxs-lookup"><span data-stu-id="9c6b7-123">Expenses transactions</span></span>

<span data-ttu-id="9c6b7-124">Om du vill visa leasingutgiftstransaktionerna väljer du en leasing på sidan **Sammanfattning av leasing** och väljer sedan **Böcker** för att öppna de leasingböcker som är kopplade till leasingposten.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-124">To view the lease expense transactions, select a lease on the **Lease summary** page, and then select **Books** to open the lease books that are attached to the lease record.</span></span> <span data-ttu-id="9c6b7-125">Välj sedan **Utgiftstransaktioner**.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-125">Then select **Expense transactions**.</span></span>

<span data-ttu-id="9c6b7-126">På sidan **Utgiftstransaktioner** visas alla utgifter som har bokförts mot leasingen, till exempel räntekostnader, avskrivningskostnader och eventuella verkställighetskostnader.</span><span class="sxs-lookup"><span data-stu-id="9c6b7-126">The **Expense transactions** page shows all the expenses that have been posted against the lease, such as interest expenses, depreciation expenses, and any executory costs.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]