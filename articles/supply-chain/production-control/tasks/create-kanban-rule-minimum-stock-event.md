--- 
title: "Skapa en kanban-regel med en minsta lagerhändelse"
description: "Den här proceduren fokuserar på inställningarna som krävs för att skapa en kanban-regel med hjälp av en minsta lagerhändelse för att se till att en specifik produkt alltid är tillgänglig på en viss plats."
author: ChristianRytt
manager: AnnBe
ms.date: 08/24/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 0c480b518925a8536ebb77d60fcf1f1a548b097f
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-kanban-rule-using-a-minimum-stock-event"></a>Skapa en kanban-regel med en minsta lagerhändelse

[!include [task guide banner](../../includes/task-guide-banner.md)]

Den här proceduren fokuserar på inställningarna som krävs för att skapa en kanban-regel med hjälp av en minsta lagerhändelse för att se till att en specifik produkt alltid är tillgänglig på en viss plats. En kanban-regel skapas för att överföra material till platsen när lagernivån sjunker under 200 enheter. Genom att köra bearbetning av pegging-händelse skapas de nödvändiga kanbans. Det demonstrationsdataföretag som används för att skapa den här uppgiften är USMF. Den här uppgiften är avsedd för processingenjören eller värdeströmansvarig när de förbereder tillverkningen av en ny eller ändrad produkt i en resurssnål miljö.


## <a name="create-a-new-kanban-rule"></a>Skapa en ny kanban-regel
1. Gå till Produktinformationshantering > Lean manufacturing > Kanban-regler.
2. Klicka på Ny.
3. Välj "Uttag" i fältet Typ.
    * Denna typ används för att skapa överföringskanban.  
4. Välj Händelse i fältet för återanskaffningsstrategi.
    * Händelsestrategin används om du vill skapa överföringen av kanban baserat på en händelse. Senare under proceduren kommer du att utlösa överföringskanban genom att använda lageråteranskaffning.  
5. Ange eller välj ett värde i fältet Första planaktivitet.
    * Ange eller välj ReplenishSpeakerComponents. Den här överföringsaktiviteten har mottagande lagerställe (utleverans) och plats 12, vilket innebär att material ska flyttas till plats 12 på lagerställe 12.  
6. Expandera avsnittet Detaljer.
7. Ange eller välj ett värde i fältet Produkt.
    * Välj M0007.  
8. Expandera avsnittet Händelser.
9. Välj "Batch" i fältet Lagerpåfyllnadshändelse.
    * Då skapas kanban för att uppfylla materialbehoven på den relaterade platsen under bearbetning av pegging-händelse.  

## <a name="set-the-minimum-quantity-for-the-item"></a>Ange minsta kvantitet för artikeln
1. Klicka för att följa länken i fältet Produkt.
2. Klicka för att följa länken i fältet Artikelnummer.
3. Expandera faktaboxen för produktbilden.
4. Klicka på Plan i åtgärdsfönstret.
5. Klicka på Artikeldisponering.
6. Klicka på Ny.
7. Markera vald rad i listan.
8. Ange eller välj ett värde i fältet Lagerställe.
    * Ange lagerstället till 12.  
9. Ange minsta till "200".

## <a name="run-the-batch-event-creation-job"></a>Kör jobbet för att skapa batch-händelse.
1. Gå till Produktionskontroll > Periodiska uppgifter > Batchbearbetning av kanban-jobb > Bearbetning av pegging-händelse.
2. Klicka på OK.
3. Gå till Produktinformationshantering > Lean manufacturing > Kanban-regler.
4. Klicka på länken på den valda raden i listan.
    * Välj kanban-regeln som du skapade tidigare.  
5. Expandera avsnittet Kanbans.
    * Observera att en kanban skapades för att överföra det nödvändiga materialet till lagerställe 12.  


