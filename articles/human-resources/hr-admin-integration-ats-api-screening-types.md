---
title: Kontrolltyper
description: I denna artikel beskrivs entiteten Gallringstyper för Dynamics 365 Human Resources.
author: jaredha
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 95f4a3dce6851c7080ac665f5922e3b5877fa9f3
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8880550"
---
# <a name="screening-types"></a>Kontrolltyper


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

I denna artikel beskrivs entiteten Gallringstyper för Dynamics 365 Human Resources.

Fysiskt namn: mshr_hcmscreeningtypeentity

## <a name="description"></a>beskrivning

I den här enheten beskrivs de gallringstyper som företaget har ställt in för gallringsprocesser av medarbetare såväl före som under anställning.

## <a name="json-representation"></a>JSON-representation

```json
{
    "mshr_description": "String",
    "mshr_frequencyunit": Int,
    "mshr_generatefrom": Int,
    "mshr_frequencyinterval": Int,
    "mshr_screeningtypeid": "String",
    "mshr_hcmscreeningtypeentityid": "Guid"
}
```

## <a name="properties"></a>Egenskaper

| Egenskap<br>**Fysiskt namn**<br>**_Typ_** | Använd | beskrivning |
| --- | --- | --- |
| **Entitets-ID för gallringstyp**<br>mshr_hcmscreeningtypeentityid<br>*GUID* | Skrivskydd<br>Obligatoriskt<br>Systemgenererad | Unik, primär identifierare för posten för gallringstyp. |
| **ID för gallringstyp**<br>mshr_screeningtypeid<br>*Sträng* | Skrivskydd<br>Obligatoriskt | Användardefinierad, unik identifierare för gallringstyp. |
| **Beskrivning**<br>mshr_description<br>*Sträng* | Skrivskydd<br>Obligatoriskt | Beskrivningen av gallringstypen. |
| **Frekvensenhet**<br>mshr_frequencyunit<br>*alternativuppsättningen mshr_hcmfrequencyunit* | Skrivskydd<br>Obligatoriskt | Beskriver hur ofta gallring måste utföras för den tilldelade personen. |
| **Generera från**<br>mshr_generatefrom<br>*alternativuppsättningen mshr_hcmfrequencygeneratefrom* | Skrivskydd<br>Obligatoriskt | Om värdet Frekvens är något annat än "Endast vid en tidpunkt" avgör värdet GenerateFrom det datum från vilket nästa gallringshändelse ska beräknas. |
| **Frekvensintervall**<br>mshr_frequencyinterval<br>*Heltal* | Skrivskydd<br>Obligatoriskt | Om värdet Frekvens är något annat än "Endast vid en tidpunkt" måste du definiera ett intervall för tidsenheterna mellan varje gallringshändelse. |

## <a name="see-also"></a>Se även

[Introduktion av API för integrering av system för sökandespårning](hr-admin-integration-ats-api-introduction.md)<br>
[Exempelfråga för kandidat att anställa](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
