---
title: Beräkna förslag till kanban-kvantitet
description: Den här proceduren fokuserar på att optimera kanban-storleken och kvantiteterna för en specifik kanban-regel med hjälp av kanban-kvantitetsberäkningen.
author: ChristianRytt
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b6769eb1c971b4641aee7cae9dd710a856b3c8fb
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3149376"
---
# <a name="calculate-kanban-quantity-suggestions"></a>Beräkna förslag till kanban-kvantitet

[!include [banner](../../includes/banner.md)]

Den här proceduren fokuserar på att optimera kanban-storleken och kvantiteterna för en specifik kanban-regel med hjälp av kanban-kvantitetsberäkningen. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF. Den här proceduren är avsedd för den värdeströmsansvarige. Det är en förutsättning att du har slutfört proceduren Lägg till en beräkningspolicy för kanban-kvantitet till en kanban-regel.


## <a name="create-a-kanban-quantity-calculation"></a>Skapa en beräkning av kanban-kvantitet
1. Gå till Produktionskontroll > Periodiska uppgifter > Kanban-kvantitetsberäkning > Beräkna kanban-kvantitet.
2. Klicka på Ny.
3. Skriv "Speaker2016" i fältet Namn.
4. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Namn.
    * Välj den policy som du har skapat i proceduren Lägg till en beräkningspolicy för kanban-kvantitet till en kanban-regel. Till exempel Speaker2016.  
5. Klicka på länken på den valda raden i listan.
6. Ange datum och tid till "2012-12-17T08:00:00" i fältet Regel aktiv från och med datum.
    * Det här datumet används som bas för att bestämma vilka fasta kanban-regler som inkluderas i kanban-kvantitetsberäkningen.  
7. Ange datum och tid till "2012-11-17T09:00:00" i fältet Startdatum för den uppfyllda efterfrågeperioden.
    * Det datum från vilket tidigare efterfrågetransaktioner inkluderas för att beräkna kanban-kvantiteten.  
8. Ange datum och tid till "2012-12-17T07:59:59" i fältet Slutdatum för den uppfyllda efterfrågeperioden.
    * Det datum fram till vilket tidigare efterfrågetransaktioner inkluderas för att beräkna kanban-kvantiteten.  
9. Ange datum och tid till "2012-12-17T08:00:00" i fältet Startdatum för efterfrågeperioden.
    * Det datum från vilket aktuella efterfrågetransaktioner inkluderas för att beräkna kanban-kvantiteten.  
10. Ange datum och tid till "2013-01-16T07:59:59" i fältet Slutdatum för efterfrågeperioden.
    * Det datum fram till vilket aktuella efterfrågetransaktioner inkluderas för att beräkna kanban-kvantiteten.  

## <a name="generate-kanban-quantity-proposal"></a>Generera förslag på kanban-kvantitet
1. Klicka på Spara.
2. Klicka på Generera.
    * Då skapas en förslagsrad för kanban-kvantitet för kanban-regeln 000020.  

## <a name="run-kanban-quantity-calculation"></a>Kör beräkning av kanban-kvantitet
1. Klicka på Beräkna.
    * Då beräknas kanban-kvantitetsförslaget.  
2. Klicka på OK.
3. Markera vald rad i listan.
    * Observera att den föreslagna kanban-kvantiteten är 2.  

## <a name="change-product-quantity-and-calculate-again"></a>Ändra produktkvantiteten och beräkna igen
1. Ange produktkvantiteten till "5".
2. Klicka på Beräkna.
3. Klicka på OK.
    * Observera att med en kanban-kvantitet på 5 så ändras förslaget till en kanban-kvantitet på 4.  
    * Detta orsakas av att med en lägre produktkvantitet så behöver vi fler kanbans för att uppfylla efterfrågan.  

## <a name="update-kanban-rule"></a>Uppdatera kanban-regel
1. Ange datum och tid i fältet Giltighetsdatum för regel.
    * Ange ”Regel aktiv från och med datum" till ett datum i framtiden. Till exempel i dag + ett år.  
2. Klicka på Uppdatera.
3. Klicka på OK.
4. Stäng sidan.

## <a name="validate-change-on-kanban-rule"></a>Validera ändringar i kanban-regel
1. Gå till Produktinformationshantering > Lean manufacturing > Kanban-regler.
2. Klicka på länken på den valda raden i listan.
    * Välj den kanban-regel som har skapats i den föregående underuppgiften. Detta ska vara den första kanban-regeln i listan sorterad efter nummer.  
3. Växla expanderingen av avsnittet Detaljer.
    * Observera giltighetsdatumet, vilket innebär att regeln inte har aktiverats förrän detta datum.  
4. Växla expanderingen av avsnittet Kvantiteter.
    * Observera att detta är den standardkvantitet som du angett på kanban-kvantitetsberäkningen.  
    * Observera att detta är den fasta kanban-kvantiteten på 4 från den kanban-kvantitetsberäkningen.  
5. Klicka på fliken ListPanel.

