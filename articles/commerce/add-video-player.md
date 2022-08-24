---
title: Modul för videospelare
description: Denna artikel handlar om moduler för videospelare och beskriver hur du lägger till dem på webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 919446981f7439d61b01deb57b206cd457eed919
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9269305"
---
# <a name="video-player-module"></a>Modul för videospelare

[!include [banner](includes/banner.md)]

Denna artikel handlar om moduler för videospelare och beskriver hur du lägger till dem på webbsidorna i Microsoft Dynamics 365 Commerce.

Modulen för videospelare används för att stödja videouppspelning. Den kan läggas till på vilken sida som helst, förutsatt att videoinnehållet överförs till och är tillgängligt i innehållshanteringssystem (CMS). Videospelarmodulen stöder mediatypen. mp4.

## <a name="video-player-module"></a>Modul för videospelare

Videospelaren kan användas för att visa videofilmer på en näthandelssajt. Den har stöd för alla uppspelningsfunktioner, till exempel spela upp, pausa, fullstorleksläge, ljudbeskrivningar och dold textning. Videospelarmodulen stöder också anpassning av textning för att möta Microsofts tillgänglighetsstandarder. Du kan till exempel anpassa teckenstorleken och bakgrundsfärgen.

Videospelarmodulen stöder också sekundära ljudspår. När en video laddas upp till CMS kan även ett sekundärt ljudspår laddas upp. Videospelarmodulen kan sedan spela upp det sekundära ljudspåret om en användare väljer det.

### <a name="examples-of-video-player-modules-in-e-commerce"></a>Exempel på moduler i videopelare i näthandel

- Visa videoklipp på produktinformationssidor eller på marknadsföringssidor
- Reklamfilmer eller videoklipp om policyer på alla marknadsföringssidor
- Marknadsföringsvideor som markerar produktegenskaper på produktinformationssidor eller på marknadsföringssidor

Följande bild visar ett exempel på en modul för videospelare på en startsida.

![Exempel på en videospelarmodul.](./media/ecommerce-videoplayer.PNG)

### <a name="video-player-module-properties"></a>Egenskaper för videospelarmodul

| Egenskapsnamn         | Värde                               | beskrivning |
|-----------------------|-------------------------------------|-------------|
| Rubrik               | Rubriktext och rubriktagg (**H1**, **H2**, **H3**, **H4**, **H5** eller **H6**) | Som standard används rubriktaggen **H2** för rubriken, men taggen kan ändras i syfte att uppfylla tillgänglighetskraven. |
| RTF-format             | Stycketext | Modulen har stöd för stycketext i RTF-format. Vissa grundläggande RTF-funktioner stöds, t.ex. hyperlänkar samt fetstil, understrykning och kursiv text. Vissa av dessa funktioner kan åsidosättas av det sidtema som används i modulen. |
| Länka                  | Länktext, länk-URL, ARIA-etikett (Accessible Rich Internet Applications) samt väljaren **Öppna länk i ny flik** | Modulen stöder en eller flera "uppmaning till åtgärd"-länkar. Om en länk läggs till, en länktext, en URL-adress och en ARIA-etikett krävs. ARIA-etiketter ska vara beskrivande i syfte att uppfylla tillgänglighetskraven. Länkar kan konfigureras så att de öppnas på en ny flik. |
| Undertext              | Rubrik, text eller länkar | Du kan lägga till ytterligare kontext för videospelaren, till exempel namnet på författaren eller designern, eller länkar till personliga bloggar. |
| Spela upp automatiskt             | **Sant** eller **falskt**               | När värdet är inställt på **Sant** spelas videon upp automatiskt. |
| Ljud av                  | **Sant** eller **falskt**               | När värdet är inställt på **Sant** stängs ljudet av. För den här spelaren är standardvärdet **Falskt**. I webbläsaren Chrome är automatiska videor avstängda som standard och ljudet spelas endast upp om användaren spelar upp videon manuellt. |
| Slinga                  | **Sant** eller **falskt**               | När värdet är inställt på **Sant** spelas videon upprepat i en slinga. |
| Medier                 | Videofilsökväg och namn. | Videofilen som spelas upp av videospelaren. |
| Spela upp på helskärm       | **Sant** eller **falskt**               | När värdet är inställt på **Sant** spelas videon upp i helskärmsläge. |
| Utlösare för spela upp och pausa    | **Sant** eller **falskt**               | När värdet är inställt på **Sant** visas en spela upp/pausa-knapp på videon. |
| Kontroller för videospelare | **Sant** eller **falskt**               | När värdet är inställt på **Sant** visas alla videospelarkontroller. Dessa kontroller omfattar både spela upp och paus-knappar, en förloppsindikator och en dold textning. |
| Dölj affischbild     | **Sant** eller **falskt**               | Ett videoklipp kan ha en affischram. När värdet för den här egenskapen har angetts till **Sant** döljs affischramen. |
| Masknivå            | Ett nummer mellan **0** och **100** | Den mask som används på videon som ska formateras. |

> [!IMPORTANT]
> Egenskaperna **Rubrik**, **RTF-text**, **Länk** och **Undertext** är tillgängliga från och med Dynamics 365 Commerce-version 10.0.20.

## <a name="add-a-video-player-module-to-a-page"></a>Lägg till en videospelarmodul till en sida

> [!NOTE] 
> Innan du skapar en videospelarmodul måste du först överföra en video till mediebiblioteket.

Om du vill lägga till en modul för videospelare på en ny sida och konfigurera de obligatoriska egenskaperna följer du stegen nedan.

1. Gå till **mallar** och välj sedan **ny** för att skapa en ny mall.
1. I dialogrutan **Ny mal** under **Mallnamn**, ange **mall för videospelare** och välj sedan **OK**.
1. I facket **brödtext** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.
1. I dialogrutan **Välj moduler**, välj modulen **Standardsida** och klicka sedan på **OK**.
1. I platsen **Huvud** i modulen **Standardsida** markerar du ellipsknappen (**...**) och väljer sedan **Lägg till modul**.
1. I dialogrutan **Välj moduler**, välj modulen **Behållare** och klicka sedan på **OK**.
1. I facket **behållare** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.
1. I dialogrutan **Välj moduler**, välj modulen **Videospelare** och klicka sedan på **OK**.
1. Välj **Spara**, välj **Slutför redigering** för att checka in mallen och välj sedan **publicera** för att publicera den. 
1. Gå till **Sidor** och välj **nytt sidfragment** för att skapa en ny sida.
1. I dialogrutan **Skapa en ny sida** under **Sidnamn**, ange **Videospelarsida** och välj sedan **Nästa**.
1. Under **Välj en mall**, välj mallen **Videospelarmall** som du skapade och välj sedan **Nästa**.
1. Under **Välj en layout** väljer du en sidlayout (till exempel **Flexibel layout**) och väljer sedan **Nästa**.
1. Under **Granska och slutför**, granska sidkonfiguration. Om du behöver redigera sidinformationen väljer du **Bakåt**. Om sidinformationen är korrekt väljer du **Skapa sida**.
1. I platsen för nya sidan väljer du **Huvud**, markerar ellipsknappen (**...**) och väljer sedan **Lägg till modul**.
1. I dialogrutan **Välj moduler**, välj modulen **Behållare** och klicka sedan på **OK**.
1. I facket **behållare** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.
1. I dialogrutan **Välj moduler**, välj modulen **Videospelare** och klicka sedan på **OK**.
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
