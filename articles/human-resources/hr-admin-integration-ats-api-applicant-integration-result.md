---
title: Resultat för integration av sökande
description: I detta ämne beskrivs alternativuppsättningen Integreringsresultat för sökande för Dynamics 365 Human Resources.
author: jaredha
manager: tfehr
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 157864cd0eee879013724615ce31306c99c5aa68
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125819"
---
# <a name="applicant-integration-result"></a>Resultat för integration av sökande

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
