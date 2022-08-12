---
title: Buffertprofil och nivåer
description: Den här artikeln innehåller information om buffertprofiler och nivåer, vilka bestämmer minimi- och maximilagernivåer som ska innehållas för respektive avdelningspunkt.
author: t-benebo
ms.date: 06/30/2022
ms.topic: article
ms.search.form: EcoResProductDetailsExtended, ReqItemDecoupledLeadTime
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-06-30
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: dd72332abefd31fd391ff66931a5abae0efb08de
ms.sourcegitcommit: 529fc10074b06f4c4dc52f2b4dc1f159c36e8dbc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/22/2022
ms.locfileid: "9186700"
---
# <a name="buffer-profile-and-levels"></a>Buffertprofil och nivåer

[!include [banner](../../includes/banner.md)]
[!INCLUDE [preview-banner](../../includes/preview-banner.md)]

När du har identifierat dina avdelningspunkter (nyckelartiklar som du ska behålla i lager) måste du bestämma hur mycket lager (buffert) du vill ha för var och en av dem. Den här uppgiften är det andra steget i efterfrågestyrd resursplanering (Demand Driven Materials Resource Planning, DDMRP).

## <a name="buffer-levels-and-zones"></a>Buffertnivåer och zoner

I DDMRP definieras varje lagerbuffert med hjälp av tre värden: minimikvantitet, maximikvantitet och beställningspunkt. Dessa värden upprättar tre differenszoner som identifieras med följande färgkoder:

- **Röd zon** – Området under minimikvantiteten. Minimikvantiteten kallas också för "röd topp" och din planeringsstrategi bör ha utformats för att se till att lagernivåerna alltid ligger över denna punkt.
- **Gul zon** – Området mellan minimikvantiteten och beställningspunkten. Beställningspunkten kallas också för "gul topp". När den här punkten har nåtts bör systemet beställa om.
- **Grön zon** – Området mellan beställningspunkten och maximikvantiteten. Den maximala kvantiteten kalla även för "grön topp". Denna punkt är den maximinivå som lagret fylls på till.

I följande bild visas de tre färgzonerna och hur de relaterar till minimikvantitet, maximikvantitet och beställningspunkt.

![DDMRP-buffertzoner och nivåer.](media/ddmrp-buffer-levels.png "DDMRP-buffertzoner och nivåer")

## <a name="calculating-the-buffer-zones"></a>Beräkna buffertzoner

Det här avsnittet beskriver hur höjden för respektive buffertzon beräknas.

Den gula zonen beräknas vanligtvis först. Denna zon representerar den kvantitet som du förbrukar från det att du beställer tills det att ordern anländer. Detta är alltså den förväntade förbrukningen under ledtiden för påfyllnad. Den beräknas med följande formel:

- **Gul zon** = *Genomsnittlig daglig användning (ADU)* × *Avdelad ledtid*

Den *avdelade ledtiden* representerar den tid som krävs för att framställa eller ta emot en artikel om avdelningspunkterna alltid finns i lager. Den är vanligtvis mycket kortare än den *ackumulerade ledtiden* som vanligtvis används i huvudplaneringen. Korrekta buffertinställningar är nyckeln till att se till att avdelningspunkter alltid finns i lager men inte är överfyllda.

Den röda zonen beräknas med följande formel:

- **Röd bas** = *ADU* × *Avdelad ledtid* × *Ledtidsfaktor*
- **Röd säkerhet** = *Röd bas* × *Variantfaktor*
- **Röd zon** = *Röd bas* + *Röd säkerhet*

Den gröna zonen beräknas som maximiresultat av följande tre formler:

- *Minsta orderkvantitet*
- *ADU* × *Ordercykel*
- *ADU* × *Avdelad ledtid* × *Ledtidsfaktor*

## <a name="calculating-average-daily-usage"></a>Beräkna genomsnittlig daglig användning

Systemet använder ett av tre sätt att beräkna hur mycket du förbrukar per dag:

- **Genomsnittlig daglig användning (tidigare)** – Detta sätt baseras på faktisk tidigare förbrukning.
- **Genomsnittlig daglig användning (kommande)** – Detta sätt baseras på prognostiserad framtida förbrukning.
- **Genomsnittlig daglig användning (blandad)** – Denna metod baseras på en viktad blandning av tidigare och prognostiserad förbrukning.

### <a name="average-daily-usage-past"></a>Genomsnittlig daglig användning (tidigare)

