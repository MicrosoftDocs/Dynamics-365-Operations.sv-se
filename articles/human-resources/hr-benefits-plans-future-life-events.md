---
title: Konfigurera kommande livshändelser
description: Du kan schemalägga framtida livhändelser i Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitFutureLifeEvents, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 25675e7704bdb3ead2618925561d1d0dded95747e0e1d6151e6ae2d714ceac43
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6758674"
---
# <a name="configure-future-life-events"></a>Konfigurera kommande livshändelser

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