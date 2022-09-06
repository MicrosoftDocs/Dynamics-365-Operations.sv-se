---
title: Hantera attribut och attributsgrupper
description: I den här artikeln beskrivs hur du hanterar attribut och attributgrupper för att beskriva produkter och deras egenskaper i Microsoft Dynamics 365 Commerce.
author: ashishmsft
ms.date: 08/31/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2018-03-30
ms.openlocfilehash: aad448ea733aabdff3dc4438dcb682d49e0665c0
ms.sourcegitcommit: 09d4805aea6d148de47c8ca38d8244bbce9786ce
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/31/2022
ms.locfileid: "9386983"
---
# <a name="manage-attributes-and-attribute-groups"></a>Hantera attribut och attributsgrupper

[!include [banner](includes/banner.md)]

I den här artikeln beskrivs hur du hanterar attribut och attributgrupper för att beskriva produkter och deras egenskaper i Microsoft Dynamics 365 Commerce.

*Attribut* ger ett sätt att beskriva produkter och deras egenskaper genom användardefinierade fält. Här kan du till exempel ha minnesstorlek, hårddiskkapacitet och Energy Star-kompatibel.

Attribut som kan förknippas med olika handelsenheter, såsom produktkategorier och handelskanaler och standardvärden kan ställas in för dem. När attribut associeras med produktkategorier eller kanaler ärver produkterna dessa attribut och deras standardvärden. Standardattributvärden kan åsidosättas på den enskilda produkten, vid kanalnivå eller i en katalog.

En normal TV-produkt kan till exempel ha följande attribut.

| Kategori   | Attribut           | Tillåtna värden                        | Standardvärde |
|------------|---------------------|-------------------------------------------|---------------|
| TV & Video | Varumärke               | Något giltigt varumärkesvärde                     | Inget          |
| TV         | Skärmstorlek         | 20-85 tum                              | 55 tum     |
|            | Vertikal lösning | 4K (2160p), Full HD (1080p) eller HD (720p) | 4K (2160p)    |
|            | Skärmuppdateringsfrekvens | 60hz, 120hz, eller 240hz                     | 60hz          |
|            | HDMI-ingångar         | 0–10                                      | 3             |

## <a name="attributes-and-attribute-types"></a>Attribut och attributtyper

Attribut baseras på *attributtyper*. Attributtypen identifierar den typ av data som kan anges för ett visst attribut. Följande attributtyper stöds i Commerce:

- **Valuta** – Denna attributtyp stöder ett valutavärde. Detta kan avgränsas (dvs, det kan stödja ett värdeintervall), eller det kan lämnas öppet.
- **DatumTid** -– Denna typ stödjer datum- och tidsvärden. Den kan begränsas eller lämnas öppen.
- **Decimal** – Denna typ stöder numeriska värden som inkluderar decimaler. Den stöder dessutom en måttenhet. Den kan begränsas eller lämnas öppen.
- **Heltal** – Denna typ stöder ett siffervärde. Den stöder dessutom en måttenhet. Den kan begränsas eller lämnas öppen.
- **Text** – Denna attributtyp stöder ett textvärde. Den stöder även en fördefinierad uppsättning möjliga värden när inställningen **Fast lista** är aktiverad.
- **Boolesk** – Denna typ stöder ett binärt värde (**sant** eller **falskt**).
- **Referens** – denna typ refererar till andra attribut.

> [!NOTE]
> På grund av [begränsningar i Azure-sökindexet](/rest/api/searchservice/data-type-map-for-indexers-in-azure-search) stöds inte attributtypen **Decimal** för molnbaserade sökerfarenheter. Azure Cognitive Search stöder inte konvertering av attributtyper **Decimal** till målindexfälttyper **Edm.Double** eftersom denna omvandling skulle minska precisionen.

### <a name="set-up-attribute-types"></a>Ställ in attributtyper

Om du vill ställa in attributtyper följer du stegen i den här exempelproceduren.

