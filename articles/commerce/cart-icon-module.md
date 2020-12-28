---
title: Vagnikonmodul
description: Det här avsnittet handlar om vagnikonmodulen och beskriver hur du lägger till den till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: ebc5cfa490a4c8538fd081aced0844ed01d63a26
ms.sourcegitcommit: 12d271bb26c7490e7525d9b4bbf125cdc39fef43
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/07/2020
ms.locfileid: "4415991"
---
# <a name="cart-icon-module"></a>Vagnikonmodul

[!include [banner](includes/banner.md)]

Det här avsnittet handlar om vagnikonmodulen och beskriver hur du lägger till den till webbsidorna i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

Vagnikonmodulen representerar kundvagnen i huvudmodulen på sidan och visar antalet artiklar i vagnen. Vagnikonmodulen visar också en sammanfattning av kundvagnen (även kallad en minivagn) när vagnikonen hovras över. Minivagnen ger användaren en sammanfattning av artiklarna i kundvagnen utan att behöva navigera till kundvagnssidan. Dessutom kan användaren gå direkt till kassasidan om de är nöjda med sammanfattningen. Detta minskar antalet sidnavigeringer och gör utcheckningen snabbare. 

> [!NOTE]
> Stöd för modulen kundvagnikon i Dynamics 365 Commerce 10.0.11-versionen.

Följande bild visar ett exempel på en kundvagnsikon som visar en minikundvagn i Fabrikam-rubriken.

![Exempel på en modul för kundvagnsikon](./media/ecommerce-Minicart.PNG)

## <a name="module-properties"></a>Modulegenskaper

- **Visa minivagn** – när värdet är sant kan den här egenskapen användas för att visa en sammanfattning av kundvagnen (minivagn) när man hovrar över vagnikonen. Den här funktionen stöds endast för portar i skrivbordsvy.

## <a name="add-a-cart-icon-module-to-a-page"></a>Lägg till en vagnikonmodul på en ny sida

Mer information om hur du lägger till en vagnikonmodul finns i [Huvudmodul](author-header-module.md).

## <a name="additional-resources"></a>Ytterligare resurser

[Kundvagnsmodul](add-cart-module.md)

[Kassamodul](add-checkout-module.md)

[Betalningsmodul](payment-module.md)

[Modul för leveransadress](ship-address-module.md)

[Modul för leveransalternativ](delivery-options-module.md)

[Informationsmodul för upphämtning](pickup-info-module.md)

[Orderinformationsmodul](order-confirmation-module.md)

[Presentkortsmodul](add-giftcard.md)
