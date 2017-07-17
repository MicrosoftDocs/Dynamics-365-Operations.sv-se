---
title: "Distribuera och slutföra en enkät"
description: "Den här artikeln beskriver hur du fördelar de enkäter som du utformar så att de blir tillgängliga för den person eller grupp som ska fylla i dem."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: KMConnectionType, KMKnowledgeCollectorPlanningTabel, SysEmailParameters
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 17424
ms.assetid: fd8d867a-2446-400a-b91f-ad4085427470
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: bcaaa846e0e88eca2c24048b483db8a031b19c43
ms.openlocfilehash: a8bbfd89d1bc34615e13b0cda62dcaf7c29e59eb
ms.contentlocale: sv-se
ms.lasthandoff: 06/20/2017


---

# Distribuera och slutföra en enkät
<a id="distribute-and-complete-a-questionnaire" class="xliff"></a>

Den här artikeln beskriver hur du fördelar de enkäter som du utformar så att de blir tillgängliga för den person eller grupp som ska fylla i dem. 

Det finns flera sätt att distribuera en enkät:

-   Markera enkäten som aktiv. Enkäten är då tillgänglig för alla medarbetare, om inte en enkätgrupp har ställts in för att begränsa åtkomst till den.
-   Tilldela rättigheter till en enkätgrupp. Enkäten är då tillgänglig för alla medlemmar i den valda gruppen.
-   Skapa planerade svarsomgångar. Enkäten är då endast tillgänglig för en viss person.
-   Skapa en tidsplan. Enkäten kan sedan vara tillgänglig för flera personer.

## Markera en enkät som aktiv.
<a id="marking-a-questionnaire-as-active" class="xliff"></a>
Genom att ange fältet **Aktiv** som **Ja** på sidan **Enkäter** kan du göra enkäten tillgänglig för alla medarbetare. De svarande kan fylla i formuläret flera gånger. Denna funktion är användbar om du vill samla in feedback kontinuerligt under hela året. Du kan till exempel göra en enkät där anställda ger feedback om lunchtjänsten i kafeterian.

## Enkätgrupper
<a id="questionnaire-groups" class="xliff"></a>
Du kan ställa in enkätgrupper och sedan inkludera de svarande som ett frågeformulär ska distribueras till. 

Du kan skapa enkätgrupper på följande sidor:

-   **Enkätgrupper**– Endast personer i en enkätgrupp kan avsluta en vald enkät. Till exempel om din målgrupp är leverantörer, då skapar du en enkätgrupp som är specifik för dessa svarande.
-   **Enkätgruppsmedlemmar** – Du kan lägga till kontakter till enkätgrupperna.

På sidan **Enkäter** klickar du på **Användarrättigheter** för att tilldela en enkätgrupp till en enkät. Medlemmarna i enkätgruppen kan fylla i enkäten när enkäten har sparats som aktiv. Denna funktion är användbar om du vill testa en enkät i en utvald grupp användare innan du skickar ut den till en större grupp, eller om du vill rikta enkäten till en mycket specifik målgrupp.

## Planerade svarsomgångar i en enkät
<a id="planned-answer-sessions-in-a-questionnaire" class="xliff"></a>
Planerade svarsomgångar är enkäter som du har utformat för och valt svarande till. 

**Anm.:** Innan du kan ställa in planerade svarsomgångar måste du utforma en enkät. 

På sidan **Planerad svarsomgång** kan du skapa en planerad svarsomgång för en enskild medarbetare. Listan på sidan visar alla planerade enkäter. 

Planerade svarsomgångar används också på sidan **Tidsplaner för enkäter** där du kan planera enkäter för flera personer:

-   Medarbetare
-   Kursdeltagare
-   Organisationsenheter

Varje person får besvara enkäten en gång.

## Tidsplanera en enkät
<a id="scheduling-a-questionnaire" class="xliff"></a>
Det går även att tidsplanera en enkät för flera svarande.

### Planeringstyper
<a id="planning-types" class="xliff"></a>

Planeringstyper krävs om du vill schemalägga planerade svarsomgångar för flera svarande. Planeringstyper används för att klassificera enkättidsplaner. Du kan till exempel tidsplanera enkäter för följande syften:

-   Utvärdering
-   Översikt
-   Testa

Du kan ange planeringstyper för en enkät på sidan **Tidsplaner för enkäter** .

### Referenstyper för enkät
<a id="reference-types-for-questionnaire" class="xliff"></a>

Du kan använda referenstyper när du vill ställa in kriterier för svarande som du kan välja när du tidsplanerar en enkät. 

