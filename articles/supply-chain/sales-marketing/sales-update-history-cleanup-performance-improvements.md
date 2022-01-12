---
title: Förbättringar av prestanda för rensning av försäljningshistorik
description: I detta ämne beskrivs funktionen för prestandaförbättringar i rensningen av försäljningshistorik och hur du aktiverar den.
author: myvakalo
ms.date: 10/05/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: myvakalo
ms.search.validFrom: 2021-09-29
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 610f0d4e0448dd21d10765400f25cd89e3c7a84b
ms.sourcegitcommit: 008779c530798f563fe216810d34b2d56f2c8d3c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/14/2021
ms.locfileid: "7920283"
---
# <a name="sales-history-cleanup-performance-improvements"></a>Förbättringar av prestanda för rensning av försäljningshistorik

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!-- KFM: Preview until GA with 10.0.24 -->

Det periodiska batchjobbet **Rensningen av försäljningsuppdateringshistorik** kan ta lång tid om den körs sällan i miljöer med stora antal försäljningsuppdateringar. I dessa situationer kan funktionen *Förbättringar i rensning av försäljningshistorik* hjälpa till att minska körningens varaktighet och förbättra tillförlitligheten.

Funktionen förbättrar det befintliga rensningsjobbet på följande sätt:

- Rensningen delas upp i batchar (du kan ändra batchstorleken genom anpassningar).
- Den kommer att köras i högst 2 timmar (du kan ändra tiden genom anpassningar).
- Där så är möjligt utnyttjar den databaskapaciteter i syfte att minimera låsningar och undvika att transaktionsregister sammanfogas under rensningen.

När funktionen har aktiverats kommer batchjobbet **Rensning av försäljningsuppdateringshistorik** (**Försäljning och marknadsföring \> Periodiska uppgifter \> Rensning \> Rensning av försäljningsuppdateringshistorik**) att köras som tidigare, men nu med bättre prestanda samt i maximalt 2 timmar. Detta innebär att det kanske måste köras flera gånger om du vill rensa alla data för en specifik kvarhållningstidsram.

## <a name="turn-on-the-sales-history-cleanup-performance-improvements-feature"></a>Aktivera funktionen för förbättringar i rensningsprestandan för försäljningshistorik

Innan du kan använda den här funktionen den aktiveras i ditt system. Administratörer kan använda inställningarna [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den. I arbetsytan **utgiftshantering** anges den här funktionen på följande sätt:

- **Modul:** *Försäljning och marknadsföring*
- **Funktionens namn** *Förbättringar i prestanda för rensning av försäljningshistorik*
