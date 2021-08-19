---
title: Cyklen är ej berättigad till rensning
description: Cyklen är ej berättigad till rensning
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSWaveTable_WHSWaveProcessingDataCleanup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 99d76b6a90045be7630785769b11e43abaf4b789b1c4a134050b6ee396c71199
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6778516"
---
# <a name="wave-isnt-eligible-for-cleanup"></a>Cyklen är ej berättigad till rensning

Felkod: WaveNotEligibleForCleanup

## <a name="symptoms"></a>Symtom

Systemet visar följande felmeddelande:

> Påfyllnaden %1 är inte berättigad till rensning.

Cykeldatan kan inte rensas.  

## <a name="cause"></a>Orsak

Cyklen bearbetas just nu enligt något av följande villkor:

- Fältet **Cykelstatus** är inställt på *Körs*.
- När du väljer **Batchjobb** i gruppen **Cykel** på fliken **Cykel** i åtgärdsfönstret, är fältet **Status** inte inställt på *Avslutat*, *Fel* eller *Avslutad*. Därför körs för tillfället ett batchjobb.

## <a name="resolution"></a>Upplösning

I åtgärdsfönstret, på fliken **Cykel** i gruppen **Cykel**, väljer du **Batchjobb** och följer sedan ett av följande steg:

- Om fältet **Status** är inställt på *Körs*: I åtgärdsfönstret, på fliken **Batchjobb** i gruppen **Batchjobb** väljer du **Visa uppgifter**. Genom att uppdatera sidan **Batchuppgifter** kan du följa processen.
- Om fältet **Status** inte är inställt på *Körs*: I åtgärdsfönstret, på fliken **Batchjobb** i gruppen **Funktioner**, väljer du **Ändra status**. I fältet **Välj ny status** väljer du *Väntar*. Välj sedan **OK**.
