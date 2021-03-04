---
title: Orsakskoder för serviceorder
description: Använd orsakskoder för att förklara statusen för en serviceorder när dess fas uppdateras.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAStageTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ec8a318561663f4a1b2cfd7735b5c1a5d18e8c0f
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437418"
---
# <a name="reason-codes-for-service-orders"></a>Orsakskoder för serviceorder   

[!include [banner](../includes/banner.md)]


Du kan använda orsakskoder för att förklara statusen för en serviceorder när dess fas uppdateras. Om du till exempel annullerar en serviceorder kan du välja en orsakskod för annulleringen.

Kör rapporten Serviceorderförlopp om du vill visa information om orsakskoder som används för att följa serviceorderförlopp. Rapporten listar alla serviceorder, oavsett vilken fas de befinner sig i, samt de orsakskoder som specificeras när en serviceorderfas uppdateras.

## <a name="turn-reason-codes-on-or-off"></a>Aktivera eller inaktivera orsakskoder

Orsakskoder är valfria. Du kan välja om det ska krävas en orsakskod när du uppdaterar en serviceorder från en viss servicefas.

1.  Klicka på **servicehantering**\>**inställningar**\>**serviceorder**\>**Servicefaser**.

2.  I formuläret **Servicefaser** väljer du en servicefas och markerar sedan kryssrutan **Orsaker** för servicefasen.

3.  Stäng formuläret så att ändringarna sparas.

## <a name="see-also"></a>Se även

[Ställ in serviceorderfaser](set-up-service-order-stages.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]