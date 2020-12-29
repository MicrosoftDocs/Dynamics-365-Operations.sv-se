---
title: Information som används i strukturlisteberäkningar med standardkostnader
description: I strukturlisteberäkningar används data från flera källor för att beräkna standardkostnaderna för en tillverkad artikel. Källorna kan till exempel vara information om artiklar, flöden, beräkningsformler för indirekta kostnader och kostnadsversionen.
author: AndersGirke
manager: tfehr
ms.date: 10/25/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMCalcDialog, BOMCalcGroup, BOMCalcTable, ProdParmBOMCalc
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 65571
ms.assetid: ca17e6dd-b16a-4bbc-8682-b16345ab9906
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bbc7e4105d085e2af0e8e6e574244f5083d08c15
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437646"
---
# <a name="information-used-in-bom-calculations-with-standard-costs"></a>Information som används i strukturlisteberäkningar med standardkostnader

[!include [banner](../includes/banner.md)]

I strukturlisteberäkningar används data från flera källor för att beräkna standardkostnaderna för en tillverkad artikel. Källorna kan till exempel vara information om artiklar, flöden, beräkningsformler för indirekta kostnader och kostnadsversionen.

Bland annat kan följande information om inköpta artiklar användas i standardkostnadens strukturlisteberäkning:
-   Kostnad – En inköpt artikels kostnader underhålls som sitespecifika kostnadsposter i en kostnadsversion för standardkostnader. Varje kostnadspost har ett giltighetsdatum, och strukturlisteberäkningens datum bestämmer vilken kostnadspost som ska användas. Till exempel en strukturlisteberäkning med ett framtida beräkningsdatum kan använda en kostnadspost med väntande status och ett framtida giltighetsdatum.
-   Kostnadsgrupp – Kostnadsgruppen som tilldelas en inköpt artikel utgör underlaget för kostnadssegmenteringen i de beräknade kostnaderna för en tillverkad artikel.
-   Varningsvillkor som bäddas in i artikelns strukturlisteberäkningsgrupp aktiverar strukturlisteberäkningen för att identifiera potentiella problem. Detta kan vara när en inköpt artikel har noll kostnad, en kvantitet i en strukturlista eller en inaktuell kostnadspost. Varningsvillkoren kan åsidosättas när en strukturlisteberäkning initieras.

Bland annat kan följande information om tillverkade artiklar användas i standardkostnadens strukturlisteberäkning:
-   Standardorderkvantitet för lager – Artikelns standardorderkvantitet (för lager) fungerar som standardredovisningspartistorlek för amortering av konstanta kostnader i en strukturlisteberäkning. Redovisningspartistorleken återspeglar också orderkvantitetens multipel om en sådan anges.
-   Varningsvillkor som bäddas in i artikelns strukturlisteberäkningsgrupp aktiverar strukturlisteberäkningen för att identifiera potentiella problem. Ett exempel kan vara att den tillverkade artikeln inte har någon strukturlista eller ett flöde. Varningsvillkoren kan åsidosättas när en strukturlisteberäkning initieras.

Bland annat kan följande information om strukturlistan användas i standardkostnadens strukturlisteberäkning:
-   Strukturlisteversion – Strukturlisteversionen som tilldelas den tillverkade artikeln har från- och till-datum för giltighetstiden samt statusvärdena godkänd och aktiv. Versionen kan gälla för hela företaget eller vara sitespecifik, och den kan också återspegla brytpunkter för kvantitet.
-   Strukturlistans radartikelkvantitet – En komponent har vanligtvis ett variabelt kvantitetsbehov, men det kan vara konstant. Komponentens kvantitet uttrycks vanligtvis för produktion av en överordnad artikel, men kan uttryckas per 100 eller per 1 000 när decimaler måste anges mer exakt. Komponentens kvantitet kan också beräknas baserat på mått.
-   Strukturlistans radartikelkassation – En komponent kan ha en variabel eller konstant kvantitet för planerad kassation.
-   Strukturlistans giltighetsdatum för radartiklar – En komponent kan ha från- och till-datum för giltighetstid.
-   Produktionstyp för strukturlistans radartikel – Kostnadspartistorleken för amortering av konstanta kostnader återspeglar strukturlisteberäkningskvantiteten och nedbrytningsläget tillverkning på beställning, eftersom strukturlisteberäkningen förutsätter att den tillverkade komponenten ska tillverkas i den exakta kvantiteten istället för dess standardorderkvantitet.
-   Understrukturlista för en tillverkad komponent – En tillverkad komponent kan eventuellt ha en angiven strukturlisteversion, som används i stället för artikelns aktuella aktiva strukturlisteversion i en strukturlisteberäkning.
-   Delflöde för en tillverkad komponent – En tillverkad komponent kan eventuellt ha en angiven flödesversion, som används i stället för artikelns aktuella aktiva flödesversion i en strukturlisteberäkning.
-   Operationsnummer och inverkan från operationskassationsprocent – Operationsnumret är en komponent för en specifik operation, och operationer kan ha en kassationsprocent. Länkningen gör det möjligt för strukturlisteberäkningen att ta hänsyn till kassationsprocent och ackumulerade kassationsprocent (över flera operationer) när det gäller den kvantitet som behövs av komponenten.
-   Ignorera strukturlisteradartiklar i kostnadsberäkningar – En komponent kan ignoreras vid strukturlisteberäkningar.

