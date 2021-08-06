---
title: Årsbokslut
description: I det här avsnittet beskrivs den nödvändiga inställningen och stegen för att köra årsslutsprocessen i redovisningen.
author: kweekley
ms.date: 07/10/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerClosingSheet
audience: Application User
ms.reviewer: roschlom
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f5b4e8c5103a06f696f863b1eed40b3821f274d7
ms.sourcegitcommit: f2dfec2f4c427e37a574e6acdfaaf150bc92ebb6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/23/2021
ms.locfileid: "6661023"
---
# <a name="year-end-close"></a>Årsbokslut

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs den nödvändiga inställningen och stegen för att köra årsslutsprocessen i redovisningen.

I slutet av ett räkenskapsår måste du köra årslutslutprocessen för att överföra ingående saldon till det nya året. De flesta företag kör årsbokslutsprocessen flera gånger. Den första körningen flyttar saldona till det nya räkenskapsåret. Processen kan sedan köras om så många gånger som krävs för att flytta saldon från justeringsposter till det nya räkenskapsåret.

Vid årsbokslutsprocessen skapas två typer av möjliga transaktioner. En IB-transaktion skapas alltid och används för att skapa ingående balans i det nya räkenskapsåret. IB-transaktionen visar balansräkningarna under det nya räkenskapsåret och saldon från resultaträkningen i det reserverade resultatbokförarkontot under det nya räkenskapsåret. UB-transaktioner skapas eventuellt för att resultaträkningens saldon ska nollställas under räkenskapsåret som avslutas

## <a name="prepare-to-run-the-year-end-close"></a>Förbered körning av årsbokslut

Innan du kör årsslutsprocessen verifierar du inställningarna för följande:

På sidan **Huvudkonto**:

- Kontrollera att fältet för **huvudkontotyp** är korrekt inställt för varje huvudkonto. Huvudkontotypen används för att avgöra om saldot för huvudkontot flyttas framåt som ett ingående saldo eller avslutas till balanserade vinstmedel i IB-transaktionen.
- Saldot på huvudkontot kan överföras till ett nytt huvudkonto under årets slut. Ange nya huvudkontot som har angetts i fältet **Ingående konto**. Vanligtvis används detta fält för balansräkningens huvudkonton när huvudkontot är inaktiverat och ett nytt huvudkonto används för det nya räkenskapsåret.

På sidan **Redovisningsparametrar** under **Stängning av räkenskapsår**:

- Alternativet **Ta bort befintliga bokslut vid årets slut när du stänger året igen** används för att ange om den systemgenererade IB-transaktionen från föregående årsbokslut ska tas bort när årsbokslutet körs igen. Om det här alternativet ställs in på **Ja**, de tidigare öppnings- och valfria stängningstransaktionerna raderas och en ny öppnings- eller stängningstransaktion skapas baserat på de aktuella saldona. Om det här alternativet ställs in på **Nej**, föregående öppnings- och valfria avslutande transaktioner kvarstår, och en ytterligare öppnings- eller avslutande transaktion skapas för att flytta saldona framåt från att justera transaktioner som bokförs efter föregående årsbokslut.
- Alternativet **Skapa UB-transaktioner vid överföring** används för att skapa UB-transaktioner i räkenskapsåret som avslutas för att visa saldon på vinst-och förlustkonton till noll. Om det här alternativet ställs in på **Ja**, skapas både IB-transaktion och UB-transaktioner. Om det här alternativet ställs in på **nej**, skapas IB-transaktion i nästa räkenskapsår för att överföra saldona. Saldon på vinst- och förlustkonton ligger kvar i slutet av räkenskapsåret.
- Alternativet **ange räkenskapsårets status till stängd permanent** används för att ställa in räkenskapsåret till permanent avslutad status. Använd det här alternativet med försiktighet, eftersom perioder med statusvärdet Permanent stängda inte kan öppnas igen. Därför kan justeringar inte bokföras på räkenskapsåret. Det bästa är att ange detta som **Nej**.
- **Verifikationsnumret måste vara ifyllt** om det har tagits bort. En verifikation krävs nu när processen årsslut körs. Då anges verifikationsnumret manuellt.

På sidan **räkenskapskalender**:

- Nästa räkenskapsår måste finnas innan du kör årsbokslut. I annat fall kan inte de ingående saldona skapas i den ingående perioden.

På sidan **Redovisningskalender**:

- Valfritt: Varje räkenskapsperiod för räkenskapsåret som stängs kan tilldelas **Väntar** för att förhindra att nya transaktioner förs in. När justeringar identifieras kan väntande perioder öppnas på nytt när du bokför justeringar, även om årsslutsprocessen redan har körts.

På sidan **Mallinställning för årsbokslut**:

- När funktionen **Bokföringsförbättringar vid årsskiftet**-funktionen är påslagen, är processen för att ställa in mallen för årsbokslut separerad från processen för att köra årsbokslutet. Mallen kan definieras på sidan **Mallinställning för årsbokslut** (**Redovisning \> Redovisningsinställningar \> Mallinställning för årsbokslut**), eller det kan nås från slutet av årsskiftet.

