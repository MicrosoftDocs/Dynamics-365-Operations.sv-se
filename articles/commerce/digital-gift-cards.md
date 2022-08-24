---
title: Digitala presentkort för näthandel
description: I denna artikel beskrivs hur digitala presentkort fungerar i näthandelsimplementeringar av Microsoft Dynamics 365 Commerce. Det ger också en översikt över viktiga konfigurationssteg.
author: anupamar-ms
ms.date: 05/27/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.15
ms.search.industry: ''
ms.search.form: ''
ms.openlocfilehash: b31ef231ea56f1c3d2fc199bb0a19bd0c991dc8b
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9270008"
---
# <a name="e-commerce-digital-gift-cards"></a>Digitala presentkort för näthandel

[!include [banner](includes/banner.md)]

I denna artikel beskrivs hur digitala presentkort fungerar i näthandelsimplementeringar av Microsoft Dynamics 365 Commerce. Det ger också en översikt över viktiga konfigurationssteg.

I Dynamics 365 Commerce följer köp av digitala presentkort samma flöde som köp av andra produkter i systemet. Inga ytterligare moduler behöver konfigureras. Om flera presentkort läggs till i kundvagnen, samlas inte presentkortsartiklarna på en och samma försäljningsrad. Detta beteende krävs det eftersom varje enskild försäljningsrad faktureras med ett separat presentkortsnummer.

Inköp av digitala presentkort stöds i Dynamics 365 Commerce version 10.0.16 och senare.

I följande bild visas ett exempel på produktinformationssidan (PDP) för ett digitalt presentkort på Fabrikams näthandelssajt.

![Exempel på ett digitalt presentkorts-PDP på Fabrikams näthandelssajt.](./media/GiftcardPDP.PNG)

## <a name="turn-on-the-digital-gift-card-feature-in-commerce-headquarters"></a>Aktivera funktionen för digitala presentkort i Commerce headquarters

För att inköpsflödet för digitala presentkort ska fungera i Dynamics 365 Commerce måste funktionen **Köpa presentkort i funktion för näthandel** vara aktiverad i Commerce headquarters. Du hittar dunktionen i arbetsytan **Funktionshantering** i Commecer-administrationen enligt följande illustration.

![Arbetsytan Funktionshantering i Commerce headquarters.](./media/Featureflag.PNG)

## <a name="configure-a-digital-gift-card-in-commerce-headquarters"></a>Konfigurera ett digitalt presentkort i Commerce headquarters

Digitala presentkortprodukter bör konfigureras i Commerce headquarters. Processen liknar processen för att skapa andra produkten. Följande viktiga steg är dock specifika för konfigurationen av presentkort för inköp. Mer information om hur du skapar och konfigurerar produkter finns i [Skapa en ny produkt i Commerce](create-new-product-commerce.md).

