---
title: Befattningsstatus för rekryteringsbegäran
description: Detta ämne beskriver alternativuppsättningen för Rekryteringsbegäran för Dynamics 365 Human Resources.
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
ms.openlocfilehash: dee34366289f2e7ade1a1ae24bea15c0d19683d79720a44a6327879e8060a810
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6725900"
---
# <a name="recruiting-request-position-status"></a>Befattningsstatus för rekryteringsbegäran

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Detta ämne beskriver alternativuppsättningen för Rekryteringsbegäran för Dynamics 365 Human Resources.

Fysiskt namn: mshr_hcmrecruitingrequestpositionstatus

Uppräkningen tillhandahåller alternativuppsättningen för statusvärdena för respektive befattning i en rekryteringsförfrågan i enheten RecruitingRequestPosition.

| Värde | Etikett | beskrivning |
| --- | --- | --- |
| 200000000 | Öppet | Befattningen i rekryteringsförfrågan är öppen för rekrytering. Detta innebär inte att det för tillfället inte finns någon aktiv befattningstilldelning för befattningen. Det kan finnas en medarbetare med denna befattning vid tidpunkten för rekrytering. Det anger bara att befattningen är tillgänglig för rekrytering i samband med rekryteringsförfrågan. |
| 200000001 | Tillsatt | En medarbetare har valts ut för tilldelning till befattningen. |
| 200000002 | Annullerade | Förfrågan om rekrytering för den här befattningen har annullerats. |

## <a name="see-also"></a>Se även

[Introduktion av API för integrering av system för sökandespårning](hr-admin-integration-ats-api-introduction.md)<br>
[Exempelfråga för rekryteringsbegäran](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]