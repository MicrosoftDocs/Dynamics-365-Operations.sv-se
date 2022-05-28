---
title: Nyheter och ändringar i Dynamics 365 Human Resources (06 augusti 2020)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Human Resources 6 augusti 2020.
author: andreabichsel
ms.date: 08/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-08-06
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: a8058c1acdde20a1b48130fa1e8b75aa415bafce
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/04/2022
ms.locfileid: "8691986"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-august-06-2020"></a>Nyheter och ändringar i Dynamics 365 Human Resources (06 augusti 2020)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Det här ämnet beskriver nya eller ändrade funktioner i Dynamics 365 Human Resources. Ändringarna tillämpas på versionsnummer 8.1.3444. Siffror inom parenteser i vissa rubriker refererar till LCS-supportnummer för referens.

## <a name="platform-update-1001236-is-now-available"></a>Plattformsuppdateringen 10.0.12(36) finns nu tillgänglig.

Mer information finns i [Plattformsuppdateringar för version 10.0.12 av Ekonomi och Drift-appar (augusti 2020)](../fin-ops-core/dev-itpro/get-started/whats-new-platform-update-10-0-12.md).

## <a name="data-management-framework-dmf-entities-for-benefits-management"></a>DMF-enheter (Data Management Framework) för förmånshantering
 
Entiteter för hantering av förmåner släpps. DMF-enheter gör det möjligt att importera och exportera data för att enkelt konfigurera hantering av förmåner. En mall för hantering av förmåner kan användas för att flytta data. Mallen exporterar och importerar data sekventiellt för att respektera databeroenden. Mer information finns i:

- [Stöd för DMF-entitet](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/dmf-entity-support) i Dynamics 365 2020 utgivningsvåg 1-planen
- [Översikt över datahantering](../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md)


## <a name="claire-creates-a-workflow-for-buying-and-selling-leave-requests-446557"></a>Claire skapar ett arbetsflöde för att köpa och sälja begäranden om ledighet (446557)

Mer information finns i:

