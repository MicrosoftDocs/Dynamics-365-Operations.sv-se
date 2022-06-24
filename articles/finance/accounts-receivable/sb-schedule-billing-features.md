---
title: Funktioner för faktureringsplan
description: Denna artikeln innehåller information om faktureringsplaner, till exempel prissättningsmetoder, eskaleringar och rabatter, justeringsdatum, proportionell fördelning, omvänd fakturering och uppdelade artikelgrupper.
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
ms.openlocfilehash: b6cfebc2bbfe06e118bfc96f9ae0df6323805e39
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8853595"
---
# <a name="billing-schedule-features"></a>Funktioner för faktureringsplan

[!include [banner](../includes/banner.md)]

Detta ämne innehåller information om faktureringsplaner och rader i faktureringsplaner. Det beskriver olika metoder för prissättning, hur du använder eskaleringar och rabatter, samt hur du återför en faktureringsperiod. Det inkluderar också exempel på beräkningar för proportionell fördelning och delade artikelgrupper.

## <a name="pricing-methods"></a>Prissättningsmetoder

Du kan använda någon av följande prissättningsmetoder när du beräknar enhetspriset för en artikel:

* Förenklat
* Standard
* Nivå
* Fast nivå

### <a name="flat-pricing"></a>Fast pris

När fast prissättningsmetod används kan enhetspriset för en radartikel i faktureringsplanen på sidan **Alla faktureringsplaner** ändras till valfritt värde. Värdet för **Prisenhet** är alltid **1**. Därför är värdena för **Enhetspris** och **Nettobelopp** för en artikel desamma.

### <a name="standard-pricing-without-a-trade-agreement"></a>Standardprissättning (utan handelsavtal)

När standardprissättningsmetoden används utan handelsavtal kan du ställa in enhetspriset för en radartikel i faktureringsplanen genom att välja **Produktinformationshantering** på sidan **Frisläpp produktinformation**. Enhetspriset visas i avsnittet **Basförsäljningspris**. Det beräknas som *Pris* &divide; *Priskvantitet*.

### <a name="standard-pricing-with-a-trade-agreement"></a>Standardprissättning (med handelsavtal)

Följande exempel visar standardprisberäkningarna när det finns ett handelsavtal. Du kan skapa handelsavtal från sidan **Frisläpp produktinformation**.

I båda exemplen används en artikel med följande prishakparenteser.

| Från-kvantitet | Till-kvantitet | U av M | Pris | Prisenhet |
|---|---|---|---|---|
| 0 | 100 | Varje | 1.50 | 1 |
| 100 | 200 | Varje | 1.25 | 1 |
| 200 | 999999 | Varje | 1.00 | 1 |

**Exempel 1**

Fakturakvantiteten är 250 och standardprissättningsmetoden används. Eftersom kvantiteten finns i priskvantitetsintervallet 200–999 999 är enhetspriset 1,00. 

Nettobeloppet beräknas på följande sätt:

*Nettobelopp* = (*Kvantitet* &times; *Pris*) &divide; *Prisenhet* = (250 &times; 1,00) &divide; 1 = 250

**Exempel 2**

Fakturakvantiteten är 100 och standardprissättningsmetoden används. Eftersom fakturakvantiteten finns i priskvantitetsintervallet 0–100 är enhetspriset 1,50.

> [!NOTE]
> Fakturakvantiteten finns i intervallet 0–100 istället för i intervallet 100–200 eftersom en kvantitet i standardkvantitetsmatchningssättet matchar om den är *mer än eller lika med* kvantiteten "från" och *mindre än* kvantiteten "till".

Nettobeloppet beräknas på följande sätt:

*Nettobelopp* = (100 &times; 1,50) &divide; 1 = 150

### <a name="tier-pricing"></a>Nivåprissättning

I följande exempel har en artikel följande prishakparenteser.

| Från-kvantitet | Till-kvantitet | U av M | Pris | Prisenhet |
|---|---|---|---|---|
| 0 | 100 | Varje | 1.50 | 10 |
| 100 | 200 | Varje | 1.25 | 10 |
| 200 | 999999 | Varje | 1.00 | 10 |

Om fakturakvantiteten är 250 och nivåprissättningsmetoden används, beräknas artiklarnas priser på följande sätt, baserat på hakparenteser:

