---
title: Digitala presentkort för näthandel
description: I detta ämne beskrivs hur digitala presentkort fungerar i näthandelsimplementeringar av Microsoft Dynamics 365 Commerce. Det ger också en översikt över viktiga konfigurationssteg.
author: anupamar-ms
ms.date: 12/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 212f425dc3603f838ce030d9ed86f2e418bef29a
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6019943"
---
# <a name="e-commerce-digital-gift-cards"></a>Digitala presentkort för näthandel

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

I detta ämne beskrivs hur digitala presentkort fungerar i näthandelsimplementeringar av Microsoft Dynamics 365 Commerce. Det ger också en översikt över viktiga konfigurationssteg.

I Dynamics 365 Commerce följer köp av digitala presentkort samma flöde som köp av andra produkter i systemet. Inga ytterligare moduler behöver konfigureras. Om flera presentkort läggs till i kundvagnen, samlas inte presentkortsartiklarna på en och samma försäljningsrad. Detta beteende krävs det eftersom varje enskild försäljningsrad faktureras med ett separat presentkortsnummer.

Inköp av digitala presentkort stöds i Dynamics 365 Commerce version 10.0.16 och senare.

I följande bild visas ett exempel på produktinformationssidan (PDP) för ett digitalt presentkort på Fabrikams näthandelssajt.

![Exempel på ett digitalt presentkort PDP på Fabrikams näthandelssajt](./media/GiftcardPDP.PNG)

## <a name="turn-on-the-digital-gift-card-feature-in-commerce-headquarters"></a>Aktivera funktionen för digitala presentkort i Commerce-administrationen

För att inköpsflödet för digitala presentkort ska fungera i Dynamics 365 Commerce måste funktionen **Köpa presentkort i funktion för näthandel** vara aktiverad i Commerce-administrationen. Du hittar dunktionen i arbetsytan **Funktionshantering** i Commecer-administrationen enligt följande illustration.

![Arbetsytan Funktionshantering i Commerce-aministrationen](./media/Featureflag.PNG)

## <a name="configure-a-digital-gift-card-in-commerce-headquarters"></a>Konfigurera ett digitalt presentkort i Commerce-administrationen

Digitala presentkortprodukter bör konfigureras i Commerce-administrationen. Processen liknar processen för att skapa andra produkten. Följande viktiga steg är dock specifika för konfigurationen av presentkort för inköp. Mer information om hur du skapar och konfigurerar produkter finns i [Skapa en ny produkt i Commerce](create-new-product-commerce.md).

- När du konfigurerar digitala presentkortprodukter i dialogrutan **Ny produkt** anger du ältet **Produkttyp** som **Tjänst**. (Om du vill öppna dialogrutan går du till **Butik och handel \> PRodukter och kategorier \> Produkter efter kategori** och väljer sedan **Ny**.) Produkter av typen **Tjänst** kontrolleras inte för tillgängligt lager innan en order läggs. Mer information finns i [Skapa en ny produkt](create-new-product-commerce.md#create-a-new-product).
- På sidan **Parametrar för Commerce**, på fliken **Bokföring**, måste fältet **Presentkortprodukt** anges som **Digitalt presentkort** enligt följande illustration. Mer information om produkten är ett externt presentkort finns i [Stöd för externa presentkort](./dev-itpro/gift-card.md).

    ![Produktfält för presentkort i Commerce-administrationen](./media/PostGiftcard.png)

- Om ett presentkort måste ha stöd för flera fördefinierade belopp (till exempel 25, 50 respektive 100 USD) ska dimensionen **Storlek** användas för att konfigurera dessa fördefinierade belopp. Varje enskilt fördefinierat belopp kommer att vara en variant. Mer information finns i [Produktdimensioner](../supply-chain/pim/product-dimensions.md?toc=%2fdynamics365%2fretail%2ftoc.json).
- Om kunderna måste kunna ange ett anpassat belopp för ett presentkort måste du först skapa en variant som tillåter ett anpassat belopp. Öppna sedan produkten från sidan **Frisläppta produkter i kategori** innan du på snabbfliken **Commerce** anger fältet **Ange pris** som **Måste ange nytt pris**, enligt följande illustration. Denna inställning garanterar att kunderna kan ange ett pris när de bläddrar i produkten på en PDP.

    ![Fältet Ange pris i Commerce-administrationen](./media/KeyInPrice.png)

- Leveranssättet för ett digitalt presentkort måste vara **Elektroniskt**. På sidan **Leveranssätt** (**Retail och commerce \> Kanalinställningar \> Leveranssätt**) väljer du leveranssättet **Elektroniskt** i listpanelen innan du lägger till den digitala presentkortprodukten i rutnätet på snabbfliken **Produkter** enligt följande illustration. Mer information finns i [Konfigurera leveranssätt](/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).

    ![Digitala presentkortprodukter på sidan Leveranssätt i Commerce-administrationen](./media/ElectronicMode.PNG)

- Kontrollera att en online-funktionsprofil har skapats och associerats med din onlinebutik i Commerce-administrationen. Ställ in alternativet **Aggregera produkter** som **Ja**. Denna inställning garanterar att alla artiklar utom presentkort aggregeras. Mer information finns i [Skapa en online-funktionsprofil](online-functionality-profile.md).
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