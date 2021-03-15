---
title: Använd lagerinställningar
description: Det här avsnittet behandlar lagerinställningar och beskriver hur du använder dem i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
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
ms.openlocfilehash: 77a3bde12fd047e15d7730903416cdb5263a8cd9
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4972819"
---
# <a name="apply-inventory-settings"></a>Använd lagerinställningar

[!include [banner](includes/banner.md)]

Det här avsnittet behandlar lagerinställningar och beskriver hur du använder dem i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

Lagerinställningarna anger om lagret ska kontrolleras innan produkter läggs till i vagnen. De definierar också lagerrelaterade marknadsföringsmeddelanden, t.ex. "i lagret" och "bara några få kvar". Dessa inställningar garanterar att en produkt inte kan köpas om den inte är i lager.

Dynamics 365 Commerce tillhandahåller uppskattningar av tillgänglig lagerbehållning för produkter. Information om hur uppskattad behållnings tillgänglighet beräknas finns i [Beräkna lagerdisposition för butikskanaler](calculated-inventory-retail-channels.md).

I Commerce webbplatsskaparen kan lagertrösklar och intervall definieras för en produkt eller en kategori. De bestämmer om lager kan klassificeras som i lager, låglager eller utanför lagret. Mer information finns i [Konfigurera inventeringsbuffertar and lagernivåer](inventory-buffers-levels.md).

> [!NOTE]
> Stöd för lagertrösklar och -intervall är tillgängliga i Dynamics 365 Commerce 10.0.12-versionen.

## <a name="inventory-settings"></a>Lagerinställningar

I Commerce, lagerinställningar definieras på **Platsinställningar \> Tillägg \> Lagerhantering** i webbplatsskaparen. Det finns fyra lagerinställningar, varav en är föråldrad (inaktuell):

- **Aktivera lagerkontroll i appen** – Den här inställningen aktiverar en produklagerkontroll. När du köper kartongen, kundvagnen och hämtningen i butiksmoduler kontrolleras produktlagret och då kan en produkt bara läggas till i kundvagnen om det finns tillgängligt lager.
- **Lagernivå baserad på** – den här inställningen definierar hur lagernivåer beräknas. De tillgängliga värdena är **Total tillgänglig**, **fysiskt tillgänglig** och **tröskel för utanför lagret**. I Commerce, lagertrösklar och intervall definieras för en varje produkt och kategori. Lager-API:erna returnerar produktinformation för båda egenskap **Total tillgänglig** och egenskap **Fysisk tillgänglig**. Återförsäljaren bestämmer om det **totala tillgängliga** eller **fysiskt tillgängliga** värdet ska användas för att fastställa lagerinventeringen och motsvarande intervall för status som lager och inte artiklar.

    Värdet **tröskel för utanför lagret** för inställning **Lagernivå baserad på** är ett gammalt (äldre) föråldrat värde. När lagerinventeringen väljs bestäms resultatet av det **totala tillgängliga** värdet, men tröskeln definieras av **inställningen för frånvaro av lagertröskel** som beskrivs senare. Den här tröskelinställningen gäller för alla produkter på en näthandelssajt. Om lagret är lägre än tröskelnumret anses en produkt vara utanför lagret. I annat fall betraktas det som i lager. Möjligheterna för **tröskelvärdet för frånvaro** är begränsade och vi rekommenderar inte att du använder det i version 10.0.12 och senare.

- **Lagerområden** – med den här inställningen definieras de lagerintervall som meddelandet visas för i moduler. Den gäller bara om antingen värdet **totala tillgängliga** eller det **fysiska tillgängliga värdet** har valts för inställning **lagernivån baserat på**. De tillgängliga värdena är **alla**, **låg och ur lagret** och inte **på lagret**.

    - När **alla** är markerat visas meddelanden för alla lagerområden, från lagret ("tillgängligt") i brist på lager ("tillgängligt").
    - När **låg och inte i lager** är markerat visas meddelanden för alla lagerområden förutom från lagret ("tillgängligt").
    - När **inte i lager** är markerat visas endast meddelandet "inte i lager".

- **Tröskel för inte i lager** – den här gamla numeriska inställningen börjar gälla först om värdet **tröskelvärdet för inte i lager** har valts för inställningen **lagernivå baserat på**.

> [!IMPORTANT] 
> Dessa inställningar finns i Dynamics 365 Commerce 10.0.12 versionen. Om du uppdaterar från en äldre version av Dynamics 365 Commerce måste du uppdatera filen appsettings.json manuellt. Information om hur du uppdaterar filen appsettings.json finns i [SDK- och modulens biblioteksuppdateringar](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).

## <a name="modules-that-use-inventory-settings"></a>Moduler som använder lagerinställningar

Ikonmodulerna inköpsruta, önskelista, butiksväljare, kundvagn och kundvagnsikon använder lagerinställningar för att visa lagerområden och meddelanden.

Följande bild visar ett exempel på en sida med produktinformation (PDP) som visar ett meddelandet "tillgängligt".

![Exempel på en PDP-modul som har ett upplagratmeddelande](./media/pdp-InStock.png)

Följande bild visar ett exempel på en PDP som visar meddelandet "Ej i lager".

![Exempel på en PDP-modul som har ett ej i lager-meddelande](./media/pdp-outofstock.png)

Följande bild visar ett exempel på en kundvagn som visar meddelandet i lager (tillgänglig).

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