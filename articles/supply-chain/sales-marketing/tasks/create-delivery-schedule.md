--- 
title: Skapa en leveransplan
description: "Den här proceduren visas hur du kan skapa en leveransplan för en försäljningsorder."
author: omulvad
manager: AnnBe
ms.date: 02/09/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 956edeac33f8531ecebef64301f2318333000429
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-delivery-schedule"></a>Skapa en leveransplan

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Den här proceduren visas hur du kan skapa en leveransplan för en försäljningsorder. En leveransplan används när en kvantitet på en order eller en offert begärs för att levereras i flera försändelser. Du kan köra den här proceduren i demonstrationsföretaget USMF eller på dina egna data.


## <a name="create-delivery-schedule"></a>Skapa leveransplaner
1. Gå till Alla försäljningsorder.
2. Klicka på Ny.
3. I fältet Kundkonto, ange eller välj ett värde.
4. Klicka på OK.
5. Ange eller välj ett värde i fältet Artikelnummer.
6. Ange ett tal som är större än 1 i fältet Kvantitet.
7. Klicka på Försäljningsorderrad.
8. Klicka på Leveransplan.
    * Leveransplansidan är stället där du kan ange antalet leveranser för den totala kvantiteten på orderraden som ska levereras till kunden.    
    * Som standard kopierar systemet den totala kvantiteten och andra leveransdetaljer för de ursprungliga försäljningsraderna till den första leveransplanraden. I det här exemplet ska du skapa ett schema för två leveranser, med det andra leveransdatumet med förskjutning på en vecka efter den första.  
9. Ange ett tal som är en del av den totala kvantiteten i fältet Kvantitet.
10. Klicka på Ny.
11. Ange den återstående kvantiteten i fältet Kvantitet.
12. Ange ett datum som infaller en vecka framåt från datumet för den första leveransraden i fältet Begärt transportdatum.
    * De två alternativen på avgiftskonverteringssnabbfliken styr hur du vill att avgifterna ska fördelas mellan leveransplanraderna, när de har tilldelats till den ursprungliga orderraden. Om du väljer att kopiera bruttobelopp, kopieras samma avgiftsbelopp till varje rad. Med alternativet Fördela på leveransrader delas avgiften lika mellan leveransraderna.  
    * Endast fasta kostnader kan delas, medan variabla avgifter ska kopieras till raderna.  
13. Flytta markören från den andra leveransraden om du vill uppdatera sidan.
    * Du kan spåra den totala kvantiteten som tilldelas till leveransplanraderna genom att visa summan och återstående fält. När den resterande kvantiteten är noll, har den fullständiga kvantiteten från den ursprungliga raden allokerats till tidsplaneringen.   
14. Klicka på OK.
    * Leveransplanen har nu kopierats till orderraderna.   
    * Den ursprungliga orderraden som kallas för en kommersiell rad, har konverterats till en orderrad med flera leveranser. Den markeras med en särskild ikon och fungerar som rubrik för leveransraderna.  
    * De två nya raderna som kallas för leveransrader utgör en leveransplan. Ordern ska bearbetas mot dessa rader och inte den ursprungliga raden. Om dokument som bekräftelser, plocklistor, följesedlar eller fakturor skrivs ut, visas bara leveransraderna.   
    * Leveransraderna kan ha andra leveransdatum, kvantiteter, leveranssätt och lagringsdimensioner, till exempel plats och lagerställe. Men produktdimensionerna måste alltid matcha dem på den kommersiella raden och kan inte ändras.  
15. Ange ett tal som är större än det nuvarande i fältet Kvantitet.
16. Markera den kommersiella raden för att se resultatet av kvantitetsomberäkningen.
17. Klicka på Plocka och packa i åtgärdsfönstret.
18. Klicka på Bokför följesedel.
19. Expandera avsnittet Parametrar.
20. Välj Alla i fältet Kvantitet.
    * Observera att följesedeln ska skapas för de två leveransplanraderna och inte den ursprungliga orderraden.  
21. Välj Ja i fältet Skriv ut följesedel.
22. Klicka på OK.
23. Klicka på Ja.
24. Stäng sidan.


