---
title: Felkoder för hälsokontrollen av tabellmappning
description: Den här artikeln beskriver felkoder för hälsokontrollen av tabellmappningen.
author: RamaKrishnamoorthy
ms.date: 05/31/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-10-04
ms.openlocfilehash: d3f413f34296fd01da6741bb49658285394cbd17
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9288773"
---
# <a name="errors-codes-for-the-table-map-health-check"></a>Felkoder för hälsokontrollen av tabellmappning

[!include [banner](../../includes/banner.md)]



Den här artikeln beskriver felkoder för hälsokontrollen av tabellmappningen.

## <a name="error-100"></a>Fel 100

Felmeddelandet är "Minsta begärda plattformsversion för Ekonomi och drift är PU 43 för att köra rekommendationer för ekonomi och drift."

För den här funktionen krävs plattformuppdateringar för version 10.0.19 eller senare av appar för ekonomi och drift.

## <a name="error-400"></a>Fel 400

Felmeddelandet är: "Ingen registreringsdata för affärshändelser hittades för entiteten \{finance and operations UniqueEntityName\}, vilket betyder att mappningen antingen inte körs eller också är all fältmappning enkelriktad."

## <a name="error-500"></a>Fel 500

Felmeddelandet är "Inga projektkonfigurationer hittades för projektet \{projektnamn\}. Detta kan vara antingen att projektet inte är aktiverat eller att alla fältmappningar är enkelriktade från Kundengagemang till Ekonomi och Drift."

Kontrollera mappningarna för registermappningen. Om de är enkelriktade från kundengagemangsappar till appar för ekonomi och drift genereras ingen trafik för livesynkronisering från appar för ekonomi och drift till Dataverse.

## <a name="error-900"></a>Fel 900

Felmeddelandet är "Ogiltigt källfilter \{sourceFilter\}-format för entitet \{finance and operations UniqueEntityName\}."

