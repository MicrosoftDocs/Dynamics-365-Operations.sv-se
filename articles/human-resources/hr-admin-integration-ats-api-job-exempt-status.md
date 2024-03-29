---
title: Befrielsestatus för jobb
description: I denna artikel beskrivs alternativuppsättningen Befrielsestatus för jobb för Dynamics 365 Human Resources.
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
ms.openlocfilehash: e59a71264d50cecce4d31dfa26ad7f05ef3f34e4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8894684"
---
# <a name="job-exempt-status"></a>Befrielsestatus för jobb


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

I denna artikel beskrivs alternativuppsättningen Befrielsestatus för jobb för Dynamics 365 Human Resources.

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