1. Logga in som marknadsföringschef på Commerce headquarters.
1. Gå till **Produktinformationshantering \> Inställningar \> Kategorier och attribut \> Attributtyper**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. I fältet **Attributtypnamn** ange **Väsktyp**.
1. I fältet **Typ**, välj **Text**.
1. Ge alternativet **Fast lista** värdet **Ja**.
1. På snabbfliken **Värden** väljer du **Lägg till**.
1. På den nya raden i **Värde** ange **Satchel**.
1. Lägg till fem rader till. I fältet **Värde** för varje, ange ett annat värde: **Aftonväska**, **Portmonnä**, **Ryggsäck**, **Kurir** eller **Plånbok**.
1. Klicka på **Spara** i åtgärdsfönstret.
1. Klicka på **Ny** i åtgärdsfönstret.
1. I fältet **Attributtypnamn** ange **Solglasögonmärke**.
1. I fältet **Typ**, välj **Text**.
1. Ge alternativet **Fast lista** värdet **Ja**.
1. På snabbfliken **Värden** väljer du **Lägg till**.
1. På den nya raden i **Värde** ange **Ray ban**.
1. Lägg till två rader till. I fältet **Värde** för var och en anger du ett annat värde: **Aviator** eller **Oakley**.
1. Klicka på **Spara** i åtgärdsfönstret.

![Sidan Attributtyper.](media/AttributeType_2022Series.png)

### <a name="set-up-an-attribute"></a>Ställ in attribut

Om du vill ställa in attribut följer du stegen i den här exempelproceduren.

1. Logga in som marknadsföringschef på Commerce headquarters.
1. Gå till **Produktinformationshantering \> Inställningar \> Kategorier och attribut \> Attribut**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. Skriv **Dokument** i fältet **Väsktyp**.
1. I fältet **Attributtyp** välj **Väsktyp**.
1. Klicka på **Spara** i åtgärdsfönstret.

![Sidan Attribut.](media/Attribute_2022Series.png)

## <a name="attribute-metadata"></a>Attributmetadata

*Attributets metadata* låter dig välja alternativ för att ange hur attributen för varje produkt ska fungera. Du kan till exempel ange om attribut krävs eller inte, om de kan användas för sökning och om de kan användas som filter.

För produkter kan attributets metadatainställningar åsidosättas på kanalnivå.

Attributets sida för **Attribut** innehåller flera alternativ relaterade till attributmetadata. Till exempel om du ställer in alternativet **Kan förfinas** till **Ja** under **Metadata för attribut för Commerce-kanaler** kommer attributet att visas för förfining eller filtrering av produkter på sökresultat och kategorisidor. För att konfigurera ett attribut som förfiningsbart måste du först välja **Filterinställningar** i åtgärdsfönstret och bekräfta filterinställningarna för attributet.

## <a name="filter-settings-for-attributes"></a>Filterinställningar för attribut

Filterinställningar för attribut låter dig definiera hur attributfilter ska visas i kassa. För att få tillgång till filterinställningar för ett attribut, på sidan **attribut**, i åtgärdsfönstret markerar du **filterinställningar**.

Sidan **Filterinställningar** innehåller följande fält:

- **Namn** – Som standard i det här fältet är som standard namnet på attributet. Du kan dock ändra värdet.
- **Displayalternativ** – Följande alternativ finns tillgängliga för bearbetningsordning:

    - **Enstaka värde** – det här alternativet är tillgängligt för följande attributtyper: **boolesk**, **valuta**, **decimal**, **heltal** och **Text**. Det går bara att välja ett enda värde förfinare på produktlistesidor, till exempel kategorisökning och sökresultatsidor för produkter.
    - **Flera värden** – det här alternativet är tillgängligt för följande attributtyper: **valuta**, **decimal**, **heltal** och **text**. Det gör att flera värden kan väljas för attributet i klienten, för förfining.

- **Displaykontroll** – Följande alternativ finns tillgängliga för bearbetningsordning:

    - **Lista** – Det här alternativet är tillgängligt för alla attributtyper.
    - **Intervall** – det här alternativet är tillgängligt för följande attributtyper: **valuta**, **decimal** och **heltal**.
    - **Reglage** – det här alternativet är tillgängligt för följande attributtyper: **valuta**, **decimal** och **heltal**.
    - **Reglage med lister** – det här alternativet är tillgängligt för följande attributtyper: **valuta**, **decimal** och **heltal**.

