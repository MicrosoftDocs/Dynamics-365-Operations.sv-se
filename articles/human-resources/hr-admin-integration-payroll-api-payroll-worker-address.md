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
ms.openlocfilehash: 3407128b0172f0e253d51bcfa23a894f981e21e2
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/18/2021
ms.locfileid: "6052299"
---
# <a name="payroll-worker-address"></a>Lönearbetarens adress

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Detta ämne tillhandahåller information och en exempelfrågeställning för entiteten för lönearbetaradresser i Dynamics 365 Human Resources.

## <a name="properties"></a>Egenskaper

| Egenskap<br>**Fysiskt namn**<br>**_Typ_** | Använd | beskrivning |
| --- | --- | --- |
| **Ort**<br>mshr_city<br>*Sträng* | Skrivskydd<br>Obligatoriskt | Den ort som angetts för adressen.   |
| **Personalnummer**<br>mshr_personnelnumber<br>*Sträng* | Skrivskydd<br>Obligatoriskt | Medarbetarens unika personalnummer.  |
| **Land/region**<br>mshr_countryregionid<br>*Sträng* | Skrivskydd<br>Obligatoriskt | Land/region som angetts för adressen  |
| **Giltig från**<br>mshr_postaladdressvalidfrom<br>*Datum Tid Offset* | Skrivskydd <br>Obligatoriskt | Det datum då adressen börjar gälla. |
| **Jobbadress**<br>mshr_isworkedinaddressbr>*Int32* | Skrivskydd<br>Obligatoriskt | Anger om adressen anger platsen där medarbetaren arbetar. |
| **Region**<br>mshr_county<br>*Sträng* | Skrivskydd<br>Obligatoriskt | Den region som angetts för adressen.  |
| **ID för lönearbetarens adress**<br>mshr_payrollworkeraddressentityid<br>*GUID* | Obligatoriskt<br>Systemgenererad | Ett systemgenererat GUID-värde som unikt identifierar adressen.  |
| **Primärt fält**<br>mshr_primaryfield<br>*Sträng* | Skrivskydd<br>Obligatoriskt |  |
| **Gata**<br>mshr_street<br>*Sträng* | Skrivskydd<br>Obligatoriskt | Den gata som angetts för adressen. |
| **Giltig till**<br>mshr_postaladdressvalidto<br>*Datum Tid Offset* | Skrivskydd <br>Obligatoriskt | Det datum då adressen slutar gälla.  |
| **Plats-id**<br>mshr_locationidbr>*Sträng* | Skrivskydd <br>Obligatoriskt | Adressens ID.  |
| **Postnummer**<br>mshr_zipcode<br>*Sträng* | Skrivskydd <br>Obligatoriskt |Det identifieringsnummer som definierats för medarbetaren.  |
| **Bostadsadress**<br>mshr_islivedinaddressbr>*Sträng* | Skrivskydd<br>Obligatoriskt | Anger om adressen anger platsen där medarbetaren bor. |
| **Delstat**<br>mshr_state<br>*Sträng* | Skrivskydd<br>Obligatoriskt | Den delstat som angetts för adressen.  |

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
