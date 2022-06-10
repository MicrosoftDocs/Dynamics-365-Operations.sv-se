---
title: Bokföring av indirekt kostnad
description: I det här avsnittet beskrivs hur du bokför indirekta kostnader, skapar kostnadsgrupper och lägger till noder i kostnadsredovisningen för indirekta kostnader.
author: rachelprofitt
ms.date: 04/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: CostSheetDesigner, BOMCostGroup, ProjCategory, CostingVersion, CostSheetCalculationFactor
audience: Application User
ms.search.region: Global
ms.author: raprofit
ms.openlocfilehash: d7f4753f69d83d172993e1c9b04be2220fdf253f
ms.sourcegitcommit: 1ea145dc606e243c7f51d91a5c0dd9e385bbda4a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/25/2022
ms.locfileid: "8804631"
---
# <a name="indirect-cost-posting"></a>Bokföring av indirekt kostnad

Indirekta kostnader är kostnader som inte är direkt relaterade till någon enstaka aktivitet i produktionsprocessen. Administrativa kostnader kan till exempel vara medarbetarlöner, avdelningskostnader för redovisning och omkostnader som hyra, el och maskiner.

## <a name="calculating-indirect-costs"></a>Beräkna indirekta kostnader

Microsoft Dynamics 365 Finance har inte ett automatiskt sätt att beräkna momssatsen för indirekta kostnader. Du måste bestämma dina indirekta kostnader, skapa indirekta kostnadskoder och underhålla kursen för varje indirekt kostnad i kostnadsredovisningen.

Den exakta process som används för att beräkna indirekta kostnader kan variera något från företag till företag. I allmänhet består processen dock av följande grundläggande steg:

1. Skapa en lista över indirekta kostnader som ska kännas igen i produktionen. Den här listan kan omfatta hyra, administrativa kostnader, redovisningsavgifter och juridiska avgifter. Det ska inte innefatta råmaterialkostnader eller arbetskostnader som har avsänds i produktionsflöden.
2. Summera alla indirekta kostnader. Du kan gruppera liknande typer av indirekta kostnader eller hålla dem åtskilda. Varje indirekt kostnad som konfigureras kan ha olika huvudkonton som används för bokföring i redovisningen.
3. Jämför de indirekta kostnaderna med en faktor, som också kallas för absorptionsbas. Faktorn kan vara vad du än väljer. Nedan följer några vanliga exempel:

    - Intäkter
    - Total kvantitet som tillverkas
    - Ställtid
    - Körtid

    Du kan välja den period du vill beräkna dina indirekta kostnader för, till exempel månad, kvartal eller år. Summan av dina indirekta kostnader och summan av din faktor ska vara för samma tid. Följande formel används för att beräkna den indirekta kostnadssatsen:

    *Indirekt kostnadssats* = *Total indirekt kostnadskostnad* &divide; *totalfaktor*

4. Skapa indirekta kostnadsgrupper.
5. Konfigurera kostnadsredovisningen med dina satser.
6. Underhåll kostnaden för dina indirekta kostnader i kostnadsversionen.

> [!NOTE]
> Du kan använda modulen **Kostnadsredovisning** för att ackumulera kostnader och fastställa omkostnader från olika källor, till exempel produktion, projekt och redovisningen. Mer information finns i [Kostnadsredovisning](/cost-accounting/cost-accounting-home-page.md).

> [!IMPORTANT]
> Olika myndighetsregleringar har publicerat riktlinjer om vilka typer av kostnader som kan inkluderas som indirekta kostnader eller omkostnader i kostnaden för dina färdiga varor. Innan du börjar konfigurera indirekta kostnader rekommenderar vi att du kontrollerar med din revisor och lokala regler för att säkerställa att du är kompatibel.

## <a name="create-cost-groups-for-indirect-costs"></a>Skapa kostnadsgrupper för indirekta kostnader

Du måste skapa minst en kostnadsgrupp som du kan använda för indirekta kostnader. Det finns ingen gräns för hur många kostnadsgrupper du kan använda. Tänk på hur du beräknar kostnaderna och om det finns olika satser för olika typer av kostnader. Organisationen tillverkar till exempel livsmedel. Vissa råmaterial och färdiga varor är torkvaror och har en indirekt kostnad för lagring. Andra råmaterial och färdiga varor härfördes och har en högre indirekt kostnad. I det här fallet kanske du vill skapa två kostnadsgrupper: **Torrt material ovanför** och **Kylt material över huvudet**.

Följ de här stegen om du vill skapa en kostnadsgrupp för indirekta kostnader.

