---
title: "Visa avgifter för en tillverkad artikel"
description: "En tillverkad artikels konstanta kostnader återspeglar driftställtiderna och komponenterna med en konstant kvantitet eller ett konstant kassationsbelopp."
author: YuyuScheller
manager: AnnBe
ms.date: 04/20/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: CostingVersion, InventItemPrice
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 274483
ms.assetid: 6f5b851b-c5a7-43ef-b380-0d316667c1ef
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.dyn365.ops.intro: AX 7.0.0
ms.search.validFrom: 2016-02-28
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 119f49d9456c49b1e010da1e0b2c52e369164344
ms.contentlocale: sv-se
ms.lasthandoff: 04/25/2017


---

# <a name="display-charges-for-a-manufactured-item"></a>Visa avgifter för en tillverkad artikel

[!include[banner](../includes/banner.md)]


En tillverkad artikels konstanta kostnader återspeglar driftställtiderna och komponenterna med en konstant kvantitet eller ett konstant kassationsbelopp.

Det beräknade beloppet för en artikels kostnader kan visas med artikelns enhetskostnad. Tilläggen visas emellertid ibland som separata fält, och de inkluderas inte i artikelns enhetskostnad. När avgifterna visas som separata fält, visar ett fält det totala avgiftsbeloppet och andra fält visar kostnadspartistorleken som används för att amortera beloppet. T.ex. sidan Artikelpris visar avgifterna som två separata fält. Emellertid visar sidan Slutförd artikelns totala kostnad per enhet och de amorterade kostnaderna ingår i enhetskostnaderna.
Avgifterna för en tillverkad artikel inkluderas alltid i artikelns enhetskostnad i standardkostnadssyfte. De kan valfritt inkluderas för planerade kostnader. En policy i kostnadsversionen gör det möjligt att inkludera avgifter i kostnaden för en tillverkad artikel. När du aktiverar en artikels kostnadspost uppdaterar du avgifterna för artikels baskostnadsinformation, vilket visas på sidan Artikelpris. Avgifterna visas ibland som två separata fält, och de inkluderas inte i artikelns enhetskostnad. Varje aktivering uppdaterar artikelns baskostnadsinformation, även om aktiveringen återspeglar olika siter. Därför bör du visa baskostnadsinformation som referensinformation.






