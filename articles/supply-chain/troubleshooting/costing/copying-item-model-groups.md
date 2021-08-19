---
title: Fältinställningar saknas när artikelmodellgrupper kopieras till en annan juridisk person
description: Fältinställningar saknas när artikelmodellgrupper kopieras till en annan juridisk person.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventModelGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 128caead04cf467c65a50bc6cd2f9e76e318f536b7eafa7972ffc1b5da5bceba
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6738853"
---
# <a name="missing-field-settings-when-item-model-groups-are-copied-to-another-legal-entity"></a>Fältinställningar saknas när artikelmodellgrupper kopieras till en annan juridisk person

KB-nummer: 4612800

## <a name="symptoms"></a>Symtom

När du kopierar artikelmodellgrupper till en annan juridisk person (företag) med hjälp av entiteten *Artikelmodellgruppslagerprinciper* saknas vissa fältinställningar (till exempel lagermodellen och beskrivningen) i den nya modellgruppen i den juridiska målenheten.

## <a name="resolution"></a>Upplösning

Om du vill skapa en fullständig kopia av en artikelmodellgrupp till en annan juridisk person måste du också välja både artikelmodellgruppslagerprinciper (`InventInventoryPolicyEntity`) och principer för kostnadsflödesantagande (`InventCostFlowAssumptionPolicyEntity`) som är kopplade till artikelmodellgruppen.