- **De första 100 artiklarna:** 100 &times; 1,50 = 150,00
- **Nästkommande 100 artiklar:** 100 &times; 1,25 = 125,00
- **Återstående artiklar:** 50 &times; 1,00 = 50,00

Nettobeloppet beräknas på följande sätt:

*Nettobelopp* = (150,00 &divide; 10) + (125,00 &divide; 10) + (50,00 &divide; 10) = 15,00 + 12,50 + 5,00 = 32,50

När nettobeloppet har beräknats beräknas enhetspriset genom att dividera nettobeloppet med kvantiteten:

*Enhetspris* = 32,50 &divide; 250 = 0,13

### <a name="flat-tier-pricing"></a>Fast nivåprissättning

I följande exempel har en artikel följande prishakparenteser.

| Från-kvantitet | Till-kvantitet | U av M | Fast nivåbelopp | Prisenhet |
|---|---|---|---|---|
| 0 | 50 | Varje | 100.00 | 50 |
| 50 | 200 | Varje | 150.00 | 200 |

I följande tabell visas fakturor och enhetspriser för de olika kvantiteter som köps in. Nettobeloppet beräknas först, därefter enhetspriset.

| Faktura | Köpt kvantitet | Pris per enhet | Nettobelopp |
|---|---|---|---|
| 1 | 25 | 2,00 &divide; 25 = 0,08 | 100 &divide; 50 = 2,00 |
| 2 | 20 | 2,00 &divide; 20 = 0,10 | 100 &divide; 50 = 2,00 |
| 3 | 50 | 2,00 &divide; 50 = 0,04 | 100 &divide; 50 = 2,00 |
| 4 | 60 | 0,75 &divide; 60 = 0,0125 = 0,01 | 150 &divide; 200 = 0,75 |

## <a name="escalations-and-discounts"></a>Eskaleringar och rabatter

En *eskalering* är en prisökning för en framtida faktureringsperiod som fakturan ännu inte har skapats för. En *rabatt* är en prissänkning för en framtida faktureringsperiod som fakturan ännu inte har skapats för.

Vid prenumerationsfakturering kan eskaleringar och rabatter inte tillämpas retroaktivt på en faktureringsplan. Du kan till exempel inte tillämpa en eskalering på en tre månader gammal faktureringsplan och bearbeta den. Med andra ord kan du inte tillämpa en prisökning som inträffade för tre månader sedan.

Du kan tillämpa en eskalering eller rabatt på en faktureringsplan eller en faktureringsplansrad på någon av följande platser:

- Listsidan **alla/aktiva faktureringsplaner**
- En specifik faktureringsplan
- En specifik faktureringsplansrad

### <a name="apply-an-escalation-or-discount"></a>Tillämpa en eskalering eller rabatt

Följ de här stegen om du vill tillämpa en eskalering eller rabatt på en faktureringsplan.

1. Välj en faktureringsplan eller en faktureringsplansrad.
2. Välj **Eskalering och rabatt** på antyingen fliken **Eskalering och rabatt** eller på raden i faktureringsplanen.
3. Om ett konsumentprisindex används för att beräkna eskaleringen eller rabatten väljer du ett värde i fältet **Beräkning av konsumentprisindex**.
4. Välj **Ny** om du vill lägga till en eskalerings- eller rabattrad.
5. För en rabatt markerar du kryssrutan **Rabatt**. Om du vill göra en eskalering lämnar du kryssrutan **Rabatt**.
6. Ställ in fälten **Startdatum** och **Frekvens**.
7. Ställ in fältet **Slutdatum** för periodiseringsartiklar som använder funktionen för icke-fakturerad intäkt.
8. Ställ in fältet **Procentsats**, **Belopp** och **Tidsplan för konsumentprisindex**.
9. Ställ in fältet **Slutdatum**.
10. Välj **OK**.
11. Upprepa stegen 4 till och med 10 för varje ytterligare eskalering eller rabattrad som du behöver.

### <a name="fields-on-the-billing-schedule-lines-page"></a>Fält på sidan Rader i faktureringsplan

Sidan **Rader i faktureringsplan** innehåller följande fält.

