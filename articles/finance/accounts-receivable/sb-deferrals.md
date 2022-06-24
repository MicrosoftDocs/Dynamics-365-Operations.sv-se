---
title: Intäkts- och utgiftsperiodiseringar i Prenumerationsfakturering
description: Detta ämne beskriver hur du ställer in intäkts- och utgiftsperiodisering i prenumerationsfakturering.
author: JodiChristiansen
ms.date: 11/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: 209afd08c0c7e3cbd63ed95613b1d1dec94856f5
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8908108"
---
# <a name="revenue-and-expense-deferrals-in-subscription-billing"></a>Intäkts- och utgiftsperiodiseringar i Prenumerationsfakturering

Detta ämne beskriver hur du ställer in och använder intäkts- och utgiftsperiodisering i prenumerationsfakturering. Periodisringsplaner baseras alltid på samt beror på ett underliggande ursprungligt dokument eller en underliggande ursprunglig faktureringsplan. Eftersom de skapas baserat på standardvärden, kan de inte anges eller skapas separat.

Processen för inställning och användning av intäkts- och utgiftsperiodiseringar sker på flera sidor:

- På sidan **Parametrar för intäkts- och utgiftsperiodisering** kan du definiera företagets inställningar.
- På sidan **Periodideringsstandarder** kan du ställa in de standardkonton och standardmallar som används för periodisringsplaner.
- På sidorna för **periodiseringsmallar** och **Händelsebaserade periodiseringsmallar** kan du definiera vilka mallar som används för periodisringsplaner.
- På sidan **Alla periodisringsplaner** kan du visa och redigera valfri periodiseringsplan.

Intäkts- och utgiftsaviseringar kan användas tillsammans med återkommande kontraktfakturering.

## <a name="revenue-and-expense-deferral-parameters"></a>Periodiseringsparametrar för intäkt och utgift

Sidan **Periodiseringsparametrar för intäkt och utgift** innehåller följande fält.

