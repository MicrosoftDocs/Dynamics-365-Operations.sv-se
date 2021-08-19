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
ms.openlocfilehash: 3f173e15d5524dfd4d63113760760b2534cc8769456df621415a11e4053cc6fb
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6725924"
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