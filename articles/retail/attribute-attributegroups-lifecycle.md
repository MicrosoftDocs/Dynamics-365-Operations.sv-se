---
title: Attribut och attributgrupper
description: "Det här avsnittet beskriver hur du använder attribut för att tillhandahålla ett sätt att beskriva en produkt och dess egenskaper med hjälp av anpassade fält."
author: ashishmsft
manager: AnnBe
ms.date: 04/28/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2018-03-30
ms.dyn365.ops.version: Application pdate 5, AX 8.0
ms.translationtype: HT
ms.sourcegitcommit: 190d0b59ad2e232b33b3c0d1700cbaf95c45aeca
ms.openlocfilehash: 76b78a898a619f1bc7faa4749e5380a0ccfef527
ms.contentlocale: sv-se
ms.lasthandoff: 01/04/2019

---

# <a name="attributes-and-attribute-groups"></a>Attribut och attributgrupper

[!include [banner](includes/banner.md)]

*Attribut* ger ett sätt att ytterligare beskriva en produkt och dess egenskaper med hjälp av anpassade fält (t.ex **minnesstorlek**, **hårddiskkapacitet**, **är Energy star-kompatibel**och så vidare). I Microsoft Dynamics 365 for Finance and Operations kan attribut förknippas med olika Retailsenheter, såsom produktkategorier och butikskanaler och standardvärden kan ställas in för dem. Produkter ärva deras attribut och värden för de attribut som när de är associerade med produktkategorier eller butik. Standardvärdena kan åsidosättas på den enskilda produkten, vid butik nivå eller i en återförsäljare katalog.

En normal TV-produkt kan till exempel ha följande attribut.

| Kategori   | Attribut                | Tillåtna värden          | Standardvärde |
|------------|--------------------------|-----------------------------|---------------|
| TV & Video | Märke                    | Något giltigt varumärkesvärde       | Inga          |
| TV         | Skärmstorlek              | 20-80 tum                | Inga          |
|            | Vertikal lösning      | 480i, 720p, 1080i, eller 1080p | 1080p         |
|            | Skärmuppdateringsfrekvens      | 60hz, 120hz, eller 240hz       | 60hz          |
|            | HDMI-ingångar              | 0–10                        | 3             |
|            | DVI-ingångar               | 0–10                        | 1             |
|            | Kompositingångar         | 0–10                        | 2             |
|            | Komponentingångar         | 0–10                        | 1             |
| LCD        | 3D Ready                 | Ja eller Nej                   | Ja           |
|            | 3D aktiverat               | Ja eller Nej                   | Nr            |
| Plasma     | Drifttemperatur från      | 32–110 grader              | 32            |
|            | Drifttemperatur till        | 32–110 grader              | 100           |
| Projektion | Projektionrörgaranti | 6, 12, eller 18 månader         | 12            |
|            | \# av antalet projektionsrör   | 1–5                         | 3             |

## <a name="attributes-and-attribute-types"></a>Attribut och attributtyper

Attribut baseras på *attributtyper*. Attributtypen identifierar den typ av data som kan anges för ett visst attribut. Finance and Operations stöder för närvarande följande attributtyper:

- **Valuta** – Denna attributtyp stöder ett valutavärde. Detta kan avgränsas (dvs, det kan stödja ett värdeintervall), eller det kan lämnas öppet.
- **DatumTid** -– Denna typ stödjer datum- och tidsvärden. Den kan begränsas eller lämnas öppen.
- **Decimal** – Denna typ stöder numeriska värden som inkluderar decimaler. Den stöder dessutom en måttenhet. Den kan begränsas eller lämnas öppen.
- **Heltal** – Denna typ stöder ett siffervärde. Den stöder dessutom en måttenhet. Den kan begränsas eller lämnas öppen.
- **Text** – Denna attributtyp stöder ett textvärde. Den stöder dessutom en fördefinierad uppsättning av möjliga värden (dvs en *uppräkning*).
- **Boolesk** – Denna typ stöder ett binärt värde (**sant** eller **falskt**).
- **Referens** – denna typ refererar till andra attribut.

### <a name="set-up-attribute-types-in-finance-and-operations"></a>Ställ in attributtyper i Finance and Operations

1. Logga in på Finance and Operations backoffice-klient som marknadsföringschef (butik).
2. Gå till **Produktinformationshantering** &gt; **Inställningar** &gt; **Kategorier och attribut** &gt; **Attributtyper**.
3. Skapa två attributtyper i typen **Text**, ange alternativet **fast lista** till **Ja** och lägg sedan till en lista över värden:

    - Namnge en attributtyp **Linsform** och lägg till följande värden: **ellips**, **ruta** och **rektangel**.
    - Namnge den andra attributtypen **Solglasögonmärke** och lägg till följande värden: **Ray ban**, **Aviator** och **Oakley**.

