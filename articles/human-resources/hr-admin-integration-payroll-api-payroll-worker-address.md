---
title: Lönearbetarens adress
description: Detta ämne tillhandahåller information och en exempelfrågeställning för entiteten för lönearbetaradresser i Dynamics 365 Human Resources.
author: jcart
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2021-04-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: bf3fc5f333333b9a832ecb9c185473e476ac231d
ms.sourcegitcommit: 12e26ef25c492e5032260733b50cd642cbd6164d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/28/2021
ms.locfileid: "7559519"
---
# <a name="payroll-worker-address"></a>Lönearbetarens adress

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Detta ämne beskriver löneentiteten för medarbetaradress för Dynamics 365 Human Resources.

Fysiskt namn: mshr_payrollworkeraddressentity.

### <a name="description"></a>beskrivning

Den här entiteten tillhandahåller löneplats och lönearbete för en viss medarbetare.

## <a name="properties"></a>Egenskaper

| Egenskap</br>**Fysiskt namn**</br>**_Typ_** | Använd | Beskrivning |
| --- | --- | --- |
| **Personalnummer**</br>mshr_personnelnumber</br>*Sträng* | Skrivskydd | Medarbetarens unika personalnummer. |
| **Plats-id**</br>mshr_locationidbr>*Sträng* | Skrivskydd | Adressens ID. |
| **Bostadsadress**</br>mshr_islivedinaddressbr </br> *[alternativuppsättningen mshr_NoYes](hr-admin-integration-payroll-api-no-yes.md)* | Skrivskydd | Ett värde som anger om adressen är där medarbetaren bor. |
| **Jobbadress** </br> mshr_isworkedinaddressbr </br>*[alternativuppsättningen mshr_NoYes](hr-admin-integration-payroll-api-no-yes.md)* | Skrivskydd | Ett värde som anger om adressen är där medarbetaren arbetare. |
| **Land/region**</br>mshr_countryregionid</br>*Sträng* | Skrivskydd</br>Obligatoriskt | Land/region som angetts för adressen. |
| **Postnummer**</br>mshr_zipcode<br>*Sträng* | Skrivskydd | Det identifieringsnummer som definierats för medarbetaren. |
| **Gata**</br>mshr_street</br>*Sträng* | Skrivskydd | Den gata som angetts för adressen. |
| **Ort**</br>mshr_city</br>*Sträng* | Skrivskydd | Den ort som angetts för adressen. |
| **Delstat**</br>mshr_state</br>*Sträng* | Skrivskydd | Delstat eller provins som angetts för adressen. |
| **Län**</br>mshr_county</br>*Sträng* | Skrivskydd | Det land som angetts för adressen. |
| **Giltig från**</br>mshr_postaladdressvalidfrom</br>*Datum Tid Offset* | Skrivskydd | Det datum då adressen börjar gälla. |
| **Giltig till**</br>mshr_postaladdressvalidto</br>*Datum Tid Offset* | Skrivskydd | Det datum då adressen gäller till. |
| **Primärt fält**</br>mshr_primaryfield</br>*Sträng* | Skrivskydd | Primärt fält. |
| **ID för lönearbetarens adress**</br>mshr_payrollworkeraddressentityid</br>*GUID* | Systemgenererad | Ett systemgenererat globalt unikt ID (GUID) som identifierar adressen unikt. |

## <a name="relations"></a>Relationer

| Egenskapsvärde | Relaterad entitet | Navigeringsegenskap | Samlingstyp |
| --- | --- | --- | --- |
| _mshr_fk_worker_id_value | [mshr_payrollemployeeentity](hr-admin-integration-payroll-api-payroll-employee.md) | mshr_FK_Worker_id | mshr_FK_PayrollEmployeeEntity_Address |

## <a name="example-query"></a>Exempelfrågeställning

**Begäran**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollworkeraddressentities?$filter=mshr_personnelnumber eq @personnelnumber and mshr_postaladdressvalidfrom le @asofdate and mshr_postaladdressvalidto ge @asofdate&@personnelnumber='000041'&@asofdate=2021-04-01
```

**Svar**

```json
{
    "mshr_personnelnumber": "000041",
    "mshr_locationid": "000000538",
    "mshr_islivedinaddress": 200000001,
    "mshr_isworkedinaddress": 200000000,
    "mshr_countryregionid": "USA",
    "mshr_zipcode": "99025",
    "mshr_street": "6543 Cypress Ave",
    "mshr_city": "Tacoma",
    "mshr_state": "WA",
    "mshr_county": "KING",
    "mshr_postaladdressvalidfrom": "2012-09-20T20:14:27Z",
    "mshr_postaladdressvalidto": "2154-12-31T23:59:59Z",
    "mshr_primaryfield": "000041 | 000000538 | 9/20/2012 08:14:27 pm",
    "_mshr_fk_worker_id_value": "00000d3c-0000-0000-d5ff-004105000000",
    "mshr_payrollworkeraddressentityid": "000006f0-0000-0000-f90f-014105000000"

}
```

## <a name="see-also"></a>Se även

[Introduktion till API för löneintegrering](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
