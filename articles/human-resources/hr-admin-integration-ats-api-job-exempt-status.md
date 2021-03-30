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
ms.openlocfilehash: 0cd6ffc01793c8ff12e36175c7c9feaf8a4b3cdf
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125579"
---
# <a name="job-exempt-status"></a>Befrielsestatus för jobb

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