1. Gå till **Produktionskontroll &gt; Inställningar &gt; Rutter &gt; Kostnadsgrupper**.
2. Klicka på **Nytt** för att skapa en grupp.
3. I fältet **Kostnadsgrupp** anger du ett unikt namn för kostnadsgruppen, t.ex.**MATOVH**.
4. I fältet **Namn** anger du en beskrivning för kostnadsgruppen, t.ex.**Materialomkostnad**.
5. I fältet **Typ av kostnadsgrupp** välj **Indirekt**.
6. Valfritt: I fältet **Beteende** väljer du **Fast kostnad** eller **Variabel kostnad**.

## <a name="configure-the-costing-sheet-for-indirect-costs"></a>Konfigurera kostnadsredovisningen för indirekta kostnader

När du har skapat en eller flera kostnadsgrupper kan du konfigurera kostnadsredovisningen med indirekta kostnader och definiera beräkningen. Du kanske vill gruppera indirekta kostnader i kostnadsredovisningen. Om du vill gruppera indirekta kostnader kan du skapa ett valfritt huvud i kostnadsredovisningen. Du måste skapa minst en nod för varje kostnadsgrupp i kostnadsredovisningen. För varje kostnadsgrupp för indirekta kostnader kan du lägga till ytterligare en indirekt kostnadsberäkning.

### <a name="indirect-cost-node-types"></a>Nodtyper för indirekta kostnader

Det här avsnittet beskriver de olika typerna av noder för indirekta kostnader.

#### <a name="surcharge"></a>Tillägg

**Tillägg** är en av de vanligaste typerna av indirekta kostnader. Det beräknar en procentsats av kostnaden från absorptionsunderlaget för kostnader på tillverkningsordern. Du definierar absorptionsunderlaget genom att välja kostnadsgrupperna som är kopplade till ditt material eller dina tidskomponenter i kostnadsredovisningen.

Ett 3-procents tillägg kan till exempel läggas till produktionskostnaden för alla råmaterial på en tillverkningsorder.

#### <a name="rate"></a>Omkostnad

En indirekt kostnad av typen **Avgift** används för att lägga till en fast kostnadsbelopp till tillverkningsordern från en absorptionsbas för kostnader på tillverkningsordern. Avgiften kan baseras på en av tre undertyper:

- **Process** – Avgiften baseras på körtiden i flödet.
- **Inställning** – Avgiften baseras på inställningstiden i flödet.
- **Kvantitet** – Avgiften baseras på den kvantitet som tillverkas.

Du definierar absorptionsunderlaget genom att välja kostnadsgrupperna som är kopplade till ditt material eller dina tidskomponenter i kostnadsredovisningen.

Till exempel läggs ett fast belopp på 2,00 USD till varje tillverkningsorder, baserat på körtiden i flödet för arbetskostnadsgruppen i kostnadsredovisningen.

#### <a name="output-unit-based"></a>Utdataenhetsbaserad

En indirekt kostnad för typen **Utdataenhetsbaserad** beräknas genom att multiplicera det belopp som anges på snabbfliken **Avgift** av kostnadsredovisningsblad efter den valda undertypen. Du kan välja kvantitet, vikt eller volym för den färdiga varan som multiplikator för den indirekta kostnaden.

Du kan till exempel använda kvantiteten för 1,50 USD beräkna avskrivningsregler för varje kvantiteten som tillverkas. Som ett annat exempel använder du volymen för att beräkna 2,00 USD i kylkostnader för volymen utrymme som de färdiga varorna tar i dina kylenheter.

#### <a name="input-unit-based"></a>Indataenhetsbaserad

En indirekt kostnad för typen **Indataenhetsbaserad** beräknas genom att den mängd råmaterial som förbrukas på en tillverkningsorder multipliceras med ett belopp. Du kan använda vikten eller volymen för indata på tillverkningsordern för att beräkna summan. Du kan begränsa beräkningen till en delmängd av material genom att välja en eller flera kostnadsgrupper på snabbfliken **Absorptionsbas** i kostnadsredovisningen.

Du kan till exempel använda volymen av indata för en viss kostnadsgrupp som är kopplad till förbundna produkter för att lägga 1,00 USD till tillverkningsordern.

### <a name="create-a-total-node-for-indirect-costs-in-the-costing-sheet"></a>Skapa en totalnod för indirekta kostnader i kostnadsredovisningen

Följ de här stegen om du vill skapa en totalnod för indirekta kostnader i kostnadsredovisningen.

1. Gå till **Kostnadshantering &gt; Ställ in policyer för indirekt kostnadsredovisning &gt; Kostnadsredovisning**.
2. I trädet väljer du en nod som representerar kostnaden för varor som har tillverkats.
3. Klicka på **Nytt** för att skapa en nod.
4. I fältet **Välj nodtyp**, välj **Totalt**.
5. I fältet **Kod**, ange till ett unikt ID för noden, t.ex. **Produktionsomkostnader**.
6. Markera kryssrutan **rubrik**.
7. Markera kryssrutan **Totalt**.
8. Välj **OK**.

