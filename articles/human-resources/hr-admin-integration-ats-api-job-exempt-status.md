---
title: Befrielsestatus för jobb
description: I detta ämne beskrivs alternativuppsättningen Befrielsestatus för jobb för Dynamics 365 Human Resources.
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
ms.openlocfilehash: 1f211002468384227acb2343ed6cbc6ae2a215d1
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/17/2021
ms.locfileid: "5464462"
---
# <a name="job-exempt-status"></a>Befrielsestatus för jobb

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