---
title: Certifikattyp
description: I detta ämne beskrivs entiteten Certifikatstyp för Dynamics 365 Human Resources.
author: jaredha
manager: tfehr
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 1d2d53a628ef43d50bd83fd6b62807f44eddd653
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125723"
---
# <a name="certificate-type"></a>Certifikattyp

I detta ämne beskrivs entiteten Certifikatstyp för Dynamics 365 Human Resources.

Fysiskt namn: mshr_hcmcertificatetypeentity

## <a name="description"></a>beskrivning

Denna entitet definierar listan över yrkesintygstyper som skapas i Personal. Entiteten är inte specifik för en juridisk person (företag).

## <a name="json-representation"></a>JSON-representation

```json
{
    "mshr_certificatetype": "String",
    "mshr_description": "String",
    "mshr_requirerenewal": Int,
    "mshr_hcmcertificatetypeentityid": "Guid"
}
```

## <a name="properties"></a>Egenskaper

| Egenskap<br>**Fysiskt namn**<br>**_Typ_** | Använd | beskrivning |
| --- | --- | --- |
| **ID för typ av certifikatsentitet**<br>mshr_hcmcertificatetypeentityid<br>*GUID* | Skrivskydd<br>Obligatoriskt 
Systemgenererad | Unik,primär identifierare för certifikatstypen. |
| **Certifikatstyp**<br>mshr_certificatetype<br>*Sträng* | Skrivskydd<br>Obligatoriskt | Unik, användarläsbar identifierare för certifikatstypen. |
| **Beskrivning**<br>mshr_description<br>*Sträng* | Skrivskydd<br>Obligatoriskt | Beskrivning av certifikatstypen. |
| **Kräv förnyelse**<br>mshr_requirerenewal<br>*alternativuppsättningen mshr_noyes* | Skrivskydd<br>Valfritt | Anger om förnyelse krävs för certifikatet. |

## <a name="see-also"></a>Se även

[Introduktion av API för integrering av system för sökandespårning](hr-admin-integration-ats-api-introduction.md)<br>
[Exempelfråga för kandidat att anställa](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]