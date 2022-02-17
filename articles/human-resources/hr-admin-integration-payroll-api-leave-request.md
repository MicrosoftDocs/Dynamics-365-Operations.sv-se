---
title: Begäran om tjänstledighet
description: Detta ämne tillhandahåller information och en exempelfrågeställning för entiteten för tjänstledighetsansökan i Dynamics 365 Human Resources.
author: marcelbf
ms.date: 06/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-06-25
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0f14c143a59553786fe85284c128cec80905810b
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/31/2022
ms.locfileid: "8067689"
---
# <a name="leave-request"></a>Begäran om tjänstledighet


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Detta ämne beskriver entiteten för tjänstledighetsansökan för Dynamics 365 Human Resources.

### <a name="description"></a>beskrivning

Denna entitet innehåller information för en tjänstledighetsansökan.

Fysiskt namn: mshr_essleaverequestentity.

## <a name="properties"></a>Egenskaper

| Egenskap</br>**Fysiskt namn**</br>**_Typ_** | Använd | beskrivning |
| --- | --- | --- |
| **ID för begäran**</br>mshr_requestid</br>*Sträng* | Skrivskydd | ID för begäran. |
| **ID för tjänstledighetstyp**</br>mshr_leavetypeid</br>*Sträng* | Skrivskydd | ID för tjänstledighetstyp. |
| **Datum**</br>mshr_leavedate</br>*Datum Tid Offset* | Skrivskydd | Datumet för tjänstledighetsbegäran. |
| **Belopp**</br>mshr_amount</br>*Decimal* | Skrivskydd | Nivå för tjänstledighetsansökan. |
| **Halvdagstyp**</br>mshr_halfdaydefinition</br>*Alternativuppsättningen mshr_LeaveHalfDayDefinition* | Skrivskydd | Halvdagsledighetstyp. |
| **Kommentar**</br>mshr_comment</br>*Sträng* | Skrivskydd | Kommentar för begäran. |
| **Status**</br>mshr_status</br>*Alternativuppsättningen mshr_status* | Skrivskydd | Status för begäran. |
| **Datum**</br>mshr_requestdate</br>*Datum Tid Offset* | Skrivskydd | Datumet för begäran. |
| **Personalnummer**</br>mshr_personnelnumber</br>*Sträng* | Skrivskydd | Medarbetarens unika personalnummer. |
| **ID för orsakskod**</br>mshr_reasoncodeid</br>*Sträng* | Skrivskydd | ID för orsakskod. |
| **ID för dataområde**</br>mshr_dataareaid</br>*Sträng* | Skrivskydd | Anger den juridiska personen (företaget). |
| **Primärt fält**</br>mshr_primaryfield</br>*GUID* | Skrivskydd</br>Systemgenererad | |
| **Entitet för tjänstledighetstyp**</br>mshr_essleaverequestentityid</br>*GUID* | Systemgenererad | Ett systemgenererat GUID-värde som unikt identifierar tjänstledighetsbegäran. |

## <a name="example-query"></a>Exempelfrågeställning

**Begäran**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_essleaverequestentities?$filter=mshr_personnelnumber eq '000020'
```

**Svar**

```json
{
    "mshr_requestid": "USMF-000001",
    "mshr_leavetype": "PTO",
    "mshr_leavedate": "2017-01-02T00:00:00Z",
    "mshr_amount": 8,
    "mshr_halfdaydefinition": 200000000,
    "mshr_comment": "Taking a week off to relax",
    "mshr_status": 200000009,
    "mshr_requestdate": "2017-07-31T00:00:00Z",
    "mshr_personnelnumber": "000020",
    "mshr_reasoncodeid": "",
    "mshr_dataareaid": "usmf",
    "mshr_primaryfield": "USMF-000001 | PTO | 1/2/2017",
    "mshr_essleaverequestentityid": "000004dd-0000-0000-0f00-005001000000",
    "_mshr_dataareaid_id_value": null
}
```

## <a name="see-also"></a>Se även

[Introduktion till API för löneintegrering](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
