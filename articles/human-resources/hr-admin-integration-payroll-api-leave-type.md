---
title: Tjänstledighetstyp
description: Detta ämne tillhandahåller information och en exempelfrågeställning för entiteten för tjänstledighetstyp i Dynamics 365 Human Resources.
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
ms.openlocfilehash: 5e64b533ad7be23060701e8826a25736a078b59d1ecf824bee0e2dd05c9c78f8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6713112"
---
# <a name="leave-type"></a>Tjänstledighetstyp

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Detta ämne beskriver entiteten för tjänstledighetstyp för Dynamics 365 Human Resources.

### <a name="description"></a>beskrivning

Denna entitet innehåller information för en viss tjänstledighetsanstyp.

Fysiskt namn: mshr_essleavetypeentity.

## <a name="properties"></a>Egenskaper

| Egenskap</br>**Fysiskt namn**</br>**_Typ_** | Använd | beskrivning |
| --- | --- | --- |
| **ID för tjänstledighetstyp**</br>mshr_leavetypeid</br>*Sträng* | Skrivskydd | ID för tjänstledighetstyp. |
| **Beskrivning**</br>mshr_description</br>*Sträng* | Skrivskydd | En beskrivning av tjänstledighetstypen. |
| **Kategori**</br>mshr_category</br>*alternativuppsättningen mshr_LeaveTypeCategory* | Skrivskydd | Kategori för tjänstledighetstyp. |
| **Orsakskod krävs**</br>mshr_isreasoncoderequired</br>*alternativuppsättningen mshr_NoYes* | Skrivskydd | Definierar om en orsakskod krävs för tjänstledighetstypen. |
| **Tjänstledighetsenhet**</br>mshr_leaveamountunit</br>*alternativuppsättningen mshr_LeaveAmountUnit* | Skrivskydd | Typen av tjänstledighet. |
| **Aktivera halvdag**</br>mshr_enablehalfdaydefinition</br>*alternativuppsättningen mshr_NoYes* | Definierar om halvdag är aktiverad för tjänstledighetstypen. |
| **ID för dataområde**</br>mshr_dataareaid_id</br>*Sträng* | Skrivskydd | Anger den juridiska personen (företaget). |
| **Entitet för ledighetstyp**</br>mshr_essleavetypeentityid</br>*GUID* | Systemgenererad | Ett systemgenererat GUID-värde som unikt identifierar tjänstledighetstypen. |

## <a name="example-query"></a>Exempelfrågeställning

**Begäran**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_essleavetypeentities?$filter=mshr_leavetypeid eq 'PTO'
```

**Svar**

```json
{
    "mshr_leavetypeid": "PTO",
    "mshr_description": "Paid time off",
    "mshr_category": 200000000,
    "mshr_isreasoncoderequired": 200000000,
    "mshr_leaveamountunit": 200000000,
    "mshr_enablehalfdaydefinition": 200000000,
    "mshr_dataareaid": "usmf",
    "mshr_essleavetypeentityid": "00000a6c-0000-0000-0000-005001000000",
    "_mshr_dataareaid_id_value": null
}
```

## <a name="see-also"></a>Se även

[Introduktion till API för löneintegrering](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
