---
title: Felsöka kostnadshantering
description: I det här avsnittet beskrivs hur du åtgärdar problem som kan uppstå när du arbetar med kostnadshantering.
author: riluan
manager: tfehr
ms.date: 10/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventAgingStorage, InventAgingStorageChart, InventAgingStorageDetails, InventValueProcess, InventValueReportSetup, InventClosing
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: riluan
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: b8c527e578fee6abfeeade99fba8070365c020bd
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4983860"
---
# <a name="troubleshoot-cost-management"></a>Felsöka kostnadshantering

I det här avsnittet beskrivs hur du åtgärdar problem som kan uppstå när du arbetar med kostnadshantering.

## <a name="functional-gaps-between-the-inventory-valueaging-reports-and-their-storage-versions"></a>Funktionella luckor mellan lagrets värde- och åldersrapporter och deras lagringsversioner

[Rapporten lagring av lagerföråldringsrapport](inventory-aging-report-storage.md) och [Lagringsrapport för lagervärde](inventory-value-report-storage.md) funktioner aktiverar Supply Chain Management för att visa stora volymer av lagertransaktioner. I varje fall sparas rapportresultaten för bläddring och export, till skillnad från de versioner av rapporterna som inte finns i minnet. Vissa funktioner i versionerna av de andra versionerna än de här rapporterna finns dock inte i lagringsversionerna. Följande underavsnitt innehåller en sammanfattning av skillnaderna och lösningar.

### <a name="storage-reports-dont-include-subtotals-even-if-they-are-enabled-in-the-report-layout"></a>Lagringsrapporter inkluderar inte del summor, även om de är aktiverade i rapportlayouten

Delsummor kan orsaka problem när resultatet exporteras, särskilt om användarna ändrar postserien.

