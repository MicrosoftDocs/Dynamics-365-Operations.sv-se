---
title: Det finns inget värde för Från-datum på fliken Aktiva priser på sidan Artikelpris
description: Det finns inget värde för Från-datum på fliken Aktiva priser på sidan Artikelpris.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventItemPrice
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 3dd13f6a3e5ce3c894e96f420358d337f2e43dba
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026930"
---
# <a name="there-is-no-from-date-value-on-the-active-prices-tab-of-the-item-price-page"></a><span data-ttu-id="6767f-103">Det finns inget värde för Från-datum på fliken Aktiva priser på sidan Artikelpris</span><span class="sxs-lookup"><span data-stu-id="6767f-103">There is no From date value on the Active prices tab of the Item price page</span></span>

<span data-ttu-id="6767f-104">KB-nummer: 4613548</span><span class="sxs-lookup"><span data-stu-id="6767f-104">KB number: 4613548</span></span>

## <a name="symptoms"></a><span data-ttu-id="6767f-105">Symtom</span><span class="sxs-lookup"><span data-stu-id="6767f-105">Symptoms</span></span>

<span data-ttu-id="6767f-106">Det finns inget värde för **Från-datum** på fliken **Aktiva priser** på sidan **Artikelpris**.</span><span class="sxs-lookup"><span data-stu-id="6767f-106">There is no **From date** value on the **Active prices** tab of the **Item price** page.</span></span>

## <a name="resolution"></a><span data-ttu-id="6767f-107">Upplösning</span><span class="sxs-lookup"><span data-stu-id="6767f-107">Resolution</span></span>

<span data-ttu-id="6767f-108">Värdet **Från-datum** (effektivt datum) som har angetts i det väntande priset överförs inte till det aktiva priset.</span><span class="sxs-lookup"><span data-stu-id="6767f-108">The **From date** value (effective date) that is set on the pending price isn't transferred to the active price.</span></span>

<span data-ttu-id="6767f-109">När en artikelkostnadspost först registreras har den status *Väntande* och ett avsett giltighetsdatum.</span><span class="sxs-lookup"><span data-stu-id="6767f-109">When an item cost record is first entered, it has a status of *Pending* and an intended effective date.</span></span> <span data-ttu-id="6767f-110">När artikelkostnadsposten aktiveras uppdateras statusvärdet till *Aktiv* och giltighetsdatumet uppdateras till aktiveringsdatumet.</span><span class="sxs-lookup"><span data-stu-id="6767f-110">When you activate the item cost record, the status is updated to *Active*, and the effective date is updated to the activation date.</span></span> <span data-ttu-id="6767f-111">Därför är det aktiva prisets aktiveringsdatum alltid det faktiska datumet för aktiveringen.</span><span class="sxs-lookup"><span data-stu-id="6767f-111">Therefore, the active price's activation date is always the actual date of the activation.</span></span>

<span data-ttu-id="6767f-112">Mer information finns i [Översikt över versioner av kostnadsredovisning](../../cost-management/costing-versions.md).</span><span class="sxs-lookup"><span data-stu-id="6767f-112">For more information, see [Costing versions overview](../../cost-management/costing-versions.md).</span></span>