![Attributtyper](media/AttributeType.png)

### <a name="set-up-an-attribute-in-finance-and-operations"></a>Ställ in en attributtyp i Finance and Operations

1. Logga in på backoffice-klienten som marknadsföringschef (butik).
2. Gå till **Produktinformationshantering** &gt; **Inställningar** &gt; **Kategorier och attribut** &gt; **Attribut**.
3. Skapa ett attribut med namnet **lins**.
4. Ange fältet **attributtyp** till **linsform**.

![Attribut](media/Attribute.png)

## <a name="attribute-metadata"></a>Attributmetadata

*Attributets metadata* låter dig välja alternativ för att ange hur attributen för varje produkt ska fungera. Du kan till exempel ange om attribut krävs eller inte, om de kan användas för sökning och om de kan användas som filter.

För butiksprodukter kan attributets metadatainställningar åsidosättas på kanalnivå. Den här funktionen kommer att diskuteras senare i det här avsnittet.

Som du kanske märker innehåller sidan **Attribut** kommandon relaterade till attributmetadata. Under **Attributmetadata för butik**, påverkar ett alternativ som heter **”kan förfinas”** beteendet för attributvärden i butikskassor (POS) eller sättet som systemet hanterar dessa attributvärden. Endast attribut där du kan ställa in alternativen **”kan förfinas”** till **”Ja”** kommer att visas för förfining eller filtrering av produkter i butikskassan.

Nedan följer de återstående alternativen för attributmetadata på sidan **Attribut**:

- Sökbart
- Hämtningsbart
- Kan få förfrågningar
- Sorteringsbart
- Tillåt flera värden
- Ignorera skiftläge och format
- Slutför matchning

De här alternativen var ursprungligen avsedda till att förbättra sökfunktionen för onlinebutiken. Även om Finance and Operations inte inkluderar skyltfönster online, inkluderar den eCommerce Publishing Software Development Kit (SDK). Kunderna kan använda denna SDK för att lägga in produkter i ett valfritt sökindex. Även om produktdata importeras bör kunder ändå kunna skilja mellan sökbar data, data som kan efterfrågas och så vidare. På så sätt kan de skapa ett optimalt index för att se till att de bara indexerar attribut som *enligt deras mening* bör indexeras.

