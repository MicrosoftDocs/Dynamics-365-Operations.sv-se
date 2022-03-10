---
title: Avanmälan av anpassade rekommendationer
description: I det här avsnittet beskrivs hur du kan låta kunderna avanmäla si från anpassade rekommendationer i Microsoft Dynamics 365 Commerce.
author: bebeale
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: f634e39fe8ca7ffecfd1952933cb82e1bfe7d5a8eec28a61e1d78d21847f95f6
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6772947"
---
# <a name="opt-out-of-personalized-recommendations"></a>Avanmäl anpassade rekommendationer

[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du kan låta kunderna avanmäla si från anpassade rekommendationer i Microsoft Dynamics 365 Commerce.

När kontot skapas konfigureras nya kunder automatiskt för att ta emot anpassade rekommendationer. Med Dynamics 365 Commerce har olika sätt för återförsäljare att låta användarna välja att inte ta emot dessa rekommendationer och begränsa bearbetningen av personuppgifter. Autentiserade användare som avanmäler sig från anpassade rekommendationer kommer omedelbart att sluta se anpassade listor. Dessutom kommer alla personliga data som samlas in för anpassning att tas bort från anpassade rekommendationsmodeller.

Mer information om anpassade produktrekommendationer finns i [aktivera anpassade rekommendationer](personalized-recommendations.md).

## <a name="ways-for-retailers-to-implement-an-opt-out-experience"></a>Sätt för återförsäljare att använda en avanmälningsupplevelse

Återförsäljare har tre sätt att använda en avanmälningsupplevelse.

### <a name="opting-out-on-behalf-of-users"></a>Avanmäla sig för användarnas räkning

I kontohantering i backoffice i Commerce kan återförsäljare avanmäla sig för användarnas räkning.

1. På startsidan för backoffice söker du efter **alla kunder**.
1. Sök efter och välj en kund och välj sedan snabbfliken **butik**.

    ![Snabbfliken Butik.](./media/Disablepersonalizationpart1.png)

1. Under **sekretess** anger du alternativet **inaktivera anpassningar** till **ja**.

    ![Sekretessinställningar.](./media/Disablepersonalizationpart2.png)

1. Markera **Spara** och stäng sedan sidan.

### <a name="module-based-opt-out-experience"></a>Modulbaserad avanmälningsupplevelse

Återförsäljare kan låta autentiserade användare välja att inte använda anpassade rekommendationer. För att tillhandahålla den här avanmälningsupplevelsen lägger du till avanmälningsmodulen i profilsidor för kundkonton.

### <a name="custom-extensions"></a>Anpassade tillägg

Återförsäljare kan skapa sina egna tillägg för att hantera användarnas avanmälningsfunktioner. Mer information finns i [anropa API:er för Butik](e-commerce-extensibility/call-retail-server-apis.md) och [Utbyggbarhet av onlinekanal](e-commerce-extensibility/overview.md).

## <a name="obtain-a-digital-copy-of-personalized-recommendations-data-on-behalf-of-an-authenticated-user"></a>Skaffa en digital kopia av dina anpassade rekommendationer, data för en autentiserad användares räkning

Kunderna kanske vill skaffa en digital kopia av sina personliga data och också se en exporterad vy över sina rekommendationer. Om en kund begär denna information måste återförsäljaren skapa ett anpassat tillägg som anropar API i Retail Server och fråga efter fullständiga resultat från listan **Dina val** som baseras på kundens kund-ID. Resultaten kan sedan exporteras i CSV-format (kommaavgränsade värden) och delas med kunden.

Följande exempel visar hur en återförsäljare kan utföra uppgiften.

1. Återförsäljaren skapar ett anpassat tillägg för att hämta personliga rekommendationer för användarens räkning. Information om hur du skapar moduler, klonar befintliga moduler, anropar API:er för Retail Server och anropar dataåtgärder finns i [Utbyggbarhet för onlinekanal](e-commerce-extensibility/overview.md).
2. Det anpassade tillägget gör ett anrop till grundläggande dataåtgärder **skaffa rekommendationer** och skickar den nödvändiga informationen till den, baserat på kraven i listan. Om du väljer listan **plockningar för dig** måste tillägget skicka rätt listnamn och kund-ID till dataåtgärden.

    Ett sätt att skapa det anpassade tillägget är att klona den befintliga modulen för produktsamlingar som används för att returnera rekommendationer. Genom att klona denna befintliga modul kan en återförsäljare ändra den befintliga koden och lägga till en ny knapp som exporterar rekommendationerna till en CSV-fil. Mer information finns i [Klona en modul för modulbibliotek](e-commerce-extensibility/clone-starter-module.md) och [Produktsamlingsmoduler](product-collection-module-overview.md).

    En fullständig vy av API-biblioteket för Retail Server finns i [API:er för Retail Server-kund och -konsument](dev-itpro/retail-server-customer-consumer-api.md).

3. När det anpassade tillägget har skapats kan återförsäljaren exportera en CSV-fil med alla rekommendationer, baserat på det unika kund-ID:t för den autentiserade användaren.
4. Återförsäljaren kan dela den exporterade CSV-filen som innehåller den fullständiga anpassade listan över rekommenderade produkter med den autentiserade användaren.

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt av produktrekommendationer](product-recommendations.md)

[Aktivera Azure Data Lake Storage i en Dynamics 365 Commerce-miljö](enable-adls-environment.md)

[Aktivera produktrekommendationer](enable-product-recommendations.md)

[Aktivera anpassade rekommendationer](personalized-recommendations.md)

[Aktivera rekommendationer för "köp liknande produkter"](shop-similar-looks.md)

[Lägga till produktrekommendationer i POS](product.md)

[Lägg till rekommendationer på transaktionsskärmen](add-recommendations-control-pos-screen.md)

[Justera rekommendationsresultat från AI-ML](modify-product-recommendation-results.md)

[Skapa granskade rekommendationer manuellt](create-editorial-recommendation-lists.md)

[Skapa rekommendationer med demodata](product-recommendations-demo-data.md)

[Vanliga frågor om produktrekommendationer](faq-recommendations.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
