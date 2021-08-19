---
title: Översikt över MyLeaveRequests
description: MyLeaveRequests-entiteten i Microsoft Dynamics 365 Human Resources tillhandahåller en lista över ledighetsansökningar i systemet, omfattningen (begränsat) till de ansökningar som är tillgängliga för den aktuella användaren som frågar efter enheten.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: fefa436142fb99ed3bfb3d4454046a5d76619daecbf6f05100e8e405fca67d48
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6732115"
---
# <a name="myleaverequests-overview"></a>Översikt över MyLeaveRequests

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