Tidigare ADU beräknas som ett medelvärde genom att addera de kvantiteter som används varje dag under ett angivet antal dagar och sedan dividera summan med antalet dagar. I följande illustration visas hur det här arbetssättet fungerar när en beräkning görs av de tre föregående dagarna.

![Diagram över genomsnittlig daglig användning (tidigare).](media/ddmrp-adu-past.png "Diagram över genomsnittlig daglig användning (tidigare)")

I illustrationen ovan är – om "idag" är morgonen den 11 juni – ADU för de föregående tre dagarna (8, 9 och 10 juni) lika med 21.

- **ADU (tidigare)** = (29 + 11 + 23) ÷ 3 = 21

### <a name="average-daily-usage-forward"></a>Genomsnittlig daglig användning (kommande)

För en ny produkt kanske du inte har några tidigare användardata. Därför kan du istället använda projekterat ADU hädanefter (till exempel baserat på prognostiserad efterfrågan). I följande illustration visas hur det här arbetssättet fungerar när en beräkning görs sett över tre dagar in i framtiden (inklusive "idag").

![Diagram över genomsnittlig daglig användning (kommande).](media/ddmrp-adu-forward.png "Diagram över genomsnittlig daglig användning (kommande)")

I föregående illustration är – om "idag" är lika med morgonen den 11 juni – ADU för de nästkommande tre dagarna (11, 12 och 13 juni) lika med 21,66.

- **ADU (kommande)** = (18 + 18 + 29) ÷ 3 = 21,66

### <a name="average-daily-usage-blended"></a>Beräkna genomsnittlig daglig användning (blandad)

Blandad ADU kombinerar medelvärdet av tidigare användning och genomsnittlig kommande användning enligt illustrationen nedan.

![Diagram för genomsnittlig daglig användning (blandad).](media/ddmrp-adu-blended.png "Diagram för genomsnittlig daglig användning (blandad)")

I föregående illustration är – om "idag" är morgonen den 11 juni – blandad ADU för de föregående och nästkommande tre dagarna (8 till 13 juni) lika med 12.33.

- **ADU blandad =** (*ADU tidigare* + *ADU kommande*) ÷ 2<br>= (21 + 21,66) ÷ 2<br>= 21,33

## <a name="buffer-calculation-factors"></a>Beräkningsfaktorer för buffert

För varje artikel kan du definiera två faktorer när du vill justera hur stora de röda och gröna zonerna ska vara. På det här sättet kan du kompensera för förväntad ledtid och efterfrågevariation.

![Faktorer för ledtid och variation.](media/ddmrp-zone-factors.png "Faktorer för ledtid och variation")

Den första faktorn är *ledtidsfaktorn*. Värdet är ett decimalvärde från 0 till 1. Ju längre ledtiden är, desto lägre ska vara värdet vara. Demand Driven Institute rekommenderar följande intervall:

- **Lång ledtid:** 0,20–0,40
- **Medellång ledtid:** 0,41 –0,60
- **Kort ledtid:** 0,61 –1,00

Den andra faktorn är *variationsfaktorn*. Värdet är ett decimalvärde från 0 till 1. Ju högre efterfrågevariation, desto lägre ska vara värdet vara. Demand Driven Institute rekommenderar följande intervall:

- **Låg variation:** 0,20 –0,40
- **Medelvariation:** 0,41 –0,60
- **Hög variation:** 0,61 –1,00

## <a name="buffer-calculation-examples"></a>Beräkningsexempel för buffert

Det här exemplet fortsätter det exempel på kuddproduktion som tillhandahålls i [Lagerplacering](ddmrp-inventory-positioning.md). I detta exempel valde du avdelningspunkter som minskade ledtiden från 21 dagar till fem dagar, enligt illustrationen nedan.

![Exempel på avdelad ledtid.](media/ddmrp-bom-decoupled-lead-time-example.png "Exempel på avdelad ledtid")

För det här exemplet ska du utgå från att ADU har beräknats som 23 enheter samt att – enligt illustrationen – den avdelade ledtiden är fem dagar. Med hjälp av dessa värden kan du beräkna den gula zonen med följande formel:

- **Gul zon** = *ADU* × *Avdelad ledtid* = 115

![Exempel på beräkning av gul zon.](media/ddmrp-example-calc-yellow.png "Exempel på beräkning av gul zon")

