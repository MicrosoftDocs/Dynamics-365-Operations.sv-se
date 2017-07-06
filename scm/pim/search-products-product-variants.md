---
title: "Sök efter produkter och produktvarianter under orderregistrering"
description: "Använd fältet <strong>Artikelnummer </strong>om du vill söka efter produkter och produktvarianter när du manuellt skapar en försäljningsorderrad eller en inköpsorderrad.  På så sätt kan du snabbt hitta produktvarianter, när du har endast har konfigurationsträngen eller en av produktdimensionerna tillgänglig."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: MCRFullTextIndexField, MCRFullTextParameters, PurchTable, SalesTable
audience: Application User
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 248534
ms.assetid: 99dd5ce1-0029-4f06-90e7-865e6d46d86e
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 3960cc3eb9b8d488973d258db45aa0ab9f1dd988
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017


---

# <a name="search-for-products-and-product-variants-during-order-entry"></a>Sök efter produkter och produktvarianter under orderregistrering

[!include[banner](../includes/banner.md)]

[!include[Retail name](../includes/retail-name.md)]

Använd fältet <strong>Artikelnummer </strong>om du vill söka efter produkter och produktvarianter när du manuellt skapar en försäljningsorderrad eller en inköpsorderrad.  På så sätt kan du snabbt hitta produktvarianter, när du har endast har konfigurationsträngen eller en av produktdimensionerna tillgänglig.

Ibland är det inte den bästa situationen att ha för mycket av något och detta gäller särskilt om du säljer ett antal liknande produkter och du försöker att komma ihåg artikelnummer eller produktsöknamn för att hitta den rätta produkten att lägga till i en försäljningsorder. Du kan använda fältet **Artikelnummer** på en försäljningsorderrad eller en inköpsorderrad som ett sökfält. Du kan ange valfri del av ett produktnamn, nummer eller dimension och få en sökning som visar alla artiklar som matchar sökordet.

## <a name="how-search-works"></a>Hur sökningen fungerar
När du söker efter produkter eller produktvarianter är det viktigt att du förstår hur sökfunktionen hittar de produkter som matchar texten som du anger. De huvudsakliga sökreglerna vid leverans av sökresultat, är:

-   Sökresultat returnerar en matchande post som ignorerar fältet som söktexten anges i.
-   Söktexten måste finnas i den matchande posten i dess fullständiga längd.
-   En matchning kommer att inträffa även om söktexten hittas i mitten av en textsträng i den matchande posten. Den måste inte visas i början av en textsträng.
-   Söktexten behandlas som en enkel textsträng, även om den innehåller tomt utrymme.

### <a name="examples"></a>Exempel

I följande exempel används produkter och produktvarianter för att visa hur sökningen hanteras i olika scenarier. **Förutsättning:** Under**Försäljning och marknadsföring &gt; Inställning &gt; Inställningar&gt; Sökparametrar** &gt; **Söktyp** väljer du alternativet **Fullständig matchning**.

| Produkttyp     | Produktnamn    | Visa produktnummer | Artikelnummer | Inställningar |
|------------------|-----------------|------------------------|-------------|---------------|
| Specifik produkt | SpeakerMidRange | D0001                  | D0001       | Inte tillämpligt            |
| Produktvariant  | Aktiv högtalare  | D0010:::Svart:         | D0010       | 000005        |
| Produktvariant  | Aktiv högtalare  | D0010:::Vit:         | D0010       | Vit         |

Om du skriver in "högtalare" i fältet **Artikelnummer** kommer du att få alla produkter över som ett resultat i sökningen. Om du skriver ”Svart” i fältet **Artikelnummer** kommer du att få den andra produkten som ett resultat, eftersom det har texten ”Svart” i visa produktnummer. Dessa två exempel visar att sökningen inte bara är i början av fältet, utan en matchning kommer att göras även om söktexten hittas i mitten av en textsträng i den matchande posten.  

Om du skriver "05 " kommer du endast att få den andra produktvarianten som ett resultat, eftersom den har "05 "i konfigurationen. Detta visar att sökningen görs över alla aktiverade fält på sidan **Sökkriterier**.  

Om du skriver in ”05 " kommer du inte att få några resultat. Detta inträffar eftersom sökningen som letar efter hela texten har ställts in. Sökningen kommer inte att försöka hitta "hög" och sedan begränsa resultaten till de som innehåller "05".  

