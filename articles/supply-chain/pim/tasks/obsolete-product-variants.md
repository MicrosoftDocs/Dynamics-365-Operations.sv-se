---
title: Sök efter inaktuella produktvarianter
description: Den här proceduren visar hur du hittar föråldrade frisläppta produkter eller produktvarianter och hur du associerar ett produktlivscykeltillstånd till de föråldrade produkterna.
author: cvocph
manager: tfehr
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 33f16cf8c731dc1a954ed94229b2a833510dac4f
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5245189"
---
# <a name="find-obsolete-product-variants"></a>Sök efter inaktuella produktvarianter 

[!include [banner](../../includes/banner.md)]

Den här proceduren visar hur du hittar föråldrade frisläppta produkter eller produktvarianter och hur du associerar ett produktlivscykeltillstånd till de föråldrade produkterna. Förutsättning: Du måste definiera minst ett produktlivscykeltillstånd som har inaktiverats för planering innan du kan spela upp denna uppgiftsguide.


## <a name="run-a-simulation"></a>Kör en simulering
1. Gå till produktinformationshantering > periodiska uppgifter > ändra status för gamla produkter.
2. Ange eller välj ett värde i fältet Nytt produktlivscykeltillstånd.
3. Välj Ja i fältet Kör en simulering utan att uppdatera produktdata.
4. Ange ett nummer i fältet Undanta produkter som har skapats inom detta antal dagar.
5. Ange ett nummer i fältet Undanta produkter som används i transkationer inom detta antal dagar.
6. Expandera avsnittet Poster som ska ingå.
7. Klicka på Filter.
8. Markera vald rad i listan.
9. Ange ett värde i fältet Kriterier.
10. Klicka på OK.
11. Klicka på OK.

> [!NOTE]
> Du rekommenderas att köra simuleringen i batch om du tänker söka ett stort antal produkter. Kontrollera också att simuleringen inte körs under den mest aktiva arbetstiden för företaget.  

## <a name="review-the-simulation-results"></a>Granska simuleringsresultatet.
1. Gå till produktinformationshantering > förfrågningar och rapporter > Underhållshistorik för produktlivscykeltillstånd.
   
> [!NOTE]
> På den här sidan kan du också granska resultaten för simulering och bedöma hur många produkter och produktvarianter som ska kopplas till ett nytt produktlivscykeltillstånd när du kör uppdateringen utan simulering.  

## <a name="run-the-update-of-the-product-lifecycle-state-for-obsolete-products"></a>Kör uppdateringen av produktlivscykeltillstånd för föråldrade produkter
1. Stäng sidan.
2. Gå till produktinformationshantering > periodiska uppgifter > ändra status för gamla produkter.
3. Expandera avsnittet Poster som ska ingå.

> [!NOTE]
> Observera att den senaste markeringen har sparats.  

4. Välj Ne i fältet Kör en simulering utan att uppdatera produktdata.
5. Expandera avsnittet Kör i bakgrunden.

> [!NOTE]
> Beroende på hur många produkterna och produktvarianterna påverka, överväg det här jobbet i batch. Se till att du inte kör ett jobb för större uppdatering under företagets mest aktiva arbetstid.  

6. Klicka på OK.
7. Gå till produktinformationshantering > förfrågningar och rapporter > Underhållshistorik för produktlivscykeltillstånd.

> [!NOTE]
> Granska de ändrade frisläppta produkterna och produktvarianterna  

8. Hitta och markera önskad post i listan.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]