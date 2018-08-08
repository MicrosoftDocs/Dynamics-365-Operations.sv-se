---
title: Planera kontoplanen
description: "De här ämnena innehåller information som hjälper dig att planera kontoplanen för din organisation."
author: aprilolson
manager: AnnBe
ms.date: 04/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DimensionConfigureAccountStructure, LedgerChartOfAccounts
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 14051
ms.assetid: 10edb129-33f0-4cf9-b2a7-4b7ffa09b229
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 93d5ef19a4b1cb2885c611c8675ac06fd841ac56
ms.contentlocale: sv-se
ms.lasthandoff: 08/07/2018

---

# <a name="plan-your-chart-of-accounts"></a><span data-ttu-id="3dd5e-103">Planera kontoplanen</span><span class="sxs-lookup"><span data-stu-id="3dd5e-103">Plan your chart of accounts</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="3dd5e-104">Det här ämnet innehåller information som hjälper dig att planera kontoplanen för din organisation.</span><span class="sxs-lookup"><span data-stu-id="3dd5e-104">This topic provides information that will help you plan the chart of accounts for your organization.</span></span>

<span data-ttu-id="3dd5e-105">Följ och underhålla ekonomisk information i en organisation genom att lägga upp en kontoplan.</span><span class="sxs-lookup"><span data-stu-id="3dd5e-105">To track and maintain financial information in an organization, you can set up a chart of accounts.</span></span> <span data-ttu-id="3dd5e-106">En kontoplan är en samling av konton som definierar ett ekonomisk ramverk.</span><span class="sxs-lookup"><span data-stu-id="3dd5e-106">A chart of accounts is a collection of accounts that define a financial framework.</span></span> <span data-ttu-id="3dd5e-107">För att ytterligare spåra transaktionerna i kontona, kan du lägga till segment.</span><span class="sxs-lookup"><span data-stu-id="3dd5e-107">To further track the transactions in these accounts, you can add segments.</span></span> <span data-ttu-id="3dd5e-108">Dessa segment kallas för ekonomiska dimensioner.</span><span class="sxs-lookup"><span data-stu-id="3dd5e-108">These segments are known as financial dimensions.</span></span> <span data-ttu-id="3dd5e-109">Ett utgiftskonto kan till exempel inkludera ekonomiska dimensioner som kallas avdelning, kostnadsställe och syfte.</span><span class="sxs-lookup"><span data-stu-id="3dd5e-109">For example, an expense account might include financial dimensions that are named Department, Cost center, and Purpose.</span></span> <span data-ttu-id="3dd5e-110">Användardefinierade regler anger sambandet mellan dessa ekonomiska dimensioner och huvudkontona och andra ekonomiska dimensioner, och även hur transaktioner kan registreras.</span><span class="sxs-lookup"><span data-stu-id="3dd5e-110">User-defined rules determine how financial dimensions are attached to the main accounts and to other financial dimensions, and also how transactions are entered.</span></span> <span data-ttu-id="3dd5e-111">Dessa användardefinierade regler är kallas kontostrukturer och avancerade regler.</span><span class="sxs-lookup"><span data-stu-id="3dd5e-111">These user-defined rules are known as account structures and advanced rules.</span></span>

<span data-ttu-id="3dd5e-112">Kontoplanen är en strukturerad lista över en juridisk persons huvudbokskonton.</span><span class="sxs-lookup"><span data-stu-id="3dd5e-112">The chart of accounts is a structured list of a legal entity's general ledger accounts.</span></span> <span data-ttu-id="3dd5e-113">Listan används för att förbereda ekonomiska rapporter för myndigheter och ägare.</span><span class="sxs-lookup"><span data-stu-id="3dd5e-113">The list is used to prepare financial reports for authorities and owners.</span></span> <span data-ttu-id="3dd5e-114">Kontona grupperas först i kontotyper och sedan i större kategorier.</span><span class="sxs-lookup"><span data-stu-id="3dd5e-114">The accounts are first grouped into types of accounts and then further aggregated into larger categories.</span></span> <span data-ttu-id="3dd5e-115">På den allmännaste nivån grupperas kontona som kostnader och intäkter (rörelsekonton) samt tillgångar och skulder (balanskonton).</span><span class="sxs-lookup"><span data-stu-id="3dd5e-115">At the most general level, the accounts are grouped as revenues and costs (operating accounts), and assets and liabilities (balance accounts).</span></span>

