---
title: Certifikattyp
description: I detta ämne beskrivs entiteten Certifikatstyp för Dynamics 365 Human Resources.
author: jaredha
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: fe5713b6b5f38ad7f6857b36c6b2f63a1dc0c320
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5798403"
---
# <a name="certificate-type"></a>Certifikattyp

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

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