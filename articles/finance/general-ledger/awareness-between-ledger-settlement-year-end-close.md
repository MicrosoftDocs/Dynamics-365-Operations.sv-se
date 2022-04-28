---
title: Medvetenhet mellan redovisningskvittning och årsbokslut
description: Det här ämnet ger information om förbättringar som in inverkan på redovisningskvittningar och stängningen av redovisningsåret.
author: kweekley
ms.date: 04/06/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-01-31
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: 13d0a0a11a8f31e4ba647ccc23906f6b137051c2
ms.sourcegitcommit: b96e0c70553bca9b3f5eb65105a52cb71d978a36
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/07/2022
ms.locfileid: "8553344"
---
# <a name="awareness-between-ledger-settlement-and-year-end-close"></a>Medvetenhet mellan redovisningskvittning och årsbokslut

[!include [banner](../includes/banner.md)]


I Microsoft Microsoft Dynamics 365 Finance version 10.0.25 finns **Medvetenhet mellan redovisningskvittning och årsbokslut** tillgänglig i arbetsytan för **funktionshantering**. Med den här funktionen läggs två primära förbättringar till som påverkar redovisningskvittning och årsbokslut.

Vid årsbokslut kommer de redovisningstransaktioner som har kvittats inte längre att inkluderas i den ingående balansen för nästa räkenskapsår. Denna förbättring säkerställer att endast oreglerade redovisningstransaktioner inkluderas i den ingående balansen. Det är viktigt när omvärdering av utländsk valuta körs i redovisningen. Omvärdering av utländsk valuta körs endast för redovisningstransaktioner med status **Ej kvittad**. Innan funktionen **Medvetenhet mellan redovisningskvittning och årsbokslut** släpptes, sammanfattade ingående balans båda transaktionerna som har statusen **Kvittad** och de som har statusen **Inte kvittad** och statusen för det sammanfattade beloppet sattes till **Inte kvittad**.

Den andra förbättringen gör att du kan bokföra detaljerade ingående saldotransaktioner vid stängning av redovisningsåret. Om alternativet **Behåll detaljer vid årsbokslut** ställs in på **Ja**, skapas en separat ingående balans för varje redovisningstransaktion som inte kvittas. Den här inställningen definieras för varje huvudkonto i inställningarna för redovisningskvittning. Genom att behålla detaljerade transaktioner för den ingående balansen kan du förbättra möjligheten att kvitta de oreglerade redovisningstransaktionerna under nästa räkenskapsår.

Som ett stöd för de nya förbättringarna har ändringar gjorts i redovisningskvittning och årsbokslutet.

### <a name="changes-to-ledger-settlement"></a>Ändringar av redovisningskvittning

- Redovisningskvittning måste ske inom ett räkenskapsår.
- Redovisningskvittning måste utföras för transaktioner på ett enda huvudkonto. Huvudkontot är nu ett obligatoriskt filter på sidan **Redovisningkvittning**.
- Redovisningskvittning och återföring av redovisningskvittning kan inte göras för transaktioner som bokförs inom ett stängt räkenskapsår (med andra ord har årsbokslutet körts).

### <a name="changes-to-year-end-close"></a>Ändringar av årsbokslut

- En årsbokslut kan inte återföras om några ingående saldotransaktioner har kvittats under nästa räkenskapsår. Den här ändringen gäller när ett årsbokslut återförs eller när ett årsbokslut körs om och **Ta bort befintliga bokslut vid årets slut när du stänger året igen** raderas när alternativet **Ja** har angetts i redovisningsparametrarna.
- Om alternativet **Behåll detaljer vid årsbokslut** ställs in på **Ja** för något balansräkningskonto i redovisningskvittningen, skapas mer detaljerade ingående saldotransaktioner för huvudkontot.

## <a name="before-you-enable-the-feature"></a>Innan du aktiverar funktionen

