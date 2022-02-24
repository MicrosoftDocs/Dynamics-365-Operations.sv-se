---
title: Distribuera en enkät med hjälp av tidsplanering
description: Enkättidsplanering gör att du kan planera och distribuera enkäter till flera svaranden.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KMKnowledgeCollectorPlanningTable, KMKnowledgeCollectorPlanningMulti, SysQueryForm, HcmPersonLookup, KMKnowledgeCollectorPlanning, HcmLearningWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d233938fe553dbd7da7fcc5477097fd885665102
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4420652"
---
# <a name="distribute-questionnaires-using-scheduling"></a>Distribuera en enkät med hjälp av tidsplanering

Enkättidsplanering gör att du kan planera och distribuera enkäter till flera svaranden. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.

## <a name="create-a-questionnaire-schedule"></a>Skapa en tidsplan för enkäter

1. Gå till Enkät > Distribuera > Tidsplaner för enkät.

2. Klicka på Ny.

3. Ange ett värde i fältet Tidsplanering.

4. Ange ett värde i fältet Beskrivning.
    * Ställ in schemat till Anonymt, om svaren ska registreras utan tillhörande namn till svaret.  
    * Om du vill tillåta anonyma resultat måste detta ställas in bland personalparametrarna först.  

5. Välj planeringstypen i fältet Typ.  I detta exempel använder vi nöjdhetstypen.

6. Hitta och markera önskad post i listan.

7. Klicka på länken på den valda raden i listan.

8. Ange ett datum i fältet Datum.

9. Expandera avsnittet Email for employee self service section.

10. Skriv ett värde i fältet Ämne.

    * Exempel: Enkät tillgänglig  

11. I textrutan skriver du brödtexten i ditt e-postmeddelande. Notera att variabeln kan användas för att byta ut värdena i systemet.

    * Exempel: Bästa %P%, vänligen logga in på Employee Self Service för att slutföra personalhälsoenkäten.  Contoso  

12. Klicka på Spara.

## <a name="use-the-setup-details-to-select-the-questionnaires-to-be-answered-as-well-as-any-queries-to-use-to-select-respondents"></a>Använd inställningsinformationen för att välja den/de enkät(er) som ska besvaras, samt alla eventuella frågor som ska användas för att välja svarande.

1. Klicka på Inställningsdetaljer.

2. I listan väljer du en fråga att använda för att söka igenom systemet efter svarande till enkäten.

    * Exempel: Arbetare  

3. Klicka på Visa eller ändra frågan, om du vill välja specifika personer eller justera frågan för att hitta personer som uppfyller vissa villkor.

    * Observera att alla svaranden även måste vara användare i systemet.  

4. Markera raden för Person i listan.

5. Ange eller välj ett värde i fältet Kriterier.

    * Välj Julia Funderburk  

6. I listan väljer du Julia Funderburk

7. Klicka på OK.

8. Klicka på fliken Enkät.

9. Expandera "the node for the questionnaire type Satisfaction Survey" i trädet.

10. Kontrollera "Workforce Health Assessment" i trädet.

11. Klicka på OK.

12. Klicka på Planerad svarsomgång.

    * Observera att Planerade svarsomgångar har skapats för varje vald/tillfrågad användare.  

13. Stäng sidan.

## <a name="start-the-questionnaire-schedule-in-order-to-make-the-questionnaire-available-for-respondents-to-complete"></a>Starta enkättidsplanen om du vill göra enkäten tillgänglig för de svarande att fylla i.

1. Klicka på Funktioner.

2. Klicka på Start.

3. Klicka på OK.

## <a name="send-the-email-to-inform-respondents-of-the-available-questionnaire"></a>Skicka e-postmeddelandet som informerar de svarande om den tillgängliga enkäten.

1. Klicka på Funktioner.

2. Klicka på Send email.

3. Klicka på Avbryt.

## <a name="use-planned-answer-sessions-to-monitor-who-needs-to-complete-the-questionnaire"></a>Använd "Planned answer sessions" för att övervaka vem som måste fylla i enkäten.

1. Klicka på Planerad svarsomgång.

    * Ta bort alla återstående planerade svarsomgångar när du är klar att avsluta den schemalagda sessionen.  

2. Klicka på Ta bort.

3. Klicka på Ja.

4. Stäng sidan.

## <a name="end-the-schedule-when-all-respondents-have-completed-the-questionnaire-andor-all-remaining-planned-answer-sessions-have-been-deleted"></a>Avsluta tidsplaneringen när alla svarande har fyllt i enkäten och/eller alla återstående planerade svarsomgångar har raderats.

1. Klicka på Funktioner.
2. Klicka på Slut.
3. Klicka på OK.

