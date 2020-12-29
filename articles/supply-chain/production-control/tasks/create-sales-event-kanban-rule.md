---
title: Skapa en kanban-regel för försäljningshändelse
description: Den här proceduren fokuserar på inställningarna som krävs för att skapa en kanban-regel som utlöses under genereringen av försäljningsorder.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, InventItemIdLookupSimple, SalesTableListPage, SalesCreateOrder, SalesTable, LeanPeggingTree
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1759adea6db8120078e2f32bff79178545c2328a
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437381"
---
# <a name="create-a-sales-event-kanban-rule"></a>Skapa en kanban-regel för försäljningshändelse

[!include [banner](../../includes/banner.md)]

Den här proceduren fokuserar på inställningarna som krävs för att skapa en kanban-regel som utlöses under genereringen av försäljningsorder. Den händelsebaserade kanban-regeln fyller på behov som har sitt ursprung i försäljningsorderrader. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF. Proceduren är avsedd för processingenjören eller värdeströmansvarig när de förbereder tillverkningen av en ny eller ändrad produkt.




## <a name="create-a-new-kanban-rule"></a>Skapa en ny kanban-regel
1. Gå till Kanban-regler.
2. Klicka på Ny.
3. Välj Händelse i fältet för återanskaffningsstrategi.
    * Om du väljer Händelse innebär det att kanban-regeln utlösas av en händelse, till exempel genereringen av en försäljningsorderrad.   Detta gäller för områden där varje kanban ska täcka en viss efterfrågan.  
4. Ange eller välj ett värde i fältet Första planaktivitet.
    * Välj Slutmontering.  
5. Expandera avsnittet Detaljer.
6. Ange eller välj ett värde i fältet Produkt.
    * Välj L0050.  

## <a name="define-an-event"></a>Definiera en händelse
1. Expandera avsnittet Händelser.
2. Välj Automatisk i fältet Försäljningshändelse.
    * Genom att välja försäljningshändelsen Automatisk kommer denna kanban-regel att utlösas automatiskt när en försäljningsrad matchar produkt- och inleveransplatsen. I den här proceduren är det produkten L0050 på lagerställe 13.  
3. Ange den minsta händelsekvantiteten till "50".
    * Med en minsta händelsekvantitet på 50 kommer kanban-regeln endast att utlösas av händelser med en kvantitet på 50 eller mer.  
4. Expandera avsnittet Produktionsflöde.
    * Observera att inleveransplatsen är lagerställe 13. Detta innebär att den här kanban-regeln utlöses för den här platsen.  
    * I det här exemplet utlöser en försäljningsrad för produkten L0050, med en kvantitet på 50 eller mer, på lagerställe 13, den här kanban-regeln.  

## <a name="create-sales-line-to-trigger-event-kanban-rule"></a>Skapa försäljningsrader för att utlösa kanban-regel för händelse
1. Gå till Alla försäljningsorder.
    * Ett varningsmeddelande visas när kanban-regeln sparas, vilket innebär att kanbans skapas i realtid under genereringen av försäljningsorder.  
2. Klicka på Ny.
3. I fältet Kundkonto, ange eller välj ett värde.
    * Välj till exempel US-003.  
4. Klicka på OK.
5. Skriv "L0050" i fältet Artikelnummer.
6. Skriv "1" i fältet Plats.
    * Välj Plats 1 eftersom Lagerställe 13 finns på Plats 1.  
7. Ange eller välj ett värde i fältet Lagerställe.
    * Ange lagerstället till 13.  
8. Ställ in kvantiteten på 75.
    * Ange en kvantitet på 50 eller högre för att utlösa den skapade kanban-regeln.  

## <a name="verify-that-kanban-is-created"></a>Kontrollera att kanban skapas
1. Klicka på Produkt och leverans.
2. Klicka på Visa pegging-träd.
    * Lägg märke till att en kanban med samma kvantitet som försäljningsraden skapas. Du kan även se materialet som behövs för att producera L0050. Detta är det sista steget i den här proceduren.  

