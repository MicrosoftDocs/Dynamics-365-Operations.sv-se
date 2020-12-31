---
title: Uteslut produkter som har specifika produktlivscykeltillstånd
description: I det här avsnittet beskrivs hur du utesluter produkter baserat på deras livscykeltillstånd när funktionen för optimering av planeringen används.
author: ChristianRytt
manager: tfehr
ms.date: 11/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2019-11-13
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 371d98eefa482fc3e430f2f0977ddffb9dd0d30e
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/25/2020
ms.locfileid: "4645102"
---
# <a name="exclude-products-that-have-specific-product-lifecycle-states"></a>Uteslut produkter som har specifika produktlivscykeltillstånd

[!include [banner](../../includes/banner.md)]

Frisläppta produkter och frisläppta produktversioner inkluderar fältet **produkt livscykeltillstånd**. I det här fältet kan du bland annat bestämma vilka produkter som ska inkluderas under huvudplaneringen. Du kan lägga till, ta bort och redigera livscykeltillstånd efter behov genom att gå till **produktinformationshanterings \> installation \> produktcykeltillstånd**. Ställ in för varje produkts livscykeltillstånd alternativet **Är aktiv för planering** till *Ja* om produkter som har den staten ska inkluderas under huvudplaneringen. När alternativet är inställt på *Nej*, kommer associerade produkter och varianter att undantas från all huvudplanering och alla beräkningar på strukturnivån.

Släppta produkter och varianter där fältet **Produktens livscykeltillstånd** lämnas tomt behandlas som om de har ett tillstånd för produktens livscykel där **Är aktiv för planering** anges till *Ja*. De kommer med andra ord att inkluderas under huvudplaneringen.

> [!NOTE]
> För att undvika onödiga förslag på leveranser rekommenderar vi starkt att du associerar alla föråldrade släppta produkter och varianter till ett produktlivscykeltillstånd där **Är aktiv för planering** anges till *Nej*. Den här metoden är särskilt viktig när du arbetar med varianter av produktkonfiguration som inte kan återanvändas, eftersom det bidrar till att undvika avfall.

## <a name="related-resources"></a>Relaterade resurser

Mer information om tillstånd för produktens livscykel finns i [Produktens livscykeltillstånd - översikt](../../pim/product-lifecycle.md).

Detaljerad information som inkluderar steg för hur du använder produktlivscykeltillstånd för att undanta produkter från huvudplanering och strukturlistenivåberäkningar, se [skapa ett produktlivscykeltillstånd från huvudplaneringen](../../pim/tasks/exclude-products-master-planning.md).