Beräkningen av den röda zonen liknar beräkningen av den gula zonen, men med marginal för varianter och ledtid. För det här exemplet ska du utgå från att du har observerat en medellång ledtid (faktor = 0,50) och höga variationer i efterfrågan (faktor = 0,8). Genom att använda dessa värden tillsammans med komponenterna från formeln för den gula zonen kan du beräkna den röda zonen med följande formler:

- **Röd bas** = *ADU* × *Avdelad ledtid* × *Ledtidsfaktor* = 57,5
- **Röd säkerhet** = *Röd bas* × *Variantfaktor* = 46
- **Röd zon** = *Röd bas* + *Röd säkerhet* = 103,5

Systemet rundar av den röda zonen till 104 enheter (ea) eftersom enheter räknas i heltal.

![Exempel på beräkning av röd zon.](media/ddmrp-example-calc-red.png "Exempel på beräkning av röd zon")

Beräkningen av den gröna zonen innehåller även komponenterna från den gula zon-formeln, men den medger en minsta orderstorlek, ordercykel och ledtidsfaktor. För det här exemplet ska du utgå från att det inte finns någon ordercykel (därför har du heller inte några tidsbegränsningar för hur ofta du beställer) och att minimiorderkvantiteten är 10 enheter. Den gröna zonen beräknas sedan som maximiresultat av följande tre formler:

- *Minsta orderkvantitet* = 10
- *ADU* × *Ordercykel* = 0
- *ADU* × *Avdelad ledtid* × *Ledtidsfaktor* = 57,5

Systemet rundar av den gröna zonen till 58 enheter (ea) eftersom enheter räknas i heltal.

![Exempel på beräkning av grön zon.](media/ddmrp-example-calc-green.png "Exempel på beräkning av grön zon")

I följande illustration sammanfattas dessa zonberäkningsresultat genom att använda den trattgrafik som ofta används i DDMRP.

![Summering av zonberäkningsresultat.](media/ddmrp-example-calc-summary.png "Summering av zonberäkningsresultat")

## <a name="dynamic-adjustments"></a><a name="dynamic-adjustments"></a>Dynamiska justeringar

Med dynamiska justeringar kan du tillämpa en *efterfrågejusteringsfaktor* under perioder med hög eller låg efterfrågan. Denna faktor multiplicerar ADU i alla beräkningar för den valda perioden. Buffertzonerna ändras sedan i sin tur. Vanligtvis gäller den här faktorn när du har genererat de ursprungliga buffertvärdena, detta så att du kan finjustera dem över tid och som svar på ändrade villkor. Den här uppgiften är det tredje steget i DDMRP.

Det kan till exempel vara större efterfrågan på en kuddprodukt i augusti när folk åker på semester. Därför förväntas försäljningen öka. I det här fallet kan du ändra värdet för **Justeringsfaktor för efterfrågan** för produkten till *1,5* för alla veckor i augusti.

På det här sättet kan du beräkna buffertvärden över tid och sedan justera dem baserat på mer än bara den information som systemet har. I en fullständig DDMRP-implementering beräknar du nya buffertvärden varje dag via ett batchjobb och accepterar värdena automatiskt. Du kör sedan planering som ett batchjobb och granskar planerade order varje dag i syfte att fylla på buffertarna.

## <a name="implement-buffers-in-supply-chain-management"></a>Implementera buffertar i Supply Chain Management

I det här avsnittet beskrivs hur du implementerar din buffertzonsstrategi i Microsoft Dynamics 365 Supply Chain Management. Detta förutsätter att du redan har utfört de analyser och beräkningar som beskrivs i den första halvan av den här artikeln.

### <a name="set-up-buffers-for-a-decoupling-point-item"></a><a name="set-up-buffers"></a>Konfigurera buffertar för en avdelningspunktartikel

Följ dessa steg om du vill konfigurera buffertvärden för en avdelningspunkt.

