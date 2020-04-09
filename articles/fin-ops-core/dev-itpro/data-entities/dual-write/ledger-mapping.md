---
title: Integrerad redovisning
description: I det här avsnittet beskrivs integreringen av redovisning mellan Finance and Operations och andra Dynamics 365-appar med Common Data Service.
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
ms.openlocfilehash: 6f1a1c7329f0936147fb8f7a8e0e9fea14f7dd4b
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/27/2020
ms.locfileid: "3173025"
---
# <a name="integrated-ledger"></a><span data-ttu-id="00d69-103">Integrerad redovisning</span><span class="sxs-lookup"><span data-stu-id="00d69-103">Integrated ledger</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="00d69-104">I ett affärsprogram definierar redovisningsdata den kärna som är inställd för hur ett företag gör affärer.</span><span class="sxs-lookup"><span data-stu-id="00d69-104">In a business application, ledger data defines the core set up for how a company does business.</span></span> <span data-ttu-id="00d69-105">Redovisningsdata beskriver t.ex. räkenskapsåret som företaget följer, de valutor det använder och vilka konton det använder.</span><span class="sxs-lookup"><span data-stu-id="00d69-105">For example, ledger data describes the fiscal year the company follows, the currencies it transacts in, and the accounts it uses.</span></span> <span data-ttu-id="00d69-106">I det här avsnittet beskrivs integrationen av dessa grundläggande ekonomiska data.</span><span class="sxs-lookup"><span data-stu-id="00d69-106">This topic describes the integration of this core financial data.</span></span>

## <a name="templates"></a><span data-ttu-id="00d69-107">Mallar</span><span class="sxs-lookup"><span data-stu-id="00d69-107">Templates</span></span>

<span data-ttu-id="00d69-108">Redovisningsdata inkluderar en samling entitetsmappningar för grundläggande ekonomiska som fungerar tillsammans under kunddatainteraktion, som visas i följande tabell.</span><span class="sxs-lookup"><span data-stu-id="00d69-108">Ledger data includes a collection of core financial entity maps that work together during data interaction, as shown in the following table.</span></span>

