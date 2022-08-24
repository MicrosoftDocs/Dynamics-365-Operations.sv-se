---
title: Integrerad redovisning
description: I den här artikeln beskrivs integreringen av redovisningsdata mellan Ekonomi och drift och andra Dynamics 365-program med hjälp av Dataverse.
author: RamaKrishnamoorthy
ms.date: 09/06/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: 728c131c260586e7f1f787f22ccf02ed81c94c01
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9289161"
---
# <a name="integrated-ledger"></a>Integrerad redovisning

[!include [banner](../../includes/banner.md)]



I ett affärsprogram definierar redovisningsdata den kärna som är inställd för hur ett företag gör affärer. Redovisningsdata beskriver t.ex. räkenskapsåret som företaget följer, de valutor det använder och vilka konton det använder. I den här artikeln beskrivs integreringen av dessa grundläggande ekonomiska data.

## <a name="templates"></a>Mallar

Redovisningsdata inkluderar en samling tabellmappningar för grundläggande ekonomiska som fungerar tillsammans under kunddatainteraktion, som visas i följande tabell.

Appar för ekonomi och drift | Kundengagemangsappar     | beskrivning
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