| Fält | Beskrivning |
|---|---|
| Artikelnummer | Artikelnummer för rad för faktureringsplan. Detta fält är endast tillgängligt när sidan öppnas från en radartikel i en faktureringstiplan. |
| Beräkning av konsumentprisindex | <p>Välj den metod som ska användas för att beräkna eskalering av konsumentprisindex:</p><ul><li>**Tidigare konsumentprisindex** – Använd det tidigare konsumentprisindexvärdet för eskaleringsberäkningen.</li><li>**Baskonsumentprisindex** – Använd baskonsumentprisindexvärdet för eskaleringsberäkningen.</li></ul> |
| **Radrutnät** | |
| Rabatt | <p>Ställ in kryssrutan för att ange om ändringen av beloppet är en eskalering eller rabatt:</p><ul><li>**Markerad** – Ändringen tillämpar en rabatt på faktureringsplanen eller raden i faktureringsplanen.</li><li>**Avmarkerad** – Ändringen tillämpar en eskalering på en faktureringsplan eller en tidsplanrad.</li></ul><p>Inställningen för denna kryssruta kan inte ändras för artiklar som använder funktionen för icke-fakturerade intäkter. Dessutom kan rabatter inte tillämpas på artiklar som använder intäktsdelning.</p> |
| Startdatum | Välj startdatum för eskalering eller rabatt. |
| Frekvens | Välj frekvens för eskalering eller rabatt: **Ingen**, **Månadsvis**, **Kvartalsvis**, **Halvårsvis** eller **Årligen**. |
| Procentsats | Ange procentandel för eskalering eller rabatt. |
| Belopp | Ange belopp för eskalering eller rabatt. |
| Schema för konsumentprisindex | Välj den tidsplan för konbsumentindex som används för beräkningarna. |
| Slutdatum | <p>Välj slutdatum för eskalering eller rabatt.</p><p>**Obs!** Detta fält är obligatoriskt för artiklar där funktionen för icke-fakturerad intäkt används.</p> |
| Nummer på periodiseringsplanen | <p>Periodiseringens tidsplannummer.</p><p>Detta fält är endast tillgängligt när sidan öppnas från en rad i en faktureringstiplan.</p> |
| Journalbatchnummer | <p>Journalbatchnumret.</p><p>Detta fält är endast tillgängligt när sidan öppnas från en rad i en faktureringstiplan.</p> |
| Totalt rabattbelopp | <p>Summan av rabattbeloppen för alla rader i rutnätet.</p><p>Detta fält är endast tillgängligt när sidan öppnas från en rad i en faktureringstiplan.</p> |
| Aktuellt belopp för kortfristig icke-fakturerad intäkt | <p>Aktuellt belopp för kortfristig icke-fakturerad intäkt.</p><p>Detta belopp visas när en kortsiktig periodiseringsmetod har valts på sidan **Återkommande faktureringsparametrar för kontrakt** och kontona för radartikeln ställs in på sidan **Inställningar för icke-fakturerade intäkter**.</p> |
| Aktuellt belopp för långfristig icke-fakturerad intäkt | <p>Aktuellt belopp för långfristig icke-fakturerad intäkt.</p><p>Detta belopp visas när en kortsiktig periodiseringsmetod har valts på sidan **Återkommande faktureringsparametrar för kontrakt** och kontona för radartikeln ställs in på sidan **Inställningar för icke-fakturerade intäkter**.</p> |

## <a name="proration-examples"></a>Exempel på proportionell fördelning

Beräkningar för proportionell fördelning kan baseras på antalet dagar eller antalet månader. Metoden som används för beräkningen av proportionell fördelning ställs in på sidan **Faktureringsparametrar för återkommande kontrakt**. Metoden för proportionell fördelning påverkar hur beloppen beräknas för en faktureringstidsplan i följande situationer:

- Initial framställning
- Tillämpning av eskalering eller rabatt
- Uppsägning
- Placering eller borttagning av spärr
- Tillägg av support eller förnyelse

Metoden för proportionell fördelning påverkar också beräkningarna i rapporten om månatlig återkommande intäkt (MRR).

### <a name="example-1"></a>Exempel 1

Årsbeloppet för en faktureringsplan är 5 000 dollar. Startdatumet är den 12 augusti 2019 och slutdatumet är den 22 december 2019. Faktureringsfrekvensen är årlig. Det beräknade beloppet beräknas på följande sätt, beroende på om den dagliga eller månatliga beräkningsmetoden används:

