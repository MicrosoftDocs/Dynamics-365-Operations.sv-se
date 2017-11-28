--- 
title: Registrera en medarbetare i en variabel kompensationsplan
description: "Chefen över kompensationer och förmåner kan anmäla medarbetare till variabla kompensationsplaner att beräkna kontanta eller icke-kontanta ersättningar för medarbetare."
author: kherr75
manager: AnnBe
ms.date: 11/01/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 63a02a64ff28531bae950f1b61d9167eaa0b0373
ms.openlocfilehash: ebb92d5ce05f2891d25fb38f6200a10f02bcc948
ms.contentlocale: sv-se
ms.lasthandoff: 11/01/2017

---
# <a name="enroll-an-employee-in-a-variable-compensation-plan"></a>Registrera en medarbetare i en variabel kompensationsplan

[!include[task guide banner](../../includes/task-guide-banner.md)]

Chefen över kompensationer och förmåner kan anmäla medarbetare till variabla kompensationsplaner att beräkna kontanta eller icke-kontanta ersättningar för medarbetare. I den här proceduren förutsätts att en variabel kompensationsplan har skapats med fältet Aktivera anmälan inställt på Ja, och att berättiganderegler har skapats för den variabla kompensationsplanen. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF. Gå till Personal > Arbetare > Medarbetare > Kompensation > Registrering i variabel plan

1. Klicka på Ny.
2. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Plan.
    * Planuppslagningen filtreras för att visa endast de variabla kompensationsplaner som medarbetaren är berättigad till baserat på berättiganderegler.  
3. Klicka på länken på den valda raden i listan.
4. Växla utökningen av avsnittet Allmänt.
5. Ange ett datum i fältet Giltighetsdatum.
6. Klicka på Spara.
7. Växla utökningen av avsnittet Åsidosättningar.
    * Du kan också välja ett anställningsregeldatum för att åsidosätta anställningsdatumet för en medarbetare när anställningsregeln som har angetts för den valda variabla planen är Procent.  
    * Om den variabla planen är en procentsats av basplanen kan ersättningsprocenten åsidosättas för medarbetaren. Om den variabla kompensationsplanen är en plan med antal enheter kan antalet enheter åsidosättas för medarbetaren.  
    * Om medarbetaren ska få ett fast belopp i belöning, kan beloppet anges här.  
8. Växla utökningen av avsnittet Organisationsåsidosättningar.
    * Om hänsyn ska tas till medarbetarens resultat, resultat för olika avdelningar eller för en annan avdelning än den som har tilldelats till medarbetarens befattning kan avdelningen åsidosättas. Kolumnen Procent ska uppgå till 100.  


