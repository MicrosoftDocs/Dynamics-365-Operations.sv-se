---
title: Schemalägg och skicka ut enkäter
description: Den här artikeln beskriver hur du fördelar de enkäter som du utformar så att de blir tillgängliga för den person eller grupp som ska fylla i dem.
author: andreabichsel
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: KMConnectionType, KMKnowledgeCollectorPlanningTabel, SysEmailParameters
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.custom: 17424
ms.assetid: fd8d867a-2446-400a-b91f-ad4085427470
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bc392c965a0d3bc308e0396263e84ecf1e713491
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/06/2019
ms.locfileid: "2898373"
---
# <a name="distribute-and-schedule-questionnaires"></a>Schemalägg och skicka ut enkäter

Den här artikeln beskriver hur du fördelar de enkäter som du utformar så att de blir tillgängliga för den person eller grupp som ska fylla i dem. 

Det finns flera sätt att distribuera en enkät:

-   Markera enkäten som aktiv. Enkäten är då tillgänglig för alla medarbetare, om inte en enkätgrupp har ställts in för att begränsa åtkomst till den.
-   Tilldela rättigheter till en enkätgrupp. Enkäten är då tillgänglig för alla medlemmar i den valda gruppen.
-   Skapa planerade svarsomgångar. Enkäten är då endast tillgänglig för en viss person.
-   Skapa en tidsplan. Enkäten kan sedan vara tillgänglig för flera personer.

## <a name="marking-a-questionnaire-as-active"></a>Markera en enkät som aktiv.
Genom att ange fältet **Aktiv** som **Ja** på sidan **Enkäter** kan du göra enkäten tillgänglig för alla medarbetare. De svarande kan fylla i formuläret flera gånger. Denna funktion är användbar om du vill samla in feedback kontinuerligt under hela året. Du kan till exempel göra en enkät där anställda ger feedback om lunchtjänsten i kafeterian.

## <a name="questionnaire-groups"></a>Enkätgrupper
Du kan ställa in enkätgrupper och sedan inkludera de svarande som ett frågeformulär ska distribueras till. 

Du kan skapa enkätgrupper på följande sidor:

-   **Enkätgrupper**– Endast personer i en enkätgrupp kan avsluta en vald enkät. Till exempel om din målgrupp är leverantörer, då skapar du en enkätgrupp som är specifik för dessa svarande.
-   **Enkätgruppsmedlemmar** – Du kan lägga till kontakter till enkätgrupperna.

På sidan **Enkäter** klickar du på **Användarrättigheter** för att tilldela en enkätgrupp till en enkät. Medlemmarna i enkätgruppen kan fylla i enkäten när enkäten har sparats som aktiv. Denna funktion är användbar om du vill testa en enkät i en utvald grupp användare innan du skickar ut den till en större grupp, eller om du vill rikta enkäten till en mycket specifik målgrupp.

## <a name="planned-answer-sessions-in-a-questionnaire"></a>Planerade svarsomgångar i en enkät
Planerade svarsomgångar är enkäter som du har utformat för och valt svarande till. 

> [!NOTE]
>   Innan du kan ställa in planerade svarsomgångar måste du utforma en enkät. 

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

Använd sidan **Referenstyper** för att ställa in referenstyper för en enkät. Varje referenstyp motsvarar en tabell i Microsoft Dynamics 365 Finance. När du skapar enkättidsplaner kan du ange de enskilda posterna i tabellen eller ett intervall med poster som enkäten ska associeras med. 

Om du till exempel väljer tabellen Kurser kan du bestämma vilken specifik kurs enkäten ska gälla för. När du ställer in en referens för tabellen Kurser blir alla fält och knappar på sidan **Kurser** tillgängliga.

### <a name="questionnaire-schedules"></a>Tidsplaner för enkäter

Du kan använda enkättidsplaner för att skapa flera planerade svarsomgångar för ett antal användare, baserat på en referenstyp. Skapa ett schema på sidan **Enkättidsplaner**. Välj planeringstyp för att kategorisera schemat, och välj även den referenstyp som ska användas för att ställa frågor i systemet för enskilda användare. Om du anger referenstypen som tabellen Kurser, kan du exempelvis välja en viss kurs i fältet **Referens**. 

Klicka på **Inställningsdetaljer** om du vill välja enkäten och andra kriterier. Ange exempelvis namnet på läraren som ett kriterium om enkäten utgör en utvärdering av instruktören. När du är klar med att ange inställningsinformationen, skapar systemet planerade svarsomgångar för de användare som deltar i enkäten. 

Klicka på **Planerade svarsomgångar** om du vill visa svarsomgången för tidsplanen. Därefter kan du manuellt skapa ytterligare planerade svarsomgångar eller ta bort planerade svarsomgångar som inte har besvarats. 

Klicka på **Funktioner** &gt; **Start** för att göra enkäten tillgänglig för användarna i relaterade planerade svarsomgångar. Klicka på **Svar** om du vill visa de ifyllda svaren på enkäten. Du kan också kopiera enkätens tidsplaninställningar, planerade svarsomgångar och svaren till en ny enkättidsplan.

## <a name="notifying-respondents-about-questionnaires-that-are-available-to-them"></a>Meddela svarande om enkäter som är tillgängliga för dem
När du distribuerar en enkät måste du meddela svarande att enkäter finns tillgängliga för dem. 

### <a name="notifying-respondents-about-a-planned-answer-session"></a>Meddela svarande om en planerad svarsomgång

Om du använder en planerad svarsomgång måste du meddela personen direkt, till exempel per telefon eller e-post.

### <a name="notifying-respondents-about-a-scheduling"></a>Meddela svarande om en planering

Använd sidan **Tidsplaner för enkäter** för att förbereda och skicka ett e-postmeddelande till alla svarande som är kopplade till enkäten. Ange e-posttexten på fliken **E-postadress för självbetjäning för medarbetare**. När schemat har startats klickar du på **Funktioner** &gt; **Skicka e-post** för att skapa och skicka mailet till mottagarna. De svarande kan sedan logga in på webbplatsen och fylla i enkäten. 

> [!NOTE]
>   Innan du kan använda e-postfunktionen måste din IT-administratör ange e-postinställningarna på sidan **E-postparametrar**.

## <a name="ending-a-scheduled-questionnaire"></a>Avsluta en tidsplanerad enkät
Du kan avsluta en tidsplanerad enkät när alla svaranden har avslutat sina tilldelade svarsomgångar. När planerad enkät slutförs kan du inte kopiera inställningarna till en ny tidsplan. 

> [!NOTE]
>   Om en eller flera svarande inte har fyllt i enkäten och du fortfarande vill avsluta tidsplanen måste du först radera dessa svarande från listan på sidan **Planerad svarsomgång**. Sedan kan du avsluta tidsplanen.

## <a name="completing-questionnaires"></a>Fylla i enkäter
När du har utformat och har fördelat en enkät kan den besvaras av valda svarande. Du kan fylla i de tillgängliga frågeformulären från två platser:

-   I navigeringsfönstret klickar du på **Enkäter** &gt; **Fördela** &gt; **Fyll i en enkät**.
-   Klicka på **Enkäter att fylla i** i Medarbetarsjälvbetjäning.

Enkäter kan göras tillgängliga för vissa användare eller grupper av användare eller för alla användare i ett nätverk.

<a name="additional-resources"></a>Ytterligare resurser
--------

[Utforma enkäter](design-questionnaires.md)

[Enkäter](questionnaires.md)

[Visa och utvärdera resultaten av enkäter](evaluate-questionnaire-results.md)


