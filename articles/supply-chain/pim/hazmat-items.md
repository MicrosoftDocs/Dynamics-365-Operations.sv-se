---
title: Farliga material i produkter, order, leveranser och laster
description: I det här avsnittet beskrivs hur du anger egenskaper för farligt material för frisläppta produkter, hur du placerar lagergränser för farliga artiklar och hur du inkluderar farligt material i en försäljningsorder, leverans eller last.
author: dasani-madipalli
manager: tfehr
ms.date: 06/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-06-10
ms.dyn365.ops.version: Release 10.0.11
ms.openlocfilehash: 3836273b1c782fe80172443f4d4c29001ccea83a
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "5007676"
---
# <a name="hazardous-materials-in-products-orders-shipments-and-loads"></a>Farliga material i produkter, order, leveranser och laster

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

I det här avsnittet beskrivs hur du anger egenskaper för farligt material för frisläppta produkter, hur du placerar lagergränser för farliga artiklar och hur du inkluderar farligt material i en försäljningsorder, leverans eller last.

## <a name="set-hazardous-material-specifications-for-products"></a>Ange specifikationer för farligt material för produkter

När du har definierat regler för farligt material och ställt in de tillhörande referenskoderna enligt beskrivningen i [ställa in farliga material](hazmat-setup.md) kan du associera den här informationen med frisläppta artiklar. Leveranstexten för leveransdokument hämtas från informationen om farligt material för de utgivna artiklarna.

Som en del av processen att associera en frisläppt artikel med ett farligt material måste du ange regelkoden och materialet. Olika regelkoder kan kopplas till en artikel, beroende på transportsätt och du kan koppla flera regler och material koder till varje artikel.

Om du vill ställa in en frisläppt produkt som ett farligt material följer du stegen nedan.

1. Gå till **Produktinformationshantering \> Produkter \> Frisläppta produkter**.
1. Välj eller skapa en produkt för att öppna dess sida **Information om frisläppt produkt**.
1. På snabbfliken **Hantera lager** ställer du in **Farligt material** till **Ja**. Den här inställningen identifierar artikeln som farligt gods och används när leveransdokumentation skrivs ut.
1. I åtgärdsfönstret, på fliken **Hantera lager** i gruppen **Regelefterlevnad** välj **Artikel för farligt material**.
1. Fyll i sidan **Artikel farligt material** för den valda artikeln med hjälp av fälten som beskrivs i följande underavsnitt.

### <a name="item-hazardous-materials-header"></a>Rubrik för artikel farligt material

I följande tabell beskrivs fälten som är tillgängliga högst upp på sidan **Artiklar om farligt material**.

| Fält | beskrivning |
|---|---|
| Artikelnummer | Den frisläppta produkt som du arbetar med. |
| Kod för föreskrift | Välj den regel för farligt material som gäller för produkten. I regeln definieras hur den utskrivna leveranstexten skapas för en artikel och de kopplade leveranssätten. Koden kan inte redigeras på den här sidan efter att den har tilldelats. Du kan dock tilldela en ny regelkod genom att välja **ny**. |
| Materialkod | (Valfritt) Välj den kod för farligt material som gäller för produkten. Materialkoden innehåller en mall som innehåller standardvärden för många andra fält på den här sidan. När du väljer en kod kopieras alla specifikationerna för det farliga materialet till den aktuella produkten. Systemet uppmanas dock först att bekräfta att artikelns materialdata ska fyllas i från materialkoden. |
| Gruppkod | (Valfritt) Välj den klassificeringsgrupp för farligt material som gäller för produkten. För fältet **Materialkod** när du väljer en kod kopieras alla specifikationerna för det farliga materialet till den aktuella produkten. Systemet uppmanas dock först att bekräfta att artikelns klassgruppdata ska fyllas i från gruppkoden. |

### <a name="descriptions-fasttab"></a><a name="hazmat-description"></a>Snabbfliken beskrivningar

Följande register beskriver de fält som är tillgängliga i snabbfliken **Beskrivningar**.

