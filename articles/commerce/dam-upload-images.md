---
title: Överför bilder
description: I det här avsnittet beskrivs hur du laddar upp bilder i Microsoft Dynamics 365 Commerce webbplatsskapare.
author: psimolin
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 3b99aeff7eafd788c19204e22dbfc61f45b25408
ms.sourcegitcommit: 5f5a8b1790076904f5fda567925089472868cc5a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/03/2021
ms.locfileid: "7891532"
---
# <a name="upload-images"></a>Överför bilder

[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du laddar upp bilder i Microsoft Dynamics 365 Commerce webbplatsskapare.

Med mediabiblioteket för Commerce webbplatsskapare kan du överföra bilder, antingen enstaka eller i bulk, med hjälp av mappar. Du bör alltid överföra bildens version med högsta upplösning och kvalitet eftersom bilden storleksändringskomponent automatiskt optimerar bilden för olika visningspunkter och deras brytpunkter.

### <a name="image-information-specified-during-upload"></a>Avbildningsinformation som anges under överföringen

När du överför en bild kan du ange följande information.

- **Rubrik, Alt text, beskrivning, nyckelord**: metadata för bilden eller bilderna. Rubrik och Alt text är obligatoriska värden.
- **Välj kategori**:
    - **Ingen**: används för en näthandels berättandebild eller bilder.
    - **Produkt, kategori, kund, medarbetare, katalog**: används för Dynamics 365 Commerce bild eller bilder i flera kanaler.
- **Publicera resurser efter uppladdning**: när den här kryssrutan är markerad publiceras bilden eller bilderna omedelbart efter överföringen.

> [!NOTE]
> - Bildtillgångar med en tilldelad kategori kodas också automatiskt med kategorin som nyckelord för att underlätta sökningen efter tillgångar i en viss kategori.
> - Produktdetaljsidorna genereras dynamiskt i **Alt-texten** med produktnamnet, så om du ändrar **Alt-texten** för en produktbild påverkas inte bilden som återges.

### <a name="naming-conventions-for-omni-channel-images"></a>Namnge regler för flerkanalsbilder 

Om du har konfigurerat mediebiblioteket som flerkanalsbild kan du använda bildkategorier för att ange vilken kategori den uppladdade bilden tillhör. Det finns också en namnkonvention som ska följas för att se till att bilderna hämtas korrekt av andra kanaler, t.ex. POS.

Standard namngivningskonventionen varierar beroende på vilken kategori:
- Katalogbilder ska heta "**/Catalogs/\{LanguageId\}/\{CatalogName\}.jpg**"
- Kategoribilder ska heta "**/Categories/\{CategoryName\}.png**"
- Kundbilder ska heta "**/Customers/\{CustomerNumber\}.jpg**"
- De anställdas bilder ska heta "**/Workers/\{WorkerNumber\}.jpg**"
- Produktbilder ska namnges på följande sätt: "**/Produkter/\{Produktnummer\}\_000_001.png**"
    - 001 är sekvensen av bilden och den kan vara 001, 002, 003, 004 eller 005
- Produktvariantbilder ska heta "**/Products/\{ProductNumber\} \^ \{Style\} \^ \{Size\} \^ \{Color\} \^\_000_001.png**"
    - Till exempel: 93039 \^ &nbsp;\^ 2 \^ Svart \^\_000_001.png
- Produktvariantbilder med konfigurationsdimensioner ska namnges på följande sätt: "**/Produkter/\{Produktnummer\} \^ \{Konfiguration\}\_000_001.png**"
    - Till exempel: 93039 \^ LB8017_000_001.png

> [!NOTE]
> För produktvariantbilder måste det finnas två blanksteg mellan inskjutningstecknen i filnamnet om dimensionsvärdet är tomt.

I exemplen ovan används standardkonfigurationen. Avgränsartecknet och måtten är konfigurerbara och det exakta namn som krävs kan variera mellan olika distributioner. En metod för att identifiera den exakta namnkonventionen som krävs är att använda webbläsarens utvecklarkonsol för att kontrollera bildförfrågningar om produktvarianter medan du ändrar produktdimensionerna på informationssidan för butiksprodukt (PDP).

## <a name="upload-an-image"></a>Ladda upp en bild

Så här överför du en bild i webbplatsskapare.

1. I vänstra navigeringsfönstret, välj **mediebibliotek**.
1. I kommandofältet, välj **Överför \> Överför medieartiklar**.
1. I fönstret Utforskaren navigerar du till och markerar en eller flera bildfiler som ska överföras och väljer sedan **öppna**.
1. I dialogrutan **Överför medieartiklar** ange önskad rubrik och alt text.
1. Ange valfri beskrivning och nyckelord och välj en kategori om du vill. 
1. Om du vill publicera bilden omedelbart efter överföringen markerar du kryssrutan **Publicera medieobjekt efter uppladdning**.
1. Välj **OK**.

## <a name="upload-a-folder-of-images"></a>Överföra en mapp med bilder

Så här massöverför du en mapp av bilder i webbplatsskapare.

1. I vänstra navigeringsfönstret, välj **mediebibliotek**.
1. I kommandofältet, välj **Överför \> Överför mapp**.
1. I fönstret Utforskaren navigerar du till och markerar en mapp att överföra och väljer sedan **öppna**.
1. I dialogrutan **Överför medieartiklar** ange valfria nyckelord och välj en kategori om så önskas. 
1. Om du vill publicera bilden i mappen omedelbart efter överföringen markerar du kryssrutan **Publicera medieobjekt efter uppladdning**.
1. Välj **OK**.

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt av digital tillgångshantering](dam-overview.md)

[Överför video](dam-upload-video.md)

[Överför filer](dam-upload-files.md)

[Beskär bilder](dam-crop-images.md)

[Anpassa bildens fokuspunkter](dam-custom-focal-point.md)

[Ladda upp och betjäna statiska filer](upload-serve-static-files.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
