---
title: Integrerad redovisning
description: I det här avsnittet beskrivs integreringen av redovisning mellan Finance and Operations och Customer Engagement med Common Data Service.
author: robinarh
manager: AnnBe
ms.date: 09/06/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ''
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 43819e23b167663a51095546cab307e7d7c79a38
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/06/2019
ms.locfileid: "2771058"
---
## <a name="integrated-ledger"></a><span data-ttu-id="91062-103">Integrerad redovisning</span><span class="sxs-lookup"><span data-stu-id="91062-103">Integrated ledger</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="91062-104">I ett affärsprogram definierar redovisningsdata den kärna som är inställd för hur ett företag gör affärer.</span><span class="sxs-lookup"><span data-stu-id="91062-104">In a business application, ledger data defines the core set up for how a company does business.</span></span> <span data-ttu-id="91062-105">Redovisningsdata beskriver t.ex. räkenskapsåret som företaget följer, de valutor det använder och vilka konton det använder.</span><span class="sxs-lookup"><span data-stu-id="91062-105">For example, ledger data describes the fiscal year the company follows, the currencies it transacts in, and the accounts it uses.</span></span> <span data-ttu-id="91062-106">I det här avsnittet beskrivs integrationen av dessa grundläggande ekonomiska data.</span><span class="sxs-lookup"><span data-stu-id="91062-106">This topic describes the integration of this core financial data.</span></span>

## <a name="templates"></a><span data-ttu-id="91062-107">Mallar</span><span class="sxs-lookup"><span data-stu-id="91062-107">Templates</span></span>

<span data-ttu-id="91062-108">Redovisningsdata inkluderar en samling entitetsmappningar för grundläggande ekonomiska som fungerar tillsammans under kunddatainteraktion, som visas i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="91062-108">Ledger data includes a collection of core financial entity maps that work together during data interaction, as shown in the following table.</span></span>

