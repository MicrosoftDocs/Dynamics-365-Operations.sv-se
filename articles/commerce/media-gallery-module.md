---
title: Modul för mediegalleri
description: Denna artikel handlar om moduler för mediegalleri och beskriver hur du lägger till dem på webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.13
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 5e2d0a4422341badee906c71bebdd491e18a38cc
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9273469"
---
# <a name="media-gallery-module"></a>Modul för mediegalleri

[!include [banner](includes/banner.md)]

Denna artikel handlar om moduler för mediegalleri och beskriver hur du lägger till dem på webbsidorna i Microsoft Dynamics 365 Commerce.

I modul för mediegalleri visas en eller flera bilder i en vy i ett galleri. Modul för mediegalleri stöder miniatyrbilderna som antingen ordnas vågrätt (som en rad under bilden) eller lodrätt (som en kolumn bredvid bilden). Moduler för mediagalleri ger också möjligheter som gör att bilder kan zoomas in (förstoras) eller visas i helskärmsläge. För att återges i modulen mediegalleri måste en bild vara tillgänglig i webbplatsskaparen för Commerce mediebibliotek. För närvarande stöder modulen mediegalleri endast bilder.

I standardläget använder modulen mediegalleri det produkt-ID som finns i sidkontexten på en produktinformationssida (PDP) för att återge motsvarande produktbilder. I Commerce headquarters måste en mediefilsökväg anges för alla produkter. Bilder ska sedan överföras till webbplatsskaparen för mediebibliotek enligt den filsökväg som definierats för produkterna i Commerce headquarters. Dessa bilder omfattar bilder för produkter och alla produktvarianter. Mer information om hur du överför bilder till webbplatsskaparen för mediebibliotek finns i [överför bilder](dam-upload-images.md).

Alternativt kan modulen mediegalleri vara värd för en helt granskad uppsättning bilder på en bildgallerisida, där det inte finns några beroenden för produkt-ID eller sidkontext. I det här fallet måste bilder överföras till webbplatsskaparen för mediebibliotek och anges i webbplatsskaparen.

Här följer några användarexempel på moduler för mediegalleri:

- Återge produktbilder på ett PDP
- Återge produktbilder på en produkt marknadsföringssida
- Visa en granskad uppsättning bilder på en marknadsföringssida, t.ex. en gallerisida

I exemplet nedan är en inköpsrruta på ett PDP-program värd för produktbilder med hjälp av modulen mediegalleri.

![Exempel på en inköpsruta på en produktinformationssida som är värd för produktbilder med hjälp av en modul för mediegalleri.](./media/ecommerce-pdp-buybox.PNG)

## <a name="media-gallery-properties"></a>Egenskaper för mediegalleri

| Egenskapsnamn | Värden | beskrivning |
|---------------|--------|-------------|
| Bildkälla | **Sidkontext** eller **produkt-ID** | Standardvärdet är **sidkontext**. Om **sidkontext** väljs förväntar modulen att sidan med produkt-ID-information. Om **produkt-ID** väljs måste produkt-ID:t för en avbildning anges som värdet för egenskapen **produkt-ID**. Den här funktionen är tillgänglig i Commerce version 10.0.12. |
| Produkt-ID | En produkt ID | Den här egenskapen används endast om värdet på egenskapen **bildkälla** är **produkt-ID**. |
| Bildzoomning | **Infogad** eller **behållare** | Med den här egenskapen kan användaren zooma bilder i modulen mediegalleri. En bild kan antingen zoomas in eller i en separat behållare bredvid bilden. Denna funktion blir 10.0.12. |
| Zoomningsfaktor | Ett decimalnummer | Den här egenskapen anger skalningsfaktorn för zoomning av bilder. Om värdet till exempel är inställt på **2,5** blir bilderna för stora än 2,5 gånger. |
| Helskärm | **Sant** eller **falskt** | Den här egenskapen anger om bilder kan visas i helskärmsläge. I helskärmsläge kan bilder också förstoras ytterligare om zoomningsfunktionen är aktiverad. Denna funktion är tillgänglig i Commerce version 10.0.13. |
| Zoomad bildkvalitet | Ett värde från 1 till 100 som motsvarar en procentsats och som väljs med hjälp av ett styrfält. | Egenskapen definierar bildkvaliteten för inzoomade bilder. Denna kan ställas in på 100 procent om du vill att en zoomad bild alltid ska använda den högsta möjliga upplösningen. Denna egenskap kan inte användas på PNG-filer eftersom dessa använder ett förlustfritt format. Denna funktion är tillgänglig från och med Commerce-versionen 10.0.19. |
| Bilder | Bilder som väljs från webbplatsskaparen för mediebibliotek | Förutom att de återges från en produkt kan bilder granskas för en modulen mediegalleriet. Dessa bilder kommer att läggas till alla produktbilder som finns tillgängliga. Den här funktionen är tillgänglig i Commerce version 10.0.12. |
| Miniatyrorientering | **Lodrät** eller **vågrät** | Den här egenskapen anger om miniatyrbilder ska visas i en lodrät remsa eller som en vågrät remsa. |
| Dölj huvudproduktbilder för variant | **Sant** eller **falskt** | Om denna egenskap anges som **True** kommer, när en variant väljs, bilder på huvudprodukten att döljas såvida varianten inte är bildfri. Egenskapen påverkar inte produkter som inte har några varianter. |
| Uppdatera media vid dimensionsurval | **Sant** eller **falskt** | Om den här egenskapen är inställd på **True**, bilder i mediebiblioteket kommer att uppdateras när någon dimension (t.ex. färg, stil eller storlek) väljs och om en bild är tillgänglig. Denna egenskap underlättar bläddringsupplevelsen eftersom inte alla produktvariantdimensioner måste väljas för att motsvarande bild ska uppdateras. Egenskapen är tillgänglig på fliken **Avancerat**. |

