---
title: Avrundningsbelopp för avskrivningsberäkningar
description: Den här artikeln diskuterar fältet Avrundning av avskrivning som finns på inställningssidorna för räkenskapsbok.
author: moaamer
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetBookTable, AssetDepBookTable
audience: Application User
ms.reviewer: kfend
ms.custom: 13931
ms.assetid: faf7db87-046f-41d1-9baf-0df66e373e97
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 98d6a21bea4688d6f258a98eab174485ceee2cfc
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2022
ms.locfileid: "8726737"
---
# <a name="round-off-amount-for-depreciation-calculations"></a>Avrundningsbelopp för avskrivningsberäkningar

[!include [banner](../includes/banner.md)]

Den här artikeln diskuterar fältet **Avrundning av avskrivning** som finns på inställningssidorna för **räkenskapsbok**.

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
