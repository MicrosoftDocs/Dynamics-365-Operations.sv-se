---
title: Modul för videospelare
description: Det här avsnittet handlar om moduler för videospelare och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
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
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 32504351f712c83ba8f593c17d2e51c532374311
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785339"
---
# <a name="video-player-module"></a>Modul för videospelare

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Det här avsnittet handlar om moduler för videospelare och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

Moduler för videospelare används för att stödja videouppspelning. Två moduler för videospelare finns i butikens startpaket: modulen för omgivande videospelaren och modulen för videospelaren. Båda spelarna stöder medietypen .mp4.

## <a name="ambient-video-player-module"></a>Modulen för omgivande videospelaren

Modulen för omgivande videospelare har stöd för korta informationsvideoklipp. Den bör användas för videoklipp som är mindre än fem sekunder långa. Denna spelare har stöd för begränsade videouppspelningsfunktioner, t.ex. uppspelning och paus.

### <a name="examples-of-ambient-video-player-modules-in-e-commerce"></a>Exempel på moduler i omgivande videopelare i e-handel

- Korta informationsvideor som markerar nya produkter på startsidan
- Korta informationsvideor som markerar produktegenskaper på en produktinformationssida

### <a name="ambient-video-player-module-properties"></a>Egenskaper för modul för omgivande videospelare

| Egenskapsnamn     | Värde                 | Beskrivning |
|-------------------|-----------------------|-------------|
| Spela upp automatiskt          | **Sant** eller **falskt** | När värdet är inställt på **Sant** spelas videon upp automatiskt. |
| Ljud av              | **Sant** eller **falskt** | När värdet är inställt på **Sant** stängs ljudet av. För den här spelaren är standardvärdet **Sant**. I webbläsaren Google Chrome är automatiska videor avstängda som standard och ljudet spelas endast upp om användaren spelar upp videon manuellt. |
| Slinga              | **Sant** eller **falskt** | När värdet är inställt på **Sant** spelas videon upprepat i en slinga. |
| Medier             |  Videofilsökväg och namn. | Videofilen som spelas upp av videospelaren. |
| Uppspelningskontroller | **Sant** eller **falskt** | När värdet är inställt på **Sant** visas en spela upp/pausa-knapp på videon. Om värdet är inställt på **Sant** visas inte knappen spela upp/pausa, men användarna kan fortfarande pausa och återuppta uppspelningen med hjälp av tangentbordet. |

## <a name="video-player-module"></a>Modul för videospelare

Videospelaren kan användas för att visa videofilmer på en näthandelsplats. Den har stöd för alla uppspelningsfunktioner, till exempel spela upp, pausa, fullstorleksläge och dold textning. Videospelarmodulen stöder också anpassning av textning för att möta Microsofts tillgänglighetsstandarder. Du kan till exempel anpassa teckenstorleken och bakgrundsfärgen.

### <a name="examples-of-video-player-modules-in-e-commerce"></a>Exempel på moduler i videopelare i e-handel

- Visa videoklipp på produktinformationssidor eller på marknadsföringssidor
- Reklamfilmer eller videoklipp om policyer på alla marknadsföringssidor
- Marknadsföringsvideor som markerar produktegenskaper på produktinformationssidor eller på marknadsföringssidor

### <a name="video-player-module-properties"></a>Egenskaper för videospelarmodul

| Egenskapsnamn         | Värde                               | Beskrivning |
|-----------------------|-------------------------------------|-------------|
| Spela upp automatiskt             | **Sant** eller **falskt**               | När värdet är inställt på **Sant** spelas videon upp automatiskt. |
| Ljud av                  | **Sant** eller **falskt**               | När värdet är inställt på **Sant** stängs ljudet av. För den här spelaren är standardvärdet **Falskt**. I webbläsaren Chrome är automatiska videor avstängda som standard och ljudet spelas endast upp om användaren spelar upp videon manuellt. |
| Slinga                  | **Sant** eller **falskt**               | När värdet är inställt på **Sant** spelas videon upprepat i en slinga. |
| Medier                 | Videofilsökväg och namn. | Videofilen som spelas upp av videospelaren. |
| Uppspelningskontroller     | **Sant** eller **falskt**               | När värdet är inställt på **Sant** visas en spela upp/pausa-knapp på videon. Om värdet är inställt på **Sant** visas inte knappen spela upp/pausa, men användarna kan fortfarande pausa och återuppta uppspelningen med hjälp av tangentbordet. |
| Spela upp på helskärm       | **Sant** eller **falskt**               | När värdet är inställt på **Sant** spelas videon upp i helskärmsläge. |
| Kontroller              | **Sant** eller **falskt**               | När värdet är inställt på **Sant** visas alla kontroller. Dessa kontroller omfattar både spela upp och paus-knappar, en förloppsindikator och en dold textning. |
| Dölj affischram     | **Sant** eller **falskt**               | Ett videoklipp kan ha en affischram. När värdet för den här egenskapen har angetts till **Sant**döljs affischramen. |
| Masknivå            | Ett nummer mellan **0** och **100** | Den mask som används på videon som ska formateras. |
| Ikonformat för helskärm | **Ruta** eller **pil**             | Formatet för den helskärmsikon som visas i videospelaren. |

## <a name="add-a-video-player-module-to-a-page"></a>Lägg till en videospelarmodul till en sida

Om du vill lägga till en modul för videospelare på en ny sida och ställa in de obligatoriska egenskaperna följer du stegen nedan.

1. Skapa en sidmall som har namnet **videospelarmall**.
1. Lägg till platsen **Huvud** på standardsida, lägg till en behållarmodul.
1. Lägg till videospelare och modul för videospelare i behållarmodulen.
1. Checka in mallen och publicera den.
1. Använd den videospelarmall som du just skapade för att skapa en sida med namnet **videospelarsida**.
1. Lägg till platsen **Huvud** på den nya sidan, lägg till en modul för omgivande videospelare.
1. Gå till **Media** i inställningar för modul för omgivande videospelare och överför en videofil. Du kan ändra **Spela upp automatiskt**, **Slinga** och andra egenskaper som behövs.
1. Spara och förhandsgranska sidan.
1. Lägg till platsen **Huvud** på den nya sidan, lägg till en modul för videospelare.
1. Gå till **Media** i inställningar för modul för videospelare och överför en videofil.
1. Spara och förhandsgranska sidan. Du bör se båda videomodulerna på sidan. Du kan ändra ytterligare inställningar om du vill anpassa funktionen för varje modul.
1. Checka in sidan och publicera den.

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över startpaket](starter-kit-overview.md)

[Notifieringsmodul](add-alert.md)

[Karusellmodul](add-carousel.md)

[Innehållsrik blockmodul](add-content-rich-block.md)

[Modul för innehållsplacering](add-content-placement-modules.md)

[Funktionsmodul](add-feature-module.md)

[Fokusmodul](add-hero-module.md)
