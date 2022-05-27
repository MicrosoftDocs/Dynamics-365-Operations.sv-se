---
title: Distribuera en enkät med hjälp av tidsplanering
description: Enkättidsplanering gör att du kan planera och distribuera enkäter till flera svaranden.
author: twheeloc
ms.date: 10/28/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KMKnowledgeCollectorPlanningTable, KMKnowledgeCollectorPlanningMulti, SysQueryForm, HcmPersonLookup, KMKnowledgeCollectorPlanning, HcmLearningWorkspace
audience: Application User
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c82f688a3d9366e629eedefd876dd5669bd7ed04
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/04/2022
ms.locfileid: "8691650"
---
# <a name="distribute-questionnaires-using-scheduling"></a>Distribuera en enkät med hjälp av tidsplanering


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Enkättidsplanering gör att du kan planera och distribuera enkäter till flera svaranden. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.

## <a name="create-a-questionnaire-schedule"></a>Skapa en tidsplan för enkäter

1. Gå till **Enkät** > **Distribuera** > **Enkätscheman**.

2. Klicka på **Ny**.

3. Ange ett värde i fältet **Schemaläggning**.

4. I fältet **Beskrivning** anger du ett värde.
    * Ange schemat som **Anonymt** om svaren ska registreras utan namn kopplade till svaret.  
    * Om du vill tillåta anonyma resultat måste detta ställas in bland personalparametrarna först.  

5. I fältet **Typ** väljer du planeringstyp.  I detta exempel använder vi typen **Nöjdhet**.

6. Hitta och markera önskad post i listan.

7. Klicka på länken på den valda raden i listan.

8. Ange ett datum i fältet **Datum.**

9. Visa avsnittet **E-post för självbetjäning för medarbetare**.

10. Skriv ett värde i fältet **Ämne**.

    * Exempel: Enkät tillgänglig  

11. I fältet **Text** anger du bördtexten för ditt e-postmeddelande. Notera att variabeln kan användas för att byta ut värdena i systemet.

    * Exempel: Bästa %P%, vänligen logga in på Självbetjäning för medarbetare för att slutföra personalhälsoenkäten.  Contoso  

12. Klicka på **Spara**.

## <a name="use-the-setup-details-to-select-the-questionnaires-to-be-answered-as-well-as-any-queries-to-use-to-select-respondents"></a>Använd inställningsinformationen för att välja den/de enkät(er) som ska besvaras, samt alla eventuella frågor som ska användas för att välja svarande.

1. Klicka på **Konfigurationsdetaljer**.

2. I listan väljer du en fråga att använda för att söka igenom systemet efter svarande till enkäten.

    * Exempel: Arbetare  

3. Klicka på **Visa eller modifiera fråga** om du vill välja folk eller justera frågan i syfte att finna folk som matchar specifika kriterier.

    * Observera att alla svaranden även måste vara användare i systemet.  

4. Markera raden för Person i listan.

5. I fältet **Kriterier** anger du eller väljer ett värde.

    * Välj Julia Funderburk  

6. I listan väljer du Julia Funderburk

7. Klicka på **OK**.

8. Klicka på fliken **Enkäter**.

9. Visa noden för enkättypen **Nöjdhetsenkät** i trädet.

10. Kontrollera "Workforce Health Assessment" i trädet.

11. Klicka på **OK**.

12. Klicka på **Planerad svarssession**.

    * Notera att **Planerade svarssessioner** har kunnat skapas för varje enskild vald/tillfrågad användare.  

13. Stäng sidan.

## <a name="start-the-questionnaire-schedule-in-order-to-make-the-questionnaire-available-for-respondents-to-complete"></a>Starta enkättidsplanen om du vill göra enkäten tillgänglig för de svarande att fylla i.

1. Klicka på **Funktioner**.

2. Klicka på **Start**.

3. Klicka på **OK**.

## <a name="send-the-email-to-inform-respondents-of-the-available-questionnaire"></a>Skicka e-postmeddelandet som informerar de svarande om den tillgängliga enkäten.

1. Klicka på **Funktioner**.

2. Klicka på **Skicka e-post**.

3. Klicka på **Avbryt**.

## <a name="use-planned-answer-sessions-to-monitor-who-needs-to-complete-the-questionnaire"></a>Använd "Planned answer sessions" för att övervaka vem som måste fylla i enkäten.

1. Klicka på **Planerad svarssession**.

    * Ta bort alla återstående planerade svarsomgångar när du är klar att avsluta den schemalagda sessionen.  

2. Klicka på **Ta bort**.

3. Klicka på **Ja**.

4. Stäng sidan.

## <a name="end-the-schedule-when-all-respondents-have-completed-the-questionnaire-andor-all-remaining-planned-answer-sessions-have-been-deleted"></a>Avsluta tidsplaneringen när alla svarande har fyllt i enkäten och/eller alla återstående planerade svarsomgångar har raderats.

1. Klicka på **Funktioner**.
2. Klicka på **Slut**.
3. Klicka på **OK**.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
