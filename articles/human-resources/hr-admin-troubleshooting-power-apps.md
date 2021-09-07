---
title: Det går inte att skapa en miljö i administrationscentret för Power Apps
description: Det här avsnittet beskriver vad du gör om administratören inte kan skapa en miljö i Microsoft Power Apps-administrationscenter.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 50a5aac71ec8ed850cfad32bdb1b8d589eb2885a
ms.sourcegitcommit: 7e32e5e39e762a4b1606161cb603a450d13b5251
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/23/2021
ms.locfileid: "7413571"
---
# <a name="cant-create-an-environment-in-the-power-apps-admin-center"></a>Det går inte att skapa en miljö i administrationscentret för Power Apps

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**Utleverans**

- Administratören för klientorganisation/miljö kan inte skapa en miljö i Microsoft Power Apps Admin center.
- Användaren har ingen licens som ger rätt att skapa miljöer.

**Lösning**

Kontrollera att klientorganisationens administratör ar tilldelat en giltig Power Apps P2-licens till användaren som skapar miljön. Följande Microsoft Dynamics-serviceplaner ger behörigheter att skapa miljöer:

| Total lagerhållningsenhet för produkt (SKU)       | Power Apps P2 serviceplan  |
|------------------------------------------------|----------------------------|
| Microsoft Dynamics 365 for Operations          | Power Apps for Dynamics 365 |
| Microsoft Dynamics 365 planen Enterprise Edition | Power Apps for Dynamics 365 |

Observera att olika Microsoft Office SKU:er också ger rättigheten tillsammans med fristående Power Apps plan 2 SKU:er. Det viktiga är att en av dessa SKU:er måste finnas.

1. Gå till [https://preview.admin.powerapps.com/environments](https://preview.admin.powerapps.com/environments).
2. Skapa miljöerna genom att följa instruktionerna i [Etablera Personal](/dynamics365/unified-operations/talent/provisioning-talent).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
