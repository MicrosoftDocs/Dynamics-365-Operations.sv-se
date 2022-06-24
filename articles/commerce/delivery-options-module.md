---
title: Modul för leveransalternativ
description: Denna artikel omfattar moduler för leveransalternativ och förklarar hur du konfigurerar dem i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 02/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 554a17cf1c90f7fdaa20de74c3f6726910ab815d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8894568"
---
# <a name="delivery-options-module"></a>Modul för leveransalternativ

[!include [banner](includes/banner.md)]

Denna artikel omfattar moduler för leveransalternativ och förklarar hur du konfigurerar dem i Microsoft Dynamics 365 Commerce.

Med hjälp av modul för leveransalternativ kan kunderna välja leveranssätt, t.ex. leverans eller upphämtning för sin onlinebeställning. Det krävs en leveransadress för att fastställa leveranssättet. Om leveransadressen ändras måste leveransalternativen hämtas igen. Om ordern bara innehåller artiklar som ska hämtas i butiken döljs modulen automatiskt.

Mer information om hur du konfigurerar leveranssätt finns i [konfiguration av onlinekanal](channel-setup-online.md) och [Ställ in leveranssätt](/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).

Varje leveranssätt kan ha en associerad avgift. Mer information om hur du konfigurerar avgifter för en nätbutik finns i [Avancerade automatiska avgifter för flera kanaler](omni-auto-charges.md).

I Commerce version 10.0.13 har modulen leveransalternativ uppdaterats för att stödja funktionerna **huvudavgifter utan proportionell fördelning** och **leverera som radavgift**. Om proportionen är inaktiverad är det förväntat att arbetsflödet för näthandel inte tillåter ett blandat leverans sätt för artiklarna i kundvagnen (dvs. vissa artiklar väljs för leverans, men andra väljs för upphämtning). Funktionen **Huvudtillägg utan proportionell fördelning** kräver att flaggan **Aktivera konsekvent hantering av leveranssätt i kanal** aktiveras i Commerce headquarters. När funktionsflaggan är påslagen kommer fraktavgifter att tillämpas antingen på rubriknivå eller radnivå, beroende på konfigurationen i Commerce headquarters.

Temat Fabrikam har stöd för ett blandat leveranssätt, där vissa artiklar har valts för leverans men andra har valts för upphämtning. I det här läget beräknas fraktkostnaderna för alla artiklar som väljs för leveranssättet. Om ett blandat leveranssätt ska fungera måste du först konfigurera funktionen **huvudavgifter utan proportionell fördelning** i Commerce headquarters. Mer information om den här konfigurationen finns i [Fördela huvudtillägg proportionellt som matchar försäljningsraderna](pro-rate-charges-matching-lines.md).

Om leveransavgifter används på radartiklar kan de visas på kundvagnsraden för varje artikel. Den här funktionen kräver att egenskapen **Visa fraktavgifter på radartikel** aktiveras för både kundvagnsmodulen och kassamodulen. Mer information finns i [kundvagnsmodulen](add-cart-module.md) och [kassamodulen](add-checkout-module.md).

Följande bild visar ett exempel på en leveransalternativmodul på en kassasida.

![Exempel på en modul för leveranssätt på en kassasida.](./media/ecommerce-deliveryoptions.PNG)

## <a name="delivery-options-module-properties"></a>Egenskaper för modul för leveransalternativ

| Egenskap | Värden | beskrivning |
|----------|--------|-------------|
| Rubrik | Rubriktext och rubriktagg (**H1**, **H2**, **H3**, **H4**, **H5** eller **H6**) | En valfri rubrik för leveransalternativmodul. |
| Anpassat CSS-klassnamn | Text | Ett klassnamn för Överlappande formatmallar (CSS) som används för att återge modulen, om det är tillämpligt. |
| Alternativ för att filtrera leveranssätt | **Filtrera inte** eller **ej leveranssätt** | Ett värde som anger om modulen för leveransalternativ ska filtrera bort alla leveranssätt som inte kan levereras. |
| Välja ett leveransalternativ automatiskt | **Filtrera inte**, **Välj leveransalternativ automatiskt och visa sammanfattning** eller **Välj leveransalternativ automatiskt och visa inte sammanfattning** | Denna egenskap tillämpar automatiskt det första tillgängliga leveransalternativet på kassan utan att användaren måste välja det. Den bör bara användas om det finns ett tillgängligt leveransalternativ. Denna egenskap stöds från och med version 10.0.19 av Commerce. |

## <a name="add-a-delivery-options-module-to-a-checkout-page-and-set-the-required-properties"></a>Lägg till leveransalternativmodul på en kassasida och konfigurera de obligatoriska egenskaperna.

En leveransalternativmodul kan bara läggas till i en betalningsmodul. Mer information om hur du konfigurerar leveransalternativmodul och lägger till den på en kassasida finns i [betalningsmodulen](add-checkout-module.md).

> [!NOTE]
> Inkonsekvent leveranshantering kan bli resultatet, eller också kanske du inte ser icke-fördelande huvudnivåavgifter i din näthandelskanal. Information om hur du löser de här problemen finns i [Aktivera konsekvent hantering av leveranssätt i näthandelskanaler](consistent-delivery-mode-handling.md).

## <a name="additional-resources"></a>Ytterligare resurser

[Vagnmodul](add-cart-module.md)

[Kassamodul](add-checkout-module.md)

[Betalningsmodul](payment-module.md)

[Modul för leveransadress](ship-address-module.md)

[Informationsmodul för upphämtning](pickup-info-module.md)

[Orderinformationsmodul](order-confirmation-module.md)

[Presentkortsmodul](add-giftcard.md)

[Konfiguration av onlinekanal](channel-setup-online.md)

[Avancerade automatiska avgifter för flera kanaler](omni-auto-charges.md)

[Allokera huvudavgifter för att matcha försäljningsrader](pro-rate-charges-matching-lines.md)

[Ställ in leveranssätt](/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
