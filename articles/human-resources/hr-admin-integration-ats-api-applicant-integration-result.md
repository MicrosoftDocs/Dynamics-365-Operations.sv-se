---
title: Resultat för integration av sökande
description: I detta ämne beskrivs alternativuppsättningen Integreringsresultat för sökande för Dynamics 365 Human Resources.
author: jaredha
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 425fc78edc933b79879c330284ef911c6fd4fd1c
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/31/2022
ms.locfileid: "8066378"
---
# <a name="applicant-integration-result"></a>Resultat för integration av sökande


[!INCLUDE [PEAP](../includes/peap-1.md)]

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
