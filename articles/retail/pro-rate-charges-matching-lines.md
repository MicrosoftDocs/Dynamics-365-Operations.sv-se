---
title: Allokera huvudavgifter för att matcha försäljningsrader
description: Det här avsnittet beskriver ytterligare funktioner för beräkning och tillämpning av automatiska avgifter för beställningar i butikskanal med hjälp av funktioner för avancerade automatiska avgifter.
author: hhaines
manager: annbe
ms.date: 04/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: d9f36da025528272b1a95456acf597dd5d923819
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/24/2019
ms.locfileid: "2025182"
---
# <a name="prorate-header-charges-to-matching-sales-lines"></a>Allokera huvudavgifter för att matcha försäljningsrader


[!include [banner](includes/banner.md)]

Det här avsnittet beskriver funktionen för gruppering av automatiska avgifter på huvudnivå och -tillägg och allokera dem till butiksförsäljningsrader. Denna funktion är tillgänglig för transaktioner som skapas i kassan i Retail version 10.0.1 och försäljning som skapas i kundtjänst i Retail version 10.0.2.

Denna funktion är endast tillgänglig om funktionen [avancerade automatiska avgifter](https://docs.microsoft.com/dynamics365/unified-operations/retail/omni-auto-charges) har aktiverats med hjälp av alternativet på sidan **Butiksparametrar**. Förbättrade beräkningsmetoden för automatiska avgifter kan dessutom tillämpas endast till försäljningsorder för butik som skapas via detaljhandelskanaler (kassan, en kundtjänst och Dynamics näthandelsplattform).

Denna nya funktion ger organisationer större flexibilitet i sättet som automatiska avgifter på huvudnivå beräknas och tillämpas på butiksförsäljningstransaktioner.

I versioner av Retail som är tidigare än version 10.0.1 beräknas automatiska avgifter på huvudnivå som har en viss leveranssättsrelation endast när det finns en matchning med leveranssätt som definieras i försäljningsorderrubriken.

Exempelvis definieras automatiska avgifter på huvudnivå **99** och leveranssätt **11**. En försäljningsorder skapas och leveranssätt **99** definieras i orderrubriken. Men vissa försäljningsrader är inställda på att levereras med hjälp av leveranssättet **11**. I det här fallet beaktas och tillämpas endast avgifter på huvudnivå som är kopplade till leveranssätt **99** på försäljningsorder.

I Retail har avgifter på huvudnivå ytterligare en funktion som gör det möjligt att definiera en [skiftindelad avgiftskonfiguration](https://docs.microsoft.com/dynamics365/unified-operations/retail/configure-call-center-delivery) som baseras på ordervärdet. Till exempel om ordervärdet är mellan 50,00 $ och 200,00 $ kanske organisationen vill debitera en fraktavgift på 5,00 $. Om ordervärdet är mellan 200,01 $ och 500,00 $ kan fraktkostnaden vara 4,00 $.

Vissa organisationer vill ha fördelarna med skiftindelad avgiftsberäkning som medföljer avgifter på huvudnivå. I scenarier som avser blandade leveranssätt kan de också vilja se till att de avgifter som beräknas baseras på matchning med leveranssättet som har definierats på varje försäljningsrad.

Du kan nu konfigurera automatiska avgifter på huvudnivå så att alla leveranssätt för ordern beaktas när avgifter beräknas. Den här funktionen kräver en mer komplicerad beräkningslogik för att beräkna avgifter på huvudnivå. Logiken samlar ihop alla artiklar som levereras med samma leveranssätt och den behandlar den gruppen som beräkningsgruppen för artiklar när den beräknar automatiska avgifter på huvudnivå. För artiklar med samma leveranssätt beräknas automatiska avgifter utifrån det kombinerade försäljningsvärdet för artiklarna. På så sätt bestäms lämplig nivå för automatisk avgift.

Efter att lämpliga avgifter på huvudnivå erhålls för försäljningsrader som levereras med samma leveranssätt, allokeras beräknade avgifter till nivån för försäljningsraden. Eftersom dessa avgifter finns på radnivå och inte hålls på huvudnivå, görs en mer specifik länk mellan artikeln och värdet på avgiften som beräknats för den. Detta sätt kan vara användbart vid delvisa returer, där en organisation endast vill återbetala en del av avgiften istället för hela avgiften när endast vissa artiklar returneras.

## <a name="scenarios"></a>Scenarier

Följande två exempelscenarier beskriver hur dessa avgifter ska beräknas när de nya funktionerna används och när de inte används.

### <a name="scenario-1"></a>Scenario 1

I det här scenariot beskrivs beteendet när alternativet **Allokera huvudavgifter för att matcha försäljningsrader** är **Nej** i inställningarna för automatisk avgift. (Beteendet motsvarar avgifter på huvudnivå i tidigare Retail-versioner än version 10.0.1.)

I det här scenariot har organisationen definierat avgifter på huvudnivå för leveranssättrelation **99** och leveranssättrelation **11**. Inga automatiska avgifter är konfigurerade för leveranssätt **21**.

![Automatiska avgifter för leveranssätt 99 när matchande proportionell fördelning stängs av](media/99_disabled.png)

![Automatiska avgifter för leveranssätt 11 när matchande proportionell fördelning stängs av](media/11_disabled.png)

En försäljningsorder skapas i kundtjänst och leveranssätt anges till **99**. Den här beställningen innehåller fem artiklar. Två rader har konfigurerats för att använda leveranssätt **99**, två rader har konfigurerats för att använda leveranssätt **11** och en rad har konfigurerats för att använda leveranssätt **21**, enligt följande tabell.

| Artikel  | Radkvantitet | Leveransläge | Pris per enhet |
|-------|---------------|---------------|----------------|
| 81331 | 1             | 11            | 10 $            |
| 81332 | 1             | 99            | $50            |
| 81333 | 2             | 11            | 30 $            |
| 81334 | 3             | 99            | 10 $            |
| 81334 | 3             | 21            | 5 $             |

I detta scenario utvärderas hela beställningen mot tabellen med automatiska avgifter för leveranssätt **99**. Den totala summan av alla försäljningsrader används för att bestämma en matchande nivå i konfigurationen av automatisk avgift och denna avgift tillämpas på orderhuvudnivån. I det här exemplet är ordersumman 165,00 $ och fraktkostnaden 15,00 $ tillämpas i orderrubriken. Automatiska avgifter som är konfigurerade för leveranssätt **11** refereras eller tillämpas aldrig.

I detta scenario, om en kund returnerar vissa av artiklarna på ordern, och om [avgiftskoden har konfigurerats så att den ska återbetalas](https://docs.microsoft.com/dynamics365/unified-operations/retail/omni-auto-charges#setup-and-configuration-2), kommer den totala avgiften på huvudnivå systematiskt tillämpas återbetalningen, även om endast vissa av artiklarna returneras.

### <a name="scenario-2"></a>Scenario 2

I det här scenariot definieras avgifter på huvudnivå för leveranssättrelation **99** och leveranssättrelation **11**. Men alternativet **Allokera huvudavgifter för att matcha försäljningsrader** är inställd på **Ja** för dessa tabeller för automatiska avgifter.

![Automatiska avgifter för leveranssätt 99 när matchande proportionell fördelning slås på](media/99_enabled.png)

![Automatiska avgifter för leveranssätt 11 när matchande proportionell fördelning slås på](media/11_enabled.png)

Det här scenariot använder samma försäljningsorder som innehåller fem rader. Leveranssätt i orderrubriken anges till **99**, men leveranssätt för varje artikel i försäljningsordern har konfigurerats enligt följande tabell.

| Artikel  | Radkvantitet | Leveransläge | Pris per enhet |
|-------|---------------|---------------|----------------|
| 81331 | 1             | 11            | 10 $            |
| 81332 | 1             | 99            | $50            |
| 81333 | 2             | 11            | 30 $            |
| 81334 | 3             | 99            | 10 $            |
| 81334 | 3             | 21            | 5 $             |

Eftersom konfigurationen av automatisk avgift är inställd på proportionellt fördelas på matchande försäljningsrader utför systemet följande beräkning.

1. Alla artiklar som har samma leveranssätt grupperas ihop och systemet beräknar det totala produktvärdet för artiklarna i gruppen.

    **Leveranssätt 11**

    - Artikel 81331, antal 1 = 10 $
    - Artikel 81333, antal 2 = 60 $ netto (30 $ per enhet)
    - **Totalt produktvärde för leveranssätt 11 = 70 $**

    **Leveranssätt 99**

    - Artikel 81332, antal 1 = 50 $
    - Artikel 81334, antal 3 = 30 $ netto
    - **Totalt produktvärde för leveranssätt 99 = 80 $**

    **Leveranssätt 21**

    - Artikel 81334, antal 3 = 15 $ netto
    - **Totalt produktvärde för leveranssätt 21 = 15 $**

2. Systemet söker efter konfigurationen för automatiska avgifter på huvudnivå som matchar kunden och inställningar för leveranssätt för varje grupp med artiklar. Om konfigurationen hittas ser systemet i den skiftindelade konfigurationen för att hitta den avgift som ska tillämpas, baserat på det totala produktvärdet för artiklar i gruppen för leveranssätt.

    **Leveranssätt 11**

    - Totalt butiksproduktvärde = 70 $
    - **Avgiftsvärde = 7 $**

    **Leveranssätt 99**

    - Totalt butiksproduktvärde = 80 $
    - **Avgiftsvärde = 15 $**

    **Leveranssätt 21**

    - Totalt butiksproduktvärde = 15 $
    - **Avgiftsvärde = 0 $** (inga automatiska avgifter har konfigurerats för den här kombinationen av kund och ett leveranssätt).

    ![Avgifter med leveranssätt 11 är indelade i det markerade skiktet.](media/step2mode11.png)

    ![Avgifter med leveranssätt 99 är indelade i det markerade skiktet.](media/step2mode99.png)

3. Systemet beräknar det avgiftsvärde som ska tillämpas på varje rad baserat på den proportionella fördelningslogiken som beaktar det proportionella värdet för raden i förhållande till gruppens totala produktvärde.

    **Leveranssätt 11**

    - Avgiftsvärde = 7 $
    - Grupproduktvärde = 70 $
    - Rad 1 värde = 10 $ (= 14,2857 procent av gruppvärdet)
    - Rad 3 värde = 60 $ (= 85,7143 procent av gruppvärdet)
    - **Radavgift för rad 1 = 1 $**
    - **Radavgift för rad 3 = 6 $**

    **Leveranssätt 99**

    - Avgiftsvärde = 15 $
    - Grupproduktvärde = 80 $
    - Rad 2 värde = 50 $ (= 62,5 procent av gruppvärdet)
    - Rad 4 värde = 30 $ (= 37,5 procent av gruppvärdet)
    - **Radavgift för rad 2 = 9,38 $**
    - **Radavgift för rad 4 = 5,62 $**

    **Leveranssätt 21**

    - Avgiftsvärde = 0 $
    - Grupproduktvärde = 15 $
    - Rad 5 värde = 15 $ (= 100 procent av gruppvärdet)
    - **Radavgift för rad 5 = 0 $**

Därför kommer artikel 81334 få en fraktavgift på 5,62 $ i det här exemplet. Du kan visa dessa avgifter på sidan **Underhållavgifter** för försäljningsraden. Följande bild visar hur den här sidan ser ut för artikel 81334.

![Proportionellt fördelade avgifter på försäljningsraden för artikel 81334](media/proratedlinecharge.png)

När denna beräkningsmetod används i ett scenario med delvis retur, om avgiftskoden återbetalas kommer endast en del av avgiften som tilldelas den här raden att återbetalas när artikeln returneras.