## <a name="define-year-end-close-templates"></a>Definiera årsbokslutsmallar

Årsbokslutsprocessen kan köras när systemet är konfigurerat. På sidan **Mallinställning för årsbokslut** kan en mall kan definieras för gruppen med juridiska personer där årsbokslutsprocessen ska köras. Mallen kommer att återanvändas nära varje årsskifte, men kan ändras om din organisation ändras.

Först definierar du fältet **gruppnamn** för mallen och väljer räkenskapskalendern. Gruppnamnet ska identifiera gruppen av juridiska personer. När du bestämmer grupperna för juridiska personer måste du komma ihåg att juridiska personer bara kan inkluderas i samma grupp om samma räkenskapskalender har valts för dem. Till exempel kan mallarna ställas in baserat på geografi och separata grupper kan skapas för juridiska personer i Nordamerika, Europa, Mellanöstern och Afrika (EMEA) juridiska enheter och Asien-Stillahavsområdet (APAC) juridiska enheter.

Juridiska personer kan sedan läggas till i mallen. Juridiska personer kan läggas till genom att välja en organisationshierarki eller genom att välja de juridiska personerna. Om en organisationshierarki väljs, läggs endast juridiska personer i hierarkin till som använder den valda skattekalendern till mallen. Om du använder juridiska personer som vill lägga till mallen kan endast juridiska personer med samma räkenskapskalender läggas till. Samma räkenskapskalender krävs eftersom årsbokslutet körs genom att välja ett räkenskapsår som kan variera från en kalender till en kalender.

När de juridiska enheterna har lagts till, definierar du de viktigaste boksluten för varje juridisk enhet.

Fliken **ekonomiska dimensionen** används för att definiera vilka ekonomiska dimensioner som ska användas på IB-transaktionen. Observera att installationen på den här fliken endast gäller den juridiska person som är vald i **juridiska personer**. Inställningen upprepas för varje juridisk person i rutnätet.

Alternativet **Överför dimensioner i balansräkningen** används för att definiera om de ekonomiska dimensionerna i transaktioner som bokförts på balansräkningskonton ska hanteras på IB-transaktion. Det bästa är att ange detta som **Ja**. Inställningen för balansräkningsdimensioner påverkar inte befintliga saldon i redovisningskontona för balanserade vinstmedel. Dessa saldon bestäms av de vinst- och förlustdimensioner som definieras i nästa avsnitt. Räkenskapsåret 2019 var till exempel det första året som stängdes och alternativet **Stäng alla** användes för att välja dimensioner för **avdelning** och **kostnadsställe** för stängning. I det här fallet skapas ett separat konto för balanserade vinstmedel för varje kombination av en avdelning och ett kostnadsställe. När årsslutsslutet körs för räkenskapsåret 2020 förblir de balanserade intäkterna från föregående år exakt som de bokfördes, även om **balansräkningsdimensionerna för överföring** är inställda på **Nej**. Saldon som bokförs på balanserade vinstmedel från föregående årsslut ändras aldrig.

Avsnittet **Överför resultatdimensioner** används för att ange vilka ekonomiska dimensionerna i transaktioner på bokförda vinst- och förlustkontot överförs till huvudkontot för balanserade vinstmedel. Först identifierar du de ekonomiska dimensionerna som är relevanta för den valda juridiska personen. Dessa finansiella dimensioner inkluderar alla finansiella dimensioner som var bokförda under året, även om den ekonomiska dimensionen inte är en del av en aktiv kontostruktur. Härnäst definierar du varje dimension som **Stäng enstaka** eller **Stäng alla**. Standardalternativet är **Stäng alla**. Detta alternativ har den ekonomiska dimensionens ursprungliga värden från bokförda transaktioner och använder dem för att skapa ingående saldon för balanserad vinst eller förlust. Separata ingående saldon för balanserad vinst eller förlust skapas för varje unik kombination av värden för ekonomiska dimensioner. Om **Stäng enstaka** är markerat kommer alla transaktioner som bokförs med den ekonomiska dimensionen sammanfattas i en balanserade vinstmedel ingående balans för det dimensionsvärde som angetts i fältet efter **Stäng enstaka**. Anta att alla transaktioner för räkenskapsåret har bokförts med kontostrukturen för **huvudkontot – avdelning**. I **Avdelning** ekonomiska dimensionen på mallen, **Stäng enstaka** är markerad och värdet **100** anges som dimension. Om den totala intäkten för alla transaktioner som bokförts till avdelningar 200, 300 och 400 är 100,000 kr skapas en ingående balans för **Balanserade vinstmedel – 100**. Om du väljer **Stäng enstaka** och lämnar värdet för ekonomisk dimension tomt kommer alla transaktioner bokföras till balanserade vinstmedel med det dimensionsvärdet tomt.

