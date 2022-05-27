---
title: Nyheter och ändringar i Dynamics 365 Human Resources (11 juni 2020)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Human Resources 11 juni 2020.
author: andreabichsel
ms.date: 06/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-06-11
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9d75c4a27ff98f52fff6ec498aded4dfcc031931
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/04/2022
ms.locfileid: "8695800"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-june-11-2020"></a>Nyheter och ändringar i Dynamics 365 Human Resources (11 juni 2020)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Den här artikeln innehåller en beskrivning av nya eller ändrade funktioner i Dynamics 365 Human Resources. Ändringarna tillämpas på versionsnummer 8.1.3316. Siffror inom parenteser i vissa rubriker refererar till LCS-supportnummer för referens.

## <a name="streamlined-employee-form-sometimes-causes-child-form-close-x-buttons-to-stop-working-442369"></a>Ett strömlinjeformat medarbetarformulär ger ibland det underordnade formuläret att stänga (X) knappar för att sluta fungera (442369)

När det nya formuläret **Arbetare** aktiverades fungerade inte stängningsknappen (**X**) ibland i underordnade formulär. Det här problemet var tillfälligt. Du kan stänga formuläret efter att ha lämnat det och sedan komma tillbaka till det. Du kan till exempel välja ett menyalternativ till vänster och navigera tillbaka till formuläret **Arbetare** och stänga det. Det här problemet åtgärdas med den här veckans utgivningsversion. 

## <a name="the-worker-personal-contact-person-entity-doesnt-export-personal-contacts-with-a-parent-relationship-type"></a>Entiteten Personlig kontaktperson för medarbetare exporterar inte personliga kontakter med en överordnad relationstyp

Med den här versionen exporterar entiteten **Personlig kontaktperson för medarbetare** alla relationstyper.

## <a name="the-hcmpositionworkerassignmentv2entity-should-be-part-of-the-ceridian-payroll-integration-package-by-default-448506"></a>HcmPositionWorkerAssignmentV2Entity bör ingå i Ceridian löneintegreringspaket som standard (448506)

Med den här ändringen inkluderas **HcmPositionWorkerAssignmentV2Entity** i Ceridian löneintegreringspaket.

## <a name="in-preview"></a>I förhandsgranskning

## <a name="database-logging"></a>Databasloggning

Med funktionen för databasloggning kan du bestämma vilka register och fält som ska övervakas. Du kan också bestämma vilka händelser som ska utlösa ändringsspårningen. Du använder funktionerna för databasloggning för att visa dessa ändringar över tiden. Mer information finns i [Konfigurera och hantera databasloggning](hr-admin-database-logging.md).

## <a name="human-resources-application-in-teams"></a>Personalapp i Teams

Medarbetare kan visa och begära ledighet från arbetet inom Microsoft Teams. De kan samverka med en bot för att skapa tjänstledighetsansökan. Mer information finns [i personalapp i Teams](./hr-admin-teams-leave-app.md). 

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a>DMF-enheter (Data Management Framework) för förmånshantering
 
Entiteter för hantering av förmåner släpps. DMF-enheter gör det möjligt att importera och exportera data för att enkelt konfigurera hantering av förmåner. En mall för hantering av förmåner kan användas för att flytta data. Mallen exporterar och importerar data sekventiellt för att respektera databeroenden.

## <a name="buy-and-sell-leave"></a>Köpa och sälja tjänstledighet 

Vissa organisationer ger en förmån som gör det möjligt för medarbetare att köpa eller sälja sin tjänstledighet. Den här processen hanteras ofta manuellt. Med den här funktionen automatiseras hanteringen av principer och begäranden för personalavdelningen. Det effektiviserar hanteringsprocessen och hjälper till att eliminera misstag. Mer information finns i:

- [Hantera principer för köpa och sälja tjänstledighet](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [Köpa och sälja tjänstledighet](hr-employee-self-service-buy-sell-leave.md)

## <a name="leave-accrual-for-a-single-company-or-single-plan"></a>Lämna periodisering för ett enskilt företag eller en plan

Kunder kan bearbeta periodiseringar för ett enskilt företag eller en enskild plan för tjänstledighet och frånvaro. Denna möjlighet ger klarhet i den periodiserade processen för kunder med olika tjänstledighetsår eller principer för periodisering av tjänstledighet. Mer information finns i [tjänstledighet per företag eller per tjänstledighetsplan](hr-leave-and-absence-accrue.md).

## <a name="add-attachments-to-time-off-requests"></a>Lägg till bifogade filer i ledighetsansökningar

Möjligheten att lägga till bilagor till godkända ansökan om tjänstledighet är viktigt i den aktuella COVID-19 miljön. Medarbetarna kan nu lägga till dessa bilagor. De har också mer inblick i hur uppdateringar görs för att lämna förfrågningar. Mer information finns i [lägga till en bilaga till en befintlig begäran](hr-employee-self-service-request-time-off.md#add-an-attachment-to-an-existing-request).

## <a name="add-reason-code-to-accrual-suspensions"></a>Lägg till orsakskod för periodiserade avstängningar 

Orsakskoder har lagts till den periodiserade avstängningen.

## <a name="carry-forward-rules"></a>Överför regler 

Du kan ange en överför tjänstledighetstyp för överföringsaldon där överför justeringar överförs. Om en medarbetare till exempel överförs 10 dagar kan du välja en annan tjänstledighetstyp för de 10 dagarna. Mer information finns i [konfigurera tjänstledighet och frånvarotyper](hr-leave-and-absence-types.md).

## <a name="suspend-leave-accrual-for-specified-leave-types"></a>Pausa tjänstledighetsperiodisering för angivna tjänstledighetstyper

Du kan skapa en regel för att pausa tjänstledighetsperiodiseringar för medarbetare som har lämnat förfrågningar om obetald tjänstledighet. Obetald tjänstledighet kan vara en typ, men behöver inte vara det. Du kan pausa eventuell tjänstledighet baserat på annan tjänstledighetstyp.

## <a name="dmf-entity-available-for-accrual-suspensions"></a>DMF-enhet tillgänglig för periodiserade avstängningar 

Nu är en DMF-enhet tillgänglig för periodiserade avstängningar.

## <a name="coming-soon"></a>Kommer snart

## <a name="new-platform-capabilities"></a>Nya plattformsfunktioner 

Du kan göra fält obligatoriska genom att använda anpassningar. Den här funktionen kräver att du aktiverar **sparade vyer**.

## <a name="configure-the-name-of-employee-self-service"></a>Konfigurera namnet på självbetjäning för medarbetare

Ett nytt alternativ är tillgängligt i personalparametrarna för att uppdatera namnet på arbetsytan självbetjäning för medarbetare till självbetjäning. 

## <a name="see-also"></a>Se även

[Nyheter och ändringar i Personal](hr-admin-whats-new.md)</br>
[Översikt över Dynamics 365 Human Resources 2019 utgivningsvåg 2](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Uppdatera process](hr-admin-setup-update-process.md)</br>
[Hantera funktioner](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]