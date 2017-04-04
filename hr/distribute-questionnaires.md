---
title: "Distribuera och slutföra en enkät"
description: "Det här avsnittet beskrivs hur distribuera enkäter som du skapar så att de blir tillgängliga för en person eller grupp av personer som ska slutföra dem.."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: KMConnectionType, KMKnowledgeCollectorPlanningTabel, SysEmailParameters
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 17424
ms.assetid: fd8d867a-2446-400a-b91f-ad4085427470
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: a76ec0cd86bcc810b42ae3cd8efd8a584e6c4da3
ms.openlocfilehash: 8e09c6b042d557e3b2d608fb5e278169fc3c1d88
ms.lasthandoff: 03/31/2017


---

# <a name="distribute-and-complete-a-questionnaire"></a>Distribuera och slutföra en enkät

Det här avsnittet beskrivs hur distribuera enkäter som du skapar så att de blir tillgängliga för en person eller grupp av personer som ska slutföra dem.. 

Det finns flera sätt att distribuera en enkät:

-   Markera enkäten som aktiv. Enkäten är då tillgänglig för alla medarbetare, om inte en enkätgrupp har ställts in för att begränsa åtkomst till den.
-   Tilldela rättigheter till en enkätgrupp. Enkäten är då tillgänglig för alla medlemmar i den valda gruppen.
-   Skapa planerade svarsomgångar. Enkäten är då endast tillgänglig för en viss person.
-   Skapa en tidsplan. Enkäten kan sedan vara tillgänglig för flera personer.

## <a name="marking-a-questionnaire-as-active"></a>Markera en enkät som aktiv.
Genom att ange den **aktiva** till **Ja** på de **enkäter** kan du göra enkäten tillgänglig för alla medarbetare att slutföra. Svarande kan fylla i formuläret flera gånger. Denna funktion är användbar om du vill samla in feedback kontinuerliga under hela året. Du kan till exempel göra en enkät där anställda ger feedback om lunchtjänsten i kafeterian.

## <a name="questionnaire-groups"></a>Enkätgrupper
Du kan ställa in enkätgrupper och sedan inkludera de svarande som ett frågeformulär ska distribueras till. 

Du kan skapa enkätgrupper på följande sidor:

-   **Enkätgrupper **– Endast personer i en enkätgrupp kan avsluta en vald enkät. Till exempel om din målgrupp är leverantörer, då skapar du en enkätgrupp som är specifik för dessa svarande.
-   **Enkätgruppsmedlemmar** – Du kan lägga till kontakter till enkätgrupperna.

Så här tilldelar du en enkätgruppen till en enkät på de **enkäter** klickar du på **användarrättigheter**. Medlemmar i enkätgruppen kan fylla i enkäten när enkäten har sparats som aktiv. Denna funktion är användbar om du vill testa en enkät i en utvald grupp användare innan du slår till en större grupp, eller om du vill bearbeta en enkät till en specifik målgrupp.

## <a name="planned-answer-sessions-in-a-questionnaire"></a>Planerade svarsomgångar i en enkät
Planerade svarsomgångar är enkäter som du har utformat för och valt svarande till. 

**Anm.:** Innan du kan ställa in planerade svarsomgångar måste du utforma en enkät. 

På sidan **Planerad svarsomgång** kan du skapa en planerad svarsomgång för en enskild medarbetare. Listan på sidan visar alla planerade enkäter. 

Planerade svarsomgångar används också på sidan **Tidsplaner för enkäter** där du kan planera enkäter för flera personer:

-   Medarbetare
-   Kursdeltagare
-   Organisationsenheter

Varje person får besvara enkäten en gång.

## <a name="scheduling-a-questionnaire"></a>Tidsplanera en enkät
Det går även att tidsplanera en enkät för flera svarande.

### <a name="planning-types"></a>Planeringstyper

Planeringstyper krävs om du vill schemalägga planerade svarsomgångar för flera svarande. Planeringstyper används för att klassificera enkättidsplaner. Du kan till exempel tidsplanera enkäter för följande syften:

-   Utvärdering
-   Översikt
-   Testa

Du kan ange planeringstyper för en enkät på sidan **Tidsplaner för enkäter** .

### <a name="reference-types-for-questionnaire"></a>Referenstyper för enkät

Du kan använda referenstyper när du vill ställa in kriterier för svarande som du kan välja när du tidsplanerar en enkät. 

