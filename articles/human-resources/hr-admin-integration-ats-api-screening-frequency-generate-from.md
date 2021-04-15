---
title: Gallringsfrekvens genereras från
description: Detta ämne beskriver frekvensen för gallringsfrekvens från alternativuppsättningen för Dynamics 365 Human Resources.
author: jaredha
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: bee0522ea244cab2f5d6864b2a763df6e314e02d
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5805164"
---
# <a name="screening-frequency-generate-from"></a>Gallringsfrekvens genereras från

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Detta ämne beskriver frekvensen för gallringsfrekvens från alternativuppsättningen för Dynamics 365 Human Resources.

Fysiskt namn: mshr_hcmfrequencygeneratefrom

Uppräkningen utgör alternativuppsättningen med värden för att bestämma startdatumet för beräkningen av nästa erforderliga gallring.

| Värde | Etikett | beskrivning |
| --- | --- | --- |
| 200000000 Ej vald | Inget värde har valts. |
| 200000001 Datum för slutförande | Beräkningen görs från det senaste gallringsdatumet som har slutförts. |
| 200000002 Datum krävs | Beräkningen görs från det senaste erforderliga gallringsdatumet. |

## <a name="see-also"></a>Se även

[Introduktion av API för integrering av system för sökandespårning](hr-admin-integration-ats-api-introduction.md)<br>
[Exempelfråga för kandidat att anställa](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]