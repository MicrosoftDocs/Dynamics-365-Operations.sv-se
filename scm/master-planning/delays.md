---
title: "Fördröjningar"
description: "Det här avsnittet innehåller information om fördröjda data i huvudplaneringen. Ett fördröjt datum är ett realistiskt förfallodatum som en transaktion får om det tidigaste uppfyllelsedatumet som huvudplaneringen beräknar infaller efter begärt datum."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ReqTransFuturesListPage
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 19311
ms.assetid: 5ffb1486-2e08-4cdc-bd34-b47ae795ef0f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 9113c7728c5d23b70e3809bab31136aff63c6acf
ms.lasthandoff: 03/31/2017


---

# <a name="delays"></a>Fördröjningar

Det här avsnittet innehåller information om fördröjda data i huvudplaneringen. Ett fördröjt datum är ett realistiskt förfallodatum som en transaktion får om det tidigaste uppfyllelsedatumet som huvudplaneringen beräknar infaller efter begärt datum.

Huvudplaneringen kan beräkna det tidigaste uppfyllelsedatumet för en transaktion baserat på produktionstiderna, materialtillgänglighet, kapacitettillgänglighet och olika planläggningsparametrar. 

Om en huvudplanering beräknar ett orderdatum som infaller före det aktuella datumet, kan inte ordern expedieras i tid. Därför är ordern försenad. I det här fallet inkluderar huvudplaneringen framåtplaner för ordern från aktuellt datum och som inkluderar ledtider. Dessa ledtider startar komponentartiklar på lägre nivå. Ordern får sedan ett försenat datum. Ett försenat datum är ett realistiskt förfallodatum baserat på aktuella uppgifter. I huvudplaneringen beräknas också antalet fördröjningsdagar. 

I vissa fall kan du välja att inte att beräkna fördröjningar, till exempel när användare vet att de kan påskynda ledtider genom att välja alternativa leveranssätt. 

Du kan konfigurera hur förseningar beräknas för en disponeringsgrupp. Du kan sedan koppla disponeringsgruppen till en artikel vid ett senare tillfälle. 

På sidan **Huvudplaneringsparametrar** kan du ange starttiden för beräkningen av förseningar. Om en order expedieras efter den här tiden läggs en försening på en dag till i orderns förseningsdatum. 

**Obs!** i tidigare versioner beräknade förseningar kallas *leveransplansmeddelanden*, försenade datumet kallades den *leveransplansdatum*, och en fördröjd transaktion som kallas *en transaktion som framtida uppsättning*.

<a name="see-also"></a>Se även
--------

[Disponeringsinställningar](coverage-settings.md)


