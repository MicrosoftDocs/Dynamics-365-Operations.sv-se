---
title: Arbetsyta för checklista för datavalidering
description: Arbetsytan checklista för datavalidering låter dig spåra processer för validering av data mellan företag, områden och personer. Checklistan kan användas under en ny implementering efter uppgradering eller efter en migrering.
author: bking
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: DataValidationWorkspace
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.assetid: ''
ms.search.region: Global
ms.author: bking
ms.openlocfilehash: 5b014f10d3ca6183fd6c26373a72213ad4c0dda5
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/02/2019
ms.locfileid: "1851209"
---
# <a name="data-validation-checklist-workspace"></a>Arbetsyta för checklista för datavalidering

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller en översikt över arbetsytan **Checklista för datavalidering** och den associerade konfigurationen.

Arbetsytan **checklista för datavalidering** låter dig spåra processer för validering av data mellan företag, områden och personer. Checklistan kan användas under en ny implementering efter uppgradering eller efter en migrering. Beroende på din vy över arbetsytan **Checklista för datavalidering** visas antingen alla uppgifter och status för ett datavalideringsprojekt eller enbart de aktiviteter som har tilldelats dig.

Du måste först markera ett datavalideringsprojekt överst på arbetsytan. Alla data som visas på arbetsytan filtreras sedan genom det markerade datavalideringsprojektet.

## <a name="summary-tiles"></a>Sammanfattningsrutor

Panelerna **Sammanfattning** ger dig en översikt över processen, och diverse indikeringar hjälper dig att styra datavalideringsprocessen. Du kan se samtliga återstående uppgifter, slutförda uppgifter, pågående uppgifter och ännu ej startade uppgifter för processen. Denna information används för alla företag som ingår i det markerade, datavalideringsprojektet.

## <a name="tasks-and-status-section"></a>Avsnittet Uppgifter och status

I avsnittet **uppgifter och status** visas status på det övergripande datavalideringsprojektet på olika sätt: status efter juridisk person, efter område och efter uppgiftslista. Du kan välja filter för att visa status för ett specifikt företag. Varje statusflik tillhandahåller en uppdelning efter såväl slutförd procent och hur många uppgifter som återstår.

Den sista fliken är för den detaljerade uppgiftslistan. I listan visas hela uppgiftslistan.
Du kan filtrera uppgiftslistan på flera sätt. Klicka på **Redigera uppgift** för att ändra status för en uppgift eller tilldela en uppgift. Klicka på **bilagor** att visa bilagor för en uppgift.

Aktivitetens namn är en hyperlänk till sidan för Microsoft Dynamics 365 for Finance and Operations dit användaren måste bege sig för att slutföra arbetet. Du kan ange denna hyperlänk genom att använda fälten **Menyalternativnamn** när du redigerar eller skapar en uppgift från formuläret **konfigurera datavalideringsprojekt**.

Du kan bifoga filer, anteckningar, bilder och URL-adresser till en aktivitet med hjälp av åtgärden **Bilagor**. Du kan till exempel koppla en rapportfil som skrevs ut för en uppgift. En ikon syns i kolumnen **Bilaga** för aktiviteten om det finns en bifogad fil.

Alternativet **Slutförd av** fylls i automatiskt när en uppgift med namnet på arbetaren som slutförde uppgiften. När en aktivitet har markerats som slutförd, uppdateras fältet **Datum för slutförande** automatiskt till aktuellt datum och aktuell tid.

## <a name="configure-data-validation-project-page"></a>Konfigurera datavalideringsprojektsidan

Innan du kan använda arbetsytan **checklista för datavalidering** måste du konfigurera processen med sidan **konfigurera datavalideringsprojekt**. (Klicka på **arbetsytor** \>**checklista för datavalidering** \>**konfigurera datavalideringsprojekt**.)

## <a name="task-areas"></a>Uppgiftsområden

Du använder uppgiftområden för att gruppera datavalideringsuppgifter i logiska området baserat på ägarskap i din organisation. Exempelvis kan Leverantörsreskontra, Kundreskontra eller Huvudbok användas som uppgiftområden.

**Menyobjektnamnet** är associerat med uppgiftens arbetsinsats, och kan användas för att gå direkt till motsvarande sida från aktivitetslänken på arbetsytan. Exempelvis en datavalideringsuppgift för att köra rapporten **åldersfördelning i leverantörsreskontra** för leverantörsreskontra kan länkas till sidan **åldersfördelningsrapport för leverantörsreskontra**.
