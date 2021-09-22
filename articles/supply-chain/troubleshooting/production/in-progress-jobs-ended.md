---
title: Pågående jobb avslutas när delkvantitet rapporteras för senaste jobb
description: När jobbkortsenheten används för att rapportera en delkvantitet för det sista jobbet i en produktionsorder avslutas automatiskt alla tidigare jobb som har statusen Pågår.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 11511d4ac7524facdd0d647e9bc38fe09c282be1
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477674"
---
# <a name="previous-in-progress-jobs-are-ended-when-reporting-partial-quantity-on-last-job"></a>Föregående pågående jobb avslutas när delkvantitet rapporteras för senaste jobb

## <a name="symptoms"></a>Symtom

När du använder jobbkortsenheten för att rapportera en delkvantitet för det sista jobbet i en produktionsorder, avslutas automatiskt alla tidigare jobb på den ordern som har statusen Pågår.

## <a name="resolution"></a>Lösning

Detta beteende är av design. På sidan **Standarder för produktionsorder** på fliken **Rapportera som färdigt** finns alternativet **Slutmarkera flöde**. Om det här avsnittet är inställt på *Ja*, bokförs en flödeskortjournal när en arbetare använder jobbkortsenhet eller jobbkortsterminal för att rapportera den senaste operationen. Den här journalen markerar alla operationer som slutförda och avslutar alla produktionsjobb. När alternativet **Slutmarkera flöde** anges till *Ja* tar systemet inte hänsyn till den jobbstatus som arbetare valde när de rapporterade den senaste åtgärden. Systemet betraktar inte heller om arbetaren rapporterar en fullständig eller partiell kvantitet.