- **Tröskelvärde** – inställningen krävs om du markerade **intervall** som displaykontrolltyp. Du kan definiera värden genom att använda ett semikolon (;) som avgränsare.

    Till exempel för attributet **Väskvolym** som har attributtypen **Heltal**, kan tröskelvärdet vara **10; 20; 50; 100; 200; 500; 1000; 5000**. I detta fall kommer POS att visa följande intervall. Områden som inte har några produkter i resultatet är nedtonade.

    - Mindre än 10
    - 10 – 20
    - 20 – 50
    - 50 – 100
    - 100 – 200
    - 200 – 500
    - 500 eller mer

Filterinställningar för attribut används bara för produktattribut och kan användas för att begränsa produktsöknings- och kategorisökningsresultat. De gäller inte för kundsökning eller ordersökning, även om samma attribut kan användas för att eftersöka kund- eller orderinformation.

I standardmodulerna för Commerce finns det inget färdigt stöd för filterinställningar **Visningskontroll** som **Intervall**, **Skjutreglage** och **Reglage med lister**. Inställningarna **Intervall** och **Skjutreglage** fortsätter att stödjas för kassalösningar och **Reglage med lister** används på gamla SharePoint online butiker och fortsätter vara tillgängliga för integration av tredje part och anpassade scenarier.

Vi rekommenderar att förfiningsbara attribut har ett attribut av typen **Text** där alternativet **Fast lista** är aktiverat och att du håller listan hanterbar (upp till 100–200 unika värden). Om en förfining har 1 000 eller fler unika värden, är det lämpligare att använda ett attribut av typen **Text** där alternativet **Fast lista** inaktiveras.

Översättningar är viktiga för attributnamn och deras värden. För attribut av typen **Text** där alternativet **Fast lista** är aktiverat, kan du definiera översättningar av attributvärdena under **Attributtyp**. För varannan attributtyp kan du definiera översättningar på sidan där du definierar attributvärdena. För ett attribut av typen **Text** kan du till exempel definiera översättningar av standardvärdet på attributets attributsida **Attribut**. Om du åsidosätter standardvärdet på produktnivå, kan du emellertid definiera översättningar för attributet på sidan **Produktattribut**.

När ett attribut har markerats som refinable för en kanal ska du inte uppdatera attributtypen. I annat fall kommer du att påverka publiceringen av produktdata till sökindexet. Vi rekommenderar istället att du skapar ett nytt attribut för en ny typ av begränsare och drar tillbaka det föregående attributet genom att ta bort det från andra attributgrupper.

Sökning efter attribut stöds men hämtar endast resultat för exakta träffar på sökord. Ett **Tyg**-attribut har till exempel värdet **Cashmere bomull**. Om en kund söker efter "Kontant" kommer inga produkter som har **Cashmere bomull** att hämtas. Men om en kund söker efter "Cashmere", "Bomull" eller "Cashmere bomull", kommer produkter som har **Cashmere bomull** som tyg att hämtas.

### <a name="additional-attribute-metadata-options"></a>Ytterligare alternativ för attributmetadata

> [!NOTE]
> Dessa attribut metadata alternativ kan bara användas på äldre SharePoint nätbutik och externa integrationer. För mer information om dessa alternativ för attributmetadata finns i [Översikt över sökschemat i SharePoint Server 2013](/SharePoint/search/search-schema-overview).

Följande ytterligare alternativen för attributmetadata finns på sidan **Attribut**:

- Sökbart
- Hämtningsbart
- Kan få förfrågningar
- Sorteringsbart
- Ignorera skiftläge och format
- Slutför matchning