| Fält | beskrivning |
|---|---|
| Korrekt transportnamn | Ange standardbeskrivningen för materialet, enligt vad som anges i den tillämpliga förordningen. Du kan ange översättningar för det här värdet på snabbfliken **textöversättning av artikelleverans**, enligt beskrivningen i nästa avsnitt. |
| Tekniskt namn | Välj det gemensamma eller generiska namnet för materialet. Det här namnet kan vara ett namn som företaget använder internt för materialet. |
| N.O.S. | Markera den här kryss rutan om du vill ange att värdet **Korrekt leveransnamn** är ett inte annars specifikt namn (N.O.S.) för artikeln. N.O.S. leveransnamn används för grupper av liknande kemikalier och material som har specifika slutanvändningsområden, men som eventuellt inte finns med i hazmat-registret i en särskild regel. |

### <a name="item-ship-text-translation-fasttab"></a>Snabbfliken textöversättning för artikelleverans

Snabbfliken **Artikelöversättning för artikelleverans** innehåller ett rutnät som visar översättningar av värden **korrekta leveransnamn** som har definierats för det primära språket på snabbfliken **Beskrivningar**. Dessa översättningar kan användas för att leverera utskriftstext för ett eller flera ytterligare språk.

Följande register beskriver de fält som är tillgängliga i snabbfliken **Textöversättning för artikelleverans**.


| Fält | beskrivning |
|---|---|
| Språk | Språkkoden som används i raden. Till exempel betyder **pt-br** brasiliansk portugisiska. |
| Utskriven leveranstext | Det översatta värdet **Korrekt leveransnamn** på det språk som raden använder. |

Om du vill lägga till eller redigera en översättning väljer du **översättningar** ovanför rutnätet för att öppna sidan **textöversättning**. Gör sedan något av följande:

- För att lägga till en översättning väljer du **Lägg till** i åtgärdsfönstret. Välj det språk som ska läggas till och ange den översatta texten i fältet **översatt text**.
- Om du vill redigera en befintlig översättning väljer du ett målspråk i fältet **språk** och redigerar den översatta texten i fältet **översatt text** om det behövs.

### <a name="material-management-fasttab"></a><a name="material-management"></a>Snabbfliken materialhantering

Följande register beskriver de fält som är tillgängliga i snabbfliken **Materialhantering**.

| Fält | beskrivning |
|---|---|
| Klass | Välj den klass av farligt material som produkten tillhör, enligt definitionen i den regel som du följer. Du måste tilldela både en avdelning och en klass till varje produkt som innehåller farligt material. |
| beskrivning | Beskrivningen som definieras för den klass som valts i fältet **klass**. Detta fält är skrivskyddat. |
| Indelning | Välj den avdelning av farligt material som produkten tillhör, enligt definitionen i den regel som du följer. Avdelningen är en del av klassen. Du måste tilldela både en avdelning och en klass till varje produkt som innehåller farligt material. |
| Identifiering | Välj identifieringskod för farligt material. Vanligtvis baseras denna kod på en FN-standard (FN). |
| Förpackningsgrupp | Välj den förpackningsgrupp som gäller för den aktuella artikeln. |
| beskrivning | Beskrivningen som definieras för den grupp som valts i fältet **Förpackningsgrupp**. Detta fält är skrivskyddat. |
| Förpackningsbeskrivningar | Välj tillämplig kod för förpackningsbeskrivning. Den här koden refererar till en beskrivning som anger hur produkten måste vara packad. |
| Etiketter för farliga material | Välj en kod som refererar till den tillämpliga koden för farligt gods som ska användas för produkten. |
| Begränsad kvantitet | Ställ in det här alternativet på **Ja** om du vill rapportera den totala produktvikten som inkluderas i varje last och på varje lastrad. |
| Kvantitet | Ange kvantiteten av farligt material i produkten i den angivna enheten. Detta värde används för att beräkna det totala antalet farliga material för laster och leveranser som omfattar produkten. |
| Multiplikator | Ange den multiplikator som används när poängen för farligt material beräknas för varje lastrad som innehåller produkten. Detta värde anges i den tillämpliga förordningen, beroende på vilken typ av farligt material som ingår i produkten. |
| Enhet | Välj den måttenhet som ska användas för kvantiteten av farligt material i produkten, enligt vad som anges i fältet **kvantitet**. Detta värde används för att beräkna det totala antalet farliga material för laster och leveranser som omfattar produkten. |