1. Gå till **Produktinformationshantering \> Produkter \> Frisläppta produkter**.
1. Välj en frisläppt artikel som har konfigurerats som en avdelningspunkt. (Mer information finns i [Lagerplacering](ddmrp-inventory-positioning.md).)
1. I åtgärdsfönstret, på fliken **Plan**, väljer du **Artikeldisponering**.
1. På sidan **Artikeldisponering** väljer du en post för artikeldisponering som skapar en avdelningspunkt. (Den här posten visar namnet på en disponeringsgrupp som har konfigurerats för att skapa avdelningspunkter.)
1. Välj fliken **Allmänt**.
1. Om du vill att systemet ska beräkna om buffertvärdena varje dag eller varje vecka baserat på din försäljningshistorik, dina prognoser och gruppinställningarna för disponering, följer du dessa steg:

    1. Ange **Buffertvärden över tid** som *Ja*.
    1. En meddelanderuta meddelar dig att dina manuella buffertinställningar (**Minimum**, **Beställningspunkt** och **Maximum**) kommer att återställas om du fortsätter. Välj **Ja** om du vill behålla den nya inställningen.

    Alternativt följer du dessa steg om du föredrar att beräkna eller ange buffertinställningarna bara en gång:

    1. Ange **Buffertvärden över tid** som *Nej*.
    1. Ställ in fälten **Minimum**, **Beställningspunkt** och **Maximum** till de buffertvärden som du har beräknat för artikeln, enligt beskrivningen tidigare i den här artikeln.

1. Ställ in följande fält för att slutföra inställningen av DDMRP-beräkningar för artikeln:

    - **Ordercykel** – Ange antalet dagar som måste passera mellan två inköpsorder för artikeln. Ange värdet till *0* (noll) om det inte finns några orderbegränsningar. Det här fältet påverkar bufferten för maximikvantitet, enligt tidigare beskrivet i den här artikeln.
    - **Genomsnittlig daglig användning** – Du kan ange ett uppskattat ADU för artikeln. Detta fält är bara avsett för information. Normalt beräknas värdet automatiskt som en del av buffertberäkningarna.
    - **Tröskel för ordertopp** – Ange det lägsta antalet dagliga försäljningar av artikeln som kvalificeras som försäljningsstopp (detta gäller för ovanligt hög efterfrågan). Systemet använder detta fält för att öka omorderkvantiteten för planerade order i perioder med hög efterfrågan. Mer information finns i [Efterfrågedriven planering](ddmrp-planning.md).

### <a name="calculate-or-enter-decoupled-lead-times"></a><a name="calc-lead-time"></a>Beräkna eller ange avdelade ledtider

