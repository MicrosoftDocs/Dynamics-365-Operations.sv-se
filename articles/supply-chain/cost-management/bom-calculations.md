---
title: BOM-beräkningar
description: Kostnadssummeringen och försäljningsprisberäkningarna kallas för strukturlisteberäkningar och du initierar dem från sidan Beräkningar. Det här ämnet innehåller information om BOM-beräknignar.
author: AndersGirke
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMCalcDialog, BOMCalcTable, CostingVersion, InventItemPrice, ProdSetupCostEstimation
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 273763
ms.assetid: c6fa3348-eafa-4847-9132-e65c5f55cbf4
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.dyn365.ops.version: AX 7.0.0
ms.search.validFrom: 2016-02-28
ms.openlocfilehash: a718a2e825630ccfaa54ff9dece1d3d19d59018c
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/10/2020
ms.locfileid: "3983950"
---
# <a name="bom-calculations"></a>BOM-beräkningar

[!include [banner](../includes/banner.md)]

Kostnadssummeringen och försäljningsprisberäkningarna kallas för strukturlisteberäkningar och du initierar dem från sidan Beräkningar. Det här ämnet innehåller information om BOM-beräknignar.

Kostnadssummeringen och försäljningsprisberäkningarna kallas för strukturlisteberäkningar och du initierar dem från sidan **Beräkningar**. Du använder sidan **Beräkningar** för att utföra följande uppgifter:

-   Beräkna en tillverkad artikels kostnad och generera en associerad artikelkostnadspost i en kostnadsversion.
-   Beräkna en tillverkad artikels försäljningspris och generera en associerad artikelprispost i en kostnadsversion.

Hur du använder sidan **beräkningar** varierar något beroende på hur du initierar strukturlisteberäkningarna. Användningen av **Beräkningar** beror också på om strukturlisteberäkningarna omfattar en kostnadsversion för standardkostnader eller planerade kostnader, och beror på flera principer som anges i den kostnadsversion som används i strukturlisteberäkningarna. **Obs!** En variant av av sidan **Beräkningar** används i kontexten för försäljningsorder, försäljningsofferter och serviceorderrader. Beräkningarna kallas orderspecifika strukturlisteberäkningar. En orderspecifik strukturlisteberäkning genererar inte någon artikelkostnadspost i en kostnadsversion. Däremot genererar en beräkningspost som visas på sidan **strukturberäkningsinformation**. Beräkningsposten omfattar en beräknad kostnad och ett beräknat försäljningspris. Sidan **beräkningar** kan öppnas för en enskild tillverkad artikel eller för en kostnadsversion:

-   Om du vill beräkna kostnader för en enskild tillverkad artikel initierar dux strukturlisteberäkningar från sidan **Artikelpris**. Sidan **beräkningar** ärver artikelidentifieraren. Du måste ange kostnadsredovisningsversion, strukturlisteversion, flödesversion, beräkningskvantitet, beräkningsdatum och site.
    -   Som standard anges strukturlisteversionen och flödesversionen till de aktiva versionerna för artikel, site, datum och beräkningskvantitet. Du kan dock åsidosätta standardvärden med godkända versioner.
    -   Beräkningskvantiteten anges som standard till artikelns standardorderkvantitet. Du kan emellertid åsidosätta standardvärdet.
    -   Beräkningsdatumet eller siten kan bestämmas via kostnadsversionen, eller tillåta användarangivna värden när datumet eller siten inte bestäms i kostnadsversionen. Ett framtida beräkningsdatum fastställer hur pågående kostnadsposter används. Strukturlisteberäkningar använder en väntande kostnadspost med det närmaste fråndatumet som infaller på eller före beräkningsdatumet.
-   Om du vill beräkna kostnader för alla tillverkade artiklar eller för valda artiklar, eller om du vill uppdatera artiklar utifrån var de används initierar du strukturlisteberäkningar från sidan **Inställningar för kostnadsredovisningsversion** eller sidan **Underhåll av kostnadsredovisningsversion**. Sidan **beräkningar** ärver kostnadsredovisningsversionen.
    -   För beräkningarna förutsätts att den aktiva strukturlisteversionen och flödesversionen används för en tillverkad artikel används (med tillhörande site, datum och kvantitet), såvida inte en tillverkad komponent har en angiven understrukturlista eller ett underflöde.
    -   För beräkningarna antas att standardorderkvantiteten används för tillverkade artiklar. Standardorderkvantiteten utgör underlaget för beräkning av komponentkvantiteter, för att fastställa relevanta strukturlisteversioner och flödesversioner (när du använder kvantitetskänsliga strukturlistor och flöden) och för att amortera konstanta kostnader. Antagandet gäller däremot inte när en tillverkad komponent har strukturlisteradtypen **Produktion** eller **Leverantör**, eller när du använder nedbrytningsläget för tillverkning på beställning för strukturlisteberäkningarna, eftersom kvantiteter återspeglar angiven beräkningskvantitet.
    -   Beräkningsdatumet eller siten kan bestämmas via kostnadsversionen, eller tillåta användarangivna värden när datumet eller siten inte bestäms i kostnadsversionen.

