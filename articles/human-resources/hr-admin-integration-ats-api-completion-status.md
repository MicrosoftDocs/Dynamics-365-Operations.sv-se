---
title: Slutförandestatus
description: I denna artikel beskrivs alternativuppsättningen Slutförandestatus för Dynamics 365 Human Resources.
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
ms.openlocfilehash: 32575dfdd9bcd61b8a16bb544a9e7906ec96eaa1
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8880579"
---
# <a name="completion-status"></a>Slutförandestatus


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

I denna artikel beskrivs alternativuppsättningen Slutförandestatus för Dynamics 365 Human Resources.

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