| Fält | Beskrivning |
|---|---| 
| Fliken **Tidsplan** | |
| Lika per period | <p>Ange om antalet dagar i en period används när beloppet per period beräknas för en periodiseringsplan:</p><ul><li>**Ja** – Beloppet för respektive period är detsamma, oavsett antalet dagar i perioden. Delperioder (till exempel perioder i början eller slutet av en periodiseringsplan) kommer att fördelas proportionellt.</li><li>**Nej** – Beloppet beräknas utifrån antalet dagar per period.</li></ul><p>Du kan åsidosätta den här inställningen på transaktionsnivå.</p> |
| Periodiseringsalternativ för försäljningsrabatt | <p>Ange hurivida separata periodiseringstidsplaner ska skapas för rabatt- och försäljningsorderbeloppen:</p><ul><li>**Separat tidsplan för rabatt** – Rabattbeloppet hålls separat från intäktsbeloppet.<p>I det här fallet skapas två periodiseringstidsplaner när en försäljningsorder skapas och sedan bokförs. Rabatt- och intäktsbeloppen bokförs på olika periodiseringskonton.</p></li><li>**Slå ihop rabatt och intäkt** – Rabattbeloppet kombineras med intäktsbeloppet. En av periodiseringstidsplanerna skapas, och både rabattbeloppet och intäktsbeloppet bokförs på samma periodiseringskonto.<p>I det här fallet skapas en periodiseringstidsplan när en försäljningsorder skapas och sedan bokförs. Både rabattbeloppet och intäktsbeloppet bokförs på samma periodiseringskonto.</p></li></ul><p>**Observera:** Om du vill tillämpa rabatter på artiklar som använder funktionen för icke-fakturerad intäkt väljer du alternativet **Separat tidsplan för rabatt**. Rabatter kan sedan tillämpas på alla artiklar, oavsett om funktionen för iocke-fakturerad intäkt används eller inte. Om alternativet **Slå ihop rabatt och intäkt** har valts kan rabatter inte tillämpas på artiklar som använder funktionen för icke-fakturerade intäkter.</p> |
| Periodiseringsalternativ för inköpsrabatt | <p>Välj huruvida separata periodiseringstidsplaner ska skapas för rabatt- och inköpsorderbeloppen:</p><ul><li>**Separat tidsplan för rabatt** – Rabattbeloppet hålls separat från utgiftsbeloppet.<p>I det här fallet skapas två periodiseringstidsplaner när en inköpsorder skapas och sedan bokförs. Rabatt- och utgiftsbeloppen bokförs på olika periodiseringskonton.</p></li><li>**Slå ihop rabatt och intäkt** – Rabattbeloppet kombineras med utgiftsbeloppet. En periodiseringstidsplaner skapas, och både rabattbeloppet och utgiftsbeloppet bokförs på samma periodiseringskonto.<p>I det här fallet skapas en periodiseringstidsplan när en inköpsorder skapas och sedan bokförs. Både rabattbeloppet och utgiftsbeloppet bokförs på samma periodiseringskonto.</p></li></ul> |
| Konsolidera föregående perioder | <p>Ange om tidsplansrader för periodisering konsolideras för föregående perioder:</p><ul><li>**Ja** – Om startdatumet för periodiseringen ligger i en period före transaktionsdatumet kombineras alla belopp under den period som omfattar transaktionsdatumet till en enda tidsplansrad för periodisering.</li><li>**Nej** – Beloppen från alla perioder förvaras på separata rader i periodiseringstidsplanen.<p>Om periodiseringens startdatum ligger i samma period som eller en senare period än transaktionsdatumet har det här alternativet ingen effekt.</p></li></ul><p>Denna inställning kan uppdateras på transaktionsnivå.</p> |
| Standardstartdatum för periodisering | <p>Välj den regel som ska användas för att bestämma startdatumet för periodiseringstidsplanen:</p><ul><li>**Transaktionsdatum** – Använd transaktionsdatum som startdatum.</li><li>**Början på aktuell månad** – Använd den 1:a i aktuell månad som startdatum. Om transaktionsdatumet är den 1:a i varje månad, är den 1:a i aktuell månad lika med startdatumet.</li><li>**Början på nästa månad** – Använd den 1:a i nästa månad som startdatum. Om transaktionsdatumet är den 1:a, används transaktionsdatumet. Annars används den 1:a i nästa månad.</li><li>**15-regeln** – Om transaktionsdatumet är mellan den 1:a och den 15:e ska du använda den 1:a i aktuell månad som startdatum. Om transaktionsdatumet är den 16:e eller senare använder du den 1:a i nästkommande månad som startdatum.</li></ul><p>Du kan uppdatera denna inställning på transaktionsnivå.</p> |
| Metod för kortfristig periodisering | <p>Välj metoden för korttidsperiodisering: **Ingen**, **Rullande perioder** eller **Fast år**.</p><p>|
| Bokföringsmetod för periodisering | <p>Välj den metod som används för att skapa periodiseringstransaktionser:</p><ul><li>**Balansräkning –** Använd bokföringsmetoden för balansräkning för att skapa periodiseringstransaktioner.</li><li>**Vinst och förlust** – Använd bokföringsmetoden för vinst och förlust för att skapa periodiseringstransaktioner. När transaktionerna har bokförts kan du granska fakturaverifikationen om du vill se de extra poster som balanserar de ursprungliga beloppen för redovisning och redovisningsförskjutning.</li></ul> |
| Återför resultaträkningen för kredit | <p>**OBS!** Detta fält är endast tillgängligt när fältet **Periodiseringsbokföring** är inställt på **Vinst och förlust**.</p><p>Ange om vinst- och förlustbeloppen ska återföras när en återföring, uppsägning eller återbetalning tillämpas på en faktureringsplan eller en försäljningsorder:</p><ul><li>**Ja** – Återför vinst- och förlustbeloppen samt tillämpa ett kreditjusteringsbelopp på periodisringsplanen.<p>Om återföringen uppstår hallvägs genom en faktureringsperiod, delräknas beloppen.</p></li><li>**Nej** – Ingen återföringstransaktion skapas för vinst- och förlustbeloppen när en återföring, uppsägning eller återbetalning tillämpas på en faktureringsplan eller en försäljningsorder:</li></ul> |
| Fliken **redovisning** | |
| Bokför allmänna journaler automatiskt | <p>Ange om journalposter som skapas av intäkts- och utgiftsperiodiseringar bokförs automatiskt:</p><ul><li>**Ja** – Bokför journalposter som skapas av intäkts- och utgiftsperiodiseringar automatiskt.<p>**Tips:** Genom att välja **Ja** kan du förhindra inkonsekvenser i redovisningen som orsakas av manuella ändringar av verifikationer.</p></li><li>**Nej** – Journalposter som skapas av intäkts- och utgiftsperiodiseringar bokförs inte automatiskt. Du måste bokföra eventuella journaler manuellt.</li></ul> |
| Summera redovisningsjournal | <p>Ange om redovisningsverifikationer ska konsolideras som standard:</p><ul><li>**Ja** – Skapa en enda verifikation för alla redovisningsrader som har samma datum. Alla rader i en verifikation som har samma konto konsolideras på en enda rad.</li><li>**Nej** – Skapa en verifikation för varje enskild redovisningsrad.</li></ul><p>Du kan uppdatera den här inställningen på sidan **redovisningsbearbetning**.</p> |
| Standardjournalnamn | Välj journalnamn för journaler som skapas från intäkts- och utgiftsperiodiseringsprocesser, t.ex. redovisningsbearbetning. |
| Beskrivning av redovisningsjournalrad | <p>Välj den beskrivning som visas i journalverifikationens radbeskrivning:</p><ul><li>**Schemalägg raddatum** – Visa raddatum för tidsplaner i journalradbeskrivningen.</li><li>**Ursprunglig transaktionsinformation** – Visa den ursprungliga transaktionsinformationen i beskrivningen av journalraden.<p>**Exempel:** USVARA-0001, CIV-00839, Software Revenue</p></li></ul> |
| Fliken **Nummersekvenser** | På den här fliken kan du ange standardvärden för nummerserier för leasingavtal. Guiden för generering av nummerserier används för att automatiskt generera och tilldela nummerserier. Du behöver inte ändra nummerserien om du inte vill göra manuella ändringar av de genererade nummerserierna. |
| Schemanummer | Det nummer som serieanvänds för periodiseringstidsplaner. |

