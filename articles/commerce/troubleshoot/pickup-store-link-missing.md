---
title: Hämtningsalternativet visas inte på informationssidorna för vagnen eller produkten
description: Det här avsnittet innehåller felsökningsvägledning som kan vara till hjälp när alternativet för upphämtning i butiken inte visas på vagnsidan eller produktinformationssidorna.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: f692d73bf1755422e9bfc8314c1156e043ccf761
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020826"
---
# <a name="pick-this-up-option-doesnt-appear-on-cart-or-product-details-pages"></a>Hämtningsalternativet visas inte på informationssidorna för vagnen eller produkten

[!include [banner](../../includes/banner.md)]

Det här avsnittet innehåller felsökningsvägledning som kan vara till hjälp när alternativet för upphämtning i butiken inte visas på vagnsidan eller produktinformationssidorna.

## <a name="description"></a>beskrivning

Knappen **Plocka upp** visas inte på informationssidorna för vagnen eller produkten.

I bilden nedan visas ett exempel på en sida där knappen **Plocka upp** finns.

![Plocka upp den här knappen](media/pickup-button-missing.jpg)

## <a name="resolution"></a>Upplösning

### <a name="enable-the-bopis-extension-in-commerce-site-builder"></a>Aktivera BOPIS-filnamnstillägget i Commerce-webbplatsbyggaren

Aktivera filnamnstillägget "handla online, upphämtning i butik" (BOPIS) i Commerce-webbplatsbyggaren genom att följa stegen nedan.

1. Välj din webbplats.
1. Välj **webbplatsinställningar** och välj sedan **tillägg**.
1. Kontrollera att alternativet **Inaktivera BOPIS** är avmarkerat.

### <a name="configure-modes-of-delivery-in-commerce-headquarters"></a>Konfigurera leveranssätt i Commerce-administration

För att konfigurera leveranssätt i Commerce-administration, följ dessa steg.

1. Gå till **Anskaffning och källa \> Inställningar \> Leveranssätt**.
1. Se till att ett leveranssätt **Kundplockning** har skapats och att produkter och adresser tilldelas den.
1. Öppna **Retail och Commerce \> Administrationsinställning \> Parametrar**.
1. I navigeringsfönstret till vänster välj er du **Kundorder**.
1. Se till leveranssättet **Leveranssätt: upphämtning** är korrekt konfigurerat.

### <a name="configure-customer-orders-payments"></a>Konfigurera kundorderbetalningar

För att konfigurera kundorderbetalningar i Commerce-administration, följ dessa steg.

1. Öppna **Retail och Commerce \> Administrationsinställning \> Parametrar**.
1. I navigeringsfönstret till vänster välj er du **Kundorder**.
1. På snabbfliken **Betalningar**, se till att fälten **Betalningsvillkor** och **Betalningsmetod** är korrekt inställda.

## <a name="additional-resources"></a>Ytterligare resurser

[Konfigurera BOPIS](../cpe-bopis.md)

[Aktivera flera leveranssätt genom upphämtning för kundorder](../multiple-pickup-modes.md)

[Flerkanals orderbetalningar för Commerce](../dev-itpro/commerce-payments.md)

[Modul för butiksväljare](../store-selector.md)