- [Tillåt medarbetare att köpa och sälja sin ledighet](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/allow-employees-buy-sell-leave) i Dynamics 365 2020 utgivningsvåg 2-planen
- [Hantera principer för köpa och sälja tjänstledighet](./hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [Köpa och sälja tjänstledighet](./hr-employee-self-service-buy-sell-leave.md)


## <a name="worker-postal-addresses-v2-entity-has-access-across-legal-entities-with-restricted-access-459126"></a>Entiteten adress till arbetare till postadress V2 har åtkomst över juridiska entiteter med begränsad åtkomst (459126)

Med den här ändringen begränsas entiteten **arbetare till postadress V2** baserat på åtkomsten till den juridiska personen som ges till användaren.

## <a name="workflow-email-hyperlink-fails-to-open-relevant-reviews-437398"></a>Hyperlänken för e-post för arbetsflödet kunde inte öppna relevanta recensioner (437398)

När du använder platshållaren för att öppna en resultatöversyn i granskningsarbetsflöde öppnar hyperlänken som skapas i e-postmeddelandet den valda posten.

## <a name="new-entities-for-buying-and-selling-leave-473180"></a>Nya entiteter för köpa och sälja ledighet (473180)

Entiteter för ramverk för datahantering finns nu tillgängliga för att köpa och sälja tjänstledighet. Mer information finns i [Översikt över datahantering](../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md).

## <a name="when-viewing-record-information-and-using-advanced-filters-a-user-could-gain-access-to-other-employees-records-472490"></a>När en användare visar postinformation och använder avancerade filter kan han eller hon få tillgång till andra medarbetares poster (472490)

Med den här ändringen kan medarbetare självbetjäningsanvändare bara komma åt sina egna poster när de använder självbetjäning för medarbetare. Att visa informationen medan du ändrar filtreringsalternativet visar inte längre ytterligare data.

## <a name="personnel-management-analytics-include-exited-worker-records-382893"></a>Analys av personalhantering inkluderar uppsägda medarbetarposter (382893)

Med den här versionen inkluderar personalhanterings analys nu endast aktiva arbetare. 
 
## <a name="unable-to-process-a-merit-increase-for-an-employee-473125"></a>Det går inte att bearbeta en meritökning för en medarbetare (473125)

Den här ändringen gör att du kan ange meritökningar när du ändrar giltighets datumet för den nya meritökningen.

## <a name="review-workflow-can-be-started-more-than-once-467541"></a>Granska arbetsflödet kan startas mer än en gång (467541)

Med den här ändringen kan du bara starta arbetsflödet för prestanda granskning en gång. Statusen för chefen visar inte längre alternativet att påbörja granskningen.

## <a name="leave-request-work-flow-ends-in-error-when-canceling-an-approved-leave-request-472063"></a>Arbetsflödet för begäran av ledighet i fel när en godkänd tjänstledighetsbegäran avbryts (472063)

När du avbryter en godkänd tjänstledighetsbegäran i den här versionen, förblir status för begäran inte längre godkänd och arbetsflödet kommer att fortsätta.

## <a name="system-suggests-exited-workers-when-creating-a-new-review-form-the-template-460624"></a>Systemet föreslår avslutade arbetare när en ny granskning skapas från mallen (460624)

Med den här ändringen är avslutade arbetare längre tillgängliga när nya recensioner skapas från en mall. Du kan inte skapa recensioner för medarbetare som ligger utanför datumen för deras anställning.

## <a name="position-hierarchy-circular-reference-detection-415879"></a>Cirkelreferens avkänning för befattningshierarki (415879)

Med den här ändringen begränsas cirkelreferens identifieringen för positionshierarki till en enskild tidpunkt. Du kan köra en cirkelreferens identifiering för olika datum för att kontrollera att rapportstrukturen inte har några cirkelreferenser.

## <a name="buy-and-sell-leave"></a>Köpa och sälja tjänstledighet 

Vissa organisationer ger en förmån som gör det möjligt för medarbetare att köpa eller sälja sin tjänstledighet. Den här processen hanteras ofta manuellt. Med den här funktionen automatiseras hanteringen av principer och begäranden för personalavdelningen. Det effektiviserar hanteringsprocessen och hjälper till att eliminera misstag. Mer information finns i:

- [Tillåt medarbetare att köpa och sälja sin ledighet](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/allow-employees-buy-sell-leave) i Dynamics 365 2020 utgivningsvåg 2-planen
- [Hantera principer för köpa och sälja tjänstledighet](./hr-leave-and-absence-manage-buy-and-sell-leave-policies.md)
- [Köpa och sälja tjänstledighet](./hr-employee-self-service-buy-sell-leave.md)

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

## <a name="in-preview"></a>I förhandsgranskning

### <a name="mandatory-fields"></a>Obligatoriska fält

Du kan göra fält obligatoriska genom att använda anpassningsfunktioner för personal. Den här funktionen kräver **sparade vyer**. Mer information om sparade vyer, se.

- [Sparade vyer-allmän tillgänglighet](/dynamics365-release-plan/2020wave2/finance-operations/finance-operations-crossapp-capabilities/saved-views--general-availability) i Dynamics 365 2020 utgivningsvåg 2-plan
- [Skapa formulär som fullt ut utnyttjar sparade vyer](../fin-ops-core/dev-itpro/user-interface/understanding-saved-views.md)

### <a name="human-resources-application-in-teams"></a>Personalapp i Teams

Medarbetare kan visa och begära ledighet från arbetet inom Microsoft Teams. De kan samverka med en bot för att skapa tjänstledighetsansökan. Mer information finns i:

- [Erfarenhet av medarbetares ledighet och frånvaro i Microsoft Teams](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) i Dynamics 365 2020 utgivningsvåg 1-planen
- [Personal-app i Teams](./hr-admin-teams-leave-app.md)

### <a name="dmf-entity-available-for-accrual-suspensions"></a>DMF-enhet tillgänglig för periodiserade avstängningar

Nu är en DMF-enhet tillgänglig för periodiserade avstängningar.

## <a name="coming-soon"></a>Kommer snart

## <a name="checklist-entities-included-in-dataverse"></a>Entiteter för checklista inkluderade i Dataverse

Entiteter för checklista för registrering, offboard, överföringar och affärsprocesser kommer snart att vara tillgängliga i Dataverse.

## <a name="known-issues"></a>Kända problem

Arbetsytan **funktionshantering** visas funktioner som har inaktiverats som förhandsgranskningsfunktioner när de är allmänt tillgängliga. Nedan visas en lista med funktioner för allmänt tillgängliga som visar en felaktig status. 

1.  Hantering av förmåner
2.  Ärendehantering
3.  Databasloggning (granskning)
4.  Ledighetsperiodisering för ett enskilt företag eller en enskild plan
5.  Uppskjuten periodisering för tjänstledighet och frånvaro
6.  Orsakskod och kommentar för saldojustering
7.  Köpa och sälja tjänstledighet
8.  Kalender för ledighet och frånvaro
9.  Överföringsregler för tjänstledighet
10. Granskning av periodisering av tjänstledighet
11. Ta bort periodiserad tjänstledighet
12. Runda av periodiserad ledighet
13. Konfigurera flera tjänstledighetstyper i en enda tjänstledighetsplan
14. Förbättringar av Uppdatera ledig tid
15. Använd en medarbetares befattning motsvarande heltid för periodiseringar
16. Kompensationsvy för korsföretag
17. Skriv ut resultatöversyner
18. Korrigeringar för periodisering av ledighet

## <a name="see-also"></a>Se även

[Nyheter och ändringar i Personal](hr-admin-whats-new.md)</br>
[Översikt över Dynamics 365 Human Resources 2019 utgivningsvåg 2](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Uppdatera process](hr-admin-setup-update-process.md)</br>
[Hantera funktioner](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]