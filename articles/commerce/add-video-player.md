---
title: Modul för videospelare
description: Det här avsnittet handlar om moduler för videospelare och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 01/23/2020
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
ms.openlocfilehash: e94658eed12b12d6666e63d2c06b86646c81a120
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025685"
---
# <a name="video-player-module"></a>Modul för videospelare


[!include [banner](includes/banner.md)]

Det här avsnittet handlar om moduler för videospelare och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

Modulen för videospelare används för att stödja videouppspelning. Den kan läggas till på vilken sida som helst, förutsatt att videoinnehållet överförs till och är tillgängligt i innehållshanteringssystem (CMS). Videospelarmodulen stöder mediatypen. mp4.

## <a name="video-player-module"></a>Modul för videospelare

Videospelaren kan användas för att visa videofilmer på en näthandelsplats. Den har stöd för alla uppspelningsfunktioner, till exempel spela upp, pausa, fullstorleksläge, ljudbeskrivningar och dold textning. Videospelarmodulen stöder också anpassning av textning för att möta Microsofts tillgänglighetsstandarder. Du kan till exempel anpassa teckenstorleken och bakgrundsfärgen.

Videospelarmodulen stöder också sekundära ljudspår. När en video laddas upp till CMS kan även ett sekundärt ljudspår laddas upp. Videospelarmodulen kan sedan spela upp det sekundära ljudspåret om en användare väljer det.

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
| Spela upp på helskärm       | **Sant** eller **falskt**               | När värdet är inställt på **Sant** spelas videon upp i helskärmsläge. |
| Utlösare för spela upp och pausa    | **Sant** eller **falskt**               | När värdet är inställt på **Sant** visas en spela upp/pausa-knapp på videon. |
| Kontroller för videospelare | **Sant** eller **falskt**               | När värdet är inställt på **Sant** visas alla videospelarkontroller. Dessa kontroller omfattar både spela upp och paus-knappar, en förloppsindikator och en dold textning. |
| Dölj affischbild     | **Sant** eller **falskt**               | Ett videoklipp kan ha en affischram. När värdet för den här egenskapen har angetts till **Sant**döljs affischramen. |
| Masknivå            | Ett nummer mellan **0** och **100** | Den mask som används på videon som ska formateras. |

## <a name="add-a-video-player-module-to-a-page"></a>Lägg till en videospelarmodul till en sida

> [!NOTE] 
> Innan du skapar en videospelarmodul måste du först överföra en video till mediebiblioteket.

Om du vill lägga till en modul för videospelare på en ny sida och ställa in de obligatoriska egenskaperna följer du stegen nedan.

1. Skapa en sidmall som har namnet **videospelarmall**.
1. Lägg till platsen **Huvud** på standardsida, lägg till en behållarmodul.
1. Lägg till videospelare och modul för videospelare i behållarmodulen.
1. Avsluta redigeringen i mallen och publicera den.
1. Använd den videospelarmall som du skapade för att skapa en sida med namnet **videospelarsida**.
1. Lägg till platsen **Huvud** på den nya sidan, lägg till en modul för videospelare.
1. Välj **Lägg till en video** i egenskapsrutan för videospelarmodulen.
1. I dialogrutan **medieväljare**, välj en video och välj sedan **Överför nytt mediobjekt**.
1. Spara och förhandsgranska sidan. Du bör se videomodulerna på sidan. Du kan ändra ytterligare inställningar om du vill anpassa funktionen för modulen.
1. Avsluta redigeringen av sidan och publicera den.

## <a name="additional-resources"></a>Ytterligare resurser

[Startpaket – översikt](starter-kit-overview.md)

[Annonsbanderollmodul](add-alert.md)

[Karusellmodul](add-carousel.md)

[Textblockmodul](add-content-rich-block.md)

[Innehållsblockmodul](add-hero-module.md)
