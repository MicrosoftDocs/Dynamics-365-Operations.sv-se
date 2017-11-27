---
title: "Skapa leverantörsbetalningar med ett betalningsförslag"
description: "Detta avsnitt ger en översikt över alternativen för betalningsförslag och inkluderar några exempel som visar hur betalningsförslag fungerar. Betalningsförslag används ofta för att skapa leverantörsbetalningar eftersom frågan kan användas för att snabbt välja leverantörsfakturor för betalning, baserat på kriterier som förfallodatum och kassarabatt."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/17/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 14312
ms.assetid: 585d5b0b-1b79-4a03-ab18-528918070377
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 454a370e73e6e0d33f0aeb1ca2b3f9d6d9f8cb98
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="create-vendor-payments-by-using-a-payment-proposal"></a>Skapa leverantörsbetalningar med ett betalningsförslag

[!include[banner](../includes/banner.md)]


Detta avsnitt ger en översikt över alternativen för betalningsförslag och inkluderar några exempel som visar hur betalningsförslag fungerar. Betalningsförslag används ofta för att skapa leverantörsbetalningar eftersom frågan kan användas för att snabbt välja leverantörsfakturor för betalning, baserat på kriterier som förfallodatum och kassarabatt. 

Organisationer använder ofta betalningsförslag för att skapa leverantörsbetalningar, detta eftersom betalningsförslagfrågan kan användas för att snabbt välja leverantörsfakturor för betalning, baserat på förfallodatum, kassarabatt och andra kriterier. 

Betalningsförslagfrågan innehåller olika flikar, som var och en har olika alternativ för att välja fakturor som ska betalas. Fliken **Parameter** innehåller alternativ som en majoritet av organisationerna använder oftast. På fliken **Poster som ska ingå** kan du ange vilka fakturor eller leverantörer som ska inkluderas för betalning genom att definiera intervall för olika egenskaper. Om du till exempel bara vill betala ett visst intervall med leverantörer kan du definiera ett filter för leverantörsintervallet. Den här funktionen används ofta för att välja fakturor för en specifik betalningsmetod. Om du till exempel definierar ett filter där **Betalningsmetod** = **Check** kommer endast fakturor som har denna betalningsmetod att väljas ut för betalning, förutsatt att de även uppfyller andra kriterier som angetts i frågan. Fliken **Avancerade parametrar** innehåller ytterligare alternativ där vissa kanske inte är relevanta för din organisation. Till exempel innehåller den här fliken alternativen för att betala fakturor för centraliserade betalningar.

## <a name="parameters"></a>Parametrar
-   **Välj fakturor efter** – Fakturor inom det datumintervall som har angetts i fälten **Startdatum** och **Slutdatum** kan väljas efter förfallodatum, kassarabattdatum eller båda. Om du använder kassarabattdatumet söker systemet först sker efter fakturor som har ett kassarabattdatum mellan start- och slutdatum. Systemet avgör sedan om fakturan är valbar för kassarabatten genom att använda sessiondatumet för att säkerställa att kassarabattdatum inte redan har passerat.
-   **Från-datum** och **Till-datum** - Fakturor som har ett förfallodatum eller kassarabattdatum inom detta datumintervall, markeras för betalning.
-   **Betalningsdatumet** – detta används endast när fältet **Period** på betalningsmetoden är inställt på **totala**. Om ett datum anges, skapas alla betalningar på detta datum. Fältet **Tidigaste betalningsdatum** ignoreras.
-   **Tidigaste betalningsdatum** – Ange det tidigaste betalningsdatumet. Till exempel anger fälten **Startdatum** och **Slutdatum** ett intervall från den 1 september till den 10 september, och det tidigaste betalningsdatumet är den 5 september. I detta fall kommer samtliga fakturor med ett förfallodatum mellan den 1 september och den 5 september att få betalningsdatumet 5 september. Alla fakturor som har ett förfallodatum mellan den 5 september och den 10 september har ett betalningsdatum som motsvarar förfallodatumet för respektive faktura.
-   **Beloppsgräns** – Ange det högsta totala beloppet för alla betalningar.
-   **Skapa betalningar utan att förhandsgranska faktura** – Om du ställer in detta alternativ på **Ja** kommer betalningarna att skapas direkt på sidan **Leverantörsbetalningar**. Sidan **Betalningsförslag** hoppas över. Detta innebär att betalningarna skapas snabbare. Betalningar kan fortfarande ändras från sidan **Leverantörsbetalningar**. Alternativt kan du gå tillbaka till sidan **Betalningsförslag** genom att använda knappen **Redigera fakturor för vald betalning**.

