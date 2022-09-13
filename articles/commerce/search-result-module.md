---
title: Sökresultatmodul
description: Denna artikel handlar om moduler för sökresultat och beskriver hur du lägger till dem på webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 08/31/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.8
ms.search.industry: ''
ms.search.form: ''
ms.openlocfilehash: eeb7cd0769fcb866a3d7dcc03e8e87daf24b2c5d
ms.sourcegitcommit: 1d5cebea3e05b6d758cd01225ae7f566e05698d2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/02/2022
ms.locfileid: "9405304"
---
# <a name="search-results-module"></a>Sökresultatmodul

[!include [banner](includes/banner.md)]

Denna artikel handlar om moduler för sökresultat och beskriver hur du lägger till dem på webbsidorna i Microsoft Dynamics 365 Commerce.

I modulen Sökresultat returneras produktsökningsresultat och en lista över tillämpliga förfiningar för produkterna. Sökresultatmoduler på Dynamics 365 Commerce-webbplatser kan användas för att återge sidor för följande scenarier:

- Sökresultat som initieras av en användarsökning
- Sökresultat som visar en specifik uppsättning produkter, t.ex. "Shop similar looks" ("sök efter liknande")
- Listor med produkter som tillhör en kategori

Mer information om kategori- och sökresultatsidor finns i [Standardkategorins landningssida och översikt över sökresultatsidor](category-search-page-overview.md).

Följande illustration visar ett exempel på en sökresultatsida för en kategori på Fabrikams webbplats.

![Exempel på en sökresultatsida på webbplatsen Fabrikam.](./media/SimpleCategoryLandingDressCategory.png)

## <a name="search-results-module-properties"></a>Egenskaper för sökresultatmodul

I följande tabell visas egenskaperna för sökresultatmodulerna tillsammans med deras värden och beskrivningar.

| Egenskap | Värden | beskrivning |
|----------|--------|-------------|
| Artiklar per sida | Heltal | Antalet objekt som ska visas på respektive sida. |
| Tillåt bakåt i PDP | **Sant** eller **falskt** | Om denna egenskap är inställd på **Sant** kommer navigeringen av säkerhetsdetaljer på produktinformationssidan (PDP) länken "Tillbaka till resultat" när en användare väljer en produkt på sökresultatsidan. |
| Visa förfiningar | **Alla**, **1**, **2**, **3** eller **4** | Antalet toppförfinare som ska utvidgas när en sida läses in. Om egenskapen exempelvis är inställd på **3** expanderas de första tre förfinarna på sidan. |
| Dölj visning av kategorihierarki | **Sant** eller **falskt** | Om egenskapen har angetts som **Sant** döljs den kategorihierarki som visas på sidan. Denna egenskap ska vara **True** om du använder [modulen för navigeringssökväg](add-breadcrumb.md) för att visa kategorihierarkin.|
| Inkludera produktattribut i sökresultat | **Sant** eller **falskt** | Om egenskapen anges som **Sant** returneras attributen för produkterna i sökresultatet. Även om dessa attribut kan visas på en Commerce-webbplats krävs ett tillägg.|
| Visa anknytningspriser | **Sant** eller **falskt** | Om denna egenskap är inställd på **Sant** visas anknytningspriser för produkter i sökresultaten när en inloggad användare bläddrar på sidan. |
| Uppdatera förfiningspanel | **Sant** eller **falskt** | Om egenskapen har satts till **Sant** uppdateras förfiningspanelen när förfining väljs. I det här läget kommer vissa flervalsförfinare att bete sig som envalsförfinare när förfiningspanelen uppdateras. |

> [!IMPORTANT]
> I Commerce version 10.0.16 och senare kan konfigurationen **Visa anknytningspriser** användas för att visa anknytningspriser på sidan.
>
> I Commerce version 10.0.20 frisläppning och senare kan konfigurationen **Uppdatera förfiningspanel** användas för att uppdatera förfiningspanelen under val av förfining.

## <a name="supported-modules"></a>Moduler som stöds

Modulen för sökresultat stöder [snabbvisningsmodulen](quick-view-module.md), där användarna kan visa produktinformation och lägga till artiklar i kundvagnen från sökresultatsidan.

## <a name="add-a-search-results-module-to-a-category-page"></a>Lägg till en sökresultatmodul på en kategorisida

Följ dessa steg för att lägga till en sökresultatmodul på en kategorisida i webbplatsbyggaren.

1. Gå till **mallar** och välj sedan **ny** för att skapa en ny mall.
1. I dialogrutan **Ny mall** anger du namnet **Sökresultat** och väljer sedan **OK**.
1. I fältet **Brödtext** väljer du ellipsen (...) och sedan **Lägg till modul**.
1. I dialogrutan **Välj moduler**, välj modulen **Standardsida** och klicka sedan på **OK**.
1. I fältet **Huvud** i modulen **Standardsida** väljer du ellipsen (...) och sedan **Lägg till modul**.
1. I dialogrutan **Välj moduler**, välj modulen **Behållare** och klicka sedan på **OK**.
1. I fältet **Behållare** väljer du ellipsen (...) och sedan **Lägg till modul**.
1. I dialogrutan **Välj moduler**, välj modulen **Synlig sökväg** och klicka sedan på **OK**.
1. I egenskapsfönstret för **Navigering** anger du värdet **1** för **Min. träffar**.
1. I fältet **Behållare** väljer du ellipsen (...) och sedan **Lägg till modul**.
1. I dialogrutan **Välj moduler** väljer du modulen **Sökresultat** och sedan **OK**.
1. I egenskapsfönstret **Sökresultat** anger du värdet **1** för **Min. träffar** och anger sedan övriga erforderliga egenskaper för sökresultatmodulen. Genom att ange dessa egenskaper i mallen säkerställer du att alla anpassningar till en viss kategorisida automatiskt inkluderar dessa inställningar.
1. Välj **Slutför redigering** och välj sedan **Publicera** för att publicera mallen.
1. Gå till **Sidor** och välj **nytt sidfragment** för att skapa en ny sida.
1. I dialogrutan **Skapa en ny sida** under **Sidnamn**, ange **Kategorisida** och välj sedan **Nästa**.
1. Under **Välj en mall**, välj mallen **Sökresultat** som du skapade och välj sedan **Nästa**.
1. Under **Välj en layout** väljer du en sidlayout (till exempel **Flexibel layout**) och väljer sedan **Nästa**.
1. Under **Granska och slutför**, granska sidkonfiguration. Om du behöver redigera sidinformationen väljer du **Bakåt**. Om sidinformationen är korrekt väljer du **Skapa sida**.
1. Välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.

## <a name="inventory-aware-search-results-module"></a>Inventeringsmedveten sökresultatmodul

Sökresultatmodulen kan konfigureras för att inkludera lagerdata och ger följande erfarenheter:

- Visa lagernivåetiketter som använder produkter.
- Dölj produkter som inte finns i lager från produktlistan.
- Visa produkter som inte finns i lager i slutet av produktlistan.
- Stödja lagerbaserad produktfiltrering.

Om du vill aktivera dessa erfarenheter måste du först aktivera funktionen **Utökad identifiering av näthandelsprodukt att bli lagermedveten** och konfigurera sedan några förutsättningsinställningar i Commerce headquarters. Mer information finns i [Lagermedveten produktlistning](inventory-aware-product-listing.md).

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över standardkategorilandningssida och sida för sökresultat](category-search-page-overview.md)

[Modulbibliotek – översikt](starter-kit-overview.md)

[Snabbvisningsmodul](quick-view-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
