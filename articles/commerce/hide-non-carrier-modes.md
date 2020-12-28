---
title: Dölj leveranssätt som inte är transportsätt från leveransalternativen i kassan
description: Det här ämnet beskriver ett konfigurationsalternativ som gör det möjligt att förhindra att leveranssätt som inte är transportsätt för val när en leveransorder skapas i kassan (POS).
author: hhainesms
manager: annbe
ms.date: 10/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: hhaines
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.7
ms.openlocfilehash: 38d57ed5f8d2b8725cd11156f0135988bb76e047
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415919"
---
# <a name="hide-non-carrier-delivery-modes-from-the-shipping-options-in-pos"></a>Dölj leveranssätt som inte är transportsätt från leveransalternativen i kassan


[!include [banner](includes/banner.md)]

Det här ämnet beskriver ett konfigurationsalternativ som är tillgängligt för kassaprogrammet (POS). Det här konfigurationsalternativet ändrar beteendet för valet av leveranssätt när en leveransorder skapas i POS.

När användarna skapar kundleveransorder i kassan kan de välja ett leveranssätt för försändelsen. Den här funktionen är tillgänglig oavsett om hela ordern levereras eller endast är valda rader.

Som standard visas alla giltiga leveranssätt för kombinationen av en kanal, en artikel och en leveransadress i dialogrutan där leveranssättet väljs. Dessa leveranssätt definieras på sidan **Leveranssätt** i Administration (**Försäljning och marknadsföring \> Inställning \> Distribution \> Leveranssätt**). Leveranssätt som inte är transportsätt, t.ex. **Utför** eller **Upphämtning** kan också visas för val i dialogrutan.

En funktion har dock lagts till som gör att du kan dölja leveranssätt som inte är transportsätt i dialogrutan. Om du vill aktivera den här funktionen går du till sidan **handelsparametrar** på fliken **kundorder** och anger alternativet **Visa endast alternativ där leveranssätt är transportsätt** till **Ja**. När du har aktiverat den här funktionen och kört lämpliga distributionsjobb för att synkronisera informationen med kanaldatabasen visas inte leveranssätt för andra företag för val under processen med att skapa leveransorder i kassan.
