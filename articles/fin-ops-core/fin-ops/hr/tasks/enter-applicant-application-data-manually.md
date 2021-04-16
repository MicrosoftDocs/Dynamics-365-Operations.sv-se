---
title: Ange sökanden och ansökningsdata manuellt
description: I den här proceduren visas hur du manuellt hanterar information om sökanden och hans/hennes ansökning.
author: andreabichsel
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: HcmApplicant, LogisticsContactInfoGrid, HRMApplication,  DirPartyTable
audience: Application User
ms.reviewer: anbichse
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 08104729f5be15ef7e727102e7be731bdda1a38c
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5751992"
---
# <a name="enter-applicant-and-application-data-manually"></a>Ange sökanden och ansökningsdata manuellt

[!include [banner](../../includes/banner.md)]

I den här proceduren visas hur du manuellt hanterar information om sökanden och hans/hennes ansökning.   Du kan ange och hantera personuppgifter, intervjudata och tider, referenser, kompetenser och logiförfrågningar för sökande. Du kan även uppdatera statusen för sökandens platsansökningar och skapa brev eller e-postmeddelande för att kommunicera med sökanden. När du skapar en sökandepost, skapas en personpost för den sökanden i den globala adressboken.       Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.


## <a name="create-a-new-applicant-record"></a>Skapa en ny sökandepost
1. Gå till Personal > Rekrytering > Sökanden > Sökanden.
2. Klicka på Ny.
3. I fältet Förnamn, skriv ett värde.
4. I fältet Efternamn, skriv ett värde.
    * Du kan ange ytterligare information om sökande, om det finns tillgängligt. Du kan till exempel inkludera information om sökandens högsta examen, aktuell jobbtitel eller föregående arbetsgivare.  
5. Växla expansionen av avsnittet Kontaktinformation.
6. Klicka på Lägg till.
7. Skriv "E-post för kommunikation" i fältet Beskrivning.
8. Välj ett alternativ i fältet Typ.
9. Skriv ett värde i fältet Kontaktens nummer/adress.
    * Den här e-postadressen används för att skapa e-postkommunikation med den sökande.  
10. Klicka på Lägg till.
11. Ange ett värde i fältet Beskrivning.
12. Skriv ett värde i fältet Kontaktens nummer/adress.
    * Personliga uppgifter om den sökande.  
    * Du kan ange ytterligare personliga uppgifter för den sökande, om det behövs. Detta kan till exempel inkludera födelsedatum, etniskt ursprung eller civilstånd.  
13. Klicka på Kompetenser i åtgärdsfönstret.
    * Du kan ange sökandens kompetensprofil, inklusive hans/hennes kompetenser, yrkeserfarenhet, utbildning, tester eller intyg.  
    * Den här informationen kan användas för att mappa sökandens kompetenser till de kompetenser som är associerade med de jobb som har definierats i företagets data.   

## <a name="create-an-application-for-the-applicant"></a>Skapa en ansökning för den sökande
1. Klicka på Ansökningar.
2. Klicka på Ny.
3. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Rekryteringsprojekt.
    * Genom att välja ett rekryteringsprojekt kommer den sökande att associeras med det specifika jobberbjudande som inkluderas i det rekryteringsprojektet.  
4. Hitta och markera önskad post i listan.
5. Klicka på länken på den valda raden i listan.
    * Som standard baseras jobbet och avdelningen på det valda rekryteringsprojektet.  
6. Klicka på Spara.
    * När du har sparat ansökningen kan du koppla dokument till den, inklusive sökandens erfarenhet, belöningar och följebrevet.  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]