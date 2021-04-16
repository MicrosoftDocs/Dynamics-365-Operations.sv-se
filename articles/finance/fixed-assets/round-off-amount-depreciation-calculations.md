---
title: Avrundningsbelopp för avskrivningsberäkningar.
description: Den här artikeln diskuterar fältet Avrundning av avskrivning som finns på inställningssidorna för räkenskapsbok.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetBookTable, AssetDepBookTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 13931
ms.assetid: faf7db87-046f-41d1-9baf-0df66e373e97
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0bf7cf68c98b14fb6c206c99673168153b32a449
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5830433"
---
# <a name="round-off-amount-for-depreciation-calculations"></a>Avrundningsbelopp för avskrivningsberäkningar.

[!include [banner](../includes/banner.md)]

Den här artikeln diskuterar fältet Avrundning av avskrivning som finns på inställningssidorna för räkenskapsbok.

Avrundningsbeloppet för avskrivning anges för varje bok. Avrundningsbeloppet för avskrivning används i avskrivningsprofilen för anläggningstillgångar som visar den framtida avskrivningen, värdet på anläggningstillgången och även i avskrivningsförslag. Ange lägsta tillåtna avskrivningsbelopp för räkenskapsboken. 

Oavsett avrundningen som har ställts in avrundas inte avskrivningsbeloppet i den sista avskrivningsperioden. I slutet av den sista avskrivningsperioden måste värdet på anläggningstillgången måste vara 0 (noll) eller kassationsvärdet, om kassationsvärde används.

### <a name="example"></a>Exempel

Avskrivning utan avrundning beräknas som 2 444,44. Som följande tabell visar varierar beloppen som föreslås beroende på hur avrundningen är inställd.

| Avrundningsmetod | Avskrivningsbelopp |
|-----------------|---------------------|
| Avrundning 0,1    | 2 444,40            |
| Avrundning 1,00   | 2 444,00            |
| Avrundning 10,00  | 2 440,00            |
| Avrundning 100,00 | 2 400,00            |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]