--- 
title: "Skapa överföringsaktiviteter för lean manufacturing"
description: "Skapa en överföringsaktivitet för lean manufacturing."
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
ms.openlocfilehash: 010ac08fa96ead49b6ecbbe083e59fb96427e29e
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="create-transfer-activities-for-lean-manufacturing"></a>Skapa överföringsaktiviteter för lean manufacturing

[!include [task guide banner](../../includes/task-guide-banner.md)]

Skapa en överföringsaktivitet för lean manufacturing. 

Förutsättningar: 

1. Ett produktionsflöde och en version som inte är aktiv måste skapas.

2. Från- och till-lagerställe och -platser måste skapas. Den påfyllande eller påfyllda arbetsgruppen bör skapas (valfritt).


## <a name="find-the-production-flow-version"></a>Hitta produktionsflödesversionen
1. Gå till Produktionskontroll > Inställningar > Lean-produktionsflöde > Produktionsflöden.
2. Hitta och markera önskad post i listan.
    * Observera att produktionsflödet måste ha en version med utkaststatus.  
3. Klicka på länken på den valda raden i listan.

## <a name="create-a-new-activity"></a>Skapa en ny aktivitet
1. Klicka på Aktiviteter.
    * Kontrollera att det valda produktionsflödet har en version i utkast och välj den version.  
2. Klicka på Skapa en ny planaktivitet.
3. Klicka på Nästa.
4. Skriv ett värde i fältet Namn.
5. I fältet Aktivitetstyp väljer du Överföring.
6. Ange ett nummer i fältet Processkvantitet.
7. Klicka på Nästa.

## <a name="select-the-work-cells"></a>Välj arbetsgrupperna
1. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Fyller på.
    * Välj en arbetsgrupp om du vill använda utleveransplatsen för arbetsgruppen som "från"-platsen i överföringsaktiviteten. Detsamma kan göras med den påfyllda arbetsgruppen, som anger destinationsplatsen för överföringsaktiviteten.  
2. Klicka på länken på den valda raden i listan.

## <a name="define-the-inventory-updates"></a>Definiera lageruppdateringarna
1. Välj ett alternativ i fältet Produkttyp.
    * Observera att en överföring inte ändrar typen av produkt. Du kan överföra färdiga produkter eller halvfärdiga produkter (överföring mellan två aktiviteter av ett produktionsflöde och eventuellt ett kanban-flöde).     När du överför färdiga produkter kan du välja om du plockar eller tar emot resultat i en lagertransaktion.  

## <a name="define-the-transfer-locations"></a>Definiera överföringsplatserna
1. Klicka på Nästa.
2. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Lagerställe.
3. Hitta och markera önskad post i listan.
4. Klicka på länken på den valda raden i listan.
5. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Plats.
6. Klicka på länken på den valda raden i listan.
7. Välj Speditör” i fältet Fraktad av.
    * Alternativen inkluderar: Speditör – organisationen som driver speditionslagret, Mottagare – organisationen som driver inleveranslagret, Transportföretag: – en tredjepartsleverantör. Om organisationen är en leverantör kräver överföringsaktiviteten ett legotillverkningsavtal.  
8. Klicka på Nästa.

## <a name="define-the-activity-times"></a>Definiera aktivitetstiderna
1. Hitta och markera önskad post i listan.
    * Definitionen av en körning krävs. Körningen används för att beräkna kostnaden och genomflödetiderna för kanban-jobben. Körningar används inte för att beräkna kapacitetsbeläggning och förbrukning, vilket beräknas med cykeltider, som hämtas från uppgiften för produktionsflödesversion.  
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


