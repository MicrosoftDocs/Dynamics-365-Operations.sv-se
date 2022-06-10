---
title: Modulen för navigeringssökväg
description: Det här avsnittet handlar om moduler för navigeringssökväg och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: aa7f6e2f2b15c3e5d89cd645b3f1cc4c83c5b8d9
ms.sourcegitcommit: ccb39767bd3430c24f4653c26560bba2cd66553c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2022
ms.locfileid: "8780344"
---
# <a name="breadcrumb-module"></a>Modul för navigeringssökväg

[!include [banner](includes/banner.md)]

Det här avsnittet handlar om moduler för navigeringssökväg och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.

Med hjälp av moduler för navigeringssökväg navigering kan du navigera på webbplatssidorna. De visas vanligtvis längst upp på sidan, under rubriken. Även om det går att lägga till moduler för navigeringssökväg på en sida, används de oftast på produktinformationssidor (PDP), för att visa produktkategorihierarki och ett snabbt sätt att flytta runt på en webbplats. En modul för navigeringssökväg kan också användas för att visa länken "tillbaka till resultat" när användaren öppnar ett PDP från en sökning eller en listsida. På så sätt kan användarna snabbt gå tillbaka till deras filtrerade listsidor och fortsätta handla.

På sidor som har produktkategorikontext, t.ex. PDP och kategorisidor, visar modulerna för navigeringssökväg kategorihierarkin. På sidor som inte har kategorikontext visar moduler för navigeringssökväg **&lt;webbplatsens rot&gt; / &lt;aktuell sida&gt;** som standard. Moduler för navigeringssökväg kan också konfigureras manuellt på andra typer av webbplatssidor för att visa länkar till specifika sidor på webbplatsen.

> [!NOTE]
> Den dynamiska modulen är tillgänglig i Dynamics 365 Commerce 10.0.12-versionen.

Följande bild visar ett exempel på en modul för navigeringssökväg som visar kategorihierarkin på ett PDP.

![Exempel på en modul för navigeringssökväg.](./media/ecommerce-breadcrumb.PNG)

## <a name="breadcrumb-module-settings"></a>Inställningar för moduler för navigeringssökväg

Modulen för navigeringssökväg är beroende av inställningen **navigeringssökväg displaytyp på PDP** som definieras i **Webbplatsinställningar \> Tillägg** i webbplatsskaparen. Den här inställningen har tre möjliga värden:

- **Visa kategorihierarki** – när det här värdet väljs visar den fullständiga kategorihierarkin för produkten som visas på PDP i modulen för dynamiska länkar.
- **Visa tillbaka till resultat** – när det här värdet väljs visas länken "tillbaka till resultat" på ett PDP om användaren har öppnat PDP från en modul där det går att använda länken "tillbaka till resultat". Den här funktionen är tillgänglig när användare navigerar på sidorna kategori, sökning, lista och rekommendationslistor. För att stödja den här funktionen har modulerna för produktsamling och sökresultat en egenskap med namnet **Tillåt tillbaka till resultaten på PDP**. Den här egenskapen ger dig flexibiliteten att definiera vilka moduler som ska stödja länkfunktionen "tillbaka till resultat" i PDP. Till exempel när **Visa tillbaka till resultat** har valts som inställning på **navigeringssökväg displaytyp på PDP** i modulen för navigeringssökväg och **Tillåt tillbaka till resultat på PDP** är vald för sökresultatmodulen för sökningssidan, en "Tillbaka till resultat"-länk visas när användare navigerar från söksidan till en PDP.
- **Visa kategorihierarki och tillbaka till resultat** – detta värde är en kombination av de föregående två. När det här värdet väljs visas både den fullständiga kategorihierarkin och länken "tillbaka till resultat" (om den har konfigurerats) på ett PDP.

> [!IMPORTANT]
> Dessa inställningar finns i Dynamics 365 Commerce 10.0.12 versionen. Om du uppdaterar från en äldre version av Dynamics 365 Commerce måste du uppdatera filen appsettings.json manuellt. Information om hur du uppdaterar filen appsettings.json finns i [SDK- och modulens biblioteksuppdateringar](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).

## <a name="breadcrumb-module-properties"></a>Egenskaper för modulen för navigeringssökväg

| Egenskapsnamn | Värden | beskrivning |
|---------------|--------|-------------|
| Rot | Text eller länk| Den här valfria egenskapen anger länktext och ett länkmål för navigeringssökvägens webbplatsrot. Om den här egenskapen inte har konfigurerats kommer ingen rot att definieras. |
| Länk till navigeringssökväg | Länka | Den här valfria egenskapen anger länkar för en manuellt konfigurerad dynamiska länk, om dessa länkar behövs. Länkarna visas i angiven ordning i. |

## <a name="add-a-breadcrumb-module-to-a-new-page"></a>Lägg till en modul för navigeringssökväg på en ny sida

Om du vill lägga till en modul för navigeringssökväg till en PDP och ställa in de obligatoriska egenskaperna följer du stegen nedan.

1. Gå till **Webbplatsinställningar \> Tillägg**. För inställningen **Displaytyp för navigeringssökväg på PDP** väljer du **Visa kategorihierarki**.
1. Gå till **mallar** och välj PDP-mallen.
1. I platsen **Behållare** som innehåller modul för inköpsruta markerar du ellipsknappen (**...**) och väljer sedan **Lägg till modul**.
1. I dialogrutan **Välj moduler**, välj modulen **Synlig sökväg** och klicka sedan på **OK**.
1. Välj **Spara**, välj **Slutför redigering** för att checka in mallen och välj sedan **publicera** för att publicera den.
1. Gå till **sidor** och öppna en PDP som använder PDP-mallen. Om det ännu inte finns något PDP skapar du ett.
1. I platsen **Behållare** som innehåller modul för inköpsruta markerar du ellipsknappen (**...**) och väljer sedan **Lägg till modul**.
1. I dialogrutan **Välj moduler**, välj modulen **Synlig sökväg** och klicka sedan på **OK**.
1. I egenskapsrutan för platsen **Navigeringssökväg**, under **Rot**, välj **Länktext**.
1. I dialogrutan **Länktext** ange **Start** och sedan under **Länkmål**, välj **Lägg till en länk**.
1. I dialogrutan **Lägg till en länk** väljer du länken för roten för navigeringssökväg och välj sedan **OK**.
1. Klicka på **Spara** och välj **Förhandsgranska** för att förhandsgranska sidan.
1. Välj **Slutför redigering** för att checka in mallen och välj sedan **publicera** för att publicera den.

## <a name="additional-resources"></a>Ytterligare resurser

[Modulbibliotek – översikt](starter-kit-overview.md)

[Modul för navigeringsmeny](nav-menu-module.md)

[Webbplatsväljarmodul](site-selector.md)

[Översikt över standardkategorilandningssida och sida för sökresultat](category-search-page-overview.md)

[Produktsamlingsmoduler](product-collection-module-overview.md)

[Modul för inköpsruta](add-buy-box.md)

[Uppdateringar av SDK och modulbibliotek](e-commerce-extensibility/sdk-updates.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
