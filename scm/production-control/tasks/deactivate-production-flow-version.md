--- 
title: "Inaktivera en produktionsflödesversion"
description: "När en aktiv produktionsflödesversion är inte längre behövs kan den inaktiveras."
author: cvocph
manager: AnnBe
ms.date: 10/07/2016
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
ms.openlocfilehash: 06daa5e7d2b8e88bca281dc9bcaa73927253553c
ms.contentlocale: sv-se
ms.lasthandoff: 07/28/2017

---
# <a name="deactivate-a-production-flow-version"></a>Inaktivera en produktionsflödesversion

[!include[task guide banner](../../includes/task-guide-banner.md)]

När en aktiv produktionsflödesversion är inte längre behövs kan den inaktiveras. Du bör bara använda detta alternativ om alla kanban-regler och -aktiviteter har avslutat och inte ska aktiveras igen. Observera att utgångsdatum för alla kanbanregler relaterade till denna produktionsflödesversion uppdateras med det aktuella datumet och tiden. 

Överväg att ange ett utgångsdatum för den aktiva versionen och skapa en ny version, du vill ändra en aktiv produktionsflödesversion. Detta gör att du fortsätta din produktionsverksamhet samtidigt som du förbereder den nya versionen och relaterade kanban-regler. 

För att låta en aktiv produktionsflödesversion upphöra måste du ange ett utgångsdatum. På så sätt är inaktivering mer som ett undantag än en regel. 

För den här proceduren behöver du ett produktionsflöde med en version som kan inaktiveras. Försök inte detta i en produktionsmiljö om du inte är 100 % säker på att versionen är helt föråldrad.


## <a name="deactivate-a-production-flow-version"></a>Inaktivera en produktionsflödesversion
1. Gå till Produktionskontroll > Inställningar > Lean-produktionsflöde > Produktionsflöden.
2. Hitta och markera önskad post i listan.
3. Klicka på länken på den valda raden i listan.
4. Hitta och markera önskad post i listan.
5. Klicka på Deactivate.
    * Fortsätt inte om du inte är 100 % säker på att denna produktionsflödesversion är föråldrad. Om du klickar på Ok kommer alla aktiva kanban-regler att hävas och omedelbart stoppa alla produktions- och lagerpåfyllnadsaktiviteter för denna produktionsflödesversion.  
6. Klicka på OK.

