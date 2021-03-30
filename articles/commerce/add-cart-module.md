---
title: Kundvagnsmodul
description: Det här avsnittet handlar om vagnmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 12/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 5b0ce69f57e6ba691803752280466b41ced7c521
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5206497"
---
# <a name="cart-module"></a>Kundvagnsmodul

[!include [banner](includes/banner.md)]

Det här avsnittet handlar om vagnmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.

En kundvagnsmodul visar artiklarna som har lagts till i kundvagnen innan kunden fortsätter till kassan. Modulen visar även en också en ordersammanfattning och gör att kunden kan använda eller ta bort kampanjkoder.

Kundvagnsmodulen stöder inloggad kassa och gästkassa. Det stöder också en **Tillbaka till shopping**-länk. Du kan konfigurera flödet för den här länken när **webbplatsinställningar \> tillägg \> flöden**.

I modulen kundvagn återges data baserat på vagn-ID:t, som är en webbläsarcookie som är tillgänglig på hela webbplatsen. 

Följande bild visar ett exempel på en kundvagnssida på Fabrikam-webbplatsen.

![Exempel på en kundvagnsmodul på webbplatsen Fabrikam](./media/cart2.PNG)

Följande bild visar ett exempel på en kundvagnssida på Fabrikam-webbplatsen. I det här exemplet är det en hanteringsavgift för en radartikel.

![Exempel på en kundvagnsmodul med en hanteringsavgift för en radartikel](./media/ecommerce-handling-fee.png)

## <a name="cart-module-properties-and-slots"></a>Egenskaper och platser för kundvagnsmodul

| Egenskap | Värden | beskrivning |
|----------------|--------|-------------|
| Rubrik | Rubriktext och rubriktagg (**H1**, **H2**, **H3**, **H4**, **H5** eller **H6**) | En rubrik för kundvagnen, till exempel "Shoppingväska" eller "Artiklarna i vagnen." |
| Visa fel av typen Slut i lager | **Sant** eller **falskt** | Om den här egenskapen har angetts till **True** visar sidan för kundvagn fel som är relaterade till lagret. Vi rekommenderar att du ställer in den här egenskapen på **True** om lagerkontroller används på webbplatsen. |
| Visa leveransavgifter för radartiklar | **Sant** eller **falskt** | Om den här egenskapen har värdet **True** visar kundvagnsartiklar leveransavgifter om den här informationen är tillgänglig. Den här funktionen stöds inte i det Fabrikam-temat, eftersom användarna väljer enbart leverans i kassaflödet. Den här funktionen kan emellertid aktiveras i andra arbetsflöden om den är tillämplig. |
| Visa tillgängliga erbjudanden| **Sant** eller **falskt** | Om egenskapen har satts till **Sant** visar kundvagnen tillgängliga erbjudanden baserat på artiklarna i vagnen. Denna funktion finns i Dynamics 365 Commerce version 10.0.16. |

## <a name="modules-that-can-be-used-in-a-cart-module"></a>Moduler kan användas i en kundvagnsmodul

- **Textblock** – den här modulen stöder anpassade meddelanden i kundvagnsmodulen. Meddelandena styrs av innehållshanteringssystem (CMS). Alla meddelanden kan läggas till, till exempel "för problem med ordern, kontakta 1-800-Fabrikam."
- **Butiksväljare** – i den här modulen visas en lista över närliggande butiker där det finns en artikel tillgänglig för upphämtning. Användare kan ange en plats för att hitta butiker som finns i närheten. Mer information om den här modulen finns i [modulen Butiksväljare](store-selector.md).

## <a name="module-properties"></a>Modulegenskaper

Följande kundvagnsmodulinställningar som kan konfigureras på **Platsinställningar \> Tillägg**:

- **Maximal kvantitet** – Den här egenskapen används för att ange det maximala antalet för varje objekt som kan läggas till i vagnen. En återförsäljare kan till exempel besluta att endast 10 av varje produkt kan säljas i en enda transaktion.
- **Lager** – För information om hur du använder lagerinställningar finns i [tillämpa lagerinställningar](inventory-settings.md).
- **Tillbaka till shopping** – den här egenskapen används för att ange vägen för länken **Tillbaka till shopping**. Vägen kan konfigureras på webbplatsnivå, vilket gör att återförsäljare kan ta kunden tillbaka till startsidan eller någon annan sida på webbplatsen.

> [!IMPORTANT]
> I Dynamics 365 Commerce 10.0.14-versionen och senare sammanställs artiklar i kundvagnen baserat på inställningarna som definieras i online-butikens funktionsprofil i Commerce-administration. Mer information om hur du skapar en funktionsprofil i online och ställer in de egenskaper som krävs för aggregering finns i [skapa en online funktionsprofil](online-functionality-profile.md).

## <a name="commerce-scale-unit-interaction"></a>Interaktion för skalningsenhet för handel

Vagnmodul för inköpsruta hämtar produktinformation med hjälp av API:er för skalningsenhet för handel. Vagn-ID från webbläsarcookien används för att hämta all produktinformation från skalningsenhet för handel.

## <a name="add-a-cart-module-to-a-page"></a>Lägg till en kundvagnsmodul på en ny sida

Om du vill lägga till en kundvagnsmodul på en ny sida och ställa in de obligatoriska egenskaperna följer du stegen nedan.

1. Gå till **Fragment** och välj **ny** för att skapa ett nytt fragment.
1. I dialogrutan **Nytt fragment**, välj modulen **Kundvagn**.
1. Under **Fragmentets namn**, anger du ett namn på **kundvagnsfragmentet** och klickar sedan på **OK**.
1. Markera platsen **kundvagn**.
1. I pennfönstret till höger väljer du pennsymbolen, anger rubriktext i fältet och markerar sedan kryssmarkeringssymbolen.
1. I facket **kundvagn** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.
1. I dialogrutan **Lägg till modul** välj modulen **butiksväljare** och sedan **OK**.
1. Välj **Spara**, välj **Slutför redigering** för att checka in fragmentet och välj sedan **publicera** för att publicera den.
1. Gå till **mallar** och välj sedan **ny** för att skapa en ny mall.
1. I dialogrutan **Ny mall** under **Mallnamn** anger du ett namn för mallen.
1. I dispositionsträdet väljer du platsen **Brödtext** markerar ellipsknappen (**...**) och väljer sedan **Lägg till fragment**.
1. I dialogrutan **Välj fragment** väljer du det **kundvagnsfragment** och väljer sedan **OK**.
1. Välj **Spara**, välj **Slutför redigering** för att checka in mallen och välj sedan **publicera** för att publicera den.
1. Gå till **Sidor** och välj **nytt sidfragment** för att skapa en ny sida.
1. I dialogrutan **Välj en mall** väljer du den mall som du skapade, anger sidnamn och väljer sedan **OK**.
1. Klicka på **Spara** och välj **Förhandsgranska** för att förhandsgranska sidan.
1. Välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.

## <a name="additional-resources"></a>Ytterligare resurser

[Ikon för kundvagnsmodul](cart-icon-module.md)

[Kassamodul](add-checkout-module.md)

[Betalningsmodul](payment-module.md)

[Modul för leveransadress](ship-address-module.md)

[Modul för leveransalternativ](delivery-options-module.md)

[Informationsmodul för upphämtning](pickup-info-module.md)

[Orderinformationsmodul](order-confirmation-module.md)

[Presentkortsmodul](add-giftcard.md)

[Beräkna lagertillgänglighet för butikskanaler](calculated-inventory-retail-channels.md)

[Skapa en onlinefunktionsprofil](online-functionality-profile.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]