---
title: Karusellmodul
description: Det här avsnittet handlar om karusellmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: c2c5adc8ab2e0330f7b07e5153fd8332ab0203e5
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785247"
---
# <a name="carousel-module"></a>Karusellmodul

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Det här avsnittet handlar om karusellmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

En karusellmodul används för att placera flera reklamartiklar i en karusell som kunder kan bläddra i. Det är en särskild behållarmodul som är värd för andra moduler. En återförsäljare kan t.ex. använda en karusellmodul på en startsida för att visa flera nya produkter eller erbjudanden.

Du kan lägga till fokus- och funktionsmoduler i en karusellmodul. Egenskaperna för karusellmodulen anger sedan hur modulerna ska renderas.

## <a name="examples-of-carousel-modules-in-e-commerce"></a>Exempel på karusellmoduler i e-handel

- En karusell med flera reklammoduler i kan användas på en startsida.
- En karusell med flera reklammoduler i kan användas på en sida med produktinformation.
- En karusell kan användas på alla marknadsföringssidor för att främja flera erbjudanden eller produkter.

## <a name="carousel-module-properties"></a>Egenskaper för karusellmodul

| Egenskapsnamn             | Värde                                | Beskrivning |
|---------------------------|--------------------------------------|-------------|
| Spela upp automatiskt                  | **Sant** eller **falskt**                | Om värdet är inställt på **Sant**sker övergången mellan objekten i karusellen automatiskt. Om värdet är inställt på **Falsk** sker ingen övergång om inte kunden använder tangentbordet eller musen för att flytta från ett objekt till nästa objekt. |
| Intervall för bildövergång | Ett värde i sekunder                   | Intervallet för övergångar mellan artiklar. |
| Övergång animering      | **Bild** eller **toning**                | Övergångseffekten. |
| Bredd                     | **Passa behållare** eller **Fyll skärm** | Om värdet är inställt på att **passa behållare** begränsas objekten i karusellen till karusellens bredd. Om värdet är inställt på **Fyll skärm** begränsas inte objekten till karusellens bredd utan kan gå in i helskärmsläge. Du kan ändra värdet för att uppnå önskad layout. |

## <a name="add-a-carousel-module-to-a-page"></a>Lägg till en karusellmodul på en ny sida

Om du vill lägga till en karusellmodul på en ny sida och ställa in de obligatoriska egenskaperna följer du stegen nedan.

1. Skapa en sidmall som har namnet **karusellmall**.
1. Lägg till platsen **Huvud** på standardsida, lägg till en karusellmodul.
1. Lägg till en fokusmodul i karusellmodulen.
1. Lägg till en funktionsmodul i karusellmodulen.
1. Checka in mallen och publicera den. 
1. Använd den karusellmall som du just skapade för att skapa en sida med namnet **karusellsida**.
1. Lägg till platsen **Huvud** på ny sida, lägg till en karusellmodul.
1. Ange egenskapen **Bredd** för karusellmodulen för att **Fylla skärmen**. 
1. Ange egenskapen **övergångsanimation** till **Bild**.
1. Lägg till en fokusmodul i karusellmodulen.
1. Lägg till en bild och en rubrik i fokusmodulen och välj sedan **Spara**.
1. Lägg till en funktionsmodul i karusellmodulen.
1. Lägg till en bild, en rubrik och en textparagraf i funktionsmodulen.
1. Spara och förhandsgranska sidan. Sidan ska innehålla en karusell med två moduler inuti (en fokusmodul och en funktionsmodul). Du kan ändra ytterligare egenskaper för karusell-, fokus- och funktionsmoduler för att uppnå önskad effekt.
1. Checka in sidan och publicera den.

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över startpaket](starter-kit-overview.md)

[Notifieringsmodul](add-alert.md)

[Innehållsrik blockmodul](add-content-rich-block.md)

[Modul för innehållsplacering](add-content-placement-modules.md)

[Funktionsmodul](add-feature-module.md)

[Fokusmodul](add-hero-module.md)

[Videospelar-modul](add-video-player.md)
