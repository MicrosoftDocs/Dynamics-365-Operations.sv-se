---
title: Associera ett produktlivscykeltillstånd till en frisläppt produktmall
description: Nedan beskrivs proceduren för att tilldela ett livscykeltillstånd till en frisläppt produktmall och dess varianter.
author: cvocph
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 62078025623a0cfc1ed6797c84907c7872dfaf38095855240b306e08f3decca7
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6716526"
---
# <a name="assign-a-product-lifecycle-state-to-a-released-product-master"></a>Associera ett produktlivscykeltillstånd till en frisläppt produktmall

[!include [banner](../../includes/banner.md)]

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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]