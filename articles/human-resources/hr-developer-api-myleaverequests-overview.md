---
title: Översikt över MyLeaveRequests
description: MyLeaveRequests-entiteten i Microsoft Dynamics 365 Human Resources tillhandahåller en lista över ledighetsansökningar i systemet, omfattningen (begränsat) till de ansökningar som är tillgängliga för den aktuella användaren som frågar efter enheten.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0ca5bc225400338e76faee41a279e91fc00ce570
ms.sourcegitcommit: 18e626c49ccfdb12c1484b985e3a275e51f61320
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/04/2021
ms.locfileid: "5115546"
---
# <a name="myleaverequests-overview"></a>Översikt över MyLeaveRequests

MyLeaveRequests-entiteten i Microsoft Dynamics 365 Human Resources tillhandahåller en lista över ledighetsansökningar i systemet, omfattningen (begränsat) till de ansökningar som är tillgängliga för den aktuella användaren som frågar efter enheten.

## <a name="key"></a>Nyckelord

  | Egenskapsnamn | Datatyp |
  |---------------|-----------|
  | dataAreaId    | Sträng    |
  | RequestId     | Sträng    |
  | LeaveType     | Sträng    |
  | LeaveDate     | Datum      |
  
## <a name="properties"></a>Egenskaper

  | Egenskapsnamn     | Datatyp | Obligatoriskt |
  |-------------------|-----------|----------|
  | dataAreaId        | Sträng    | X        |
  | RequestId         | Sträng    | X        |
  | LeaveType         | Sträng    | X        |
  | LeaveDate         | Datum      | X        |
  | ReasonCodeId      | Sträng    |          |
  | PersonnelNumber   | Sträng    | X        |
  | RequestDate       | Datum      | X        |
  | Kommentar           | Sträng    |          |
  | Status            | Fasttexttyp      | X        |
  | Tid            | Realtal      |          |
  | HalfDayDefinition | Fasttexttyp      |          |

## <a name="actions"></a>Åtgärder

 | Namn på åtgärd                               | Beskrivning                                     |
 |-------------------------------------------|-------------------------------------------------|
 | [skicka](hr-developer-api-myleaverequests-submit.md)   | Skicka begäran som ska bearbetas av arbetsflödet. |

## <a name="see-also"></a>Se även

- [Skicka en ledighetsansökan till arbetsflödet](hr-developer-api-myleaverequests-submit.md)
- [Autentisering](hr-developer-api-authentication.md)