På grund av ändringarna i funktionen och datamodellen är det viktigt att du överväger följande innan du aktiverar funktionen:

- Eftersom endast kvittade transaktioner visas i den ingående balansen måste du ta bort transaktioner från det aktuella räkenskapsåret som kvittas mot transaktioner under föregående räkenskapsår. Transaktionerna måste kvittas på nytt mot transaktioner inom aktuellt räkenskapsår. Detta kan göras via en justeringspost för aktuellt räkenskapsår. Justeringen återför de summerade ingående saldona och motbokar med den detaljerade transaktion som krävs för att kvitta redovisningsposterna för aktuellt år. 

  > [!IMPORTANT]
  > Om detta inte sker får du ett felmeddelande om **saldofel** när du kör årsbokslutsstängningen för aktuellt räkenskapsår. Om det inte är möjligt att ta bort och återställa redovisningstransaktioner med samma räkenskapsår, bör du inte aktivera funktionen förrän efter att årsboksslutet har slutförts. Aktivera funktionen omedelbart efter att årsbokslutet har slutförts och innan några nya redovisningstransaktioner kvittas under nästa räkenskapsår. 
  
- Alla transaktioner som har markerats för kvittning men inte kvittats avmarkeras automatiskt när funktionen aktiveras. Om du vill förhindra att arbetet går förlorade, kvittar du alla markerade transaktioner innan du aktiverar funktionen.
- Vissa organisationer kör årsbokslutet flera gånger för samma räkenskapsår. Aktivera inte funktionen om årsbokslutet redan har körts en gång och kommer att köras igen för samma räkenskapsår. Funktionen måste vara aktiverad innan du bearbetar det första årsbokslutet eller efter att du har bearbetat räkenskapsårets senaste årsbokslut.

  Om du vill aktivera funktionen, men årsbokslutet redan har körts en gång, måste du återföra årsbokslutet innan du kan aktivera funktionen.

- Eftersom kvittning mellan huvudkonton inte längre är tillåten bör du justera kontoplanen eller processerna så som krävs för att säkerställa att redovisningskvittning kan göras på samma huvudkonto.
- Funktionen kan inte aktiveras om den offentliga sektorns årsbokslutprocess används.

## <a name="set-up-ledger-settlement"></a>Ställa in redovisningskvittning

När du har aktivera funktionen, och innan du kör nästa årsbokslut, måste varje organisation bestämma om den ska behålla transaktionsdetaljerna under årsbokslutet. Valet påverkar inte ingående saldobokföring från föregående årsbokslutsprocesser.

Alternativet **Behåll detaljer vid årsbokslut** ställs in för varje huvudkonto på sidan **Inställning av redovisningskvittning**.

1.  Gå till **Redovisning** > **Redovisningsinställning** > **Redovisningsparametrar**.
2.  På fliken **Redovisningskvittningar**, välj **Konton för redovisningskvittning**.

- eller -

1.  Gå till **Redovisning** > **Periodiska uppgifter** > **Redovisningskvittningar**.
2.  Välj **redovisningkvittningskonton**.

Två kolumner har lagts till på sidan **Redovisningskvittningar**:
    
- **Huvudkontotyp** – Den här kolumnen är endast till för information. Den visar den typ som tilldelats huvudkontot.
- **Behåll detaljer vid årsbokslut** – Alternativet ställs som standard in på **Nej**. Det kan endast ställas in på **Ja** om värdet i kolumnen **Huvudkontotyp** är **Balansräkning**, **Tillgång** eller **Skulder**. När alternativet ställs in på **Nej** bokförs ingående saldon sammanfattningen, vilket är vanligt vid stängningen av året. Om det är inställt på **Ja**, skapas ingående saldon i detalj för varje redovisningstransaktion som inte kvittas för huvudkontot.

## <a name="year-end-close"></a>Årsbokslut