Andra varianter av strukturlisteberäkningarna återspeglar kostnadstypen och begränsningarna för kostnadsversionen.

-   Strukturlisteberäkningar med standardkostnader måste begränsas via kostnadsversionsprinciper, eftersom begränsningarna säkerställer standardkostnadsprinciperna. Standardkostnadsprinciper framtvingar begränsningar av användningen av standardkostnader för inköpta artiklar, en enskild nivå i nedbrytningsläget och inkluderingen av tillägg i enhetskostnader.
-   Strukturlisteberäkningar med planerade kostnader behöver å andra sidan inte följa standardkostnadsprinciper. Dessa strukturlisteberäkningar kan använda olika nedbrytningslägen, alternativa kostnadsdatakällor för inköpta artiklar och valfria tvingande begränsningar inom kostnadsversionen.

### <a name="bom-calculations-that-use-standard-costs"></a>Strukturlisteberäkningar med standardkostnader

Principer inom kostnadsversionen (för standardkostnader) kan bestämma att fem principer för strukturlisteberäkning måste användas. Alternativet **registreringsbegränsning** i kostnadsversionen bestämmer en av dessa principer, där tillägg måste inkluderas i enhetspriset. Tillägg för artiklar kan registreras manuellt, medan tillägg för tillverkade artiklar återspeglar den beräknade amorteringen för konstanta kostnader. Alternativet **beräkningsbegränsning** i kostnadsversionen bestämmer de övriga fyra principerna för strukturlisteberäkning.

-   Källan till den inköpta artikelns kostnadsbidrag måste baseras på standardkostnader. Det innebär att strukturlisteberäkningar måste använda artikelkostnadsposterna i angiven kostnadsversion, eller i reserven som innehåller standardkostnader.
-   Nedbrytningsläget måste vara en enda nivå, vilket ser till att beräkningen av standardkostnader blir korrekt och enhetlig.
-   För att garantera konsekventa resultat när försäljningspriset för artiklarna beräknas måste vinstinställningen bestämmas. Vinstinställningen kan endast användas och prisposter för artikelförsäljning kan endast skapas om kostnadsredovisningsversionen tillåter innehåll för försäljningspriser.
-   Reservprincipen måste bestämmas, där den kan anges som **Ingen**, **Aktiv** (för aktiva kostnader), eller **kostnadsversion** (för en angiven kostnadsversion).

### <a name="bom-calculations-that-use-planned-costs"></a>Strukturlisteberäkningar med planerade kostnader

Principer inom kostnadsversionen (för planerade kostnader) kan valfritt bestämma att fem principer för strukturlisteberäkning måste användas. Principerna kan bara ange standardvärden. Alternativet **registreringsbegränsning** i kostnadsversionen fastställer om strukturlisteberäkningsprincipen om tillägg ska bestämmas, eller fungera som standardvärde. Tillägg kan valfritt tas med i enhetspriset. Alternativet **beräkningsbegränsning** i kostnadsversionen fastställer om de andra fyra principerna för strukturlisteberäkning ska bestämmas eller fungera som standardvärden:

-   Källan till kostnadsbidragen för en inköpt artikel kan vara artikelkostnadsposterna i en kostnadsversion. Alternativt kan källan definieras av strukturlisteberäkningsgruppen som tilldelas artikeln. Strukturlisteberäkningsgruppen kan till exempel definiera handelsavtal för inköpspris som källa till kostnadsbidragsdata.
-   Nedbrytningsläget kan vara en enskild nivå, flera nivåer, tillverkas på beställning eller baseras på strukturlistans radartikel. Nedbrytningsläget för strukturlistans radtyp replikerar kostnadsberäkningslogiken för uppskattningar av tillverkningsorder.
-   Vinstinställningen kan vara bestämd eller ha ett standardvärde. Vinstinställningen kan endast användas och prisposter för artikelförsäljning kan endast skapas om kostnadsredovisningsversionen tillåter innehåll för försäljningspriser.
-   Reservprincipen kan vara bestämd eller ha ett standardvärde. Reservprincipen kan anges som **Ingen**, **Aktiv** (för aktiva kostnader), eller **kostnadsversion** (för en angiven kostnadsversion).

Strukturlisteberäkningar genererar en varningsmeddelanden och andra typer av meddelanden. Flera principer för strukturlisteberäkningarna bestämmer vilka typer av meddelanden som finns. Varningsvillkoren som har definierats för den grupp av strukturlisteberäkningar som artiklarna har tilldelats. Du kan åsidosätta dessa varningssituationer när du startar strukturlisteberäkningen. När reservprincipen används, är det ofta användbart att visa reservinformationen som informationsmeddelanden. När du försöker att uppdatera kostnader för artiklar med saknade kostnadsposter, är det också värdefullt om informationsmeddelanden kan identifiera artiklar som inte uppdaterades.

