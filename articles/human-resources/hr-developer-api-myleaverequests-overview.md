---
title: Översikt över MyLeaveRequests
description: Entiteten MyLeaveRequests i Microsoft Dynamics 365 Human Resources tillhandahåller listan över tjänstledighetsansökningar.
author: twheeloc
ms.date: 02/03/2020
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 20cc53ec3bcf38444ccf75f81e28d5efd9fc4537
ms.sourcegitcommit: 1d2eeacad11c28889681504cdc509c90e3e8ea86
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/05/2022
ms.locfileid: "8717067"
---
# <a name="myleaverequests-overview"></a>Översikt över MyLeaveRequests


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

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

[!INCLUDE[footer-include](../includes/footer-banner.md)]