När du kör årsskiftet nära genom att gå till **Redovisning** > **Periodstängning** > **Årsbokslut**, skapar processen de ingående saldona för de huvudkonton som har definierats för redovisningskvittning. De ingående saldona skapas i antingen sammanfattning eller detalj, beroende på inställningarna för redovisningskvittning. Processen exkluderar redovisningstransaktioner som har kvittats, oavsett om du bokför den ingående balansen för varje huvudkonto i sammanfattning eller i detalj.

Flera transaktioner bokförs till exempel på huvudkontot 130100 räkenskapsåret 2021.

| Journalnummer | Verifikation  | Datum       | Typ      | Huvudbokskonto | Kontonamn        | Beskrivning       | Valuta | Belopp i transaktionsvaluta | Belopp  | Belopp i rapporteringsvaluta |
|----------------|----------|------------|-----------|----------------|---------------------|-------------------|----------|--------------------------------|---------|------------------------------|
| 20853          | FTV-3000 | 12/3/2021  | Pågående | 130100-001-    | Kundreskontra | Tjänstavgift       | USD      | 100                            | 100     | 100                          |
| 20855          | FTV-3004 | 12/5/2021  | Pågående | 130100-002-    | Kundreskontra | Verktyg         | USD      | 175                            | 175     | 175                          |
| 20854          | CMV-4000 | 12/16/2021 | Pågående | 130100-001-    | Kundreskontra | Återbetalning            | USD      | -100                           | -100    | -100                         |
| 20851          | ARP-8000 | 12/20/2021 | Pågående | 130100-002-    | Kundreskontra |                   | USD      | -0,88                          | -0,88   | -0,88                        |
| 20853          | ARPM0004 | 12/20/2021 | Pågående | 130100-002-    | Kundreskontra |                   | EUR      | -127,11                        | -174,12 | -174,12                      |
| 20856          | CMV-4010 | 12/21/2021 | Pågående | 130100-002-    | Kundreskontra | Kredit på konto | USD      | -175                           | -175    | -175                         |
| 20857          | FTV-3011 | 12/28/2021 | Pågående | 130100-001-    | Kundreskontra | Verktyg         | USD      | 400                            | 400     | 400                          |
| 20910          | FTV-3020 | 12/29/2021 | Pågående | 130100-002-    | Kundreskontra | Service           | USD      | 300                            | 300     | 300                          |

Av dessa transaktioner kvittas tre under redovisningskvittning.

Det finns en faktura på 175 USD. Fakturan betalades med en betalning i euro (EUR) och en kassarabatt togs.

| Journalnummer | Verifikation  | Datum       | Typ      | Huvudbokskonto | Kontonamn        | Beskrivning | Valuta | Belopp i transaktionsvaluta | Belopp  | Belopp i rapporteringsvaluta |
|----------------|----------|------------|-----------|----------------|---------------------|-------------|----------|--------------------------------|---------|------------------------------|
| 20855          | FTV-3004 | 12/5/2021  | Pågående | 130100-002-    | Kundreskontra | Verktyg   | USD      | 175                            | 175     | 175                          |
| 20851          | ARP-8000 | 12/20/2021 | Pågående | 130100-002-    | Kundreskontra |             | USD      | -0,88                          | -0,88   | -0,88                        |
| 20853          | ARPM0004 | 12/20/2021 | Pågående | 130100-002-    | Kundreskontra |             | EUR      | -127,11                        | -174,12 | -174,12                      |

Resultaten för huvudkonto 130100 på om funktionen är aktiverad innan stängningen av året körs. Om funktionen är aktiverad beror resultatet även på inställningen av Behåll detaljer vid stängningen av året.

### <a name="the-feature-isnt-enabled"></a>Funktionen är inte aktiverad
Vid årsbokslut skapas tre ingående saldotransaktioner för huvudkontot 130100 under 2022. Summan av transaktionerna i redovisningsvalutan är 525 USD.

