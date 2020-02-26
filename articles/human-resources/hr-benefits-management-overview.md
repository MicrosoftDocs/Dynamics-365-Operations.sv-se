---
title: Förmånshantering – översikt
description: Översikt över funktionen för förmånshantering i Dynamics 365 Human Resources. Erbjud dina medarbetare utökade förmånsalternativ med en lättanvänd onlineupplevelse.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 63db1b55bae9150dd87d9981136b96d72ffd0c59
ms.sourcegitcommit: 523049c363a999050c58d20695f1c7d151b3fd3e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/06/2020
ms.locfileid: "3029473"
---
# <a name="benefits-management-overview"></a>Förmånshantering – översikt

[!include [banner](includes/preview-feature.md)]

För att vara konkurrenskraftig måste du erbjuda en stor mängd fördelar för att kunna locka till dig och behålla dina bästa anställda. Förutom standardförmåner som sjukvård och tandvård kanske du även vill erbjuda utökade tjänster som implementeringshjälp, rekreationsprogram och bidrag till kläder. Med funktionen för förhandsgranskning av förmånshantering i Microsoft Dynamics 365 Human Resources får du en flexibel lösning som stöder en mängd olika förmånsalternativ. Personal inkluderar också en lättanvänd medarbetarupplevelse som visar dina erbjudanden.

- Med hjälp av förbättrade förmånsplaner kan du skapa och hantera unika förmånsplaner och stödja komplexa förmånspristabeller och kapslade nivåer. Du kan enkelt skapa förmånsprogram, buntar och automatiska registreringsregler för en enklare medarbetarupplevelse.

- Med flexkreditprogram kan du göra proportionell fördelning för att stödja pension och andra livhändelser.

- Omfattande berättiganderegler garanterar att du gör rätt förmåner tillgängliga för rätt medarbetare.

- En anmälan online av förmåner är en enkel upplevelse för dina anställda.

- Kvalificerad bearbetning av livshändelse integreras med självbetjäning för medarbetare och stöder även framtida livshändelser.

Om du vill ha tillgång till demonstrationsdata måste du omdistribuera miljön i begränsat läge.

Du kan tillhandahålla direkt återrapportering eller rapportera problem till: D365BenefitsPreview@microsoft.com.

## <a name="benefits-management-known-issues"></a>Kända problem med förmånshantering

### <a name="eligibility-processing"></a>Bearbetning av berättigande

När du kör berättigande till förmåner som använder en 1-5X lön, % av lönen och fast belopp för försäkringsbeloppet, måste du ställa in datum för **förmånsinformation** till **medarbetarens startdatum** i **anställningshistoriken**. Du måste också inkludera **arbetade timmar**, **lönefrekvens** och **årlig inkomst av förmånen**. Om arbetaren har fast kompensation, ange **arbetade timmar** och **lönefrekvens**. Den årliga inkomsten kommer att beräknas. Om medarbetaren har län behöver du inte ange **arbetade timmar**. Vi rekommenderar att du först anger fast kompensation när du skapar nya medarbetare. Om du vill uppdatera informationen om förmånsposter, gå till **Arbetare > Arbetarhistorik > Information om anställning**. Justera datumet till arbetarens startdatum.

### <a name="employee-self-service"></a>Självbetjäning för medarbetare

Medarbetarbelopp beräknas inte när täckningsbeloppet uppdateras för livförsäkring. När en medarbetare till exempel erbjuds en livförsäkringsplan kan han eller hon välja upp för att $ 50 000 för täckning till en kostnad av $ 0,36 per $ 1 000 av täckning.  När medarbetaren uppdaterar täckningsbeloppet finns medarbetarens kopplade kostnad kvar på noll.

För en förmånsplan som bara tillåter ett enda urval av den aktuella plantypen får användaren ett fel om de försöker att avstå från en plan efter att ha valt en plan. En användare väljer till exempel en sjukvårdsplan och placerar den i vagnen. Användaren väljer sedan **Avstå** för en annan sjukvårdsplan. Användaren får ett felmeddelande.

## <a name="enable-benefits-management"></a>Aktivera hantering av förmåner

Hantering av förmåner är en förhandsgranskningsfunktion som bara är tillgänglig i miljöer med **begränsat läge**. I dessa artiklar beskrivs hur du aktiverar förhandsgranskningsfunktionerna i personal. De talar också om vilka befintliga funktioner i personal som hantering av förmåner ersätter eller inaktiveras när du har aktiverat hantering av förmåner.

- [Hantera funktioner](hr-admin-manage-features.md)
- [Förhandsgranskningsfunktion: Hantering av förmåner](hr-admin-manage-features.md?preview-feature-benefits-management)

## <a name="configure-benefits-management"></a>Konfigurera hantering av förmåner

Innan du kan skapa förmånsplaner för dina medarbetare måste du konfigurera alternativen för planerna.

- [Ställ in parametrar för hantering av förmåner](hr-benefits-setup-parameters.md)
- [Konfigurera berättiganderegler och alternativ](hr-benefits-setup-eligibility-rules.md)
- [Konfigurera berättigandealternativ för personlig kontakt](hr-benefits-setup-contact-eligibility-options.md)
- [Skapa omfattningsalternativ](hr-benefits-setup-coverage-options.md)
- [Ställ in lönefrekvenser](hr-benefits-setup-payment-frequencies.md)
- [Konfigurera livshändelsetyper](hr-benefits-setup-life-event-types.md)
- [Skapa plantyper](hr-benefits-setup-plan-types.md)
- [Ställ in orsakskoder](hr-benefits-setup-reason-codes.md)
- [Ställa in nivåkoder](hr-benefits-setup-tier-codes.md)
- [Konfigurera tariffer](hr-benefits-setup-rates.md)
- [Konfigurera avdrag](hr-benefits-setup-deductions.md)
- [Konfigurera väntedagar](hr-benefits-setup-waiting-days.md)
- [Konfigurera vänteperioder](hr-benefits-setup-waiting-periods.md)
- [Ställ in avrundningsregler](hr-benefits-setup-rounding-rules.md)
- [Skapa anställningskategorier](hr-benefits-setup-employment-categories.md)
- [Ställ in anställningstyper](hr-benefits-setup-employment-types.md)
- [Konfigurera självbetjäning för medarbetare](hr-benefits-setup-employee-self-service.md)

## <a name="create-benefit-plans"></a>Skapa förmånsplaner

Dessa artiklar visar hur du skapar förmånsplaner, inklusive buntar och flexkreditprogram.

- [Ställa in förmånsplaner](hr-benefits-plans-setup.md)
- [Skapa förmånsplaner för arbetare](hr-benefits-plans-worker.md)
- [Ställ in flexkreditprogram](hr-benefits-plans-flex-credit-programs.md)
- [Konfigurera kommande livshändelser](hr-benefits-plans-future-life-events.md)

## <a name="process-benefit-plans"></a>Bearbeta förmånsplaner

Du måste bearbeta några av dina ändringar för att göra dem aktiva.

- [Bearbetning av berättigande för anmälan](hr-benefits-process-enrollment-eligibility.md)
- [Bearbeta livshändelse](hr-benefits-process-life-events.md)
- [Bearbeta ändring av livshändelse](hr-benefits-process-life-event-changes.md)
- [Bearbetning av berättigande för livshändelse](hr-benefits-process-life-event-eligibility.md)
- [Behandla prisändringar](hr-benefits-process-rate-changes.md)