<span data-ttu-id="3dd5e-116">En kontoplan kan delas och användas av alla juridiska personer i organisationen.</span><span class="sxs-lookup"><span data-stu-id="3dd5e-116">A chart of accounts can be shared and used by any legal entity in an organization.</span></span> <span data-ttu-id="3dd5e-117">Kontoplanen som används av en juridisk person definieras på sidan **Redovisning**.</span><span class="sxs-lookup"><span data-stu-id="3dd5e-117">The chart of accounts that is used by a legal entity is defined on the **Ledger** page.</span></span>

<span data-ttu-id="3dd5e-118">Här är några av faktorerna du måste ta hänsyn till när du lägger upp kontoplanen för organisationen:</span><span class="sxs-lookup"><span data-stu-id="3dd5e-118">Here are some of the factors that you must consider when you plan the structure of the chart of accounts for your organization:</span></span>

- <span data-ttu-id="3dd5e-119">Rapporteringskraven i det land eller den region där organisationen har sin bas</span><span class="sxs-lookup"><span data-stu-id="3dd5e-119">The reporting requirements of the country or region where your organization is based</span></span>
- <span data-ttu-id="3dd5e-120">Rapporteringskraven för en juridisk person</span><span class="sxs-lookup"><span data-stu-id="3dd5e-120">The reporting requirements of your legal entity</span></span>
- <span data-ttu-id="3dd5e-121">Specificeringsgraden som behövs, både för externa organisationer och för din organisation</span><span class="sxs-lookup"><span data-stu-id="3dd5e-121">The degree of specification that is required, both for both external organizations and for your organization</span></span>

<span data-ttu-id="3dd5e-122">Du skapar kontoplanen på sidan **Kontoplan**.</span><span class="sxs-lookup"><span data-stu-id="3dd5e-122">You create the chart of accounts on the **Chart of accounts** page.</span></span> <span data-ttu-id="3dd5e-123">Du kan skapa huvudkonton från sidan **Kontoplan** eller **Huvudkonton**.</span><span class="sxs-lookup"><span data-stu-id="3dd5e-123">You can create main accounts from the **Chart of accounts** page or the **Main accounts** page.</span></span> <span data-ttu-id="3dd5e-124">I dina huvudkonton ska inte användas specialtecken som används som kontoplanavgränsare.</span><span class="sxs-lookup"><span data-stu-id="3dd5e-124">Your main accounts shouldn't use any special characters that are used as delimiters for chart of accounts.</span></span> <span data-ttu-id="3dd5e-125">Annars kan det uppstå instabilitet eller du kanske alltid måste använda sökningar eller dialogrutan när du anger kombinationer av konton och dimensioner.</span><span class="sxs-lookup"><span data-stu-id="3dd5e-125">Otherwise, you might experience instability, or you might always have to use lookups or the dialog box when you enter combinations of accounts and dimensions.</span></span> <span data-ttu-id="3dd5e-126">Mer information finns i [Skapa ett huvudkonto](tasks/create-main-account.md).</span><span class="sxs-lookup"><span data-stu-id="3dd5e-126">For more information, see [Create a main account](tasks/create-main-account.md).</span></span>

> [!NOTE]
> <span data-ttu-id="3dd5e-127">I Microsoft Dynamics for Finance and Operations version 8.0 (april 2018), kan du ändra kontoplansavgränsare från sidan **Allmänna redovisningsparametrar**.</span><span class="sxs-lookup"><span data-stu-id="3dd5e-127">In Microsoft Dynamics for Finance and Operations version 8.0 (April 2018), you can modify the chart of accounts delimiter from the **General ledger parameters** page.</span></span>

