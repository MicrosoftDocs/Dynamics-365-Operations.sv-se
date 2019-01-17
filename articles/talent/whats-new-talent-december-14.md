---
title: "Nyheter och ändringar i Dynamics 365 for Talent Core HR (14 december 2018)"
description: "Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 for Talent Core HR."
author: Darinkramer
manager: AnnBe
ms.date: 12/14/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-12-14
ms.dyn365.ops.version: Talent
ms.translationtype: HT
ms.sourcegitcommit: 844c23fc908c962203e644f1154cc480425d830b
ms.openlocfilehash: 7d2866923efd7f115ad5290f35ed4fcac5e47573
ms.contentlocale: sv-se
ms.lasthandoff: 12/18/2018

---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-december-14-2018"></a>Nyheter och ändringar i Dynamics 365 for Talent Core HR (14 december 2018)

[!include [banner](includes/banner.md)]

**Skapa 8.1.2085**

Det här ämnet beskriver nya eller ändrade funktioner i Core HR.

## <a name="changes"></a>Ändringar

### <a name="us---aca-affordable-care-act-support-for-tax-year-2018-1095-b-and-1095-c-forms"></a>US - ACA (Affordable Care Act) stöder för skatt år 2018 1095-B- och 1095-C-formulär

Varje år måste Applicable Large Employers (ALE) tillhandahålla varje heltidsanställd med 1095-C. Dessutom, om arbetsgivaren ger självförsäkringstäckning måste även tillhandahålla 1095-C (om de är en ALE) och en 1095-B (om det är en liten arbetsgivare) till alla medarbetare på heltid eller deltid, som täcks av en av deras erbjudna hälsoplaner. Den här funktionen ger formulär som kan skrivas för både 1095-C och 1095-B.

### <a name="during-import-submittedbypersonid-field-on-hcmperfjournalentity-is-ignored"></a>Under import ignoreras fältet SubmittedByPersonId på HcmPerfJournalEntity

När du importerar/exporterar prestationsjournalposter ignoreras fältet **Skickas av**. Med denna skillnad kommer värdet **importerad/exporterad** återspegla värdet i registret under exporten, när du importerar kommer systemet att uppdateras med värdet i importfilen.

### <a name="analytics-tab-on-leave-and-absence-workspace-displays-openconnectionerror-error-for-non-system-admin-roles"></a>Fliken Analys på arbetsytan ”tjänstledighet och frånvaro” visar felet ”OpenConnectionError” för icke-systemadministratörsroller

Med denna uppdatering kommer inga fel att utfärdas när du öppnar fliken **analys** i arbetsytan **Tjänstledighet och frånvaro**.

### <a name="employee-self-service-position-hierarchy-drill-down-from-tile-fails-to-get-parent-node"></a>Självservice för anställda, den nedrullningen befattningshierarkin från panel misslyckas med att hämta överordnad nod

En ändring har gjorts för att korrigera felet ”hämtning av den överordnade noden misslyckades” när befattningshierarkin har anpassats så att den visas på en befintlig arbetsyta och en befattning väljs i hierarkin.  

### <a name="must-be-system-admin-to-see-the-payroll-tab-in-the-position-page"></a>Måste vara systemadministratör för att se fliken Lön på sidan Befattning

En ändring har gjorts för att inkludera rätt element i den befintliga behörigheten: ”Underhåll lönearbetare och befattningsdetaljer”. Med den här ändringen har löneadministratören som standard åtkomst till fälten Lön på sidan Befattning.

### <a name="error-when-submitting-performance-review-to-manager-and-the-reviewsperfperiod-placeholder-is-used-in-the-submission-instructions"></a>Fel när du skickar resultatöversyn för granskning till chef och %Reviews.PerfPeriod% platshållare används i sändningsinstruktioner

En ändring har gjorts som rättar felet ”null-referens” när du använder %Reviews.PerfPeriod% platshållare i sändningsinstruktionerna.

### <a name="workforce-power-bi-report-shows-error-when-worker-seniority-date-is-a-leap-day"></a>Personalens Power BI-rapport visar fel när datum för tjänsteålder för arbetaren är en skottdag

Med den här ändringen stöds nu skottdagar i Power BI.

### <a name="integration-between-core-hr-and-attract"></a>Integration mellan Core HR och Attract

En ändring har gjorts för att uppdatera integrationen mellan Core HR och Attract som är relaterad till kandidater att anställa. För att kandidater att anställa ska visas i arbetsytan **personalhantering** kommer följande CDS för appar (CD 2.0) enheter används:

