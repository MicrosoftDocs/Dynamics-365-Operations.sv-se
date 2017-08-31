--- 
title: "Skapa och bearbeta en överensstämmelse"
description: "Använd den här proceduren för att utföra avvikelsehantering baserat på en befintlig kvalitetsorder."
author: perlynne
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: 4082caf2cc8393345d4f79a991f2cf205b06b142
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---
# <a name="create-and-process-a-conformance"></a>Skapa och bearbeta en överensstämmelse

[!include[task guide banner](../../includes/task-guide-banner.md)]

Använd den här proceduren för att utföra avvikelsehantering baserat på en befintlig kvalitetsorder. Du kan köra denna registrering i USMF-demonstrationsföretaget och kan använda det föreslagna värdet. Vanligtvis utförs den här proceduren av en kontorist.  Kör uppgiftsregistreringen "kontrollera kvaliteten på varor" först. För att bearbeta godkännandet av en avvikelse måste användaren som utför uppgiftsregistreringen ha ett "namn"-värde tilldelat på användarsidan. För att använda dokumentanteckningar måste användaren även ha Dokumenthantering aktiverat i användaralternativen. 


## <a name="select-a-quality-order"></a>Välj en kvalitetsorder.
1. Gå till Kvalitetsorder.
2. Markera vald rad i listan.
    * Välj kvalitetsordern som skapades från uppgiftsregistreringen "kontrollera kvaliteten på varor".  

## <a name="create-a-nonconformance"></a>Skapa en avvikelse
1. Klicka på Förfrågningar.
2. Klicka på Avvikelser.
3. Klicka på Ny.
4. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Problemtyp.
    * Välj problemet som hittades vid inspektionen.  
5. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Problemtyp.
6. Hitta och markera önskad post i listan.
7. Klicka på länken på den valda raden i listan.
8. Klicka på OK.

## <a name="approvereject-a-nonconformance"></a>Godkänn/avvisa en avvikelse
1. Klicka på Funktioner.
2. Klicka på Godkänn avvikelse.
    * I detta exempel godkänner du avvikelsen. Godkända avvikelser kan associeras med tillhörande åtgärder om du vill registrera arbete som utförs som en del av avvikelsehanteringen och, som i den här uppgiften, bearbetningen av korrigeringshanteringen.  
3. Klicka på Ja.

## <a name="create-a-correction-action"></a>Skapa en korrigeringsåtgärd
1. Klicka på Korrigeringar.
2. Klicka på Ny.
3. Markera vald rad i listan.
4. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Personalnummer.
5. Klicka på länken på den valda raden i listan.
6. Klicka på Välj.
7. Klicka på Koppla.
    * Skapa en notering om korrigeringen. För det här exemplet är åtgärden att kontakta leverantören för att diskutera avvikelsen.  
8. Klicka på Ny.
9. Klicka på Anmärkning.
    * Observera att, beroende på rapportinställningarna, olika dokumenttyper kan skrivas ut på rapporter som är relaterade till avvikelsehanteringen.  
10. Ange ett värde i fältet Beskrivning.
11. Stäng sidan.

## <a name="maintain-a-correction"></a>Underhåll en korrigering
1. Klicka på Markera som slutförd.
2. Klicka på OK.
3. Stäng sidan.

## <a name="close-a-nonconformance"></a>Stäng en avvikelse
1. Klicka på Funktioner.
2. Klicka på Stäng avvikelsen.
3. Klicka på Ja.
4. Stäng sidan.
5. Stäng sidan.


