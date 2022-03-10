---
title: Lönemedarbetare
description: Detta ämne tillhandahåller information och en exempelfrågeställning för entiteten för lönearbetare i Dynamics 365 Human Resources.
author: jcart
ms.date: 08/25/2021
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
ms.openlocfilehash: e853a8a5730d397f253c8ce3a330794594dfd907
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/31/2022
ms.locfileid: "8068494"
---
# <a name="payroll-employee"></a>Lönemedarbetare


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Detta ämne beskriver löneentiteten för medarbetare för Dynamics 365 Human Resources.

Fysiskt namn: mshr_payrollemployeeentity.

### <a name="description"></a>beskrivning

Denna entitet ger information om medarbetaren. Du måste ställa in [löneintegreringsparametrarna](hr-admin-integration-payroll-api-parameters.md) innan du använder den här entiteten.

>[!IMPORTANT] 
>Fälten **FirstName**, **MiddleName**, **LastName**, **NameValidFrom** och **NameValidTo** kommer inte längre att vara tillgängliga på den här enheten. På så sätt ser du till att det bara finns en datakälla med giltighetsdatum som backar den här enheten.
>Dessa fält kommer att vara tillgängliga på **DirPersonNameHistoricalEntity**, som släpptes i Plattformsuppdatering 43. Det finns en OData-relation från **PayrollEmployeeEntity** till **DirPersonNameHistoricalEntity**. 

## <a name="properties"></a>Egenskaper

| Egenskap</br>**Fysiskt namn**</br>**_Typ_** | Använd | beskrivning |
| --- | --- | --- |
| **ID för juridisk person**</br>mshr_legalentityid</br>*Sträng* | Skrivskydd | Anger den juridiska personen (företaget). |
| **Personalnummer**</br>mshr_personnelnumber</br>*Sträng* | Skrivskydd | Medarbetarens unika personalnummer. |
| **Startdatum för anställning**</br>mshr_employmentstartdate</br>*Datum Tid Offset* | Skrivskydd | Startdatumet för medarbetarens anställning. |
| **Slutdatum för anställning**</br>mshr_employmentenddate</br>*Datum Tid Offset* | Skrivskydd |Slutet på medarbetarens anställning.  |
| **Födelsedatum**</br>mshr_birthdate</br>*Datum Tid Offset* | Skrivskydd | Medarbetarens födelsedatum. |
| **Kön**</br>mshr_gender</br>[alternativuppsättningen mshr_hcmpersongender](hr-admin-integration-payroll-api-gender.md) | Skrivskydd | Medarbetarens kön. |
| **Anställningstyp**</br>mshr_employmenttype</br>[Alternativuppsättningen mshr_hcmemploymenttype](hr-admin-integration-payroll-api-hcmemploymenttype.md) | Skrivskydd | Anställningstyp. |
| **ID för identifieringstyp**</br>mshr_identificationtypeid</br>*Sträng* |Skrivskydd | Identifieringstypen som definierats för medarbetaren. |
| **ID-nummer till**</br>mshr_identificationnumber</br>*Sträng* | Skrivskydd |Det identifieringsnummer som definierats för medarbetaren. |
| **Klar att betalas**</br>mshr_readytopay</br>[alternativuppsättningen mshr_noyes](hr-admin-integration-payroll-api-no-yes.md) | Skrivskydd | Anger om medarbetaren är markerad som redo att betala. |
| **Entitets-ID för lönemedarbetare**</br>mshr_payrollemployeeentityid</br>*GUID* | Systemgenererad | Ett systemgenererat globalt unikt ID (GUID) som identifierar medarbetaren unikt. |

## <a name="relations"></a>Relationer

|Egenskapsvärde | Relaterad entitet | Navigeringsegenskap | Samlingstyp |
| --- | --- | --- | --- |
| _mshr_fk_employment_id_value | mshr_hcmemploymentdetailentity | mshr_FK_Employment_id | mshr_FK_HcmEmploymentDetailEntity_PayrollEmployee |
| _mshr_fk_fixedcompplan_id_value | [mshr_payrollfixedcompensationplanentity](hr-admin-integration-payroll-api-payroll-fixed-compensation-plan.md) | mshr_FK_FixedCompPlan_id | mshr_FK_PayrollFixedCompensationPlanEntity_Employee |
| _mshr_fk_name_id_value | mshr_dirpersonnamehistoricalentity | mshr_FK_Name_id | - |
| _mshr_fk_worker_id_value | mshr_hcmworkerbaseentity | mshr_FK_Worker_id | mshr_FK_HcmWorkerBaseEntity_PayrollEmployee |
| _mshr_fk_workerbankaccount_id_value | mshr_hcmworkerbankaccountentity | mshr_FK_WorkerBankAccount_id | mshr_FK_HcmWorkerBankAccountEntity_PayrollEmployee |
| _mshr_fk_variablecompaward_id_value | [mshr_payrollvariablecompensationawardentity](hr-admin-integration-payroll-api-payroll-variable-compensation-plan.md) | mshr_FK_VariableCompAward_id | mshr_FK_PayrollVariableCompensationAwardEntity_Employee |
| _mshr_fk_address_id_value | [mshr_payrollworkeraddressentity](hr-admin-integration-payroll-api-payroll-worker-address.md) | mshr_FK_Address_id | mshr_FK_PayrollWorkerAddressEntity_Worker |

## <a name="example-query-for-payroll-employee"></a>Exempelfrågeställning för lönemedarbetare

**Begäran**

```http
GET [Organizaton URI]/api/data/v9.1/mshr_payrollemployeeentities?$filter=mshr_personnelnumber eq '000041'
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
    "mshr_employmenttype": 200000000,
    "mshr_identificationtypeid": "SSN",
    "mshr_identificationnumber": "888-99-9342",
    "mshr_readytopay": 200000000,
    "mshr_dataareaid": "USMF",
    "mshr_primaryfield": "000041 | USMF | 4/5/2011 07:00:00 am",
    "_mshr_fk_employment_id_value": "00000d4e-0000-0000-0600-014105000000",
    "_mshr_fk_fixedcompplan_id_value": "00000598-0000-0000-4cd0-fda002000000",
    "_mshr_fk_name_id_value": "00000832-0000-0000-d700-014105000000",
    "_mshr_fk_worker_id_value": "000000af-0000-0000-d5ff-004105000000",
    "_mshr_fk_workerbankaccount_id_value": "000006f2-0000-0000-b7ff-004105000000",
    "mshr_payrollemployeeentityid": "00000666-0000-0000-d5ff-004105000000",
    "_mshr_fk_address_id_value": null,
    "_mshr_fk_variablecompaward_id_value": null,
    "_mshr_dataareaid_id_value": null
}
```

## <a name="see-also"></a>Se även

[Introduktion till API för löneintegrering](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