> [!IMPORTANT]
> Egenskapen **Uppdatera media för dimensionsurval är tillgänglig** i versionen 10.0.21 av Commerce-versionen. De kräver att paketversion 9.31 för Commerce-modulens bibliotek är installerad.

Följande illustration visar ett exempel på en modul mediegalleri där helskärms- och zoomningsalternativen är tillgängliga.

![Exempel på en modul för mediegalleri där helskärms- och zoomningsalternativen är tillgängliga.](./media/ecommerce-media-zoom.png)

Följande illustration visar ett exempel på modulen mediegaller som har granskade bilder (dvs. de angivna bilderna är inte beroende av produkt-ID eller sidkontext).

![Exempel på modul för mediegalleri som har granskade bilder.](./media/ecommerce-media-curated.PNG)

## <a name="commerce-scale-unit-interaction"></a>Interaktion för skalningsenhet för handel

När bildkällan hämtas från sidkontexten används produkt-ID:t från PDP för att hämta bilderna. Modulen för mediegalleri hämtar bildsökfilen för produkten med hjälp av API:er för skalningsenhet för Commerce Scale Unit. Bilderna hämtas sedan från mediebiblioteket så att de kan återges i modulen.

## <a name="add-a-media-gallery-module-to-a-page"></a>Lägg till modulen mediegalleri till en sida

För att lägga till en modul för mediegalleri till en marknadsföringssida, följ dessa steg.

1. Gå till **mallar** och välj sedan **ny** för att skapa en ny mall.
1. I dialogrutan **Ny mall** under **Mallnamn**, ange **Marknadsföringsmall** och välj sedan **OK**.
1. I facket **brödtext** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.
1. I dialogrutan **Välj moduler**, välj modulen **Standardsida** och klicka sedan på **OK**.
1. I platsen **Huvud** i standardsida markerar du ellipsknappen (**...**) och väljer sedan **Lägg till modul**.
1. I dialogrutan **Välj moduler**, välj modulen **Behållare** och klicka sedan på **OK**.
1. Välj **Spara**, välj **Slutför redigering** för att checka in mallen och välj sedan **publicera** för att publicera den.
1. Gå till **Sidor** och välj **nytt sidfragment** för att skapa en ny sida.
1. I dialogrutan **Skapa en ny sida** under **Sidnamn**, ange **Sidan mediegalleri** och välj sedan **Nästa**.
1. Under **Välj en mall**, välj mallen **Marknadsföringsmall** som du skapade och välj sedan **Nästa**.
1. Under **Välj en layout** väljer du en sidlayout (till exempel **Flexibel layout**) och väljer sedan **Nästa**.
1. Under **Granska och slutför**, granska sidkonfiguration. Om du behöver redigera sidinformationen väljer du **Bakåt**. Om sidinformationen är korrekt väljer du **Skapa sida**. 
1. I platsen för nya sidan väljer du **Huvud**, markerar ellipsknappen (**...**) och väljer sedan **Lägg till modul**.
1. I dialogrutan **Välj moduler**, välj modulen **Behållare** och klicka sedan på **OK**.
1. I facket **behållare** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.
1. I dialogrutan **Välj moduler** välj modulen **Mediagalleriet** och sedan **OK**.
1. I egenskapsfönstret under **modulen mediegalleri**, välj **Produkt-ID**. I fältet **Produkt-ID** anger du ett produkt-ID.
1. Klicka på **Spara** och välj **Förhandsgranska** för att förhandsgranska sidan. Du bör kunna se bilderna för produkten i en gallerivy.
1. Om du bara vill använda kuraterade bilder i fastighetsfönstret, under **Bidkälla**, välj **Produkt-ID**. Sedan under **Bilden**, välj **Lägg till en bild** så många gånger som krävs för att lägga till bilder från mediebiblioteket.
1. Ange eventuella ytterligare egenskaper som du vill konfigurera t.ex. **Bildzoom**, **Zoomfaktor** och **Miniatyrorientering**.
1. Välj **Spara** när du är klar och välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över modulbibliotek](starter-kit-overview.md)

[Modul för inköpsruta](add-buy-box.md)

[Behållarmodul](add-container-module.md)

[Överför bilder](dam-upload-images.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
