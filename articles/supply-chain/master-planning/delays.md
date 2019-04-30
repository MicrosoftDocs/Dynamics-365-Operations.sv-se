---
title: Fördröjningar
description: Det här ämnet innehåller information om fördröjda data i huvudplaneringen. Ett fördröjt datum är ett realistiskt förfallodatum som en transaktion får om det tidigaste uppfyllelsedatumet som huvudplaneringen beräknar infaller efter begärt datum.
author: roxanadiaconu
manager: AnnBe
ms.date: 03/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqTransFuturesListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19311
ms.assetid: 5ffb1486-2e08-4cdc-bd34-b47ae795ef0f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7c26fedf15118a304469604527c33a25871356be
ms.sourcegitcommit: 8eac5eee94bb32143df44c82a2dfdbe903967af8
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/20/2019
ms.locfileid: "878320"
---
# <a name="delays"></a>Fördröjningar

[!include [banner](../includes/banner.md)]

Det här ämnet innehåller information om fördröjda data i huvudplaneringen. Ett fördröjt datum är ett realistiskt förfallodatum som en transaktion får om det tidigaste uppfyllelsedatumet som huvudplaneringen beräknar infaller efter begärt datum.

Huvudplaneringen kan beräkna det tidigaste uppfyllelsedatumet för en transaktion baserat på produktionstiderna, materialtillgänglighet, kapacitettillgänglighet och olika planläggningsparametrar. 

Om en huvudplanering beräknar ett orderdatum som infaller före det aktuella datumet, kan inte ordern expedieras i tid. Därför är ordern försenad. I det här fallet inkluderar huvudplaneringen framåtplaner för ordern från aktuellt datum och som inkluderar ledtider. Dessa ledtider startar komponentartiklar på lägre nivå. Ordern får sedan ett försenat datum. Ett försenat datum är ett realistiskt förfallodatum baserat på aktuella uppgifter. I huvudplaneringen beräknas också antalet fördröjningsdagar. 

I vissa fall kan du välja att inte att beräkna fördröjningar, till exempel när användare vet att de kan påskynda ledtider genom att välja alternativa leveranssätt. 

Du kan konfigurera hur förseningar beräknas för en disponeringsgrupp. Du kan sedan koppla disponeringsgruppen till en artikel vid ett senare tillfälle. 

På sidan **Huvudplaneringsparametrar** kan du ange starttiden för beräkningen av förseningar. Om en order expedieras efter den här tiden läggs en försening på en dag till i orderns förseningsdatum. 

> OBS!} I tidigare versioner kallades beräknade förseningar *leveransplansmeddelanden*, förseningsdatumet kallades *leveransplansdatum* och en försenad transaktion kallades *en transaktion som är inställd på ett datum i framtiden*.

## <a name="desired-date"></a>Önskat datum

På sidan **planerad order** under fliken **Förseningar** är **önskat datum** för den planerade ordern. Önskat datum för en planerad order är grunddata för förseningar, vilket är ett beräknat datum som är lika med **begärt datum** beräknat från **nettobehovet**. Om den planerade ordern är en strukturlisterad, produktionsrad eller kanban-rad, baseras önskat datum på **Behovsdatum** och det önskade datumet visas på sidan **Planerad order**.

<a name="additional-resources"></a>Ytterligare resurser
--------

[Disponeringsinställningar](coverage-settings.md)
