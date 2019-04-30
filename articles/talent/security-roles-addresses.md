---
title: Åtkomst till privata adresser efter säkerhetsroll
description: Det här avsnittet beskriver hur du löser problemet när en kund kan inte komma åt privata adresser.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: f8aaa33e5fda404b48548f9a57977dd0ccd53dc1
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2019
ms.locfileid: "859492"
---
# <a name="access-to-private-addresses-by-security-role"></a>Åtkomst till privata adresser efter säkerhetsroll

[!include [banner](includes/banner.md)]

**Utleverans**

Efter att en kund duplicerar en säkerhetsroll och loggar in som den nya rollen kan kunden inte se adresser som är märkta som privata.

**Upplösning**

För att lösa problemet måste kunden följa instruktionerna på den dubblerade säkerhetsrollen.

1. Gå till **Organisationsadministration \> Global adressbok \> Parametrar för global adressbok**.
2. På fliken **Säkerhet för privat plats** och flytta den nya rollen från listan **Tillgängliga roller** till listan **Markerade roller**.
3. Välj **Spara**.

![Sidan Parametrar för global adressbok](media/GAD-parameters.png)