Källfiltret som anges på tabellmappningen för appar för ekonomi och drift är inte syntaktiskt korrekt. För att validera filterkriterierna, se [Felsök problem med livesynkronisering](dual-write-troubleshooting-live-sync.md#live-synchronization-issues-that-are-caused-by-incorrect-query-filter-syntax-on-the-dual-write-maps).

## <a name="error-1000"></a>Fel 1000

Felmeddelandet är "Entitet \{finance and operations UniqueEntityName\} fråga som används för livesynkronisering med dubbelriktad skrivning är \{finance and operations EntityFilterQueryString\}. Poster som uppfyller frågevillkoren plockas upp för synkronisering med live."

Enhetsfrågan som returnerades är stöd-SQL-frågan för enheten. Sök efter interna sammankopplingar eller filter för frågan som bestämmer vilka affärsdata som plockas för livesynkronisering. Inre sammankopplingar och filter är obligatoriska villkor som måste uppfyllas för varje post som hämtas för livesynkronisering av filter.

## <a name="error-1300"></a>Fel 1300

Felmeddelandet är "Virtuella fält \{s.EntityFieldName\} för entitet \{finance and operations EntityMetadata.EntityProperties.LogicalEntityName\} kanske inte kan spåras för dubbelriktad skrivning."

Virtuella fält från tabeller för ekonomi och drift har inte aktiverats för spårning. Synkroniseringen av live-synkronisering kan synkroniseras, men de ändringar som görs i kolumnerna kan inte hämtas.

## <a name="error-1500"></a>Fel 1500

Felmeddelandet är: "Det bör finnas minst ett fält mappat till ett icke-uppslagningsfält för Customer Engagement för att möjliggöra spårning på datakällan \{datasource.DataSourceName\}."

Datakällan från enheten har inget fält som mappas för dubbelriktig skrivning. Ändringar i det underliggande registret spåras inte för dubbelriktig skrivning.

## <a name="error-1600"></a>Fel 1600

Felmeddelandet är "Datakälla: \{datasource.DataSourceName\} för entitet \{finance and operations EntityMetadata.EntityProperties.LogicalEntityName\} har ett intervall. Endast poster som uppfyller intervallvillkoret plockas för utgående samtal."

Entiteter i appar för ekonomi och drift kan ha datakällor där filterintervall aktiverats. De här intervallen definierar de poster som plockas som en del av en live-synkronisering. Om vissa poster hoppas över från appar för ekonomi och drift till Dataverse kontrollerar du huruvida posterna uppfyller intervallkriterierna för entiteten. Ett enkelt sätt att göra den här kontrollen är att köra en SQL-fråga som liknar följande exempel.

```sql
select * from <EntityName> where <filter criteria for the records> on SQL.
```

## <a name="error-1700"></a>Fel 1700

Felmeddelandet är, "Tabell: \{datasourceTable.Key.subscribedTableName\} för entitet \{datasourceTable.Key.entityName\} spåras för entitet \{origTableToEntityMaps.EntityName\}. Samma register som spåras för flera enheter kan påverka systemets prestanda för synkroniserade live-transaktioner."

Om samma register spåras av flera enheter utlöser en ändring av registret en utvärdering av dubbelriktad skrivning för de länkade enheterna. Även om filterklausulerna endast skickar giltiga poster kan utvärderingen orsaka ett prestandaproblem om det finns körande frågor eller inte optimerade frågeplaner. Det här problemet kan eventuellt inte undvikas ur affärsperspektiv. Om det finns många korsade register mellan flera enheter bör du emellertid förenkla enheten eller kontrollera optimeringar för enhetsfrågor.

## <a name="error-1800"></a>Fel 1800
Felmeddelandet är "Datasource : {} för enhet CustCustomerV3Entity innehåller ett intervallvärde. Inkommande postuppdateringar/-tillägg från Dataverse till Ekonomi och drift kan påverkas av intervallvärden för entitet. Testa postuppdateringar från Dataverse till Ekonomi och drift med poster som inte matchar filterkriteriet för att validera dina inställningar."

Om ett intervall har angetts för enheten i appar för ekonomi och drift ska de inkommande synkroniseringen från Dataverse till appar för ekonomi och drift testas för uppdateringsbeteende för poster som inte matchar det här intervallkriteriet. Alla poster som inte matchar intervallet behandlas som en infogningsoperation av enheten. Om det finns en befintlig post i det underliggande registret misslyckas infogning. Vi rekommenderar att du testar det här fallet i alla scenarier innan du distribuerar till produktion.

## <a name="error-1900"></a>Fel 1900
Felmeddelandet är, "Entittet: har {}datakällor som inte spåras för utgående nedskrivningar. Detta kan påverka prestandan för direkt synkroniserade frågor. Omforma entiteten i Ekonomi och drift för att ta bort oanvända datakällor och tabeller eller implementera getEntityRecordIdsImpactedByTableChange för att optimera körtidsfrågorna."

Om det finns många datakällor som inte används för spårning i den faktiska livesynkroniseringen från appar för ekonomi och drift, finns det en möjlighet att enhetens prestanda kan påverka livesynkroniseringen. För att optimera de spårade tabellerna, använd metoden getEntityRecordIdsImpactedByTableChange.

## <a name="error-5000"></a>Fel 5000
Felmeddelandet är"Synkrona plugin-program har registrerats för datahanteringshändelser för enhetskonton. De kan påverka den initiala synkroniseringen och den live synkroniserade importprestandan till Dataverse. Du får bäst prestanda genom att ändra den till asynkron bearbetning. Lista över registrerade plugin-program {}."

Synkrona plugin-program på en Dataverse entitet kan påverka livesynkronisering och initial synkroniseringsprestanda när den ökar transaktionsbelastningen. Vi rekommenderar att du antingen stänger av den eller så gör du dessa synkroniserade om du har långsamma beläggningstider i den första synkroniseringen eller live-synkroniseringen för en viss enhet.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

