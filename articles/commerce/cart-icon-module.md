---
title: Vagnikonmodul
description: Det här avsnittet handlar om vagnikonmodulen och beskriver hur du lägger till den till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 05/28/2020
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
ms.openlocfilehash: 6771a84118504cd5c8e44302380eb970e4658902
ms.sourcegitcommit: b52477b7d0d52102a7ca2fb95f4ebfa30ecd9f54
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/29/2020
ms.locfileid: "3411099"
---
# <a name="cart-icon-module"></a>Vagnikonmodul

[!include [banner](includes/banner.md)]

Det här avsnittet handlar om vagnikonmodulen och beskriver hur du lägger till den till webbsidorna i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

Vagnikonmodulen representerar kundvagnen i huvudmodulen på sidan och visar antalet artiklar i vagnen. Vagnikonmodulen visar också en sammanfattning av kundvagnen (även kallad en minivagn) när vagnikonen hovras över. Minivagnen ger användaren en sammanfattning av artiklarna i kundvagnen utan att behöva navigera till kundvagnssidan. Dessutom kan användaren gå direkt till kassasidan om de är nöjda med sammanfattningen. Detta minskar antalet sidnavigeringer och gör utcheckningen snabbare. 

Följande bild visar ett exempel på en kundvagnsikon som visar en minikundvagn i Fabrikam-rubriken.

![Exempel på en modul för kundvagnsikon](./media/ecommerce-Minicart.PNG)

## <a name="module-properties"></a>Modulegenskaper

- **Visa minivagn** – när värdet är sant kan den här egenskapen användas för att visa en sammanfattning av kundvagnen (minivagn) när man hovrar över vagnikonen. Den här funktionen stöds endast för portar i skrivbordsvy.


## <a name="add-a-cart-icon-module-to-a-page"></a>Lägg till en vagnikonmodul på en ny sida

Mer information om hur du lägger till en vagnikonmodul finns i [Huvudmodul](author-header-module.md).


## <a name="additional-resources"></a>Ytterligare resurser

[Modul för inköpsruta](add-buy-box.md)

[Kundvagnsmodul](add-cart-module.md)

[Kassamodul](add-checkout-module.md)

[Modul för orderbekräftelse](order-confirmation-module.md)

[Modul för sidhuvud](author-header-module.md)

[Modul för sidfot](author-footer-module.md)