- **Dagligen**

    - *Antal dagar* = *Slutdatum* – *Startdatum* + 1 = 133 dagar
    - *Antal dagar under året* = 11 augusti 2020 – 12 augusti 2019 + 1 = 366 dagar
    - *Proportionerligt fördelat belopp* = 5 000 &times; (133 &divide; 366) = 1 816,94

- **Månatlig**

    - *Startmånadsandel* = (31 – 12 + 1) &divide; 31 = 20 &divide; 31
    - *Mellanmånader* = 3
    - *Slutmånadsandel* = 22 &divide; 31
    - Proportionerligt fördelat belopp = 5 000 &divide; 12 &times; \[(20 &divide; 31) + 3 + (22 &divide; 31)\] = 1 814,52

### <a name="example-2"></a>Exempel 2

Årsbeloppet för en faktureringsplan är 12 000 dollar. Startdatumet är den 1 augusti 2019 och slutdatumet är den 31 december 2019. Faktureringsfrekvensen är årlig. Det proportionellt fördelade beloppet beräknas på följande sätt, beroende på om den dagliga eller månatliga beräkningsmetoden används:

- **Dagligen**

    - *Antal dagar* = *Slutdatum* – *Startdatum* + 1 = 153 dagar
    - *Antal dagar under året* = 31 juli 2020 – 1 augusti 2019 + 1 = 366 dagar
    - *Proportionerligt fördelat belopp* = 12 000 &times; (153 &divide; 366) = 5 016,39

- **Månadsvis (Hel månad)**

    - *Antal månader* = 5
    - *Totalt antal månader* = 12
    - *Proportionerligt fördelat belopp* = (12 000 &times; 5) &divide; 12 = 5 000

## <a name="reversing-a-period-billing"></a>Återföra en periodfakturering

I det här exemplet finns det bara en rad i en faktureringstidsplan:

- Faktureringen utförs månadsvis i 12 månader från januari till december.
- Fakturor har skapats för alla perioder upp till och med april.

Du vill återföra fakturan för faktureringsperioden i april.

Om ingen försäljningsfaktura ännu har skapats för faktureringsperioden för april kan du ta bort försäljningsordern. I detta fall tas statusen **Fakturerad** bort för detaljen. Eftersom en faktura har skapats för faktureringsperioden kan statusen **Fakturerad** emellertid inte avmarkeras för detaljen. Om du vill återföra faktureringen för april måste du därför skapa en motinställning av kreditfakturan för raden.

1. På sidan **Alla faktureringsplaner** skapar du en tidsplansrad för samma artikel.
2. Ändra värdet för **Kvantitet** för artikeln till det negativa värdet för den ursprungliga kvantiteten.
3. Ställ in fältet **Faktureringsfrekvens** på **En gång**.
4. Uppdatera start- och slutdatum så att dessa matchar datumen för faktureringsdetaljraden som du vill skapa en kreditfaktura för. För detta exempel anger du startdatumet till 1 april 2019 och slutdatumet till 30 april 2019.
5. Spara ändringarna.
6. Öppna sidan **Generera faktura** och skapa försäljningsordern som har kreditfakturan för den angivna perioden.
7. Tillval: Bokför fakturan.

När du granskar raderna för faktureringsplanen ser du att den nya raden har en länk till kreditfakturan. Ursprungsraden kommer fortfarande att ha en länk till den ursprungliga aprilfakturan.

## <a name="split-item-group-examples"></a>Exempel på delartikelgrupp

I detta exempel används följande inställningar:

- På sidan **Faktureringsparametrar för återkommande kontrakt** väljs **Dela efter artikelgrupp**, och fältet **Unik tidsplanstyp** anges som **Kund**.
- Tre artikelgrupper har skapats: **PREFIX**, **DATAHUB** och **SPP**.
- Kundkonto US-001 har flera faktureringsscheman där artikelgruppen är PREFIX eller DATAHUB.
- Kundkonto US-002 har flera faktureringsscheman där artikelgruppen är PREFIX eller SPP.

| Fakturaschemanummer | Kund | Artikelgrupp |
|---|---|---|
| SCH001 | US-001 | PREFIX |
| SCH002 | US-001 | DATAHUB |
| SCH003 | US-002 | PREFIX |
| SCH004 | US-002 | SPP |

Kund US-001 köper en förnyelseartikel som tillhör PREFIX-artikelgruppen. Den här transaktionen är en ny försäljningsorder.