De här alternativen var ursprungligen avsedda till att förbättra sökfunktionen för den gamla SharePoint-baserade onlinebutiken. De gäller inte nödvändigtvis på e-handelswebbplatser eller kassaterminaler. Eftersom huvudlös integration fortsätter att stöds, är dessa alternativ tillgängliga för export av attributmetadata genom att använda Commerce programutvecklingskit (SDK). Du kan använda Commerce SDK om du vill placera produkter i ett anpassat, optimerat externt sökindex. På det här sättet kan du säkerställa att endast attribut som ska indexeras är indexerade.

## <a name="attribute-groups"></a>Attributgrupper

En *attributgrupp* används för att gruppera attributen för en komponent eller en subcomponent i en modell för produktkonfiguration. Ett attribut kan inkluderas i fler än en attributgrupp. Attributgrupper kan hjälpa användare att konfigurera produkter, eftersom de olika valen är arrangerade i ett visst sammanhang. Attributgrupper kan tilldelas kategorier eller kanaler. Du kan också ange standardvärden för attribut i en attributgrupp.

![Sidan attributgrupper.](media/AttributeGroup_2022Series.png)

### <a name="create-an-attribute-group"></a>Skapa attributgrupper

Om du vill skapa en attributgrupp följer du stegen i den här exempelproceduren.

1. Logga in som marknadsföringschef på Commerce headquarters.
1. Gå till **Produktinformationshantering \> Inställningar \> Kategorier och attribut \> Attributgrupper**.
1. Skapa en attributgrupp med namnet **Klänningskjortor**.
1. Lägg till följande attribut: **CleaningMethod**, **CollarType**, **Collection** och **Design**.

> [!NOTE]
> Visningsordningsvärdena för attributen i attributgruppen påverkar eller gäller inte förfining i sök- och kategorisökningsresultaten. De kan bara användas i scenariot för "orderattribut".

### <a name="assign-attribute-groups-to-categories"></a>Tilldela attributgrupper till kategorier

En eller flera attributgrupper kan kopplas till kategorinoder i följande typer av kategorihierarkier:

- Handelsprodukthierarki
- Kanalnavigeringshierarki för kategori
- Extra kategorihierarki för produkt

När produkter kategoriseras i kategorier som associeras med attributgrupper ärver de de attribut som ingår i dessa attributgrupper.

![Snabbflik för produktattributgrupper på sidan Commerce produkthierarki.](media/AGRetailProdHierarchy_2022Series.png)

För att tilldela attributgrupper till kategorier i Commerce-produkthierarkin, följ stegen i det här exemplet.

1. Logga in som marknadsföringschef på Commerce headquarters.
1. Gå till **Retail and Commerce \> Produkter och kategorier \> Produkthierarki och handel**.
1. Välj navigeringshierarkin **Mode**.
1. Under **Herrkläder** markerar du kategorin **Byxor** och sedan på snabbfliken **Produktattributgrupper** lägger du till en attributgrupp med namnet **Herrbälten**.
1. Välj kategorin **Modesolglasögon** och kontrollera de nya attributen i attributgruppen **Modesolglasögon** genom att markera **Visa attributen**. Attributgruppen ska visa den nya attributen **Linsform** och **Solglasögonmärke**.
1. Välj kategorin **Byxor** och kontrollerar attributen för attributgruppen **Herrbälten** genom att markera **Visa attributen**. Attributgruppen bör visa attributen **Herrbältemärken**, **Beltesmaterial** och **Bältesstorlek**.

Samma grundläggande procedur kan också användas för att tilldela attributgrupper till kategorier i kanalens navigeringskategorihierarki och tillägg för produktkategorihierarki. I steg 2 använder du dock någon av följande sökvägar, beroende på vilken hierarki du vill tilldela attributgrupper till:

- **Kanalnavigeringshierarki för kategori:** Gå till **Butik och handel \> Kategori- och produkthantering \> Navigeringskategorier för kanal**.
- **Extra kategorihierarki för produkt:** Gå till **Butik och handel \> Kategori- och produkthantering \> Ytterligare produktkategorier**.

