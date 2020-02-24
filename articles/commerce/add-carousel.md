---
title: Karusellmodul
description: Det här avsnittet handlar om karusellmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 01/23/2020
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
ms.openlocfilehash: f279d7db0a92df9e64b1d3f6ca01c65ca1478d79
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025791"
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

## <a name="carousel-module-properties"></a>Egenskaper för karusellmodul

| Egenskapsnamn             | Värde                 | Beskrivning |
|---------------------------|-----------------------|-------------|
| Spela upp automatiskt                  | **Sant** eller **falskt** | Om värdet är inställt på **Sant**sker övergången mellan objekten i karusellen automatiskt. Om värdet är inställt på **Falsk** sker ingen övergång om inte kunden använder tangentbordet eller musen för att flytta från ett objekt till nästa objekt. |
| Intervall för bildövergång | Ett värde i sekunder    | Intervallet för övergångar mellan artiklar. |
| Övergångstyp           | **Bild** eller **toning** | Övergångseffekten mellan objekt. |
| Dölj karusellens flipper     | **Sant** eller **falskt** | Om värdet är inställt på **Sant** döljs ikonen karusell och sekvensindikator. |
| Tillåt att karusellen stängs    | **Sant** eller **falskt** | Om värdet är inställt på **Sant** kan användare stänga karusellen. |

## <a name="add-a-carousel-module-to-a-page"></a>Lägg till en karusellmodul på en ny sida

Om du vill lägga till en karusellmodul på en ny sida och ställa in de obligatoriska egenskaperna följer du stegen nedan.

1. Skapa en sidmall som har namnet **karusellmall**.
1. I facket **Brödtext**, lägg till en **standardsida**-modul.
1. Checka in mallen och publicera den. 
1. Använd den karusellmall som du just skapade för att skapa en sida med namnet **karusellsida**.
1. Lägg till platsen **Huvud** på ny sida, lägg till en behållarmodul. 
1. I fönstret till höger, ange värdet **Bredd** till **Fyll skärm**.
1. Under **Siddisposition**, lägg till en karusellmodul i behållarmodulen.
1. I karusellmodulen, lägg till en innehållsblockmodul. Ställ in egenskaperna för innehållsblockmodulen genom att ange **rubrik**, **länk**, **layout** och andra egenskaper.
1. Lägg till och konfigurera en annan innehållsblockmodul.
1. Ställ in ytterligare egenskaper för karusellmodulen som du behöver.
1. Spara och förhandsgranska sidan. Sidan ska innehålla en karusell med två moduler inuti (en fokusmodul och en funktionsmodul). Du kan ändra ytterligare egenskaper för karusell-, fokus- och funktionsmoduler för att uppnå önskad effekt.
1. Avsluta redigeringen av sidan och publicera den.

## <a name="additional-resources"></a>Ytterligare resurser

[Startpaket – översikt](starter-kit-overview.md)

[Annonsbanderollmodul](add-alert.md)

[Textblockmodul](add-content-rich-block.md)

[Innehållsblockmodul](add-hero-module.md)

[Modul för videospelare](add-video-player.md)
