---
title: Nyheter och ändringar i Dynamics 365 for Talent (10 september 2019)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 9/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-09-10
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 0aadecd5b37759492f7895ccfda1a777793a08b3
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2020
ms.locfileid: "3006251"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-september-10-2019"></a>Nyheter och ändringar i Dynamics 365 for Talent (10 september 2019)

Det här ämnet beskriver nya eller ändrade funktioner i Dynamics 365 for Talent.

## <a name="changes-in-attract"></a>Ändringar i Attract

### <a name="candidate-e-mail-login"></a>E-postinloggning för kandidat

Kandidater kan nu använda vilken e-postadress som helst för att skapa ett konto och logga in på en Talent karriärwebbplats för att söka efter jobb och se deras ansökningsstatus. Detta är dessutom att redan kunna logga in på den Talent karriärswebbplatsen med hjälp av deras sociala konton eller deras autentiseringsuppgifter.

### <a name="job-activation-and-posting"></a>Jobbaktivering och bokföring

Vi har gjort några ändringar för jobbaktivering och bokföring. Du måste aktivera jobb innan du bokför dem på den Talent karriärswebbplatsen eller på några externa jobbtavlor, inklusive LinkedIn eller Broadbean.

## <a name="changes-in-onboard"></a>Ändringar i Onboard

Den här versionen inkluderar felkorrigeringar för Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Ändringar i Core HR

Ändringar som beskrivs i detta avsnitt gäller versionsnummer 8.1.2482. Siffror inom parenteser i vissa rubriker refererar till supportnummer i Microsoft Dynamics Lifecycle Services (LCS).

### <a name="you-can-enable-preview-features-in-sandbox-and-trial-environments"></a>Du kan aktivera förhandsgranskningsfunktioner i begränsade miljöer och testmiljöer

När du etablerar en ny instans av Talent kan du ange om instanstypen är produktion eller begränsat läge. Med instanser Begränsat läge kan tidig test av nya funktioner göras. Om du vill uppdatera en av dina befintliga förekomster till instanstypen Begränsat läge kontaktar du Support för att initiera ändringsbegäran.

Mer information om hur du ändringar publiceras finns i [Etablera Talent](./provisioning-talent.md).

### <a name="platform-update-29"></a>Plattform update 29

Ytterligare information om plattformsuppdatering 29 finns i [Förhandsgranskningsfunktioner i Dynamics 365 for Finance and Operations plattformsuppdatering 29 (oktober 2019)](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-29).

### <a name="new-job-base-entity-available-in-data-management-framework-347202"></a>Ny basenhet för jobb tillgänglig i datahanteringsramverk (347202)

Med den här versionen av den här versionen finns det en ny basjobbsenhet för import/export av data. 

### <a name="worker-advanced-security-policy-incorrectly-displays-positions-in-position-hierarchy-354868"></a>Avancerad säkerhetspolicy för arbetare visar felaktigt befattningar i positionshierarkin (354868)

Med den här versionen visas positioner inte längre öppna med en "Tom" arbetare när användare har begränsat åtkomsten.

### <a name="job-form-close-box-wont-close-form-in-certain-situations-342467"></a>Stängningsruta för jobbformulär stänger inte formuläret i vissa situationer (342467)

I den här versionen ingår en ändring som gör att jobbformuläret stängs i alla scenarier.

### <a name="new-case-on-employee-record-is-locked-for-human-resources-manager-role-337111"></a>Nytt ärende för medarbetarpost är låst för personalchefsrollen (337111)

Med den här ändringen är formuläret ärendehantering inte längre låst när det öppnas från medarbetarformuläret.

### <a name="employment-end-date-always-defaults-to-235959-351492"></a>Anställningsslutdatum är alltid standardvärdet 23:59:59 (351492)

Med den här ändringen kan du ändra anställningsdatumet till en annan tidpunkt än 23:59:59 när du avslutar en anställning manuellt.

### <a name="unable-to-set-up-expiration-date-on-an-earning-code-through-data-management-336604"></a>Det går inte att ställa in förfallodatum för den aktuella koden via datahantering (336604)

I den här versionen kan du skapa de betalningskoder som går ut genom **PayrollWorkerPositionEarningCodeEntity**-enheten.

### <a name="employee-development-analytic-report-doesnt-display-data-348737"></a>Analysrapport för medarbetarutveckling visar inte data (348737)

Under den här veckans frisläppning har analysen för medarbetarens kompetenser uppdaterats för att tillhandahålla korrekt rapportering.

### <a name="terms-of-employment-datetime-dont-default-to-beginning-of-day-349101"></a>Datum/tid för anställningsvillkor kan inte börja på dagens datum (349101)

Med den här ändringen startas datum/tid för start nu som standard till början på dagen och slutdatum/-tid används till dagens datum.

### <a name="changing-the-employment-end-date-on-worker-action-form-displays-an-error-354092"></a>Om du ändrar slutdatumet i formuläret för arbetsuppgifter visas ett fel (354092) 

Den här ändringen åtgärdar ett problem när slutdatum för anställning ändras som en del av arbetsåtgärden.

### <a name="applying-onboarding-checklists-across-companies-338433"></a>Använda integrationschecklistor över flera företag (338433)

I den här versionen kan du nu tillämpa checklistor för medarbetare som är anställda i andra juridiska personer än den undertecknade juridiska personen.

## <a name="in-preview"></a>I förhandsgranskning

### <a name="streamlined-employee-entry-and-navigation"></a>Strömlinjeformad medarbetarinmatning och navigering

Den här funktionen är nu tillgänglig i miljöer med begränsat läge. Om du vill aktivera den här funktionen navigerar du till **Systemadministration > Länkar > Inställningar > Systemparametrar > Förhandsfunktioner**. Välj **Förbättrade arbetarformulär och navigering**. Detta aktiverar dessa ändringar för alla användare. Du kan stänga av det här alternativet när du vill.

Mer information finns i [strömlinjeformad medarbetarinmatning och navigering](./streamlined-employee-entry.md)
