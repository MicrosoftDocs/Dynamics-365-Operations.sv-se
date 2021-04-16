---
title: Skapa aktivitetsrelation - Efterträdare
description: Flödet för aktiviteter i ett resurssnålt produktionsflöde dokumenteras genom aktivitetsrelationer.
author: cvocph
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LeanProductionFlow, PlanActivity, PlanActivityRelationNew, PlanActivityLookup, DefaultDashboard
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: e46dda12d4ad2b23ee86d240e6cdd8a1d46f1838
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5829244"
---
# <a name="create-activity-relation---successor"></a>Skapa aktivitetsrelation - Efterträdare

[!include [banner](../../includes/banner.md)]

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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]