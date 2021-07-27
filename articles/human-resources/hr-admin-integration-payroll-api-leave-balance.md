---
title: Tjänstledighetssaldo
description: Detta ämne tillhandahåller information och en exempelfrågeställning för entiteten för tjänstledighetssaldo i Dynamics 365 Human Resources.
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
ms.openlocfilehash: a16da91a7e0d63a0951804861a51bf3835829f6c
ms.sourcegitcommit: 89bb2a7f402deed32998eddc1e56e75250e3d15e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314497"
---
# <a name="leave-balance"></a>Tjänstledighetssaldo

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Detta ämne beskriver entiteten för tjänstledighetssaldo för Dynamics 365 Human Resources.

### <a name="description"></a>beskrivning

Denna entitet tillhandahåller tjänstledighetssaldot per tjänstledighetstyp för en viss medarbetare.

Fysiskt namn: mshr_essleavebalanceentities.

## <a name="properties"></a>Egenskaper

| Egenskap</br>**Fysiskt namn**</br>**_Typ_** | Använd | beskrivning |
| --- | --- | --- |
| **Personalnummer**</br>mshr_personnelnumber</br>*Sträng* | Skrivskydd | Medarbetarens unika personalnummer. |
| **Aktuellt saldo**</br>mshr_balanceavailable</br>*Decimal* | Skrivskydd | Medarbetarens aktuella balans. |
| **Typ**</br>mshr_balanceavailable</br>*Sträng* | Skrivskydd | ID för tjänstledighetstyp. |
| **Periodiseringstakt**</br>mshr_accrualratedescription</br> | Skrivskydd | Periodiseringssatsen. |
| **Senaste överföringsbelopp**</br>mshr_lastcarryforwardamount</br>*Decimal* | Skrivskydd | Belopp för senaste överföring. |
| **Uttaget detta år**</br>mshr_takenthisyear</br>*Decimal* | Skrivskydd | Mängden tjänstledighet som har tagits ut i år. |
| **Totalt i år**</br>mshr_totalthisyear</br>*Decimal* | Skrivskydd | Den totala mängden för i år. |
| **ID för dataområde**</br>mshr_dataareaid_id</br>*Sträng* | Skrivskydd | Anger den juridiska personen (företaget). |
| **Primärt fält**</br>mshr_primaryfield</br>*GUID* | Skrivskydd</br>Systemgenererad | |
| **ID för tjänstledighetstyp**</br>_mshr_fk_leavetype_id_value</br>*GUID* | Skrivskydd</br>Sekundärnyckel: mshr_essleavetypeentityid för entiteten mshr_essleavetypeentity  | Tjänstledighetstyp-ID |
| **Entiteten Tjänstledighetssaldo**</br>mshr_essleavebalanceentityid</br>*GUID* | Systemgenererad | Ett systemgenererat GUID-värde som unikt identifierar saldot. |

## <a name="example-query"></a>Exempelfrågeställning

**Begäran**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_essleavebalanceentities?$filter=mshr_personnelnumber eq '000013'
```

**Svar**

```json
{
    "mshr_personnelnumber": "000013",
    "mshr_balanceavailable": 67.76,
    "mshr_leavetypeid": "PTO",
    "mshr_accrualratedescription": "6.16 hrs / Semimonthly",
    "mshr_lastcarryforwardamount": 0,
    "mshr_takenthisyear": 0,
    "mshr_totalthisyear": 67.76,
    "mshr_dataareaid": "usmf",
    "mshr_primaryfield": "000013 | PTO",
    "_mshr_fk_leavetype_id_value": "00000a6c-0000-0000-0000-005001000000",
    "mshr_essleavebalanceentityid": "0000091f-0000-0000-2703-005001000000",
    "_mshr_dataareaid_id_value": null
},
{
    "mshr_personnelnumber": "000013",
    "mshr_balanceavailable": 80,
    "mshr_leavetypeid": "Sick",
    "mshr_accrualratedescription": "80.00 hrs / Annually",
    "mshr_lastcarryforwardamount": 0,
    "mshr_takenthisyear": 0,
    "mshr_totalthisyear": 80,
    "mshr_dataareaid": "usmf",
    "mshr_primaryfield": "000013 | Sick",
    "_mshr_fk_leavetype_id_value": "00000a6c-0000-0000-ee02-005001000000",
    "mshr_essleavebalanceentityid": "0000091f-0000-0000-3003-005001000000",
    "_mshr_dataareaid_id_value": null
},
{
    "mshr_personnelnumber": "000013",
    "mshr_balanceavailable": 0,
    "mshr_leavetypeid": "Bereavement",
    "mshr_accrualratedescription": "0.00 hrs / Annually",
    "mshr_lastcarryforwardamount": 0,
    "mshr_takenthisyear": 0,
    "mshr_totalthisyear": 0,
    "mshr_dataareaid": "usmf",
    "mshr_primaryfield": "000013 | Bereavement",
    "_mshr_fk_leavetype_id_value": "00000a6c-0000-0000-f402-005001000000",
    "mshr_essleavebalanceentityid": "0000091f-0000-0000-4403-005001000000",
    "_mshr_dataareaid_id_value": null
},
{
    "mshr_personnelnumber": "000013",
    "mshr_balanceavailable": 66.65,
    "mshr_leavetypeid": "Vacation",
    "mshr_accrualratedescription": "13.33 hrs / Monthly",
    "mshr_lastcarryforwardamount": 0,
    "mshr_takenthisyear": 0,
    "mshr_totalthisyear": 66.65,
    "mshr_dataareaid": "usmf",
    "mshr_primaryfield": "000013 | Vacation",
    "_mshr_fk_leavetype_id_value": "00000a6c-0000-0000-f502-005001000000",
    "mshr_essleavebalanceentityid": "0000091f-0000-0000-1009-005001000000",
    "_mshr_dataareaid_id_value": null
}
```

## <a name="see-also"></a>Se även

[Introduktion till API för löneintegrering](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
