---
title: Konfigurera kommande livshändelser
description: Du kan schemalägga framtida livhändelser i Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitFutureLifeEvents, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d390bf2e9b25c50e913967ea51fcfadd4a1120b8
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/17/2021
ms.locfileid: "5464360"
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