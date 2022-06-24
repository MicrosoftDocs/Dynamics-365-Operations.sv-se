---
title: Konfigurera expressbetalningar för PayPal
description: I denna artikel beskrivs hur du konfigurerar expressbetalningar för PayPal för att aktivera snabbare kassa i Microsoft Dynamics 365 Commerce.
author: BrianShook
ms.date: 05/11/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: b69b7384992fb86370ff6881824a7d2c9a77d2c4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8905292"
---
# <a name="configure-express-payments-for-paypal"></a>Konfigurera expressbetalningar för PayPal

[!include [banner](../includes/banner.md)]

I denna artikel beskrivs hur du konfigurerar expressbetalningar för PayPal för att aktivera snabbare kassa i Microsoft Dynamics 365 Commerce.

## <a name="key-terms"></a>Nyckeltermer

| Villkor | Beskrivning |
|---|---|
| PayPal Wallet | Den kundupplevelse och -integrering som stöds av PayPal-anslutningsprogrammet. Den kallas också för PayPal-knappen. |
| Plånbok | En betalningstyp som inte har traditionella betalningsegenskaper, som BIN-intervall (Bank Identification Number) och utgångsdatum, som används för att särskilja typer av kredit- och betalkort. |
| Expressbetalning | En Commerce-modul som stöder snabbare kassasätt när betalningsmetoder som stöds används. I denna artikel används betalningsexpressmodulen med PayPal. |

Dynamics 365 Commerce erbjuder en färdig integrering för PayPal Wallet. När du har konfigurerat Dynamics 365 Payment Connector för PayPal visas knappen PayPal som en betalningsmetod som kan väljas när onlineordern checkas ut. När användarna väljer PayPal skickas de direkt till PayPal för att betala via PayPal och skickas sedan tillbaka till onlinebutiken för att slutföra sin order. I kassa av PayPal-kundvagnen kan kunderna använda sin betalningskontoinformation för att förifylla kassaformuläret så att de snabbt kan slutföra kassaprocessen.

Commerce har lagt till en betalningsexpressmodul för att underlätta expresskassor. Modulen för expressbetalning kan användas i ett fragment som kan inkluderas på en kassa- eller kundvagnssida. När PayPal konfigureras används samma Dynamics 365 Payment Connector för PayPal-anslutningsprogramreferens för både expressbetalningsalternativet och det vanliga kassaalternativet.

## <a name="paypal-checkout-in-commerce"></a>PayPal-checkout i Commerce

### <a name="prerequisites"></a>Förutsättningar

Konfigurera PayPal Wallet för din miljö enligt beskrivningen i [Dynamics 365 Payment Connector för PayPal](../paypal.md).

Om du använder PayPal som ett alternativ i det vanliga kassaflödet (där användarna manuellt anger sin kontoinformation utan att använda förfyllningsåtgärderna för betalning) följer du installationsanvisningarna i [modulen Betalning](../payment-module.md).

### <a name="payment-express-module-with-paypal"></a>Modul för expressbetalning med PayPal

Modulen för expressbetalning fungerar med de betalningsmetoder som stöds så att webbplatskunder kan välja att checka ut snabbare genom att förifylla sin betalningstjänstkontoinformation under kassaprocessen. I expressbetalningsmodulen används den konfigurerade betalningsanslutningsprogrammet för att förifylla kassaformuläret med användarkontoinformation som t.ex. adress, kontaktinformation och vald betalningsmetod.

När PayPal expresskassa används, och en användare väljer knappen PayPal i avsnittet för expressbetalning på kassasidan, öppnas ett iFrame-fönster för PayPal-betalning. Användaren loggar sedan in på sitt PayPal-konto för att använda kontots leveransadress, faktureringsadress, e-postadress och PayPal-betalningsmetod för att betala för transaktionen.

När användaren har slutfört åtgärden i PayPal-fönstret skickas den tillbaka till kassasidan för Commerce-webbplatsen där kassaformuläret förifylls med de valda detaljerna. I expressbetalningsflödet fylls det första leveransalternativet i som är tillgängligt för leveransadressen som returneras för användaren. Användaren har sedan möjlighet att granska ordern och ändra detaljer i kassaordern innan de väljer **Beställ** för att slutföra ordern.

### <a name="add-the-payment-express-module-with-paypal-to-a-fragment"></a>Lägg till modulen för expressbetalning med PayPal i ett fragment

Om du vill lägga till expressbetalningsmodulen med PayPal i ett fragment i Commerce-webbplatsbyggaren följer du stegen nedan.

