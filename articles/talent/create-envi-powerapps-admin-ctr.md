---
title: Det går inte att skapa en miljö i administrationscentret för Power Apps
description: Det här avsnittet beskriver vad du gör om administratören inte kan skapa en miljö i Microsoft Power Apps-administrationscenter.
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
ms.openlocfilehash: 7a66b7624655aaf976aaa63b2626f65c54d0ea38
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/06/2019
ms.locfileid: "2898833"
---
# <a name="cant-create-an-environment-in-the-power-apps-admin-center"></a>Det går inte att skapa en miljö i administrationscentret för Power Apps

**Utleverans**

- Administratören för klientorganisation/miljö kan inte skapa en miljö i Microsoft Power Apps Admin center.
- En licens som ger användaren rättigheter att utföra steget för att skapa miljö har inte tilldelats direkt till användaren som genomför detta steg.

**Lösning**

Se till att klientorganisationens administratör har tilldelats en giltig licens för Power Apps P2 direkt till den användare som ska utföra steget för att skapa miljö. Här är de Microsoft Dynamics serviceplaner som tillhandahåller denna rättighet.

| Total lagerhållningsenhet för produkt (SKU)       | Power Apps P2 serviceplan  |
|------------------------------------------------|----------------------------|
| Microsoft Dynamics 365 for Operations          | Power Apps for Dynamics 365 |
| Microsoft Dynamics 365 planen Enterprise Edition | Power Apps for Dynamics 365 |

Observera att olika Microsoft Office SKU:er också ger rättigheten tillsammans med fristående Power Apps plan 2 SKU:er. Det viktiga är att en av dessa SKU:er måste finnas.

1. Gå till [https://preview.admin.powerapps.com/environments](https://preview.admin.powerapps.com/environments).
2. Skapa miljöerna genom att följa instruktionerna i [Etablera Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).
