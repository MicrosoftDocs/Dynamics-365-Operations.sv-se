---
title: Karusellmodul
description: Det här avsnittet handlar om karusellmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 05/28/2020
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
ms.openlocfilehash: 10ff0cd566a1a8d89ccadce9571dafc5a592520b
ms.sourcegitcommit: 4a981ee4be6d7e6c0e55541535d386bce2565cba
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/27/2020
ms.locfileid: "3620996"
---
# <a name="carousel-module"></a>Karusellmodul

[!include [banner](includes/banner.md)]

Det här avsnittet handlar om karusellmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

En karusellmodul används för att placera flera reklamartiklar (inklusive rika bilder) i en roterande karusellbanderoll som kunder kan bläddra i. En återförsäljare kan t.ex. använda en karusellmodul på en startsida för att visa flera nya produkter eller erbjudanden.

Du kan lägga till innehållsblockmoduler i en karusellmodul. Egenskaperna för karusellmodulen anger sedan hur modulerna ska renderas.

## <a name="examples-of-carousel-modules-in-e-commerce"></a>Exempel på karusellmoduler i e-handel

- En karusell med flera reklammoduler i kan användas på en startsida.
- En karusell med flera reklammoduler i kan användas på en sida med produktinformation.
- En karusell kan användas på alla marknadsföringssidor för att främja flera erbjudanden eller produkter.

Följande bild visar ett exempel på en karusellmodul som används på en startsida. Den här karusellmodulen innehåller flera innehållsblockobjekt.

![Exempel på en karusellmodul](./media/Hero.PNG)

## <a name="carousel-module-properties"></a>Egenskaper för karusellmodul

| Egenskapsnamn             | Värde                 | beskrivning |
|---------------------------|-----------------------|-------------|
| Spela upp automatiskt                  | **Sant** eller **falskt** | Om värdet är inställt på **Sant**sker övergången mellan objekten i karusellen automatiskt. Om värdet är inställt på **Falsk** sker ingen övergång om inte kunden använder tangentbordet eller musen för att flytta från ett objekt till nästa objekt. |
| Intervall för bildövergång | Ett värde i sekunder    | Intervallet för övergångar mellan artiklar. |
| Övergångstyp           | **Bild** eller **toning** | Övergångseffekten mellan objekt. |
| Dölj karusellens flipper     | **Sant** eller **falskt** | Om värdet är inställt på **Sant** döljs ikonen karusell och sekvensindikator. |
| Tillåt att karusellen stängs    | **Sant** eller **falskt** | Om värdet är inställt på **Sant** kan användare stänga karusellen. |

## <a name="add-a-carousel-module-to-a-page"></a>Lägg till en karusellmodul på en ny sida

Om du vill lägga till en karusellmodul på en ny sida och ställa in de obligatoriska egenskaperna följer du stegen nedan.

1. Gå till **mallar**och välj sedan **ny** för att skapa en ny mall.
1. I dialogrutan **Ny mal** under **Mallnamn**, ange **Karusellmall** och välj sedan **OK**.
1. I facket **Brödtext**, lägg till en **standardsida**-modul.
1. Välj **Slutför redigering** för att checka in mallen och välj sedan **publicera** för att publicera den.  
1. Använd den karusellmall som du just skapade för att skapa en sida med namnet **karusellsida**.
1. Lägg till platsen **Huvud** på ny sida, lägg till en behållarmodul. 
1. I fönstret till höger, ange värdet **Bredd** till **Fyll skärm**.
1. Under **Siddisposition**, lägg till en karusellmodul i behållarmodulen.
1. I karusellmodulen, lägg till en innehållsblockmodul. Ställ in egenskaperna för innehållsblockmodulen genom att ange **rubrik**, **länk**, **layout** och andra egenskaper.
1. Lägg till och konfigurera en annan innehållsblockmodul.
1. Ställ in ytterligare egenskaper för karusellmodulen som du behöver.
1. Klicka på **Spara** och välj **Förhandsgranska** för att förhandsgranska sidan. Sidan ska innehålla en karusell med två moduler inuti (en fokusmodul och en funktionsmodul). Du kan ändra ytterligare egenskaper för karusell-, fokus- och funktionsmoduler för att uppnå önskad effekt.
1. Välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.

## <a name="additional-resources"></a>Ytterligare resurser

[Startpaket – översikt](starter-kit-overview.md)

[Modul med kampanjbanderoll](add-alert.md)

[Textblockmodul](add-content-rich-block.md)

[Innehållsblockmodul](add-hero-module.md)

[Modul för videospelare](add-video-player.md)