> [!NOTE]
> Se till att du bara associerar attributgrupper i en kategorihierarki på snabbfliken **Produktattributgrupper**, inte snabbfliken **Kategoriattributvärden**. Om attributen visas på snabbfliken **Kategoriattributvärden** väljer du **Redigera kategorihierarki** i åtgärdsfönstret. Sedan på snabbfliken **Kategoriattributgrupper** väljer du kategorinoder och sedan **Ta bort**. Det finns inget stöd för hämtning av attribut per kategori via Commerce Scale Unit.

## <a name="identify-viewable-and-refinable-attributes-for-commerce-channels-for-the-default-product-collection"></a>Identifiera visningsbara och förfiningsbara attribut för Commerce-kanaler för standardproduktsamlingen

Efter att du har associerat olika attributgrupper med kategorier i olika hierarkier (Commerce produkthierarki eller kanalnavigeringskategorier) och definierat attributvärden för varje produkt, baserat på kategoriassociationen, måste du aktivera flaggan **Visa attribut på kanal** för att göra dessa attribut synliga i en specifik kanal.

1. Gå till **Butik och handel \> Kanalinställningar \> Kanalkategorier och produktattribut**.
1. Välj **Ställ in attributmetadata** och välj sedan ett attribut i det vänstra navigeringsfönstret.
1. På snabbfliken **Kanalproduktattribut** (inte snabbfliken **Kategoriattribut**), ställ in alternativet **Visa attribut på kanal** på **Ja** för att göra attributet visningsbart.
1. Om du vill att attributet också ska kunna förfinas, ställ in alternativet **Kan förfinas** till **Ja**.

### <a name="control-visibility-of-dimension-based-refiners-such-as-size-style-and-color"></a>Kontrollera synligheten hos dimensionsbaserade refiners, t.ex. storlek, stil och färg

Produktdimensioner som storlek, stil och färg är de vanligaste förfiningarna. Om du vill göra dessa produktdimensioner tillgängliga som begränsare bör du koppla en attributgrupp på kanalnivå som innehåller en referens till en attributtyp som automatiskt ärver värden från produktdimensionsvärden.

Du kan ange att produktdimensioner kan visas och kan definieras om du uppdaterar flaggor på sidan **Kanalkategorier och produktattribut**. Välj rotnoden i navigeringsfönstret och sedan på snabbfliken **Kanalproduktattribut** ställer du in alternativet **Visa attribut på kanal** till **Ja** för attributen **Storlek**, **Format** och **Färg**. Om du vill att attributen ska kunna förfinas, ställ in alternativet **Kan förfinas** till **Ja** för var och en.

![Ange attributmetadata för dimensionsförfinare.](./media/ProductDimensionRefinersMetadataSetup_2022Series.png)

För att aktivera attributen så att de är tillgängliga i den demo-databaserade Houston-kanalen, följ stegen i det här exemplet.

1. Gå till **Butik och handel \> Kanalinställningar \> Kanalkategorier och produktattribut**.
1. Välj kanalen **Houston**.
1. I åtgärdsfönstret, välj **ange attributmetadata**.
1. Välj kategorinoden **Mode** och klicka sedan på snabbfliken **Kanalproduktattribut**, välj **Inkludera attribut** för varje attribut.
1. Välj kategorinoden **Mode accessoarer** och välj kategorin **Modesolglasögon** och välj **Kanalproduktattribut** på snabbfliken och sedan **Inkludera attribut** för varje attribut.
1. Välj kategorinoden **Herrkläder** och välj kategorin **Byxor** och välj **Modesolglasögon** på snabbfliken och sedan **Inkludera attribut** för varje attribut.
1. När du har uppdaterat attributmetadata för dina avsedda attribut och förfiningar måste du spara ändringarna och köra jobbet **Publicera kanaluppdateringar**. När uppdateringarna sedan har publiceras måste du köra följande jobb: **1070** (**Kanalkonfiguration**), **1040** (**Produkter**) och **1150** (**Katalog**).

