---
title: Nyheter och ändringar i Dynamics 365 Talent - Core HR (10 september 2018)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Talent - Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 09/12/2018
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
ms.search.validFrom: 2018-09-06
ms.dyn365.ops.version: Talent September 10, 2018 update
ms.openlocfilehash: ff5d21a8a71b068a276bedaf6e4b9964adcb4027
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4462629"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent---core-hr-september-10-2018"></a>Nyheter och ändringar i Dynamics 365 Talent - Core HR (10 september 2018)

**Skapa 8.1.138.0**

Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Talent: Core HR.

## <a name="allow-specific-time-of-day-on-time-off-requests-half-days"></a>Tillåta viss tid på ledighetsbegärande (halv dagar)

Om ledighet och frånvaro är inställd så att ledig tid lämnas in i dagar, kan du nu även aktivera en halvdagars definition. Därefter när användaren skickar ledighetsbegäranden, kan de ange om de begär första halvan eller andra halvan av den lediga dagen.

Det här alternativet är inaktiverat som standard. För anställda att begära den första halvan eller andra halvan av dagen, måste du aktivera det här alternativet i området **Tjänstledighet och frånvaro** personalparametrar.

Säkerhetsprivilegier för den här funktionen är Underhåll personalparametrar.

## <a name="validation-of-leave-and-absence-entries"></a>Validering av tjänstledighets- och frånvaroposter

Beroende på hur ledigheten är konfigurerad, får anställda som försöker skicka in en ledighetsbegäran som är längre än sin arbetsdag ett varningsmeddelande. Med andra ord varnas de om de försöker ta mer än en hel dag vid ett givet datum.

Verifieringen är alltid aktiverad. När anställda överstiger tröskelvärdet som definieras får de en varning i sin ledighetsbegäran.

## <a name="additional-fields-for-conditional-statements-in-workflows"></a>Ytterligare fält för villkorssatser i arbetsflöden

Ytterligare fält har lagts till villkorssatser och platshållare för flera arbetsflöden i Core HR.

Följande fält har lagts till kompensation, avslutning och överföra arbetsflöden:

- EmploymentType
- LegalEntity
- AdjustedWorkerStartDate
- EmployerNoticeAmount
- EmployerUnitOfNotice
- TransitionDate
- WorkerNoticeAmount
- WorkerStartDate
- WorkerUnitOfNotice
- ProbationEndDate
- Befattning
- Fackförening
- Avdelning
- PositionType
- CompLocation
- Namn
- Jobb
- JobType
- JobFamily
- JobFunction

Följande fält har lagts till i befattningsarbetsflöden:

- Befattning
- Fackförening
- Avdelning
- PositionType
- CompLocation
- Namn
- Jobb
- JobType
- JobFamily
- JobFunction

Fält i villkorssatser och platshållare är tillgängliga för alla användare som har tillgång till konfiguration av tidigare nämnda arbetsflöden.

## <a name="navigation-to-attract-from-personnel-management"></a>Navigera till Attract från personalhantering

I personalhantering, om Attract inte har konfigurerats, hjälper avsnittet **Kandidater att anställa** användare att komma igång med Attract i stället för att visa meddelandet, ”Vi hittade ingenting att visa här”.

## <a name="other-changes"></a>Andra ändringar

Den här versionen innehåller flera ytterligare felkorrigeringar:

- När en entreprenör anställs bör fliken **kompensation** inte vara tillgänglig på sidan förfrågan/åtgärd.
- Under processen om begäran om uppsägning kan du inte fortsätta förrän alla obligatoriska fält innehåller data.
- Problem med sorteringsordning och datumvisning i analysen för Personalhantering har hanterats.