| Journalnummer | Verifikation  | Datum     | Typ    | Huvudbokskonto | Kontonamn        | Beskrivning | Valuta | Belopp i transaktionsvaluta | Belopp  | Belopp i rapporteringsvaluta |
|----------------|----------|----------|---------|----------------|---------------------|-------------|----------|--------------------------------|---------|------------------------------|
| 20910          | YEC_2021 | 2022-01-01 | Ingående | 130100-002-    | Kundreskontra |             | USD      | 299.12                         | 299.12  | 299.12                       |
| 20910          | YEC_2021 | 2022-01-01 | Ingående | 130100-001-    | Kundreskontra |             | USD      | 400                            | 400     | 400                          |
| 20910          | YEC_2021 | 2022-01-01 | Ingående | 130100-002-    | Kundreskontra |             | EUR      | -127,11                        | -174,12 | -174,12                      |

Även om betalningens transaktion för EUR -127,11 har kvittats kommer transaktionen fortfarande att börja som ett ingående saldo.

### <a name="feature-is-enabled-and-keep-detail-during-year-end-close--no"></a>Funktionen är aktiverad och behåll detaljer under stängningen av året = Nej

Vid årsbokslut skapas två ingående saldotransaktioner för huvudkontot 130100 under 2022. Summan av transaktionerna i redovisningsvalutan är fortfarande USD 525, men de redovisningsreglerade transaktionerna exkluderas från den ingående balansen. Det totala beloppet för kontobeloppet 130100-002 är 125 USD i stället för 299,12 USD och transaktionen på 127,11 euro/174,12 USD är utesluten.

| Journalnummer | Verifikation  | Datum     | Typ    | Huvudbokskonto | Kontonamn        | Beskrivning | Valuta | Belopp i transaktionsvaluta | Belopp | Belopp i rapporteringsvaluta |
|----------------|----------|----------|---------|----------------|---------------------|-------------|----------|--------------------------------|--------|------------------------------|
| 20910          | YEC_2021 | 2022-01-01 | Ingående | 130100-002-    | Kundreskontra |             | USD      | 125                            | 125    | 125                          |
| 20910          | YEC_2021 | 2022-01-01 | Ingående | 130100-001-    | Kundreskontra |             | USD      | 400                            | 400    | 400                          |

### <a name="feature-is-enabled-and-keep-detail-during-year-end-close--yes"></a>Funktionen är aktiverad och behåll detaljer under stängningen av året = Ja

Vid årsbokslut skapas fem ingående saldotransaktioner för huvudkontot 130100 under 2022. En separat ingående balanstransaktion skapas för var och en av de fem transaktioner som inte kvittas. Summan av transaktionerna i redovisningsvalutan är fortfarande 525 USD.

| Journalnummer | Verifikation  | Datum     | Typ    | Huvudbokskonto | Kontonamn        | Beskrivning       | Valuta | Belopp i transaktionsvaluta | Belopp | Belopp i rapporteringsvaluta |
|----------------|----------|----------|---------|----------------|---------------------|-------------------|----------|--------------------------------|--------|------------------------------|
| 20910          | YEC_2021 | 2022-01-01 | Ingående | 130100-001-    | Kundreskontra | Tjänstavgift       | USD      | 100                            | 100    | 100                          |
| 20910          | YEC_2021 | 2022-01-01 | Ingående | 130100-001-    | Kundreskontra | Återbetalning            | USD      | -100                           | -100   | -100                         |
| 20910          | YEC_2021 | 2022-01-01 | Ingående | 130100-002-    | Kundreskontra | Kredit på konto | USD      | -175                           | -175   | -175                         |
| 20910          | YEC_2021 | 2022-01-01 | Ingående | 130100-001-    | Kundreskontra | Verktyg         | USD      | 400                            | 400    | 400                          |
| 20910          | YEC_2021 | 2022-01-01 | Ingående | 130100-002-    | Kundreskontra | Service           | USD      | 300                            | 300    | 300                          |