> [!NOTE]
> - Om ditt företag kräver att du ofta lägger till eller tar bort produkter i navigeringshierarkin, eller att du gör ändringar som att uppdatera visningsbeställningsvärden, lägga till nya kategorier och lägga till nya attributgrupper i kategorier, rekommenderar vi att du konfigurerar jobbet **Publicera kanaluppdateringar** att köra som ett frekvent batchjobb. Du kan också utlösa jobbet **Publicera kanaluppdateringar** manuellt och sedan Commerce Data Exchange (CDX) jobb: **1070** (**Kanalkonfiguration**), **1040** (**Produkter**) och **1150** (**Katalog**).
> - Ett alternativ **Ärva** låter dig ange att denna kanal ska ärva attributgrupper från sin överordnade kanal i hierarkin. Om du konfigurerar alternativet **Ärva** till **Ja**, ärver den underordnade noden alla attributgrupperna och alla attributen i dessa attributgrupper.
> - Om knappen **Ställ in attributmetadata** i åtgärdsfönstret inte är tillgänglig måste du kontrollera att **navigeringshierarkin** är kopplad till kanalen på snabbfliken **allmänt**.
> - Du får inte associera några attributgrupper förutom dimensionsbaserade attributgrupper på kanalnivå (till exempel under **Attributgrupper** på sidan **Kanalkategorier och produktattribut**).
> - Efter introduktionen av stöd för kundspecifika B2B-kataloger i Commerce version 10.0.27 förväntas du identifiera förfiningar och attributinställningarna för varje B2B-katalog på samma sätt som beskrivs i den här artikeln.

## <a name="override-attribute-values"></a>Åsidosätta attributvärden

Standardvärden för attribut kan åsidosättas för enskilda produkter på produktnivå. De kan även åsidosättas för enskilda produkter i särskilda kataloger som är riktade på specifika kanaler.

### <a name="override-the-attribute-values-of-an-individual-product"></a>Åsidosätt attributvärdena för en enskild produkt

Åsidosätt attributvärdena för en enskild produkt genom att följa stegen i det här exemplet.

1. Logga in som marknadsföringschef på Commerce headquarters.
1. Gå till **Butik och handel \> Kategori- och produkthantering \> Frisläppta produkter efter kategori**.
1. Välj **Mode \> Modeaccessoarer \> Modesolglasögon**.
1. Välj den nödvändiga produkten i rutnätet. I åtgärdsfönstret, på fliken **Produkt**, i gruppen **Inställning**, markerar du sedan **Produktattribut**.
1. Välj ett attribut i det vänstra fönstret och uppdatera dess värde i den högra rutan.

![Sidan produktattributvärden.](media/ProdDetailsProdAttrValues_2022Series.png)

### <a name="override-the-attribute-values-of-all-products-in-a-catalog"></a>Åsidosätt attributvärdena för alla produkterna i en katalog

Åsidosätt attributvärdena för alla produkter i en katalog genom att följa stegen i det här exemplet.

1. Logga in som marknadsföringschef på Commerce headquarters.
1. Gå till **Butik och handel \> Kataloghantering \> Alla kataloger**.
1. Välj katalogen **Fabrikam baskatalogen**.
1. Välj **Mode \> Modeaccessoarer \> Modesolglasögon**.
1. På snabbfliken **Produkter** väljer du den produktkvalitet som behövs och väljer sedan **Attribut** ovanför produktrutnätet.
1. Uppdatera värden för de attribut som krävs på följande snabbflikar:

    - Delad produktmedia
    - Delade produktattribut
    - Kanalmedia
    - Kanalproduktattribut

### <a name="override-the-attribute-values-of-all-products-in-a-channel"></a>Åsidosätt attributvärdena för alla produkterna i en kanal

Åsidosätt attributvärdena för alla produkter i en kanal genom att följa stegen i det här exemplet.

1. Logga in som marknadsföringschef på Commerce headquarters.
1. Gå till **Butik och handel \> Kanalinställningar \> Kanalkategorier och produktattribut**.
1. Välj kanalen **Houston**.
1. På snabbfliken **Produkter** väljer du den produktkvalitet som behövs och väljer sedan **Attribut** ovanför produktrutnätet.
1. Om det inte finns några tillgängliga, markera **Lägg till** på snabbfliken **Produkter** och välj sedan nödvändiga produkter i dialogrutan **lägga till produkter**.
1. Uppdatera värden för de attribut som krävs på följande snabbflikar:

    - Delad produktmedia
    - Delade produktattribut
    - Kanalmedia
    - Kanalproduktattribut

