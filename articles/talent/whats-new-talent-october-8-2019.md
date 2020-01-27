---
title: Nyheter och ändringar i Dynamics 365 Talent (8 oktober 2019)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 10/08/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-10-08
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 06758ff5eb1c00ae299b1b8849fcabb0cd9593e8
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/06/2019
ms.locfileid: "2896645"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-october-8-2019"></a>Nyheter och ändringar i Dynamics 365 Talent (8 oktober 2019)

Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Ändringar i Attract

Den här versionen inkluderar felkorrigeringar för Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Ändringar i Onboard

Den här versionen inkluderar felkorrigeringar för Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Ändringar i Core HR

Ändringar som beskrivs i detta avsnitt gäller versionsnummer 8.1.2542. Siffror inom parenteser i vissa rubriker refererar till supportnummer i Microsoft Dynamics Lifecycle Services (LCS).

### <a name="removal-of-benefits-open-enrollment-from-public-preview"></a>Borttagning av funktionen för öppna anmälan från offentlig förhandsgranskning

I samverkan med vårt meddelande i blogginlägget [Strategiska investeringar i det grundläggande HR-systemet för att effektivisera verksamheten](https://cloudblogs.microsoft.com/dynamics365/bdm/2019/10/02/strategic-investments-in-core-hr-drive-operational-excellence/) tar Microsoft bort funktionen för öppna anmälan i den allmänna förhandsversionen 18 oktober 2019. I stället kommer nya funktioner att publiceras i framtiden. Produktionsanvändning av funktionen för öppna anmälan som för närvarande ingår i den allmänna förhandsgranskningen stöds inte. 

### <a name="common-data-service-integration-is-now-turned-off-by-default-on-new-provisions-343675"></a>Common Data Service integrering är nu inaktiverad som standard på nya bestämmelser (343675)
 
När nya miljöer etableras är Common Data Service-integreringen nu inaktiverad. Mer information finns i avsnittet [Konfigurera Common Data Service-integration](hr-common-data-service-integration.md).

### <a name="streamlined-employee-entry-and-navigation"></a>Strömlinjeformad medarbetarinmatning och navigering

Funktioner för medarbetarpost och navigering är nu tillgängliga i alla miljöer. Om du vill aktivera den här funktionen går du till **Systemadministration \> Länkar \> Inställningar \> Systemparametrar \> Förhandsfunktioner** och välj **Förbättrade arbetarformulär och navigering**. Funktionen aktiveras sedan för alla användare. Du kan stänga av det här alternativet när du vill.

Mer information finns i [Strömlinjeformad medarbetarinmatning](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/streamlined-employee-data-entry) i Dynamics 365: 2019 släpp av påfyllnad 2 plan.

### <a name="attract-and-onboard-create-inactive-workers-in-core-hr-380517"></a>Attract och Onboard skapar inaktiva arbetare i Core HR (380517)

I denna veckas version korrigeras ett problem där man ska skapa inaktiva arbetare i Attract och Onboard i Core HR.

### <a name="the-workflow-fails-when-the-manager-is-signed-in-to-another-company-while-terminating-an-employee-346852"></a>Arbetsflödet misslyckas när chefen är inloggad på ett annat företag medan en medarbetare avslutas (346852)

Arbetsflödet kan inte längre hanteras baserat på den juridiska person som chefen har loggat in på.

### <a name="missing-information-on-hcmonboardingworkerchecklisttaskentity-349591"></a>Information saknas på HcmOnboardingWorkerChecklistTaskEntity (349591)

Den här versionen innehåller ytterligare information om **HcmOnboardingWorkerChecklistTaskEntity**. Nedan följer några exempel:

- **Gruppnamn** när den tilldelade typen är **grupp**
- **Namn på medarbetare** när den tilldelade typen är **medarbetare**
- **Namn på chef** när den tilldelade typen är **chef**

### <a name="entities-arent-listed-in-alphabetical-order-in-common-data-service-administration-377414"></a>Entiteter visas inte i alfabetisk ordning Common Data Service i Administration (377414)

Entiteter visas nu i alfabetisk ordning på sidan **CDS Administration**.

### <a name="changing-the-employment-type-with-a-future-date-doesnt-allow-a-position-assignment-339958"></a>Ändra anställningstypen med ett framtida datum tillåter inte en befattningstilldelning (339958)

Denna ändring tillåter befattningstilldelningar när medarbetartyper ändras (t.ex. från medarbetare till leverantör).

### <a name="updating-the-common-data-service-leave-bank-transaction-entity-creates-a-new-record-in-talent-352938"></a>Uppdateringen av Common Data Service enheten för tjänstledighet för banktransaktioner skapar en ny post i Talent (352938)

Tjänstledighetstransaktionen uppdateras nu när en uppdatering görs till Common Data Service för att lämna banktransaktioner.

### <a name="the-title-of-attachments-for-feedback-items-shows-the-feedback-description-343765"></a>Titeln på bifogade filer för feedback-poster visar beskrivningen av feedback (343765)

Beskrivningen av feedback visas inte längre i den bifogade filens titel.

### <a name="compensation-workflow-comments-field-shows-incorrect-content-339297"></a>Kommentarsfältet kompensation för arbetsflöde visar felaktigt innehåll (339297)

Den här ändringen visar innehållet i fältet **%HcmActionState.HcmWorkerActionComment.Comments%**.

### <a name="workcalendarentity-and-workcalendardayentity-arent-exposed-through-odata-376329"></a>WorkCalendarEntity och WorkCalendarDayEntity exponeras inte genom OData (376329)

I den här versionen är **WorkCalendarEntity** och **WorkCalendarDayEntity** nu tillgängliga via Open Data Protocol (OData).

### <a name="hcmworkerentity-is-slow-when-odata-is-used-375221"></a>HCMWorkerEntity är långsam när OData används (375221)

Ändringar förbättrar prestanda för **HCMWorkerEntity** när designer för Microsoft Excel-arbetsböcker används.

### <a name="manager-performance-journal-entry-shows-an-error-after-deleting-a-performance-journal-and-creating-a-new-one-336061"></a>Chefens prestationsjournalpost visar ett fel när en prestandajournal har tagits bort och en ny har skapats (336061)

Den här utgåvan korrigerar ett problem som uppstår efter att en prestandajournal har tagits bort och en ny av dem skapas omedelbart efteråt. Den här korrigeringen ändrar beteendet i självbetjäning för chefer.

## <a name="coming-soon"></a>Kommer snart

### <a name="print-performance-reviews"></a>Skriv ut resultatöversyner

Se [Skriv ut resultatöversyner](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) i Dynamics 365: 2019 släpp påfyllnad 2 plan.