<span data-ttu-id="00d69-109">Finance and Operations-appar</span><span class="sxs-lookup"><span data-stu-id="00d69-109">Finance and Operations apps</span></span>      | <span data-ttu-id="00d69-110">Modellstyrda appar i Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="00d69-110">Model-driven app in Dynamics 365</span></span> | <span data-ttu-id="00d69-111">beskrivning</span><span class="sxs-lookup"><span data-stu-id="00d69-111">Description</span></span>
---------------------------------|----------------------------------|------------
<span data-ttu-id="00d69-112">Valutor</span><span class="sxs-lookup"><span data-stu-id="00d69-112">Currencies</span></span>                       | <span data-ttu-id="00d69-113">transactioncurrencies</span><span class="sxs-lookup"><span data-stu-id="00d69-113">transactioncurrencies</span></span>            |
<span data-ttu-id="00d69-114">FiscalCalendar</span><span class="sxs-lookup"><span data-stu-id="00d69-114">FiscalCalendar</span></span>                   | <span data-ttu-id="00d69-115">msdyn\_fiscalcalendars</span><span class="sxs-lookup"><span data-stu-id="00d69-115">msdyn\_fiscalcalendars</span></span>        |
<span data-ttu-id="00d69-116">FiscalCalendarYear</span><span class="sxs-lookup"><span data-stu-id="00d69-116">FiscalCalendarYear</span></span>               | <span data-ttu-id="00d69-117">msdyn\_fiscalcalendaryears</span><span class="sxs-lookup"><span data-stu-id="00d69-117">msdyn\_fiscalcalendaryears</span></span>        |
<span data-ttu-id="00d69-118">ExchRateType</span><span class="sxs-lookup"><span data-stu-id="00d69-118">ExchRateType</span></span>                     | <span data-ttu-id="00d69-119">msdyn\_exchangeratetypes</span><span class="sxs-lookup"><span data-stu-id="00d69-119">msdyn\_exchangeratetypes</span></span>        |
<span data-ttu-id="00d69-120">ExchangeRateCurrencyPair</span><span class="sxs-lookup"><span data-stu-id="00d69-120">ExchangeRateCurrencyPair</span></span>         | <span data-ttu-id="00d69-121">msdyn\_currencyexchangeratepairs</span><span class="sxs-lookup"><span data-stu-id="00d69-121">msdyn\_currencyexchangeratepairs</span></span>        |
<span data-ttu-id="00d69-122">FiscalPeriodEntity</span><span class="sxs-lookup"><span data-stu-id="00d69-122">FiscalPeriodEntity</span></span>               | <span data-ttu-id="00d69-123">msdyn\_fiscalcalendarperiods</span><span class="sxs-lookup"><span data-stu-id="00d69-123">msdyn\_fiscalcalendarperiods</span></span>        |
<span data-ttu-id="00d69-124">MainAccountCategory</span><span class="sxs-lookup"><span data-stu-id="00d69-124">MainAccountCategory</span></span>              | <span data-ttu-id="00d69-125">msdyn\_mainaccountcategory</span><span class="sxs-lookup"><span data-stu-id="00d69-125">msdyn\_mainaccountcategory</span></span>        |
<span data-ttu-id="00d69-126">MainAccount</span><span class="sxs-lookup"><span data-stu-id="00d69-126">MainAccount</span></span>                      | <span data-ttu-id="00d69-127">msdyn\_mainaccounts</span><span class="sxs-lookup"><span data-stu-id="00d69-127">msdyn\_mainaccounts</span></span>        |
<span data-ttu-id="00d69-128">Redovisning</span><span class="sxs-lookup"><span data-stu-id="00d69-128">Ledger</span></span>                           | <span data-ttu-id="00d69-129">msdyn\_ledgers</span><span class="sxs-lookup"><span data-stu-id="00d69-129">msdyn\_ledgers</span></span>        |
<span data-ttu-id="00d69-130">ExchangeRates</span><span class="sxs-lookup"><span data-stu-id="00d69-130">ExchangeRates</span></span>                    | <span data-ttu-id="00d69-131">msdyn\_currencyexchangerates</span><span class="sxs-lookup"><span data-stu-id="00d69-131">msdyn\_currencyexchangerates</span></span>        |
<span data-ttu-id="00d69-132">FinancialCalendarPeriod</span><span class="sxs-lookup"><span data-stu-id="00d69-132">FinancialCalendarPeriod</span></span>          | <span data-ttu-id="00d69-133">msdyn\_fiscalcalendarperiods</span><span class="sxs-lookup"><span data-stu-id="00d69-133">msdyn\_fiscalcalendarperiods</span></span>        |
<span data-ttu-id="00d69-134">DimensionAttributeEntity</span><span class="sxs-lookup"><span data-stu-id="00d69-134">DimensionAttributeEntity</span></span>         | <span data-ttu-id="00d69-135">msdyn\_dimensionattributes</span><span class="sxs-lookup"><span data-stu-id="00d69-135">msdyn\_dimensionattributes</span></span>        |
<span data-ttu-id="00d69-136">DimensionIntegrationFormatEntity</span><span class="sxs-lookup"><span data-stu-id="00d69-136">DimensionIntegrationFormatEntity</span></span> | <span data-ttu-id="00d69-137">msdyn\_financialdimensionformats</span><span class="sxs-lookup"><span data-stu-id="00d69-137">msdyn\_financialdimensionformats</span></span>        |
<span data-ttu-id="00d69-138">LedgerChartOfAccounts</span><span class="sxs-lookup"><span data-stu-id="00d69-138">LedgerChartOfAccounts</span></span>            | <span data-ttu-id="00d69-139">msdyn\_chartofaccounts</span><span class="sxs-lookup"><span data-stu-id="00d69-139">msdyn\_chartofaccounts</span></span>        |


[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Currency](includes/Currencies-transactioncurrencies.md)]

[!include [Fiscal calendar](includes/FiscalCalendar-msdyn-fiscalcalendars.md)]

[!include [Fiscal calendar year](includes/FiscalCalendarYear-msdyn-fiscalcalendaryears.md)]

[!include [Exchange rate types](includes/ExchRateType-msdyn-exchangeratetypes.md)]

[!include [Exchange rate pair](includes/ExchangeRateCurrencyPair-msdyn-currencyexchangeratepairs.md)]

[!include [Ledger fiscal periods](includes/FiscalPeriodEntity-msdyn-fiscalcalendarperiods.md)]

[!include [Main account category](includes/MainAccountCategory-msdyn-mainaccountcategory.md)]

[!include [Main account](includes/MainAccount-msdyn-mainaccounts.md)]

[!include [Ledger](includes/Ledger-msdyn-ledgers.md)]

[!include [Exchange rates](includes/ExchangeRates-msdyn-currencyexchangerates.md)]

[!include [Financial Calendar Period](includes/FiscalPeriodEntity-msdyn-fiscalcalendarperiods.md)]

[!include [Dimension attribute](includes/DimensionAttributeEntity-msdyn-dimensionattributes.md)]

[!include [Dimension integration format](includes/DimensionIntegrationFormatEntity-msdyn-financialdimensionformats.md)]

[!include [Chart Of Account](includes/LedgerChartOfAccounts-msdyn-chartofaccounts.md)]




