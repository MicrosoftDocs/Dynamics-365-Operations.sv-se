---
title: Använd lagerinställningar
description: Det här avsnittet behandlar lagerinställningar och beskriver hur du använder dem i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 3da447c298993794afa49a0fbaddb1c21cf6231a
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2021
ms.locfileid: "6271315"
---
# <a name="apply-inventory-settings"></a>Använd lagerinställningar

[!include [banner](includes/banner.md)]

Det här avsnittet behandlar lagerinställningar och beskriver hur du använder dem i Microsoft Dynamics 365 Commerce.

Lagerinställningarna anger om lagret ska kontrolleras innan produkter läggs till i vagnen. De definierar också lagerrelaterade marknadsföringsmeddelanden, t.ex. "i lagret" och "bara några få kvar". Dessa inställningar garanterar att en produkt inte kan köpas om den inte är i lager.

Dynamics 365 Commerce tillhandahåller uppskattningar av tillgänglig lagerbehållning för produkter. Information om hur uppskattad behållnings tillgänglighet beräknas finns i [Beräkna lagerdisposition för butikskanaler](calculated-inventory-retail-channels.md).

I Commerce webbplatsskaparen kan lagertrösklar och intervall definieras för en produkt eller en kategori. De bestämmer om lager kan klassificeras som i lager, låglager eller utanför lagret. Mer information finns i [Konfigurera inventeringsbuffertar and lagernivåer](inventory-buffers-levels.md).

> [!NOTE]
> Stöd för lagertrösklar och -intervall är tillgängliga i Dynamics 365 Commerce 10.0.12-versionen.

## <a name="inventory-settings"></a>Lagerinställningar

I Commerce, lagerinställningar definieras på **Platsinställningar \> Tillägg \> Lagerhantering** i webbplatsskaparen. Det finns fem lagerinställningar, varav en är föråldrad (inaktuell):

- **Aktivera lagerkontroll i appen** – Den här inställningen aktiverar en produklagerkontroll. När du köper kartongen, kundvagnen och hämtningen i butiksmoduler kontrolleras produktlagret och då kan en produkt bara läggas till i kundvagnen om det finns tillgängligt lager.
- **Lagernivå baserad på** – den här inställningen definierar hur lagernivåer beräknas. De tillgängliga värdena är **Total tillgänglig**, **fysiskt tillgänglig** och **tröskel för utanför lagret**. I Commerce, lagertrösklar och intervall definieras för en varje produkt och kategori. Lager-API:erna returnerar produktinformation för båda egenskap **Total tillgänglig** och egenskap **Fysisk tillgänglig**. Återförsäljaren bestämmer om det **totala tillgängliga** eller **fysiskt tillgängliga** värdet ska användas för att fastställa lagerinventeringen och motsvarande intervall för status som lager och inte artiklar.

    Värdet **tröskel för utanför lagret** för inställning **Lagernivå baserad på** är ett gammalt (äldre) föråldrat värde. När lagerinventeringen väljs bestäms resultatet av det **totala tillgängliga** värdet, men tröskeln definieras av **inställningen för frånvaro av lagertröskel** som beskrivs senare. Den här tröskelinställningen gäller för alla produkter på en näthandelssajt. Om lagret är lägre än tröskelnumret anses en produkt vara utanför lagret. I annat fall betraktas det som i lager. Möjligheterna för **tröskelvärdet för frånvaro** är begränsade och vi rekommenderar inte att du använder det i version 10.0.12 och senare.

- **Lagernivå för flera lagerställen** – Med den här inställningen kan lagernivån beräknas mot standardlagerstället eller flera lagerställen. Alternativet **Baserat på enskilda lagerställen** beräknar lagernivåer baserat på standardlagerstället. Alternativt kan en näthandelsplats peka på flera lagerställen i syfte att underlätta uppfyllelsen. I sådana fall används alternativet **Baserat på aggregering för leverans- och upphämtningslagerställen** för att ange lagertillgänglighet. När en kund till exempel köper in en artikel och väljer "leverans" som leveransläge kan artikeln skeppas från valfritt lagerställe i uppfyllelsegruppen som har tillgängligt lager. På sidan för produktinformation (PDP) visas ett "I lager"-meddelande för leverans om något tillgängligt leveranslager i uppfyllelsegruppen har lager. 

> [!IMPORTANT] 
> Inställningen **Lagernivån för flera lagerställen** är tillgänglig i version 10.0.19 av Commerce. Om du uppdaterar från en äldre version av Commerce måste du uppdatera filen appsettings.json manuellt. För instruktioner, se [SDK- och modulbiblioteksuppdateringar](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).

- **Lagerområden** – med den här inställningen definieras de lagerintervall som meddelandet visas för i moduler. Den gäller bara om antingen värdet **totala tillgängliga** eller det **fysiska tillgängliga värdet** har valts för inställning **lagernivån baserat på**. De tillgängliga värdena är **alla**, **låg och ur lagret** och inte **på lagret**.

    - När **alla** är markerat visas meddelanden för alla lagerområden, från lagret ("tillgängligt") i brist på lager ("tillgängligt").
    - När **låg och inte i lager** är markerat visas meddelanden för alla lagerområden förutom från lagret ("tillgängligt").
    - När **inte i lager** är markerat visas endast meddelandet "inte i lager".

- **Tröskel för inte i lager** – den här gamla numeriska inställningen börjar gälla först om värdet **tröskelvärdet för inte i lager** har valts för inställningen **lagernivå baserat på**.

> [!IMPORTANT] 
> Dessa inställningar finns i Dynamics 365 Commerce 10.0.12 versionen. Om du uppdaterar från en äldre version av Dynamics 365 Commerce måste du uppdatera filen appsettings.json manuellt. Information om hur du uppdaterar filen appsettings.json finns i [SDK- och modulens biblioteksuppdateringar](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).

## <a name="modules-that-use-inventory-settings"></a>Moduler som använder lagerinställningar

Ikonmodulerna inköpsruta, önskelista, butiksväljare, kundvagn och kundvagnsikon använder lagerinställningar för att visa lagerområden och meddelanden.

I exemplet i följande illustration visar en PDP ett meddelande om "I lager" ("Tillgänglig").

![Exempel på en PDP-modul som har ett upplagratmeddelande](./media/pdp-InStock.png)

I exemplet i följande illustration visar en PDP ett meddelande om "Ej i lager".

![Exempel på en PDP-modul som har ett ej i lager-meddelande](./media/pdp-outofstock.png)

I exemplet i följande illustration visar en kundvagn ett meddelande om "I lager&quot; (&quot;Tillgänglig").

![Exempel på en kundvagnmodul som har ett upplagratmeddelande](./media/cart-instock.png)

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över modulbibliotek](starter-kit-overview.md)

[Konfigurera lagerkvantiteter och lagernivåer](inventory-buffers-levels.md)

[Kundvagnsmodul](add-cart-module.md)

[Modul för inköpsruta](add-buy-box.md)

[Sidor och moduler för kontohantering](account-management.md)

[Modul för butiksväljare](store-selector.md)

[Uppdateringar av SDK och modulbibliotek](e-commerce-extensibility/sdk-updates.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
