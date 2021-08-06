---
title: Lönemedarbetare
description: Detta ämne tillhandahåller information och en exempelfrågeställning för entiteten för lönearbetare i Dynamics 365 Human Resources.
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
ms.openlocfilehash: 672db002ddf8d12aaab5b97241390c036ad7ab5c
ms.sourcegitcommit: 8fb79920bea14746a71551a4456236a6386bfcea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/12/2021
ms.locfileid: "6538864"
---
# <a name="payroll-employee"></a>Lönemedarbetare

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Detta ämne beskriver löneentiteten för medarbetare för Dynamics 365 Human Resources.

Fysiskt namn: mshr_payrollemployeeentity.

### <a name="description"></a>beskrivning

Denna entitet ger information om medarbetaren. Du måste ställa in [löneintegreringsparametrarna](hr-admin-integration-payroll-api-parameters.md) innan du använder den här entiteten.

>[!IMPORTANT] 
>Fälten **FirstName**, **MiddleName**, **LastName**, **NameValidFrom** och **NameValidTo** kommer inte längre att vara tillgängliga på den här enheten. På så sätt säkerställer du att det bara finns ett enda datum för datakällan som backar upp enheten, det vill säga **HcmEmployment** med fälten **EmploymentStartDate** och **EmploymentEndDate**.

>Dessa fält kommer att vara tillgängliga på **DirPersonNameHistoricalEntity**, som släpptes i Plattformsuppdatering 43. Det finns en OData-relation från **PayrollEmployeeEntity** till **DirPersonNameHistoricalEntity** på fältet **Person**. Alternativt kan enheten **DirPersonNameHistoricalEntity** enhet kan frågas direkt via OData med det offentliga namnet, **PersonHistoricalNames**.


## <a name="properties"></a>Egenskaper

| Egenskap<br>**Fysiskt namn**<br>**_Typ_** | Använd | beskrivning |
| --- | --- | --- |
| **Personalnummer**<br>mshr_personnelnumber<br>*Sträng* | Skrivskydd<br>Obligatoriskt | Medarbetarens unika personalnummer. |
| **Primärt fält**<br>mshr_primaryfield<br>*Sträng* | Obligatoriskt<br>Systemgenererad |  |
| **ID för juridisk person**<br>mshr_legalentityID<br>*Sträng* | Skrivskydd<br>Obligatoriskt | Anger den juridiska personen (företaget). |
| **Kön**<br>mshr_gender<br>[alternativuppsättningen mshr_hcmpersongender](hr-admin-integration-payroll-api-gender.md) | Skrivskydd<br>Obligatoriskt | Medarbetarens kön. |
| **Entitets-ID för lönemedarbetare**<br>mshr_payrollemployeeentityid<br>*GUID* | Obligatoriskt<br>Systemgenererad | Ett systemgenererat GUID-värde som unikt identifierar medarbetaren. |
| **Startdatum för anställning**<br>mshr_employmentstartdate<br>*Datum Tid Offset* | Skrivskydd<br>Obligatoriskt | Startdatumet för medarbetarens anställning. |
| **ID för identifieringstyp**<br>mshr_identificationtypeid<br>*Sträng* |Skrivskydd<br>Obligatoriskt | Identifieringstypen som definierats för medarbetaren. |
| **Slutdatum för anställning**<br>mshr_employmentenddate<br>*Datum Tid Offset* | Skrivskydd<br>Obligatoriskt |Slutet på medarbetarens anställning.  |
| **ID för dataområde**<br>mshr_dataareaid_id<br>*GUID* | Obligatoriskt <br>Systemgenererad | Systemgenererat GUID-värde som identifierar den juridiska personen (företaget). |
| **Giltig till**<br>mshr_namevalidto<br>*Datum Tid Offset* |  Skrivskydd<br>Obligatoriskt | Det datum då medarbetarinformationen slutar gälla. |
| **Födelsedatum**<br>mshr_birthdate<br>*Datum Tid Offset* | Skrivskydd <br>Obligatoriskt | Medarbetarens födelsedatum |
| **ID-nummer till**<br>mshr_identificationnumber<br>*Sträng* | Skrivskydd <br>Obligatoriskt |Det identifieringsnummer som definierats för medarbetaren.  |

## <a name="example-query-for-payroll-employee"></a>Exempelfrågeställning för lönemedarbetare

**Begäran**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollemployeeentities?$filter=mshr_personnelnumber eq @personnelnumber and mshr_identificationtypeid eq @idtype and mshr_namevalidfrom le @asofdate and mshr_namevalidto ge @asofdate&@personnelnumber='000041'&@idtype='SSN'&@asofdate=2021-04-01
```

**Svar**

```json
{
    "mshr_legalentityid": "USMF",
    "mshr_personnelnumber": "000041",
    "mshr_employmentstartdate": "2011-04-05T07:00:00Z",
    "mshr_employmentenddate": "2154-12-31T23:59:59Z",
    "mshr_birthdate": "1987-09-12T00:00:00Z",
    "mshr_gender": 200000002,
    "mshr_identificationtypeid": "SSN",
    "mshr_identificationnumber": "888-99-9342",
    "mshr_dataareaid": "USMF",
    "mshr_primaryfield": "000041 | USMF | 4/5/2011 07:00:00 am",
    "_mshr_fk_worker_id_value": "000000ad-0000-0000-d5ff-004105000000",
    "_mshr_fk_employment_id_value": "00000d0d-0000-0000-0600-014105000000",
    "_mshr_fk_fixedcompplan_id_value": "0000029f-0000-0000-d5ff-004105000000",
    "mshr_payrollemployeeentityid": "00000d3c-0000-0000-d5ff-004105000000",
    "_mshr_dataareaid_id_value": null
}
```
## <a name="see-also"></a>Se även

[Introduktion till API för löneintegrering](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
