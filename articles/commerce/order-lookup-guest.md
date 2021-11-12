---
title: Aktivera ordersökning för gästutcheckningar
description: I det här avsnittet beskrivs hur du aktiverar ordersökning för gästutcheckningar i Microsoft Dynamics 365 Commerce.
author: stuharg
ms.date: 09/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2021-08-15
ms.dyn365.ops.version: Release 10.0.22
ms.openlocfilehash: 639ee670b83198423425d03dad308306c9eed25c
ms.sourcegitcommit: 1707cf45217db6801df260ff60f4648bd9a4bb68
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/23/2021
ms.locfileid: "7674986"
---
# <a name="enable-order-lookup-for-guest-checkouts"></a>Aktivera ordersökning för gästutcheckningar

[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du aktiverar ordersökning för gästutcheckningar i Microsoft Dynamics 365 Commerce.

Genom att söka efter order för gästutcheckningar kan kunder som gör inköp som gästanvändare söka efter sina order. Sökfunktionen för order är användbar när kunder vill utföra åtgärder som t.ex. att kontrollera uppfyllelsestatus för produkter på en order, verifiera adressen som en order har levererats till, beställa om en produkt eller bekräfta butiken som en order kommer att hämtas från.

Kunder som gör beställningar som registrerade användare kan se sina orderuppgifter när de är inloggade, men kunder som använder gästutcheckning för att göra beställningar kan inte göra det. När ordersökningen för funktionen gästutcheckningar är aktiverad, ger den ett formulär som kunder kan använda för att söka efter beställningar som de har gjort som gäster. I det här formuläret anger kunder orderbekräftelse-ID och (valfritt) den e-postadress som de angett i kassan.

En länk eller knapp som tar kunden direkt till sidan med orderinformation för sin order kan också inkluderas i orderrelaterade transaktionsmeddelanden. Denna länk eller knapp fungerar för beställningar som har gjorts både av registrerade användare och av gästanvändare.

## <a name="turn-on-necessary-features-in-commerce-headquarters"></a>Aktivera nödvändiga funktioner i Commerce Headquarters

Om du vill aktivera ordersökning för gästutcheckningar måste du aktivera följande funktioner i **Arbetsytor \> Funktionshantering** i Commerce Headquarters.

| Funktion | Syfte |
|---------|---------|
| Valfunktion för anonym användarsökordningsinformation i Retail | Den här funktionen visar användargränssnittet i Commerce-parametrar som gör att du kan aktivera ordersöknings-API för oautentiserade användare och konfigurera hur personliga data visas. |
| Aktivera generering av ett referens-ID för kanalen som används för kanalen | Den här funktionen genererar ett säkrare 12-teckens kanalreferens-ID (orderbekräftelse-ID) som kan skickas i frågesträngen när en order söks upp. |
| Generera ett konsekvent format för kanalreferens-ID för alla kanaler | Den här funktionen genererar ett säkert kanalreferens-ID för beställningar som görs via en näthandelsplats, en butikskassa (POS) eller ett kundtjänstcenter. Innan du kan aktivera funktionen måste funktionen **Aktivera generering av ett starkare kanalreferens-ID** vara aktiverad. |

När du har aktiverat funktionen **alternativ för anonym Retail-användares sökning av orderdetaljer** måste du aktivera det API som stöder ej autentiserad ordersökning i Commerce headquarters. Öppna **Retail och Commerce \> Administrationsinställning \> Parametrar \> Kundorder**. På sidan **Kundorder**, på snabbfliken **Ordersökning**, anger du alternativet **Aktivera ej autentiserad ordersökning** som **Ja**, så som visas på bilden nedan.

## <a name="manage-the-display-of-personal-data"></a>Hantera visningen av personuppgifter

Snabbfliken **Ordersökning** på sidan **Kundorder** i Commerce headquarters innehåller fältet **Inkludera personuppgifter i gästs ordersökning** där du styr om personlig information visas för kunder. Den här personliga informationen inkluderar kundens leveransadress och de fyra sista siffrorna i kundens kreditkortsnummer. Som standard visas inte personlig information för kunder när ej autentiserad ordersökning har aktiverats. Det tillgängliga alternativen beskrivs i följande tabell.

| Alternativ | Resultat |
|--------|--------|
| Aldrig | Standardvärdet. Ingen personlig information visas i ordersökning. När registrerade användare som är inloggade söker efter en order som de skapade när de var inloggade kommer de att kunna se sina personuppgifter. |
| Endast gästorder | Personlig information visas i ordersökningar för order som kunder har skapat som gäster. Om en order skapats av en registrerad användare måste den användaren logga in för att se sina personuppgifter. |
| Alla order | Personlig information visas i alla ordersökningar. |

> [!NOTE]
> Dessa alternativ avgör när personuppgifter, till exempel kundens adress och de fyra sista siffrorna i kundens kreditkortsnummer, visas för anonyma gästanvändare. För att skydda registrerade kunders integritet rekommenderar vi att du endast väljer alternativet **Endast gästorder**. Det säkraste alternativet är dock **Aldrig**.

När du har ändrat värdet i fältet **Inkludera personuppgifter i gästs ordersökning** måste du köra jobb 1070 (**Kanalkonfiguration**) i Commerce headquarters genom att gå till **Retail och Commerce \> Retail och Commerce IT \> Distributionsschema**.

## <a name="configure-the-order-lookup-module"></a>Konfigurera modulen för ordersökning

Modulen för ordersökning i Commerce-modulbibliotek används för att återge det formulär som gästanvändare använder för att söka efter order. Sökmodulen för order kan inkluderas i brödtexten på alla sidor där kundens inloggning inte krävs. Information om hur du konfigurerar modulen finns i [Modul för ordersökning](order-lookup-module.md).

## <a name="additional-resources"></a>Ytterligare resurser

[Modul för ordersökning](order-lookup-module.md)

[Ställa in en meddelandeprofil för e-post](email-notification-profiles.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
