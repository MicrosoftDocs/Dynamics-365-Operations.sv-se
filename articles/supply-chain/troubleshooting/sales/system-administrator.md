---
title: Systemadministratörer kan inte rensa order som finns eftersom de inte är behöriga
description: Systemadministratörer kan inte rensa order som finns eftersom de inte är behöriga.
author: SmithaNataraj
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 0d0fbcc111d77ae1a362984033216f5973e2bc74f2ee95947b662ef60a13d83e
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6750916"
---
# <a name="system-administrators-cant-clear-order-holds-because-they-arent-authorized"></a>Systemadministratörer kan inte rensa order som finns eftersom de inte är behöriga

KB-nummer: 4614642

## <a name="symptoms"></a>Symtom

Systemadministratörer kan inte rensa försäljningsorder såvida de inte har den specifika roll som är tilldelad i orderkoden.

## <a name="resolution"></a>Upplösning

Åtkomsten till vissa åtgärder, till exempel att rensa försäljningsorder, styrs av inställningarna i en affärspolicy. Systemadministratörer har normalt inte rätt att utföra åtgärder av den här typen. 

Oftast styrs åtkomsten till en viss uppgift av affärspolicyn och endast vissa personer i organisationen godkänns för att utföra den uppgiften. Godkännanden kan till exempel vara resultat av arbetsflödesgodkännanden och specifika uppgifter som är resultatet av en arbetsflödeskonfiguration.

Även om inget arbetsflöde associeras med order är principen liknande. En relevant roll anger den specifika gruppen av personer i en organisation som har rätt att rensa order. Den här behörigheten bör inte nödvändigtvis beviljas till alla administratörer, eftersom den metoden bryter mot den definierade affärspolicyn.
