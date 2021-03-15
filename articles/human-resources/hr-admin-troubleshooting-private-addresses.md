---
title: Åtkomst till privata adresser per säkerhetsroll
description: Det här avsnittet beskriver hur du löser problemet när en kund kan inte komma åt privata adresser.
author: andreabichsel
manager: tfehr
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
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
ms.openlocfilehash: 6598094e7877a30c35e1b03794f82c8a4ec001a7
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2021
ms.locfileid: "5114269"
---
# <a name="access-to-private-addresses-by-security-role"></a>Åtkomst till privata adresser efter säkerhetsroll

**Utleverans**

Efter att en kund duplicerar en säkerhetsroll och loggar in som den nya rollen kan kunden inte se adresser som är märkta som privata.

**Upplösning**

För att lösa problemet måste kunden följa instruktionerna på den dubblerade säkerhetsrollen.

1. Gå till **Organisationsadministration \> Global adressbok \> Parametrar för global adressbok**.
2. På fliken **Säkerhet för privat plats** och flytta den nya rollen från listan **Tillgängliga roller** till listan **Markerade roller**.
3. Välj **Spara**.

![Sidan Parametrar för global adressbok](media/GAD-parameters.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]