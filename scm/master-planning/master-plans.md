---
title: Huvudplaner
description: "Använda olika huvudplaner för att hantera ditt företags dagliga verksamhet, simulera olika planeringsstrategier som du vill övervaka och implementera en företagspolicy, t ex en princip om tillfredsställande för intern prestanda eller kund."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ReqParameters, ReqPlanSched
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 7911
ms.assetid: a116b7de-3d6d-4321-87ba-5a5d99c2f64e
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 29bb560c11e63938bea73ed8471c27563b546f8f
ms.lasthandoff: 03/31/2017


---

# <a name="master-plans"></a>Huvudplaner

Använda olika huvudplaner för att hantera ditt företags dagliga verksamhet, simulera olika planeringsstrategier som du vill övervaka och implementera en företagspolicy, t ex en princip om tillfredsställande för intern prestanda eller kund. 

Du kan konfigurera huvudplaner på sidan **Huvudplaner**.

Det finns två typer av planer:
-   **Statisk plan** – Beräkningen av huvudplaneringen använder aktuella data för att generera en nettobehovsplan. Den här planen förändras inte förrän nästa gång du kör huvudplanering. Det är en verksamhetsplan som olika anställda, till exempel en inköpare eller produktionsplanerare, kan använda för att basera sina beslut på och utföra sina dagliga uppgifter och aktiviteter.
-   **Dynamisk plan** – Den här planen börjar med samma nettobehovsplan som genererades av huvudplaneringen. Du kan dock uppdatera den dynamiska planen varje gång som huvuddata ändras. Det kan till exempel vara när du skapar en ny försäljningsorder. Det blir då lättare att övervaka ändringar av order och artikeltillgänglighet utan att ändra den statiska planen som andra använder i sina arbetsprocesser.

Ett företag kan välja att arbeta med bara en dynamisk plan eller det kan använda både en statisk och dynamisk plan. Du kan dessutom konfigurera en huvudplan så att den återspeglar en viss strategi eller fokuserar på ett problem. Exempel är som följer:
-   Ställa in högre lagernivåer för att förhindra brist.
-   Ställa in längre säkerhetsmarginaler för att skydda sig mot opålitliga leverantörer.

Du kan också ställa in den dynamiska planen så att den uppdateras med den nya behovsplanen varje gång du kör huvudplanering. Du kan ange inställningarna på sidan **Huvudplaneringsparametrar**.



<a name="see-also"></a>Se även
--------

[Disponeringsinställningar](coverage-settings.md)

[Separera taktisk och avgörande planering för huvudplanering](http://blogs.msdn.com/b/axmfg/archive/2012/10/12/separating-tactical-and-operative-planning-for-master-scheduling.aspx)

[Master Planning: En statisk och dynamisk huvudplan eller använda en plan?](https://community.dynamics.com/ax/b/msdynaxlessonslearned/archive/2014/01/16/master-planning-use-a-static-and-dynamic-master-plan-or-use-one-plan)

