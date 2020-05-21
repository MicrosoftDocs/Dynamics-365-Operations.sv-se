---
title: Översikt
description: I Dynamics 365 Human Resources ger arbetsytan tjänstledighet och frånvaro finns ett flexibel ramverk för att skapa nya frånvaroplaner, arbetsflöden för hantering av förfrågningar och en intuitiv sida för självbetjäningstjänster för medarbetare som ber om ledighet.
author: andreabichsel
manager: AnnBe
ms.date: 04/30/2020
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
ms.openlocfilehash: 2bb123b808615ff7d770c7c6b83338a32d922be3
ms.sourcegitcommit: de217452a85429675994e9cc0e06eb4821cab3e5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/30/2020
ms.locfileid: "3325775"
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

- **Skjuta upp tjänstledighet** - Du kan skjuta upp tjänstledighet och frånvaro i personal för en medarbetare. Om du skjuter upp tjänstledighet avbryts tjänstledigheten för de valda tjänstledighetstyperna. Om uppskjutningen sker efter att en periodisering har bearbetats, skapar skjuta upp ledighet en proportionell justering av medarbetarens ledighetssaldo. Du kan även inkludera orsakskoder när du pausar en medarbetares tjänstledighet. Användarupplevelsen har uppdaterats för att visa paus. 

- **Överför regler** - Du kan ange en överför tjänstledighetstyp för överföringsaldon där överför justeringar överförs. Om en medarbetare till exempel överförs 10 dagar kan du välja en annan tjänstledighetstyp för de 10 dagarna. 

- **Inkludera orsakskod och kommentarer för justeringar** – Du kan inkludera en orsakskod och en kommentar när du gör en justering av en medarbetares ledighetssaldo. 

- **Övergång till tjänstledighet och frånvaroparametrar** – Nu behöver du bara använda parametrar för tjänstledighet och frånvaro istället för HR-parametrar. 