## <a name="advanced-options"></a>Avancerade alternativ
-   **Kontrollera leverantörssaldo** – Om det här alternativet anges till **Ja**, kontrollerar systemet att ingen leverantör har ett debetsaldo innan någon faktura betalas. Om en leverantör har ett debetsaldo, skapas ingen betalning. Leverantören kan till exempel ha kreditnotor och betalningar som har bokförts men ännu inte har betalats. I så fall bör inte leverantören betalas. Istället ska kreditnotor eller betalningarna kvittas mot de utestående fakturorna.
-   **Radera negativa betalningar** - Detta alternativ fungerar annorlunda beroende på om betalningar görs för enskilda fakturor eller för summan av fakturor som uppfyller betalningsvillkoren. Detta beteende har definierats på betalningsmetoden.
-   **Betalning för varje faktura** – Om alternativet **Radera negativa betalningar** anges till **Ja**, och en oreglerade faktura och betalning finns för en leverantör, kommer endast fakturan att väljas för betalning. Den befintliga betalningen kvittas inte mot fakturan. Om alternativet **Radera negativa betalningar** anges till **Nej**, och en faktura och en betalning inte kvittas, kommer både betalningen och fakturan att väljas för betalning. En betalning skapas för betalningen, och en återbetalning (negativ betalning) skapas för betalningen.
-   **Betalning för totala antalet fakturor** – Om alternativet **Radera negativa betalningar** anges till **Ja**, och en oreglerad faktura och betalning finns för en leverantör, väljs både den oreglerade betalningen och fakturan för betalning och beloppet anges till tillsammans för att producera det totala betalningsbeloppet. Det enda undantaget förekommer, om summan leder till en återbetalning. I det här fallet varken fakturan eller betalningen har valts. Om alternativet **Radera negativa betalningar** anges som **Nej**, och en faktura och en betalning inte kvittas, väljs både betalningen och fakturan för betalning och beloppen adderas i syfte att generera det totala betalningsbeloppet.
-   **Skriv endast ut rapport** Ange det här alternativet till **Ja** för att se resultaten av betalningsförslaget i en rapport, men, utan att skapa eventuella betalningar.
-   **Inkludera leverantörsfakturor från andra juridiska personer** - Om din organisation har en centraliserad process för betalning, och betalningsförslaget skulle innehålla fakturor från andra juridiska personer som inkluderas i sökkriteriet, anger du detta alternativ till **Ja**.
-   **Föreslå leverantörsbetalning per separat juridisk person** – Om det här alternativet anges till **Ja**, skapas en separat betalning för varje juridisk person per leverantör. Leverantören för betalningen är leverantören från fakturan från varje juridisk person. Om det här alternativet anges till **Nej**, och en leverantör har fakturor som ska betalas i flera juridiska personer skapas en betalning för det totala beloppet på de markerade fakturorna. Leverantören för betalningen är leverantören i den aktuella juridiska personen. Om leverantörskontot inte finns i den aktuella juridiska personen används leverantörskontot för den första fakturan som måste betalas.
-   **Betalningsvaluta** – Det här fältet anger den valuta som alla betalningar skapas i. Om en valuta inte har definierats, betalas varje faktura i valutan för fakturan.
-   **Veckodag för betalning** Ange dagen i veckan då betalningen ska göras. Det här fältet används bara om betalningsmetoden ställs in på totala antalet fakturor för betalning på en viss dag i veckan.
-   **Motkontotyp** och **Motkonto** – Ange dessa fält för att definiera en viss kontotyp (t.ex **Redovisning** eller **Bank**) och motkonto (t.ex ett specifikt bankkonto). Betalningsmetoden för fakturan definierar standardmotkontotyp och motkonto, men du kan använda fälten för att åsidosätta standardvärdena.
-   **Ytterligare filter** – På snabbfliken **Poster som ska ingå** definierar du ytterligare intervallkriterier. Om du till exempel bara vill betala ett visst leverantörsintervall kan du definiera ett filter för leverantörsintervallet. Den här funktionen används ofta för att välja fakturor för en specifik betalningsmetod. Om du till exempel definierar ett filter där **Betalningsmetod** = **Check** kommer endast fakturor som har denna betalningsmetod att väljas ut för betalning, förutsatt att de även uppfyller andra kriterier som angetts i frågan.

## <a name="scenarios"></a>Scenarier
| Säljare | Faktura | Fakturadatum | Fakturabelopp | Förfallodatum | Kassarabattdatum | Kassarabattbelopp |
|--------|---------|--------------|----------------|----------|--------------------|----------------------|
| 3050   | 1001    | 15 juni      | 500.00         | 15 juli  | 29 juni            | 10,00                |
| 3050   | 1002    | 20 juni      | 600,00         | 20 juli  | 4 juli             | 12,00                |
| 3075   | 1003    | 15 juni      | 250.00         | 29 juni  |                    | 0,00                 |
| 3100   | 1004    | 17 juni      | 100,00         | 17 juli  | 1 juli             | 1,00                 |