- När du konfigurerar digitala presentkortprodukter i dialogrutan **Ny produkt** anger du ältet **Produkttyp** som **Tjänst**. (Om du vill öppna dialogrutan går du till **Butik och handel \> PRodukter och kategorier \> Produkter efter kategori** och väljer sedan **Ny**.) Produkter av typen **Tjänst** kontrolleras inte för tillgängligt lager innan en order läggs. Mer information finns i [Skapa en ny produkt](create-new-product-commerce.md#create-a-new-product).
- På sidan **Parametrar för Commerce**, på fliken **Bokföring**, måste fältet **Presentkortprodukt** anges som **Digitalt presentkort** enligt följande illustration. Mer information om produkten är ett externt presentkort finns i [Stöd för externa presentkort](./dev-itpro/gift-card.md).

    ![Produktfält för presentkort i Commerce headquarters.](./media/PostGiftcard.png)

- Om ett presentkort måste ha stöd för flera fördefinierade belopp (till exempel 25, 50 respektive 100 USD) ska dimensionen **Storlek** användas för att konfigurera dessa fördefinierade belopp. Varje enskilt fördefinierat belopp kommer att vara en produktvariant. Mer information finns i [Produktdimensioner](../supply-chain/pim/product-dimensions.md?toc=%2fdynamics365%2fretail%2ftoc.json).
- Om kunderna måste kunna ange ett anpassat belopp för ett presentkort utöver fördefinierade belopp måste du först skapa en variant som tillåter ett anpassat belopp. Attributet **Storlek** har stöd för anpassade beloppsvarianter. Öppna sedan produkten från sidan **Frisläppta produkter i kategori** innan du på snabbfliken **Commerce** anger fältet **Ange pris** som **Måste ange nytt pris**, enligt följande exempelillustration. Denna inställning garanterar att kunderna kan ange ett pris när de bläddrar i produkten på en PDP.

    ![Fältet Ange pris i Commerce headquarters.](./media/KeyInPrice.png)
    
    I följande exempelillustrationen visas en lista över digitala presentkortsproduktvarianter i Commerce headquarters, inklusive två anpassade prisvarianter.
    ![Exempel på digitala presentkortsvarianter med anpassade prisvarianter](./media/DigitalGiftCards_ProductVariantsWithCustom.png)

- Leveranssättet för ett digitalt presentkort måste vara **Elektroniskt**. På sidan **Leveranssätt** (**Retail och commerce \> Kanalinställningar \> Leveranssätt**) väljer du leveranssättet **Elektroniskt** i listpanelen innan du lägger till den digitala presentkortprodukten i rutnätet på snabbfliken **Produkter** enligt följande illustration. Mer information finns i [Konfigurera leveranssätt](/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).

    ![Digitala presentkortprodukter på sidan Leveranssätt i Commerce headquarters.](./media/ElectronicMode.PNG)
    
- Kontrollera att en online-funktionsprofil har skapats och associerats med din onlinebutik i Commerce headquarters. Ställ in alternativet **Aggregera produkter** som **Ja**. Denna inställning garanterar att alla artiklar utom presentkort aggregeras. Mer information finns i [Skapa en online-funktionsprofil](online-functionality-profile.md).
- Om du vill försäkra dig om att kunderna får ett e-postmeddelande efter att ett presentkort fakturerats, skapar du ett nytt e-postmeddelande på sidan **Profiler för e-postmeddelanden** och anger fältet **E-postmeddelandetyp** som **Utfärda presentkort**. Mer information finns i [Konfigurera profil för e-postmeddelande](email-notification-profiles.md).

## <a name="add-product-images-to-the-commerce-site-builder-media-library"></a>Lägg till produktbilder i mediabiblioteket för Commerce-webbplatsbyggaren

Du måste lägga till produktbilder för digitala presentkortprodukter i mediabiblioteket för Commerce-webbplatsbyggaren. Se till att filnamnen på presentkortbildfilerna följer webbplatsens namnkonventioner för produktbilder. Mer information finns i [Ladda upp bilder](dam-upload-images.md).

## <a name="configure-a-custom-amount-for-a-digital-gift-card-in-commerce-site-builder"></a>Konfigurera ett anpassat belopp för ett digitalt presentkort i Commerce-webbplatsbyggaren

Om ett digitalt presentkort har konfigurerats för att tillåta ett anpassat belopp, måste detta beteende också aktiveras i den [modul för inköpsruta](add-buy-box.md) som använd på webbplatsens PDP:er. Modulen för inköpsruta stöder modulkonfiguration i syfte att tillåta anpassade belopp. Du kan också definiera tillåtna minimi- och maximibelopp för anpassade belopp.

Följ dessa steg om du vill konfigurera ett anpassat belopp för ett digitalt presentkort i Commerce-webbplatsbyggaren.

1. Gå till modulen för inköpsruta som används på webbplatsens PDP:er. Denna modul för inköpsruta kan implementeras i ett fragment, i en mall eller på en sida.
1. Välj **Redigera**.
1. I egenskapsfönstret till höger väljer du kryssrutan **Tillåt anpassat pris**.
1. Valfritt: Om du vill definiera minimi- och maximibelopp för anpassade belopp anger du belopp under **Minimipris** och **Maximipris**.
1. Välj **Avsluta redigering** och sedan **Publicera**.

## <a name="additional-resources"></a>Ytterligare resurser

[Modul för inköpsruta](add-buy-box.md)

[Kassamodul](add-checkout-module.md)

[Kundvagnsmodul](add-cart-module.md)

[Skapa en ny produkt i Commerce](create-new-product-commerce.md)

[Ställ in leveranssätt](/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery)

[Produktdimensioner](../supply-chain/pim/product-dimensions.md?toc=%2fdynamics365%2fretail%2ftoc.json)

[Ställa in en meddelandeprofil för e-post](email-notification-profiles.md)

[Skapa en onlinefunktionsprofil](online-functionality-profile.md)

[Stöd för externa presentkort](./dev-itpro/gift-card.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
