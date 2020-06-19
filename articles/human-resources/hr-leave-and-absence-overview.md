---
title: Översikt
description: I Dynamics 365 Human Resources ger arbetsytan tjänstledighet och frånvaro finns ett flexibel ramverk för att skapa nya frånvaroplaner, arbetsflöden för hantering av förfrågningar och en intuitiv sida för självbetjäningstjänster för medarbetare som ber om ledighet.
author: andreabichsel
manager: AnnBe
ms.date: 06/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ec72d2d741f7f8428a7daa97bb982e9fc00b8c3f
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2020
ms.locfileid: "3428977"
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

- [Begära ledig tid](hr-employee-self-service-request-time-off.md)
- [Hantera begäranden om ledighet och frånvaro](hr-employee-self-service-manage-requests.md)

## <a name="leave-and-absence-known-issues"></a>Lämna och kända frånvaroproblem

### <a name="rounding-precision"></a>Avrundningsprecision

Du kan inte ange **avrundningsprecision** när du anger **avrundningstyp**. Du kan bara ange **avrundningsprecision** genom att använda entiteten **tjänstledighet och frånvaro**. 

1. Från **tjänstledighets- och frånvarotyper**, välj **öppna i Excel** för att öppna entiteten **tjänstledighet och frånvarotyp**.

2. När filen har öppnats och aktiverats väljer du **Design**.

3. I tabellen **tjänstledighets- och frånvarotyper**, välj pennalternativ för att redigera.

4. Välj **RoundingPrecision** och **RoundingType** och välj sedan **Lägg till** i listan över fält.

5. Välj **Uppdatera**och välj sedan **Klart**.

6. Ange eller välj **avrundningstyp** för varje tjänstledighetstyp om de inte redan har angetts. 

7. Ange **avrundningsprecision** för lämpliga typer.

8. Välj **publicera** om du vill skicka ändringarna till personal.

## <a name="leave-and-absence-preview-features"></a>Funktioner för förhandsgranskning av tjänstledighet och frånvaro

Du kan testa nya funktioner för tjänstledighet och frånvaro i en **begränsad** miljö. Mer information om hur du aktiverar funktionerna för förhandsgransknings finns i [hantera funktioner](hr-admin-manage-features.md). 

[!include [banner](includes/preview-feature.md)]

Bland funktionerna för förhandsgranskning är:

- **Lämna periodisering per företag eller plan** - du kan köra periodiseringsprocessen antingen för alla företag eller för ett enskilt företag. Du kan också köra periodiseringsprocessen för en viss plan för tjänstledighet och frånvaro för ett visst företag. 

- **Köp tjänstledighet** – du kan aktivera och skapa policyer för tjänstledighet som medarbetare kan använda för att skicka in inköpsförfrågningar. Medarbetare kan skicka inköpsförfrågningar och få saldon uppdateras automatiskt för att återspegla begäran.  

- **Lägg till bilagor till godkända ansökan om tjänstledighet** – du kan lägga till en bilaga på en begäran om att lämna en begäran som redan har godkänts. 