## <a name="run-the-year-end-close-process"></a>Körning av årsbokslutprocess

När mallarna för årsbokslut har skapats kan du initiera processen för årsbokslut på sidan **Årsbokslut** (**Redovisning \> Periodstängning \> Årsbokslut**). Innan du kör årsskiftet kan du lägga till nya mallar för slutet av året eller ändra befintliga mallar genom att välja **Mallinställning för årsbokslut** för att öppna installationssidan för mallarna.

Välj årsbokslutsmallen och välj sedan åtgärdsfönstret **köra årsbokslutet**. Välj antingen alla juridiska enheter eller en delmängd av juridiska personer från mallen som du kör bokslutet för slutet av året. När du kör årsbokslut för första gången i ett räkenskapsår, kommer du troligen att välja de juridiska personerna för att skapa ingående balanser för dem. Om du tidigare har kört slutet på årsskiftet kanske du vill köra om det bara för de juridiska personer som justeringar har bokförts för.

Välj sedan det räkenskapsår som du vill köra årsbokslutsprocessen. Om det finns fler än en bokslutsperiod för räkenskapsårets sista period blir fältet **Periodnamn** tillgängligt. Du kan sedan välja den slutperiod som ska användas för att bokföra den avslutande transaktionen, om inställningen är definierad för att skapa den avslutande transaktionen.

Sedan anger du ett verifikationsnummer. Samma verifikationsnummer används för alla juridiska personer som har valts för årsbokslutsprocessen. Verifikationsnummer genereras inte för att använda nummersekvens.

Årsbokslutprocessens standardvärden som ska köras i batchläge. När du har initierat det kan du därför återgå till andra aktiviteter.

Eftersom kontostrukturer kan ändras under ett räkenskapsår kan den relevanta kontostrukturen inte alltid identifieras. Årsbokslutsprocessen följer inte kontostrukturer. När IB-transaktioner skapas flyttas saldona framåt med ekonomiska dimensioner enligt årsbokslutsmallen. Posterna i ingående saldon kan inte längre inkludera ekonomiska dimensioner i aktuell kontostruktur och segmentkombinationerna är inte längre giltiga i den aktuella kontostrukturen. Om organisationen vill utesluta en ekonomisk dimension för balanserade vinstmedel ingående balans anger du ekonomiska dimensionen **Stäng enstaka** och lämnar dimensionsvärdet tomt.

När processen är klar skapas en post för varje kombination av en juridisk person och ett räkenskapsår. Du kommer bara att se poster för juridiska personer som du har åtkomst till. Varje post innehåller systemdatum och -tid när processen körs samt en direkt länk till verifikationerna som skapades för årsslutsslutet.

[![Poster som skapas på snabbflik för Årsbokslutshistorik på sidan Årsbokslut](./media/run-yr-end-close.png)](./media/run-yr-end-close.png)

Om du kör om bokslutet på nytt ser du en eller flera poster för varje kombination av en juridisk person och ett räkenskapsår, beroende på inställningen för alternativet **Ta bort befintliga bokslut vid årets slut när du stänger året igen** på sidan **Redovisningsparametrar** page:

- Om alternativet anges till **Ja**, verifikation för föregående årsbokslut raderas. Posten markeras som **Återfört** och stämplas med datum och tid då återföringen gjordes. Dessutom tas länken till verifikationsnumret bort. När årsbokslut är slutfört skapas en ny post för den nya verifikationen som skapas.
- Om alternativet ställs in på **Nej**, posten för föregående årsbokslut kvarstår, tillsammans med länken till verifikationen. Varje gång årsbokslut kör igen skapas en ny post tillsammans med en länk till de nya verifikationerna.

## <a name="reverse-the-year-end-close-process"></a>Återföring av årsbokslutprocess

På sidan **Årsbokslut** kan du återföra ett årsbokslut. Markera posten för kombinationen av en juridisk person och ett räkenskapsår som måste återföras, och välj återför **årsslutsslut**. Återföringsprocessen tar bort alla ingående och UB-verifikationer som har skapats för räkenskapsåret. Posten markeras som **Återfört** och stämplas med datum och tid då återföringen gjordes. Dessutom tas länken till verifikationsnumret bort. Liksom årsbokslutprocessens ska återföringen köras i batchläge.

En kryssruta **Visa återförd** som är tillgängligt ovanför rutnätet kan du dölja eller visa poster för omvända slutet av processerna vid årsbokslut. När du har kört processen **Återföra årsbokslut** måste du kanske markera kryssrutan **Visa återförd** för att se posten. Du kan ställa in ytterligare filter om du vill visa annan information.

[![Använda kryssrutan Visa återförda om du vill visa poster för återförda årsbokslut processer på sidan Årsbokslut](./media/rvrs-yr-end-close.png)](./media/rvrs-yr-end-close.png)

Mer information finns i [Stäng redovisningen vid periodslut](close-general-ledger-at-period-end.md) och [Stäng räkenskapsåret](tasks/close-fiscal-year.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
