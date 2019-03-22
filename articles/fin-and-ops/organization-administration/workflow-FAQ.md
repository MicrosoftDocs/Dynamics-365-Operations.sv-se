---
title: Vanliga frågor om arbetsflöde
description: Detta avsnitt besvarar några vanliga frågor om arbetsflödessystemet i Microsoft Dynamics 365 for Finance and Operations.
author: ChrisGarty
manager: AnnBe
ms.date: 02/28/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f058a450eb18e688efbc5306a42b4efef6aa91e7
ms.sourcegitcommit: 9a723737565ac78c884e40f7129d0f5aad747524
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/01/2019
ms.locfileid: "773233"
---
# <a name="workflow-system"></a>Arbetsflödessystem

[!include [banner](../includes/banner.md)]

Detta avsnitt besvarar några vanliga frågor om arbetsflödessystemet i Microsoft Dynamics 365 for Finance and Operations.

## <a name="notifications"></a>Meddelanden

### <a name="why-are-multiple-notifications-received-when-a-work-item-is-rejected"></a>Varför tas flera meddelanden emot när en arbetsuppgift avvisas?
När en arbetsuppgift har avvisats kommer detta arbetsobjekt slutföras som avvisat. En annan arbetsuppgift skapas och tilldelas till upphovsmannen. Detta innebär att det finns ett meddelande till upphovsmannen för den avvisade arbetsuppgiften och ett separat meddelande till användaren som är tilldelad till den nya ”ändringsbegärda” arbetsuppgiften. 

Varje meddelande är för en olika arbetsuppgift, men likheten kan vara förvirrande. Vi undersöker sätt att förbättra detta i framtida versioner.