När transaktionsinformationen sparas påverkas inte de ursprungliga detaljerade transaktionerna. De förblir bokförda och oreglerade i räkenskapsåret som stängs. En kopia av dessa transaktioner skapas för den ingående balansen. Följande värden från de ursprungliga transaktionerna kopieras till ingående balanstransaktioner.

- Redovisningskonto (huvudkontot och alla ekonomiska dimensioner)
- Belopp i transaktions-, redovisnings- och rapporteringsvalutor
- Beskrivning
- Bokföringsskikt
- Bokföringstyp

   > [!NOTE]
   > Inga andra ingående saldotransaktioner har tilldelats en bokföringstyp. Bokföringstypen kan därför användas för att ingående transaktioner ska särskiljas i detalj.

Vissa fält från de ursprungliga transaktionerna måste ändra i den ingående balansens detaljerade transaktioner. Datumet för ingående saldotransaktioner är alltid den första dagen på nästa räkenskapsår. Journalnumret måste ändras och verifikationsnumret ändras till värdet som angavs i dialogrutan årsbokslut.

Information från de ursprungliga transaktionerna finns på sidan **Redovisningkvittning**. Varje detaljerad ingående balanstransaktion visar kolumnen **Ursprungligt transaktionsdatum** i rutnätet. Den här kolumnen kan hjälpa dig att matcha transaktioner i det nya räkenskapsåret. Du kan välja **Visa ursprunglig verifikation** om du vill gå tillbaka till hela originalverifikationen.

## <a name="settle-transactions"></a><a name="settle-transactions"></a>Kvitta transaktioner
Om du vill kvitta redovisningstransaktioner följer du dessa steg.

1. Gå till **Redovisning** > **Periodiska uppgifter** > **Redovisningskvittningar**.
2.  Ställ in filtren längst upp på sidan.

    1. Välj ett datumintervall. Alternativt kan du välja en datumintervallkod för att automatiskt fylla i datumintervallet.

       - Datumintervallet får inte gå mellan räkenskapsår. Om datumintervallet sträcker sig över räkenskapsår visas inga transaktioner när du väljer **Visa transaktioner**.
       - Om datumintervallet är i ett öppet räkenskapsår kan transaktionerna kvittas och kvittningen kan återföras. Om datumintervallet är i ett stängt räkenskapsår, eller om årsbokslutet har slutförts, visas transaktioner, men de kan inte kvittas eller oregleras. Du kan bara avmarkera transaktioner i ett stängt räkenskapsår. Om datumintervallet är i ett stängt räkenskapsår är knapparna **Markera valda**, **Kvitta markerade transaktioner** och **Återför markerade transaktioner** inte tillgängliga.

    2. Välj huvudkontot att visa transaktioner för. Detta fält måste fyllas i. I uppslagslistan visas bara de huvudkonton som har valts på sidan **Redovisningskvittning** för företagets kontoplan.
    3. Välj bokföringsskikt. Du kan inte kvitta transaktioner som finns i olika bokföringsskikt.
    4. Om du vill visa huvudkonto och dimensioner i separata kolumner, välj en uppsättning av ekonomiska dimensioner.

3.  Välj **Visa transaktioner** för att visa alla transaktioner som matchar de filter du anger. Om du ändrar något av filtren eller dimensionsuppsättningarna måste du markera **Visa transaktioner** igen.
4.  Markera rader för kvittning. Värdet på fältet **markerade belopp** längst upp på sidan höjs eller sänks med för att återspegla det totala beloppet på de valda raderna.
5.  När du är klar med att välja transaktioner väljer du **Markera valda**. För varje vald transaktion visas en bockmarkering i kolumnen **Markerad**. Dessutom ökar eller minskar värdet på fältet **markerat belopp** ovanför rutnätet ökar eller minskar för att återspegla den totala mängden på de markerade raderna.
6.  När värdet i fältet **markerade belopp** är **0** (noll), välj **Kvitta markerade transaktioner**.

    - Delvis kvittning är inte tillåten. Du kan till exempel inte kvitta en debettransaktion på 100 USD mot en kredittransaktion på 90 USD. Återstående 10 USD måste även markeras för inkludering i kvittningen.
    - Ange ett kvittningsdatum. Datumet måste in på eller efter det senaste datumet för de transaktioner som har markerats för kvittning.

