---
title: Resultat för integration av sökande
description: I detta ämne beskrivs alternativuppsättningen Integreringsresultat för sökande för Dynamics 365 Human Resources.
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
ms.openlocfilehash: e8e41fe485cc70a668d4610ce6eabba5cd16ac86
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5795127"
---
# <a name="applicant-integration-result"></a>Resultat för integration av sökande

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

I detta ämne beskrivs alternativuppsättningen Integreringsresultat för sökande för Dynamics 365 Human Resources.

Fysiskt namn: mshr_hcmapplicantintegrationresult

Uppräkningen ger statusen för en kandidatpost.

| Värde | Etikett | beskrivning |
| --- | --- | --- |
| 200000000 | Inte bearbetats | Kandidaten övervägs fortfarande. |
| 200000001 | Anställd | Kandidaten har anställts. |
| 200000002 | Inte anställd | Beslut har fattats om att inte anställa kandidaten. |
| 200000003 | Ignorerat | Kandidaten avslogs från beaktande. |

## <a name="see-also"></a>Se även

[Introduktion av API för integrering av system för sökandespårning](hr-admin-integration-ats-api-introduction.md)<br>
[Exempelfråga för kandidat att anställa](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]