Du kan begränsa antalet sökresultat med hjälp av fältet **Antal resultat** på sidan **Försäljning och marknadsföring &gt; Inställningar &gt; Sök &gt; Sökparametrar**. Om du ställer in detta fält på 0 kommer alla sökresultat att returneras. Om du har ställt in den på 10 till exempel kommer den att returnera maximalt 10 sökträffar.

## <a name="configure-the-product-search"></a>Konfigurera produktsökningen
Gör på följande sätt för att konfigurera produktsökningen innan du kan använda sökfunktionen för produkt- och produktvariant. [![3 steg för att konfigurera produktsökning\_AXAppFall](./media/3-steps-to-configure-product-search_axappfall.png)](./media/3-steps-to-configure-product-search_axappfall.png)

### <a name="step-1-include-all-the-relevant-product-and-product-variant-identifiers-and-dimensions-in-the-search-criteria"></a>Steg 1: Inkludera alla relevanta produkter och produktvariantidentifierare och dimensioner i sökvillkoren

Exempel på produkt- och produktvariantidentifierare och dimensioner som du kan söka med är **Produktnamn, artikelnummer**. **visa produktnummer, konfiguration, storlek, färg, utförande, söknamn, etc.**  

Gå till sidan **Försäljning och marknadsföring &gt; Inställningar &gt; Sök &gt; Sökvillkor**. Sidan **Sökkriterier** låter dig definiera kriterier för kund, potentiell kund och produktsökning. Se till att filtrera sidan genom att använda produktsökvillkor. Detta kan du göra genom att växla till **Produkt** på sidans meny.  

Om du vill lägga till produktvisningsnumret till sökvillkoren klickar du på **Ny** på sidans meny. Då läggs en ny post till i rutnätet **Sökvillkor**. Öppna kolumnen **Fältnamn**-sökningen och välj **DisplayProductNumber**. För att lägga till produktens konfiguration till sökkriterierna skapar du en ny post i rutnätet **Sökkriterier** och väljer **configId** i kolumnen **Fältnamn**. På samma sätt skapar du en post med **Fältnamn** **InventColorId** för färgdimensionen, **InventSizeId** för storleksdimensionen och **InventStyleId** för utförandedimensionen.

### <a name="step-2-populate-the-database-table-that-is-used-for-product-search"></a>Steg 2: Fyll i databasregistret som används för produktsökning

På sidan **Sökkriterier** klickar du på knappen **Uppdatera sökdata** . I dialogrutan **Updatera sökdata** ser du till att **Källa** är inställd på **Produkt** och klickar sedan på **OK**. Systemet kommer att samla alla sökkriteriet enligt steg 1 i en tabell. Åtgärden kan ta lång tid och du kan få ett varningsmeddelande om du har väldigt många produkter och produktvarianter. Vi rekommenderar att du schemalägger ifyllning av söktabellen på batchservern vid en tidpunkt när servern inte är för upptagen.  

Innan tabellen är ifylld, kommer produktsökningen inte att ge korrekt resultat. Om du inte får några sökresultat ser du till att fylla i den här tabellen.  

Tabellen måste endast fyllas i när sökkriterierna ändras. Nyligen frisläppta produkter och varianter läggs till automatiskt i tabellen. Borttagna produkter och varianter tas bort automatiskt från tabellen.

### <a name="step-3-enable-the-lookup-for-product-search-on-sales-and-purchase-order-lines"></a>Steg 3: Aktivera uppslag för produktsökning på försäljnings- och inköpsorderrader

Du kan aktivera denna funktion, genom att gå **Försäljning och marknadsföring &gt; Inställningar &gt; Sök &gt; Sökparametrar** och ange **Aktivera uppslag för sökning** till **Ja** på fliken **Allmän**.  

För försäljningsorderradpost är standardbeteendet att öppna sidan **Produktsökning** när du börjar att skriva i fältet **Artikelnummer** och sedan trycker på tangenten **Flik**. Sidan **Produktsökning** ändrar kontexten under skapande av orderrader och kan betraktas onödigt påträngande. Om du föredrar att få sökresultaten i ett uppslag och att inte förlora kontexten under orderradposten, kan du använda sökuppslag istället. Om du söker efter en produkt eller en produktvariant, men inte väljer något i uppslaget och trycker på tangenten **Flik** kommer sidan **Produktsökning** att visas.