## <a name="bom-calculations-that-use-the-fallback-principle"></a>Strukturlisteberäkningar som använder reservprincipen
Följande situationer illustrerar hur reservprincipen kan används på två sätt:

-   **Uppdatera standardkostnader med hjälp av två versioner** - En kostnadsversion kan innehålla de stegvisa ändringarna av standardkostnaderna, till exempel väntande kostnadsposter som representerar nya artiklar eller kostnadsändringar. I den här situationen kan reservprincipen identifiera hur aktiva standardkostnader i de övriga kostnadsversionerna används.
-   **Simulera effekten av kostnadsändring med planerade kostnader** – en kostnadsversion för planerade kostnader kan innehålla stegvisa ändringar för simulering. Denna kostnadsversion innehåller väntande kostnadsposter som representerar de simulerade kostnadsändringarna för artiklar, kostnadskategorier och beräkningsformler för indirekta kostnader. I den här situationen kan reservprincipen identifiera hur aktiva standardkostnader i de övriga kostnadsversionerna används.

## <a name="bom-calculation-of-a-suggested-sales-price"></a>Strukturlisteberäkning av ett föreslaget försäljningspris
När du använder en metod för kostnad plus tillägg återspeglar artikelns beräknade försäljningspris de grupper med avkastningsprocent som anges i strukturlisteberäkningen och kostnaderna om associeras med dess komponentartiklar, flödesoperationer och tillämpbara tillverkningsomkostnader. Tillägget återspeglar avkastningsprocenten som tilldelas kostnadsgrupper och  kostnadsgrupperna som tilldelas artiklar, kostnadskategorier för flödesoperationer och beräkningsformlerna för indirekta kostnader för tillverkningsomkostnader. Grupperna med avkastningsprocent har etiketterna **standard**, **vinst 1**, **vinst 2**, och **vinst 3**. Inom uppsättningen vinst 1 kan till exempel en avkastningsprocent på 50 procent definieras för en kostnadsgrupp som tilldelas inköpt material och en avkastningsprocent på 80 kan definieras för en kostnadsgrupp som tilldelas kostnadskategorier för flödesoperationer. Sammanhanget för strukturlisteberäkningen bestämmer hur resultatet från ett beräknat försäljningspris hanteras.

-   **Strukturlisteberäkning för en artikel och angiven kostnadsversion** - Strukturlisteberäkningen genererar en väntande försäljningsprispost i kostnadsversionen. Försäljningsprisposten utgör startpunkten när du visar beräkningsdetaljer, (till exempel på sidan **Beräkna artikelkostnad**). Försäljningsprisposten fungerar främst som referensinformation, och ligger inte till grund för ett försäljningspris på försäljningsorder.
-   **Orderspecifik strukturlisteberäkning** - En variation på sidan **strukturlisteberäkning** som används när det gäller försäljningsorder, försäljningsofferter eller radartiklar på en serviceorder. En orderspecifik strukturlisteberäkning genererar ingen post i en kostnadsversion. Däremot genererar en beräkningspost som visas på sidan **strukturberäkningsresultat**. Beräkningsposten utgör startpunkten när du visar beräkningsdetaljer, (till exempel på sidan **Beräkna artikelkostnad**). Information om den valda beräkningsposten kan överföras till den ursprungliga radartikeln. Till exempel kan det beräknade försäljningspriset överföras till en radartikel på försäljningsordern.

## <a name="order-specific-bom-calculations"></a>Orderspecifika strukturlisteberäkningar
En orderspecifik strukturlisteberäkning är en variant på en strukturlisteberäkning för en tillverkad artikel. En orderspecifik strukturlisteberäkning utförs för försäljningsorder, försäljningsofferter och radartiklar på serviceorder. En orderspecifik strukturlisteberäkning genererar en beräkningspost som visas på sidan **resultat från strukturlisteberäkningar**. Beräkningsposten omfattar en beräknad vikt, en beräknad kostnad som baseras på aktiva kostnadsposter och ett beräknat försäljningspris. Beräkningsposten som varje orderspecifik strukturlisteberäkning för en artikel genererar på sidan **Resultat från strukturlisteberäkningar** identifieras unikt med ett beräkningsnummer. Resultatet från en beräkningspost kan överföras till den ursprungliga radartikeln. En orderspecifik strukturlisteberäkning skiljer sig från en strukturlisteberäkning för en tillverkad artikel på två sätt.

-   En orderspecifik strukturlisteberäkning genererar inte någon artikelkostnadspost i en kostnadsversion. Det innebär därför att strukturlisteberäkningsprinciperna inte gäller när en artikelkostnadspost skapas eller när en kostnadspost skrivs över.
-   En orderspecifik strukturlisteberäkning alltid de aktiva kostnadsposterna för komponenter, kostnadskategorier och beräkningsformler för indirekta kostnader.





