---
title: Nyheter och ändringar i Dynamics 365 Human Resources (08 juli 2020)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Human Resources 8 juli 2020.
author: andreabichsel
manager: tfehr
ms.date: 07/08/2020
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
ms.author: jaredha
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 14dfd925009cb2a9d40044e27f28521ff4d331b7
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/06/2021
ms.locfileid: "5130407"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-july-8-2020"></a>Nyheter och ändringar i Dynamics 365 Human Resources (8 juli 2020)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Det här ämnet beskriver nya eller ändrade funktioner i Dynamics 365 Human Resources. Ändringarna tillämpas på versionsnummer 8.1.3382. Siffror inom parenteser i vissa rubriker refererar till LCS-supportnummer för referens.

## <a name="database-logging"></a>Databasloggning

Databasloggning kan du bestämma vilka register och fält som ska övervakas. Du kan också bestämma vilka händelser som ska utlösa ändringsspårningen. Du använder funktionerna för databasloggning för att visa dessa ändringar över tiden. Mer information finns i [Konfigurera och hantera databasloggning](hr-admin-database-logging.md).

## <a name="configure-the-name-of-employee-self-service"></a>Konfigurera namnet på självbetjäning för medarbetare

I **personalparametrar** kan du nu ändra namnet på arbetsytan **självbetjäning för medarbetare** till **självservice**. Mer information finns i [Ändra namn på arbetsytan för självbetjäning för medarbetare](hr-employee-self-service-workspace-name.md)

## <a name="benefits-management-open-enrollment-access-outside-of-period"></a>Hantering av förmåner öppna registreringsåtkomst utanför period

Genom den här utgåvan åtgärdas ett fel där medarbetarna kan få åtkomst till förmåner vid en öppen registrering utanför anmälningsperioden eller utan livshändelser. Om du behöver demo öppna en registrering i självbetjäning för medarbetare måste du justera de öppna anmälningsdatumen till idag (eller tidigare) för att göra det tillgängligt. Du kan ändra den här inställningen under **förmånshantering > regler och alternativperioder**.

## <a name="email-employee-enrollment-confirmation"></a>Bekräftelse på e-postanmälan om medarbetare

Du kan nu skicka e-postmeddelanden till medarbetare efter att de slutfört urvalet av förmåner. Du kan antingen skicka ett standardmeddelande eller använda en organisations e-postmall. Dessa inställningar finns under **Personalparametrar > Hantering av förmåner**.

## <a name="canceled-leave-still-appears-in-upcoming-time-off-on-people-workspace-441358"></a>Annullerad ledighet visas fortfarande i kommande ledighet på arbetsytan personer (441358)

Annullerad låt visas inte längre som kommande ledighet på tjänstledighetskortet på arbetsytan **personer**.

## <a name="unable-to-use-the-department-entity-property-in-the-positionv2-entity-456486"></a>Det går inte att använda egenskapen avdelningsenhet i PositionV2-entiteten (456486)

Nu kan du lägga till en avdelning utan att skapa en duplicerad relation.

## <a name="payrollworkerenrolledbenefitdetailentity-should-only-use-calculated-field-for-retirement-plans-459779"></a>PayrollWorkerEnrolledBenefitDetailEntity bör endast använda beräknade fält för pensionsplaner (459779)

När du exporterar **PayrollWorkerEnrolledBenefitDetailEntity**-entiteten avgör exporten om det ska använda ett beräknat fält baserat på en kostnadstabell eller använda fältet **ContributionAmountCur** i säkerhetstabellen. Logiken som används av dataenheten använder kostnadstabellen i situationer där programmet normalt inte är det. Den här logiken gör att enhetens export returnerar ett nollvärde för den här kolumnen eftersom ingen beräkningsavgiftstabell och produkten inte tillåter kunden att ange en sådan.
 
## <a name="confusing-translations-in-czech-language-in-personnel-management-and-employee-self-service-400276"></a>Förvirrande översättningar på tjeckiska språk i personalhantering och Självbetjäning för medarbetare (400276)

Den här versionen korrigerar översättningarna för **Företagskatalogen**, **Nästa registrerade kurs**, **Jobb** och **Befattning**.
 
## <a name="the-workcalendaremployment-table-doesnt-have-the-created-and-modified-system-fields-enabled-460171"></a>De skapade och ändrade systemfälten är inte aktiverade i WorkCalendarEmployment-registret (460171)

Skapade och ändrade systemfält har nu aktiverats i registret **WorkCalendarEmployment** i personal.
 
## <a name="null-reference-exception-for-hire-and-add-details-for-future-employee-455475"></a>Null-referens undantag för anställning och lägg till detaljer för framtida medarbetare (455475)

Den här versionen korrigerar ett fel (null-referens) i strömlinjeformad medarbetartransaktion när du anställer en medarbetare med alternativet att **anställa och lägga till detaljer**.

## <a name="changes-made-in-the-dataverse-worker-entity-dont-reflect-in-human-resources-455652"></a>Ändringar gjorda i Dataverse arbetsenheten visas inte i personal (455652)

Ändringar som görs i följande fält i entiteten **Arbetare** i Dataverse kommer nu att visas i personal:

- **Arbetar hemifrån**
- **Datum för tjänsteålder**
- **Jubileumsdatum**
- **Ursprungligt anställningsdatum**

## <a name="correct-compensation-level-doesnt-default-based-on-the-job-assigned-to-the-position-394136"></a>Korrekt kompensationsnivå är inte standard baserad på jobbet som tilldelats befattningen (394136)

Med denna ändring är den korrekta kompensationsnivån standard baserad på poster för **giltighetsdatum** för **befattningsdetaljer** och **Startdatum** för **Tilldelning av kompensationsplan**.

## <a name="in-preview"></a>I förhandsgranskning

## <a name="mandatory-fields"></a>Obligatoriska fält 

Du kan nu göra fält obligatoriska genom att använda anpassningsfunktioner för personal. Den här funktionen kräver **sparade vyer**.

## <a name="human-resources-application-in-teams"></a>Personalapp i Teams

Medarbetare kan visa och begära ledighet från arbetet inom Microsoft Teams. De kan samverka med en bot för att skapa tjänstledighetsansökan. Mer information finns [i personalapp i Teams](https://go.microsoft.com/fwlink/?linkid=2127841). 

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

## <a name="checklist-entities-included-in-dataverse"></a>Entiteter för checklista inkluderade i Dataverse

Entiteter för checklista för registrering, offboard, överföringar och affärsprocesser kommer snart att vara tillgängliga i Dataverse.

## <a name="see-also"></a>Se även

[Nyheter och ändringar i Personal](hr-admin-whats-new.md)</br>
[Översikt över Dynamics 365 Human Resources 2019 utgivningsvåg 2](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Uppdatera process](hr-admin-setup-update-process.md)</br>
[Hantera funktioner](hr-admin-manage-features.md)
