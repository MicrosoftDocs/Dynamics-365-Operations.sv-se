--- 
title: Aktivera utskrift av ID-nummer
description: "I den här proceduren aktiveras automatisk utskrift av ett EAN-kollinummer (SSCC) efter den sista artikeln som plockas från lagret i arbetsprocessen för försäljningsplocklistan."
author: perlynne
manager: AnnBe
ms.date: 11/03/2016
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
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 6d186bf7e4aee8cfa97adbd90b9090085e842f9b
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="enable-license-plate-label-printing"></a>Aktivera utskrift av ID-nummer

[!include[task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren aktiveras automatisk utskrift av ett EAN-kollinummer (SSCC) efter den sista artikeln som plockas från lagret i arbetsprocessen för försäljningsplocklistan. Du kan köra den här proceduren i demonstrationsdataföretaget USMF. Om du kör med dina egna data måste du ha en nummerserie som har ställts in för ID-nummer. Du måste konfigurera en etikettskrivare innan du börjar med den här uppgiften. Gå till Organisationsadministration > Inställningar > Nätverksskrivare. I åtgärdsfönstret klickar du på Alternativ och sedan på knappen Hämta installationsprogram för dokumentflödesagent. Kör installationsprogrammet och kontrollera att du har en nätverkskrivare som är inställd på Aktiv innan du fortsätter med proceduren.


## <a name="set-up-the-gs1-company-prefix"></a>Ställ in GS1-företagsprefix
1. Gå till Lagerstyrning > Inställningar > Parametrar för lagerstyrning.
2. Ange det sjusiffriga numret på ditt GS1-företag i fältet GS1-företagsprefix.
3. Klicka på Spara.
4. Stäng sidan.

## <a name="setup-the-sscc-license-plate-number-sequence"></a>Ställ in nummerserien för SSCC-ID-numret
1. Gå till Organisationsadministration > Nummerserier > Nummerserier.
2. Markera ett alternativ i fältet Område.
3. Markera ett alternativ i fältet Referens.
4. Skriv ett värde i fältet Företag.
5. Markera vald rad i listan.
6. Klicka på länken på den valda raden i listan.
7. Expandera avsnittet Segment.
8. Klicka på Redigera.
9. Välj den första raden i segmentregistret
10. Klicka på Ta bort.
11. Klicka på Ta bort.
12. Klicka på Spara.
13. Stäng sidan.

## <a name="create-the-document-route-layout"></a>Skapa dokumentflödeslayouten
1. Gå till Lagerstyrning > Inställningar > Dokumentflöde > Dokumentflödets layouter.
    * Aktivera SSCC-layout.  
2. Klicka på Ny.
3. Skriv ett värde i fältet Layout-ID.
4. Ange ett värde i fältet Beskrivning.
5. Hitta och markera önskad post i listan.
6. Klicka på Infoga vid textens slut.
7. Klicka på Spara.
8. Stäng sidan.

## <a name="set-up-the-document-routing"></a>Ställ in dokumentflödet
1. Gå till Lagerstyrning > Inställningar > Dokumentflöde > Dokumentflöde.
2. Välj ett alternativ i fältet Arbetsorder.
3. Klicka på Ny.
4. Ange ett värde i fältet Lagerställe.
5. Skriv ett värde i fältet Namn.
6. Klicka på Ny.
7. Ange eller välj ett värde i fältet Layout-ID.
8. I namnfältet väljer du det skrivarnamn som du vill använda.
9. Klicka på Spara.
10. Stäng sidan.

## <a name="create-mobile-device-menu"></a>Skapa meny på mobil enhet
1. Gå till Lagerstyrning > Inställningar > Mobil enhet > Menyalternativ på mobil enhet.
2. Klicka på Ny.
3. Skriv ett värde i fältet Menyalternativ.
4. Ange ett värde i fältet Titel.
5. Markera ett alternativ i fältet Läge.
6. Välj Ja i fältet Använd befintligt arbete.
7. Välj Ja i fältet Generera nummerplåt.
8. Expandera arbetsklassavsnittet.
9. Klicka på Ny.
10. Skriv ett värde i fältet Arbetsklass-ID.
11. Klicka på Spara.
12. Stäng sidan.
13. Gå till Lagerstyrning > Inställningar > Mobil enhet > Meny på mobil enhet.
14. Hitta och markera önskad post i listan.
15. I trädet markerar du "Välj menyalternativet du skapade tidigare i trädet".
16. Klicka på Redigera.
17. Klicka på pilen för att lägga till menykommandot till menyn.
18. Klicka på Spara.
19. Stäng sidan.

## <a name="update-a-work-template"></a>Uppdatera en arbetsuppgiftsmall
1. Gå till Lagerstyrning > Inställningar > Arbete > Arbetsmallar.
2. Hitta och markera önskad post i listan.
3. Klicka på Redigera.
4. Klicka på Ny.
5. Markera vald rad i listan.
6. Välj "Skriv ut" i fältet Arbetstyp.
7. I fältet Arbetsklass-ID, ange eller välj ett värde.
8. Klicka på länken på den valda raden i listan.
9. Klicka på Flytta upp.
10. Klicka på Spara.
11. Stäng sidan.