## <a name="deferral-templates"></a>Periodiseringsmallar

Använd sidan **Periodiseringsmallar** om du vill definiera linjära mallar som används för periodiseringstidsplaner.

Här följer några av fördelarna med att använda en mall:

* Längden på perioden beräknas automatiskt.
* Du tillåter periodiseringsscheman som har perioder där redovisningen hoppas över.
* Du kan automatisera periodiseringarna genom att tilldela mallen till en produkt, en produktgrupp, en produktkategori, kunder eller en kundgrupp. Malltilldelningen görs från sidan **Standardperiodiseringar**.

Flera periodfrekvenser är tillgängliga för mallar: dagliga, månatliga eller räkenskapsperioder.

Mallraderna består av en typ (**Godkänd** eller **Ignorerad**) samt periodlängden. Ignorerade rader har beloppet 0 (noll) på raderna för periodiseringstidsplan. Detta beteende kan vara praktiskt om du inte vill beakta intäkten i alla perioder.

### <a name="create-a-deferral-template"></a>Skapa en periodiseringsmall

Gör så här om du vill skapa en ny periodiseringsmall.

1. På sidan **Periodiseringsmallar** väljer du **Ny**.
2. I fältet **Mall** anger du ett namn.
3. Ange en beskrivning i fältet **beskrivning**.
4. I fältet **Periodfrekvens** väljer du periodfrekvensen.
5. Välj **Lägg till** om du vill lägga till en rad överst i listan med rader, eller välj **Lägg till** för att lägga till en rad längst ned i listan.
6. I fältet **Typ** väljer du periodtypen.
7. I fältet **Periodlängd** anger du periodens längd.
8. Upprepa stegen 5 till och med 7 för varje ytterligare rad som du behöver.
9. Välj **Spara**.

## <a name="deferral-defaults"></a>Standardinställningar för periodisering

Använd sidan **Standardinställningar för periodisering** för att konfigurera periodiseringskonton för artiklar och tilldela standardmallar till periodiseringsbara artiklar. Du kan även konfigurera periodiseringskonton för avgifter och tilldela mallar till de avgifter som kan periodiseras.