Information om syftet med dessa återstående alternativ finns i [Översikt över sökschemat i SharePoint 2013 Server](https://technet.microsoft.com/library/jj219669.aspx).

## <a name="filter-settings-for-attributes"></a>Filterinställningar för attribut

Filterinställningar för attribut låter dig definiera hur filter för attribut visas i butikskassa. För att få tillgång till filterinställningar för ett attribut, på sidan **attribut** i Finance and Operations, välj attributet och i åtgärdsfönstret markerar du **filterinställningar**.

Sidan **Visningsinställningar för filter** innehåller följande fält:

- **Namn** – Som standard i det här fältet är som standard namnet på attributet. Du kan dock ändra värdet.
- **Displayalternativ** – Följande alternativ finns tillgängliga för bearbetningsordning:

    - **Enstaka värde** – det här alternativet är tillgängligt för följande attributtyper: **boolesk**, **valuta**, **decimal**, **heltal** och **Text**. Detta alternativ tillåter val av enstaka värden för dessa attribut i klienten för förfining.
    - **Flera värden** – det här alternativet är tillgängligt för följande attributtyper: **valuta**, **decimal**, **heltal** och **text**. Detta alternativ tillåter val av flera värden för detta attribut i klienten för förfining.

- **Displaykontroll** – Följande alternativ finns tillgängliga för bearbetningsordning:

    - **Lista** – Det här alternativet är tillgängligt för alla attributtyper.
    - **Intervall** – det här alternativet är tillgängligt för följande attributtyper: **valuta**, **decimal** och **heltal**.
    - **Reglage** – det här alternativet är tillgängligt för följande attributtyper: **valuta**, **decimal** och **heltal**.
    - **Reglage med lister** – det här alternativet är tillgängligt för följande attributtyper: **valuta**, **decimal** och **heltal**.

- **Tröskelvärde** – inställningen krävs om du markerade **intervall** som displaykontrolltyp. Du kan definiera värden genom att använda ett semikolon (;) som avgränsare.

    För exempelvis filter som **väskvolym** kan ett tröskelvärde vara **10; 20; 50; 100; 200; 500; 1000; 5000**. I detta fall kommer kassan att visa följande intervall. Alla områden som inte har några produkter i resultatet är nedtonade.

    - Mindre än 10
    - 10 – 20
    - 20 – 50
    - 50 – 100
    - 100 – 200
    - 200 – 500
    - 500 eller mer

![Filterinställningar för attribut.](media/AttributeFilterSettings.PNG)

## <a name="attribute-groups"></a>Attributgrupper

När attribut har definierats, kan de tilldelas till attributgrupper. En *attributgrupp* används för att gruppera attributen för en komponent eller en subcomponent i en modell för produktkonfiguration. Ett attribut kan inkluderas i fler än en attributgrupp. Attributgrupper kan hjälpa användare att konfigurera produkter, eftersom de olika valen är arrangerade i ett visst sammanhang. Attributgrupper kan tilldelas butikskategorier eller butikskanaler.

Du kan också ange standardvärden för attribut som ingår i en attributgrupp. Exempelvis kan du lägga till ett attribut för färg till en attributgrupp och markera **blå** som standardattributvärde. I det här fallet, när attributgruppen läggs till en butiksprodukt som inkluderar färg som ett av attributen, visas **blå** som standardfärg för den produkten.

![Attributgrupper](media/AttributeGroup.png)

### <a name="create-an-attribute-group"></a>Skapa attributgrupper

1. Logga in på backoffice-klienten som marknadsföringschef (butik).
2. Gå till **Produktinformationshantering** &gt; **Inställningar** &gt; **Kategorier och attribut** &gt; **Attributgrupper**.
3. Skapa en attributgrupp med namnet **Modesolglasögon**.
4. Lägg till följande attribut: **linsform** och **solglasögonmärke**.

### <a name="assign-attribute-groups-to-retail-categories"></a>Tilldela attributgrupper till butikskategorier

En eller flera attributgrupper kan kopplas till kategorinoder i följande typer av butikskategorihierarkier: butiksprodukthierarki, kanalens navigeringskategorihierarki och tillägg för produktkategorihierarki När produkterna har kategoriserats, de ärver de attribut som ingår i attributgrupper.

![Produkthierarki (butik) – produktattributgrupper](media/AGRetailProdHierarchy.PNG)

Gör så här om du vill tilldela attributgrupper till kategorier i produkthierarki (butik).

1. Logga in på backoffice-klienten som marknadsföringschef (butik).
2. Gå till **Butik**&gt;**Kategori- och produkthantering**&gt;**Produkthierarki (butik)**.
3. Välj **Modenavigeringshierarkin**.
4. Under **Herrkläder**markerar du kategorin **Byxor** och sedan på snabbfliken **Produktattributgrupper** lägger du till en attributgrupp med namnet **Herrbälten**.
5. Välj kategorin **Modesolglasögon** och kontrollera de nya attributen i attributgruppen **Modesolglasögon** genom att markera **Visa attributen**.

    Attributgruppen ska visa den nya attributen **Linsform** och **Solglasögonmärke**.

6. Under **Herrkläder**markerar du kategorin **Byxor** och kontrollerar attributen för attributgruppen **Herrbälten** genom att markera **Visa attributen**.

    Attributgruppen bör visa attributen **Herrbältemärken**, **Beltesmaterial** och **Bältesstorlek**.

> [!NOTE]
> Den här proceduren kan också användas för att tilldela attributgrupper till kategorier i kanalens navigeringskategorihierarki och tillägg för produktkategorihierarki. Använd följande sökvägar i steg 2:
>
> - **Butik**&gt;**Kategori- och produkthantering**&gt;**Navigeringskategorier för kanal**
> - **Butik**&gt;**Kategori- och produkthantering**&gt;**Ytterligare produktkategorier**.

### <a name="assign-attribute-groups-to-retail-stores"></a>Tilldela attributgrupper till butiker

En eller flera attributgrupper som kan förknippas med en eller flera butiker i butikskategorihierarkin. När produkterna har förädlats för specifika butiker, de ärver de attribut som ingår i attributgrupper.

1. Logga in på backoffice-klienten som marknadsföringschef (butik).
2. Gå till **Butik** &gt; **Kanalinställningar** &gt; **Kanalkategorier och produktattribut**.
3. Tilldela attributgrupper till Houston-kanalen:

    1. Välj kanalen **Houston**.
    2. På snabbfliken **Attributgrupp** välj **Lägg till** och sedan i fältet **namn** väljer du **SharePointProvisionedProductAttributeGroup**.
    3. Välj **Lägg till** igen och sedan, i fältet **Namn** väljer du **Herrbälten**.
    4. Välj **Lägg till** igen och sedan, i fältet **Namn** väljer du **Modesolglasögon**.

        > [!NOTE]
        > Ett alternativ låter dig ange att denna kanal ska ärva attributgrupper från sin överordnade kanal i hierarkin. Om du ställer in alternativet **Ärva** till **Ja**, ärver den underordnade noden alla attributgrupperna och alla attributen i dessa attributgrupper.

4. Aktivera attributen så att de är tillgängliga i Houston-kanalen:

    1. I åtgärdsfönstret, välj **ange attributmetadata**.
    2. Välj kategorinoden **Mode** och klicka sedan på snabbfliken **Kanalproduktattribut**, välj **Inkludera attribut** för varje attribut.
    3. Välj kategorinoden **Mode accessoarer** och välj kategorin **Modesolglasögon** och välj **Kanalproduktattribut** på snabbfliken och sedan **Inkludera attribut** för varje attribut.
    4. Välj kategorinoden **Herrkläder** och välj kategorin **Byxor** och välj **Modesolglasögon** på snabbfliken och sedan **Inkludera attribut** för varje attribut.

![Kanalkategorier och produktattribut - attributgrupper](media/CCPAttrGrp.png)

## <a name="overriding-attribute-values"></a>Åsidosätta attributvärden

Standardvärden för attribut kan åsidosättas för enskilda produkter på produktnivå. Standardvärden kan även åsidosättas för enskilda produkter i särskilda kataloger som är riktade på specifika butikskanaler.

### <a name="override-the-attribute-values-of-an-individual-product"></a>Åsidosätt attributvärdena för en enskild produkt

1. Logga in på backoffice-klienten som marknadsföringschef (butik).
2. Gå till **Butik**&gt;**Kategori- och produkthantering**&gt;**Frisläppta produkter efter kategori**.
3. Välj kategorinoden **Mode**&gt;**Modeaccessoarer**&gt;**Modesolglasögon**.
4. Välj den nödvändiga produkten i rutnätet. I åtgärdsfönstret, på fliken **Produkt**, i gruppen **Inställning**, markerar du sedan **Produktattribut**.
5. Välj ett attribut i det vänstra fönstret och uppdatera dess värde i den högra rutan.

![Produkdetaljsida – produktattributgrupper](media/ProdDetailsProdAttrValues.png)

### <a name="override-the-attribute-values-of-products-in-a-catalog"></a>Åsidosätt attributvärdena för produkterna i en katalog

1. Logga in på backoffice-klienten som marknadsföringschef (butik).
2. Gå till **Butik**&gt;**kataloghantering**&gt;**alla kataloger**.
3. Välj katalogen **Fabrikam baskatalogen**.
4. Välj kategorinoden **Mode**&gt;**Modeaccessoarer**&gt;**Modesolglasögon**.
5. På snabbfliken **Produkter** väljer du den produktkvalitet som behövs och väljer sedan **Attribut** ovanför produktrutnätet.
6. Uppdatera värden för de attribut som krävs på följande snabbflikar:

    - Delad produktmedia
    - Delade produktattribut
    - Kanalmedia
    - Kanalproduktattribut

    > [!NOTE]
    > Om delad produktmedia och delade produktattribut skapas i Finance and Operations gäller de för alla återförsäljarprodukter.

![Katalogens produktattributgrupper](media/CatalogProdAttrValues.png)

### <a name="override-the-attribute-values-of-products-in-a-channel"></a>Åsidosätt attributvärdena för produkterna i en kanal

1. Logga in på backoffice-klienten som marknadsföringschef (butik).
2. Gå till **Butik** &gt; **Kanalinställningar** &gt; **Kanalkategorier och produktattribut**.
3. Välj kanalen **Houston**.
4. På snabbfliken **Produkter** väljer du den produktkvalitet som behövs och väljer sedan **Attribut** ovanför produktrutnätet.

    > [!NOTE]
    > Om det inte finns några produkter tillgängliga, lägg till produkter genom att markera **Lägg till** på snabbfliken **Produkter** och välj sedan nödvändiga produkter i dialogrutan **lägga till produkter**.

5. Uppdatera värden för de attribut som krävs på följande snabbflikar:

    - Delad produktmedia
    - Delade produktattribut
    - Kanalmedia
    - Kanalproduktattribut

    > [!NOTE]
    > Om delad produktmedia och delade produktattribut skapas i Finance and Operations gäller de för alla återförsäljarprodukter.

