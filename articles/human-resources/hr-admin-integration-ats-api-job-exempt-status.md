---
title: Befrielsestatus för jobb
description: I detta ämne beskrivs alternativuppsättningen Befrielsestatus för jobb för Dynamics 365 Human Resources.
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
ms.openlocfilehash: 29d3c4fd37a219b520172c6866c5fec488c698f7
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/31/2022
ms.locfileid: "8065001"
---
# <a name="job-exempt-status"></a>Befrielsestatus för jobb


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

I detta ämne beskrivs alternativuppsättningen Befrielsestatus för jobb för Dynamics 365 Human Resources.

Fysiskt namn: cdm_jobexemptstatus

Denna uppräkning anger alternativuppsättningen för befrielsestatusvärden för FLSA-jobb. Informationen finns i den befintliga alternativuppsättningen cdm_jobexemptstatus.

| Värde | Etikett | beskrivning |
| --- | --- | --- |
| 200000000 | Momsbefrielse | Jobbet har befrielsestatus baserat på FLSA-riktlinjer. |
| 200000001 | NonExempt | Jobbet har icke-befrielsestatus baserat på FLSA-riktlinjer. |
| 200000002 | Gäller inte | FLSA-statusriktlinjer gäller inte för jobbet. |

## <a name="see-also"></a>Se även

[Introduktion av API för integrering av system för sökandespårning](hr-admin-integration-ats-api-introduction.md)<br>
[Exempelfråga för rekryteringsbegäran](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
