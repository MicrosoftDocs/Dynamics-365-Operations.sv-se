---
title: "Det går inte att skapa en miljö i PowerApps administrationscenter"
description: "Det här avsnittet beskriver vad du gör om administratören inte kan skapa en miljö i Microsoft PowerApps administrationscenter."
author: Darinkramer
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.translationtype: HT
ms.sourcegitcommit: d3f974f94b6c327fd70b8098d24f9e1f1e1e8eeb
ms.openlocfilehash: 6f9b7ceef6895b295e6ae5a50d8ac7970497efe5
ms.contentlocale: sv-se
ms.lasthandoff: 12/04/2018

---

# <a name="cant-create-an-environment-in-the-powerapps-admin-center"></a>Det går inte att skapa en miljö i PowerApps administrationscenter

[!include [banner](includes/banner.md)]

**Utleverans**

- Administratören för klientorganisation/miljö kan inte skapa en miljö i Microsoft PowerApps administrationscenter.
- En licens som ger användaren rättigheter att utföra steget för att skapa miljö har inte tilldelats direkt till användaren som genomför detta steg.

**Lösning**

Se till att klientorganisationens administratör har tilldelats en giltig licens för PowerApps P2 direkt till den användare som ska utföra steget för att skapa miljö. Här är de Microsoft Dynamics serviceplaner som tillhandahåller denna rättighet.

| Total lagerhållningsenhet för produkt (SKU)       | PowerApps P2 serviceplan  |
|------------------------------------------------|----------------------------|
| Microsoft Dynamics 365 for Operations          | PowerApps för Dynamics 365 |
| Microsoft Dynamics 365 plan, Enterprise Edition | PowerApps för Dynamics 365 |

Observera att olika Microsoft Office SKU:er också ger rättigheten tillsammans med fristående PowerApps Plan 2 SKU:er. Det viktiga är att en av dessa SKU:er måste finnas.

1. Gå till [https://preview.admin.powerapps.com/environments](https://preview.admin.powerapps.com/environments).
2. Skapa miljöerna genom att följa instruktionerna i [Etablera Talent](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/provisioning-talent).

