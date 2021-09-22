---
title: Uppdateringskonflikt när lagervärderingsmetoden är standardkostnad eller glidande medelvärde
description: En uppdateringskonflikt uppstår när lagervärderingsmetoden är standardkostnad eller glidande medelvärde
author: AndersGirke
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: InventAgingStorage, InventAgingStorageChart, InventAgingStorageDetails, InventValueProcess, InventValueReportSetup, InventClosing
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 920d20d19843ce0cac678c5426c00ec99aa61c61
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477662"
---
# <a name="an-update-conflict-occurs-when-the-inventory-valuation-method-is-either-standard-cost-or-moving-average"></a>En uppdateringskonflikt uppstår när lagervärderingsmetoden är standardkostnad eller glidande medelvärde

## <a name="symptoms"></a>Symtom

När du bokför dokument som lagerjournaler, inköpsorderfakturor eller försäljningsorderfakturor parallellt med skalbarhet och prestanda, kanske du får ett felmeddelande om en uppdateringskonflikt och vissa dokument kanske inte bokförs. Detta problem kan uppstå när lagervärderingsmetoden är *Standardkostnad* eller *Glidande medelvärde*. Båda dessa metoder är beständig kostnadsredovisning. Med andra ord bestäms den slutliga kostnaden vid bokföringstidsdatumet.

Om du använder metoden *Glidande medelvärde* liknar felmeddelandet det här exemplet:

> Lagervärde xx.xx förväntas inte efter den proportionella utgiftsberäkningen

Om du använder metoden *Standardkostnad* liknar felmeddelandet det här exemplet:

> Standardkostnaden matchar inte det ekonomiska lagervärdet efter uppdateringen. Värde = xx.xx, Kvt = yyy.yy, Standardkostnad = zz.zz

## <a name="workaround"></a>Lösning

Fram till dess att Microsoft har frisläppt en lösning på problemet kan du överväga att använda följande lösningar för att undvika eller minska dessa fel:

- Bokföra om de misslyckade dokumenten på samma sätt.
- Skapa dokument med färre rader.
- Undvika decimalvärden i standardkostnaden. Försök att definiera standardkostnaden så att fältet **Priskvantitet** sätts till *1*. Om du måste ange ett värde för **priskvantitet** som är mer än *1*, försöker du minimera antalet decimaler i enhetens standardkostnad. (Helst bör det finnas färre än två decimaler.) Undvik till exempel att definiera standardkostnadsinställningar som **Pris** = *10* och **Priskvantitet** = *3*, eftersom de skapar en enhetsstandardkostnad på 3,333333 (där decimalvärdet upprepas).
- Undvik att ha flera rader som innehar samma kombination av produkt och ekonomiska lagerdimensioner i en majoritet av dokumenten.
- Minska parallelliseringsgraden. (I så fall kanske ditt system snabbare, eftersom färre uppdateringskonflikter och nya försök görs.)
