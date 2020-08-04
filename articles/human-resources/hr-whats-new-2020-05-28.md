---
title: Nyheter och ändringar i Dynamics 365 Human Resources (28 maj 2020)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Human Resources.
author: Darinkramer
manager: AnnBe
ms.date: 05/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2020-05-28
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 7664afbd0b1fd4e2c9686053fa102d85809c0411
ms.sourcegitcommit: bd9ff0d28718d535356ffbe1cffaaf60310dd430
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/13/2020
ms.locfileid: "3555325"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-may-28-2020"></a>Nyheter och ändringar i Dynamics 365 Human Resources (28 maj 2020)

Det här ämnet beskriver nya eller ändrade funktioner i Dynamics 365 Human Resources. Ändringarna tillämpas på versionsnummer 8.1.3287. Siffror inom parenteser i vissa rubriker refererar till LCS-supportnummer för referens.

## <a name="leaverequest-entity-doesnt-work-when-you-enable-multiple-types-per-leave-plan-447498"></a>LeaveRequest-entitet fungerar inte när du aktiverar flera typer per tjänstledighetsplan (447498)

Med den här ändringen är **LeaveEnrollmentV2Entity** nu tillgänglig för att korrigera det fel som uppstår när du aktiverar flera tjänstledighetstyper.

## <a name="batch-contention-reduction-feature-preview-446619"></a>Funktionen för minskning av batch-konkurrens (förhandsgranskning) (446619)

När du aktiverar den här funktionen kan du förvänta dig en minskning av blockeringen på batch-ramverkstabeller när du väljer uppgifter och slutför jobb.

## <a name="updateconflict-while-saving-worker-prevents-editing-a-record-in-people-427915"></a>UpdateConflict medan du sparar arbetare förhindrar redigering av en post i personer (427915)

Den här ändringen korrigerar ett fel när en ny arbetare läggs till, uppdatering av adressinformation och ändring av språkinställningar görs. I det unika scenariot visas ett fel som anger att posten inte kunde uppdateras. 

## <a name="unable-to-add-an-attachment-to-an-approved-leave-request-to-resubmit-425407"></a>Det går inte att lägga till en bilaga till en godkänd tjänstledighetsansökan som ska skickas in på nytt (425407)

Denna ändring tillåter nu bilagor till godkända tjänstledighetsansökningar.

## <a name="user-can-enter-compensation-for-an-employee-in-a-different-legal-entity-form-409529"></a>Användaren kan ange kompensation för en medarbetare i ett annat formulär för juridisk person (409529)

Denna ändring inaktiverar kompensationsalternativ för att förhindra oavsiktlig registrering av kompensationsposter för fel juridisk person.

## <a name="error-when-you-transfer-an-employee-and-the-worker-position-assignment-date-is-before-the-position-duration-429402"></a>Fel när du överför en medarbetare och datumet för tilldelningsarbetarposition är före positionen varaktighet (429402)

Felmeddelanden vid överföring av en medarbetare i det här scenariot har uppdaterats för att bättre beskriva de ändringar som är nödvändiga för att rätta till problemet.

## <a name="attachments-capabilities-in-employee-self-service-benefits-enrollment"></a>Bilagefunktioner i registrering av självbetjäningen för medarbetarens förmåner
 
Nu kan du lägga till bilagor under förmånsregistreringsprocessen för varje plan som medarbetaren registrerar sig i. Du kan sedan visa bilagorna i formuläret **Förmåner som arbetaren är anmäld till**.

## <a name="in-preview"></a>I förhandsgranskning

## <a name="human-resources-application-in-teams"></a>Personalapp i Teams

