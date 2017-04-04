---
title: "Kanban-jobbet tidsplanering för lean manufacturing"
description: "Det här avsnittet innehåller information om visuell kontroll över kanban-jobbplanering och olika sätt för att schemalägga kanban-jobb."
author: YuyuScheller
manager: AnnBe
ms.date: 2016-02-24 15 - 02 - 36
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: KanbanBoardScheduleJobForward, KanbanBoardShowJobs, KanbanJobSchedulingListPage
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 52961
ms.assetid: fe3b4822-6140-4b02-bebb-1fc17be2bce8
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 062cbbc8a4fd3b4dc738f24ee0606a3741736377
ms.lasthandoff: 03/29/2017


---

# <a name="kanban-job-scheduling-for-lean-manufacturing"></a>Kanban-jobbet tidsplanering för lean manufacturing

Det här avsnittet innehåller information om visuell kontroll över kanban-jobbplanering och olika sätt för att schemalägga kanban-jobb.  

**Kanban-jobbplanering** sidan ger en visuell kontroll över scheman för lean manufacturing arbete celler. Den ger en översikt över alla Kanbankort jobb och skaffar flera filtrering kapaciteter. Från den här sidan kan du flytta till alla andra sidor som är relaterade till kanban konfiguration och utförande.

## <a name="automatic-scheduling-of-kanban-jobs"></a>Automatisk schemaläggning av kanban jobb
Tidsplanering kan aktiveras automatiskt om du anger det **automatisk planering kvantitet** parameter på kanban-regeln. Om du ställer in **automatisk planering kvantitet** till **1**, varje kanban-jobbet planeras omedelbart när den skapas. Resultatet är en serie först ut, först till kvarn. Om du ställer in**automatisk planering kvantitet** till ett värde som är större än 1, kanban jobb grupperas innan de är planerade. Detta koncept gör kanban storlekar att reduceras under de faktiska ekonomiska standardstorlekar. Exempelvis är 30 ekonomiska batchstorleken för en viss artikel (eller artikelfamiljen). Istället för att skapa kanbans som använder produktkvantitet 30, konfigureras kanban-regeln så att den har en produktkvantitet 10 och en ** automatisk planering kvantitet ** värdet för **3**. Trots att automatisk planering av scheman kanban jobb för flödesgrupp bara när tre oplanerade jobb finns, det är helt transparent för planerare och verkstadsgolvet arbetsledare som två oplanerade jobb kanske väntar på avrättning. Den planerare eller shop floor manager kan sedan ta dessa två jobb i produktionen genom att manuellt planera dem eller skapa ytterligare kanban.

## <a name="manual-scheduling"></a>Manuell planering
För manuell planering, Microsoft Dynamics AX 2012 introducerade kanban scheduling brädan. Manuell planering kan kombineras med automatisk scheduling. Kanban planering styrelsen låter dig planera och avplanera jobb, flyttat dem i sekvens, eller flytta dem från period till period. Jobb som är baserat på en kanban-regel om **automatisk planering** värdet är mer än **0** kan vara manuellt oplanerade. Dessa arbeten kommer att omplaneras när nästa automatiska planering händelse inträffar (som när en ny kanban skapas). Följande alternativ är tillgängliga för manuell planering:

-   **Schema** schema de markerade jobben enligt deras förfallodatum. (Detta alternativ liknar automatisk planering).
-   **Planera framåt från datum** försöker planera de markerade jobben enligt deras förfallodatum men begränsar resultatet genom att använda den angivna tidigaste startdatum.
-   **Bakåt** flyttar den valda schemalagda jobb bakåt i sekvensen inom perioden.
-   **Framåt** flyttar den valda schemalagda jobb framåt i sekvensen med period.
-   **Föregående period** flyttar den valda schemalagda jobb till början eller slutet av föregående period.
-   **Nästa period** flyttar den valda schemalagda jobb till början eller slutet av nästa period.
-   **Planera**&gt;**Återställ jobbstatus** kan du unschedule ett schemalagt jobb.

## <a name="lean-scheduling-groups"></a>Lean planering grupperna
Varje färg representerar en lean-planeringsgrupp. Lean planering grupperna kan definieras fritt som generiska grupper eller grupper som tillhör en enda flödesgrupp. Objekt och dimensioner kan användas fritt till cbs-grupper. Exempelvis i en målning cell, ett schema grupp kan representera en färg av produkten. I arbetet som drivs av särskilda verktyg, Poster kan grupperas efter verktygets krav och en förpackning flödesgrupp kan gruppera artiklar efter förpackningsmall. Användning av färger för lean planering grupperna är valfri men rekommenderas. Det ger bättre insyn i status för planen. Exempelvis är det lätt att se vilka färger som produceras på vilken dag och du kan direkt se hur detta fungerar kan optimeras.

## <a name="work-cell-capacity-and-period-capacity"></a>Flödesgrupp kapacitet och tid kapacitet
Kapaciteten för en lean arbete cell är alltid samtidiga kapacitet. Med andra ord, flera jobb kan vara aktiv i en cell på samma gång. Kapaciteten kan spåras i två lägen: genomströmning och timmar.

### <a name="throughput"></a>Genomflöde

Kapaciteten för en flödesgrupp definieras av den genomsnittliga kapaciteten kvantitet av en referensperiod (vanlig arbetsdag, vecka eller månad). Den faktiska kapaciteten per dag eller vecka beräknas sedan baserat på arbetstiden för den kalender som är kopplad till arbetet cell. Den kapacitet som är laddad med jobbet är den kvantitet av jobbet, justeras av genomströmning förhållandet i flödesgrupp.

### <a name="hours"></a>Timmar

Den tillgängliga kapaciteten per dag eller vecka definieras av den kalender som är kopplad till arbetet cell. Den kapacitet som är laddad med jobbet är cykeltid aktivitet, justerat med den kvantitet (standard aktivitet kvantitet kontra verkliga jobb kvantitet) och genomgång av kursen i flödesgrupp.

#### <a name="period-capacity-factbox"></a>Period kapacitet faktaruta

**Kanban scheduling för jobb** lista sidan innehåller en faktaruta som visar tillgängliga och bokat tid kapacitet för vald flödesgrupp. Beroende på det valda schemat perioder i produktionsflödet modell, perioder visa dagar eller veckor.

<a name="see-also"></a>Se även
--------


