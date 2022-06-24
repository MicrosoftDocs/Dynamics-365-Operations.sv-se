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
ms.openlocfilehash: 736bdbfb8759ab61202d1f17e3cdc8294be0ba84
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8846426"
---
# <a name="recruiting-request-position-status"></a>Befattningsstatus för rekryteringsbegäran


[!INCLUDE [PEAP](../includes/peap-1.md)]

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
