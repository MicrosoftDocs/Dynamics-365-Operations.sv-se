---
title: Skapa aktivitetsrelation - Efterträdare
description: Flödet för aktiviteter i ett resurssnålt produktionsflöde dokumenteras genom aktivitetsrelationer.
author: cvocph
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanProductionFlow, PlanActivity, PlanActivityRelationNew, PlanActivityLookup, DefaultDashboard
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 07ebb7d2158964a5d8862df998fe470032a0d354
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/03/2019
ms.locfileid: "2550423"
---
# <a name="create-activity-relation---successor"></a>Skapa aktivitetsrelation - Efterträdare

[!include [task guide banner](../../includes/task-guide-banner.md)]

Flödet för aktiviteter i ett resurssnålt produktionsflöde dokumenteras genom aktivitetsrelationer. Den här inspelningen visar hur du skapar en aktivitetsrelation.

Förutsättningar:

- Ett produktionsflöde och en version i utkastläge. 

- Två aktiviteter som följer på varandra i produktionsflödet skapas, men är inte relaterade.


## <a name="find-the-production-flow-version"></a>Hitta produktionsflödesversionen 
1. Gå till Produktionskontroll > Inställningar > Lean-produktionsflöde > Produktionsflöden.
2. Hitta och markera önskad post i listan.
3. Klicka på länken på den valda raden i listan.
4. Markera vald rad i listan.
5. Välj en utkastversion i listan.
    * Aktivitetsrelationer kan läggas till både i utkastversioner och aktiva versioner av ett produktionsflöde.  

## <a name="open-the-activity-overview"></a>Öppna aktivitetsöversikten
1. Klicka på Aktiviteter.
    * Observera att formuläret visar alla aktiviteter i produktionsflödet som tilldelats versionen av de produktionsflöden som du arbetar i.  

## <a name="add-a-successor"></a>Lägg till en efterträdare
1. Klicka på Lägg till efterträdare.
2. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Aktivitet.
3. Hitta och markera önskad post i listan.
4. Klicka på länken på den valda raden i listan.
5. Markera kryssrutan Begränsning.
6. Ange ett värde i fältet Begränsningsvärde.
    * Begränsningstiden att tiden som ska schemaläggas mellan det schemalagda slutet av företrädaren (förfallodatum och tid) och den schemalagda starten av efterträdaren.  
7. Skriv ett värde i fältet Enheter.
8. Ange ett värde i fältet Grad för cykeltid.
    * Om båda verksamheterna körs i samma takt, ska cykeltidsförhållande vara 1. Om den föregående aktiviteten körs med dubbel hastighet på efterföljande ska förhållandet vara 2.   Cykeltidsförhållandena används för att beräkna de enskilda cykeltiderna för aktiviteterna i produktionsflödet.  
9. Klicka på OK.
10. Stäng sidan.
11. Klicka på fliken GridPanel.
12. Stäng sidan.
13. Uppdatera sidan.

