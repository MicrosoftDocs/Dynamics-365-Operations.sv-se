---
title: Det går inte att annullera en följesedel efter att den har bokförts från en order
description: När plocknings- och leveransprocesser är aktiverade för WMS kan du inte annullera en följesedel efter att den har bokförts från en försäljningsorder. På den här sidan finns en lösning.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: d20e66e2721560b8409eb63c3546a79adc188c7c
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477685"
---
# <a name="cant-cancel-a-packing-slip-after-its-posted-from-a-sales-order"></a>Det går inte att annullera en följesedel efter att den har bokförts från en försäljningsorder

## <a name="symptoms"></a>Symtom

När plocknings- och leveransprocesser är aktiverade för WMS (Advanced Warehous Management) kan du inte annullera en följesedel efter att den har bokförts från en försäljningsorder.

## <a name="resolution"></a>Lösning

För att korrigera bokförda paket för artiklar som är aktiverade för WMS måste bokningen ske från lasten, inte från beställningen. Microsoft har utvärderat det här problemet och har fastställt att det är en funktionsbegränsning.  

I allmänhet kan en försäljningsorder som har plockats och levererats via lagerstyrningsprocesser följesedel-uppdateras från beläggningen eller utleveransen och själva försäljningsorderdokumentet. Om du följesedel-uppdaterar försäljningsordern från försäljningsorderdokumentet kan det dock fortfarande inte göras någon återföring av följesedeln från beläggningen eller försäljningsordern. Därför rekommenderar vi att du använder följesedels bokföringen från lasten. I det här fallet kommer den återföring som måste göras från lasten att aktiveras.