<span data-ttu-id="3dd5e-128">Det är en bra idé att länka huvudkontona till huvudkontokategorier, så att du kan använda ekonomiska standardrapporterna utan att behöva göra några ändringar.</span><span class="sxs-lookup"><span data-stu-id="3dd5e-128">It's a good idea to link the main accounts to main account categories, so that you can take advantage of the default financial reports without having to make any modifications.</span></span> <span data-ttu-id="3dd5e-129">Därför kan du snabbt och enkelt designa och underhålla rapporter.</span><span class="sxs-lookup"><span data-stu-id="3dd5e-129">Therefore, you can more quickly and easily design and maintain reports.</span></span>

<span data-ttu-id="3dd5e-130">Du skapar kontostrukturer på sidan **Konfigurera kontostrukturer**.</span><span class="sxs-lookup"><span data-stu-id="3dd5e-130">You create account structures on the **Configure account structures** page.</span></span> <span data-ttu-id="3dd5e-131">Kontostrukturer definierar giltiga kombinationer.</span><span class="sxs-lookup"><span data-stu-id="3dd5e-131">Account structures define valid combinations.</span></span> <span data-ttu-id="3dd5e-132">Dessa kombinationer, tillsammans med huvudkontona, bildar en kontoplan.</span><span class="sxs-lookup"><span data-stu-id="3dd5e-132">These combinations, together with main accounts, form a chart of accounts.</span></span> <span data-ttu-id="3dd5e-133">Mer information finns i [Skapa en kontostruktur](tasks/create-account-structures.md).</span><span class="sxs-lookup"><span data-stu-id="3dd5e-133">For more information, see [Create account structures](tasks/create-account-structures.md).</span></span>

<span data-ttu-id="3dd5e-134">**Juridisk person åsidosätter**</span><span class="sxs-lookup"><span data-stu-id="3dd5e-134">**Legal entity overrides**</span></span>

<span data-ttu-id="3dd5e-135">Alla huvudkonton är inte giltiga för alla juridiska personer, och några huvudkonton kanske bara är relevanta under en viss period.</span><span class="sxs-lookup"><span data-stu-id="3dd5e-135">Not all main accounts are valid for all legal entities, and some main account might be relevant only for a specific period.</span></span> <span data-ttu-id="3dd5e-136">I detta scenario kan du använda avsnittet **Juridisk person åsidosätter** för att identifiera vilka företag som huvudkontot ska uppskjutas för, vem ägaren är och tidsperioden dimensionen är aktiv i.</span><span class="sxs-lookup"><span data-stu-id="3dd5e-136">In this scenario, you can use the **Legal entity overrides** section to identify the companies that the main account should be suspended for, the owner, and the period when the dimension is active.</span></span> <span data-ttu-id="3dd5e-137">Åsidosättandet på den delade nivån kan inte vara restriktivare än åsidosättandet på nivån för juridisk person.</span><span class="sxs-lookup"><span data-stu-id="3dd5e-137">The overrides at the shared level can't be more restrictive than the overrides at the legal entity level.</span></span>

<span data-ttu-id="3dd5e-138">Mer information finns i följande avsnitt:</span><span class="sxs-lookup"><span data-stu-id="3dd5e-138">For more information, see the following topics:</span></span>

- [<span data-ttu-id="3dd5e-139">Ekonomiska dimensioner</span><span class="sxs-lookup"><span data-stu-id="3dd5e-139">Financial dimensions</span></span>](financial-dimensions.md)
- [<span data-ttu-id="3dd5e-140">Skapa och tilldela avancerade regelstrukturer</span><span class="sxs-lookup"><span data-stu-id="3dd5e-140">Create and assign advanced rule structures</span></span>](tasks/create-assign-advanced-rule-structures.md)

