---
title: Åtkomst till privata adresser per säkerhetsroll
description: Det här avsnittet beskriver hur du löser problemet när en kund kan inte komma åt privata adresser.
author: andreabichsel
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8daee1b645836e96a4bf3057cb317d5409d4583a
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5803931"
---
# <a name="access-to-private-addresses-by-security-role"></a>Åtkomst till privata adresser efter säkerhetsroll

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**Utleverans**

Efter att en kund duplicerar en säkerhetsroll och loggar in som den nya rollen kan kunden inte se adresser som är märkta som privata.

**Upplösning**

För att lösa problemet måste kunden följa instruktionerna på den dubblerade säkerhetsrollen.

1. Gå till **Organisationsadministration \> Global adressbok \> Parametrar för global adressbok**.
2. På fliken **Säkerhet för privat plats** och flytta den nya rollen från listan **Tillgängliga roller** till listan **Markerade roller**.
3. Välj **Spara**.

![Sidan Parametrar för global adressbok](media/GAD-parameters.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]