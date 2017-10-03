--- 
title: 'Definiera rullande inventering '
description: "Rullande inventering är en lagerställesprocess som du kan använda för att kontrollera lagerbehållningsartiklar."
author: MarkusFogelberg
manager: AnnBe
ms.date: 06/23/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: f0d598bbd13406b27a23dcf349f6c81e758a9e61
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---
# <a name="define-cycle-counting"></a>Definiera rullande inventering  

[!include[task guide banner](../../includes/task-guide-banner.md)]

Rullande inventering är en lagerställesprocess som du kan använda för att kontrollera lagerbehållningsartiklar. Den här uppgiftsinspelningen visar hur du kan ställa in standardarbetsprioriteten för inventering; aktivera ett menykommando för mobila enheter för att bearbeta både plocknings- och inventeringsåtgärder; aktivera en utlösare för inventeringströskeln när en plats blir tom; aktivera en plan för rullande inventering för en viss artikel i ett bestämt lagerställe. Dessa inställningsuppgifter utförs normalt av en lagerchef. Du kan gå igenom den här proceduren i demonstrationsdataföretaget USMF eller i dina egna data.


## <a name="set-the-priority-of-counting-work"></a>Ange prioriteten för inventeringsarbete
1. Gå till Lagerstyrning > Inställningar > Parametrar för lagerstyrning.
2. Klicka på fliken Rullande inventering.
3. Ange ett värde i fältet Standardarbetsprioritet för rullande inventering.
    * Det här steget ändrar prioriteten för arbetet med rullande inventering jämfört med andra typer av arbete i lagerstället. Genom att ange ett lägre nummer än numret för andra typer av arbete, ger du arbetet med rullande inventering en högre prioritet.  
4. Klicka på Spara.
5. Stäng sidan.

## <a name="enable-the-mobile-device"></a>Aktivera den mobila enheten
1. Gå till Lagerstyrning > Inställningar > Mobil enhet > Menyalternativ på mobil enhet.
2. Klicka på Ny.
3. Skriv ett värde i fältet Menyalternativ.
4. Ange ett värde i fältet Titel.
5. Välj Arbete i fältet Läge.
6. Ange alternativet Använd befintligt arbete till Ja.
    * Om du anger det här alternativet till Ja kommer systemet att leta efter befintligt arbete när menykommandot för mobila enheter används.  
7. Välj Systemstyrd i fältet Dirigerad av.
    * När Systemstyrd har valts styrs lagerarbetaren till öppet arbete som definieras i arbetsklasser. (Vi ska skapa dessa arbetsklasser härnäst.)  
8. Dölj eller Visa avsnittet Arbetsklasser.
    * Härnäst ska vi skapa två arbetsklasser som ska användas med menykommandot för mobila enheter. När menykommandot används skickas frågor till dessa arbetsklasser, och arbetet med den högsta prioriteten visas för användaren.  
9. Klicka på Ny.
10. Välj ett värde i fältet Arbetsklass-ID.
11. Klicka på Ny.
12. Välj ett värde i fältet Arbetsklass-ID.
13. Klicka på Spara.
14. Stäng sidan.
15. Gå till Lagerstyrning > Inställningar > Mobil enhet > Meny på mobil enhet.
16. Hitta och markera önskad post i listan.
17. Välj menykommandot som du nyss skapat i trädet.
18. Klicka på Redigera.
19. Klicka på pilen för att lägga till menykommandot på menyn.
20. Klicka på Spara.

## <a name="create-a-counting-threshold"></a>Skapa en tröskel för rullande inventering
1. Gå till Lagerstyrning > Inställningar > Rullande inventering > Trösklar för rullande inventering.
2. Klicka på Ny.
3. Skriv ett värde i fältet Tröskel-ID för rullande inventering.
4. Ange alternativet Bearbeta rullande inventering direkt till Ja.
5. Ange ett värde i fältet Beskrivning.
6. Klicka på Spara.
7. Klicka på Välj platser.
8. Markera vald rad i listan.
9. Välj ett värde i fältet Kriterier.
10. Klicka på OK.
11. Stäng sidan.

## <a name="create-a-cycle-count-plan"></a>Skapa en plan för rullande inventering
1. Gå till Lagerstyrning > Inställningar > Rullande inventering > Planer för rullande inventering.
2. Klicka på Ny.
3. Skriv ett värde i fältet Plan-ID för rullande inventering.
4. Skriv ett värde i fältet Beskrivning.
5. Ange ett värde i fältet Högsta antal rullande inventeringar.
6. Klicka på Spara.
7. Klicka på Välj platser.
8. Markera vald rad i listan.
9. Välj ett värde i fältet Kriterier.
10. Klicka på OK.
11. Ange ett värde i fältet Dagar mellan rullande inventering.
    * Om till exempel fältet Dagar mellan rullande inventering anges till 5 kommer ett arbete för rullande inventering att skapas var femte dag. Men om arbete för rullande inventering bearbetas på dag tre kommer nästa arbete för rullande inventering skapas fem dagar efter att den sista rullande inventeringen bearbetades på dag åtta.  
12. Klicka på Spara.
13. Klicka på Ny.
14. Ange ett nummer i fältet Sekvensnummer.
    * Sorteringsordningen är från det lägsta talet till det högsta talet. Värdet måste vara större än 0 (noll).  
15. Markera vald rad i listan.
16. Ange ett värde i fältet Beskrivning.
17. Klicka på Spara.
18. Klicka på Definiera produktfråga.
19. Markera vald rad i listan.
20. Ange eller välj ett värde i fältet Kriterier.
21. Klicka på OK.
22. Stäng sidan.


