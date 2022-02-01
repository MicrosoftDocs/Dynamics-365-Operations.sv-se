---
title: Dynamics 365 Human Resources infrastrukturkoppling – version 10.0.25 uppdatering
description: Det här ämnet ger information om Microsoft Dynamics 365 Human Resources version 10.0.25, som för den första utgivningscykel av funktioner i infrastrukturkopplingen.
author: twheeloc
ms.date: 01/19/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-27
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ec6d47c44136f7a105a702358370dd676d9339c1
ms.sourcegitcommit: 96f936267d3f314f06da6ce6f809eba2ec3b205f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/24/2022
ms.locfileid: "8018358"
---
# <a name="dynamics-365-human-resources-infrastructure-merge---release-10025-update"></a>Dynamics 365 Human Resources infrastrukturkoppling – version 10.0.25 uppdatering

Version 10.0.25 ger den första utgivningscykeln av möjligheter i infrastrukturkopplingen. Under nfrastrukturkopplingen sammanfogas Microsoft Dynamics 365 Human Resources med infrastrukturerna Ekonomi och Drift. Den kommer dock att fortsätta att vara licensierad som ett oberoende program, som Dynamics 365 Finance och Dynamics 365 Supply Chain Management. Mer information om infrastrukturkopplingen finns i [vanliga frågor om Dynamics 365 Human Resources infrastrukturkoppling](../human-resources/hr-infrastructure-merge-faq.md).

Kopplingen blir konsekvent för Personal-användare på följande sätt:

- [Miljöhantering och -integrationer är konsekventa mellan programmen Personal och Ekonomi och Drifter.](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/consistent-environment-management-integrations-between-human-resources-finance-operations-apps)

    - Hantera miljöer i Microsoft Dynamics Lifecycle Services, problemsökning och Regression Suite Automation Tool.
    - Det finns en kodbas där nya funktioner för Personal släpps som en del av den vanliga uppdateringsprocessen för en version.
    - Det sätt som uppgraderar, uppdaterar och snabbkorrigeringar används i miljön är konsekvent.

- [Utbyggbarhetsalternativen förbättras.](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/improve-extensibility-options.md)

    - Du kan fortsätta att använda Microsoft Power Platform Tools och utöka efter behov.
    - Du kan utöka funktioner via formulär, register, metoder och API (Application Programming Interfaces).
    - Du kan skapa och utöka enheter.

    Mer information om tillgängliga filnamnstillägg finns i [Översikt över utvidgningar i Dynamics 365](../fin-ops-core/dev-itpro/extensibility/extensibility-home-page.md).

- [Skapa en uppsättning med personalfunktioner i Dynamics 365.](/dynamics365-release-plan/2021wave2/human-resources/create-one-set-human-resources-capabilities-within-dynamics-365.md)

    I versionen 10.0.25 har funktionella funktioner som endast finns i Personal gjorts tillgängliga i infrastruktur för Ekonomi och Drift. För att kunderna ska kunna dra nytta av den här kapaciteten i en Ekonomi och Drift-miljö måste följande personalfunktioner vara aktiverade i Funktionshantering.

    | Funktionsnamn | Översikt | Frisläppningsstatus | 
    |--------------|----------|----------------| 
    | Beräkning av antal tjänsteår | Med hjälp av ett inställningsalternativ kan du välja det datum som ska användas för beräkningen av **tjänsteår**. | Allmänt tillgängligt | 
    | Förbättringar av arbetsflöden | Den här funktionen ger en förbättrad användarupplevelse för arbetsflödesskick och godkännanden. | Allmänt tillgängligt | 
    | Skriv ut prestationsgranskningar | Du kan skriva ut prestandagranskningar i PDF-format. | Allmänt tillgängligt | 
    | Anpassade länkar i **Självbetjäning för chef** | Du kan skapa anpassade länkar som visas i avsnittet **Relaterade länkar** i **Självbetjäning för chef**. | Allmänt tillgängligt | 
    | Kompensationsvy för korsföretag | Användarna kan visa kompensationsplaner i **självbetjäning för chef** för alla juridiska personer, utan att behöva byta företag. | Allmänt tillgängligt | 
    | Konfigurera flera kompensationsnivåer efter jobb\*&dagger; | Jobb har nu stöd för flera kompensationsnivåer. | Allmänt tillgängligt | 
    | Uppgiftshantering\* | Du kan skapa checklistor och uppgifter för registrering, avregistrering och övergångsperiod. | Förhandsgranska | 
    | Strömlinjeformad medarbetarinmatning | Med den här funktionen får du uppdaterad användarupplevelse på den befintliga sidan **arbetare**. | Förhandsgranska | 
    | Förbättringar av personalavdelningens användarupplevelse | Se registret i nästa avsnitt.  | Förhandsgranska | 

\* Den här funktionen måste vara aktiverad innan funktionen **användarupplevelse för personalfunktionen** kan aktiveras.

&dagger; Denna funktion kan inte inaktiveras när du har aktiverat dem.

## <a name="human-resource-user-experience-enhancements"></a>Förbättringar av användarupplevelse för personal

| Funktionsnamn | Översikt | 
|--------------|----------| 
| Ta bort anställning | Du kan ta bort en anställning för en medarbetare. | 
| Jobbgrupper | Du kan spåra en grupp av jobb som inbegriper liknande arbete och som kräver liknande utbildning, färdigheter, kunskap och expertis. | 
| Ytterligare sysselsättningsfält | Följande fält läggs till: **Anställningskategori**, **Anställningstyp** och **Anställningsstatus**.  | 
| Sidan **Arbetare utan anställning** | På en sida visas en lista med arbetare som inte har någon anställningspost. | 
| Uppdatering av användarupplevelse för befattningsdimension | Det finns en förbättrad användarupplevelse för tilldelning av befattningsdimensioner per juridisk person. | 
| Adress ändras i arbetsytan **personalhantering** | Denna funktion innehåller en sammanställning av alla adressändringar som gjorts under ett visst antal dagar som definieras på sidan **Personalparametrar**. | 
| Utgående poster i arbetsytan **personalhantering** | Den här funktionen tillhandahåller en lista över föremål som har löpt ut eller kommer att upphöra att gälla för certifikat, identifiering, prövning, undersökningar eller tester. | 
| Sidan **Validering av befattningshierarki** | En kontroll görs av cirkulära referenser i positionradshierarkin. | 
| Landsspecifik löneinformation | Ytterligare lönefält är tillgängliga på sidan **Arbetarens anställning** beroende på land eller region för den juridiska person där arbetarna är anställda. | 
| Förbättringar av efterföljanderapportering | Fler rapporteringsalternativ finns för EEO-1, Vets 4212 och OSHA300a. | 
| Uppdatera arbetsytan **Personalhantering** | Uppdateringar har gjorts för att spåra adressändringar och utgångsposter. Nya flikar visar dessutom arbets- och befattningsåtgärder. | 
