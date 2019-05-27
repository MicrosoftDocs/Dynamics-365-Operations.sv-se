---
title: Hantering av tjänstledighet och frånvaro
description: Det här avsnittet innehåller en översikt över modulen tjänstledighets- och frånvarohantering.
author: andreabichsel
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2017-07-01
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ebfaeb0696d7200ddf3c715f96a259b91db08e7a
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2019
ms.locfileid: "1519102"
---
# <a name="leave-and-absence-management"></a>Hantering av tjänstledighet och frånvaro

[!include [banner](includes/banner.md)]

Modulen **Tjänstledighet- och frånvarohantering** erbjuder ett flexibelt ramverk för att definiera processen av frånvarohantering. Tjänstledighets- och frånvaroplaner kan skapas för att avgöra hur medarbetare ackumulerar eller beviljas ledighet. När medarbetarna är anmälda till en plan, kan de skicka in ledighetsansökningar till cheferna för godkännande. Med ledighetsuppföljning kan både chefer på första nivån och personalchefer se hur mycket ledig tid som tagits ut, och hur mycket som finns kvar.  

Tjänstledighets- och frånvarohantering innehåller följande funktioner: 

- **Definierar tjänstledighets- och frånvarotyper.**

    Tjänstledighetstyper definierar olika typer av frånvaro som medarbetare kan rapportera. Dessa typer är användardefinierade och kan skräddarsys för din organisation. Vissa typiska tjänstledighetstyper kan vara betald ledighet (PTO, tjänstledighet, kortfristig arbetsoförmåga, jurytjänst (den här typen är specifik för USA) och dödsfall. 

- **Definiera tjänstledighet- och frånvaroplaner som är nivåindelade så att de passar ditt företag.**

    Tjänstledighet och frånvaro kan definieras så att ackumulering inträffar i särskilda frekvenser som exempelvis årligen, varje månad eller var fjortonde dag. Planer kan även definieras som ett anslag, där en enda ackumulering sker på ett visst datum. 

    Tjänstledighetsplaner innehåller ofta nivåer där vissa grupper av anställda får ytterligare fördelar, baserat på hur lång tid som har varit med i organisationen. Dessa användardefinierade nivåer tillåter automatisk registrering i ytterligare förmånstimmar baserat på de datumkriterier som definieras. Tjänstledighetsplaner kan också konfigureras för att framtvinga ett överföringsbelopp eller ett minimisaldo för att förhindra att medarbetare med använder fler förmånstimmar än vad de har ackumulerat. 

    Typiska tjänstledighetsplaner innehåller planer i nivåer som beviljas en förmån på 80 timmars betald ledighet (PTO) för nyanställda, men en fördel på 120 timmar efter 60 månaders tjänst. Ytterligare planer kan ge flytande helgdagar eller positionbaserade förmåner som t.ex. förmånstimmar som endast gäller chefer.

- **Anmäla medarbetare till planer för tjänstledighet och frånvaro individuellt eller genom masstilldelning som baseras på kriterier.**

    Flera projektrelaterade filter kan användas för att tilldela en plan lämna en grupp medarbetare. Personalchefer kan visa en medarbetare om du vill se vilka planer för tjänstledighet och frånvaro som medarbetaren är anmäld till. Personalchefer kan visa alla planer och relaterade medarbetaranmälningar.

- **Skjut upp planer för tjänstledighet och frånvaro**

    Planer för tjänstledighet och frånvaro kan skjutas upp för att göra dem inaktiva och förhindra ytterligare periodiseringar. Ackumuleringar upphör för medarbetare om slutar sin anställning.  

- **Justera rättigheter och bidrag.**

    En medarbetare kan registreras på en högre nivå i planen genom att använda ett arbetarspecifikt datum för att åsidosätta medarbetarens standardplanerbjudande. Medarbetare kan få en manuell justering av deras tjänstledighets- och frånvarosaldon vid tidpunkten för anmälan av planen eller personalen kan göra en manuell justering när som helst. 

- **Använda ett arbetsflöde för ledighetsansökningar.**

     Ett arbetsflöde kan anpassas och tillämpas på ledighetsansökningar för att möta organisationens krav.  

- **Spåra medarbetares frånvarosaldon.**

    Medarbetare, deras chef och personal kan visa tjänstledighets- och frånvarosaldon. Personal kan använda interaktiva rapporter för att spåra anmälningar till en plan och ledighetssaldon efter typ. 

- **Skicka ledighetsansökningar.**

    Medarbetare kan skicka ledighetsansökningar mot sina tillgängliga timmar. Ansökningar kan vara enkla endagsansökningar eller flera dagar ansökningar som omfattar flera typer av tjänstledighet och frånvaro. Om ett arbetsflöde inte är aktiverat kommer ansökan att godkännas automatiskt. Om ett arbetsflöde aktiverats kan godkännandet ske automatiskt eller kräva signering, beroende på hur arbetsflödet är inställt.
