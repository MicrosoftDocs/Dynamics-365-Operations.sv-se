---
title: Presentkortsmodul
description: Denna artikel handlar om presentkortsmoduler och beskriver hur du lägger till dem på webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 08/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.search.industry: ''
ms.search.form: ''
ms.openlocfilehash: 93e2a6608b6d3190df7df1d8f85fd9d7e1c18692
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9280569"
---
# <a name="gift-card-module"></a>Presentkortsmodul

[!include [banner](includes/banner.md)]

Denna artikel handlar om presentkortsmoduler och beskriver hur du lägger till dem på webbsidorna i Microsoft Dynamics 365 Commerce.

Presentkortmoduler är en vanlig typ av betalningsmoduler för att acceptera presentkort, en vanlig betalningsmetod för näthandelstransaktioner. Presentkortsmodulen kan användas med Dynamics 365, SVS, och Givex presentkortskort. SVS och Givex presentkort löses in via Adyen betalningsförmedlaren. Mer information om stöd för externa presentkort, t.ex. SVS och Givex, se [Stöd för externa presentkort](./dev-itpro/gift-card.md).

> [!NOTE]
> Stöd för att lösa in SVS och Givex presentkort under kassaflödet är tillgängligt i Dynamics 365 Commerce 10.0.11-versionen. 

Det finns två tillgängliga presentkortmoduler:

- **Presentkort** – Denna modul kan användas på en betalningssida för att lösa in ett presentkort som betalningsmedel. 
- **Kontroll av presentkortssaldo** – Denna modul kan användas på alla sidor för att kontrollera saldot på ett presentkort. Den här modulen är tillgänglig i Commerce version 10.0.14 och senare.

> [!NOTE]
> Stödet för modulen Kontroll av presentkortssaldo är tillgänglig i Dynamics 365 Commerce 10.0.14-versionen.

Följande bild visar ett exempel på en presentkortmodul på en kassasida.

![Exempel på en presentkortsmodul.](./media/ecommerce-giftcard.PNG)

## <a name="module-properties"></a>Modulegenskaper

- **Visa ytterligare fält** – Denna egenskap definierar vilka fält som ska visas för presentkort utöver presentkortsnumret, som alltid visas som standard. Vissa presentkort stöder t.ex. ett personligt ID-nummer (PIN-kod) och andra support visar en PIN-kod och ett förfallodatum. Alternativt kan den här egenskapen anges till "ingen", vilket bara visar presentkortsnumret och inga ytterligare fält.

    Följande värden stöds:

    - PIN-kod
    - Utgångsdatum
    - PIN och utgångsdatum 
    - None