**Perkiodisera efter artikel**

För transaktioner som har en artikel (till exempel försäljningsorder) kan du tilldela konton och mallar till specifika artiklar och kunder. Dessa inställningar används som standardvärden när en transaktion periodiseras. Om du vill göra transaktionen periodiseringsbar som standard måste du konfigurera artiklarna på sidan **Periodiseringsbara artiklar**.

**Perkiodisera efter konto**

För transaktioner som inte har några artiklar (till exempel allmänna journaler) kan du ange periodiseringskontona. När dessa konton används på en transaktionsrad markeras transaktionen automatiskt som periodiserad. Motsvarande mall och redovisningskonto tilldelas transaktionsraden.

**Alla transaktionstyper (t.ex. på flikarna Försäljningsorder, Inköp och Allmänt)**

Kontona på sidan är huvudkonton som inte har ekonomiska dimensioner. De ekonomiska dimensionerna för redovisningskontot kommer från kunden eller artikeln, baserat på din organisation.

Varje mallrad måste ha antingen en linkjär radmall eller en händelsebaserad mall. Den kan inte ha båda.

### <a name="for-sales-orders"></a>För försäljningsorder

Följ de här stegen om du vill ange standardvärdena för försäljningsorder.

1. På fliken **Försäljningsorder** väljer du periodiseringstyp.
2. Välj **Lägg till** för att lägga till en rad.
3. I fältet **Artikelkod** väljer du artikelkoden. Artikelkoden bestämmer hur standardvärdena för periodisering används.
4. Ange hur artikelkoden tillämpas:

    * Om fältet **Artikelkod** anges som **Tabell** eller **Grupp** markerar du artikelrelationen i fältet **Artikelrelation**.
    * Om fältet **Artikelkod** är inställt på **Kategori** väljer du kategorirelationen under **Artikelkod**.
    * Om fältet **Artikelkod** ställs in på **Alla** används standardvärdena för alla tillämpliga poster.

5. Ange hur kontokoden tillämpas:

    * Om fältet **Kontokod** anges som **Tabell** eller **Grupp** markerar du kontorelationen i fältet **Kontorelation**.
    * Om fältet **Kontokod** ställs in på **Alla** används kontot för samtliga poster.

6. I fältet **Huvudkonto** väljer du huvudkontot för periodiseringen.
7. Om fältet **Bokföringsmetod för periodisering** är inställt på **Vinst och förlust** anger du det ursprungliga intäktskontot i fältett **Ursprungligt intäktskonto** och motkontot för intäkt i fältet **Motkonto för intäkt**.
8. Om fältet **Kortsiktig periodiseringsmetod** är inställt på **Rullande perioder** eller **Fast år** väljer du kontot för kortsiktig periodisering i fältet **Kortsiktigt periodiseringskonto**.
9. För en mall kan du välja **Lägg till** om du vill lägga till en rad.
10. I fältet **Artikelkod** väljer du artikelkoden.
11. Ange hur artikelkoden tillämpas:

    * Om fältet **Artikelkod** anges som **Tabell** eller **Grupp** markerar du artikelrelationen i fältet **Artikelrelation**.
    * Om fältet **Artikelkod** är inställt på **Kategori** väljer du kategorirelationen i fältet **Kategorirelation**.
    * Om fältet **Artikelkod** ställs in på **Alla** används standardvärdena för alla tillämpliga poster.

12. Ange hur kontokoden tillämpas:

    * Om fältet **Kontokod** anges som **Tabell** eller **Grupp** markerar du kontorelationen i fältet **Kontorelation**.
    * Om fältet **Kontokod** ställs in på **Alla** används kontot för samtliga tillämpbara poster.
    * Välj den linjära mallen i fältet **Linjär mall** eller den händelsebaserade mallen i fältet **Händelsebaserad mall**.

13. Välj **Spara**.

### <a name="for-purchase-orders"></a>För Inköpsorder

Följ de här stegen om du vill ange standardvärdena för inköpsorder.

