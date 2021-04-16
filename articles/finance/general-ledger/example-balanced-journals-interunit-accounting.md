---
title: Balanserade journaler för internredovisning
description: Den här artikeln visar hur en journal automatiskt balanseras när en balanserande ekonomisk dimension har valts på sidan Redovisning.
author: ShylaThompson
ms.date: 10/30/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerParameters
audience: Application User
ms.reviewer: roschlom
ms.custom: 15791
ms.assetid: 301bd80e-f8b1-4f12-8194-e6d7de736084
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a5a926adcc631ec286f37796713466eb0144494c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5818402"
---
# <a name="balanced-journals-for-interunit-accounting"></a><span data-ttu-id="10d1c-103">Balanserade journaler för internredovisning</span><span class="sxs-lookup"><span data-stu-id="10d1c-103">Balanced journals for interunit accounting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="10d1c-104">Den här artikeln visar hur en journal automatiskt balanseras när en balanserande ekonomisk dimension har valts på sidan Redovisning.</span><span class="sxs-lookup"><span data-stu-id="10d1c-104">This article shows how a journal is automatically balanced when a balancing financial dimension is selected on the Ledger page.</span></span> 

<span data-ttu-id="10d1c-105">Om redovisningposterna inte balanserar på nivån av värdena för den ekonomiska dimension, skapas ytterligare kontoposter automatiskt till att balansera journalen.</span><span class="sxs-lookup"><span data-stu-id="10d1c-105">If account entries don't balance at the level of the financial dimension values, additional account entries are created automatically to balance the journal.</span></span> <span data-ttu-id="10d1c-106">Dessa kontoposter använder bokföringstyperna **Enhetsintern – debet** och **Enhetsintern – kredit** på sidan **Konton för automatiska transaktioner** för att bestämma huvudkontot.</span><span class="sxs-lookup"><span data-stu-id="10d1c-106">These account entries use the **Interunit - debit** and **Interunit - credit** posting types on the **Accounts for automatic transactions** page to determine the main account.</span></span> <span data-ttu-id="10d1c-107">Exempelvis väljs Affärsenhet, som är det andra segmentet i huvudbokskonto, som den balanserade ekonomiska dimensionen och följande redovisningsposter håller på att skapas.</span><span class="sxs-lookup"><span data-stu-id="10d1c-107">For example, Business Unit, which is the second segment of the ledger account, is selected as the balancing financial dimension, and the following accounting entries are about to be created.</span></span>

| &nbsp;               | &nbsp;    |
|----------------------|-----------|
| <span data-ttu-id="10d1c-108">6100 – MSP – OU\_256</span><span class="sxs-lookup"><span data-stu-id="10d1c-108">6100 – MSP – OU\_256</span></span> | <span data-ttu-id="10d1c-109">100.00 DR</span><span class="sxs-lookup"><span data-stu-id="10d1c-109">100.00 DR</span></span> |
| <span data-ttu-id="10d1c-110">6100 – NY – OU\_249</span><span class="sxs-lookup"><span data-stu-id="10d1c-110">6100 – NY – OU\_249</span></span>  | <span data-ttu-id="10d1c-111">100.00 DR</span><span class="sxs-lookup"><span data-stu-id="10d1c-111">100.00 DR</span></span> |
| <span data-ttu-id="10d1c-112">2100 – MSP – OU\_256</span><span class="sxs-lookup"><span data-stu-id="10d1c-112">2100 – MSP – OU\_256</span></span> | <span data-ttu-id="10d1c-113">200.00 CR</span><span class="sxs-lookup"><span data-stu-id="10d1c-113">200.00 CR</span></span> |

<span data-ttu-id="10d1c-114">I detta fall bestäms följande saldon:</span><span class="sxs-lookup"><span data-stu-id="10d1c-114">In this case, the following balances are determined:</span></span>

-   <span data-ttu-id="10d1c-115">För Affärsenhet MSP = 100,00 CR</span><span class="sxs-lookup"><span data-stu-id="10d1c-115">For Business Unit MSP = 100.00 CR</span></span>
-   <span data-ttu-id="10d1c-116">För Affärsenhet NY = 100,00 DR</span><span class="sxs-lookup"><span data-stu-id="10d1c-116">For Business Unit NY = 100.00 DR</span></span>

<span data-ttu-id="10d1c-117">Därför skapas följande redovisningsposter automatiskt för att balansera journalen till nivån för värdena för ekonomisk dimension.</span><span class="sxs-lookup"><span data-stu-id="10d1c-117">Therefore, the following accounting entries are created automatically to balance the  journal at the level of the financial dimension values.</span></span>

| &nbsp;                            | &nbsp;    |
|-----------------------------------|-----------|
| <span data-ttu-id="10d1c-118">(Enhetsintern debit) – MSP – OU\_256</span><span class="sxs-lookup"><span data-stu-id="10d1c-118">(Interunit Debit) – MSP – OU\_256</span></span> | <span data-ttu-id="10d1c-119">100.00 DR</span><span class="sxs-lookup"><span data-stu-id="10d1c-119">100.00 DR</span></span> |
| <span data-ttu-id="10d1c-120">(Enhetsintern kredit) – NY – OU\_249</span><span class="sxs-lookup"><span data-stu-id="10d1c-120">(Interunit Credit) – NY – OU\_249</span></span> | <span data-ttu-id="10d1c-121">100.00 CR</span><span class="sxs-lookup"><span data-stu-id="10d1c-121">100.00 CR</span></span> |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]