---
title: Produktsamlingsmoduler
description: Det här ämnet innehåller en översikt över produktsamlingsmoduler i Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 4bae9ca722c2b6e776abb0e1da9694edc8afadf8
ms.sourcegitcommit: 872600103d2a444d78963867e5e0cdc62e68c3ec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/01/2021
ms.locfileid: "5097113"
---
# <a name="product-collection-modules"></a>Produktsamlingsmoduler

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Det här ämnet innehåller en översikt över produktsamlingsmoduler i Microsoft Dynamics 365 Commerce.

Produktidentifiering är ett primärt verktyg som återförsäljare använder för att kommunicera med sina kunder på en näthandelssajt. Produktsamlingsmoduler hjälper återförsäljare att skapa övertygande kundupplevelser genom att tillhandahålla ett intuitivt visuellt gränssnitt som snabbt kan användas för att redigera produktsamlingar.

Produktsamlingsmoduler representerar fysiska produkter och tjänster på webbplatsen. En produktsamlingsmodul är vanligtvis länkad till en informationssida där kunder kan köpa en produkt eller tjänst, eller få mer information om den. 

Källorna för produktsamlingar kan vara listor av följande fyra typer:

- Redaktionella listor med produkter som definieras manuellt i Dynamics 365 Commerce som relaterade produkter för en produkt eller produktlistor
- Algoritmiska listor, till exempel listor över nya, bästsäljande eller trendbaserade produkter
- Rekommendationslistor som baseras på maskininlärning
- Anpassningslistor som stöder anpassade resultat för en kund. Kunder måste vara inloggade på näthandelssajten för att se anpassade resultat. Gästanvändare ser inte anpassade resultat. Kunder kan välja bort anpassning från sidan [sidan kontohantering](account-management.md).

Följande bild visar de olika typer av produktsamlingar som används på en näthandelssajt.

![Exempel på olika typer av produktsamlingar på en näthandelssajt](./media/ProductCollectionsAcrossTheSiteUseProductPlacement.png)

> [!NOTE]
> Använd alltid moduler för att visa en grupp med produkter av liknande typ.

## <a name="product-collection-modules-and-types"></a>Produktsamlingsmoduler och typer

I följande tabell beskrivs olika typer av moduler för produktsamlingar i Dynamics 365 Commerce.

| Produktsamlingsmodul  | Typ | Beskrivning |
|----------------------------|------|-------------|
| Kategori                   | Kategori | I den här modulen visas en lista över produkter i en kategori, enligt definitionen i den navigeringskategorihierarki som återförsäljaren skapade för en kanal. |
| Relaterade produkter           | Redaktionellt | Den här modulen visar en lista över produkter som en inköpschef har konfigurerat som relaterade produkter i handel, för den relationstyp som författaren har valt. |
| Sökresultat             | Sökfråga | Den här typen av produktsamlingsmodul visar en lista över produkter som bäst matchar sökfrågan som kunden har angett. |
| Granskade produktlistor      | Redaktionellt | Den här modulen visar anpassade listor som produkter och redigerare har skapat i Commerce. |
| Nya                        | Algoritmiska | Den här modulen visar en lista över de senaste produkterna som har varit utvalda för kanaler och kataloger. Den här listan kan visa anpassade resultat för en inloggad användare om webbplatsförfattaren väljer det alternativet. |
| Bästsäljare               | Algoritmiska | Den här modulen visar en lista över produkter som rangordnas med det högsta antalet försäljningar. Den här listan kan visa anpassade resultat för en inloggad användare om webbplatsförfattaren väljer det alternativet. |
| Trend                   | Algoritmiska | Den här modulen visar en lista över produkter som är mest presterande för en viss period. Den här listan kan visa anpassade resultat för en inloggad användare om webbplatsförfattaren väljer det alternativet. |
| Ofta köpta tillsammans | Artificiell intelligens/maskininlärning | Den här modulen använder maskininlärning för att analysera konsumenters inköpsmönster och rekommendera relaterade artiklar som ofta köps tillsammans med en viss produkt. Den här listan kan visa anpassade resultat för en inloggad användare om webbplatsförfattaren väljer det alternativet. |
| Andra gillar också           | Artificiell intelligens/maskininlärning | Den här modulen använder maskininlärning för att analysera konsumenters inköpsmönster och rekommendera artiklar som är relaterade till en viss produkt. Den här listan kan visa anpassade resultat för en inloggad användare om webbplatsförfattaren väljer det alternativet. |
| Val för dig              | Artificiell intelligens/maskininlärning | Den här modulen använder maskininlärning för att analysera inköpsmönster för den inloggade användaren och tillhandahålla anpassade rekommendationer som baseras på dessa inköpsmönster. För en gästanvändare kommer den här listan att döljas. |

