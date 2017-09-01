--- 
title: "Lägg till en föregångare i en produktionsflödesaktivitet"
description: "I ett produktionsflödesversionen måste alla aktiviteter planeras sekventiellt."
author: cvocph
manager: AnnBe
ms.date: 10/26/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: c1afd6a5c2eb5235a42fc9aeea0c8aed6d33e0c9
ms.contentlocale: sv-se
ms.lasthandoff: 07/28/2017

---
# <a name="add-a-predecessor-to-a-production-flow-activity"></a>Lägg till en föregångare i en produktionsflödesaktivitet

[!include[task guide banner](../../includes/task-guide-banner.md)]

I ett produktionsflödesversionen måste alla aktiviteter planeras sekventiellt. En aktivitet kan ha en eller flera föregående eller efterföljande aktiviteter. 

I den här proceduren visas hur du kopplar en tidigare aktivitet till en aktivitet. 

För att utföra denna uppgift behöver du ett produktionsflöde som har utkastversionen med minst två aktiviteter som kan kopplas. 

Mer information finns i dokumentet betitlat "Production flows and activities in lean manufacturing."


## <a name="find-the-production-flow-and-version"></a>Hitta produktionsflöde och version
1. Gå till Produktionskontroll > Inställningar > Lean-produktionsflöde > Produktionsflöden.
2. Hitta och markera önskad post i listan.
3. Klicka på länken på den valda raden i listan.
4. Hitta och markera önskad post i listan.
5. Klicka på Aktiviteter.

## <a name="select-an-activity-and-add-a-predecessor"></a>Välj en aktivitet och lägg till en föregående
1. Hitta och markera önskad post i listan.
2. Klicka på Add predecessor.
3. Ange eller välj ett värde i fältet Activity.
4. Ange ett värde i fältet Grad för cykeltid.
    * Standardcykeltidsförhållande i en aktivitetsrelation är 1. Detta förutsätter att båda aktiviteterna körs i samma takt eller takttid. Om föregångaren körs med en högre hastighet (lägre takttid), bör förhållande vara lägre än 1; om föregångaren körs med en långsammare hastighet (högre takttid) är cykeltidsförhållandet större än 1.  
5. Klicka på OK.

