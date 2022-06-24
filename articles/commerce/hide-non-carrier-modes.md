---
title: Dölj leveranssätt som inte är transportsätt från leveransalternativen i POS
description: Denna artikel beskriver ett konfigurationsalternativ som gör det möjligt att förhindra att leveranssätt som inte är transportsätt för val när en leveransorder skapas i POS.
author: hhainesms
ms.date: 10/24/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: hhaines
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 469e6ebb8afed26a6bf25f4c9c3ab8f7f4ac78ba
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8897015"
---
# <a name="hide-non-carrier-delivery-modes-from-the-shipping-options-in-pos"></a>Dölj leveranssätt som inte är transportsätt från leveransalternativen i POS


[!include [banner](includes/banner.md)]

Denna artikel beskriver ett konfigurationsalternativ som är tillgängligt för kassaprogrammet (POS). Det här konfigurationsalternativet ändrar beteendet för valet av leveranssätt när en leveransorder skapas i POS.

När användarna skapar kundleveransorder i POS kan de välja ett leveranssätt för försändelsen. Den här funktionen är tillgänglig oavsett om hela ordern levereras eller endast är valda rader.

Som standard visas alla giltiga leveranssätt för kombinationen av en kanal, en artikel och en leveransadress i dialogrutan där leveranssättet väljs. Dessa leveranssätt definieras på sidan **Leveranssätt** i Administration (**Försäljning och marknadsföring \> Inställning \> Distribution \> Leveranssätt**). Leveranssätt som inte är transportsätt, t.ex. **Utför** eller **Upphämtning** kan också visas för val i dialogrutan.

En funktion har dock lagts till som gör att du kan dölja leveranssätt som inte är transportsätt i dialogrutan. Om du vill aktivera den här funktionen går du till sidan **handelsparametrar** på fliken **kundorder** och anger alternativet **Visa endast alternativ där leveranssätt är transportsätt** till **Ja**. När du har aktiverat den här funktionen och kört lämpliga distributionsjobb för att synkronisera informationen med kanaldatabasen visas inte leveranssätt för andra företag för val under processen med att skapa leveransorder i POS.


[!INCLUDE[footer-include](../includes/footer-banner.md)]