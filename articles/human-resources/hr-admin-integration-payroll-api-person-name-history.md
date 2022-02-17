---
title: Personens namnhistorik
description: Detta ämne tillhandahåller information och en exempelfrågeställning för entiteten för Personnamnshistorik i Dynamics 365 Human Resources.
author: marcelbf
ms.date: 09/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d87803b6ae0ada3ed2de6e4e7da5ffa57bf22eec
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/31/2022
ms.locfileid: "8064851"
---
# <a name="person-name-history"></a>Personens namnhistorik


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

I detta ämne beskrivs entiteten Personnamnshistorik i Dynamics 365 Human Resources.

Fysiskt namn: mshr_dirpersonnamehistoricalentity.

### <a name="description"></a>Beskrivning

Den här enheten innehåller information om namnhistorik för en viss person.

> [!IMPORTANT] 
> Fälten **FirstName**, **MiddleName**, **LastName**, **NameValidFrom** och **NameValidTo** kommer inte längre att vara tillgängliga på entiteten Lönemedarbetare. De har tagits bort för att säkerställa att endast en datumeffektiv datakälla backar denna entitet.

## <a name="properties"></a>Egenskaper

| Egenskap</br>**Fysiskt namn**</br>**_Typ_** | Använd | Beskrivning |
| --- | --- | --- |
| **Förnamn**</br>mshr_firstname</br>*Sträng* | Skrivskydd | Förnamn. |
| **Efternamnsprefix**</br>mshr_lastnameprefix</br>*Sträng* | Skrivskydd | Prefix för efternamn. |
| **Efternamn**</br>mshr_lastname</br>*Sträng* | Skrivskydd | Efternamn. |
| **Mellannamn**</br>mshr_middlename</br>*Sträng* | Skrivskydd | Mellannamn. |
| **Giltig till**</br>mshr_validto</br>*Sträng* | Skrivskydd | Det datum som namnet är giltigt för. |
| **Partnummer**</br>mshr_partynumber</br>*Sträng* | Skrivskydd | En systemgenererad unik identifierare för personen, läsbar för användaren. |
| **Primärt fält**</br>mshr_primaryfield</br>*Sträng* | Skrivskydd | Den unika identifieraren för posten. |
| **Enhets-ID för personnamnshistorik**</br>mshr_dirpersonnamehistoricalentityid</br>*GUID* | Systemgenererad | Ett systemgenererat globalt unikt ID (GUID) som identifierar posten unikt. |

## <a name="relations"></a>Relationer

| Egenskapsvärde | Relaterad entitet | Navigeringsegenskap | Samlingstyp |
| --- | --- | --- | --- |
| Inte tillämpligt | [mshr_payrollemployeeentity](hr-admin-integration-payroll-api-payroll-employee.md) | Inte tillämpligt | mshr_FK_PayrollEmployeeEntity_Name |

## <a name="example-query-for-payroll-employee"></a>Exempelfrågeställning för lönemedarbetare

**Begäran**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_dirpersonnamehistoricalentities?$filter=mshr_partynumber eq 'HR000001606'
```

**Svar**

```json
{
    "mshr_firstname": "Agustina",
    "mshr_lastnameprefix": "",
    "mshr_lastname": "Fierro",
    "mshr_middlename": "middle",
    "mshr_validto": "2021-09-10T21:23:53Z",
    "mshr_partynumber": "HR000001606",
    "mshr_primaryfield": "HR000001606 | ",
    "mshr_dirpersonnamehistoricalentityid": "00000832-0000-0000-c12b-014105000000",
    "mshr_validfrom": null
},
{
    "mshr_firstname": "Agustina",
    "mshr_lastnameprefix": "",
    "mshr_lastname": "Fierro",
    "mshr_middlename": "",
    "mshr_validto": "2154-12-31T23:59:59Z",
    "mshr_partynumber": "HR000001606",
    "mshr_primaryfield": "HR000001606 | 9/10/2021 09:23:54 pm",
    "mshr_dirpersonnamehistoricalentityid": "00000832-0000-0000-d20b-000010000000",
    "mshr_validfrom": "2021-09-10T21:23:54Z"
}
```

## <a name="see-also"></a>Se även

[Introduktion till API för löneintegrering](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
