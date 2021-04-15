---
title: Slutförandestatus
description: I detta ämne beskrivs alternativuppsättningen Slutförandestatus för Dynamics 365 Human Resources.
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
ms.openlocfilehash: f1b0c61ac9d9dc611d2a4700a1a004e3d15b4445
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5798379"
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