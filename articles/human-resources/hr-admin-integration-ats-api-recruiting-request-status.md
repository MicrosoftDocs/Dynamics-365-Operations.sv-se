---
title: Status för rekryteringsförfrågan
description: Detta ämne beskriver alternativuppsättningen Rekryteringsbegäran för Dynamics 365 Human Resources.
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
ms.openlocfilehash: 888fbc511bffbecd837c929049006266191da5ba
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5806052"
---
# <a name="recruiting-request-status"></a>Status för rekryteringsförfrågan

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Detta ämne beskriver alternativuppsättningen Rekryteringsbegäran för Dynamics 365 Human Resources.

Fysiskt namn: mshr_hcmrecruitingrequeststatus

Denna uppräkning utgör alternativuppsättningen för statusvärden för RecruitingRequest.

| Värde | Etikett | beskrivning |
| --- | --- | --- |
| 200000000 | Utkast | Förfrågningen finns i utkast och är inte redo för aktiv rekrytering. |
| 200000001 | Under granskning | Denna begäran har skickats in och skickas nu runt för godkännande via arbetsflödet. Endast tillgängligt när arbetsflödet har aktiverats. |
| 200000002 | Väntar | Begäran väntar på en arbetsflödesåtgärd. Endast tillgängligt när arbetsflödet har aktiverats. |
| 200000003 | Annullerade | Denna begäran har annullerats. Endast tillgängligt när arbetsflödet har aktiverats. |
| 200000004 | Nekade | Denna begäran har avslagits. Endast tillgängligt när arbetsflödet har aktiverats. |
| 200000005 | Aktiva | Alla arbetsflöden har slutförts och godkänts, och ansökan är klar för aktiv rekrytering. |
| 200000006 | Stängda | Rekryteringsförfrågan har avslutats. |

## <a name="see-also"></a>Se även

[Introduktion av API för integrering av system för sökandespårning](hr-admin-integration-ats-api-introduction.md)<br>
[Exempelfråga för rekryteringsbegäran](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]