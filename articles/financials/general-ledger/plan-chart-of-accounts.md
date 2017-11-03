---
title: Planera din kontoplan
description: "Det här avsnittet innehåller information som hjälper dig att planera kontoplanen för din organisation."
author: aprilolson
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DimensionConfigureAccountStructure, LedgerChartOfAccounts
audience: Application User
ms.reviewer: robinr
ms.search.scope: Core, Operations
ms.custom: 14051
ms.assetid: 10edb129-33f0-4cf9-b2a7-4b7ffa09b229
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 038886f0a6e1c133a33ee34725eb20352e64341a
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="plan-your-chart-of-accounts"></a><span data-ttu-id="6fd2e-103">Planera din kontoplan</span><span class="sxs-lookup"><span data-stu-id="6fd2e-103">Plan your chart of accounts</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="6fd2e-104">Det här avsnittet innehåller information som hjälper dig att planera kontoplanen för din organisation.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-104">This article provides information that will help you plan the chart of accounts for your organization.</span></span>

<span data-ttu-id="6fd2e-105">Följ och underhålla ekonomisk information i en organisation genom att lägga upp en kontoplan.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-105">To track and maintain financial information in an organization, you can set up a chart of accounts.</span></span> <span data-ttu-id="6fd2e-106">En kontoplan är en samling av konton som definierar ett ekonomisk ramverk.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-106">A chart of accounts is a collection of accounts that define a financial framework.</span></span> <span data-ttu-id="6fd2e-107">För att följa transaktionerna i dessa konton kan du lägga till segment, som kallas ekonomiska dimensioner.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-107">To further track the transactions in these accounts, you can add segments, which are known as financial dimensions.</span></span> <span data-ttu-id="6fd2e-108">Ett utgiftskonto kan till exempel inkludera ekonomiska dimensioner som kallas avdelning, kostnadsställe och syfte.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-108">For example, an expense account might include financial dimensions that are named Department, Cost center, and Purpose.</span></span> <span data-ttu-id="6fd2e-109">Användardefinierade regler, som kallas kontostrukturer och avancerade regler, anger sambandet mellan dessa ekonomiska dimensioner och huvudkontona och andra ekonomiska dimensioner, och även hur transaktioner kan registreras.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-109">User-defined rules, which are known as account structures and advanced rules, determine how financial dimensions are attached to the main accounts and other financial dimensions, and also how transactions are entered.</span></span> 

<span data-ttu-id="6fd2e-110">Kontoplanen är en strukturerad lista över en juridisk persons huvudbokskonton.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-110">The chart of accounts is a structured list of a legal entity’s general ledger accounts.</span></span> <span data-ttu-id="6fd2e-111">Listan används för att förbereda ekonomiska rapporter för myndigheter och ägare.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-111">The list is used to prepare financial reports for authorities and owners.</span></span> <span data-ttu-id="6fd2e-112">Kontona grupperas i kontotyper och sedan i större kategorier.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-112">The accounts are grouped into types of accounts and then further aggregated into larger categories.</span></span> <span data-ttu-id="6fd2e-113">På den allmännaste nivån grupperas kontona som kostnader och intäkter (rörelsekonton) samt tillgångar och skulder (balanskonton).</span><span class="sxs-lookup"><span data-stu-id="6fd2e-113">At the most general level, the accounts are grouped as revenues and costs (operating accounts), and assets and liabilities (balance accounts).</span></span> 

<span data-ttu-id="6fd2e-114">En kontoplan kan delas och användas av alla juridiska personer i organisationen.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-114">A chart of accounts can be shared and used by any legal entity in an organization.</span></span> <span data-ttu-id="6fd2e-115">Kontoplanen som används av en juridisk person definieras på sidan **Redovisning**.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-115">The chart of accounts that is used by a legal entity is defined on the **Ledger** page.</span></span> 

<span data-ttu-id="6fd2e-116">Här är några av faktorerna du måste ta hänsyn till när du lägger upp kontoplanen för organisationen:</span><span class="sxs-lookup"><span data-stu-id="6fd2e-116">Here are some of the factors that you must consider when you plan the structure of the chart of accounts for your organization:</span></span>

-   <span data-ttu-id="6fd2e-117">Rapporteringskraven i det land eller den region där organisationen har sin bas</span><span class="sxs-lookup"><span data-stu-id="6fd2e-117">The reporting requirements of the country/region where your organization is based</span></span>
-   <span data-ttu-id="6fd2e-118">Rapporteringskraven för en juridisk person</span><span class="sxs-lookup"><span data-stu-id="6fd2e-118">The reporting requirements of your legal entity</span></span>
-   <span data-ttu-id="6fd2e-119">Specificeringsgraden som behövs, både för externa organisationer och för din organisation</span><span class="sxs-lookup"><span data-stu-id="6fd2e-119">The degree of specification that is required, both for both external organizations and for your organization</span></span>