1. På fliken **Inköp** väljer du periodiseringstyp.
2. Välj **Lägg till** för att lägga till en rad.
3. I fältet **Artikelkod** väljer du artikelkoden.
4. Ange hur artikelkoden tillämpas:

    * Om fältet **Artikelkod** anges som **Tabell** eller **Grupp** markerar du artikelrelationen i fältet **Artikelrelation**.
    * Om fältet **Artikelkod** är inställt på **Kategori** väljer du kategorirelationen i fältet **Kategorirelation**.
    * Om fältet **Artikelkod** ställs in på **Alla** används standardvärdena för alla tillämpliga poster.

5. Ange hur kontokoden tillämpas:

    * Om fältet **Kontokod** anges som **Tabell** eller **Grupp** markerar du kontorelationen i fältet **Kontorelation**.
    * Om fältet **Kontokod** ställs in på **Alla** används kontot för samtliga tillämpbara poster.

6. I fältet **Huvudkonto** väljer du huvudkontot för periodiseringen.
7. Om fältet **Bokföringsmetod för periodisering** är inställt på **Vinst och förlust** anger du det ursprungliga intäktskontot i fältett **Ursprungligt intäktskonto** och motkontot för intäkt i fältet **Motkonto för intäkt**.
8. Om fältet **Kortsiktig periodiseringsmetod** är inställt på **Rullande perioder** eller **Fast år** väljer du kontot för kortsiktig periodisering i fältet **Kortsiktigt periodiseringskonto**.
9. För en mall väljer du **Lägg till** om du vill lägga till en rad. 
10. I fältet **Artikelkod** väljer du artikelkoden.
11. Ange hur artikelkoden tillämpas:

    * Om fältet **Artikelkod** anges som **Tabell** eller **Grupp** markerar du artikelrelationen i fältet **Artikelrelation**.
    * Om fältet **Artikelkod** är inställt på **Kategori** väljer du kategorirelationen i fältet **Kategorirelation**.
    * Om fältet **Artikelkod** ställs in på **Alla** används standardvärdena för alla tillämpliga poster.

12. Ange hur kontokoden tillämpas:

    * Om fältet **Kontokod** anges som **Tabell** eller **Grupp** markerar du kontorelationen i fältet **Kontorelation**.
    * Om fältet **Kontokod** ställs in på **Alla** används kontot för samtliga tillämpbara poster.
    * Välj den linjära mallen i fältet **Linjär mall** eller den händelsebaserade mallen i fältet **Händelsebaserad mall**.

13. Välj **Spara**.

### <a name="for-general-journals"></a>För allmänna journaler

Följ de här stegen om du vill ange standardvärdena för periodisering för allmänna journalposter.

1. Välj fliken **Allmän journal**.
2. För en periodisering väljer du **Lägg till** om du vill lägga till en rad.
3. Om fältet **Kortsiktig periodiseringsmetod** är inställt på **Rullande perioder** eller **Fast år** väljer du kontot för kortsiktig periodisering i fältet **Kortsiktigt periodiseringskonto**.
4. I fältet **Periodiseringskonto** markerar du periodiseringskontot.
5. I fältet **Redovisningskonto** markerar du redovisningskontot.
6. Om fältet **Bokföringsmetod för periodisering** är inställt på **Vinst och förlust** anger du det ursprungliga intäktskontot i fältett **Ursprungligt intäktskonto** och motkontot för intäkt i fältet **Motkonto för intäkt**.
7. Välj den linjära mallen i fältet **Linjär mall** eller den händelsebaserade mallen i fältet **Händelsebaserad mall**.
8. Välj **Spara**.

### <a name="for-free-text-invoices"></a>För fritextfakturor

Följ de här stegen om du vill ange standardvärdena för periodisering för fritextfakturor.

1. Välj fliken **Fritextfaktura**.
2. För en periodisering väljer du **Lägg till** om du vill lägga till en rad.
3. Ange hur kontokoden tillämpas:

    * Om fältet **Kontokod** anges som **Tabell** eller **Grupp** markerar du kontorelationen i fältet **Kontorelation**.
    * Om fältet **Kontokod** ställs in på **Alla** används kontokoden för samtliga tillämpbara poster.

