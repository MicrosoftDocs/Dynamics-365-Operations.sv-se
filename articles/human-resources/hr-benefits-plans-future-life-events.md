---
title: Konfigurera kommande livshändelser
description: Du kan schemalägga framtida livhändelser i Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitFutureLifeEvents
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 655070e52e3d1f43ca6904ce3218582868f193fe
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010613"
---
# <a name="configure-future-life-events"></a>Konfigurera kommande livshändelser

[!include [banner](includes/preview-feature.md)]

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