Den 1 juli betalar April leverantörer. Hon använder ett betalningsförslag för att hjälpa henne att effektivare slutföra denna uppgift.

### <a name="option-1-by-cash-discount"></a>Alternativ 1: Efter kassarabatt

April väljer **Kassarabatt** som förslagstyp. Hon anger datumintervallet 26 juni till 10 juli. Följande fakturor inkluderas i förslaget:

-   1002, eftersom rabattdatumet 4 juli ligger inom intervallet för betalningsdatum.
-   1004, eftersom rabattdatumet för 1 juli ligger inom intervallet för betalningsdatum.

Följande fakturor inkluderas inte i förslaget:

-   1001, eftersom rabattdatumet 29 juni redan har förfallit, så den här fakturan är inte längre valbar för kassarabatten.
-   1003, eftersom den här fakturan inte har ett rabattdatum.

### <a name="option-2-by-due-date"></a>Förslag 2: Efter förfallodatum

April väljer **Per förfallodatum** som förslagstyp. Hon anger datumintervallet 26 juni till 10 juli. Följande fakturor inkluderas i förslaget:

-   1003, eftersom förfallodatumet 29 juli ligger inom intervallet för betalningsdatum.

Följande fakturor inkluderas inte i förslaget:

-   1001, eftersom förfallodatumet 15 juli ligger utanför intervallet för betalningsdatum.
-   1002, eftersom förfallodatumet 20 juli ligger utanför intervallet för betalningsdatum.
-   1004, eftersom förfallodatumet 17 juli ligger utanför intervallet för betalningsdatum.

### <a name="option-3-by-due-date-and-cash-discount"></a>Alternativ 3: Efter förfallodatum och kassarabattdatum

April väljer **Förfallodatum och kassarabattdatum** som förslagstyp. Hon anger datumintervallet 26 juni till 10 juli. Följande fakturor inkluderas i förslaget:

-   1003, eftersom förfallodatumet 29 juli ligger inom intervallet för betalningsdatum.
-   1002, eftersom rabattdatumet 4 juli ligger inom intervallet för betalningsdatum.
-   1004, eftersom rabattdatumet för 1 juli ligger inom intervallet för betalningsdatum.

Följande fakturor inkluderas inte i förslaget:

-   1001, eftersom rabattdatumet 29 juni redan har förfallit, så den här fakturan är inte längre valbar för kassarabatten, och förfallodatumet 15 juli ligger också utanför datumintervallet.

## <a name="country-specific-considerations"></a>Lands-/regionspecifika hänsyn
### <a name="norway"></a>Norge

#### <a name="dimension-control"></a>Dimensionskontroll

Med dimensionskontroll kan du kontrollera grupperingen av genererade rader efter betalningsförslag och ange standardinställningsdimensioner baserat på de ekonomiska dimensioner som används för de tillämpade fakturorna. Under den norska landskontexten för varje betalningsmetod finns en ekonomisk dimensionflik där du kan aktivera dimensionskontroll samt även aktivera gruppering för respektive dimension. Möjliga alternativ är:

-   Fältet **Dimensionskontroll** avaktiveras. Betalningsförslaget fungerar som för alla andra länder.
-   Fältet **Dimensions control** aktiveras utan att ytterligare definiera dimensionerna. Betalningsförslaget skapas utan att ta hänsyn till dimensioner. Den skapade transaktionen ärver inga dimensioner från den använda posten.
-   Fältet **Dimensionskontroll** aktiveras och ytterligare dimensioner aktiveras. Nu kan du definiera hur dimensionerna ska kopieras till journalen. Till exempel: • Välj kryssrutan **BusinessUnit** kryssrutan om du vill skapa ett betalningsförslag per affärsenhet för betalningsmetoden • Välj kryssrutan **CostCenter** för att skapa ett betalningsförslag per kostnadsställe för betalningsmetoden

**Obs!** Om du väljer fler än en dimension i det tredje alternativet skapas ett betalningsförslag för dimensionskombinationen.

#### <a name="bank-account-selection"></a>Val av bankkonto

Du kan definiera ett standardkonto för betalningsdebitering per betalningsmetod oavsett landskontext. Detta ska anges i betalningsrader som genereras av ett förslag. Med bankkontofunktionen kan du definiera flera debiterande bankkonton som hanteras av dimension och valuta, eller en kombination av dessa om du vill använda andra debiteringsbankkonton, beroende på respektive kombination. Du kan ställa in dessa kombinationer på sidan **Betalningsmetoder** genom att använda knappen **Bankkonton** som finns för respektive betalningsmetod med **Bokförande kontotyp** = **Bank**.




