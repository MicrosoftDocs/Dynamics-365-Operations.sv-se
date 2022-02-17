---
title: Integrerad redovisning
description: I det här avsnittet beskrivs integreringen av redovisning mellan Finance and Operations och andra Dynamics 365-appar med Dataverse.
author: tonyafehr
ms.date: 09/06/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: tfehr
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 0deb4198acb59b90bf06e4050889d028df2223e3
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/31/2022
ms.locfileid: "8063657"
---
# <a name="integrated-ledger"></a>Integrerad redovisning

[!include [banner](../../includes/banner.md)]



I ett affärsprogram definierar redovisningsdata den kärna som är inställd för hur ett företag gör affärer. Redovisningsdata beskriver t.ex. räkenskapsåret som företaget följer, de valutor det använder och vilka konton det använder. I det här avsnittet beskrivs integreringen av dessa grundläggande ekonomiska data.

## <a name="templates"></a>Mallar

Redovisningsdata inkluderar en samling tabellmappningar för grundläggande ekonomiska som fungerar tillsammans under kunddatainteraktion, som visas i följande tabell.

Finance and Operations-appar | Kundengagemangsappar     | beskrivning
---------------------------------|----------------------------------|------------
[Valutakurser för CDS](mapping-reference.md#123) | msdyn_currencyexchangerates |
[Kontoplan](mapping-reference.md#121) | msdyn_chartofaccountses |
[Valutor](mapping-reference.md#218) | transactioncurrencies |
[Valutapar för valutakurs](mapping-reference.md#122) | msdyn_currencyexchangeratepairs |
[Valutakurstyp](mapping-reference.md#129) | msdyn_exchangeratetypes |
[Format för ekonomisk dimension](mapping-reference.md#130) | msdyn_financialdimensionformats |
[Ekonomiska dimensioner](mapping-reference.md#128) | msdyn_dimensionattributes |
[Integreringsenhet för räkenskapskalender](mapping-reference.md#132) | msdyn_fiscalcalendars |
[Period i räkenskapskalender](mapping-reference.md#131) | msdyn_fiscalcalendarperiods |
[Integreringsenhet för räkenskapskalenderår](mapping-reference.md#133) | msdyn_fiscalcalendaryears |
[Ledger](mapping-reference.md#148) | msdyn_ledgers |
[Huvudkonto](mapping-reference.md#152) | msdyn_mainaccounts |
[Huvudkontokategorier](mapping-reference.md#151) | msdyn_mainaccountcategories |

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