### <a name="define-variant-specific-attribute-values-and-define-multiple-values-for-product-attributes"></a>Definiera variantspecifika attributvärden och definiera flera värden för produktattribut

Om du vill definiera variantspecifika attributvärden och definiera flera värden för produktattribut följer du stegen i den här exemplet.

1. Logga in som marknadsföringschef på Commerce headquarters.
1. Gå till **Butik och handel \> Kanalinställningar \> Kanalkategorier och produktattribut**.
1. Välj kanalen **Houston**.
1. På snabbfliken **Produkter** väljer du den produktvariant som behövs och väljer sedan **Attribut** ovanför produktrutnätet.
1. Om det inte finns några tillgängliga, markera **Lägg till** på snabbfliken **Produkter** och välj sedan nödvändiga produktvarianter i dialogrutan **lägga till produkter**.
1. Uppdatera värden för de attribut som krävs på följande snabbflikar:

    - Delad produktmedia
    - Delade produktattribut
    - Kanalmedia
    - Kanalproduktattribut

#### <a name="example-of-variant-specific-attribute-configuration"></a>Exempel på variantspecifik attributkonfiguration
        
I det här exemplet är produkten **P001-Master** en fleraktivitetsprodukt som har tre varianter: **Springa**, **Gå** och **Robust**. För varje variant vill du unikt definiera värdet för attributet **Aktivitet**. På snabbfliken **Produkter** på sidan **Kanalkategorier och produktattribut** för din kanal definierar du attributvärdet **Aktivitet** för varianterna, på det sätt som visas i följande tabell.

| Variant     | Värde för aktivitetsattribut |
|-------------|--------------------------|
| P001-Master | Sport                   |
| P001-1      | Körs                  |
| P001-2      | Går                  |
| P001-3      | Vandring                 |

Om användare söker "sko" visas produkten **P001-Master** i sökresultaten. Om du har konfigurerat attributet **Aktivitet** som förfining kommer förfiningen **Aktivitet** endast att visa ett förfiningsvärde för **Sport** eftersom detta värde har definierats för attributet **Aktivitet** på produktnivån **P001-Master**.

Attribut på variantnivå ska som standard bara användas på produktinformationssidor. När du väljer en specifik produktvariant på en PDP uppdateras produktspecifikationerna på PDP för denna specifika variant.

Om begränsare ska kunna plocka upp attributvärden som definieras på produktvariantnivå måste du definiera ett attribut på produkt huvudnivå, markera kryssrutan **Tillåt flera värden** och ställa in attributtypen till **Text**.

Sedan måste du bestämma alla möjliga värden för dina produktvarianter. För attributet **Aktivitet** som används i det här exemplet kan det hända att möjliga värden inkluderar **Springa**, **Gå**, **Fotvandra**, **Vandra**, **Camping**, **Vattensporter**, och **Snösporter**.

När du har bestämt vad variantattributvärdena ska vara kan du definiera dem på produkt huvudnivå med hjälp av pipeavgränsade värden. För attributet **Aktivitet** kan du definiera attributvärdet i produkt huvudprodukten som **Running|Walking|Hiking|Trekking|Camping|Watersports|Snowsports**.

Sedan kan du definiera attributvärden för varje variant genom att ange antingen pipeavgränsade värden eller enstaka värden. För attributet **Aktivitet** kan du konfigurera en enskild produktvariant som **Running|Walking|Hiking**, **Running**, **Running|Hiking|Watersports**, etc.

När du har definierat variant attributvärdena, på sidan **Kanalkategorier och produktattribut**, i åtgärdsfönstret, välj **Publicera kanaluppdateringar** och kör sedan jobben **1150**, **1040** och **1070**.

När jobben har slutförts och sökindexet har uppdaterats ska alla förväntade värden visas i sökresultaten och i kategori bläddringsresultaten.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
