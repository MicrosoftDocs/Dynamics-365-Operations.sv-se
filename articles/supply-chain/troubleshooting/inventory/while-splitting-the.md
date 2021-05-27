---
title: När en faktisk/nominell kvanitet delas upp används minimikvantitet i stället för nominell kvantitet.
description: När en faktisk/nominell kvantitet delas upp i batchar använder fältet Plocka kvantitet den minsta kvantitet som har angetts för artikeln, inte den nominella kvantiteten.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: WMSPickingRegistration
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 185365ced5c4516d8fcdbdca88794d0078615888
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026924"
---
# <a name="when-a-catch-weight-quantity-is-split-minimum-quantity-is-used-instead-of-nominal-quantity"></a><span data-ttu-id="4b59d-103">När en faktisk/nominell kvanitet delas upp används minimikvantitet i stället för nominell kvantitet.</span><span class="sxs-lookup"><span data-stu-id="4b59d-103">When a catch-weight quantity is split, minimum quantity is used instead of nominal quantity</span></span>

<span data-ttu-id="4b59d-104">KB-nummer: 4612073</span><span class="sxs-lookup"><span data-stu-id="4b59d-104">KB number: 4612073</span></span>

## <a name="symptoms"></a><span data-ttu-id="4b59d-105">Symtom</span><span class="sxs-lookup"><span data-stu-id="4b59d-105">Symptoms</span></span>

<span data-ttu-id="4b59d-106">När en faktisk/nominell kvantitet delas upp i batchar använder fältet **Plocka kvantitet** den minsta kvantitet som har angetts för artikeln, inte den nominella kvantiteten.</span><span class="sxs-lookup"><span data-stu-id="4b59d-106">When a catch-weight quantity is being split into batches, the **Pick qty** field uses the minimum quantity that is set for the item, not the nominal quantity.</span></span>

## <a name="resolution"></a><span data-ttu-id="4b59d-107">Upplösning</span><span class="sxs-lookup"><span data-stu-id="4b59d-107">Resolution</span></span>

<span data-ttu-id="4b59d-108">Systemet beter sig som det är utformat.</span><span class="sxs-lookup"><span data-stu-id="4b59d-108">The system is behaving as designed.</span></span> <span data-ttu-id="4b59d-109">Systemet använder varje artikels minsta kvantitetsinställningar för plockning.</span><span class="sxs-lookup"><span data-stu-id="4b59d-109">The system uses each item's minimum quantity setup for picking.</span></span>
