---
title: Kundvagnsmodul
description: Det här avsnittet handlar om kundvagnsmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 01/23/2020
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
ms.openlocfilehash: f6dd8fb56f7342eb9c877eda503a92f4a31e5863
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025446"
---
# <a name="cart-module"></a>Kundvagnsmodul


[!include [banner](includes/banner.md)]

Det här avsnittet handlar om kundvagnsmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

En kundvagnsmodul används för att visa artiklarna som har lagts till i kundvagnen innan kunden fortsätter till kassan. Den innehåller till exempel alla artiklar som har lagts till i kundvagnen och en ordersammanfattning. Det gör också att kunden kan använda eller ta bort kampanjkoder.

Kundvagnsmodulen stöder inloggade utcheckning och gästkassa. Det stöder också en **Tillbaka till shopping**-länk. Du kan konfigurera flödet för den här länken när **webbplatsinställningar \> tillägg \> flöden**.

Kundvagnsmodulen återger data baserat på kundvagn-ID. Kundvagn-ID är en webbläsarcookie som finns tillgänglig på hela webbplatsen.

## <a name="cart-module-properties-and-slots"></a>Egenskaper och platser för kundvagnsmodul

Kundvagnsmodulen har en egenskap för **Rubrik** som kan ställas in på värden som **Shoppingväska** och **Artiklarna i vagnen**. 

## <a name="modules-that-can-be-used-in-a-cart-module"></a>Moduler kan användas i en kundvagnsmodul

- **Textblock** – den här modulen stöder anpassade meddelanden i kundvagnsmodulen. Meddelandena styrs av innehållshanteringssystem (CMS). Alla meddelanden kan läggas till, till exempel "för problem med ordern, kontakta 1-800-Fabrikam."
- **Butiksväljare** – i den här modulen visas en lista över närliggande butiker där det finns en artikel tillgänglig för upphämtning. Användare kan ange en plats för att hitta butiker som finns i närheten. Butiksväljarmodulen är integrerad med geokodnings-API för Bing Maps för att konvertera platsen till en latitud och longitud. En Bing Maps API-nyckel krävs och måste läggas till på sidan för delade butiksparametrar i Dynamics 365 Retail. Den här modulen har stöd för två egenskaper **Sökradien** och **Länk till användarvillkor**. Egenskapen **Sökradie** definierar sökradien för butiker, i mil. Om inget värde anges används standardsökradien 50 mil. Om Bing Maps eller någon extern tjänst används kan egenskapen **Länken för tjänstvillkor** användas för att skapa en länk till villkoren för tjänsten. Det krävs en länk för tjänstvillkors för Bing Maps-tjänsten. 

## <a name="cart-module-settings"></a>Inställningar för kundvagnsmodul

Vagnmoduler har följande inställningar som kan konfigureras på **Platsinställningar \> Tillägg**:

- **Maximal kvantitet** – Den här egenskapen används för att ange det maximala antalet för varje objekt som kan läggas till i vagnen. En återförsäljare kan till exempel besluta att endast 10 av varje produkt kan säljas i en enda transaktion.
- **Inventering** – när värdet är inställt på **Sant** läggs en artikel till i vagnen först när modul för inköpsruta kontrollerar att den finns i lager. Den här inventeringen görs både för scenarier där artikeln ska levereras och för scenarier där den ska hämtas i butiken. Om värdet är inställt på **Falsk** görs ingen lagerkontroll innan en artikel läggs till i vagnen och ordern placeras.
- **Lagerkvantitet** – den här egenskapen används för att ange ett buffertnummer för lager. Lagret underhålls i realtid och när många kunder gör beställningar kan det vara svårt att underhålla en korrekt inventering. När en lagerkontroll utförs, om lagret är mindre än buffertlagret, behandlas produkten som om den ligger utanför lagret. När försäljningen går snabbt via flera kanaler, så att lager inventeringen inte fullständigt synkroniseras, finns det därför mindre risk för försäljning av en artikel som ligger utanför lagret.
- **Tillbaka till shopping** – den här egenskapen används för att ange vägen för länken **Tillbaka till shopping**. Den här vägen kan konfigureras på webbplatsnivå. Den här konfigurationen låter återförsäljare kan han eller hon gå tillbaka till startsidan eller någon annan sida på webbplatsen.

## <a name="commerce-scale-unit-interaction"></a>Interaktion för skalningsenhet för handel

Vagnmodul för inköpsruta hämtar produktinformation med hjälp av API:er för skalningsenhet för handel. Vagn-ID från webbläsarcookien används för att hämta all produktinformation från skalningsenhet för handel.

## <a name="add-a-cart-module-to-a-page"></a>Lägg till en kundvagnsmodul på en ny sida

Om du vill lägga till en kundvagnsmodul på en ny sida och ställa in de obligatoriska egenskaperna följer du stegen nedan.

1. Skapa ett fragment med namnet **vagnfragment**och lägg till en kundvagnsmodul.
1. Lägg till en rubrik i vagnmodulen.
1. Lägg till modulen för butiksväljare i vagnmodulen.
1. Spara fragmentet, slutför redigeringen och publicera det.
1. Skapa en mall med namnet **vagnmall** och lägg till det vagnfragment som du precis skapade i den.
1. Spara mallen, slutför redigeringen och publicera den.
1. Skapa en sida som använder den nya mallen.
1. Spara och förhandsgranska sidan.
1. Avsluta redigeringen av sidan och publicera den.

## <a name="additional-resources"></a>Ytterligare resurser

[Startpaket – översikt](starter-kit-overview.md)

[Behållaremodul](add-container-module.md)

[Modul för inköpsruta](add-buy-box.md)

[Kassamodul](add-checkout-module.md)

[Modul för orderbekräftelse](order-confirmation-module.md)

[Modul för sidhuvud](author-header-module.md)

[Modul för sidfot](author-footer-module.md)
