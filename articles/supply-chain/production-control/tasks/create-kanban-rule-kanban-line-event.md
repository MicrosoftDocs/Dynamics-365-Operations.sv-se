---
title: Skapa en kanban-regel med en kanban-radhändelse
description: Den här proceduren skapar en kanban-regel genom att använda inställningen för kanban-radhändelsen för att utlösa drag från en processaktivitet.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5a6c4b7103874a6d955b21e99b8e219a039d4b55
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437390"
---
# <a name="create-a-kanban-rule-using-a-kanban-line-event"></a>Skapa en kanban-regel med en kanban-radhändelse

[!include [banner](../../includes/banner.md)]

Den här proceduren skapar en kanban-regel genom att använda inställningen för kanban-radhändelsen för att utlösa drag från en processaktivitet. Kanban-regeln utlöses av en kanban processaktivitet med en kvantitet lika med eller större än 25 vardera. Det demonstrationsdataföretag som används för att skapa den här uppgiften är USMF. Den här uppgiften är avsedd för processingenjören eller värdeströmansvarig när de förbereder tillverkningen av en ny eller ändrad produkt i en resurssnål miljö.


## <a name="create-a-kanban-rule"></a>Skapa en kanban-regel
1. Gå till Produktinformationshantering > Lean manufacturing > Kanban-regler.
2. Klicka på Ny.
3. Välj Händelse i fältet för återanskaffningsstrategi.
    * Detta skapar kanban direkt från efterfrågan. Den används för att ställa in regler som definierar ett tillverkas på beställning-scenario.  
4. Ange eller välj ett värde i fältet Första planaktivitet.
    * Ange eller välj SpeakerAssemblyAndPolish. Den första aktiviteten av en tillverkningskanban-regel är en processaktivitet i produktionsflödet. När du väljer en aktivitet, kopieras giltighetsdatum för aktiviteten till giltighetsdatum för kanban-regeln.  
5. Expandera avsnittet Detaljer.
6. Ange "L0001" i fältet Produkt.
7. Expandera avsnittet Händelser.
8. Välj "Automatisk" i fältet Kanban-radhändelse.
    * Då skapas händelse-kanbans på begäran.  Detta fällt används för att konfigurera kanban-regeln som fyller på det material som behövs för en underordnad processaktivitet. När du väljer Automatiskt, skapas händelse-kanbans med efterfrågan. Den här inställningen rekommenderas om du förväntar dig att köra produktion samma dag.  
9. Ange den minsta händelsekvantiteten till "25".
    * Händelse-kanban skapas när efterfrågekvantiteten är lika med eller fler än det här fältet. Detta är användbart om du vill producera en orderkvantitet som är mindre än det här fältet på en dator och mer än det här fältet på en annan dator.  
10. Klicka på Spara.

## <a name="create-sales-order-and-trigger-kanban-chain"></a>Skapa försäljningsorder och utlösa kanbankedjan
1. Gå till försäljning och marknadsföring > beställningar > Alla beställningar.
2. Klicka på Ny.
3. I fältet Kundkonto, ange eller välj ett värde.
    * Välj kundkontot US-003, Forest Wholesales.  
4. Klicka på OK.
5. Skriv "L0001" i fältet Artikelnummer.
    * L0001 är den artikel som du skapat för kanban-regeln.  
6. Ställ in kvantiteten på 27.
    * Eftersom 27 är högre än minimikvantiteten på 25 på kanban-regel, kommer detta att utlösa en händelse-kanban.  
7. Skriv "1" i fältet Plats.
8. Ange eller välj ett värde i fältet Lagerställe.
    * Välj lagerställe 13.  
9. Klicka på Spara.

## <a name="view-the-kanban-generated-by-the-kanban-rule"></a>Visa den kanban som genereras av kanban-regeln
1. Gå till Produktinformationshantering > Lean manufacturing > Kanban-regler.
2. Hitta och markera önskad post i listan.
3. Expandera avsnittet Kanbans.
    * Observera att en kanban för 27 skapades för att bearbeta den aktivitet som baseras på den skapade kanban-regeln.  
    * Detta är det sista steget.  