| Försäljningsorder # | Kund | Huvudartikel | Förnyelseartikel | Förnyelseartikelgrupp | Fakturaschemanummer |
|---|---|---|---|---|---|
| SO0001 | US-001 | D0001 | D0002 | PREFIX | SCH001 |

När fakturan för försäljningsordern bokförs läggs förnyelseartikeln till i det befintliga faktureringsschemat (ISO001) för kunden. Denna faktureringstidsplan använder artikelgruppen PREFIX. Alla förnyelseartiklar som ingår i samma artikelgrupp förs in i samma faktureringstidsplan.

**Siduvud**
 
| Fakturaschemanummer | Kund | Artikelgrupp |
|---|---|---| 
| SCH001 | US-001 | PREFIX |

**Rad**

| Fakturaschemanummer | Kund | Artikelgrupp |
|---|---|---|
| SCH001 | US-001 | D0002 |

Kund US-001 köper nu en förnyelseartikel som tillhör SPP-artikelgruppen. Den här transaktionen är en ny försäljningsorder.

| Försäljningsorder # | Kund | Huvudartikel | Förnyelseartikel | Förnyelseartikelgrupp | Fakturaschemanummer |
|---|---|---|---|---|---|
| SO0002 | US-001 | D0003 | D0004 | SPP | |

För närvarande har US-001 inget faktureringsschema som använder artikelgruppen SPP. Därför skapas en ny faktureringstidsplan.

**Siduvud**

| Fakturaschemanummer| Kund | Artikelgrupp |
|---|---|---|
| SCH005 | US-001 | SPP |

**Rad**

| Fakturaschemanummer | Kund | Artikelgrupp |
|---|---|---|
| SCH005 | US-001 | D0004 |

### <a name="multiple-billing-schedules-for-the-same-end-user-and-customer"></a>Flera faktureringstidsplaner för samma slutanvändare och kund

I detta exempel används följande inställningar:

- På sidan **Faktureringsparametrar för återkommande kontrakt** väljs **Dela efter artikelgrupp**, och fältet **Unik tidsplanstyp** anges som **Slutanvändare**.
- På sidan **Slutanvändare** ställs följande kund- och slutanvändarrelation in.

    | Kundkonto | Konto för slutanvändare |
    |---|---|
    | US-001 | US-221 |

Flera faktureringstidsplaner skapas för kund- och slutanvändarkombinationen. Eftersom **Dela efter artikelgrupp** har valts på sidan **Faktureringsparametrar för återkommande kontrakt** kan flera faktureringstidsplaner skapas för samma kund- och slutanvändarrelation.

| Fakturaschemanummer | Kund | Konto för slutanvändare | Rubrikartikelgrupp |
|---|---|---|---|
| SCH005 | US-001 | US-221 | IG1 |
| SCH006 | US-001 | US-221 | IG2 |
| SCH007 | US-001 | US-221 | IG3 |

På sidan **Artikelkonfiguration** skapar du relationer för support och förnyelseartiklar.

| Artikelkod | Artikelrelation | Supportartikel | Förnyelseartikel | Förnyelseartikelgrupp |
|---|---|---|---|---|
| Register | D001 | ITEM27 | D007 | IG1 |
| Register | D002 | ITEM28 | D005 | IG2 |
| Register | D003 | ITEM29 | D006 | IG3 |

Nu skapar du en försäljningsorder för kunden US-001. Denna försäljningsorder innehåller artiklar från sidan **Artikelinställningar**. När du skapar försäljningsordern öppnar du sidan **Support- och förnyelseproess**, konfigurerar fältet **Slutanvändarkonto** och annan erforderlig information för förnyelseartikeln.

När fakturan för transaktionen skapas och bokförs, skapas olika faktureringstidsplanber för kund/slutanvändar- och artikelgruppskombinationen. Fler än en rad på samma försäljningsorder kan tilldelas samma faktureringstidsplan.

| Försäljningsorder # | Kund | Konto för slutanvändare | Huvudartikel | Supportartikel | Förnyelseartikel | Fakturaschemanummer |
|---|---|---|---|---|---|---|
| SO0001 | US-001 | US-221 | D001 | ITEM27 | D007 | SCH005 |
| SO0001 | US-001 | US-221 | D002 | ITEM28 | D005 | SCH006 |
| SO0001 | US-001 | US-221 | D003 | ITEM29 | D006 | SCH005 |
