---
title: Produktsamlingsmoduler
description: Det här ämnet innehåller en översikt över produktsamlingsmoduler i Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 44f78b55b8e67b7358be75aa63c40a0147507e26
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785477"
---
# <a name="product-collection-modules"></a>Produktsamlingsmoduler  

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Det här ämnet innehåller en översikt över produktsamlingsmoduler i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

Produktidentifiering är ett primärt verktyg som återförsäljare använder för att kommunicera med sina kunder på en näthandelsplats. Produktsamlingsmoduler hjälper återförsäljare att skapa övertygande kundupplevelser genom att tillhandahålla ett intuitivt visuellt gränssnitt som snabbt kan användas för att redigera produktsamlingar.

Produktsamlingsmoduler representerar fysiska produkter och tjänster på webbplatsen. En produktsamlingsmodul är vanligtvis länkad till en informationssida där kunder kan köpa en produkt eller tjänst, eller få mer information om den. 

Källorna för produktsamlingar kan vara listor av tre typer:

- Redaktionella listor med produkter som definieras manuellt i Dynamics 365 Retail som relaterade produkter för en produkt eller produktlistor
- Algoritmiska listor, till exempel listor över nya, bästsäljande eller trendbaserade produkter
- Rekommendationslistor som baseras på maskininlärning

Följande bild visar de olika typer av produktsamlingar som används på en näthandelsplats.

![Exempel på olika typer av produktsamlingar på en näthandelsplats](./media/ProductCollectionsAcrossTheSiteUseProductPlacement.png)

> [!NOTE]
> Använd alltid moduler för att visa en grupp med produkter av liknande typ eller tema.

## <a name="product-collection-modules-and-types"></a>Produktsamlingsmoduler och typer

I följande tabell beskrivs olika typer av moduler för produktsamlingar i Dynamics 365 Commerce.

| Produktsamlingsmodul  | Typ | Beskrivning |
|----------------------------|------|-------------|
| Kategoribläddring            | Redaktionellt | Den här typen av produktsamlingsmodul använder den navigeringskategorihierarki som en återförsäljare skapat för en detaljhandelskanal för att visa ett sökflöde för produkter som erbjuds i en viss webbplatskategori. |
| Sökresultat             | Sökfråga | Den här typen av produktsamlingsmodul visar en lista över produkter som bäst matchar sökfrågan som kunden har angett. |
| Relaterade produkter           | Redaktionellt | Den här typen av produktsamlingsmodul visar en lista över produkter som en inköpschef har konfigurerat som relaterade produkter i butik, för den relationstyp som författaren har valt. |
| Granskade produktlistor      | Redaktionellt | I den här typen av produktsamlingsmodul visas anpassade listor som varor och redigerare har skapat i Retail. |
| Nya                        | Algoritmiska | Den här typen av produktsamlingsmodul visar en lista över de senaste produkterna som har varit utvalda för kanaler och kataloger. |
| Bästsäljare               | Algoritmiska | Den här typen av produktsamlingsmodul visar en lista över produkter som rangordnas med det högsta antalet försäljningar. |
| Trend                   | Algoritmiska | Den här typen av produktsamlingsmodul visar en lista över de produkter som har bäst prestanda för en viss period. |
| Ofta köpta tillsammans | Artificiell intelligens/maskininlärning | Denna typ av produktsamlingsmodul använder maskininlärning för att analysera konsumenters inköpsmönster och rekommendera relaterade artiklar som ofta köps tillsammans med en viss produkt. |
| Andra gillar också           | Artificiell intelligens/maskininlärning | Denna typ av produktsamlingsmodul använder maskininlärning för att analysera konsumenters inköpsmönster och rekommendera relaterade till en viss produkt. |

## <a name="add-a-product-collection-module-to-a-category-page"></a>Lägga till en modul för produktsamling på en kategorisida

För att lägga till en modul för produktsamling på en kategorisida, följ dessa steg.

1. I Dynamics 365 Commerce gå till webbplatsen och skapa en sida som använder samma mall som din standardkategorisida.
1. I siddispositionen väljer du platsen **Undersidfot**, markerar ellipsknappen (**...**) och väljer sedan **Lägg till modul**.
1. I dialogrutan **Lägg till modul**, välj **Behållare** och klicka sedan på **OK**.
1. I behållarmodulen väljer du ellipsknappen och väljer sedan **Lägg till modul**.
1. I dialogrutan **Lägg till modul**, välj **Produktsamling** och klicka sedan på **OK**.
1. Konfigurera inställningar genom att välja en lämplig datakälla och indata för produktsamlingen.
1. Välj **Lägg till en produktlista** i egenskapsrutan för modulen produktsamling.
1. I dialogrutan **Välj konfiguration av produktlista** väljer du typ av lista, anger antalet artiklar och väljer eventuella andra alternativ som är tillgängliga för listtypen. Mer information om dessa listtyper finns i följande tabell. 
1. Välj **OK**.
1. Spara sidan och checka in den.

I följande tabell visas de listtyper som är tillgängliga för val i dialogrutan **Välj konfiguration för produktlista**.
   
| Typ                       | Beskrivning | Allmän praxis | Kontext som kan härledas från sidans kontext | En kontext som författaren kan åsidosätta sidans kontext med |
|----------------------------|-------------|------------------|-------------------------------------|-----------------------------------------------|
| Produkter efter kategori       | En lista med produkter som tillhör en given kategori. Den här kategorin bestäms antingen från sidkontexten eller det sammanhang som författaren tillhandahåller. | Utöka kategorisida, startsida, kassasida och kundvagnssida och produktsidor | Kategori | Kategori fastställd av författare |
| Relaterade produkter           | En lista över produkter som en inköpschef har konfigurerat som relaterade produkter i Retail för relationstypen. | Produktsida, kassasida och kundvagnssida, önskelistsida och kundkontosida | Produkt, relationstyp (obligatorisk)  | Produkt, relationstyp |
| Modererad                    | En anpassad lista som produkter och redigerare har skapat i Retail. | Utöka kategorisida, startsida, kassasida och kundvagnssida och produktsidor | Inte aktuellt | Listplockare |
| Algoritmiska                | <ul><li>**Ny** – en lista över de senaste produkterna som har varit utvalda för kanaler och kataloger.</li><li>**Bästsäljande** – en lista över produkter som rangordnas med det högsta antalet försäljningar.</li><li>**Trender** – en lista över produkter som är mest presterande för en viss period.</li></ul> | Startsida, utöka kategorisida och kassasida och kundvagnssida | Kategori | Kategori fastställd av författare |
| Ofta köpta tillsammans | En lista som använder maskininlärning för att analysera konsumenters inköpsmönster och rekommendera relaterade artiklar som ofta köps tillsammans med en viss produkt. | Produktsidor, och kassa- och kundvagnssidor | Produkt, kundvagn | Inkludera kundvagn |
| Andra gillar också           | En lista som använder maskininlärning för att analysera konsumenters inköpsmönster och rekommendera artiklar som är relaterade till en viss produkt. | Produktsidor, och kassa- och kundvagnssidor | Produkt, kundvagn | Inte aktuellt |

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över startpaket](starter-kit-overview.md)

[Karusellmodul](add-carousel.md)

[Innehållsrik blockmodul](add-content-rich-block.md)

[Modul för innehållsplacering](add-content-placement-modules.md)

[Behållaremodul](add-container-module.md)

[Modul för inköpsruta](add-buy-box.md)

