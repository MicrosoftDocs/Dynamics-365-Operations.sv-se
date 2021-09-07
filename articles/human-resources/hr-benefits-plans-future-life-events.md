---
title: Konfigurera framtida livshändelser
description: Detta ämne förklarar hur du tidsplanerar framtida händelser i Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitFutureLifeEvents, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: aa772f5c58e199e8786185c783db7016c8aebafd
ms.sourcegitcommit: 4f9c889e5cf72f34dd9746a322f8c0d6b983037b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/25/2021
ms.locfileid: "7417592"
---
# <a name="configure-future-life-events"></a>Konfigurera framtida livshändelser

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Du kan schemalägga framtida livhändelser i Dynamics 365 Human Resources.

1. I arbetsytan **Förmånshantering** under **inställningar**, välj **Framtida livshändelser**.

2. Välj **Ny**.

3. Ange värden för de följande fälten:

   | Fält | Beskrivning |
   | --- | --- |
   | Datum för livshändelse | Systemet bearbetar alla händelser under anmälningsperioden som inträffar fram till detta datum. |
   | Lifehändelse har loggats | Datum och den tid då livshändelsen loggades. |
   | Loggtyp | Visar om åtgärden är något av följande:</br></br>- **Uppdatera** – en ändring i en befintlig post som följer upp livhändelser</br></br>- **Infoga** – skapandet av en ny tjänstehändelsepost |
   | ID för livshändelsetyp | Unik identifierare för livshändelsen. |
   | Livshändelsetyp | En katalysator för att uppdatera en medarbetares förmånsanmälan. Mer information finns i avsnittet om utlösare för livscykelhändelser. |
   | Status | Anger om livshändelsen har bearbetats eller inte. |
   | Rad | Radnumret för den framtida livshändelsen. |

4. Välj **Spara**. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
