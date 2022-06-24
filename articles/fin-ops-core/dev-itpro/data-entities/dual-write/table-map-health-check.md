---
title: Felkoder för hälsokontrollen av tabellmappning
description: Den här artikeln beskriver felkoder för hälsokontrollen av tabellkartan.
author: RamaKrishnamoorthy
ms.date: 05/31/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-10-04
ms.openlocfilehash: 3ae78077fc716311c38620b14665af3983a44c2d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8884095"
---
# <a name="errors-codes-for-the-table-map-health-check"></a>Felkoder för hälsokontrollen av tabellmappning

[!include [banner](../../includes/banner.md)]



Den här artikeln beskriver felkoder för hälsokontrollen av tabellkartan.

## <a name="error-100"></a>Fel 100

Felmeddelandet är "Minsta begärda Ekonomi och Drift plattformsversion is PU 43 för att köra Ekonomi och Drift-rekommendationer."

För den här funktionen krävs uppdateringar av plattform för version 10.0.19 eller senare av Ekonomi och Drift-appar.

## <a name="error-400"></a>Fel 400

Felmeddelandet är: "Ingen registreringsdata för affärshändelser hittades för enheten \{Ekonomi och drift UniqueEntityName\} vilket betyder att kartan antingen inte körs eller så är all fältmappning enkelriktad."

## <a name="error-500"></a>Fel 500

Felmeddelandet är "Inga projektkonfigurationer hittades för projektet \{projektnamn\}. Detta kan vara antingen projektet inte är aktiverat eller att alla fältmappningar är enkelriktade från Customer Engagement till Ekonomi och Drift."

Kontrollera mappningarna för registerkartan. Om de är enkelriktade från kundengagemangsappar till Ekonomi och Drift-appar genereras ingen trafik för livesynkronisering från Ekonomi och Drift-appar till Dataverse.

## <a name="error-900"></a>Fel 900

Felmeddelandet är formatet "Ogiltigt källfilterfilterformat \{sourceFilter\} för entiteten \{Finance and Operations UniqueEntityName\}."