Operationens resursinformation som används i standardkostnadens strukturlisteberäkning:
-   Timkostnader – De timkostnader som associeras med en operations resurs uttrycks i kostnadskategorier som tilldelas ställtid och körtid. Dessa kostnadskategorier kan identifieras för resursgrupper och operationsresurser. Timkostnaderna som associeras med en kostnadskategori kan gälla för hela företaget eller en viss site.
-   Kostnader per enhet – I vissa tillverkningsmiljöer tilldelas operationsresurskostnader per utleveransenhet, som uttrycks som en annan kostnadskategori för kvantitet. Kvantitetsrelaterade kostnader kan till exempel återspegla ackord för arbete, eller så kan en färgtillverkare tilldela operationsresurskostnader per liter utleverans.
-   Åsidosättning av operationsresursinformation i flödesoperationer – Resursinformation om kostnadskategorier ärvs av operationer, där den kan åsidosättas. Strukturlisteberäkningar använder kostnadskategoriinformationen som anges i flödesoperationer.
-   Kostnadsgrupp för en kostnadskategori – Kostnadsgruppen som tilldelas en kostnadskategori tillhandahåller kostnadssegmentering i de beräknade kostnaderna för en tillverkad artikel. Olika kostnadsgrupper kan till exempel användas för att segmentera de beräknade kostnaderna som associeras med maskiner och arbetskraft eller med ställ- och körtid.

Bland annat används följande flödesinformation i standardkostnadens strukturlisteberäkning:
-   Flödesversion – Flödesversionen som tilldelas den tillverkade artikeln har från- och till-datum för giltighetstiden samt statusvärdena godkänd och aktiv. Flödesversionen måste vara sitespecifik, och den kan också återspegla brytpunkter för kvantitet.
-   Flödesoperationstid – Tiden kan anges för kör- eller ställtid. Timtiden uttrycks vanligtvis för produktion av en överordnad artikel, men kan uttryckas per 100 eller per 1 000 när decimaler måste anges mer exakt.
-   Flödesoperationstid för sekundära resurser – En sekundär resurs har samma operationsnummer som den primära resursen, och har samma flödesoperationstid. En operation kanske till exempel kräver en maskin som primär resurs och arbete och verktyg som sekundära resurser.
-   Kassationsprocent för flödesoperation - Länkningen gör det möjligt för strukturlisteberäkningen att ta hänsyn till kassationsprocent och ackumulerade kassationsprocent (över flera operationer) när det gäller den kvantitet som behövs av komponenten. Detta gäller den tid som krävs för flödesoperationer och erforderlig kvantitet för komponenter som är länkade till operationsnummer.
-   Kostnadskategorier för en flödesoperation – Operationsresursinformationen om kostnadskategorier ärvs av operationer, där den kan åsidosättas. Strukturlisteberäkningar använder kostnadskategoriinformationen som anges i flödesoperationer.

Bland annat används följande information om tillverkningsomkostnader i standardkostnadens strukturlisteberäkning:
-   Tillägg – En tilläggsberäkningsformel återspeglar ett procentvärde, till exempel 100 procent, som knyts till en viss kostnadsgrupp, till exempel arbete.
-   Tariff – En tariffberäkningsformel återspeglar ett belopp per enhet, till exempel 100 kronor per timme, som knyts till en viss kostnadsgrupp, till exempel arbete.
-   Tidsbaserad kontra materialbaserad omkostnad – Tillverkningsomkostnaden kan knytas till flödesoperationer eller materialkomponenter.

Bland annat används följande kostnadsversionsinformation i standardkostnadens strukturlisteberäkning:
-   Kostnadstyp – Kostnadsversionen måste innehålla standardkostnader. Flera restriktioner gäller för strukturlisteberäkningar som använder standardkostnader. Dessa restriktioner kan till exempel ange att tillägg måste inkluderas i enhetskostnaderna och att strukturlisteberäkningens nedbrytningsläge måste ha en enda nivå.
-   Bestämd reservprincip – Kostnadsversionen kan bestämma att en reservprincip ska användas, till exempel att en angiven kostnadsversion eller de aktiva kostnadsposterna ska användas. Den bestämda reservprincipen gäller vanligtvis för en kostnadsversion som representerar de stegvisa uppdateringarna när två versioner används vid kostnadsuppdateringar.
-   Spärrflagga för pågående kostnader – En spärrflagga kan förhindra strukturlisteberäkningar av pågående kostnader för tillverkade artiklar.
-   Angivet från-datum – Det angivna från-datumet fungerar som standardberäkningsdatum för alla strukturlisteberäkningar som involverar kostnadsversionen.
-   Angiven site – En angiven site begränsar strukturlisteberäkningar till den enskilda siten.
-   Innehållet i kostnadsversionen måste omfatta kostnader – Innehållet måste omfatta kostnader. Det kan dessutom valfritt omfatta försäljningspriser så att föreslagna försäljningspriser kan beräknas för tillverkade artiklar.

När du initierar en strukturlisteberäkning kan du ange flera informationskällor. Det kan till exempel vara siten, beräkningsdatumet och kostnadsversionen.





