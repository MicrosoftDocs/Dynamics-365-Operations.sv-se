---
title: Inställningar för parametrar för kredithantering
description: I den här artikeln beskrivs alternativen som du kan använda för att konfigurera kredithantering efter företagets behov.
author: JodiChristiansen
ms.date: 11/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 8955518e7b5c0200d3827c1c22b7d150a09be244
ms.sourcegitcommit: fb9b6969218f2b82f0a4c72bfad75387fe00395c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/22/2022
ms.locfileid: "9799556"
---
# <a name="credit-management-parameters-setup"></a>Inställningar för parametrar för kredithantering

[!include [banner](../includes/banner.md)]

I den här artikeln beskrivs alternativen som du kan använda för att konfigurera kredithantering efter företagets behov. Du börjar använda kredithanteringsfunktioner genom att ställa in parametrarna på sidan **Parametrar för kredit och inkasso** (**kredit och inkasso \> inställningar \> parametrar för kredit och inkasso**).

## <a name="credit-parameters"></a>Kreditparametrar

Det finns fyra snabbflikar i avsnittet **Kredit** där du kan ändra parametrarna som styr kredithanteringen: **kreditspärrar**, **kontrollpunkt för kredithantering**, **statistik för kredithantering** och **kreditgränser**. I följande avsnitt beskrivs de inställningar som är tillgängliga på varje snabbflik.

### <a name="credit-holds"></a>Kreditspärrar

- Ange alternativet **Tillåt redigering av försäljningsordervärden efter att orderspärren frisläppts** till **Nej** om du vill att bokföringsreglerna ska kontrolleras igen om försäljningsorderns värde (utökat pris) har ökat sedan försäljningsordern släpptes från den spärrade listan.
- I fältet **orsaker till annullerade order** väljer du den frisläppningsorsak som kommer att användas som standard när en försäljningsorder som hade kredithanteringsspärr annulleras.
- Ange alternativet **Kontrollera kundkreditgruppernas kreditgräns** till **JA** för att kontrollera kreditgränsen för en kundkreditgrupp när kunden på en försäljningsorder tillhör en kundkreditgrupp. Kreditgränsen för gruppen kommer att kontrolleras och om det behövs, kontrolleras kreditgränsen för kunden.
- Ange alternativet **Kontrollera kreditgräns när betalningsvillkoren ökas** till **Ja** för att kontrollera betalningsvillkoren rankning för att avgöra om betalningsvillkoren i försäljningsordern skiljer sig från standardbetalningsvillkoren för kunden. Om de nya betalningsvillkoren har en högre rangordning än de ursprungliga betalningsvillkoren placeras ordern i en kredithanteringsspärr.
- Ange alternativet **Kontrollera kreditgränsen när kvittningsrabatt höjs** till **Ja** för att kontrollera kvittningsrabattens rangordningar för att avgöra om kassarabatten på försäljningsordern skiljer sig från standardkassarabatten för kunden. Om den nya kassarabatten har en högre rangordning än den ursprungliga kassarabatten placeras ordern i en kredithanteringsspärr.
- I fältet **orsak för frisläppning av ändrade order** väljer du den frisläppningsorsak som ska användas som standard när ändrade order automatiskt släpps från kredithanteringsspärren.
- Ange alternativet **ignorera kreditgräns för förfallen spärregel när förfallodatum är tomt** till **Ja** om du vill kontrollera beteendet för regeln **Kreditgränsen förfallen**. Ställ in alternativet på **Nej** om du vill blockera en order när utgångsdatumet är tomt.
- I lagerstyrning kan inläsningar skapas när försäljningsorder registreras. Ställ in alternativet **Ta bort spärrade lastrader** till **Nej** att lämna försäljningsorderrader på lasten när en försäljningsorder är i kreditspärr. Lasten kan inte behandlas när försäljningsordern är spärrad. Ställ in alternativet till **Ja** för att ta bort försäljningsorderrader från lasten när en försäljningsorder är i kreditspärr. Lasten kan sedan bearbetas.
- Försäljningsorder kan automatiskt frisläppas från granskning av kredithantering. I fältet **orsak till frisläppning automatiskt** väljer du den frisläppningsorsak som ska användas som standard när försäljningsorder frisläpps automatiskt.
- Försäljningsorder kan automatiskt frisläppas från granskning av kredithantering. I fältet **Frisläpp automatiskt** väljer du **utan bokföring** för att frisläppa spärren på en order. Du måste köra processen som spärrar ordern manuellt. Välj **med bokföring** om du vill bokföra ordern med samma bokföringsprocess som kördes när försäljningsordern spärrades.

### <a name="credit-management-checkpoint"></a>Kontrollpunkt för kredithantering

Du kan ställa in tidsinställningen som används för att kontrollera försäljningsorder för kreditutleveranser. Snabbfliken **kontrollpunkt för kredithantering** identifierar de bokföringsprocesser för dokument som inkluderar bearbetning av kredithanteringsregler. Du kan också kontrollera kreditreglerna samtidigt som du gör en proforma-bokföring eller en fullständig bokföring av försäljningsordern. Markera kryssrutorna för att definiera de bokföringsprocesser som ska spärras om en utleverans hittas efter det att spärrningsreglerna för kredithantering har bearbetats.

