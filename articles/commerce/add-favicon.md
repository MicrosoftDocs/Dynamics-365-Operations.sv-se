---
title: Lägg till en favicon
description: I det här avsnittet beskrivs hur du lägger till en favicon på webbplatsen.
author: bicyclingfool
manager: annbe
ms.date: 04/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 198927e3391bdb577ebc845ff41d49ca798251ff
ms.sourcegitcommit: 81f162f2d50557d7afe292c8d326618ba0bc3259
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/11/2020
ms.locfileid: "3686800"
---
# <a name="add-a-favicon"></a>Lägg till en favicon

[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du lägger till en favicon på webbplatsen.

## <a name="overview"></a>Översikt

En favicon är en liten grafisk fil som visas på en flik i webbläsaren, i adressfältet, i webbhistoriken och i bokmärken eller favoriter, bland annat. Vi rekommenderar att du lägger till en favicon på din webbplats, eftersom den representerar och stärker ditt varumärke och hjälper till att skilja din webbplats från andra webbplatser som dina kunder besöker.

Även om du kan lägga till flera favicons av olika storlekar och filtyper på din webbplats, visar det här avsnittet hur du lägger till en enskild favicon. Samma process och plats används dock för att lägga till fler favicons.

## <a name="upload-a-favicon-to-your-sites-asset-collection"></a>Överför en favicon till webbplatsens tillgångssamling

Överför en favicon till webbplatsens tillgångssamling genom att följa dessa steg.

1. I vänstra navigeringsfönstret, välj **mediebibliotek**.
1. I kommandofältet, välj **Överför \> Överför medieartiklar**.
1. I fönstret Utforskaren bläddrar du till avbildningsfilen favicon som du vill överföra, markerar den och väljer sedan **Öppna**.
1. I dialogrutan **Överför medieartiklar** ange önskad titel och alt text.
1. Om du vill publicera bilden omedelbart efter överföring markerar du kryssrutan **Publicera medieobjekt efter uppladdning**.

    > [!NOTE]
    > Om du inte markerar kryssrutan **Publicera medieobjekt efter överföring** måste du gå tillbaka till sidan **Medieobjekt** och publicera favicon manuellt senare.

1. Välj **OK**.
1. Kopiera den offentliga URL:en för favicon i egenskapsrutan till höger. Du kommer att använda denna URL senare.

## <a name="create-the-html-for-your-favicon"></a>Skapa HTML för din favicon

Om du vill skapa HTML för favicon använder du följande HTML-sträng. För attributet **href**, ersätt **Public\_URL\_for\_your\_favicon** med den offentliga URL som du kopierade tidigare.

`<link rel="shortcut icon" href="Public_URL_for_your_favicon">`

## <a name="create-a-page-fragment-that-contains-a-metatag-for-your-favicon"></a>Skapa ett sidfragment som innehåller en metatagg för din favicon

För att skapa ett sidfragment som innehåller en metatagg för din favicon ska du följa dessa steg.

1. Gå till **Fragment** och välj sedan **Nytt**.
1. I dialogrutan **Nytt sidfragment** markerar du **Metataggar** som modulen sidfragment är baserat på.
1. Ange ett namn på sidfragmentet och välj sedan **OK**.
1. I trädet för fragmentets hierarki väljer du underordnade **Standard metataggar**.
1. I det högra fönstret, under **Metataggar**, väljer du **Lägg till** och anger sedan den HTML-sträng som du skapade tidigare för favicon. 
1. Välj **Slutför redigering** och välj sedan **Publicera** för att publicera sidfragmentet.

## <a name="add-the-metatag-page-fragment-to-the-html-head-section-of-your-pages"></a>Lägg till sidfragmentet med metatagg i HTML-huvudet på dina sidor

För att lägga till sidfragmentet med metatagg i HTML-**huvudet** på dina sidor ska du följa dessa steg

1. Gå till **Mallar** och öppna mallen för sidorna som du vill lägga till din favicon i och välj sedan **Redigera**.
1. I trädet för mallhierarkin väljer du ellipsknappen (**...**) till höger om behållaren för **HTML-huvud** och väljer **Lägg till sidfragment**.
1. I dialogrutan **Välj sidfragment** väljer du det metatagsidfragment som du skapade tidigare och väljer sedan **OK**.
1. Välj **Slutför redigering** och välj sedan **Publicera** för att publicera mallen.

> [!NOTE]
> Om mer än en mall används på webbplatsen måste du lägga till metatagsidfragmentet på alla.

När du förhandsgranskar sidor baserade på den mall som du har lagt till metatagsidfragmentet till ska du nu se favicon på fliken i webbläsaren.

## <a name="additional-resources"></a>Ytterligare resurser

[Lägga till en logotyp](add-logo.md)

[Välja ett tema för webbplatsen](select-site-theme.md)

[Arbeta med CSS åsidosättningsfiler](css-override-files.md)

[Lägg till ett välkomstmeddelande](add-welcome-message.md)

[Lägg till copyrightmeddelande](add-copyright-notice.md)

[Lägg till språk på din webbplats](add-languages-to-site.md)

[Lägga till skriptkod på webbsidor för att stödja telemetri](add-telemetry.md)

