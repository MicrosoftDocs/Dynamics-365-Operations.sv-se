---
title: Modul för leveransalternativ
description: Det här avsnittet modul för leveransalternativ och förklarar hur du konfigurerar dem i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 08/05/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: f9e8df576efd1e58fde235828823f31e87ed58bf
ms.sourcegitcommit: 12d271bb26c7490e7525d9b4bbf125cdc39fef43
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/07/2020
ms.locfileid: "4415998"
---
# <a name="delivery-options-module"></a>Modul för leveransalternativ

[!include [banner](includes/banner.md)]

Det här avsnittet modul för leveransalternativ och förklarar hur du konfigurerar dem i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

Med hjälp av modul för leveransalternativ kan kunderna välja leveranssätt, t.ex. leverans eller upphämtning för sin onlinebeställning. Det krävs en leveransadress för att fastställa leveranssättet. Om leveransadressen ändras måste leveransalternativen hämtas igen. Om ordern bara innehåller artiklar som ska hämtas i butiken döljs modulen automatiskt.

Mer information om hur du konfigurerar leveranssätt finns i [konfiguration av onlinekanal](channel-setup-online.md) och [Ställ in leveranssätt](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).

Varje leveranssätt kan ha en associerad avgift. Mer information om hur du konfigurerar avgifter för en nätbutik finns i [Avancerade automatiska avgifter för flera kanaler](omni-auto-charges.md).

I Commerce version 10.0.13 har modulen leveransalternativ uppdaterats för att stödja funktionerna **huvudavgifter utan proportionell fördelning** och **leverera som radavgift**. Om proportionen är inaktiverad är det förväntat att arbetsflödet för näthandel inte tillåter ett blandat leverans sätt för artiklarna i kundvagnen (dvs. vissa artiklar väljs för leverans, men andra väljs för upphämtning). Funktionen **huvudavgifter utan proportionell fördelning** kräver att flaggan **Aktivera konsekvent hantering av leveranssätt i kanal** aktiveras i Commerce-administration. När den flaggan är påslagen kommer fraktkostnader att tillämpas antingen på huvudnivå eller radnivå, beroende på konfigurationen i Commerce-administration.

Temat Fabrikam har stöd för ett blandat leveranssätt, där vissa artiklar har valts för leverans men andra har valts för upphämtning. I det här läget beräknas fraktkostnaderna för alla artiklar som väljs för leveranssättet. Om ett blandat leveranssätt ska fungera måste du först konfigurera funktionen **huvudavgifter utan proportionell fördelning** i Commerce-administration. Mer information om den här konfigurationen finns i [Fördela huvudtillägg proportionellt som matchar försäljningsraderna](pro-rate-charges-matching-lines.md).

Om leveransavgifter används på radartiklar kan de visas på kundvagnsraden för varje artikel. Den här funktionen kräver att egenskapen **Visa fraktavgifter på radartikel** aktiveras för både kundvagnsmodulen och kassamodulen. Mer information finns i [kundvagnsmodulen](add-cart-module.md) och [kassamodulen](add-checkout-module.md).

Följande bild visar ett exempel på en leveransalternativmodul på en kassasida.

![Exempel på en modul för leveranssätt på en sida i kassan](./media/ecommerce-deliveryoptions.PNG)

## <a name="delivery-options-module-properties"></a>Egenskaper för modul för leveransalternativ

| Egenskap | Värden | beskrivning |
|----------|--------|-------------|
| Rubrik | Rubriktext och rubriktagg (**H1**, **H2**, **H3**, **H4**, **H5** eller **H6**) | En valfri rubrik för leveransalternativmodul. |
| Anpassat CSS-klassnamn | Text | Ett klassnamn för Överlappande formatmallar (CSS) som används för att återge modulen, om det är tillämpligt. |
| Alternativ för att filtrera leveranssätt | **Filtrera inte** eller **ej leveranssätt** | Ett värde som anger om modulen för leveransalternativ ska filtrera bort alla leveranssätt som inte kan levereras. |

## <a name="add-a-delivery-options-module-to-a-checkout-page-and-set-the-required-properties"></a>Lägg till leveransalternativmodul på en kassasida och ställa in de obligatoriska egenskaperna.

En leveransalternativmodul kan bara läggas till i en betalningsmodul. Mer information om hur du konfigurerar leveransalternativmodul och lägger till den på en kassasida finns i [betalningsmodulen](add-checkout-module.md).

## <a name="additional-resources"></a>Ytterligare resurser

[Kundvagnsmodul](add-cart-module.md)

[Kassamodul](add-checkout-module.md)

[Betalningsmodul](payment-module.md)

[Modul för leveransadress](ship-address-module.md)

[Informationsmodul för upphämtning](pickup-info-module.md)

[Orderinformationsmodul](order-confirmation-module.md)

[Presentkortsmodul](add-giftcard.md)

[Konfiguration av onlinekanal](channel-setup-online.md)

[Avancerade automatiska avgifter för flera kanaler](omni-auto-charges.md)

[Allokera huvudavgifter för att matcha försäljningsrader](pro-rate-charges-matching-lines.md)

[Ställ in leveranssätt](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery)
