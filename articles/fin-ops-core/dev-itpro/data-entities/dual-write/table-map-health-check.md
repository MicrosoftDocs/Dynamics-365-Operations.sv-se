---
title: Felkoder för hälsokontrollen av tabellmappning
description: Det här avsnittet beskriver felkoder för hälsokontrollen av tabellkartan.
author: nhelgren
ms.date: 10/04/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: nhelgren
ms.search.validFrom: 2021-10-04
ms.openlocfilehash: c2d1f1e39a5ddccddf6fbbf524ff7eb0945b3c32
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/10/2021
ms.locfileid: "7782247"
---
# <a name="errors-codes-for-the-table-map-health-check"></a>Felkoder för hälsokontrollen av tabellmappning

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Det här avsnittet beskriver felkoder för hälsokontrollen av tabellkartan.

## <a name="error-100"></a>Fel 100

Felmeddelandet är "Minsta begärda Finance and Operations plattformsversion is PU 43 för att köra Finance and Operations rekommendationer."

För den här funktionen krävs uppdateringar av plattform för version 10.0.19 eller senare av Finance and Operations-appar.

## <a name="error-400"></a>Fel 400

Felmeddelandet är: "Ingen registreringsdata för affärshändelser hittades för enheten \{Finance and Operations UniqueEntityName\} vilket betyder att kartan antingen inte körs eller så är all fältmappning enkelriktad."

## <a name="error-500"></a>Fel 500

Felmeddelandet är "Inga projektkonfigurationer hittades för projektet \{projektnamn\}. Detta kan vara antingen projektet inte är aktiverat eller att alla fältmappningar är enkelriktade från Customer Engagement till Finance and Operations."

Kontrollera mappningarna för registerkartan. Om de är enkelriktade från kundengagemangsappar till Finance and Operations-appar genereras ingen trafik för livesynkronisering från Finance and Operations-appar till Dataverse.

## <a name="error-900"></a>Fel 900

Felmeddelandet är formatet "Ogiltigt källfilterfilterformat \{sourceFilter\} för entiteten \{Finance and Operations UniqueEntityName\}."

Källfiltret som anges på registerkartan för Finance and Operations-app är inte syntaktiskt korrekt. För att validera filterkriterierna, se [Felsök problem med livesynkronisering](dual-write-troubleshooting-live-sync.md#live-synchronization-issues-that-are-caused-by-incorrect-query-filter-syntax-on-the-dual-write-maps).

## <a name="error-1000"></a>Fel 1000

Felmeddelandet är, "Entity \{Finance and Operations UniqueEntityName\} fråga som används för dubbelriktad skrivning livesynkronisering är \{Finance and Operations EntityFilterQueryString\}. Poster som uppfyller frågevillkoren plockas upp för synkronisering med live."

Enhetsfrågan som returnerades är stöd-SQL-frågan för enheten. Sök efter interna sammankopplingar eller filter för frågan som bestämmer vilka affärsdata som plockas för livesynkronisering. Inre sammankopplingar och filter är obligatoriska villkor som måste uppfyllas för varje post som hämtas för livesynkronisering av filter.

## <a name="error-1300"></a>Fel 1300

Felmeddelandet är, "Virtuella fält \{s.EntityFieldName\} för enheten \{Finance and Operations EntityMetadata.EntityProperties.LogicalEntityName\} kanske inte kan spåras för dubbelriktad skrivning."

Virtuella fält från Finance and Operations register har inte aktiverats för spårning. Synkroniseringen av live-synkronisering kan synkroniseras, men de ändringar som görs i kolumnerna kan inte hämtas.

## <a name="error-1500"></a>Fel 1500

Felmeddelandet är: "Det bör finnas minst ett fält mappat till ett icke-uppslagningsfält för Customer Engagement för att möjliggöra spårning på datakällan \{datasource.DataSourceName\}."

Datakällan från enheten har inget fält som mappas för dubbelriktig skrivning. Ändringar i det underliggande registret spåras inte för dubbelriktig skrivning.

## <a name="error-1600"></a>Fel 1600

Felmeddelandet är, "Datakälla: \{datasource.DataSourceName\} för entiteten \{Finance and Operations EntityMetadata.EntityProperties.LogicalEntityName\} har ett intervall. Endast poster som uppfyller intervallvillkoret plockas för utgående samtal."

Enheter i Finance and Operations program kan ha datakällor där filterintervall aktiveras. De här intervallen definierar de poster som plockas som en del av en live-synkronisering. Om vissa poster hoppas över från Finance and Operations program till Dataverse, kontrollerar du om posterna uppfyller intervallkriterierna i enheten. Ett enkelt sätt att göra den här kontrollen är att köra en SQL-fråga som liknar följande exempel.

```sql
select * from <EntityName> where <filter criteria for the records> on SQL.
```

## <a name="error-1700"></a>Fel 1700

Felmeddelandet är, "Register: \{datasourceTable.Key.subscribedTableName\} för entitet \{datasourceTable.Key.entityName\} spåras för entiteten \{origTableToEntityMaps.EntityName\}. Samma register som spåras för flera enheter kan påverka systemets prestanda för synkroniserade live-transaktioner."

Om samma register spåras av flera enheter utlöser en ändring av registret en utvärdering av dubbelriktad skrivning för de länkade enheterna. Även om filterklausulerna endast skickar giltiga poster kan utvärderingen orsaka ett prestandaproblem om det finns körande frågor eller inte optimerade frågeplaner. Det här problemet kan eventuellt inte undvikas ur affärsperspektiv. Om det finns många korsade register mellan flera enheter bör du emellertid förenkla enheten eller kontrollera optimeringar för enhetsfrågor.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]