Källfiltret som anges på registerkartan för Ekonomi och Drift-app är inte syntaktiskt korrekt. För att validera filterkriterierna, se [Felsök problem med livesynkronisering](dual-write-troubleshooting-live-sync.md#live-synchronization-issues-that-are-caused-by-incorrect-query-filter-syntax-on-the-dual-write-maps).

## <a name="error-1000"></a>Fel 1000

Felmeddelandet är, "Entity \{Finance and Operations UniqueEntityName\}  fråga som används för dubbelriktad skrivning livesynkronisering är \{Finance and Operations EntityFilterQueryString\}. Poster som uppfyller frågevillkoren plockas upp för synkronisering med live."

Enhetsfrågan som returnerades är stöd-SQL-frågan för enheten. Sök efter interna sammankopplingar eller filter för frågan som bestämmer vilka affärsdata som plockas för livesynkronisering. Inre sammankopplingar och filter är obligatoriska villkor som måste uppfyllas för varje post som hämtas för livesynkronisering av filter.

## <a name="error-1300"></a>Fel 1300

Felmeddelandet är, "Virtuella fält \{s.EntityFieldName\} för enheten \{Finance and Operations EntityMetadata.EntityProperties.LogicalEntityName\} kanske inte kan spåras för dubbelriktad skrivning."

Virtuella fält från Ekonomi och Drift register har inte aktiverats för spårning. Synkroniseringen av live-synkronisering kan synkroniseras, men de ändringar som görs i kolumnerna kan inte hämtas.

## <a name="error-1500"></a>Fel 1500

Felmeddelandet är: "Det bör finnas minst ett fält mappat till ett icke-uppslagningsfält för Customer Engagement för att möjliggöra spårning på datakällan \{datasource.DataSourceName\}."

Datakällan från enheten har inget fält som mappas för dubbelriktig skrivning. Ändringar i det underliggande registret spåras inte för dubbelriktig skrivning.

## <a name="error-1600"></a>Fel 1600

Felmeddelandet är, "Datakälla, "Datasource: \{datasource.DataSourceName\} för entiteten \{Finance and Operations EntityMetadata.EntityProperties.LogicalEntityName\} har ett intervall. Endast poster som uppfyller intervallvillkoret plockas för utgående samtal."

Enheter i Ekonomi och Drift-program kan ha datakällor där filterintervall aktiveras. De här intervallen definierar de poster som plockas som en del av en live-synkronisering. Om vissa poster hoppas över från Ekonomi och Drift-program till Dataverse, kontrollerar du om posterna uppfyller intervallkriterierna i enheten. Ett enkelt sätt att göra den här kontrollen är att köra en SQL-fråga som liknar följande exempel.

```sql
select * from <EntityName> where <filter criteria for the records> on SQL.
```

## <a name="error-1700"></a>Fel 1700

Felmeddelandet är, "Register: \{datasourceTable.Key.subscribedTableName\} för entitet \{datasourceTable.Key.entityName\} spåras för entiteten \{origTableToEntityMaps.EntityName\}. Samma register som spåras för flera enheter kan påverka systemets prestanda för synkroniserade live-transaktioner."

Om samma register spåras av flera enheter utlöser en ändring av registret en utvärdering av dubbelriktad skrivning för de länkade enheterna. Även om filterklausulerna endast skickar giltiga poster kan utvärderingen orsaka ett prestandaproblem om det finns körande frågor eller inte optimerade frågeplaner. Det här problemet kan eventuellt inte undvikas ur affärsperspektiv. Om det finns många korsade register mellan flera enheter bör du emellertid förenkla enheten eller kontrollera optimeringar för enhetsfrågor.

## <a name="error-1800"></a>Fel 1800
Felmeddelandet är "Datasource : {} för enhet CustCustomerV3Entity innehåller ett intervallvärde. Inkommande post upserts från Dataverse Ekonomi och drift kan påverkas av intervallvärden för entitet. Testa postuppdateringar från Dataverse Ekonomi och drift med poster som inte matchar filterkriteriet för att validera dina inställningar."

Om ett intervall har angetts för enheten i appar för ekonomi och drift ska de inkommande synkroniseringen från Dataverse till appar för ekonomi och drift testas för uppdateringsbeteende för poster som inte matchar det här intervallkriteriet. Alla poster som inte matchar intervallet behandlas som en infogningsoperation av enheten. Om det finns en befintlig post i det underliggande registret misslyckas infogning. Vi rekommenderar att du testar det här fallet i alla scenarier innan du distribuerar till produktion.

## <a name="error-1900"></a>Fel 1900
Felmeddelandet är, "Entittet: har {}datakällor som inte spåras för utgående nedskrivningar. Detta kan påverka prestandan för direkt synkroniserade frågor. Omforma enheten i ekonomi och drift för att ta bort oanvända datakällor och tabeller eller implementera getEntityRecordIdsImpactedByTableChange för att optimera körtidsfrågorna."

Om det finns många datakällor som inte används för spårning i den faktiska livesynkroniseringen från appar för ekonomi och drift, finns det en möjlighet att enhetens prestanda kan påverka livesynkroniseringen. För att optimera de spårade tabellerna, använd metoden getEntityRecordIdsImpactedByTableChange.

## <a name="error-5000"></a>Fel 5000
Felmeddelandet är"Synkrona plugin-program har registrerats för datahanteringshändelser för enhetskonton. De kan påverka den initiala synkroniseringen och den live synkroniserade importprestandan till Dataverse. Du får bäst prestanda genom att ändra den till asynkron bearbetning. Lista över registrerade plugin-program {}."

Synkrona plugin-program på en Dataverse entitet kan påverka livesynkronisering och initial synkroniseringsprestanda när den ökar transaktionsbelastningen. Vi rekommenderar att du antingen stänger av den eller så gör du dessa synkroniserade om du har långsamma beläggningstider i den första synkroniseringen eller live-synkroniseringen för en viss enhet.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
