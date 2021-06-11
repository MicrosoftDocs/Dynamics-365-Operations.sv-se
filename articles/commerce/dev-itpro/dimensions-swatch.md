---
title: Konfigurera värden för produktdimensioner som ska visas som färgrutor
description: I det här avsnittet beskrivs hur du konfigurerar produktdimensionsvärden som färgrutor i Microsoft Dynamics 365 Commerce-administration.
author: anupamar-ms
ms.date: 05/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rapraj
ms.search.validFrom: 2020-09-20
ms.dyn365.ops.version: Retail 10.0.20 update
ms.openlocfilehash: 08564ce7af7412f2501b917b3496942004402611
ms.sourcegitcommit: 53b797ff1b524f581046b48cdde42f50b37495bc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/28/2021
ms.locfileid: "6117246"
---
# <a name="configure-product-dimension-values-to-appear-as-swatches"></a>Konfigurera värden för produktdimensioner som ska visas som färgrutor

[!include [banner](../../includes/banner.md)]
[!include [banner](../../includes/preview-banner.md)]

I det här avsnittet beskrivs hur du konfigurerar produktdimensionsvärden som färgrutor i Microsoft Dynamics 365 Commerce-administration. Mer information om produktdimensioner finns i [produktdimensioner](../../supply-chain/pim/product-dimensions.md).

Dynamics 365 Commerce stöder dimensioner för storlek, utförande och färg som representerar produktvarianter. Produktdimensioner har användarvänliga namn som visas på produktinformationssidor så att produktvarianter kan väljas. Dessa användarvänliga namn kan till exempel vara "Small", "Medium" och "Large" för storlekar och "Svart" och "Brunt" för färger. Om en produkt har stöd för många variationer, krävs det dock flera val för att visa bilden för varje produktvariant. Därför kan det vara långsamt och svårt för kunderna att bläddra och välja produktvarianter.

När dimensionerna visas som färgrutor på PDP får kunderna en visuell förhandsgranskning av en produkts variationer. De kan enkelt bläddra i en stor mängd färger, mönster och texturer, och kan snabbt visa olika kombinationer av produktvariationer.

Funktionen för visningsdimensioner som färgrutor gör det möjligt för Commerce att använda hexadecimala koder och bilder som visar dimensioner som färgrutor. Dessutom kan liknande dimensioner, som färger, grupperas på produktlistesidor. En kund söker till exempel efter blå produkter. Om de olika blå dimensionsvärdena grupperas tillsammans visar sökresultatlistan produkter som har olika blå färg. Dimensionsgruppering förbättrar produktförfining avsevärt och hjälper kunder att hitta fler produkter genom en enskild produktsökningsfråga.

> [!NOTE]
> Funktionen för visningsdimensioner som färgrutor finns i Dynamics 365 Commerce version 10.0.20.

I följande bild visas ett exempel där färger visas som färgrutor på en Commerce-PDP.

![Exempel på färger som visas som färgrutor på en produktinformationssida](../dev-itpro/media/swatch_pdp.png)

I följande bild visas ett exempel där färger visas som färgrutor på en sida för Commerce-sökresultatlistan.

![Exempel på färger som visas som färgrutor på en sida för sökresultatlista](../dev-itpro/media/swatch_searchresults.PNG)

## <a name="enable-the-display-dimensions-as-swatches-feature-in-commerce-headquarters"></a>Aktivera visning av dimensioner som färgrutor i Commerce-administration

För att aktivera visningsdimensionerna som färgrutor i Commerce-administration, gå till **Arbetsytor \> Funktionshantering** och aktiverar funktionen **Aktivera bildstöd för produktdimensionsvärden**. När funktionens flagga aktiveras, läggs tre nya fält till för varje dimension i de passande registren i Commerce-administration: **Hexkod**, **URL** (för bilder) och **RefinerGroup**.

## <a name="configure-dimension-values-in-commerce-headquarters"></a>Konfigurera dimensionsvärden i Commerce-administration

Visning av dimensioner som färgrutor stöds för dimensioner för storlek, stil och färg. URL-värden för hexkod och bild för de relevanta dimensionerna kan anges i Commerce-administration. Om webbadressvärdena för hexkoden och bilden inte anges som standard för en dimension, visar systemet texten i dimensionens användarvänliga namn.

