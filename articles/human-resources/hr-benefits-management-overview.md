---
title: Hantering av förmåner – översikt
description: Översikt över funktionen för förmånshantering i Dynamics 365 Human Resources. Erbjud dina medarbetare utökade förmånsalternativ med en lättanvänd onlineupplevelse.
author: andreabichsel
ms.date: 04/21/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 1b6ace2ce83c668e83ec1b433f8062148a6dfaf4
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059074"
---
# <a name="benefits-management-overview"></a>Förmånshantering – översikt

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

För att vara konkurrenskraftig måste du erbjuda en stor mängd fördelar för att kunna locka till dig och behålla dina bästa anställda. Förutom standardförmåner som sjukvård och tandvård kanske du även vill erbjuda utökade tjänster som implementeringshjälp, rekreationsprogram och bidrag till kläder. Med förmånshantering i Microsoft Dynamics 365 Human Resources får du en flexibel lösning som stöder en mängd olika förmånsalternativ. Personal inkluderar också en lättanvänd medarbetarupplevelse som visar dina erbjudanden.

- Med hjälp av förbättrade förmånsplaner kan du skapa och hantera unika förmånsplaner och stödja komplexa förmånspristabeller och kapslade nivåer. Du kan enkelt skapa förmånsprogram, buntar och automatiska registreringsregler för en enklare medarbetarupplevelse.

- Med flexkreditprogram kan du göra proportionell fördelning för att stödja pension och andra livhändelser.

- Omfattande berättiganderegler garanterar att du gör rätt förmåner tillgängliga för rätt medarbetare.

- En anmälan online av förmåner är en enkel upplevelse för dina anställda.

- Kvalificerad bearbetning av livshändelse stöder framtida livshändelser.

Om du vill ha tillgång till demonstrationsdata måste du omdistribuera miljön i begränsat läge.

>[!NOTE]
>Du kan nu formulären för hantering av förmåner. Du kan nu lägga till anpassade fält som hör till disponeringssatser i formuläret **Disponeringsalternativ** för förmånsplaner. Mer information om arbete med anpassade fält finns i [Anpassade fält](hr-developer-custom-fields.md).
>![Anpassade fält för förmånshantering](media/hr-benefits-management-custom-fields.png)

## <a name="enable-benefits-management"></a>Aktivera hantering av förmåner

Det här ämnet beskriver hur du aktiverar funktionerna i personal. Den talar också om vilka befintliga funktioner i personal som hantering av förmåner ersätter eller inaktiveras när du har aktiverat hantering av förmåner.

> [!IMPORTANT]
> När du har aktiverat hantering av förmåner i miljön **produktion** kan du inte inaktivera den. Vi rekommenderar att du aktiverar och testar förmånshantering i en miljö med **begränsat läge** innan du aktiverar den i en miljö för **produktion**. Det finns betydande skillnader mellan den tidigare förmånsfunktionen och nya fördelar för hanteringsfunktioner som kräver ytterligare inställningar och bör testas innan de kan placeras i produktionen.

- [Hantera funktioner](hr-admin-manage-features.md)

## <a name="configure-employee-information"></a>Konfigurera information om medarbetare

Innan du kan registrera medarbetare i förmåner måste du ange den information som krävs. Du måste registrera en medarbetare i en **fast kompensationsplan** på deras startdatum och du måste välja en **förmånslönefrekvens** i **medarbetarinformation** i formuläret **medarbetare**.

Om du har en medarbetare som tar emot kompletterande kompensation som provisioner kan du lägga till ett belopp för **årslön** från medarbetarposten. Personal kommer att använda beloppet **Årslön** vid fastställande av täckningsbelopp, istället för det årliga beloppet för fast ersättning. Den **Årslönen** måste vara giltig för medarbetarens startdatum eller början av förmånsperioden, beroende på vilket som är senaste. Om både en fast kompensation och bestämda årslönsbelopp registreras för en medarbetare, kommer den bestämda årslönen att användas vid fast ställande av täckningsbelopp.

När du skapar en förmånsplan som bygger på kön eller ålder måste du ange ett födelsedatum och kön för medarbetaren för att beräkna förmånskostnaden.

## <a name="configure-benefits-management"></a>Konfigurera förmånshantering

Innan du kan skapa förmånsplaner för dina medarbetare måste du konfigurera alternativen för planerna.

- [Ställ in parametrar för hantering av förmåner](hr-benefits-setup-parameters.md)
- [Konfigurera berättiganderegler och alternativ](hr-benefits-setup-eligibility-rules.md)
- [Konfigurera berättigandealternativ för personlig kontakt](hr-benefits-setup-contact-eligibility-options.md)
- [Skapa disponeringsalternativ](hr-benefits-setup-coverage-options.md)
- [Ställa in betalningsfrekvenser](hr-benefits-setup-payment-frequencies.md)
- [Konfigurera livshändelsetyper](hr-benefits-setup-life-event-types.md)
- [Skapa plantyper](hr-benefits-setup-plan-types.md)
- [Ställa in orsakskoder](hr-benefits-setup-reason-codes.md)
- [Ställa in skiktkoder](hr-benefits-setup-tier-codes.md)
- [Konfigurera satser](hr-benefits-setup-rates.md)
- [Konfigurera avdrag](hr-benefits-setup-deductions.md)
- [Konfigurera väntedagar](hr-benefits-setup-waiting-days.md)
- [Konfigurera vänteperioder](hr-benefits-setup-waiting-periods.md)
- [Ställa in avrundningsregler](hr-benefits-setup-rounding-rules.md)
- [Skapa anställningskategorier](hr-benefits-setup-employment-categories.md)
- [Ställ in anställningstyper](hr-benefits-setup-employment-types.md)
- [Konfigurera självbetjäning för medarbetare](hr-benefits-setup-employee-self-service.md)

## <a name="create-benefit-plans"></a>Skapa förmånsplaner

Dessa artiklar visar hur du skapar förmånsplaner, inklusive buntar och flexkreditprogram.

- [Ställa in förmånsplaner](hr-benefits-plans-setup.md)
- [Ställa in flexkreditprogram](hr-benefits-plans-flex-credit-programs.md)

## <a name="process-benefit-plans"></a>Bearbeta förmånsplaner

Du måste bearbeta några av dina ändringar för att göra dem aktiva.

- [Bearbetning av berättigande för anmälan](hr-benefits-process-enrollment-eligibility.md)
- [Bearbeta livshändelse](hr-benefits-process-life-events.md)
- [Bearbeta ändring av livshändelse](hr-benefits-process-life-event-changes.md)
- [Bearbetning av berättigande för livshändelse](hr-benefits-process-life-event-eligibility.md)
- [Behandla prisändringar](hr-benefits-process-rate-changes.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]