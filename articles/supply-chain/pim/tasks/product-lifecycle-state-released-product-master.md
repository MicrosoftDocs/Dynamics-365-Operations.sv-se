---
title: Associera ett produktlivscykeltillstånd till en frisläppt produktmall
description: Nedan beskrivs proceduren för att tilldela ett livscykeltillstånd till en frisläppt produktmall och dess varianter.
author: cvocph
manager: AnnBe
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dd9d40bb331b9e024617c8be55330dfce8ba1cc6
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "309482"
---
# <a name="assign-a-product-lifecycle-state-to-a-released-product-master"></a>Associera ett produktlivscykeltillstånd till en frisläppt produktmall

[!include [task guide banner](../../includes/task-guide-banner.md)]

Nedan beskrivs proceduren för att tilldela ett livscykeltillstånd till en frisläppt produktmall och dess varianter. Förutsättning: Du behöver spela uppgiftsguiden ”skapa ett nytt tillstånd för produktlivscykel” först för att se till att minst ett produktlivscykeltillstånd skapas innan du kan spela upp den här uppgiftsguiden.


## <a name="find-a-released-product-master"></a>Hitta den frisläppta produktmallen
1. Gå till Produktinformationshantering > Produkter > Frisläppta produkter.
2. Hitta och markera önskad post i listan.

> [!NOTE]
> En produktmall har produktundertypen Produktmall.  

## <a name="update-the-lifecycle-state"></a>Uppdatera livscykeltillståndet
1. Klicka på Redigera.
2. Ange eller välj ett värde i fältet produktlivscykeltillstånd.
3. Klicka på Spara.
4. Klicka på Ja.

> [!NOTE]
> Om Ja väljs uppdateras även alla relaterade frisläppta produktvarianter som har samma ursprungliga tillstånd, eftersom frisläppt produktmall även uppdateras till det nya produktlivscykeltillståndet. Om Nej är markerat kommer alla varianter behålla sina verkliga tillstånd. Varianter som har ett annat produktlivscykeltillstånd än den frisläppta produktmallen uppdateras inte.  

## <a name="verify-the-lifecycle-state-of-the-variants"></a>Kontrollera livscykelstatus för varianterna
1. Klicka på Frisläppta produktvarianter.

> [!NOTE]
> Observera att alla varianter har ärvt det valda livscykeltillståndet från den frisläppt produktmallen.  

2. Markera vald rad i listan.
3. Ange eller välj ett värde i fältet produktlivscykeltillstånd.

