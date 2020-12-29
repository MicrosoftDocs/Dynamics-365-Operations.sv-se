---
title: Skapa leveransplaner
description: Den här proceduren visas hur du kan skapa en leveransplan för en försäljningsorder.
author: omulvad
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, SalesDeliverySchedule, SalesEditLines,  SrsReportViewerForm
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7341ec21a89bf952e2fd21e9bebf7de65a1b2648
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437475"
---
# <a name="create-delivery-schedule"></a>Skapa leveransplaner

[!include [banner](../../includes/banner.md)]

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