<span data-ttu-id="6fd2e-120">Skapa kontoplanen på sidan **Kontoplan**.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-120">Create the chart of accounts on the **Chart of accounts** page.</span></span> <span data-ttu-id="6fd2e-121">Huvudkonton kan skapas på sidan **Kontoplan** eller **Huvudkonton**.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-121">Main accounts can be created from the **Chart of accounts** page or the **Main accounts** page.</span></span> <span data-ttu-id="6fd2e-122">I dina huvudkonton ska inte användas specialtecken som används som kontoplanavgränsare.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-122">Your main accounts shouldn't use any special characters that are used as chart of accounts delimiters.</span></span> <span data-ttu-id="6fd2e-123">Om du har ett specialtecken som är samma som din kontoplanavgränsare, kan du få instabilitet eller också måste du alltid använda uppslagningar eller den utfällbara menyn när du anger konto- och dimensionskombinationer.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-123">If you do have a special character that is the same as your chart of accounts delimiter, you may experience instability, or the need to always use lookups or the flyout when entering account and dimension combinations.</span></span> <span data-ttu-id="6fd2e-124">Mer information finns i [Skapa ett huvudkonto](tasks/create-account-structures.md).</span><span class="sxs-lookup"><span data-stu-id="6fd2e-124">For more information, see [Create a main account](tasks/create-account-structures.md).</span></span>


<span data-ttu-id="6fd2e-125">Det är en bra idé att länka huvudkontona till huvudkontokategorier, så att du kan använda ekonomiska standardrapporterna utan att behöva göra några ändringar.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-125">It's a good idea to link the main accounts to main account categories, so that you can take advantage of the default financial reports without having to make any modifications.</span></span> <span data-ttu-id="6fd2e-126">Därför kan du snabbt och enkelt designa och underhålla rapporter.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-126">Therefore, you can more quickly and easily design and maintain reports.</span></span> 

<span data-ttu-id="6fd2e-127">Använd sidan **Konfigurera kontostrukturer** för att konfigurera kontostrukturer.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-127">Use the **Configure account structures** page to create account structures.</span></span> <span data-ttu-id="6fd2e-128">Kontostrukturer definierar giltiga kombinationer.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-128">Account structures define valid combinations.</span></span> <span data-ttu-id="6fd2e-129">Kombinationerna, tillsammans med huvudkontona, bildar en kontoplan.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-129">The combinations, together with main accounts, form a chart of accounts.</span></span>  <span data-ttu-id="6fd2e-130">Mer information finns i [Skapa en kontostruktur](tasks/create-main-account.md).</span><span class="sxs-lookup"><span data-stu-id="6fd2e-130">For more information, see [Create account structures](tasks/create-main-account.md).</span></span>

<span data-ttu-id="6fd2e-131">**Juridisk person åsidosätter**</span><span class="sxs-lookup"><span data-stu-id="6fd2e-131">**Legal entity overrides**</span></span> 

<span data-ttu-id="6fd2e-132">Alla huvudkonton är inte giltiga för alla juridiska personer, och några kanske bara är relevanta under en viss tidsperiod.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-132">Not all main accounts are valid for all legal entities and some may only be relevant for a specific time period.</span></span> <span data-ttu-id="6fd2e-133">I det här scenariot kan åsidosättandet av juridisk person användas för att identifiera vilka företag huvudkontot ska uppskjutas för, vem ägaren är och tidsperioden dimensionen är aktiv i.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-133">In this scenario the Legal entity overrides section can be used to identify which companies the main account should be suspended for, who the owner is and the time period the dimension is active.</span></span> <span data-ttu-id="6fd2e-134">Åsidosättandet på den delade nivån kan inte vara restriktivare än åsidosättandet på nivån för juridisk person.</span><span class="sxs-lookup"><span data-stu-id="6fd2e-134">The overrides at the shared level cannot be more restrictive than the overrides at the legal entity level.</span></span>

<span data-ttu-id="6fd2e-135">Mer information finns i följande avsnitt: [Ekonomiska dimensioner](financial-dimensions.md)
[SKapa och tilldela avancerade regelstrukturer](tasks/create-assign-advanced-rule-structures.md)</span><span class="sxs-lookup"><span data-stu-id="6fd2e-135">For more information, see the following topics: [Financial dimensions](financial-dimensions.md)
[Create and assign advanced rule structures](tasks/create-assign-advanced-rule-structures.md)</span></span>