4. I fältet **Periodiseringskonto** markerar du periodiseringskontot.
5. Om fältet **Kortsiktig periodiseringsmetod** är inställt på **Rullande perioder** eller **Fast år** väljer du kontot för kortsiktig periodisering i fältet **Kortsiktigt periodiseringskonto**.
6. I fältet **Redovisningskonto** markerar du redovisningskontot.
7. Om fältet **Bokföringsmetod för periodisering** är inställt på **Vinst och förlust** anger du det ursprungliga intäktskontot i fältett **Ursprungligt intäktskonto** och motkontot för intäkt i fältet **Motkonto för intäkt**.
8. Välj den linjära mallen i fältet **Linjär mall** eller den händelsebaserade mallen i fältet **Händelsebaserad mall**.
9. Välj **Spara**.

### <a name="for-invoice-journals"></a>För fakturajournaler

Följ de här stegen om du vill ange standardvärdena för periodisering för fakturajournalposter.

1. Välj fliken **Fakturajournal**.
2. För en periodisering väljer du **Lägg till** om du vill lägga till en rad.
3. Ange hur kontokoden tillämpas:

    * Om fältet **Kontokod** anges som **Tabell** eller **Grupp** markerar du kontorelationen i fältet **Kontorelation**.
    * Om fältet **Kontokod** ställs in på **Alla** används kontokoden för samtliga tillämpbara poster.

4. I fältet **Periodiseringskonto** markerar du periodiseringskontot.
5. Om fältet **Kortsiktig periodiseringsmetod** är inställt på **Rullande perioder** eller **Fast år** väljer du kontot för kortsiktig periodisering i fältet **Kortsiktigt periodiseringskonto**.
6. I fältet **Redovisningskonto** markerar du redovisningskontot.
7. Om fältet **Bokföringsmetod för periodisering** är inställt på **Vinst och förlust** anger du det ursprungliga intäktskontot i fältett **Ursprungligt intäktskonto** och motkontot för intäkt i fältet **Motkonto för intäkt**.
8. Välj den linjära mallen i fältet **Linjär mall** eller den händelsebaserade mallen i fältet **Händelsebaserad mall**.
9. Välj **Spara**.

### <a name="items-that-are-deferred-by-default"></a>Artiklar som periodiseras som standard

Använd sidan **Artiklar som periodiseras som standard** för att definiera vilka artiklar som ska periodiseras som standard. Du kan ange de transaktionstyper som artiklarna ska periodiseras för. Du kan ange om en enskild artikel, en hel artikelgrupp eller en hel kategori ska periodiseras.

När du ställer in artiklar som periodiserade väljer du standardkonton och standardmallar på sidan **Standardinställningar för periodisering**. Om kontona och mallarna inte markeras, periodiseras inte transaktionsrader där dessa artiklar anges.

För artiklar som periodiseras baserat på den försäljnings- eller inköpskategori som de är associerade med, baseras periodiseringsinställningarna på kategorin. Om kategorin inte har valts i fältet **Kategorirelation** används emellertid de periodiseringsinställningar för den kategori som har högre rangordning. Du kan till exempel lägga till en försäljningskategori för **Hemmavideo** men inte en försäljningskategori för **TV**. När du lägger till en periodiseringsartikel som är associerad med kategorin **TV** används periodiseringsinställningarna för **Hemmavideo** för artikeln.

### <a name="set-up-deferred-items"></a>Konfigurera periodiserade artiklar

Om du vill konfigurera artiklar som periodiseras som standard, följer du dessa steg.

1. På sidan **Artiklar som periodiseras som standard** väljer du den flik som du vill ha: **Försäljningsorder** eller **Inköp**.
2. Välj **Lägg till** för att lägga till en rad.
3. I fältet **Artikelkod** väljer du artikelkoden.
4. Ange hur artikelkoden tillämpas:

    * Om fältet **Artikelkod** anges som **Grupp** eller **Tabell** markerar du artikelrelationen i fältet **Artikelrelation**.
    * Om fältet **Artikelkod** är inställt på **Kategori** väljer du kategorirelationen i fältet **Kategorirelation**.

5. Upprepa stegen 2 till och med 4 för varje ytterligare rad som du behöver.
6. Välj **Spara**.

## <a name="deferred-charges"></a>Periodiserade avgifter