Jobbansökan
- Statusorsak måste anges för Erbjudandet godkänt
-   Ger kandidat och ledigt jobb

Kandidat
-   Ger information om kandidat

Ledigt jobb
-   Ger ID för ledigt jobb och deltagare i ledigt jobb

Deltagare i ledigt jobb
-   Ger anställande chef

När en kandidat läggs till personalhantering kan kandidaten nu också avfärdas med ett nytt alternativ som är tillgängligt på kandidatkortet.

## <a name="coming-soon"></a>Kommer snart

### <a name="leave-and-absence-future-leave-and-forecasting-leave-balances"></a>Tjänstledighet och frånvaro: framtida tjänstledighet och prognostisering lämnar saldon

Med de ändringar som görs för att möjliggöra för anställda att uppskatta ledig tid och begära framtida ledighetsansökningar utan att påverka deras nuvarande ledighetssaldon, ändrar också hur ledighetssaldon ändras. 

Saldot som visas för tillfället är hur lång ledighet som är tillgänglig för begäranden, inklusive periodiseringar via idag och alla godkända tjänstledighetsansökningar till slutet av tiden. 

När möjligheten att ställa en prognos frisläpps, visar saldot ändringar för att det aktuella saldot för ledighet inklusive periodiseringar via idag och ansökningar via idag. Medarbetare och chefer ser dessa uppdaterade saldon i medarbetares och chefers självbetjäning på kortet **ledighet** och i fönstret **ledighetssaldon**. Personalchefer kommer att se alla dessa uppdaterade saldon på arbetsytan **Personer** och i medarbetarens fönster **Tilldelade tjänstledighetsplaner**.

## <a name="known-issue"></a>Kända problem

### <a name="mapping-errors-in-the-integration-with-finance-and-operations"></a>Mappningsfel i integrationen med Finance and Operations

Följande problem har identifierats i den aktuella mallen för integrering av Talent med Dynamics 365 for Finance and Operations. En ny mall kommer snart att publiceras och kommer att gälla alla nya integrationsprojekt som har skapats. För befintliga integrationsprojekt uppdateras uppgiftsmappningarna. Se följande tabell för uppdaterade mappningar. 

>[!NOTE]
> Jobbbefattningarna till överordnad jobbuppgiftstilldelning för befattningar integrerar inte data. Detta är ett problem som för närvarande undersöks. Det finns ingen lösning för den aktuella mappningen. 

Avdelningar för driftenhetsuppgift måste ha följande mappningar uppdaterade.

| Befintligt källfält          | Nytt källfält |
| -------------------------------|------------------|
| cdm_description (beskrivning)  | cdm_name (namn)  |

En ytterligare mappning måste också läggas till. Välj det senaste fältet **Ingen** för att lägga till följande mappning.

| Källfält                   | Målfält    |
| -------------------------------|----------------------|
| cdm_description (beskrivning)  | NAMEALIAS (NAMEALIAS)|

Uppdaterade mappningar ska se ut som följande bilden.

![Avdelningar till driftenhetsuppgift](./media/DepartmentMapping.png)


Jobb till jobbdetaljuppgift måste ha följande mappningar uppdaterade.

| Befintligt källfält          | Nytt källfält                   |
| -------------------------------|------------------------------------|
| cdm_name (namn)                | cdm_description (beskrivning)      |
| cdm_name (beskrivning)         | cdm_jobdescription (jobbeskrivning)|


Uppdaterade mappningar ska se ut som bilden nedan.

![Jobb till jobbdetaljuppgift](./media/JobMapping.png)

Arbetare till arbetsuppgift måste ha följande mappningar uppdaterade.

| Befintligt källfält                 | Nytt källfält                               |
| --------------------------------------|------------------------------------------------|
| cdm_emailaddress1 (e-postadress 1)   | cdm_primaryemailaddress (primär e-postadress) |
| cdm_telephone1 (telefon 1)          | cdm_primarytelephone (primär telefon)       |

Transformering av fältet Kön behöver också uppdateras. Välj mapptypen **fn** (funktion) för kön och uppdatera följande värdemappningar.

| CDS-värde                   | Finance and Operations-värde                     |
| ----------------------------|--------------------------------------------------|
| 75440000                    | Man                                             |
| 75440001                    | Kvinna                                           |
| 75440002                    | Ingen                                             | 
| 75440003                    | Icke-specifikt                                      |

Uppdaterade mappningar ska se ut som följande bilderna.

![Arbetare till arbetaruppgift.](./media/WorkerMapping.png)

![Transformering av fältet Kön](./media/WorkerTransform.png)

