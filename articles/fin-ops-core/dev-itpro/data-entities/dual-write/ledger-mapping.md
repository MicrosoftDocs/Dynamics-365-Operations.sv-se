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
ms.author: rhaertle
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 20c038d0d4fe8ec3e07219862f98aef970882f26
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/10/2020
ms.locfileid: "3985255"
---
# <a name="integrated-ledger"></a>Integrerad redovisning

[!include [banner](../../includes/banner.md)]



I ett affärsprogram definierar redovisningsdata den kärna som är inställd för hur ett företag gör affärer. Redovisningsdata beskriver t.ex. räkenskapsåret som företaget följer, de valutor det använder och vilka konton det använder. I det här avsnittet beskrivs integrationen av dessa grundläggande ekonomiska data.

## <a name="templates"></a>Mallar

Redovisningsdata inkluderar en samling entitetsmappningar för grundläggande ekonomiska som fungerar tillsammans under kunddatainteraktion, som visas i följande tabell.

Finance and Operations-appar      | Modellstyrda appar i Dynamics 365 | beskrivning
---------------------------------|----------------------------------|------------
Valutor                       | transactioncurrencies            |
FiscalCalendar                   | msdyn\_fiscalcalendars        |
FiscalCalendarYear               | msdyn\_fiscalcalendaryears        |
ExchRateType                     | msdyn\_exchangeratetypes        |
ExchangeRateCurrencyPair         | msdyn\_currencyexchangeratepairs        |
FiscalPeriodEntity               | msdyn\_fiscalcalendarperiods        |
MainAccountCategory              | msdyn\_mainaccountcategory        |
MainAccount                      | msdyn\_mainaccounts        |
Redovisning                           | msdyn\_ledgers        |
ExchangeRates                    | msdyn\_currencyexchangerates        |
FinancialCalendarPeriod          | msdyn\_fiscalcalendarperiods        |
DimensionAttributeEntity         | msdyn\_dimensionattributes        |
DimensionIntegrationFormatEntity | msdyn\_financialdimensionformats        |
LedgerChartOfAccounts            | msdyn\_chartofaccounts        |


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