Använd sidan **Referenstyper** för att ställa in referenstyper för en enkät. Varje referenstyp motsvarar en tabell i Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition. När du skapar enkättidsplaner kan du ange de enskilda posterna i tabellen eller ett intervall med poster som enkäten ska associeras med. 

Om du till exempel väljer tabellen Kurser kan du bestämma vilken specifik kurs enkäten ska gälla för. När du ställer in en referens för tabellen Kurser blir alla fält och knappar på sidan **Kurser** tillgängliga.

### Tidsplaner för enkäter
<a id="questionnaire-schedules" class="xliff"></a>

Du kan använda enkättidsplaner för att generera flera planerade svarsomgångar för ett antal användare, baserat på en referenstyp. Skapa ett schema på sidan **Enkättidsplaner**. Välj planeringstyp för att kategorisera schemat, och välj även den referenstyp som ska användas för att ställa frågor i systemet för enskilda användare. Om du anger referenstypen som tabellen Kurser, kan du exempelvis välja en viss kurs i fältet **Referens**. 

Klicka på **Inställningsdetaljer** om du vill välja enkäten och andra kriterier. Ange exempelvis namnet på läraren som ett kriterium om enkäten utgör en utvärdering av instruktören. När du är klar med att ange inställningsinformationen, genererar systemet planerade svarsomgångar för de användare som deltar i enkäten. 

Klicka på **Planerade svarsomgångar** om du vill visa svarsomgången för tidsplanen. Därefter kan du manuellt skapa ytterligare planerade svarsomgångar eller ta bort planerade svarsomgångar som inte har besvarats. 

Klicka på **Funktioner** &gt; **Start** för att göra enkäten tillgänglig för användarna i relaterade planerade svarsomgångar. Klicka på **Svar** om du vill visa de ifyllda svaren på enkäten. Du kan också kopiera enkätens tidsplaninställningar, planerade svarsomgångar och svaren till en ny enkättidsplan.

## Meddela svarande om enkäter som är tillgängliga för dem
<a id="notifying-respondents-about-questionnaires-that-are-available-to-them" class="xliff"></a>
När du distribuerar en enkät måste du meddela svarande att enkäter finns tillgängliga för dem. 

**Obs!** De svarande måste vara användare i Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition för att fylla i en enkät.

### Meddela svarande om en planerad svarsomgång
<a id="notifying-respondents-about-a-planned-answer-session" class="xliff"></a>

Om du använder en planerad svarsomgång måste du meddela personen direkt, till exempel per telefon eller e-post.

### Meddela svarande om en planering
<a id="notifying-respondents-about-a-scheduling" class="xliff"></a>

Använd sidan **Tidsplaner för enkäter** för att förbereda och skicka ett e-postmeddelande till alla svarande som är kopplade till enkäten. Skriv in e-postmeddelandets text på fliken **E-post för medarbetarsjälvbetjäning**. När du har startat schemat klickar du på **Funktioner** &gt; **Skicka e-post** för att generera och skicka e-postmeddelandet till de svarande. De svarande kan sedan logga in på webbplatsen och fylla i enkäten. 

**Anm.:** Innan du kan använda e-postfunktionen måste din IT-administratör ange e-postinställningarna på sidan **E-postparametrar**.

## Avsluta en tidsplanerad enkät
<a id="ending-a-scheduled-questionnaire" class="xliff"></a>
Du kan avsluta en tidsplanerad enkät när alla svaranden har avslutat sina tilldelade svarsomgångar. När planerad enkät slutförs kan du inte kopiera inställningarna till en ny tidsplan. 

**Anm.:** Om en eller flera svarande inte har fyllt i enkäten och du fortfarande vill avsluta tidsplanen måste du först radera dessa svarande från listan på sidan **Planerad svarsomgång**. Sedan kan du avsluta tidsplanen.

## Fylla i enkäter
<a id="completing-questionnaires" class="xliff"></a>
När du har utformat och har fördelat en enkät kan den besvaras av valda svarande. Du kan fylla i de tillgängliga frågeformulären från två platser:

-   I navigeringsfönstret klickar du på **Enkäter** &gt; **Fördela** &gt; **Fyll i en enkät**.
-   Klicka på **Enkäter att fylla i** i Medarbetarsjälvbetjäning.

Enkäter kan göras tillgängliga för vissa användare eller grupper av användare eller för alla användare i ett nätverk.

Se även
<a id="see-also" class="xliff"></a>
--------

[Utforma enkäter](design-questionnaires.md)

[Använda enkäter](questionnaires.md)

[Visa och utvärdera resultaten av en enkät](evaluate-questionnaire-results.md)


