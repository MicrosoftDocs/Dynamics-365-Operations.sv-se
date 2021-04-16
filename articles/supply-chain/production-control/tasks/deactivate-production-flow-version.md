---
title: Inaktivera en produktionsflödesversion
description: När en aktiv produktionsflödesversion är inte längre behövs kan den inaktiveras.
author: cvocph
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LeanProductionFlow
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e47cb950ce488d8b6170f829e1fedc664b921a1a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5811568"
---
# <a name="deactivate-a-production-flow-version"></a>Inaktivera en produktionsflödesversion

[!include [banner](../../includes/banner.md)]

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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]