Använd sidan **Periodiseringsavgifter** att definiera vilka avgifter som periodiseras som standard.

> [!NOTE]
> * Periodiserade avgifter är för närvarande endast tillgängliga för försäljningsorder.
> * Avgifter kan endast periodiseras på radnivå. Om du vill periodisera en avgift på rubriknivån för försäljningsorder kan du ställa in avgiften som en periodiseringsartikel på en separat rad på försäljningsordern.
> * Om du vill periodisera en avgift för en fritextfaktura måste du ange avgiften som en separat periodiserad fakturarad.
> * Den här funktionen är inte tillgänglig för supportavgifter och funktionen för intäktsdelning.

### <a name="set-up-deferred-charges"></a>Konfigurera perkiodiserade avgifter

Följ dessa steg för att konfigurera periodiserade avgifter.

1. På sidan **Periodiseringsavgifter** väljer du **Lägg till** för att lägga till en rad.
2. I fältet **Avgiftskod** väljer du avgiftskoden.
3. I fältet **Avgiftsrelation** väljer du avgiftsrelationen.
4. Upprepa stegen 1 till och med 3 för varje ytterligare rad som du behöver.
5. Välj **Spara**.

## <a name="event-based-deferral-templates"></a>Händelsebaserade periodiseringsmallar

På sidan **Händelsebaserade periodiseringsmallar** kan du definiera händelsebaserade periodiseringsmallar som du kan använda i periodiseringstransaktioner och tilldela på sidan **Standardinställningar för periodisering**.

### <a name="create-an-event-based-template"></a>Skapa en händelsebaserad mall

Följ de här stegen om du vill skapa en händelsebaserad periodiseringsmall.

1. På sidan **Händelsebaserade periodiseringsmallar** väljer du **Ny**.
2. I fältet **Mall** anger du ett unikt namn för mallen.
3. Ange en beskrivning i fältet **beskrivning**.
4. I fältet **Allokeringstyp** väljer du allokeringstypen:

    * **Variabelt belopp** – Allokera ett specifikt belopp för varje rad som anges.
    * **Lika belopp** – Allokera samma belopp för varje rad som anges. 
    * **Procent** – Allokera ett belopp som baseras på den procentsats som anges för varje rad.
    * **Slutförandeprocent** – Allokera ett ackumulerat slutförandevärde för varje rad som anges.
    * **Variabel kvantitet** – Allokera en specifikt kvantitet för varje rad som anges.

5. Ställ in alternativet **Skapa separata händelser per enhet** som **Ja** om du vill att varje händelserad ska delas jämnt med antalet enheter i fakturatransaktionen. Ange som **Nej** om du inte vill dela upp händelseraderna.
6. I fältet **Utgångskonto** markerar du utgångskontot.
7. Välj **Lägg till** om du vill lägga till en rad överst i listan med rader, eller välj **Lägg till** för att lägga till en rad längst ned i listan.
8. I fältet **Beksrivning** anger du en beskrivning för händelsen.
9. Om fältet **Allokeringstyp** har ställts in på **Procentsats** anger du allokeringsprocenten i fältet **Allokeringsprocent**. Procentsatsen måste vara mellan 0 (noll) och 100. Om du lämnar fältet **Allokeringsprocent** tomtm betraktas procentsatsen som 0. Summan av alla procentsatser anges i fältet **Total procentsats** längst ned på sidan, och måste motsvara 100.
10. I fältet **Månader till utgångsdatum** anger du det antal månader som händelsen är giltig. Utgångsdatumet på transaktionsperiodiseringen anges automatiskt baserat på detta värde.
11. Markera kryssrutan **Redovisa vid bokföring** om du vill att intäkten ska redovisas automatiskt när transaktionen bokförs. Om du lämnar kryssrutan avmarkerad måste intäkten redovisas manuellt.
12. I fältet **Redovisningskonto** markerar du redovisningskontot för händelsen om händelsen använder ett annat konto än hela periodiseringstidsplanen. Detta fält används tillsammans med kryssrutan **Redovisa vid bokföring**.
13. Upprepa stegen 7 till och med 12 för varje ytterligare rad som du behöver.
14. Välj **Spara**.
