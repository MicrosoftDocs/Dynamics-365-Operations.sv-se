---
title: Spåra en artikel eller råmaterial
description: I den här proceduren visas hur du använder artikelspårning för att identifiera var artiklar eller råmaterial har använts eller används.
author: pjacobse
manager: tfehr
ms.date: 08/12/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTrackingDimTracing, InventTrackingDimTracingCriteria, InventTrackingItemIdLookup, InventBatchIdLookup, CustTable, SalesLine
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: pjacobse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 044b098b24d8cdf8008824b7ed1359f2b0566a8f
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4961519"
---
# <a name="trace-an-item-or-raw-material"></a>Spåra en artikel eller råmaterial

[!include [banner](../../includes/banner.md)]

I den här proceduren visas hur du använder artikelspårning för att identifiera var artiklar eller råmaterial har använts eller används. Med den här proceduren kan identifiera en artikel, spåra den tillbaka till källan och sedan spåra framåt igenom produktionen och försäljningen av den färdiga produkten. Processen kan användas för att undersöka berörda kunder, försäljningsorder och annat. I proceduren används demonstrationsföretag USP2.


## <a name="trace-an-item-backwards-using-a-known-batch-number"></a>Spåra en artikel bakåt med ett känt batchnummer
1. I **navigeringsfönstret**, gå till **Moduler > Lagerhantering > Förfrågningar och rapporter > Spårningsdimensioner > Artikelspårning**.
2. Välj P9100 i fältet **Artikelnummer**.
3. Klicka på länken på den valda raden i listan.
4. Välj Bakåt i fältet **Framåt eller bakåt.**
5. I fältet **Batchnummer**, välj "as-12-344-01".
6. Klicka på länken på den valda raden i listan.
7. Klicka på **OK**.

## <a name="identify-an-item-trace-it-forward-and-make-an-analysis"></a>Identifiera en artikel, spåra den framåt och gör en analys

Den övre noden i trädet representerar lagerbehållningen för den valda artikeln och batchen. Du behöver expandera noderna i trädstrukturen för att hitta artikeln som framåtspårningen ska köras på.   
1. Expandera ”noder som beskrivs nedan och välj sedan den senaste noden” i trädet.
    
    Visa: "P9100 / 1 / 10 / as-12-344-01 ● 2 keg ● 7,00 gal \P9100 ● Plockad ● Försäljningsorder 000072 ● 12/22/2015  ● -1 keg ● -4,00 gal ● Site=1, Lagerställe=10, Batchnummer=as-12-344-01 \P9100 ● Produktion B-000050 ● 12/9/2015● 7 keg ● 27,00 gal ● Site=1, Lagerställe=10, Batchnummer=as-12-344-01 ● Samprodukter: P9101" och sedan väljer du den noden.     
2. Expandera ”noden som beskrivs nedan och välj sedan den noden” i trädet.
    
    Med start från noden som du just har markerat visar du "M9103 ● Produktionsrad B-000050 ● 12/9/2015  ● -160,00 lb ● Storlek=70, Färg=OK, Site=1, Lagerställe=10, Batchnummer=App01" och sedan väljer du den noden.  
3. Klicka på **Spåra från nod.**
4. Klicka på **Framåt.**
5. Klicka på **Spårning** i **åtgärdsfönstret**.
    
    Det finns flera spårningsalternativ som ger information om kunder som har påverkats av artikeln som du spårar och de försäljningsorder som är relaterade till artikeln och som inte har levererats.   
6. Klicka på **Kunder.**
7. Stäng sidan.
8. Klicka på **Spårning** i **åtgärdsfönstret**.
9. Klicka på **Levererade försäljningsorder.**
10. Stäng sidan.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]