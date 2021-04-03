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
ms.openlocfilehash: dd25eca9cccf46ec4e4bb2a1d948ca98985e73e4
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/17/2021
ms.locfileid: "5467563"
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