---
title: Slutförandestatus
description: I detta ämne beskrivs alternativuppsättningen Slutförandestatus för Dynamics 365 Human Resources.
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
ms.openlocfilehash: da91084d30873b79033d789beab829da9fbdb010
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/31/2022
ms.locfileid: "8065556"
---
# <a name="completion-status"></a>Slutförandestatus


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

I detta ämne beskrivs alternativuppsättningen Slutförandestatus för Dynamics 365 Human Resources.

Fysiskt namn: mshr_hcmcompletionstatus

Denna uppräkning utgör alternativuppsättningen med statusvärden för gallring av sökande. 

| Värde | Etikett | beskrivning |
| --- | --- | --- |
| 200000000 | Ej fullständigt | Sökanden har ännu inte slutfört gallringen. |
| 200000001 | Lyckat | Sökanden har godkänts i gallringsprovet. |
| 200000002 | Misslyckad | Sökanden har ej godkänts i gallringsprovet. |

## <a name="see-also"></a>Se även

[Introduktion av API för integrering av system för sökandespårning](hr-admin-integration-ats-api-introduction.md)<br>
[Exempelfråga för kandidat att anställa](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