Konfigurationen kan utföras på någon av följande nivåer:

- **Dimension** – I Commerce-administration, öppna sidan för en dimension genom att söka efter **Färg**, **Storlek** eller **Format**. På varje sida listar ett rutnät dimensionsvärdena. Du kan hantera webbadressvärdena för visningsordning, hexkod och bild. Följande illustration visar ett exempel på konfiguration på sidan **Färger**.

    ![Exempel på dimensionskonfiguration på sidan Färger](../dev-itpro/media/swatch_Color.PNG)

- **Dimensionsgrupp** – I Dynamics 365 Commerce, kan du använda egenskapen **RefinerGroup** för att skapa dimensionsgrupper. Om dimensionsgrupper har definierats öppnar du lämplig sida genom att söka efter **färggrupp**, **storleksgrupp** eller **formatgrupp**. På varje sida kan du hantera hexkod, webbadress för bilder och värden för förfiningsgrupper. Följande illustration visar ett exempel på konfiguration på sidan **Färggrupper**.

    ![Exempel på dimensionskonfiguration på sidan Färggrupper](../dev-itpro/media/swatch_colorGroup.PNG)

- **Produktdimension (när produkten skapas)** – När du skapar en ny produkt kan du använda sidan **Produktdimensioner** för att ange dimensionsvärden. För befintliga produkter kan fälten **Hexkod**, **URL** (för bilder) och **RefinerGroup** redan ha ställts in. Du kan dock ändra värdena som du vill. Följande illustration visar ett exempel på konfiguration på sidan **Produktdimensioner**.

    ![Exempel på dimensionskonfiguration på sidan Produktdimensioner](../dev-itpro/media/swatch_product_dimensions.PNG)

> [!NOTE]
> Processen för hantering av hexkod och URL-konfigurationer för bilder följer samma mönster som vid hantering av visningsordningen för dimensioner.

## <a name="configure-dimension-values-by-using-hex-codes"></a>Konfigurera dimensionsvärden med hjälp av hexkoder

För de flesta färgdimensioner ska ett färgvärde för hexkod anges på dimensionssidorna i Commerce-administration. Till exempel bör färgen svart ha ett hexkodvärde på **#00000**. När Commerce återger en webbplatssida representeras hexkoden av en färgruta.

I följande bild visas ett exempel där färgdimensioner konfigureras med hjälp av hexkodvärden.

![Exempel på dimensionskonfiguration som använder hexkoder](../dev-itpro/media/swatch_color_hexcode.png)

## <a name="configure-dimension-values-by-using-image-urls"></a>Konfigurera dimensionsvärden med hjälp av bild-URL

Vissa färgdimensioner representerar mönster, inte färger. En färgdimension kan till exempel beskrivas som "leopard". I dessa fall kan du på ett mer effektivt sätt representera färgdimensionerna genom att använda publicerade bilder i stället för hexkoder för färgrutor.

Du måste överföra varje bild till Commerce webbplatsskaparen och publicera den. Ange sedan bild-URL för den publicerade bilden på motsvarande dimensionssidor i Commerce-administration. Om en dimension har valts för visning som en färgruta, men en hexkod är definierad, utförs en bilduppslag när sidan visas i Commerce. Om bildvisningen misslyckas visar Commerce texten i dimensionens användarvänliga namn.

Följande illustration visar ett exempel på när bild-URL används för konfigurationen på sidan **Färger**.

![Exempel på dimensionskonfiguration som använder bild-URL](../dev-itpro/media/swatch_color_urls.PNG)

Du kan använda en mediemall för att definiera webbadresser för bilder, på samma sätt som för produkt- och kategoribilder. När du överför bilder till webbplatsskaparen måste filnamnskonventioner och filsökvägar vara konsekventa.

Följande illustration visar ett exempel på när bild-URL används för konfigurationen av en mediemall.

![Exempel på konfiguration av mediemall](../dev-itpro/media/swatch_media_template.PNG)

## <a name="configure-dimension-values-by-using-both-hex-codes-and-image-urls"></a>Konfigurera dimensionsvärden med hjälp av både hexkoder och bild-URL