#### <a name="how-the-hazardous-material-score-is-calculated"></a>Hur det farliga material resultatet beräknas

Flera av de värden som anges på snabbfliken **materialhantering** för en produkt används för att beräkna ett *poäng för farligt material* för varje lastrad som innehåller produkten. Poängen beräknas med följande formel:

Poäng för farlig material = *&lt;LineQty&gt;* × *&lt;HazmatQty&gt;* × *&lt;UnitConversion&gt;* × *&lt;Multiplier&gt;*

Här följer en nyckel till formeln:

- *&lt;LineQty&gt;* är den kvantitet av produkten som har angetts för en lastrad.
- *&lt;HazmatQty&gt;* är kvantiteten av farligt material som har angetts för en produkt i fältet **kvantitet** på snabbfliken **materialhantering**.
- *&lt;UnitConversion&gt;* är en konverteringsfaktor för konvertering mellan enheten som används för laddning av kvantitet och den enhet som har angetts för en produkt i fältet **enhet** på snabbfliken **materialhantering**.
- *&lt;Multiplier&gt;* är den multiplikator som har angetts för en produkt i fältet **multiplikator** på snabbfliken **materialhantering**.

Det här resultatet rapporteras för varje lastrad som innehåller en produkt där dessa värden anges. Mer information finns i [leveranser som innehåller farligt material](#hazmat-shipments) och [laster som innehåller farliga material](#hazmat-loads) senare i det här avsnittet.

#### <a name="how-the-hazardous-material-weight-is-calculated"></a>Hur det farliga materialets vikt beräknas

Laster och lastrader som innehåller produkter alternativet **begränsad kvantitet** på snabbfliken **material hantering** är inställt på **Ja** visar den totala vikten för farligt material, som beskrivs i [leveranserna som innehåller farliga material](#hazmat-shipments) och avsnittet [laster som innehåller farliga material](#hazmat-loads) senare i det här avsnittet. Hur det farliga materialets vikt beräknas med följande formel:

Vikt på farligt material = *&lt;LineQty&gt;* × *&lt;ProductWeight&gt;* × *&lt;UnitConversion&gt;*

Här följer en nyckel till formeln:

- *&lt;LineQty&gt;* är den kvantitet av produkten som har angetts för en lastrad.
- *&lt;ProductWeight&gt;* är den nettovikt som anges för produkten, i den lagerenhet som har angetts för produkten.
- *&lt;UnitConversion&gt;* är en konverteringsfaktor för konvertering mellan enheten som används för lastkvantiteten och den lagerenhet som används för *&lt;ProductWeight&gt;*.

### <a name="transport-information-fasttab"></a>Transportinformation, snabbfliken

Följande register beskriver de fält som är tillgängliga i snabbfliken **Transportinformation**.

| Fält | beskrivning |
|---|---|
| Transportkategori | Välj relaterad transportkategori. |
| Tunnelkod | Välj den relaterade tunnel begränsningskoden för artikeln. |
| Stuvning av farligt material | Välj referenskoden som används för att hantera sjötransporter när artikeln fraktas med sjötransport. |
| Flygplanstyp | Välj den begränsning för flygplan som gäller för materialet när det levereras med flygtransport. |
| Förpackning – endast lastflygplan | Baserat på det värde som du har valt i fältet **flygplanstyp** väljer du den förpackningskod som gäller när produkten endast kan levereras av lastflygplan. |
| Förpackning – passagerar- och fraktflygplan | Baserat på det värde som du har valt i fältet **flygplanstyp** väljer du den förpackningskod som gäller när produkten endast kan levereras med antingen lastflygplan eller passagerarflygplan. |
| IATA-gradering | Ställ in det här alternativet på **Ja** om du vill ange att de specifikationer för flygtransport som anges på denna snabbflik är relaterade till den internationella luftfartsföreningens (IATA) standard för farligt gods. Det här fältet är bara avsett för information. |
| Beredskap för nödsituation | Välj den kod som hänvisar till instruktioner om hur materialet hanteras i en nödsituation. |

### <a name="environmental-information-fasttab"></a>Snabbfliken miljöinformation

Följande register beskriver de fält som är tillgängliga i snabbfliken **Miljöinformation**.

| Fält | beskrivning |
|---|---|
| Miljöfarligt | Ställ in det här alternativet på **Ja** om du vill visa att produkten är miljömässigt farlig. Använd det här fältet för ditt eget rapporteringssyfte. |
| Marin förorening | Ställ in det här alternativet på **Ja** om du vill visa att produkten är en marin förorening. Använd det här fältet för ditt eget rapporteringssyfte. |

## <a name="set-stock-limits-for-hazardous-products"></a><a name="stock-limits"></a>Ställa in lagergränser för farliga produkter

Av säkerhetsskäl måste du kanske begränsa det totala beloppet för en viss produkt som kan lagras på en och samma plats. Om du vill ställa in lagergränser för en frisläppt produkt, följ dessa steg.

1. Gå till **Produktinformationshantering \> Produkter \> Frisläppta produkter**.
1. Välj en produkt för att öppna dess sida **Information om frisläppt produkt**.
1. I åtgärdsfönstret, på fliken **Hantera lager** i gruppen **Regelefterlevnad** välj **Rapporteringsdetaljer**.
1. I fälten **lagergränser för farliga produkter** och **varningsgränser för farliga produkter** ange lämpliga värden för den valda produkten.

Med rapporten **lagergräns för farligt material** kan du övervaka lagernivåerna för de farliga materialen på dina lagerställen, för att se till att de ligger kvar under de säkerhetsgränser som fastställs här. Mer information finns i [rapporten lagergräns för farligt material](hazmat-reports.md#stock-limit-report).

## <a name="sales-order-transactions-that-include-hazardous-materials"></a>Försäljningsordertransaktioner som innehåller farligt material

Om du vill inkludera en produkt som klassificeras som ett farligt material på en försäljningsorder måste du koppla det relevanta transportföretaget till försäljningsordern. Öppna försäljningsordern och på snabbfliken **Leverans**, ange fälten **Transportföretag** och **Transportföretag** efter behov.

Transportföretag är också associerat med leveranssättet. Därför måste du se till att denna information anpassas till regeln för farliga material. Det leveranssätt som anges i förordningen för farligt material måste med andra ord matcha specifikationerna i rubriken i försäljningsordern. På detta sätt kopplas förordningen, transportföretaget och tjänsten till de leveransrader som används på en försäljningsorder.

När en försäljningsorder har slutförts och är klar att levereras, kan den frisläppas till lagerstället för att indikera överföringen mellan försäljnings- och lageroperationer.

## <a name="shipments-that-include-hazardous-materials"></a><a name="hazmat-shipments"></a>Försändelser som innehåller farliga material

### <a name="view-hazardous-material-scores-for-each-shipment-line"></a>Visa poäng för farligt material för varje leveransrad

Sidan **Leveransdetaljer** för en försändelse visar de totala vikt- och poängvärden för farligt material som har beräknats för varje lastrad som ingår i den leveransen. Om du vill visa poäng och vikt följer du stegen nedan.

1. Gå till **Lagerstyrning \> Leveranser \> Alla leveranser**.
1. Välj en leverans för att öppna dess sida **Information om leverans**.
1. På snabbfliken **Lastrader** för att kontrollera raderna. För varje rad visas beräkningar av de farliga ämnena i följande fält:

    - **Poäng för farliga material** – i det här fältet visas det farliga material resultatet för lastraden. Värdet beräknas enligt de regler och värden som har fastställts för den tillämpliga förordningen och i inställningen för frisläppt produkt. Beräkningen görs i kvantiteten på lastraden och referensmultiplikatorn i [inställningar för hanteringsinställningarna](#material-management) för den frisläppta produkten.
    - **Nettovikt för begränsad kvantitet** – för produkter som har markerats som begränsade produkter på grund av innehållet av farliga material visar det här fältet den totala nettovikten av farligt innehåll som finns på lastraden. Beräkningen baseras på de produkter som har markerats som farligt material i inställningarna för frisläppt produkt. Om en artikel har markerats som en artikel med begränsad kvantitet, tar beräkningen kvantiteten på varje lastrad och refererar till vikten i [inställningar för materialhantering](#material-management) för den frisläppta produkten.

### <a name="check-for-compatibility-among-hazardous-materials-that-are-included-in-a-shipment"></a>Kontrollera kompatibilitet mellan farliga material som ingår i en leverans

Systemet kan utvärdera om alla farliga material som ingår i en leverans är lämpliga att leverera tillsammans. För att utvärdera kompatibiliteten kontrollerar systemet den samhanteringsgrupp som tilldelas varje produkt som ingår i försändelsen. Mer information finns i [Samhanteringsgrupper för farligt material](hazmat-setup.md#compatibility-groups).

Följ dessa steg för att köra kompatibilitetskontrollen.

1. Gå till **Lagerstyrning \> Leveranser \> Alla leveranser**.
1. Välj en leverans för att öppna dess sida **Information om leverans**.
1. I åtgärdsfönstret, på fliken **Leverans** i gruppen **Åtgärder** markerar du **Kompatibilitetskontroll**.

Du får ett meddelande som informerar dig om resultatet av kontrollen.

## <a name="loads-that-include-hazardous-materials"></a><a name="hazmat-loads"></a>Laster som innehåller farliga material

### <a name="view-hazardous-material-scores-for-each-load-line"></a>Visa poäng för farligt material för varje lastrad

Sidan **Lastdetaljer** för en last visar de totala vikt- och poängvärden för farligt material som har beräknats för den lasten och för varje lastrad. Om du vill visa poäng och vikt följer du stegen nedan.

1. Gå till **Lagerstyrning \> Leveranser \> Alla laster**.
1. Välj en last för att öppna sidan **Lastinformation**. (Du kan också öppna lastinformationen genom att välja en länk från en relaterad leverans.)
1. På snabbfliken **Last** kan du granska de totala poängen och vikterna för farligt material för hela lasten genom att granska följande fält:

    - **Poäng för farliga material** – i det här fältet visas det farliga material resultatet för lasten. Värdet beräknas enligt de regler och värden som har fastställts för den tillämpliga förordningen och i inställningen för frisläppt produkt. Beräkningen görs i kvantiteten som ingår i lasten och referenserna i multiplikatorn i [inställningar för hanteringsinställningarna](#material-management) för den frisläppta produkten.
    - **Nettovikt för begränsad kvantitet** – för produkter som har markerats som begränsade produkter på grund av innehållet av farliga material visar det här fältet den totala nettovikten av farligt innehåll som finns på lasten. Beräkningen baseras på de produkter som har markerats som farligt material i inställningarna för frisläppt produkt. Om en artikel har markerats som en artikel med begränsad kvantitet, tar beräkningen kvantiteten på varje last och refererar till vikten i [inställningar för materialhantering](#material-management) för den frisläppta produkten.

1. Om du vill granska resultat och vikt för enskilda rader väljer du snabbfliken **lastrader**. De värden som anges för varje rad liknar värdena som anges för hela lasten, vilket beskrivs i föregående steg.

### <a name="check-for-compatibility-among-hazardous-materials-that-are-included-in-a-load"></a>Kontrollera kompatibilitet mellan farliga material som ingår i en last

Systemet kan utvärdera om alla farliga material som ingår i en last är lämpliga att leverera tillsammans. För att utvärdera kompatibiliteten kontrollerar systemet den samhanteringsgrupp som tilldelas varje produkt som ingår i last. Mer information finns i [Samhanteringsgrupper för farligt material](hazmat-setup.md#compatibility-groups).

Följ dessa steg för att köra kompatibilitetskontrollen.

1. Gå till **Lagerstyrning \> Leveranser \> Alla laster**.
1. Välj en leverans för att öppna sidan **Lastinformation**. (Du kan också öppna lastinformationen genom att välja en länk från en relaterad leverans.)
1. I åtgärdsfönstret, på fliken **Laster** i gruppen **Åtgärder** markerar du **Kompatibilitetskontroll**.

Du får ett meddelande som informerar dig om resultatet av kontrollen.
