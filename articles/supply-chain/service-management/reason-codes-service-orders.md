---
title: Orsakskoder för serviceorder
description: Använd orsakskoder för att förklara statusen för en serviceorder när dess fas uppdateras.
author: ShylaThompson
manager: AnnBe
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAStageTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cdade89d07fec6a01926015a8c73bacce015fd7a
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1563843"
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