Medarbetare kan visa och begära ledighet från arbetet inom Microsoft Teams. De kan samverka med en bot för att skapa tjänstledighetsansökan. Mer information finns [i personalapp i Teams](https://go.microsoft.com/fwlink/?linkid=2127841). 

## <a name="leave-suspension"></a>Lämna uppehåll

Du kan skjuta upp tjänstledighet och frånvaro i personal för en medarbetare. Om du skjuter upp tjänstledighet avbryts tjänstledigheten för de valda tjänstledighetstyperna. Om indraget sker efter att en periodisering har bearbetats, skapar skjuta upp ledighet en proportionell justering av medarbetarens ledighetssaldo. Mer information finns i [Skjut upp tjänstledighet](hr-leave-and-absence-suspend-leave.md).

## <a name="update-user-experience-to-indicate-that-accrual-is-suspended-429550"></a>Uppdatera användarupplevelsen att anger att periodiseringen är pausad (429550)

Användarupplevelsen anger nu att periodiseringen har avbrutits för en plan.

## <a name="coming-soon"></a>Kommer snart

## <a name="database-logging-in-preview-in-june"></a>Databasloggning (i förhandsgranskning i juni)

Med funktionen för databasloggning kan du bestämma vilka register och fält som ska övervakas. Du kan också bestämma vilka händelser som ska utlösa ändringsspårningen. Förfrågankapacitet kan visa dessa ändringar med tiden.

## <a name="buy-and-sell-leave-in-preview-june-1"></a>Köpa och sälja tjänstledighet (i förhandsversion 1 juni)

Vissa organisationer ger en förmån som gör det möjligt för medarbetare att köpa eller sälja sin tjänstledighet. Den här processen hanteras ofta manuellt. Med hjälp av den här funktionen kan du på ett mer automatiserat sätt hantera policyer och förfrågningar för personalavdelningen och ta bort misstag samtidigt som du effektiviserar hanteringsprocessen. Mer information finns i:

- [Hantera principer för köpa och sälja tjänstledighet](hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [Köpa och sälja tjänstledighet](hr-employee-self-service-buy-sell-leave.md)

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a>DMF-enheter (Data Management Framework) för förmånshantering
 
Entiteter för hantering av förmåner släpps. DMF-enheter gör det möjligt att importera och exportera data för att enkelt konfigurera hantering av förmåner. En mall för hantering av förmåner kan också användas för att flytta data. Mallen exporterar och importerar data på ett sekventiellt sätt för att respektera databeroenden.

## <a name="add-reason-code-to-accrual-suspensions-june-1"></a>Lägg till orsakskod för periodiserade avstängningar (1 juni)

Orsakskoder har lagts till den periodiserade avstängningen.

## <a name="carry-forward-rules-june-1"></a>Överför regler (1 juni)

Du kan ange en överför tjänstledighetstyp för överföringsaldon där överför justeringar överförs. Om en medarbetare till exempel överförs 10 dagar kan du välja en annan tjänstledighetstyp för de 10 dagarna. Mer information finns i [konfigurera tjänstledighet och frånvarotyper](hr-leave-and-absence-types.md).

## <a name="suspend-leave-accrual-for-specified-leave-types-june-1"></a>Pausa tjänstledighetsperiodisering för angivna tjänstledighetstyper (1 juni)

I den här versionen kan HR skapa en regel för att pausa tjänstledighetsperiodiseringar för medarbetare som har lämnat förfrågningar om obetald tjänstledighet. Obetald tjänstledighet kan vara en typ, men behöver inte vara det. Du kan pausa eventuell tjänstledighet baserat på annan tjänstledighetstyp.

## <a name="dmf-entity-available-for-accrual-suspensions-june-1"></a>DMF-enhet tillgänglig för periodiserade avstängningar (1 juni)

Nu är en DMF-enhet tillgänglig för periodiserade avstängningar.

## <a name="see-also"></a>Se även

[Nyheter och ändringar i Human Resources](hr-admin-whats-new.md)</br>
[Översikt över Dynamics 365 Human Resources 2019 utgivningsvåg 2](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Uppdatera process](hr-admin-setup-update-process.md)</br>
[Hantera funktioner](hr-admin-manage-features.md)