- **Aktivera för gästanvändare** – När denna egenskap är aktiverad kan gästanvändare lösa in eller kontrollera saldon på presentkort. Denna egenskap kräver att anonym (gäst) åtkomst för presentkort ska aktiveras i Commerce headquarters. Mer information finns i [Aktivera presentkortsbetalningar för gästkassa](#enable-gift-card-payments-for-guest-checkout).

> [!IMPORTANT]
> Egenskapen **Aktivera för gästanvändare** är tillfälligt som Commerce version 10.0.21. De kräver att paketversion 9.31 för Commerce-modulens bibliotek är installerad.

## <a name="site-settings-for-gift-card-modules"></a>Platsinställningar för presentkortsmoduler

I Commerce webbplatsskaparen under **webbplatsinställnings \> tillägg**, finns en presentkorts inställning som kallas **presentkortstyp som stöds**. Den här inställningen har stöd för tre värden:
- **Dynamics 365-presentkort** – När den här inställningen används tillåter presentkortsmodulen bara inlösen av Dynamics 365-presentkort. Den här inställningen stöds endast för inloggade användare på webbplatsen för näthandel.
- **SVS- och Givex-presentkort** – När den här inställningen används tillåter presentkortsmodulen bara inlösen av SVS- och Givex-presentkort. Den här inställningen stöds för inloggade anonyma användare på webbplatsen för näthandel.
- **Dynamics 365-, SVS- och Givex-presentkort** – När den här inställningen används tillåter presentkortet inlösen av Dynamics 365-, Givex- och SVS-presentkort. Den här inställningen stöds endast för inloggade användare på webbplatsen för näthandel.

> [!IMPORTANT]
> Dessa inställningar är tillgängliga i Dynamics 365 Commerce 10.0.11-versionen och krävs endast om du behöver stöd för SVS eller Givex presentkort. Om du uppdaterar från en äldre version av Dynamics 365 Commerce måste du uppdatera filen appsettings.json manuellt. Information om hur du uppdaterar filen appsettings.json finns i [SDK- och modulens biblioteksuppdateringar](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file). 

## <a name="extend-internal-gift-cards-for-use-in-e-commerce-storefronts"></a>Utöka interna presentkort för användning i näthandelsbutik

Som standard är interna presentkort inte optimerade för användning i näthandelsskyltfönster. Innan du tillåter att interna presentkort används som betalning bör du därför konfigurera dem med tillägg som gör dem säkrare. Här följer de områden med presentkort som du bör utöka innan du tillåter att interna presentkort används i produktionen:

- **Presentkortsnummer** – Nummerserier används för att generera presentkortsnummer för interna presentkort. Eftersom nummerserier enkelt kan förutsägas bör du utöka genereringen av presentkortsnummer så att slumpmässiga, kryptografiskt säkra strängar används för de presentkortsnummer som utfärdas.
- **GetBalance** – API:t **GetBalance** används för att slå upp presentkortssaldon. Som standard är denna API offentlig. Om en PIN-kod inte krävs för att slå upp presentkortssaldon finns det en risk för att råstyrkeattacker kan använda API:t **GetBalande** för att söka efter presentkortsnummer som har saldon. Genom att implementera både PIN-krav för interna presentkort och API-begränsning kan du minska risken.
- **PIN** – Som standard har interna presentkort inte stöd för PINs. Du bör utöka interna presentkort så att det krävs en PIN-kod för att slå upp saldon. Den här funktionen kan även användas för att låsa presentkort efter på varandra följande felaktiga försök att ange PIN-koden.

## <a name="enable-gift-card-payments-for-guest-checkout"></a>Aktivera presentkortsbetalningar för gästkassa

Som standard aktiveras inte presentkortsbetalningar för gästkassa (anonymt). För att aktivera dem följer du stegen nedan.

1. I Commerce headquarters går du till **Retail och Commerce \> Kanalinställningar \> Kassainställningar \> Kassa \> Kassafunktioner**.
1. Markera och håll (eller högerklicka) på rutnätets rubrik och välj sedan **Infoga kolumner**.
1. I dialogrutan **Infoga kolumner** väljer du kryssrutan **AllowAnonymousAccess**.
1. Välj **Uppdatera**.
1. För funktionerna **520** (presentkortssaldo) och **214** anger du värdet för **AllowAnonymousAccess** som **1**.
1. Välj **Spara**.
1. Kör schemaläggningsjobbet **1090** för att synkronisera ändringar i kanaldatabasen. 

## <a name="add-a-gift-card-module-to-a-page"></a>Lägg till presentkortmodulen på en ny sida

Instruktioner om hur du lägger till en presentkortsmodul på en betalningssida och anger de obligatoriska egenskaperna finns i [betalningsmodulen](add-checkout-module.md).

## <a name="additional-resources"></a>Ytterligare resurser

[Kundvagnsmodul](add-cart-module.md)

[Ikon för kundvagnsmodul](cart-icon-module.md)

[Kassamodul](add-checkout-module.md)

[Betalningsmodul](payment-module.md)

[Modul för leveransadress](ship-address-module.md)

[Modul för leveransalternativ](delivery-options-module.md)

[Informationsmodul för upphämtning](pickup-info-module.md)

[Orderinformationsmodul](order-confirmation-module.md)

[Stöd för externa presentkort](./dev-itpro/gift-card.md)

[Uppdateringar av SDK och modulbibliotek](e-commerce-extensibility/sdk-updates.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
