---
title: Behållaremodul
description: Det här avsnittet handlar om behållarmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 43017cbb76c38eed6951a9e87c763cf919c3bd93
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5206425"
---
# <a name="container-module"></a>Behållarmodul

[!include [banner](includes/banner.md)]

Det här avsnittet handlar om behållarmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.

En behållarmodul är en modul som är värd för andra moduler inne i den. Det primära syftet med en behållare är att definiera, via de egenskaper som är inställda för den, layouten för modulerna som den innehåller. Dessa moduler kan till exempel visas sida vid sida i en layout med två kolumner, tre kolumner, fyra kolumner och sex kolumner. De kan också begränsas till behållarens bredd, eller så att de fyller skärmen. En rubrik kan också läggas till i varje behållarmodul.

Tre behållarmoduler stöds: behållare, behållare med 2 platser och behållare med 3 platser. Moduler av valfri typ kan placeras i dessa behållare. 

> [!NOTE] 
> Vi rekommenderar att du alltid placerar moduler inuti en behållarmodul så att de kan begränsas till behållarens bredd.

## <a name="examples-of-container-modules-in-e-commerce"></a>Exempel på behållarmoduler i näthandel

- En webbplatsförfattare vill ha en layout med tre kolumner, där tre moduler visas sida vid sida. Därför använder webbplatsförfattaren en behållarmodul med typen 3 platser.
- En webbplatsförfattare vill ha en layout med sex kolumner, där sex moduler visas sida vid sida. Därför använder webbplatsförfattaren en behållare som innehåller sex kolumner.
- En webbplatsförfattare vill placera en modul på en sida men vill inte att den ska fylla skärmen. Därför lägger webbplatsförfattaren till modulen i en behållarmodul och anger behållarens egenskap **bredd** till **anpassad behållare**.

Följande bild visar ett exempel på en behållarmodul som innehåller en karusellmodul i Commerce webbplatsskaparen. I det här exemplet är egenskapen **Bredd** för behållarmodulen inställd på **Fyll skärm**.

![Exempel på en behållarmodul](./media/ecommerce-container.PNG)

## <a name="container-module-properties"></a>Egenskaper för behållarmoduler

| Egenskapsnamn     | Värden | beskrivning |
|-------------------|--------|-------------|
| Rubrik           | Rubriktext och rubriktagg (**H1**, **H2**, **H3**, **H4**, **H5** eller **H6**) | En valfri rubrik kan anges för behållaren. Som standard används rubriktaggen **H2** för rubriken. Taggen kan emellertid ändras så att den uppfyller tillgänglighetskraven. |
| Bredd             | **Passa behållare** eller **Fyll skärm** | Om värdet är inställt på att **Fylla behållare** (standardvärdet) modulerna inne i behållaren begränsas till behållarens bredd. Om värdet är inställt på **Fyll skärm** begränsas modulerna inte till behållarens bredd utan kan fylla skärmen. |
| Antal kolumner | **1**, **2**, **3**, **4**, **6** eller **12** | Den här egenskapen definierar antalet kolumner i behållaren. En behållare kan ha upp till 12 kolumner. |

## <a name="container-with-2-slots"></a>Behållare med två platser

Behållaren av typen 2 platser är optimerad för en layout med två kolumner. Den här typen av behållare har två platser som du kan använda för att visa modulerna bredvid varandra.

Ytterligare egenskaper kan användas för att optimera layouten för olika visningsportar (mobila enheter, surfplattor, datorer och så vidare). För varje visningsport kan bredden på varje kolumn definieras. Följande inställningar av kolumnbredd är tillgängliga:

- **75 %/25 %** – den första modulen har kolumnbredden 75 procent och den andra modulen har kolumnbredden 25 procent. Alternativet **25 %/75 %** är också tillgängligt.
- **50 %/50 %** – båda modulerna har samma kolumnbredd.
- **67 %/33 %** – den första modulen har kolumnbredden 67 procent och den andra modulen har kolumnbredden 33 procent. Alternativet **33 %/67 %** är också tillgängligt.
- **100 %** – båda modulerna har en fullständig kolumnbredd. Därför staplas modulerna lodrätt i en enda kolumn. Även om den här layouten för en kolumn ska placeras i förhållande till behållaren med två platser, kan det vara bättre att använda vissa visningsportar (t.ex. extra små vyer som t.ex. mobila enheter).

### <a name="container-with-2-slots-properties"></a>Behållare med egenskaper för 2 platser

| Egenskapsnamn                   | Värden | Beskrivning |
|---------------------------------|--------|-------------|
| Rubrik                         | Rubriktext och rubriktagg | En valfri kan anges för behållaren. |
| Konfiguration av extra liten visningsport | **25 %/75 %**, **75 %/25 %**, **50 %/50 %**, **67 %/33 %**, **33 %/67 %** eller **100 %** | Den här egenskapen definierar layouten för extra små visningsportar. |
| Konfiguration av liten visningsport   | **25 %/75 %**, **75 %/25 %**, **50 %/50 %**, **67 %/33 %**, **33 %/67 %** eller **100 %** | Den här egenskapen definierar layouten för små visningsportar, t.ex. mobila enheter. |
| Konfiguration av medelstor visningsport  | **25 %/75 %**, **75 %/25 %**, **50 %/50 %**, **67 %/33 %**, **33 %/67 %** eller **100 %** | Den här egenskapen definierar layouten för medelstora visningsportar, t.ex. surfplattor. |
| Konfiguration av stor visningsport   | **25 %/75 %**, **75 %/25 %**, **50 %/50 %**, **67 %/33 %**, **33 %/67 %** eller **100 %** | Den här egenskapen definierar layouten för stora visningsportar, t.ex. datorer. |