Status för de markerade transaktionerna uppdateras till **Kvittad**.

> [!IMPORTANT]
> Alla transaktioner som du har markerat för kvittning för den aktiva juridiska personen och det valda huvudkontot kvittas. Transaktionerna behöver inte visas på sidan. De kvittas även om de är dolda på grund av ett filter.

Vissa processer, till exempel en transaktionsåterföring, kvittar automatiskt redovisningstransaktioner. Till exempel kvittas en betalning och faktura i kundreskontra och kvittningen genererar en realiserad vinst/förlust. Kvittningen av betalningen och fakturan kvittar inte några redovisningstransaktioner, till exempel transaktioner för redovisningskonton för kundreskontra. Om betalningen och fakturan inte kvittas i kundreskontra, kommer den återföringsredovisningspost som bokfördes vid återföringen av kundreskontrakvittningen att medföra att de ursprungliga redovisningsposterna och återföringsposterna kvittas i huvudboken. När funktionen **Medvetenhet mellan redovisningskvittning** och årsbokslut har aktiverats, inträffar inte redovisningskvittningen för en återföring automatiskt om återföringsdatumet är ett annat räkenskapsår.

## <a name="use-excel-for-ledger-settlement"></a>Använd Excel för redovisningskvittning

Transaktioner som visas på sidan **redovisningskvittning** kan exporteras till Excel. I Excel kan du filtrera transaktioner ytterligare för att avgöra vilka transaktioner som ska markeras för kvittning.
Båda kvittningsenheterna i redovisningen exporterar redovisningstransaktioner bara för huvudkontot som valts på sidan **Redovisningkvittning**. Transaktioner för stängda räkenskapsår kan fortfarande markeras eller avmarkeras med hjälp av Excel, men de kan inte kvittas. Kvittade transaktioner kan inte återföras för samma räkenskapsår.

## <a name="make-transactions-easier-to-find"></a>Göra det lättare att hitta transaktioner

Sidan **Redovisningskvittningar** innehåller funktioner som gör det lättare att visa de transaktioner som behövs för kvittning.

•   Använd filtret **Markerade** låter dig filtrera transaktioner utifrån om fältet **Markerade** har markerats.
•   Använd filtret **Status** för att filtrera transaktioner utifrån deras status.
•   Välj **Sortera efter absolut belopp** om du vill sortera beloppen efter absolut värde. På det här sättet kan du gruppera debet- och kredit som har samma belopp.

## <a name="reverse-a-settlement"></a>Återföra en kvittning

Du kan återföra en kvittning som har gjorts av misstag.

1.  Följ stegen 1 till 3 i avsnittet [Kvitta transaktioner](#settle-transactions) för att visa de transaktioner som du är intresserad av.
2.  I fältet **Status** markerar du **Kvittad**.
3.  Markera rader för återföring.
4.  Välj **Återför markerade transaktioner**. Statusvärdet för alla transaktioner som har samma kvittnings-ID uppdateras till **Inte kvittad**.

> [!IMPORTANT]
> Alla transaktioner som har samma kvittnings-ID återförs, även om de inte är markerade. Till exempel har fyra rader markerats och kvitterats. Alla fyra raderna har samma kvittnings-ID. Om du markerar en av dessa fyra rader och sedan väljer **Återföra markerade transaktioner** kommer alla fyra raderna att återföras.






