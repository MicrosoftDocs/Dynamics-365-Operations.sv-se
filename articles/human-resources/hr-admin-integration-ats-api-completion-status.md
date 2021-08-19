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
ms.openlocfilehash: 67e464262897d89f80bd615156d56cc12a822dd4a0dfa6d5eb206c38ddd61ec5
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6732883"
---
# <a name="completion-status"></a>Slutförandestatus

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