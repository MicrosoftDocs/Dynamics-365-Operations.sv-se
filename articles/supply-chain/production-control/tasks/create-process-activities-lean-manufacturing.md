--- 
title: "Skapa processaktiviteter för lean manufacturing"
description: "Skapa en processaktivitet för lean manufacturing."
author: cvocph
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: dd77c20b622fd8a14e1cdf77883043699f9a6317
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="create-process-activities-for-lean-manufacturing"></a>Skapa processaktiviteter för lean manufacturing

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Skapa en processaktivitet för lean manufacturing. 

Förutsättningar: 

1. Ett produktionsflöde och en version som inte är aktiv måste skapas.

2. En arbetsgrupp måste skapas.


## <a name="find-the-production-flow-version"></a>Hitta produktionsflödesversionen
1. Gå till Produktionskontroll > Inställningar > Lean-produktionsflöde > Produktionsflöden.
2. Hitta och markera önskad post i listan.
3. Klicka på länken på den valda raden i listan.

## <a name="create-a-new-activity"></a>Skapa en ny aktivitet
1. Klicka på Aktiviteter.
    * Kontrollera att det valda produktionsflödet har en version i utkast och välj den version.  
2. Klicka på Skapa en ny planaktivitet.
3. Klicka på Nästa.
4. Skriv ett värde i fältet Namn.
5. Skriv ett värde i fältet Namn.
    * Observera att namnet måste vara unikt för ett visst produktionsflöde för alla versioner.  
6. Ange ett nummer i fältet Processkvantitet.
    * Observera att oavsett vilken jobbkvantitet som ska bearbetas så är detta den minsta kvantiteten per jobb för att beräkna arbetskostnaden. Om jobbkvantiteter avviker från denna kvantitet skapas arbetskostnadsavvikelser.  
7. Klicka på Nästa.

## <a name="select-the-work-cell"></a>Välj arbetsgruppen
1. Klicka på den nedrullningsbara knappen för att öppna uppslaget i fältet Arbetsgrupp.
2. Klicka på länken på den valda raden i listan.

## <a name="define-the-inventory-updates"></a>Definiera lageruppdateringarna
1. Markera eller avmarkera kryssrutan Uppdatera inleverans för behållning.
    * Om Uppdatera behållning = Nej kan du definiera aktiviteten för att ta emot en halvfärdig produkt (aktiviteten når inte nästa strukturlistenivån).    Du kan också välja att förbruka halvfärdiga produkter.  

## <a name="define-the-picking-activities"></a>Definiera plockningsaktiviteterna
1. Klicka på Nästa.
2. Markera vald rad i listan.
    * En standardplockningsaktivitet skapas för inleveransplatsen för den valda arbetsgruppen.  
3. Klicka på Lägg till.
    * Du kan skapa ytterligare plockningsaktiviteter för specifika produkter, som inte mellanlagras i inleveransaktiviteten för arbetsgruppen.  
4. Hitta och markera önskad post i listan.
5. Skriv ett värde i fältet Artikelnummer.
6. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Lagerställe.
    * Med denna definition plockas allt material som förbrukats i aktiviteten från standardinleveranslagret och standardinleveransplatsen förutom artikeln som definieras i den andra plockningsaktiviteten. Den här artikeln plockas från ett annat lagerställe och en annan plats.  
7. Hitta och markera önskad post i listan.
8. Klicka på länken på den valda raden i listan.
9. Markera eller avmarkera kryssrutan Registerkassation.
10. Klicka på Nästa.

## <a name="define-the-activity-times"></a>Definiera aktivitetstiderna
1. Hitta och markera önskad post i listan.
    * Definitionen av en körning krävs. Körningen används för att beräkna kostnader och genomflödetiderna för kanban-jobben. Körningar används inte för att beräkna kapacitetsbeläggning och förbrukning; detta beräknas med cykeltider, som hämtas från uppgiften för produktionsflödesversion.  
2. Ange ett värde i fältet Tid.
3. Skriv ett värde i fältet Enhet.
4. Välj tidsenhet.
5. Ange ett värde i fältet Per kvantitet.
6. Hitta och markera önskad post i listan.
    * Kötider är valfria.  
7. Ange ett värde i fältet Tid.
8. Skriv ett värde i fältet Enhet.
9. Välj tidsenhet.
10. Ange ett värde i fältet Per kvantitet.
11. Klicka på Nästa.
12. Klicka på Avsluta.
13. Stäng sidan.


