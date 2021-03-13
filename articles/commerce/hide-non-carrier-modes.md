---
title: Dölj leveranssätt som inte är transportsätt från leveransalternativen i POS
description: Det här ämnet beskriver ett konfigurationsalternativ som gör det möjligt att förhindra att leveranssätt som inte är transportsätt för val när en leveransorder skapas i POS.
author: hhainesms
manager: annbe
ms.date: 10/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: hhaines
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: fcacb4243e78607d19d2c57aff5debe04d85d6f2
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "5009733"
---
# <a name="hide-non-carrier-delivery-modes-from-the-shipping-options-in-pos"></a>Dölj leveranssätt som inte är transportsätt från leveransalternativen i POS


[!include [banner](includes/banner.md)]

Det här ämnet beskriver ett konfigurationsalternativ som är tillgängligt för kassaprogrammet (POS). Det här konfigurationsalternativet ändrar beteendet för valet av leveranssätt när en leveransorder skapas i POS.

När användarna skapar kundleveransorder i POS kan de välja ett leveranssätt för försändelsen. Den här funktionen är tillgänglig oavsett om hela ordern levereras eller endast är valda rader.

Som standard visas alla giltiga leveranssätt för kombinationen av en kanal, en artikel och en leveransadress i dialogrutan där leveranssättet väljs. Dessa leveranssätt definieras på sidan **Leveranssätt** i Administration (**Försäljning och marknadsföring \> Inställning \> Distribution \> Leveranssätt**). Leveranssätt som inte är transportsätt, t.ex. **Utför** eller **Upphämtning** kan också visas för val i dialogrutan.

En funktion har dock lagts till som gör att du kan dölja leveranssätt som inte är transportsätt i dialogrutan. Om du vill aktivera den här funktionen går du till sidan **handelsparametrar** på fliken **kundorder** och anger alternativet **Visa endast alternativ där leveranssätt är transportsätt** till **Ja**. När du har aktiverat den här funktionen och kört lämpliga distributionsjobb för att synkronisera informationen med kanaldatabasen visas inte leveranssätt för andra företag för val under processen med att skapa leveransorder i POS.
