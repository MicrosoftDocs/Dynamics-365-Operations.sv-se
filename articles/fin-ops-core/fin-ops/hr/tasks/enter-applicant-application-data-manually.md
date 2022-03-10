---
title: Ange sökanden och ansökningsdata manuellt
description: I den här proceduren visas hur du manuellt hanterar information om sökanden och hans/hennes ansökning.
author: twheeloc
ms.date: 01/10/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: HcmApplicant, LogisticsContactInfoGrid, HRMApplication,  DirPartyTable
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 68f236ad000adea91e746309564baf84a270a0e5
ms.sourcegitcommit: 89655f832e722cefbf796a95db10c25784cc2e8e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/31/2022
ms.locfileid: "8075460"
---
# <a name="enter-applicant-and-application-data-manually"></a>Ange sökanden och ansökningsdata manuellt

> [!IMPORTANT]
> Funktionerna som anges i det här avsnittet är för närvarande tillgängliga för Personal-kunder i ekonomiinfrastrukturen.  


I den här proceduren visas hur du manuellt hanterar information om sökanden och hans/hennes ansökning. Du kan ange och hantera personuppgifter, intervjudata och tider, referenser, kompetenser och logiförfrågningar för sökande. Du kan även uppdatera statusen för sökandens platsansökningar och skapa brev eller e-postmeddelande för att kommunicera med sökanden. När du skapar en sökandepost, skapas en personpost för den sökanden i den globala adressboken. Demonstrationsdataföretaget **USMF** har använts för att skapa denna procedur.

## <a name="create-a-new-applicant-record"></a>Skapa en ny sökandepost

1. Gå till **Personal \> Rekrytering \> Sökanden \> Sökanden**.
2. Välj **Ny**.
3. Ange ett värde i fältet **Förnamn**.
4. I fältet **Efternamn** anger du ett värde.

    Du kan ange ytterligare information om sökande, om det finns tillgängligt. Du kan till exempel inkludera information om sökandens högsta examen, aktuell jobbtitel eller föregående arbetsgivare.

5. Expandera avsnittet **Kontaktinformation.**
6. Markera **Lägg till**.
7. I fältet **Beskrivning** ange **E-post för kommunikation**.
8. Välj ett alternativ i fältet **Typ**.
9. Skriv ett värde i fältet **Kontaktens nummer/adress**.

    Den här e-postadressen används för att skapa e-postkommunikation med den sökande.

10. Markera **Lägg till**.
11. I fältet **Beskrivning** anger du ett värde.
12. Skriv ett värde i fältet **Kontaktens nummer/adress**.

    Använd det här fältet om du vill ange ytterligare personlig information om den sökande, vid behov. Denna information kan till exempel inkludera ansökandens födelsedatum, etniskt ursprung eller civilstånd.

13. I åtgärdsfönstret väljer du **Kompetenser**.

    Du kan ange sökandens kompetensprofil, inklusive hans/hennes kompetenser, yrkeserfarenhet, utbildning, tester eller intyg. Den här informationen kan användas för att mappa sökandens kompetenser till de kompetenser som är associerade med de jobb som har definierats i företagets data.

## <a name="create-an-application-for-the-applicant"></a>Skapa en ansökning för den sökande

1. Välj **ansökning**.
2. Välj **Ny**.
3. I fältet **Rekryteringsprojekt** väljer du listrutepilen för att öppna sökningen.

    Genom att välja ett rekryteringsprojekt kommer den sökande att associeras med det specifika jobberbjudande som inkluderas i det rekryteringsprojektet.

4. Hitta och markera önskad post i listan.
5. Klicka på länken på önskad rad i valda listan.

    Som standard baseras jobbet och avdelningen på det valda rekryteringsprojektet.

6. Välj **Spara**.

    När du har sparat ansökan kan du bifoga dokument till den. Dessa dokument kan omfatta den sökandes erfarenhet, belöningar och cover letter.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