1. Gå till webbplatsen.
1. I vänster navigeringsfönstret, välj **Fragment** och välj sedan **Nytt**.
1. I dialogrutan **Nytt fragment** hitta och välj modulen **Expressbetalning** och sedan under **Namn på fragment** ange ett namn (till exempel **Expresskassa**).
1. Skapa fragmentet genom att välja **OK**.
1. I översiktsvyn väljer du platsen för den expressbetalningsmodul som du har skapat.
1. Välj **Rubrik** i egenskapsfönstret.
1. I dialogrutan **Rubrik**, i fältet **Rubriktext**, anger du den rubriktext som du vill visa för expresskassaavsnittet på webbplatsen (till exempel **Expresskassa**).
1. Under **Rubriknivå** väljer du rubriknivå (t.ex. **H2**).
1. Välj **OK**.
1. I egenskapsfönstret i fältet **Höjd på iFrame** anger eller justerar du höjden på iFrame-elementet (till exempel **60**).
1. I fältet **Betalningsmedelstyper som stöds** anger du **PayPal**.
1. Välj **Spara**, välj **Slutför redigering** för att checka in fragmentet och välj sedan **publicera** för att publicera den.

### <a name="add-the-payment-express-fragment-to-the-checkout-page"></a>Lägga till expressbetalningsfragment på kassasidan

För att lägga till ett fragment för expressbetalning på kassasidan i webbplatsbyggaren följer du dessa steg.

1. Gå till webbplatsen.
1. Välj **Sidor** i vänster navigeringsfönster och välj sedan webbplatsens kassasida.
1. Välj **Redigera** för att redigera sidan.
1. I facket **Huvud** väljer du ellipsknappen (**...**) och välj sedan **Lägg till modul**.
1. I dialogrutan **Välj moduler**, välj modulen **Behållare** och klicka sedan på **OK**.

    > [!NOTE]
    > Om en behållarmodul som innehåller ett kassafragment redan finns, flyttar du expressbetalningsavsnittet så att det visas ovanför den befintliga kassabehållaren på platsen **Huvud**. Expressbetalningsavsnittet återges ovanför den vanliga kassabehållaren. Om du vill flytta en behållarmodul uppåt eller nedåt väljer du ellipsen (**...**) och väljer sedan **Flytta upp** eller **Flytta ned**.

1. I egenskapsfönstret **Behållare** rekommenderar vi att du konfigurerar egenskapsinställningarna på följande sätt:

    - **Behållarens layout** – välj **Staplad**.
    - **Bredd** – Välj **Fyll behållare**.
    - **Underordnade som visas** – välj **Tre**.

1. I facket **Behållare** välj ellipsen (**...**) och välj sedan **Lägg till fragment**.
1. I dialogrutan **Välj ett fragment** letar du rätt på och väljer expressbetalningsfragmentet som du skapade tidigare och väljer sedan **OK**.
1. Välj **Spara**, välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.

### <a name="add-the-payment-express-fragment-to-the-cart-page"></a>Lägga till expressbetalningsfragment på kundvagnssidan

För att lägga till ett fragment för expressbetalning på kundvagnssidan i webbplatsbyggaren följer du dessa steg.

1. Gå till webbplatsen.
1. Välj **Sidor** i vänster navigeringsfönster och välj sedan webbplatsens kundvagnssida.
1. Välj **Redigera** för att redigera sidan.
1. I rutan **Huvud** letar du rätt på behållaren som innehåller modulen **Kundvagn**. Modulen **Kundvagn** innehåller rutan **Expressbetalning**.
1. Välj rutan **Expressbetalning**, välj ellipsen (**...**) och välj sedan **Lägg till modul**.
1. I dialogrutan **Välj moduler**, välj modulen **Expressbetalning** och klicka sedan på **OK**.
1. I egenskapsfönstret i **Betalningsmedelstyper som stöds** anger du **Paypal**.
1. Välj **Spara**, välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.

### <a name="modes-of-delivery"></a>Leveranssätt

När expressbetalningsmodulen är konfigurerad till att använda PayPal, kommer det första leveransalternativet som returneras för leveransadressen som valts för PayPal-kontot att förifyllas. Användarna kan ändra leveransadressen om de vill.

Leveranssättet konfigureras i avsnittet **Leveranssätt** för kanalen i Commerce headquarters. Mer information finns i [Konfigurera leveranssätt](/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).

kassamodulen använder också leveransalternativmodulen när leveranssätt återges vid kassa. Mer information finns i [Modul för leveransalternativ](../delivery-options-module.md).

Leveranssätt läggs till i listan för onlinebutiken i Commerce headquarters. Gå till **Butik och handel \> Kanaler \> Onlinebutiker** och välj kanal-ID för din butik. Välj sedan **Konfigurera \> Leveranssätt**. Modulens leveranssätt som visas i konfigurationen visas på liknande sätt på webbplatsen. Om du vill lägga till eller ta bort leveranssätt för en butikskanal eller produkt väljer **Hantera leveranssätt** i åtgärdsfönstret.

## <a name="additional-resources"></a>Ytterligare resurser

[Vanliga frågor om betalningar](payments-retail.md)

[Kassamodul](../add-checkout-module.md)

[Betalningsmodul](../payment-module.md)

[Ställ in leveranssätt](/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery)

[Modul för leveransalternativ](../delivery-options-module.md)
