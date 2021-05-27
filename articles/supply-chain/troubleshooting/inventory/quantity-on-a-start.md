---
title: Kvantitet på en startad karantänorder uppdateras inte när ordern delas upp
description: När du skapar en karantänorder och försöker dela den uppdateras inte orderkvantiteten till den uppdelade resterande kvantiteten.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventQuarantineOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: shawan
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: a8af535257ce217629d5ba92e624623c3ea39345
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026928"
---
# <a name="quantity-on-a-started-quarantine-order-isnt-updated-when-the-order-is-split"></a><span data-ttu-id="0bebc-103">Kvantitet på en startad karantänorder uppdateras inte när ordern delas upp</span><span class="sxs-lookup"><span data-stu-id="0bebc-103">Quantity on a started quarantine order isn't updated when the order is split</span></span>

<span data-ttu-id="0bebc-104">KB-nummer: 4613113</span><span class="sxs-lookup"><span data-stu-id="0bebc-104">KB number: 4613113</span></span>

## <a name="symptoms"></a><span data-ttu-id="0bebc-105">Symtom</span><span class="sxs-lookup"><span data-stu-id="0bebc-105">Symptoms</span></span>

<span data-ttu-id="0bebc-106">När du skapar en karantänorder och försöker dela den uppdateras inte orderkvantiteten till den resterande kvantiteten efter uppdelningen.</span><span class="sxs-lookup"><span data-stu-id="0bebc-106">When you create a quarantine order and try to split it, the order quantity isn't updated to the remaining quantity after the split.</span></span>

## <a name="resolution"></a><span data-ttu-id="0bebc-107">Upplösning</span><span class="sxs-lookup"><span data-stu-id="0bebc-107">Resolution</span></span>

<span data-ttu-id="0bebc-108">Systemet ändrar inte den ursprungliga kvantiteten från en karantänorder för att säkerställa att du kan spåra den ursprungliga kvantiteten som skapades för karantänordern.</span><span class="sxs-lookup"><span data-stu-id="0bebc-108">The system doesn't change the original quantity from a quarantine order to ensure that you can track the original quantity that was created for that quarantine order.</span></span> <span data-ttu-id="0bebc-109">Systemet spårar dock den kvantitet som delas upp från en karantänorder.</span><span class="sxs-lookup"><span data-stu-id="0bebc-109">However, the system does track the quantity that is split from a quarantine order.</span></span> <span data-ttu-id="0bebc-110">För att spåra använder den ett databasfält med namnet `QuantityThatHasSplitIntoOtherQuarantineOrders`.</span><span class="sxs-lookup"><span data-stu-id="0bebc-110">To do this tracking, it uses a database field that is named `QuantityThatHasSplitIntoOtherQuarantineOrders`.</span></span> <span data-ttu-id="0bebc-111">Det här fältet visas dock inte i användargränssnittet (UI).</span><span class="sxs-lookup"><span data-stu-id="0bebc-111">However, this field isn't visible in the user interface (UI).</span></span>
