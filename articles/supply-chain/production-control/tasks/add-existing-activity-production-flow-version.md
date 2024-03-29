---
title: Lägg till en befintlig aktivitet i en produktionsflödesversion
description: När du skapar nya versioner av produktionsflöden kan du välja att lägga till aktiviteter som skapats för de äldre versionerna, till den nya versionen.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LeanProductionFlow, PlanActivity, PlanActivityAddExisting, PlanActivityAddExistingLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1f73274c6e102df3007793e027587793d87c4f83
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/29/2021
ms.locfileid: "7579314"
---
# <a name="add-an-existing-activity-to-a-production-flow-version"></a>Lägg till en befintlig aktivitet i en produktionsflödesversion

[!include [banner](../../includes/banner.md)]

När du skapar nya versioner av produktionsflöden kan du välja att lägga till aktiviteter som skapats för de äldre versionerna, till den nya versionen. I den här proceduren visas hur en ny version skapas för ett befintligt produktionsflöde, utan aktiviteterna kopieras. I nästa steg läggs en befintlig aktivitet till i den nya versionen. 

Denna uppgift kräver produktionsflöde med version och aktiviteter som redan har skapats.


## <a name="create-a-new-production-flow-version"></a>Skapa en ny produktionsflödesversion
1. Gå till Produktionskontroll > Inställningar > Lean-produktionsflöde > Produktionsflöden.
2. Hitta och markera önskad post i listan.
3. Klicka på länken på den valda raden i listan.
4. Klicka på Redigera.
5. Markera vald rad i listan.
6. I fältet Utgångsdatum anger du datum och tid.
    * Observera att du, innan du skapar en ny produktionsflödesversion, måste kontrollera utgångsdatum och tid för den aktiva versionen. Den nya versionen skapas med ett effektivt startdatum som kopplas till den valda versionens utgångsdatum.  
7. Klicka på Lägg till.
8. Välj No i fältet Copy from version.
    * Välj No för att börja med en tom version om de flesta aktiviteter i den kopierade versionen ska ersättas av nya aktiviteter. Lägg till oförändrade aktiviteter i funktionen Add existing function manuellt i aktivitetsformuläret.  
9. Välj No i fältet Duplicate kanban rules.
    * När aktiviteterna inte kopieras till den nya versionen går det inte att kopiera kanban-reglerna när den nya versionen skapas.   Istället ska du använda funktionen för skapande av kanbanutbyte senare i regelformuläret för kanban, detta för att ersätta kanban-reglerna i den gamla produktionsflödesversionen med kanbanregler, detta med hjälp av aktiviteter i den nya versionen.  
10. Klicka på OK.
11. Hitta och markera önskad post i listan.

## <a name="add-an-existing-activity"></a>Lägg till en befintlig aktivitet
1. Klicka på Aktiviteter.
2. Klicka på Add existing för att öppna dialogrutan.
    * Välj en befintlig aktivitet som ska läggas till i den nya produktionsflödesversionen.  Observera att listan visas alla aktiviteter som har skapats för detta produktionsflöde för alla tidigare versioner av flödet.  
3. Ange eller välj ett värde i fältet Activity.
4. Klicka på OK.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]