## <a name="container-with-3-slots"></a>Behållare med tre platser

Behållaren av typen 3 platsmoduler är optimerad för en layout med tre kolumner.

Ytterligare egenskaper kan användas för att optimera layouten för olika visningsportar. För varje visningsport kan bredden på varje kolumn definieras. Följande inställningar av kolumnbredd är tillgängliga:

- **33 %/33 %/33 %** – Alla tre modulerna har samma kolumnbredd.
- **50 %/25 %/25 %** – den första modulen har kolumnbredden 50 procent och var och en av de återstående två modulerna har kolumnbredden 25 procent. Alternativen **25 %/50 %/25 %** och **25%/25%/50%** är också tillgängliga.
- **16 %/16 %/67 %** – Var och en av de första två modulerna har kolumnbredden 16 procent och den tredje modulen har kolumnbredden 67 procent. Alternativen **16 %/67 %/16 %** och **67%/16%/16%** är också tillgängliga.

### <a name="container-with-3-slots-properties"></a>Behållare med egenskaper för 3 platser

| Egenskapsnamn                   | Värden | Beskrivning |
|---------------------------------|--------|-------------|
| Rubrik                         | Rubriktext och rubriktagg | En valfri rubrik kan läggas till behållaren. |
| Konfiguration av extra liten visningsport | **33 %/33 %/33 %**, **50 %/25 %/25 %**, **25 %/50 %/25 %**, **25 %/25 %/50 %**, **16 %/16 %/67 %**, **16 %/67 %/16 %** eller **67 %/16 %/16 %** | Den här egenskapen definierar layouten för extra små visningsportar. |
| Konfiguration av liten visningsport   | **33 %/33 %/33 %**, **50 %/25 %/25 %**, **25 %/50 %/25 %**, **25 %/25 %/50 %**, **16 %/16 %/67 %**, **16 %/67 %/16 %** eller **67 %/16 %/16 %** | Den här egenskapen definierar layouten för små visningsportar, t.ex. mobila enheter. |
| Konfiguration av medelstor visningsport  | **33 %/33 %/33 %**, **50 %/25 %/25 %**, **25 %/50 %/25 %**, **25 %/25 %/50 %**, **16 %/16 %/67 %**, **16 %/67 %/16 %** eller **67 %/16 %/16 %** | Den här egenskapen definierar layouten för medelstora visningsportar, t.ex. surfplattor. |
| Konfiguration av stor visningsport   | **33 %/33 %/33 %**, **50 %/25 %/25 %**, **25 %/50 %/25 %**, **25 %/25 %/50 %**, **16 %/16 %/67 %**, **16 %/67 %/16 %** eller **67 %/16 %/16 %** | Den här egenskapen definierar layouten för stora visningsportar, t.ex. datorer. |

## <a name="add-a-container-module-to-a-page"></a>Lägg till en behållarmodul på en sida

Om du vill lägga till en modul för behållarspelare på en ny sida och ställa in de obligatoriska egenskaperna följer du stegen nedan.

1. Gå till **mallar** och välj sedan **ny** för att skapa en ny mall.
1. I dialogrutan **Ny mal** under **Mallnamn**, ange **Behållarmall** och välj sedan **OK**.
1. I facket **brödtext** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.
1. I dialogrutan **Lägg till modul**, välj modulen **Standardsida** och klicka sedan på **OK**.
1. Välj **Spara**, välj **Slutför redigering** för att checka in mallen och välj sedan **publicera** för att publicera den. 
1. Gå till **Sidor** och välj **nytt sidfragment** för att skapa en ny sida.
1. I dialogrutan **Välj en mall**, välj den videospelarmall du skapade. Under **sidnamn**, ange **Behållarsida** och klicka sedan på **OK**.
1. I platsen för nya sidan väljer du **Huvud**, markerar ellipsknappen (**...**) och väljer sedan **Lägg till modul**.
1. I dialogrutan **Lägg till modul**, välj modulen **Behållare** och klicka sedan på **OK**.
1. I egenskapsrutan för behållarmodulen anger du egenskapen **antalet kolumner** till **1** och egenskapen **bredd** till **fyll behållare**.
1. I facket **behållare** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.
1. I dialogrutan **Lägg till modul**, välj modulen **Innehållsblock** och klicka sedan på **OK**.
1. Konfigurera rubrik, bild och layout i egenskapsfönstret för innehållsblockmodulen.
1. Klicka på **Spara** och välj **Förhandsgranska** för att förhandsgranska sidan. Du bör se en modul som får plats inom samma bredd som behållarmodulen.
1. I behållarmodulens egenskapsfönster, ändra värdet för **Antal kolumner** till **3**.
1. Lägg till ytterligare två moduler för innehållsblock i behållarmodulen och konfigurera dem.
1. Klicka på **Spara** och välj **Förhandsgranska** för att förhandsgranska sidan. Nu ska du se tre innehållsblockmoduler som visas sida vid sida.
1. När du har uppnått layouten du vill ha väljer du **Slutför redigering** för att checka in sidan och väljer sedan **Publicera** för att publicera den.

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över modulbibliotek](starter-kit-overview.md)

[Dragspelsmodul](add-accordion.md)

[Flikmodul](add-tab.md)

[Karusellmodul](add-carousel.md)

[Textblockmodul](add-content-rich-block.md)

[Modul för inköpsruta](add-buy-box.md)

[Kundvagnsmodul](add-cart-module.md)

[Kassamodul](add-checkout-module.md)

[Modul för sidhuvud](author-header-module.md)

[Sidfotmodul](author-footer-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]