<span data-ttu-id="91062-109">Finance and Operations-appar</span><span class="sxs-lookup"><span data-stu-id="91062-109">Finance and Operations apps</span></span>      | <span data-ttu-id="91062-110">Andra Dynamics 365-appar</span><span class="sxs-lookup"><span data-stu-id="91062-110">Other Dynamics 365 apps</span></span>
---------------------------------|---------------------------------
<span data-ttu-id="91062-111">Valutor</span><span class="sxs-lookup"><span data-stu-id="91062-111">Currencies</span></span>                       | <span data-ttu-id="91062-112">transactioncurrencies</span><span class="sxs-lookup"><span data-stu-id="91062-112">transactioncurrencies</span></span>
<span data-ttu-id="91062-113">FiscalCalendar</span><span class="sxs-lookup"><span data-stu-id="91062-113">FiscalCalendar</span></span>                   | <span data-ttu-id="91062-114">msdyn\_fiscalcalendars</span><span class="sxs-lookup"><span data-stu-id="91062-114">msdyn\_fiscalcalendars</span></span>
<span data-ttu-id="91062-115">FiscalCalendarYear</span><span class="sxs-lookup"><span data-stu-id="91062-115">FiscalCalendarYear</span></span>               | <span data-ttu-id="91062-116">msdyn\_fiscalcalendaryears</span><span class="sxs-lookup"><span data-stu-id="91062-116">msdyn\_fiscalcalendaryears</span></span>
<span data-ttu-id="91062-117">ExchRateType</span><span class="sxs-lookup"><span data-stu-id="91062-117">ExchRateType</span></span>                     | <span data-ttu-id="91062-118">msdyn\_exchangeratetypes</span><span class="sxs-lookup"><span data-stu-id="91062-118">msdyn\_exchangeratetypes</span></span>
<span data-ttu-id="91062-119">ExchangeRateCurrencyPair</span><span class="sxs-lookup"><span data-stu-id="91062-119">ExchangeRateCurrencyPair</span></span>         | <span data-ttu-id="91062-120">msdyn\_currencyexchangeratepairs</span><span class="sxs-lookup"><span data-stu-id="91062-120">msdyn\_currencyexchangeratepairs</span></span>
<span data-ttu-id="91062-121">FiscalPeriodEntity</span><span class="sxs-lookup"><span data-stu-id="91062-121">FiscalPeriodEntity</span></span>               | <span data-ttu-id="91062-122">msdyn\_fiscalcalendarperiods</span><span class="sxs-lookup"><span data-stu-id="91062-122">msdyn\_fiscalcalendarperiods</span></span>
<span data-ttu-id="91062-123">MainAccountCategory</span><span class="sxs-lookup"><span data-stu-id="91062-123">MainAccountCategory</span></span>              | <span data-ttu-id="91062-124">msdyn\_mainaccountcategory</span><span class="sxs-lookup"><span data-stu-id="91062-124">msdyn\_mainaccountcategory</span></span>
<span data-ttu-id="91062-125">MainAccount</span><span class="sxs-lookup"><span data-stu-id="91062-125">MainAccount</span></span>                      | <span data-ttu-id="91062-126">msdyn\_mainaccounts</span><span class="sxs-lookup"><span data-stu-id="91062-126">msdyn\_mainaccounts</span></span>
<span data-ttu-id="91062-127">Redovisning</span><span class="sxs-lookup"><span data-stu-id="91062-127">Ledger</span></span>                           | <span data-ttu-id="91062-128">msdyn\_ledgers</span><span class="sxs-lookup"><span data-stu-id="91062-128">msdyn\_ledgers</span></span>
<span data-ttu-id="91062-129">ExchangeRates</span><span class="sxs-lookup"><span data-stu-id="91062-129">ExchangeRates</span></span>                    | <span data-ttu-id="91062-130">msdyn\_currencyexchangerates</span><span class="sxs-lookup"><span data-stu-id="91062-130">msdyn\_currencyexchangerates</span></span>
<span data-ttu-id="91062-131">FinancialCalendarPeriod</span><span class="sxs-lookup"><span data-stu-id="91062-131">FinancialCalendarPeriod</span></span>          | <span data-ttu-id="91062-132">msdyn\_fiscalcalendarperiods</span><span class="sxs-lookup"><span data-stu-id="91062-132">msdyn\_fiscalcalendarperiods</span></span>
<span data-ttu-id="91062-133">DimensionAttributeEntity</span><span class="sxs-lookup"><span data-stu-id="91062-133">DimensionAttributeEntity</span></span>         | <span data-ttu-id="91062-134">msdyn\_dimensionattributes.md</span><span class="sxs-lookup"><span data-stu-id="91062-134">msdyn\_dimensionattributes.md</span></span>
<span data-ttu-id="91062-135">DimensionIntegrationFormatEntity</span><span class="sxs-lookup"><span data-stu-id="91062-135">DimensionIntegrationFormatEntity</span></span> | <span data-ttu-id="91062-136">msdyn\_financialdimensionformats.md</span><span class="sxs-lookup"><span data-stu-id="91062-136">msdyn\_financialdimensionformats.md</span></span>
<span data-ttu-id="91062-137">LedgerChartOfAccounts</span><span class="sxs-lookup"><span data-stu-id="91062-137">LedgerChartOfAccounts</span></span>            | <span data-ttu-id="91062-138">msdyn\_chartofaccounts.md</span><span class="sxs-lookup"><span data-stu-id="91062-138">msdyn\_chartofaccounts.md</span></span>


[!include [banner](../includes/dual-write-symbols.md)]

[!include [Currency](dual-write/Currencies-transactioncurrencies.md)]

[!include [Fiscal calendar](dual-write/FiscalCalendar-msdyn-fiscalcalendars.md)]

[!include [Fiscal calendar year](dual-write/FiscalCalendarYear-msdyn-fiscalcalendaryears.md)]

[!include [Exchange rate types](dual-write/ExchRateType-msdyn-exchangeratetypes.md)]

[!include [Exchange rate pair](dual-write/ExchangeRateCurrencyPair-msdyn-currencyexchangeratepairs.md)]

[!include [Ledger fiscal periods](dual-write/FiscalPeriodEntity-msdyn-fiscalcalendarperiods.md)]

[!include [Main account category](dual-write/MainAccountCategory-msdyn-mainaccountcategory.md)]

[!include [Main account](dual-write/MainAccount-msdyn-mainaccounts.md)]

[!include [Ledger](dual-write/Ledger-msdyn-ledgers.md)]

[!include [Exchange rates](dual-write/ExchangeRates-msdyn-currencyexchangerates.md)]

[!include [Financial Calendar Period](dual-write/FiscalPeriodEntity-msdyn-fiscalcalendarperiods.md)]

[!include [Dimension attribute](dual-write/DimensionAttributeEntity-msdyn-dimensionattributes.md)]

[!include [Dimension integration format](dual-write/DimensionIntegrationFormatEntity-msdyn-financialdimensionformats.md)]

[!include [Chart Of Account](dual-write/LedgerChartOfAccounts-msdyn-chartofaccounts.md)]