Du kan konfigurera både hexkoder och bild-URL-adresser för de flesta färgdimensioner. Reservlogiken för Commerce-återgivning söker automatiskt efter antingen en hexkod eller en bild-URL-adress som visar en färgruta. Genom att använda både hexkoder och URL-adresser för att konfigurera färgdimensioner kan du förenkla bildhanteringen när antalet färger är stort.

Följande illustration visar ett exempel när både hexkoder och bild-URL används för konfigurationen på sidan **Färger**.

![Exempel på dimensionskonfiguration som använder både hexkoder och bild-URL](../dev-itpro/media/swatch_color_hexandimage.png)

## <a name="configure-refiner-groups"></a>Konfigurera förfiningsgrupper

När du definierar en URL för en hexkod eller en bild-URL för ett dimensionsvärde, kan du också ange ett värde för fältet **RefinerGroup**. Det här fältet definierar den dimension som ska användas för att gruppera liknande dimensionsvärden i förfiningserfarenheten.

Om till exempel dina färgdimensionsvärden är "blå", "blå pläd, " blåtvätt" och "mörkblå" mappas varje värde till en annan hexkod eller bild-URL. Därför visas varje värde som en annan färg på PDU och produktkort för lämpliga produkter. Om du däremot mappar alla dessa färgdimensionsvärden till ett **RefinerGroup**-värde för **Blått**, kommer en sökning efter "blå" produkter att generera listsidessökningsresultat för produkter som har dimensionsfärgsvärden som "blå", "blå pläd" eller "blåtvätt" eller "mörkblå".

I följande bild visas relationen mellan egenskaperna **Färg** och **RefinerGroup** i Commerce-administration.

![Exempel på hantering av förfiningsgrupper](../dev-itpro/media/swatch_refiner_group.png)

## <a name="manage-images-in-commerce-site-builder"></a>Hantera bilder i Commerce-webbplatsbyggaren

Om bild-URL-adresser används för dimensionsvärden måste motsvarande bilder överföras till Commerce-webbplatsskaparen. Placeringen av varje bild ska matcha filnamnet och mappsökvägen som är definierad för bilden i Commerce-administration. Bildfiler måste överföras till rätt kategoriplatser i webbplatsskaparen. Färgbilder måste till exempel överföras till kategorimappen **Färg**. Mer information om hur du överför bilder till webbplatsskaparen finns i [överför bilder](../dam-upload-images.md).

I följande bild visas ett exempel där dialogrutan **Överför filer** används för att överföra bilder till mediebiblioteket för webbplatsbyggaren. I rapporten markeras de kategorier med **storlek**, **färg** och **stil** som är tillgängliga för urval.

![Exempel på bildfilskategorier under överföring till mediebiblioteket för webbplatsskaparen](../dev-itpro/media/swatch_sitebuilder.png)

## <a name="enable-swatch-display-on-e-commerce-site-pages"></a>Aktivera visning av färgrutor på sidor för e-handel

Innan färgrutor kan visas på webbplatssidor med e-handel som kräver dimensionsval, såsom PDP och listsidor, måste du konfigurera dimension webbplatsinställningar i Commerce-administration. Mer information finns i [Använd webbplatsinställningar för dimensioner](../dimension-settings.md).

Du bör dessutom aktivera egenskapen **Inkludera produktattribut i sökresultaten** för sökresultatmoduler. Om din webbplats använder anpassade kategorisidor bör du uppdatera sökresultat modulerna som används på dessa sidor så att egenskapen **Inkludera produktattribut i sökresultat** är aktiverad. Mer information finns i avsnittet [modulen sökresultaten](../search-result-module.md).

## <a name="display-swatches-in-pos-and-other-channels"></a>Visa färgrutor i kassa och andra kanaler

Commerce har för närvarande inte en "medföljande" implementering som stöder visningen av färgrutor i kassa och andra kanaler. Du kan emellertid implementera färgrutefunktionen som ett tillägg som gör att kanal-API:er returnerar de hexkoder och bild-URL-adresser som krävs för att återge färgrutor.

## <a name="additional-resources"></a>Ytterligare resurser

[Sökresultatmodul](../search-result-module.md)

[Använd webbplatsinställningar för dimensioner](../dimension-settings.md)

[Produktdimensioner](../../supply-chain/pim/product-dimensions.md)

[Överför bild](../dam-upload-images.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
