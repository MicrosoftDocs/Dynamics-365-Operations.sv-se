---
title: Åtkomst till privata adresser per säkerhetsroll
description: Denna artikel förklarar hur du löser problemet när en kund kan inte komma åt privata adresser.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 7102bbcbecec0d88351e796e2c63663d956b86f0
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8849693"
---
# <a name="access-to-private-addresses-by-security-role"></a>Åtkomst till privata adresser per säkerhetsroll


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**Utleverans**

Efter att en kund duplicerar en säkerhetsroll och loggar in som den nya rollen kan kunden inte se adresser som är märkta som privata.

**Upplösning**

För att lösa problemet måste kunden följa instruktionerna på den dubblerade säkerhetsrollen.

1. Gå till **Organisationsadministration \> Global adressbok \> Parametrar för global adressbok**.
2. På fliken **Säkerhet för privat plats** och flytta den nya rollen från listan **Tillgängliga roller** till listan **Markerade roller**.
3. Välj **Spara**.

![Sidan Parametrar för global adressbok.](media/GAD-parameters.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