### <a name="create-an-indirect-cost-group-node-in-the-costing-sheet"></a>Skapa en indirekt kostnadsgruppsnod i kostnadsredovisningsblad

Följ dessa steg för att skapa en indirekt kostnadsgruppsnod i kostnadsredovisningsblad.

1. Gå till **Kostnadshantering &gt; Ställ in policyer för indirekt kostnadsredovisning &gt; Kostnadsredovisning**.
2. Markera i trädet den nod som du vill skapa den indirekta kostnaden under. Välj till exempel totalnoden för **Produktionsomkostnader**.
3. Klicka på **Nytt** för att skapa en nod.
4. I fältet **Välj nodtyper** välj **Kostnadsgrupp**.
5. I fältet **Kod**, ange till ett unikt ID för noden, t.ex. **TRANSP**.
6. I fältet **Beskrivning** anger du en kort beskrivning såsom **Transportomkostnad**.
7. Välj **OK**.
8. I fältet **kostnadsgrupp**, välj kostnadsgrupp, t.ex. **OVH1: Transportomkostnad**.

### <a name="create-a-surcharge-indirect-cost"></a>Skapa en indirekt kostnad för tilläggsavgift

Följ dessa steg för att skapa en indirekt kostnad för tilläggsavgift på ditt kostnadsredovisningsblad.

1. Gå till **Kostnadshantering &gt; Ställ in policyer för indirekt kostnadsredovisning &gt; Kostnadsredovisning**.
2. Markera i trädet den nod för ndirekt kostnadsgrupp som du vill skapa den indirekta kostnaden under. Välj till exempel totalnoden för **TRANSP - Transportomkostnad**.
3. Klicka på **Nytt** för att skapa en nod.
4. I fältet **Välj nodtyp**, välj **Tilläggsavgift**.
5. I fältet **Kod**, ange till ett unikt ID för noden, t.ex. **Transporttillägg**.
6. Välj **OK**.
7. I fältet **Deltyp**, välj **Total**.
8. På snabbfliken **Absorptionsbas**, klicka på **Ny** för att skapa en kostnadskod.
9. I fältet **Kod**, välj en kostnadsgrupp att använda för att beräkna tilläggsavgiften.
10. Valfritt: Upprepa steg 8 till 9 för varje ytterligare kostnadsgrupp som du vill använda i beräkningen.
11. På snabbfliken **Tilläggsavgift**, klicka på **Ny** för att skapa en ny avgift.
12. I fältet **Version**, välj den kostnadsversion som tilläggsavgiften ska läggas till.
13. Valfritt: I fältet **webbplats**, gå in på en webbplats för att tillämpa tilläggsavgiften.
14. I fältet **Procent** anger du den procentandel som ska beräknas på produktionsorder från kostnadsgrupperna som är definierade i snabbfliken **Absorptionsbas**.
15. På snabbfliken **Redovisningsbokföring** välj huvudkontot att använda för fälten **Beräknad indirekt kostnad som förbrukats**, **Beräknad kostnad för indirekt kostnad som förbrukats, PIA**, **Indirekt kostnad som förbrukats** och **Kostnader för indirekt kostnad som förbrukats, PIA**.
16. Valfritt: På snabbfliken **Ekonomiska dimensioner**, ange eventuella finansiella dimensioner som ska anges som standard på transaktioner när de bokförs till huvudboken.

Föregående procedur visar hur du skapar en indirekt kostnad av typen **Tilläggsavgift**. Liknande steg används för att skapa andra typer av indirekta kostnader. I följande avsnitt beskrivs skillnaderna för varje typ.

#### <a name="rate"></a>Omkostnad

- I steg 4 väljer du **Avgift** i stället **Tilläggsavgift**.
- I steg 7 väljer du **Bearbeta**, **Inställningar** eller **Kvantitet** istället för **Total**.
- I steg 11 använder du snabbfliken **Avgift** i stället för **Tilläggsavgift**.
- I steg 14 anger du ett belopp i fältet **Belopp** i stället för en procentsats i fältet **Procent**.

#### <a name="output-unit-based"></a>Utdataenhetsbaserad

- I steg 4 väljer du **Utdataenhetsbaserad** i stället för **Tilläggsavgift**.
- I steg 7 väljer du **Kvantitet**, **Vikt** eller **Volym** istället för **Total**.
- Hoppa över steg 8 till och med 10.
- I steg 11 använder du snabbfliken **Avgift** i stället för **Tilläggsavgift**.

#### <a name="input-unit-based"></a>Indataenhetsbaserad

- I steg 4 väljer du **Indataenhetsbaserad** i stället för **Tilläggsavgift**.
- I steg 7 väljer du **Vikt** eller **Volym** istället för **Total**.
- I steg 11 använder du snabbfliken **Avgift** i stället för **Tilläggsavgift**.
