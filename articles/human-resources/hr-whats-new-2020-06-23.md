---
title: Nyheter och ändringar i Dynamics 365 Human Resources (25 juni 2020)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Human Resources 23 juni 2020.
author: andreabichsel
ms.date: 06/25/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-06-25
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 15e40152041ca6f531350a8403492dd98f8f3f0c
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "5891923"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-june-23-2020"></a>Nyheter och ändringar i Dynamics 365 Human Resources (23 juni 2020)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Det här ämnet beskriver nya eller ändrade funktioner i Dynamics 365 Human Resources. Ändringarna tillämpas på versionsnummer 8.1.3347. Siffror inom parenteser i vissa rubriker refererar till LCS-supportnummer för referens.

## <a name="when-an-enrollment-is-expired-for-a-terminated-employee-the-leave-type-balance-and-amount-are-all-cleared-in-the-leave-enrollment-form-444867"></a>När en registrering har upphört för en avslutad medarbetare avmarkeras tjänstledighetstypen, saldot och beloppet i Anmälan om tjänstledighet (444867)

Värdena i **Tjänstledighetstyp**, **Saldo** och **Belopp** underhålls nu i stället för att de markeras.

## <a name="incorrect-forecasted-balance-when-new-feature-leave-accrual-for-a-single-company-or-a-single-plan-is-enabled-456553"></a>Felaktigt prognostiserat saldo när ny funktion (lämna periodisering av tjänstledighet för ett enskilt företag eller en enskild plan) är aktiverad (456553)

Det korrekta prognostiserade saldot visas nu när ledighetstillägget för ett enda företag eller en enskild plan har aktiverats.

## <a name="entities-with-relations-that-result-in-duplicate-navigation-properties-456486"></a>Entiteter med relationer som resulterar i duplicerade navigeringsegenskaper (456486)

Genom den här versionen åtgärdas ett problem med flera entiteters navigeringsegenskaper (relation). Dubbletter av relationer upptäcks. Dessa scenarier har korrigerats.
 
## <a name="cross-company-comments-on-performance-review-455536"></a>Korsföretagskommentarer på prestandagranskning (455536)

Korsföretagskommentarer visas nu i resultatgranskningar med den här korrigeringsfilen. Den här ändringen korrigerar visningen av granskares kommentarer som har registrerats i olika företag för samma resultatgranskning.
 
## <a name="inconsistency-in-showing-compensation-management-data-432562"></a>Inkonsekvenser vid visning av kompensationshanteringsdata (432562)

En konsekvent översikt över kompensationsdata underhålls nu i självbetjäning för chef. Beroende på hur du navigerar till en arbetares **kompensationsinformation**, visas kompensationsdata konsekvent för chefer.
 
## <a name="fixed-compensation-plans-effective-date-defaults-to-todays-date-411994"></a>Den fasta kompensationsplanens giltighetsdatum används som standard för dagens datum (411994)

Startdatumet för kompensationen baseras nu på startdatumet för befattningen som tilldelas medarbetaren.

## <a name="leave-and-absence-form-enable-half-day-definition-is-disabled-when-form-opens-452607"></a>Formulär för tjänstledighet och frånvaro aktivera halvdags definition inaktiveras när formuläret öppnas (452607)

Med den här ändringen **aktiveras definitionen av aktivera halv dag** tills det finns nya tjänstledighetstransaktioner. 

## <a name="unable-to-publish-to-hcmdiscussionentity-via-excel-totalratingscore-field-error-453899"></a>Det går inte att publicera till HcmDiscussionEntity via Excel. TotalRatingScore fältfel (453899)

Du kan nu uppdatera fältet **TotalRatingScore** med hjälp av designer för **HCMDiscussionEntity** i Excel-arbetsboken.

## <a name="in-preview"></a>I förhandsgranskning

## <a name="database-logging"></a>Databasloggning

Databasloggning kan du bestämma vilka register och fält som ska övervakas. Du kan också bestämma vilka händelser som ska utlösa ändringsspårningen. Du använder funktionerna för databasloggning för att visa dessa ändringar över tiden. Mer information finns i [Konfigurera och hantera databasloggning](hr-admin-database-logging.md).

## <a name="mandatory-fields"></a>Obligatoriska fält 

Du kan nu göra fält obligatoriska genom att använda anpassningsfunktioner för personal. Den här funktionen kräver **sparade vyer**.

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

## <a name="configure-the-name-of-employee-self-service"></a>Konfigurera namnet på självbetjäning för medarbetare

Ett nytt alternativ är tillgängligt i **personalparametrarna** för att uppdatera namnet på arbetsytan självbetjäning för medarbetare till självbetjäning.

## <a name="checklist-entities-included-in-dataverse"></a>Entiteter för checklista inkluderade i Dataverse

Entiteter för checklista för registrering, offboard, överföringar och affärsprocesser kommer snart att vara tillgängliga inom Dataverse.

## <a name="see-also"></a>Se även

[Nyheter och ändringar i Personal](hr-admin-whats-new.md)</br>
[Översikt över Dynamics 365 Human Resources 2019 utgivningsvåg 2](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Uppdatera process](hr-admin-setup-update-process.md)</br>
[Hantera funktioner](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]