---
title: Lean manufacturing – Kanban-jobbplanering
description: Det här avsnittet innehåller information om visuell kontroll över kanban-jobbplanering och olika sätt för att schemalägga kanban-jobb.
author: johanhoffmann
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanBoardScheduleJobForward, KanbanBoardShowJobs, KanbanJobSchedulingListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 52961
ms.assetid: fe3b4822-6140-4b02-bebb-1fc17be2bce8
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f70c3cf44ce90b13250836013636920267d2016d
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/29/2021
ms.locfileid: "7570235"
---
# <a name="kanban-job-scheduling-for-lean-manufacturing"></a>Lean manufacturing – Kanban-jobbplanering

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller information om visuell kontroll över kanban-jobbplanering och olika sätt för att schemalägga kanban-jobb.  

**Kanban-jobbplanering** sidan ger en visuell kontroll över scheman för lean manufacturing arbete celler. Den ger en översikt över alla Kanbankort jobb och skaffar flera filtrering kapaciteter. Från den här sidan kan du flytta till alla andra sidor som är relaterade till kanban konfiguration och utförande.

## <a name="automatic-scheduling-of-kanban-jobs"></a>Automatisk schemaläggning av kanban jobb
Tidsplanering kan aktiveras automatiskt om du anger parametern **Automatisk planeringskvantitet** på kanban-regeln. Om du anger **Automatisk planeringskvantitet** som **1**, planeras varje kanban-job omedelbart när det skapas. Resultatet är en serie först ut, först till kvarn. Om du ställer in **automatisk planering kvantitet** till ett värde som är större än 1, kanban jobb grupperas innan de är planerade. 

Detta koncept gör kanban storlekar att reduceras under de faktiska ekonomiska standardstorlekar. Exempelvis är 30 den ekonomiska batchstorleken för en viss artikel (eller artikelfamilj). Istället för att skapa kanbans som använder produktkvantitet 30 kan du konfigurera kanban-regeln så att den har en produktkvantitet på 10 och ett värde för **Automatisk planeringskvantitet** på **3**. Trots att automatisk planering av scheman kanban jobb för flödesgrupp bara när tre oplanerade jobb finns, det är helt transparent för planerare och verkstadsgolvet arbetsledare som två oplanerade jobb kanske väntar på avrättning. Den planerare eller shop floor manager kan sedan ta dessa två jobb i produktionen genom att manuellt planera dem eller skapa ytterligare kanban.

## <a name="manual-scheduling"></a>Manuell planering
För manuell planering Microsoft Dynamics AX 2012 introducerade planeringstavlan för kanban. Manuell planering kan kombineras med automatisk scheduling. Kanban planering styrelsen låter dig planera och avplanera jobb, flyttat dem i sekvens, eller flytta dem från period till period. Jobb som är baserat på en kanban-regel om **automatisk planering** värdet är mer än **0** kan vara manuellt oplanerade. Dessa arbeten kommer att omplaneras när nästa automatiska planering händelse inträffar (som när en ny kanban skapas). Följande alternativ är tillgängliga för manuell planering:

-   **Schema** schema de markerade jobben enligt deras förfallodatum. (Detta alternativ liknar automatisk planering).
-   **Planera framåt från datum** försöker planera de markerade jobben enligt deras förfallodatum men begränsar resultatet genom att använda den angivna tidigaste startdatum.
-   **Bakåt** flyttar den valda schemalagda jobb bakåt i sekvensen inom perioden.
-   **Framåt** flyttar den valda schemalagda jobb framåt i sekvensen med period.
-   **Föregående period** flyttar den valda schemalagda jobb till början eller slutet av föregående period.
-   **Nästa period** flyttar den valda schemalagda jobb till början eller slutet av nästa period.
-   **Plan** &gt; **Återställ jobbstatus** låter dig avplanera ett planerat jobb.

## <a name="lean-scheduling-groups"></a>Lean planering grupperna
Varje färg representerar en lean-planeringsgrupp. Lean planering grupperna kan definieras fritt som generiska grupper eller grupper som tillhör en enda flödesgrupp. Objekt och dimensioner kan användas fritt till cbs-grupper. Exempelvis i en målning cell, ett schema grupp kan representera en färg av produkten. I arbetet som drivs av särskilda verktyg, Poster kan grupperas efter verktygets krav och en förpackning flödesgrupp kan gruppera artiklar efter förpackningsmall. Användning av färger för lean planering grupperna är valfri men rekommenderas. Det ger bättre insyn i statusen för planen. Det är exempelvis väldigt lätt att se vilka färger som framställs vilken dag, och du kan omedelbart se hur detta arbete kan optimeras.

## <a name="work-cell-capacity-and-period-capacity"></a>Flödesgrupp kapacitet och tid kapacitet
Kapaciteten för en lean arbete cell är alltid samtidiga kapacitet. Med andra ord, flera jobb kan vara aktiv i en cell på samma gång. Kapaciteten kan spåras i två lägen: genomströmning och timmar.

### <a name="throughput"></a>Genomflöde

Kapaciteten för en flödesgrupp definieras av den genomsnittliga kapaciteten kvantitet av en referensperiod (vanlig arbetsdag, vecka eller månad). Den faktiska kapaciteten per dag eller vecka beräknas sedan baserat på arbetstiden för den kalender som är kopplad till arbetet cell. Den kapacitet som är laddad med jobbet är den kvantitet av jobbet, justeras av genomströmning förhållandet i flödesgrupp.

### <a name="hours"></a>Timmar

Den tillgängliga kapaciteten per dag eller vecka definieras av den kalender som är kopplad till arbetet cell. Den kapacitet som är laddad med jobbet är cykeltid aktivitet, justerat med den kvantitet (standard aktivitet kvantitet kontra verkliga jobb kvantitet) och genomgång av kursen i flödesgrupp.

#### <a name="period-capacity-factbox"></a>Period kapacitet faktaruta

**Kanban scheduling för jobb** lista sidan innehåller en faktaruta som visar tillgängliga och bokat tid kapacitet för vald flödesgrupp. Beroende på det valda schemat perioder i produktionsflödet modell, perioder visa dagar eller veckor.

## <a name="additional-resources"></a>Ytterligare resurser





[!INCLUDE[footer-include](../../includes/footer-banner.md)]