Använd sidan **Referenstyper** för att ställa in referenstyper för en enkät. Varje referenstyp motsvarar en tabell i Microsoft Dynamics 365 för operationer. När du skapar enkättidsplaner kan du ange de enskilda posterna i tabellen eller ett intervall med poster som enkäten ska associeras med. 

Om du till exempel väljer tabellen Kurser kan du bestämma vilken specifik kurs enkäten ska gälla för. När du ställer in en referens för tabellen Kurser blir alla fält och knappar på sidan **Kurser** tillgängliga.

### <a name="questionnaire-schedules"></a>Tidsplaner för enkäter

Du kan använda tidsplaner för att generera flera planerade svarsomgångar för ett antal användare, baserad på en referenstyp. Skapa ett schema på den **tidsplaner** sida. Välj planeringstyp att kategorisera schemat och även välja referenstypen som ska användas för frågor i systemet för enskilda användare. Om du anger referenstypen tabellen kurser du exempelvis välja en viss kurs i den **referens** fält. 

Klicka på **Inställningsdetaljer** om du vill välja enkäten och andra kriterier. Ange namn på lärare som exempelvis om enkäten är en utvärdering av instruktören. När du är klar med att ange information genererar systemet planerade svarsomgångar för de användare som ingår i frågan. 

Klicka på **Planerade svarsomgångar** om du vill visa svarsomgången för tidsplanen. Därefter kan du manuellt skapa ytterligare planerade svarsomgångar eller ta bort planerade svarsomgångar som inte har besvarats. 

Klicka på **funktion**&gt;**starta** vill göra enkäten tillgänglig för användarna i relaterade planerade svarssessioner. Klicka på **Svar** om du vill visa de ifyllda svaren på enkäten. Du kan också kopiera enkätens tidsplaninställningar, planerade svarsomgångar och svaren till en ny enkättidsplan.

## <a name="notifying-respondents-about-questionnaires-that-are-available-to-them"></a>Meddela svarande om enkäter som är tillgängliga för dem
När du distribuerar en enkät måste du meddela svarande att enkäter finns tillgängliga för dem. 

**Anmärkning:** svarande måste vara en användare i Microsoft Dynamics 365 att slutföra en enkät.

### <a name="notifying-respondents-about-a-planned-answer-session"></a>Meddela svarande om en planerad svarsomgång

Om du använder en planerad svarsomgång måste du meddela personen direkt, till exempel per telefon eller e-post.

### <a name="notifying-respondents-about-a-scheduling"></a>Meddela svarande om en planering

Använd sidan **Tidsplaner för enkäter** för att förbereda och skicka ett e-postmeddelande till alla svarande som är kopplade till enkäten. Skriv in e-postmeddelandets text på fliken **E-post för medarbetarsjälvbetjäning**. När du har startat schemat klickar du på **funktion**&gt;**skicka e-post** att generera och skicka e-postmeddelandet till svarande. Svarande kan sedan logga in på webbplatsen och fylla i enkäten. 

**Anm.:** Innan du kan använda e-postfunktionen måste din IT-administratör ange e-postinställningarna på sidan **E-postparametrar**.

## <a name="ending-a-scheduled-questionnaire"></a>Avsluta en tidsplanerad enkät
Du kan avsluta en tidsplanerad enkät när alla svaranden har avslutat sina tilldelade svarsomgångar. När planerad enkät slutförs kan du inte kopiera inställningarna till en ny tidsplan. 

**Anm.:** Om en eller flera svarande inte har fyllt i enkäten och du fortfarande vill avsluta tidsplanen måste du först radera dessa svarande från listan på sidan **Planerad svarsomgång**. Sedan kan du avsluta tidsplanen.

## <a name="completing-questionnaires"></a>Fylla i enkäter
När du har utformat och har fördelat en enkät kan den besvaras av valda svarande. Du kan fylla i de tillgängliga frågeformulären från två platser:

-   I navigeringsfönstret klickar du på **enkäter**&gt;**fördela**&gt;**fylla i en enkät**.
-   Klicka på **Enkäter att fylla i** i Medarbetarsjälvbetjäning.

Enkäter kan göras tillgängliga för vissa användare eller grupper av användare eller för alla användare i ett nätverk.

<a name="see-also"></a>Se även
--------

[Utforma enkäter](design-questionnaires.md)

[Använda enkäter](questionnaires.md)

[Visa och utvärdera resultaten för enkäter](evaluate-questionnaire-results.md)