Du kan även definiera antalet respitdagar innan kreditreglerna kontrolleras igen. Även om du kan ange att kredithanteringsreglerna kontrolleras vid bokföring, kontrolleras inte reglerna under det angivna antalet respitdagar. Du bekräftar t.ex. en försäljningsorder på dag 1 och du anger två respitdagar för bekräftelsesteget. I det här fallet kontrolleras inte kreditregler vid nästa bokföringssteg (t.ex. för att skapa en följesedel eller fakturering av ordern) fram till dag 4. På dag eller efter 4 kommer reglerna att kontrolleras igen när bokföringen sker och antalet respitdagar ändras till värdet som anges för nästa kontrollpunkt för bokföring.

Om du inte anger antalet respitdagar kontrolleras kreditreglerna vid varje bokföringssteg som har ställts in för att köra kredithanteringsregler. Om du släpper försäljningsordern utan att bokföra och sedan kör samma orderbearbetningssteg igen kontrolleras kreditreglerna igen. En order spärras till exempel efter en bekräftelse och du frisläpper den antingen med eller utan bokföring. I det här fallet kommer ordern att spärras igen om du bekräftar den igen. Använd respitdagar om ordern ska flyttas vidare till nästa bearbetningssteg utan att spärras igen.

> [!Note]
> Om en bokföringskontrollpunkt har en respitdag angivet, måste alla checkpunkter som markeras för bokföring ha respitdagar.

- Markera kryssrutan **bokföring** om du vill köra kredithanteringsreglerna när kontrollpunkt för bokföring som visas på raden körs. Om du inte markerar kryssrutan kommer reglerna endast att kontrolleras en gång under hela bokföringsprocessen.
- Om du markerar kryssrutan **bokföring** ska du ange antalet respitdagar som ska gå innan spärrningsreglerna kontrolleras igen. Du kan inte lägga till respitdagar om kryssrutan **bokföring** är avmarkerad.
- Markera kryssrutan **proforma** om du vill köra kredithanteringsreglerna när kontrollpunkt för proformabokföring som visas på raden körs. I de flesta fall är fältet **bokföring** inställt på **Nej** i dialogrutan som visas när en försäljningsorder bokförs.
- Om du markerar kryssrutan **bokföring** ska du ange antalet respitdagar som ska gå innan spärrningsreglerna kontrolleras igen. Du kan inte lägga till respitdagar om kryssrutan **bokföring** är avmarkerad.

### <a name="credit-management-statistics"></a>Statistik för kredithantering

Flera statistik för kredithantering inkluderas i faktarutan **Statistik över kundkredithantering** på sidan **kund**. Du måste ange flera värden som krävs för att beräkna statistiken. Ange antalet månader som ska användas för att beräkna följande värden i faktarutan **Statistik över kundkredithantering**:

1. Dagar för utestående försäljning 1
2. Dagar för utestående försäljning 2
3. Genomsnittligt saldo 1
4. Genomsnittligt saldo 2
5. Genomsnittlig kreditgräns %
6. Genomsnittlig exponering %

### <a name="credit-limits"></a>Kreditgränser

- I kredithantering visas kundkreditgränsen i kundens valuta. Du måste ange valutakurstypen för kreditgränsen i kundens valuta. I fältet **kreditgränsens valutakurstyp** väljer du den typ av valutakurs som ska användas för att konvertera den primära kreditgränsen till kundens kreditgräns.
- Ange alternativet **Tillåt manuell redigering av kreditgränser** till **Nej** om du vill förhindra att användare redigerar kreditgränser på sidan **kund**. Om det här alternativet är inställt på **Nej** kan ändringar av kundens kreditgräns endast göras genom att transaktioner för kreditgränsjusteringar bokförs.
- Ställ in alternativet **Hoppa över lagerreservationer** till **Ja**, om du vill ignorera lagerreservationer när spärregler för kredithantering kontrolleras. I det här fallet görs en kontroll av att alla kvantiteter har slutförts och att respitperioder kontrolleras oberoende av kvantiteten för lagerreservationen.
- När Kredithantering är aktiverad används inställningen av **meddelandet när kreditgränsen** överskrids för att endast bearbeta fritextfakturor. Även om meddelanden fortfarande läggs till försäljningsorder när kunderna har överskridit sin kreditgräns, blockeras inte bekräftelse, utskrift av plocklistor och följesedlar eller bokföring av fakturor.

    Kredithantering aktiveras som standard, men du kan inaktivera det. Om den är aktiverad använder du spärrreglerna och checkpointsen för kredithantering för att identifiera när kunderna har överskridit sin kreditgräns. Om det är inaktiverat läggs meddelandena till i försäljningsorder baserat på inställningen av **Meddelande när kreditgränsen överskrids** kan hjälpa dig att identifiera när kunder har överskridit sin kreditgräns.

### <a name="number-sequences-and-shared-number-sequence-parameters"></a>Nummerserier och delade parametrar för nummerserier

Ett journal-ID krävs för att bearbeta kreditgränsjusteringar. Du måste lägga till det kreditgränsjusteringsnummer som ska användas för att generera journal-ID.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
