---
title: Fördröjningar
description: Det här avsnittet innehåller information om fördröjda data i huvudplaneringen. Ett fördröjt datum är ett realistiskt förfallodatum som en transaktion får om det tidigaste uppfyllelsedatumet som huvudplaneringen beräknar infaller efter begärt datum.
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
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
ms.openlocfilehash: a87b19732f413aa2844101f76dea83535da86599
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "359622"
---
# <a name="delays"></a>Fördröjningar

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller information om fördröjda data i huvudplaneringen. Ett fördröjt datum är ett realistiskt förfallodatum som en transaktion får om det tidigaste uppfyllelsedatumet som huvudplaneringen beräknar infaller efter begärt datum.

Huvudplaneringen kan beräkna det tidigaste uppfyllelsedatumet för en transaktion baserat på produktionstiderna, materialtillgänglighet, kapacitettillgänglighet och olika planläggningsparametrar. 

Om en huvudplanering beräknar ett orderdatum som infaller före det aktuella datumet, kan inte ordern expedieras i tid. Därför är ordern försenad. I det här fallet inkluderar huvudplaneringen framåtplaner för ordern från aktuellt datum och som inkluderar ledtider. Dessa ledtider startar komponentartiklar på lägre nivå. Ordern får sedan ett försenat datum. Ett försenat datum är ett realistiskt förfallodatum baserat på aktuella uppgifter. I huvudplaneringen beräknas också antalet fördröjningsdagar. 

I vissa fall kan du välja att inte att beräkna fördröjningar, till exempel när användare vet att de kan påskynda ledtider genom att välja alternativa leveranssätt. 

Du kan konfigurera hur förseningar beräknas för en disponeringsgrupp. Du kan sedan koppla disponeringsgruppen till en artikel vid ett senare tillfälle. 

På sidan **Huvudplaneringsparametrar** kan du ange starttiden för beräkningen av förseningar. Om en order expedieras efter den här tiden läggs en försening på en dag till i orderns förseningsdatum. 

**Obs!** I tidigare versioner kallades beräknade förseningar *leveransplansmeddelanden*, förseningsdatumet kallades *leveransplansdatum* och en försenad transaktion kallades *en transaktion som är inställd på ett datum i framtiden*.

<a name="additional-resources"></a>Ytterligare resurser
--------

[Disponeringsinställningar](coverage-settings.md)