För artiklar där du väljer att tillåta systemet att [beräkna dina buffertzoner automatiskt](#set-up-buffers), följ då dessa steg för att beräkna eller ange avdelade ledtider för en artikel med avdelningspunkt.

1. Öppna sidan **Artikeldisponering** för avdelningspunktartikeln. (Mer information finns i [Konfigurera buffertar för en avdelningspunktartikel](#set-up-buffers).)
1. Välj en post för artikeldisponering som skapar en avdelningspunkt.
1. Välj fliken **Buffertvärden**.
1. Om inga tidsperioder visas i rutnätet väljer du fliken **Buffertvärden** i åtgärdsfönstret och väljer **Lägg till tidsperioder**. Systemet fyller rutnätet med rader för varje dag eller vecka, beroende på om fältet **Minimal, Maximal och beställningspunktperiod** för [disponeringsgruppen](ddmrp-inventory-positioning.md) angetts som *Daglig* eller *Veckovis*. Systemet lägger till tillräckligt med rader för att komma upp till tidsgränsen som har angetts för disponeringsgruppen som tilldelats artikeln.
1. Välj den tidsperiod där du vill beräkna den avdelade ledtiden. (Vanligtvis är denna tidsperiod den period som inkluderar dagens datum.)
1. I åtgärdsfönstret, på fliken **Buffertvärden**, väljer du **Beräkna avdelad ledtid**.
1. I dialogrutan **Beräkna avdelad ledtid** ställer du in följande fält:

    - **Strukturlista** – Välj den strukturlista som du vill köra beräkningen på.
    - **Datum** – Välj det datum som du vill köra beräkningen på. Uppsättningen tillgängliga strukturlistor filtreras så att endast strukturlistor som är aktiva för det valda datumet visas.
    - **Kvantitet** – Ange den kvantitet som du vill köra beräkningen på. Uppsättningen tillgängliga strukturlistor filtreras så att endast strukturlistor som gäller för angiven kvantitet visas.

1. Välj **OK** om du vill köra beräkningen och stänga dialogrutan **Beräkna avdelad ledtid**. I kolumnen **Avdelad ledtid** för din valda tidsperiod visas nu det beräknade värdet.

### <a name="calculate-or-enter-average-daily-usage"></a><a name="calc-adu"></a>Beräkna eller ange genomsnittlig daglig användning

För artiklar där du väljer att tillåta systemet att [beräkna dina buffertzoner automatiskt](#set-up-buffers) följer du dessa steg för att beräkna eller ange ADU för en artikel med avdelningspunkt.

1. Öppna sidan **Artikeldisponering** för avdelningspunktartikeln. (Mer information finns i [Konfigurera buffertar för en avdelningspunktartikel](#set-up-buffers).)
1. Välj en post för artikeldisponering som skapar en avdelningspunkt.
1. Välj fliken **Buffertvärden**.
1. Om inga tidsperioder visas i rutnätet väljer du fliken **Buffertvärden** i åtgärdsfönstret och väljer **Lägg till tidsperioder**. Systemet fyller rutnätet med rader för varje dag eller vecka, beroende på om fältet **Minimal, Maximal och beställningspunktperiod** för [disponeringsgruppen](ddmrp-inventory-positioning.md) angetts som *Daglig* eller *Veckovis*. Dessutom tas standardvärden för fälten för **ledtidsfaktor** och **varianter** från disponeringsgruppen. Du kan redigera dessa värden för varje enskild rad efter behov.
1. Välj en tidsperiod där du vill beräkna ADU.
1. I åtgärdsfönstret, på fliken **Buffertvärden**, väljer du **Beräkna genomsnittlig daglig användning**. Systemet försöker samla in data som krävs för ADU-beräkningen enligt definitionen för [disponeringsgruppen](ddmrp-inventory-positioning.md).
1. Gör något av följande:

    - Om nödvändiga data är tillgängliga läggs beräkningsresultat till i kolumnen **Genomsnittlig daglig användning**. I så fall krävs ingen åtgärd.
    - Om obligatoriska data inte är tillgängliga läggs inga värden till automatiskt. I det här fallet anger du manuellt uppskattade värden för varje rad där du planerar att beräkna buffertvärden.

### <a name="calculate-and-apply-buffer-values"></a>Beräkna och tillämpa buffertvärden

För artiklar där du väljer att tillåta systemet att [beräkna dina buffertzoner automatiskt](#set-up-buffers) kan du utläsa beräkningen av buffertvärden manuellt genom att följa dessa steg.

1. För den relevanta artikeln för avdelningspunkt [konfigurerar du buffertberäkningen](#set-up-buffers), [beräknar eller anger avdelade ledtider](#calc-lead-time) samt [beräknar eller anger genomsnittlig daglig användning](#calc-adu) för alla relevanta tidsperioder, på det sätt som tidigare beskrivs i artikeln.
1. Öppna sidan **Artikeldisponering** för avdelningspunktartikeln.
1. Välj fliken **Buffertvärden** som redan bör visa en lista över tidsperioder.
1. Välj den tidsperiod där du vill beräkna buffertvärden. (Vanligtvis kommer den här tidsperioden att vara perioden som inkluderar "idag".) Den rad du väljer måste redan ha värden som inte är noll i kolumnerna **Genomsnittlig daglig användning** och **Avdelad ledtid**.
1. Redigera fältet **Faktor för efterfrågejustering** för en eller flera rader efter behov. Systemet tillämpar denna faktor på värdet **Genomsnittlig dagliga användning** i alla buffertberäkningar där värdet används. Med hjälp av denna faktor kan du justera hur efterfrågan varierar efter datum (till exempel för semestrar eller säsongsartiklar).
1. I åtgärdsfönstret, på fliken **Buffertvärden**, väljer du **Beräkna minimi-, maximi- och beställningspunktkvantiteter**. Systemet beräknar och fyller i kolumnerna **Beräknat minimum**, **Beräknad beställningspunkt** och **Beräknat max** i rutnätet på sidan **Artikeldisponering**.
1. När du har slutfört granskningen av de beräknade värdena måste du tillämpa dem. I annat fall har de ingen effekt. När du applicerar en beräkning på en eller flera rader kommer värden från fälten **Beräknat minimum**, **Beräknad beställning** och **Beräknat maximum** att kopieras till kolumnen **Minimum**, **Beställningspunkt** respektive **Maximum**. I åtgärdsfönstret, på fliken **Buffertvärden**, i gruppen **Vidta åtgärd**, väljer du en av följande knappar:

    - **Acceptera alla beräkningar** – Applicera alla beräknade värden i rutnätet.
    - **Acceptera beräkningar för markerade rader** – Applicera endast beräknade värden för de markerade raderna.
    - **Ignorera alla beräkningar** – Ignorera alla beräknade värden för minimikvantiteter, maximikvantiteter och beställningspunkter i rutnätet.
    - **Ignorera beräkningar för valda rader** – Ignorera alla beräknade värden för minimikvantiteter, maximikvantiteter och beställningspunkter för valda rader.

### <a name="schedule-automatic-buffer-value-calculations"></a>Tidsplanering av automatiska beräkningar av buffertvärde

När du har ställt in dina DDMRP-inställningar och bekräftat att de fungerar som väntat vill du troligen skapa ett batchjobb för att periodiskt omberäkna ADU och relaterade buffertvärden, baserat på faktiska förbrukningsdata och/eller uppdaterade prognoser. Den här proceduren gäller bara för artiklar där du väljer att tillåta att [buffertzoner beräknas automatiskt i systemet](#set-up-buffers).

Följ dessa steg för att tidsplanera automatiska beräkningar av buffertvärde.

1. Gå till **Huvudplanering \> Huvudplanering \> DDMRP \> Beräkna buffertvärden**.
1. I dialogrutan **Beräkna buffertvärden** ställer du in följande fält:

    - **Beräkna genomsnittlig daglig användning** – Ange det här alternativet som *Ja* om du vill omberäkna ADU för avdelningspunktartiklar varje gång jobbet körs. Ange som *Nej* för att hoppa över denna beräkning. Vanligtvis ska du ange detta alternativ som *Ja*.
    - **Beräkna avdelad ledtid** – Ange detta alternativ som *Ja* för att beräkna om de avdelade ledtiderna varje gång jobbet körs. Ange som *Nej* för att hoppa över denna beräkning. Vanligtvis ska du ange detta alternativ som *Ja*.
    - **Beräkna buffertvärden** – Ange det här alternativet som *Ja* om du vill omberäkna buffertvärden varje gång jobbet körs. Ange som *Nej* för att hoppa över denna beräkning. Vanligtvis ska du ange detta alternativ som *Ja*.
    - **Acceptera beräkning för min, max och beställningspunkt** – Ange det här alternativet som *Ja* om du vill godkänna och tillämpa de omberäknade buffertvärdena automatiskt varje gång jobbet körs. Ange som *Nej* om du vill att de omberäknade värdena inte ska tillämpas. I det här fallet kommer de omberäknade värdena inte att gälla om inte någon tillämpar dem manuellt från respektive produkts sida för **Artikeldisponering**. Vanligtvis ska du ange detta alternativ som *Ja*.
    - **Huvudplan** – Välj en huvudplan som inkluderar de artiklar som kommer att påverkas av beräkningen. Beräkningen gäller för alla artiklar i planfiltret, som begränsas ytterligare av **filterinställningarna** i den här dialogrutan.

1. För att begränsa mängden poster som detta batchjobb ska köras på: På snabbfliken **Poster som ska inkluderas** väljer du **Filter** för att öppna dialogrutan **Förfrågan**. Denna dialogruta fungerar precis som den gör för andra typer av [bakgrundsjobb](../../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) i Supply Chain Management.
1. På snabbfliken **Kör i bakgrunden** anger du hur, när och hur ofta valda beräkningar ska utföras för de valda artiklarna. Fälten fungerar precis som de gör för andra typer av [bakgrundsjobb](../../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) i Supply Chain Management.
1. Välj **OK** om du vill lägga till det nya jobbet i en batchkö för körning.

### <a name="review-and-recalculate-decoupled-lead-times-for-all-items"></a>Granska och beräkna om avdelade ledtider för alla artiklar

Följ dessa steg när du vill granska och beräkna om alla avdelade ledtider som är tillgängliga i din juridiska person (företaget).

1. Gå till **Huvudplanering \> Huvudplanering \> DDMRP \> Avdelad ledtid**.
1. På sidan **Avdelad ledtid** bläddrar du fram till och filtrerar listan efter behov för att hitta den information du letar efter. Om du vill visa ännu mer information om en artikel markerar du dess länk i kolumnen **Artikelnummer**.
1. Om du vill beräkna om den avdelade ledtiden för valfri artikel markerar du artikeln och väljer **Beräkna avdelad ledtid** i åtgärdsfönstret. Dialogrutan **Beräkna avdelad ledtid** visas. Den här dialogrutan fungerar på samma sätt som när du [beräknar avdelade ledtider](#calc-lead-time) för samma artikel på sidan **Artikeldisponering**.