Du kan kontrollera delsummorna genom att exportera resultatet till Microsoft Excel. Om du vill kontrollera delsummor inom Supply Chain Management använder du [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att aktivera funktionerna *nya rutnätskontrollen* och *(förhandsgranskning) gruppering i rutnät*, vilket ger ett mycket mer flexibelt sätt att visa delsummor för en grupp efter kolumn. Mer information finns i [Rutnätsmöjligheter](../../fin-ops-core/fin-ops/get-started/grid-capabilities.md).

### <a name="inventory-value-storage-report-doesnt-support-ledger-account-information"></a>Rapporten lagringsvärde för lagerhanteringskonto stöder inte redovisningskontoinformation

Du kan köra råbalansen för att få fram saldot för lagerkonton och jämföra det med rapporten **lagring för lagervärde**.

## <a name="warnings-or-errors-are-shown-when-changing-a-ledger-period-status-without-closing-inventory"></a>Varningar eller felmeddelanden visas när en redovisningsperiodsstatus ändras utan att lagret stängs

Microsoft introducerade följande valideringar för att förhindra problem som orsakas av felaktig periodslutprocess kring kostnadsredovisning. Om du stöter på något av följande felmeddelanden hittar du [KB 4561987](https://fix.lcs.dynamics.com/Issue/Details?kb=4561987&bugId=445351&dbType=3&qc=f514f2adcddcddceec43af58c26ae8a9020effdc7cdfe085d9d0deeb8cc7b6a3) för mer information om hur du löser dessa problem.

- Du kör en ny beräkning med ett datum %1 (10-02-2019). Den senast registrerade omberäkningen kördes under en tidigare period med ett datum %2 (20-01-2019). Inget utförande av en inventering nära ett datum %3 (31-01-2019) matchningsperiodens slut har registrerats. Kom ihåg att köra en lagerstängning från och med %3 (31-01-2019) som matchar periodens slut. Värderingen av lager, sålda varor och avvikelser kan inte vara korrekt i delredovisning eller redovisning förrän denna har utförts.

- Du håller på att ändra status för redovisningsperioden %1 till %2. Inget utförande av en inventering nära ett datum %3 matchningsperiodens slut har registrerats. Kör en lagerstängning för att %3 matcha periodens slut innan du ändrar status. Värderingen av lager, sålda varor och avvikelser kan inte vara korrekt i delredovisning eller redovisning förrän denna har utförts. Rapporterad från juridisk person %4. För tillfället i informationssyfte, men du måste utföra en sådan åtgärd i framtiden.

- Kontostrukturen %1 har ändrats. Ett eller flera huvudkonton %2 finns inte längre. Dessa huvudkonton är obligatoriska för %3 med ett datum %4. Lägg till dessa huvudkonton i kontostrukturen %1 innan du kan återuppta %3 jobbet. För tillfället i informationssyfte, men du måste utföra en sådan åtgärd i framtiden.

- Du håller på att utföra en inventering nära ett datum %1 (31-01-2019). Ingen kostnadskalkylering med automatisk lageravräkning med datum %2 (31-01-2019) matchningsperiodens slut har registrerats. Kom ihåg att utföra en kostnadskalkylering med automatisk lageravräkning med datum %3 (31-01-2019) matchningsperiodens slut. Värderingen av lager, sålda varor och avvikelser kan inte vara korrekt i delredovisning eller redovisning förrän denna har utförts.

- Du håller på att utföra en ny kostnadskalkylering med automatisk lageravräkning med ett datum %1 (28-02-2019). Den senast registrerade kostnadskalkylering med automatisk lageravräkning kördes under en tidigare period med ett datum %2 (31-01-2019). Inget utförande av en inventering nära ett datum %3 (31-01-2019) matchningsperiodens slut har registrerats.
Kom ihåg att köra en lagerstängning från och med %3 (31-01-2019) som matchar periodens slut. Värderingen av lager, sålda varor och avvikelser kan inte vara korrekt i delredovisning eller redovisning förrän lagerstängningen har utförts.

## <a name="inventory-aging-report-discrepancies"></a>Avvikelser för lagerföråldringsrapport

**Åldersfördelningsrapport för lager** visar olika värden när den visas på olika lagringsdimensioner (t.ex. webbplats eller lagerställe). Mer information om rapportlogik finns i rapport över [exempel på lagerföråldringsrapport och logik](inventory-aging-report.md).

## <a name="an-update-conflict-occurs-when-the-inventory-valuation-method-is-either-standard-cost-or-moving-average"></a>En uppdateringskonflikt uppstår när lagervärderingsmetoden är Standardkostnad eller Glidande medelvärde

När du bokför dokument som lagerjournaler, inköpsorderfakturor eller försäljningsorderfakturor parallellt med skalbarhet och prestanda, kanske du får ett felmeddelande om en uppdateringskonflikt och vissa dokument kanske inte bokförs. Detta problem kan uppstå när lagervärderingsmetoden är *Standardkostnad* eller *Glidande medelvärde*. Båda dessa metoder är beständig kostnadsredovisning. Med andra ord bestäms den slutliga kostnaden vid bokföringstidsdatumet.

Om du använder metoden *Glidande medelvärde* liknar felmeddelandet det här exemplet:

> Lagervärde xx.xx förväntas inte efter den proportionella utgiftsberäkningen

Om du använder metoden *Standardkostnad* liknar felmeddelandet det här exemplet:

> Standardkostnaden matchar inte det ekonomiska lagervärdet efter uppdateringen. Värde = xx.xx, Kvt = yyy.yy, Standardkostnad = zz.zz

Fram till dess att Microsoft har frisläppt en lösning på problemet kan du överväga att använda följande lösningar för att undvika eller minska dessa fel:

- Bokföra om de misslyckade dokumenten på samma sätt.
- Skapa dokument med färre rader.
- Undvika decimalvärden i standardkostnaden. Försök att definiera standardkostnaden så att fältet **Priskvantitet** sätts till *1*. Om du måste ange ett värde för **priskvantitet** som är mer än *1*, försöker du minimera antalet decimaler i enhetens standardkostnad. (Helst bör det finnas färre än två decimaler.) Undvik till exempel att definiera standardkostnadsinställningar som **Pris** = *10* och **Priskvantitet** = *3*, eftersom de skapar en enhetsstandardkostnad på 3,333333 (där decimalvärdet upprepas).
- Undvik att ha flera rader som innehar samma kombination av produkt och ekonomiska lagerdimensioner i en majoritet av dokumenten.
- Minska parallelliseringsgraden. (I så fall kanske ditt system snabbare, eftersom färre uppdateringskonflikter och nya försök görs.)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]