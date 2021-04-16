---
title: Orsakskoder för serviceorder
description: Använd orsakskoder för att förklara statusen för en serviceorder när dess fas uppdateras.
author: ShylaThompson
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAStageTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9548d3a29c787b49713499519e1a02b5d218ac1c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5836192"
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