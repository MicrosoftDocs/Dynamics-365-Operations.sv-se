---
title: Modul för videospelare
description: Det här avsnittet handlar om moduler för videospelare och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 13072c8d6839fef1ab0dd55d626c23a2a1084d4d
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5209189"
---
# <a name="video-player-module"></a>Modul för videospelare

[!include [banner](includes/banner.md)]

Det här avsnittet handlar om moduler för videospelare och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.

Modulen för videospelare används för att stödja videouppspelning. Den kan läggas till på vilken sida som helst, förutsatt att videoinnehållet överförs till och är tillgängligt i innehållshanteringssystem (CMS). Videospelarmodulen stöder mediatypen. mp4.

## <a name="video-player-module"></a>Modul för videospelare

Videospelaren kan användas för att visa videofilmer på en näthandelssajt. Den har stöd för alla uppspelningsfunktioner, till exempel spela upp, pausa, fullstorleksläge, ljudbeskrivningar och dold textning. Videospelarmodulen stöder också anpassning av textning för att möta Microsofts tillgänglighetsstandarder. Du kan till exempel anpassa teckenstorleken och bakgrundsfärgen.

Videospelarmodulen stöder också sekundära ljudspår. När en video laddas upp till CMS kan även ett sekundärt ljudspår laddas upp. Videospelarmodulen kan sedan spela upp det sekundära ljudspåret om en användare väljer det.

### <a name="examples-of-video-player-modules-in-e-commerce"></a>Exempel på moduler i videopelare i näthandel

- Visa videoklipp på produktinformationssidor eller på marknadsföringssidor
- Reklamfilmer eller videoklipp om policyer på alla marknadsföringssidor
- Marknadsföringsvideor som markerar produktegenskaper på produktinformationssidor eller på marknadsföringssidor

Följande bild visar ett exempel på en modul för videospelare på en startsida.

![Exempel på en videospelar-modul](./media/ecommerce-videoplayer.PNG)

### <a name="video-player-module-properties"></a>Egenskaper för videospelarmodul

| Egenskapsnamn         | Värde                               | beskrivning |
|-----------------------|-------------------------------------|-------------|
| Spela upp automatiskt             | **Sant** eller **falskt**               | När värdet är inställt på **Sant** spelas videon upp automatiskt. |
| Ljud av                  | **Sant** eller **falskt**               | När värdet är inställt på **Sant** stängs ljudet av. För den här spelaren är standardvärdet **Falskt**. I webbläsaren Chrome är automatiska videor avstängda som standard och ljudet spelas endast upp om användaren spelar upp videon manuellt. |
| Slinga                  | **Sant** eller **falskt**               | När värdet är inställt på **Sant** spelas videon upprepat i en slinga. |
| Medier                 | Videofilsökväg och namn. | Videofilen som spelas upp av videospelaren. |
| Spela upp på helskärm       | **Sant** eller **falskt**               | När värdet är inställt på **Sant** spelas videon upp i helskärmsläge. |
| Utlösare för spela upp och pausa    | **Sant** eller **falskt**               | När värdet är inställt på **Sant** visas en spela upp/pausa-knapp på videon. |
| Kontroller för videospelare | **Sant** eller **falskt**               | När värdet är inställt på **Sant** visas alla videospelarkontroller. Dessa kontroller omfattar både spela upp och paus-knappar, en förloppsindikator och en dold textning. |
| Dölj affischbild     | **Sant** eller **falskt**               | Ett videoklipp kan ha en affischram. När värdet för den här egenskapen har angetts till **Sant** döljs affischramen. |
| Masknivå            | Ett nummer mellan **0** och **100** | Den mask som används på videon som ska formateras. |

## <a name="add-a-video-player-module-to-a-page"></a>Lägg till en videospelarmodul till en sida

> [!NOTE] 
> Innan du skapar en videospelarmodul måste du först överföra en video till mediebiblioteket.

Om du vill lägga till en modul för videospelare på en ny sida och ställa in de obligatoriska egenskaperna följer du stegen nedan.

1. Gå till **mallar** och välj sedan **ny** för att skapa en ny mall.
1. I dialogrutan **Ny mal** under **Mallnamn**, ange **mall för videospelare** och välj sedan **OK**.
1. I facket **brödtext** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.
1. I dialogrutan **Lägg till modul**, välj modulen **Standardsida** och klicka sedan på **OK**.
1. I platsen **Huvud** i modulen **Standardsida** markerar du ellipsknappen (**...**) och väljer sedan **Lägg till modul**.
1. I dialogrutan **Lägg till modul**, välj modulen **Behållare** och klicka sedan på **OK**.
1. I facket **behållare** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.
1. I dialogrutan **Lägg till modul**, välj modulen **Videospelare** och klicka sedan på **OK**.
1. Välj **Spara**, välj **Slutför redigering** för att checka in mallen och välj sedan **publicera** för att publicera den. 
1. Gå till **Sidor** och välj **nytt sidfragment** för att skapa en ny sida.
1. I dialogrutan **Välj en mall**, välj den videospelarmall du skapade. Under **sidnamn**, ange **Videospelarsida** och klicka sedan på **OK**.
1. I platsen för nya sidan väljer du **Huvud**, markerar ellipsknappen (**...**) och väljer sedan **Lägg till modul**.
1. I dialogrutan **Lägg till modul**, välj modulen **Behållare** och klicka sedan på **OK**.
1. I facket **behållare** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.
1. I dialogrutan **Lägg till modul**, välj modulen **Videospelare** och klicka sedan på **OK**.
1. Välj **Lägg till en video** i egenskapsrutan för videospelarmodulen.
1. I dialogrutan **medieväljare**, välj en video och välj sedan **Överför nytt mediobjekt**.
1. Markera en videofil i Utforskaren och välj sedan **öppna**.
1. I dialogrutan **Överför medieartiklar** ange en rubrik och övrig information efter behov och välj sedan **OK**.
1. I dialogrutan **Mediaväljare**, välj **Stäng**.
1. Klicka på **Spara** och välj **Förhandsgranska** för att förhandsgranska sidan. Du bör se videomodulerna på sidan. Du kan ändra ytterligare inställningar om du vill anpassa funktionen för modulen.
1. Välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den. 

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över modulbibliotek](starter-kit-overview.md)

[Modul med kampanjbanderoll](add-alert.md)

[Karusellmodul](add-carousel.md)

[Textblockmodul](add-content-rich-block.md)

[Innehållsblockmodul](add-hero-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]