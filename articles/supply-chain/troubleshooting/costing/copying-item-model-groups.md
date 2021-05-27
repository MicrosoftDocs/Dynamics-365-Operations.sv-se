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
ms.openlocfilehash: 6f6fdfef0bc377418ed8a9c8830e74526a0b95eb
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026910"
---
# <a name="missing-field-settings-when-item-model-groups-are-copied-to-another-legal-entity"></a><span data-ttu-id="f3dec-103">Fältinställningar saknas när artikelmodellgrupper kopieras till en annan juridisk person</span><span class="sxs-lookup"><span data-stu-id="f3dec-103">Missing field settings when item model groups are copied to another legal entity</span></span>

<span data-ttu-id="f3dec-104">KB-nummer: 4612800</span><span class="sxs-lookup"><span data-stu-id="f3dec-104">KB number: 4612800</span></span>

## <a name="symptoms"></a><span data-ttu-id="f3dec-105">Symtom</span><span class="sxs-lookup"><span data-stu-id="f3dec-105">Symptoms</span></span>

<span data-ttu-id="f3dec-106">När du kopierar artikelmodellgrupper till en annan juridisk person (företag) med hjälp av entiteten *Artikelmodellgruppslagerprinciper* saknas vissa fältinställningar (till exempel lagermodellen och beskrivningen) i den nya modellgruppen i den juridiska målenheten.</span><span class="sxs-lookup"><span data-stu-id="f3dec-106">When you copy item model groups to another legal entity (company) by using the *Item model group inventory policies* entity, some field settings (for example, the inventory model and description) are missing in the new model group in the destination legal entity.</span></span>

## <a name="resolution"></a><span data-ttu-id="f3dec-107">Upplösning</span><span class="sxs-lookup"><span data-stu-id="f3dec-107">Resolution</span></span>

<span data-ttu-id="f3dec-108">Om du vill skapa en fullständig kopia av en artikelmodellgrupp till en annan juridisk person måste du också välja både artikelmodellgruppslagerprinciper (`InventInventoryPolicyEntity`) och principer för kostnadsflödesantagande (`InventCostFlowAssumptionPolicyEntity`) som är kopplade till artikelmodellgruppen.</span><span class="sxs-lookup"><span data-stu-id="f3dec-108">To create a complete copy of an item model group to another legal entity, you must also select both the item model group inventory policies (`InventInventoryPolicyEntity`) and the cost flow assumption policies (`InventCostFlowAssumptionPolicyEntity`) that are associated with the item model group.</span></span>
