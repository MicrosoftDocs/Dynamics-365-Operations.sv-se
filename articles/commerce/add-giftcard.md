---
title: Presentkortsmodul
description: Det här avsnittet handlar om presentkortsmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
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
ms.openlocfilehash: fc47d590789c79c08af7555222aa7cc9409da23c
ms.sourcegitcommit: 8028fbc5b9585e87d3331ea02577ff82ede090af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/16/2020
ms.locfileid: "3817436"
---
# <a name="gift-card-module"></a>Presentkortsmodul

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Det här avsnittet handlar om presentkortsmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

Presentkortmoduler är en vanlig typ av betalningsmoduler för att acceptera presentkort, en vanlig betalningsmetod för e-handelstransaktioner. Presentkortsmodulen kan användas med Dynamics 365, SVS, och Givex presentkortskort. SVS och Givex presentkort löses in via Adyen betalningsförmedlaren. Mer information om stöd för externa presentkort, t.ex. SVS och Givex, se [Stöd för externa presentkort](./dev-itpro/gift-card.md).

> [!NOTE]
> Stöd för att lösa in SVS och Givex presentkort under kassaflödet är tillgängligt i Dynamics 365 Commerce 10.0.11-versionen. 

Det finns två tillgängliga presentkortmoduler:

- **Presentkort** – den här modulen kan användas på en betalningssida för att lösa in ett presentkort som betalningsmedel. 
- **Kontroll av presentkortssaldo** – den här modulen kan användas på alla sidor för att kontrollera saldot på ett presentkort. Den här modulen är tillgänglig i Commerce version 10.0.14 och senare.

> [!NOTE]
> Stödet för modulen Kontroll av presentkortssaldo är tillgänglig i Dynamics 365 Commerce 10.0.14-versionen.

Följande bild visar ett exempel på en presentkortmodul på en kassasida.

![Exempel på en presentkortsmodul](./media/ecommerce-giftcard.PNG)

## <a name="module-properties"></a>Modulegenskaper

- **Visa ytterligare fält** – den här egenskapen definierar vilka fält som ska visas för presentkort utöver presentkortsnumret, som alltid visas som standard. Vissa presentkort stöder t.ex. ett personligt ID-nummer (PIN-kod) och andra support visar en PIN-kod och ett förfallodatum. Alternativt kan den här egenskapen anges till "ingen", vilket bara visar presentkortsnumret och inga ytterligare fält.

Värden som stöds:
-   PIN-kod
-   Utgångsdatum
-   PIN och utgångsdatum 
-   None

## <a name="site-settings-for-gift-card-modules"></a>Platsinställningar för presentkortsmoduler

I Commerce webbplatsskaparen under **webbplatsinställnings \> tillägg**, finns en presentkorts inställning som kallas **presentkortstyp som stöds**. Den här inställningen har stöd för tre värden:
- **Dynamics 365 presentkort** - när den här inställningen används tillåter presentkortet bara inlösen av Dynamics 365-presentkort. Den här inställningen stöds endast för inloggade användare på webbplatsen för e-handel.
- **SVS- och Givex-presentkort** - när den här inställningen används tillåter presentkortet bara inlösen av SVS- och Givex-presentkort. Den här inställningen stöds för inloggade anonyma användare på webbplatsen för e-handel.
- **Dynamics 365, SVS- och Givex-presentkort** - när den här inställningen används tillåter presentkortet inlösen av Dynamics 365, Givex och SVS-presentkort. Den här inställningen stöds endast för inloggade användare på webbplatsen för e-handel.

> [!IMPORTANT]
> Dessa inställningar är tillgängliga i Dynamics 365 Commerce 10.0.11-versionen och krävs endast om du behöver stöd för SVS eller Givex presentkort. Om du uppdaterar från en äldre version av Dynamics 365 Commerce måste du uppdatera filen appsettings.json manuellt. Information om hur du uppdaterar filen appsettings.json finns i [SDK- och modulens biblioteksuppdateringar](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file). 

## <a name="add-a-gift-card-module-to-a-page"></a>Lägg till presentkortmodulen på en ny sida

Instruktioner om hur du lägger till en presentkortsmodul på en betalningssida och anger de obligatoriska egenskaperna finns i [betalningsmodulen](add-checkout-module.md).

## <a name="additional-resources"></a>Ytterligare resurser

[Kundvagnsmodul](add-cart-module.md)

[Ikon för kundvagnsmodul](cart-icon-module.md)

[Kassamodul](add-checkout-module.md)

[Betalningsmodul](payment-module.md)

[Modul för leveransadress](ship-address-module.md)

[Modul för leveransalternativ](delivery-options-module.md)

[Orderinformationsmodul](order-confirmation-module.md)

[Stöd för externa presentkort](./dev-itpro/gift-card.md)

[Uppdateringar av SDK och modulbibliotek](e-commerce-extensibility/sdk-updates.md)