## <a name="supported-modules"></a>Moduler som stöds 

Modulen för produktsamling stöder [snabbvisningsmodulen](quick-view-module.md), där användarna kan visa produktinformation och lägga till artiklar i kundvagnen från en insamlingssida för produkter.

## <a name="add-a-product-collection-module-to-a-category-page"></a>Lägga till en modul för produktsamling på en kategorisida

För att lägga till en modul för produktsamling på en kategorisida, följ dessa steg.

1. Gå till **Sidor** och välj **nytt sidfragment** för att skapa en ny sida.
1. I dialogrutan **Välj en mall** väljer du samma mall som den som används på din standardkategorisida. Under **sidnamn**, ange ett lämpligt namn och klicka sedan på **OK**.
1. I facket **Undersidfot** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.
1. I dialogrutan **Lägg till modul**, välj modulen **Behållare** och klicka sedan på **OK**.
1. I facket **behållare** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.
1. I dialogrutan **Lägg till modul**, välj modulen **produktsamling** och sedan **OK**.  
1. Välj **Lägg till en produktlista** i egenskapsrutan för modulen produktsamling.
1. I dialogrutan **Välj konfiguration av produktlista** väljer du typ av lista, listkälla och anger antalet artiklar. Konfigurera andra tillgängliga alternativ för listtypen. Mer information om dessa listtyper finns i följande tabell. 
1. Välj **OK**.
1. Klicka på **Spara** och välj **Förhandsgranska** för att förhandsgranska sidan.
1. Välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.

I följande tabell visas de listtyper som är tillgängliga för val i dialogrutan **Välj konfiguration för produktlista**.

| Typ                       | Beskrivning | Användning | Sidkontext | Specifik kontext | Anpassning |
|----------------------------|-------------|-------|--------------|------------------|-----------------|
| Produkter efter kategori       | En lista med produkter som tillhör en given kategori. Den här kategorin bestäms antingen från sidkontexten eller det sammanhang som författaren tillhandahåller. | Den här typen av lista kan användas på alla sidor (till exempel en startsida, kategorisida, marknadsföringssida eller produktinformationssida \[PDP\]) för att marknadsföra en viss kategori av produkter. | Kategori från sidans kontext, där den är tillgänglig (till exempel en kategorisida) | Författaren kan ge en specifik kategori som kontext för listan. | Inte aktuellt |
| Relaterade produkter           | En lista över produkter som en inköpschef har konfigurerat som relaterade produkter för relationstypen i Commerce. | Den här typen av lista används främst på PDP, men den kan användas på alla sidor om en överordnad produkt tillhandahålls. | Produkt från sidan, relationstyp (obligatoriskt) | Produkten kan väljas i väljaren och relationstypen används. | Inte aktuellt |
| Modererad                    | En anpassad lista som produkter och redigerare har skapat i Commerce. | Utöka kategorisida, startsida, kassasida och kundvagnssida och produktsidor | Inte aktuellt | Inte aktuellt | Inte aktuellt |
| Algoritmiska                | <ul><li>**Ny** – en lista över de senaste produkterna som har varit utvalda för kanaler och kataloger.</li><li>**Bästsäljande** – en lista över produkter som rangordnas med det högsta antalet försäljningar.</li><li>**Trender** – en lista över produkter som är mest presterande för en viss period.</li></ul> | Startsida, utöka kategorisida och kassasida och kundvagnssida | Kategori från sidans kontext (till exempel en kategorisida) | Den kategori som bestäms av webbplatsens författare | Stöds |
| Ofta köpta tillsammans | En lista som använder maskininlärning för att analysera konsumenters inköpsmönster och rekommendera relaterade artiklar som ofta köps tillsammans med en viss produkt. | Den här typen av lista gäller endast för kundvagnssidan. | Kundvagn | Inte aktuellt | Stöds |
| Andra gillar också           | En lista som använder maskininlärning för att analysera konsumenters inköpsmönster och rekommendera artiklar som är relaterade till en viss produkt. | Den här typen av lista används på PDP för att visa produkter som andra kunder har köpt. | Produktkontext från sidan | Den produkt som etableras av webbplatsens författare | Stöds |
| Val för dig              | En lista som använder maskininlärning för att fastställa kundpreferenser. | Den här typen av lista kan användas på alla sidor. | Inte aktuellt| Inte aktuellt | Stöds | 

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över modulbibliotek](starter-kit-overview.md)

[Karusellmodul](add-carousel.md)

[Innehållsrik blockmodul](add-content-rich-block.md)

[Behållarmodul](add-container-module.md)

[Modul för inköpsruta](add-buy-box.md)

[Översikt av produktrekommendationer](product-recommendations.md)

[Snabbvisningsmodul](quick-view-module.md)
