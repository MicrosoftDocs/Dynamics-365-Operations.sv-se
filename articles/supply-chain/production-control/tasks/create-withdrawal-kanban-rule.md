--- 
title: "Skapa en kanban-regel för uttag"
description: "I den här proceduren visas de inställningar som behövs om du vill skapa en kanban-regel för uttag för överföring av material i en resurssnål miljö."
author: ChristianRytt
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, InventItemIdLookupSimple, UnitOfMeasureLookup, KanbanCreate
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 02c7133d2e02b27fb428874deeda21e2bab28fb6
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-withdrawal-kanban-rule"></a>Skapa en kanban-regel för uttag

[!include [task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren visas de inställningar som behövs om du vill skapa en kanban-regel för uttag för överföring av material i en resurssnål miljö. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF. Den här proceduren är avsedd för processingenjören eller värdeströmansvarig när de förbereder lagerpåfyllnaden av ett nytt eller ändrat material.


## <a name="create-new-kanban-rule"></a>Skapa en ny kanban-regel
1. Gå till Kanban-regler.
2. Klicka på Ny.
3. Välj "Uttag" i fältet Typ.
    * Uttagstypen används för kanban-regler för att överföra material och gods.  
4. Ange eller välj ett värde i fältet Första planaktivitet.
    * Välj ReplenishSpeakerComponents.   Denna aktivitet ställs in för att flytta komponenter från lagerställe 11, plats 11 till lagerställe 12 och plats 12.  
5. Ange eller välj ett värde i fältet Produkt.
    * Välj M0007.  
6. Ange ett värde i fältet Produktionstid.
    * Exempelvis 60.  
7. Ange eller välj ett värde i fältet Måttenhet.
    * T.ex. minuter.  

## <a name="set-quantities-for-kanban"></a>Ange kvantiteter för kanban
1. Ange standardkvantiteten till "5".
    * Detta är kvantiteten som ska överföras för varje kanban.  
2. Ange "2" i fältet Fast kanban-kvantitet.
    * Detta är antalet kanban som ska vara aktiva. I det här fallet överför 2 kanbans 5 var.  
3. Ange "1" i fältet Notifieringsgränsminimum.
    * Används för att hålla reda på den minsta mängd fullständiga kanbans som ska finnas på destinationen. Detta används till exempel i översikten över kanban-kvantitet.  
4. Ange "2" i fältet Notifieringsgränsmaximum.
    * Används för att hålla reda på den största mängd fullständiga kanbans som ska finnas på destinationen. Detta används till exempel i översikten över kanban-kvantitet.  

## <a name="create-kanbans"></a>Skapa kanban
1. Klicka på Spara.
    * Kanban-regeln måste sparas innan kanbans kan skapas.  
2. Klicka på Lägg till.
    * Observera att det inte finns några aktiva kanbans. Därför är det föreslagna antalet nya kanbans 2. Detta är lika med ”den fasta kanban-kvantiteten”.  
3. Klicka på Skapa.
    * Detta skapar 2 kanbans.  
    * Observera att 2 kanbans, för 5 vardera, skapades för den här kanban-regeln för uttag.  Detta är det sista steget i den här proceduren.  


