---
title: Översikt
description: I Dynamics 365 Human Resources ger arbetsytan **tjänstledighet och frånvaro** finns ett flexibel ramverk för att skapa nya frånvaroplaner, arbetsflöden för hantering av förfrågningar och en intuitiv sida för självbetjäningstjänster för medarbetare som ber om ledighet.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 493bc3abe82103541125914896252b2eae596b38
ms.sourcegitcommit: f38302b9430f2ab3efe91d0a7beff946bc610e8f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/28/2020
ms.locfileid: "3091758"
---
# <a name="overview"></a>Översikt

Dynamics 365 Human Resources hjälper dig att ge dina arbetare bra fördelar. På arbetsytan **tjänstledighet och frånvaro** finns ett flexibel ramverk för att skapa nya frånvaroplaner, arbetsflöden för hantering av förfrågningar och en intuitiv sida för självbetjäningstjänster för medarbetare som ber om ledighet. Analyser hjälper ditt företag att mäta och övervaka ledighetssaldon och förbrukning för dina tjänstledighetsplaner.

## <a name="set-up-leave-and-absence"></a>Ställ in tjänstledighet och frånvaro

Innan du kan skapa tjänstledighetsplaner för dina medarbetare måste du göra något av följande:

- [Konfigurera tjänstledighets- och frånvaroparametrar](hr-leave-and-absence-parameters.md)
- [Skapa en arbetstidskalender](hr-leave-and-absence-working-time-calendar.md)
- [Skapa en ledighetsansökan till arbetsflödet](hr-leave-and-absence-workflow.md)

## <a name="create-and-manage-leave-plans"></a>Skapa och hantera tjänstledighetsplaner

Innan du skapar tjänstledighetsplaner för dina arbetare måste du skapa tjänstledighets- och frånvarotyper. När du har skapat en tjänstledighetsplan kan du registrera arbetare i planen. Du kan även köra processen periodisera, skapa notifieringar och visa analys för dina planer.

- [Konfigurera typer av tjänstledighet och frånvaro](hr-leave-and-absence-types.md)
- [Skapa en plan för tjänstledighet och frånvaro](hr-leave-and-absence-plans.md)
- [Tilldela arbetare till en tjänstledighetsplan](hr-leave-and-absence-enroll.md)
- [Periodisera planer för tjänstledighet och frånvaro](hr-leave-and-absence-accrue.md)
- [Visa analys för tjänstledighet och frånvaro](hr-leave-and-absence-analytics.md)

## <a name="request-time-off-and-manage-requests"></a>Begär ledigt och hantera förfrågningar

Dina medarbetare kan skicka ledighetsansökningar och du kan hantera dem på arbetsytan **medarbetarens självbetjäning**.

- [Begär ledig tid](hr-employee-self-service-request-time-off.md)
- [Hantera tjänstledighets- och frånvaroansökningar](hr-employee-self-service-manage-requests.md)

## <a name="leave-and-absence-preview-features"></a>Funktioner för förhandsgranskning av tjänstledighet och frånvaro

Du kan testa nya funktioner för tjänstledighet och frånvaro i en **begränsad** miljö. Mer information om hur du aktiverar funktionerna för förhandsgransknings finns i [hantera funktioner](hr-admin-manage-features.md). Bland funktionerna för förhandsgranskning är:

- **Tjänstledighets- och frånvaro-kalender** - tjänstledighets- och frånvaroparametrar flyttas från **personalparametrar** till en ny skärm som kallas **tjänstledighets- och frånvaroparametrar**. Den nya skärmen innehåller ny flik för **kalender**. Den här förhandsgranskningen aktiverar bara en del av parametrarna. Du når den nya skärmen från fliken **Länkar** i arbetsytan **ledighet och frånvaro**. Kalendern innehåller:
  - **Företagskalender** - visar alla förfrågningar om medarbetarledighet. Personer med rollen **Personal** har åtkomst till den här kalendern från fliken **länkar** i arbetsytan **tjänstledighet och frånvaro**.
  - **Chef teamkalender** - visar alla direktrapporters ledighetsbegäran. Chefer får åtkomst till kalendern från fliken **mitt team** i självbetjäning för medarbetare under **tjänstledighet och frånvaro**. 

- **Semesterkalender för tjänstledighet och frånvaro** - tjänstledighetstyper inkluderar ett nytt alternativ för **helgdag** som används tillsammans med arbetstidskalendern. Dagar som definieras i semestrar och stängningar betecknas nu som **helgdag** när arbetsdagar skapas. När periodiseringar bearbetas görs justeringar av medarbetare som har tilldelats till kalendern för att redovisa helgdagar på en arbetsdag.

- **Granskning av periodisering av tjänstledighet** - en ny skärm gör det möjligt att granska när periodiseringen har bearbetats och raderats, både av alla medarbetare och enskilda medarbetare. Du når den nya skärmen från fliken **Länkar** i arbetsytan **ledighet och frånvaro**.

- **Ta bort periodisering av tjänstledighet** - du kan nu ta bort periodiseringar för specifika tjänstledighetsplaner. Du når detta nya alternativ från fliken **Länkar** i arbetsytan **ledighet och frånvaro**. För enskilda medarbetare visas det här alternativet i grupperingen **tjänstledighet och frånvaro** i medarbetarprofilen. 

- **Avrundning av periodisering av tjänstledighet** - Nya alternativ för **tjänstledighetstyp** definiera vilken typ av avrundning som ska användas, plus decimalens precision för avrundningen under periodiseringsprocessen. När periodiseringar bearbetas tillämpas avrundningen och precisionen på posterna i periodiseringen. 

- **Konfigurera flera tjänstledighetstyper på en enda tjänstledighetsplan** - en ny kolumn i det periodiseringsschemat för tjänstledighet där du kan definiera flera tjänstledighetstyper i en tjänstledighets- och frånvaroplan med olika periodiseringsscheman. Tidigare fältet **tjänstledighetstyp** tas bort. På medarbetarens registrering visas saldona för tjänstledighetstyperna i en tabell i stället för längst upp på skärmen.

  > [!IMPORTANT]
  > Du kan inte stänga av den här funktionen när du har aktiverat den.

- **Använd en medarbetares heltidslön (FTE) för periodisering** - en ny kolumn i periodiseringsschemat för tjänstledighet gör det möjligt att använda en FTE för periodisering. När periodiseringar bearbetas använder programmet medarbetarens primära befattning och den heltid som definierats för att bestämma det proportionella periodiserade beloppet.

  > [!NOTE]
  > Den här funktionen är bara tillgänglig om du aktiverar **Konfigurera flera ledighetstyper per ledighetsplan**. 
