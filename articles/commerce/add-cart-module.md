---
title: Kundvagnsmodul
description: Det här avsnittet handlar om kundvagnsmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 05/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: f21268ed4cffed1d5c789f722796cdf05e965819
ms.sourcegitcommit: 4a981ee4be6d7e6c0e55541535d386bce2565cba
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/27/2020
ms.locfileid: "3621046"
---
# <a name="cart-module"></a>Kundvagnsmodul

[!include [banner](includes/banner.md)]

Det här avsnittet handlar om kundvagnsmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

En kundvagnsmodul visar artiklarna som har lagts till i kundvagnen innan kunden fortsätter till kassan. Modulen visar även en också en ordersammanfattning och gör att kunden kan använda eller ta bort kampanjkoder.

Kundvagnsmodulen stöder inloggade utcheckning och gästkassa. Det stöder också en **Tillbaka till shopping**-länk. Du kan konfigurera flödet för den här länken när **webbplatsinställningar \> tillägg \> flöden**.

I modulen kundvagn återges data baserat på vagn-ID:t, som är en webbläsarcookie som är tillgänglig på hela webbplatsen. 

Följande bild visar ett exempel på en kundvagnssida på Fabrikam-webbplatsen.

![Exempel på en kundvagnsmodul](./media/cart2.PNG)

## <a name="cart-module-properties-and-slots"></a>Egenskaper och platser för kundvagnsmodul

Kundvagnsmodulen har en egenskap för **Rubrik** som kan ställas in på värden som **Shoppingväska** och **Artiklarna i vagnen**. 

## <a name="modules-that-can-be-used-in-a-cart-module"></a>Moduler kan användas i en kundvagnsmodul

- **Textblock** – den här modulen stöder anpassade meddelanden i kundvagnsmodulen. Meddelandena styrs av innehållshanteringssystem (CMS). Alla meddelanden kan läggas till, till exempel "för problem med ordern, kontakta 1-800-Fabrikam."
- **Butiksväljare** – i den här modulen visas en lista över närliggande butiker där det finns en artikel tillgänglig för upphämtning. Användare kan ange en plats för att hitta butiker som finns i närheten. Mer information om den här modulen finns i [modulen Butiksväljare](store-selector.md).

## <a name="module-properties"></a>Modulegenskaper

Följande kundvagnsmodulinställningar som kan konfigureras på **Platsinställningar \> Tillägg**:

- **Maximal kvantitet** – Den här egenskapen används för att ange det maximala antalet för varje objekt som kan läggas till i vagnen. En återförsäljare kan till exempel besluta att endast 10 av varje produkt kan säljas i en enda transaktion.
- **Lager** – För information om hur du använder lagerinställningar finns i [tillämpa lagerinställningar](inventory-settings.md).
- **Tillbaka till shopping** – den här egenskapen används för att ange vägen för länken **Tillbaka till shopping**. Vägen kan konfigureras på webbplatsnivå, vilket gör att återförsäljare kan ta kunden tillbaka till startsidan eller någon annan sida på webbplatsen.

## <a name="commerce-scale-unit-interaction"></a>Interaktion för skalningsenhet för handel

Vagnmodul för inköpsruta hämtar produktinformation med hjälp av API:er för skalningsenhet för handel. Vagn-ID från webbläsarcookien används för att hämta all produktinformation från skalningsenhet för handel.

## <a name="add-a-cart-module-to-a-page"></a>Lägg till en kundvagnsmodul på en ny sida

Om du vill lägga till en kundvagnsmodul på en ny sida och ställa in de obligatoriska egenskaperna följer du stegen nedan.

1. Gå till **Sidfragment** och välj **ny** för att skapa ett nytt fragment.
1. I dialogrutan **Ny sidfragment**, välj modulen **kundvagn**.
1. Under **sidfragmentets namn**, anger du ett namn på **kundvagnsfragmentet** och klickar sedan på **OK**.
1. Markera platsen **kundvagn**.
1. I pennfönstret till höger väljer du pennsymbolen, anger rubriktext i fältet och markerar sedan kryssmarkeringssymbolen.
1. I facket **kundvagn** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.
1. I dialogrutan **Lägg till modul** välj modulen **butiksväljare** och sedan **OK**.
1. Välj **Spara**, välj **Slutför redigering** för att checka in fragmentet och välj sedan **publicera** för att publicera den.
1. Gå till **mallar**och välj sedan **ny** för att skapa en ny mall.
1. I dialogrutan **Ny mall** under **Mallnamn** anger du ett namn för mallen.
1. I dispositionsträdet väljer du platsen **Brödtext** markerar ellipsknappen (**...**) och väljer sedan **Lägg till fragment**.
1. I dialogrutan **Välj sidfragment** väljer du det **kundvagnsfragment** och väljer sedan **OK**.
1. Välj **Spara**, välj **Slutför redigering** för att checka in mallen och välj sedan **publicera** för att publicera den.
1. Gå till **Sidor** och välj **nytt sidfragment** för att skapa en ny sida.
1. I dialogrutan **Välj en mall** väljer du den mall som du skapade, anger sidnamn och väljer sedan **OK**.
1. Klicka på **Spara** och välj **Förhandsgranska** för att förhandsgranska sidan.
1. Välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.

## <a name="additional-resources"></a>Ytterligare resurser

[Startpaket – översikt](starter-kit-overview.md)

[Behållarmodul](add-container-module.md)

[Modul för butiksväljare](store-selector.md)

[Modul för inköpsruta](add-buy-box.md)

[Vagnikonmodul](cart-icon-module.md)

[Kassamodul](add-checkout-module.md)

[Modul för orderbekräftelse](order-confirmation-module.md)

[Modul för sidhuvud](author-header-module.md)

[Modul för sidfot](author-footer-module.md)

[Beräkna lagertillgänglighet för butikskanaler](calculated-inventory-retail-channels.md)
