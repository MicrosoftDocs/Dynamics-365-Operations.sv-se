---
title: Huvudplaner
description: "Använd olika huvudplaner för att hantera ditt företags dagliga verksamhet, simulera olika planeringsstrategier som du vill övervaka, och implementera en företagspolicy, till exempel en policy för intern prestanda eller kundvård."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqParameters, ReqPlanSched
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 7911
ms.assetid: a116b7de-3d6d-4321-87ba-5a5d99c2f64e
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: c530284f83f13bce6941bf889aaddbb1a1e82dae
ms.contentlocale: sv-se
ms.lasthandoff: 05/08/2018

---

# <a name="master-plans"></a>Huvudplaner

[!include [banner](../includes/banner.md)]

Använd olika huvudplaner för att hantera ditt företags dagliga verksamhet, simulera olika planeringsstrategier som du vill övervaka, och implementera en företagspolicy, till exempel en policy för intern prestanda eller kundvård. 

Du kan konfigurera huvudplaner på sidan **Huvudplaner**.

Det finns två typer av planer:
-   **Statisk plan** – Beräkningen av huvudplaneringen använder aktuella data för att generera en nettobehovsplan. Den här planen förändras inte förrän nästa gång du kör huvudplanering. Det är en verksamhetsplan som olika anställda, till exempel en inköpare eller produktionsplanerare, kan använda för att basera sina beslut på och utföra sina dagliga uppgifter och aktiviteter.
-   **Dynamisk plan** – Den här planen börjar med samma nettobehovsplan som genererades av huvudplaneringen. Du kan dock uppdatera den dynamiska planen varje gång som huvuddata ändras. Det kan till exempel vara när du skapar en ny försäljningsorder. Det blir då lättare att övervaka ändringar av order och artikeltillgänglighet utan att ändra den statiska planen som andra använder i sina arbetsprocesser.

Ett företag kan välja att arbeta med bara en dynamisk plan eller det kan använda både en statisk och dynamisk plan. Du kan dessutom konfigurera en huvudplan så att den återspeglar en viss strategi eller fokuserar på ett problem. Exempel är som följer:
-   Ställa in högre lagernivåer för att förhindra brist.
-   Ställa in längre säkerhetsmarginaler för att skydda sig mot opålitliga leverantörer.

Du kan också ställa in den dynamiska planen så att den uppdateras med den nya behovsplanen varje gång du kör huvudplanering. Du kan ange inställningarna på sidan **Huvudplaneringsparametrar**.



<a name="additional-resources"></a>Ytterligare resurser
--------

[Disponeringsinställningar](coverage-settings.md)

[Separera taktisk och operativ planering för huvudplanering](http://blogs.msdn.com/b/axmfg/archive/2012/10/12/separating-tactical-and-operative-planning-for-master-scheduling.aspx)

[Huvudplanering: Använda en statisk och dynamisk huvudplan eller en enda plan?](https://community.dynamics.com/ax/b/msdynaxlessonslearned/archive/2014/01/16/master-planning-use-a-static-and-dynamic-master-plan-or-use-one-plan)




