---
title: Du kan inte ta bort dimensionen Efterfrågeprognos för lagerställe från prognosrader
description: Du kan inte ta bort dimensionen Efterfrågeprognos för lagerställe från prognosrader.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ForecastSales
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 6b643c4fe51ae6ce73b34ab81d4e458dcd5032df
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026918"
---
# <a name="you-cant-remove-the-warehouse-demand-forecast-dimension-from-forecast-lines"></a><span data-ttu-id="e3596-103">Du kan inte ta bort dimensionen Efterfrågeprognos för lagerställe från prognosrader</span><span class="sxs-lookup"><span data-stu-id="e3596-103">You can't remove the Warehouse demand forecast dimension from forecast lines</span></span>

<span data-ttu-id="e3596-104">KB-nummer: 4614408</span><span class="sxs-lookup"><span data-stu-id="e3596-104">KB number: 4614408</span></span>

## <a name="symptoms"></a><span data-ttu-id="e3596-105">Symtom</span><span class="sxs-lookup"><span data-stu-id="e3596-105">Symptoms</span></span>

<span data-ttu-id="e3596-106">Det här problemet uppstår när dimensionen **Lagerställe** inte har tilldelats under fliken **Prognosticeringsdimension** på sidan **Parameter för efterfrågeprognos**.</span><span class="sxs-lookup"><span data-stu-id="e3596-106">This issue occurs when the **Warehouse** dimension isn't assigned on the **Forecast dimensions** tab of the **Demand forecasting parameter** page.</span></span> <span data-ttu-id="e3596-107">Ändå visas kolumnen **Lagerställe** på sidan **Efterfrågeprognos** (**Huvudplanering \> Prognos \> Manuell prognos \> Efterfrågeprognosrader**).</span><span class="sxs-lookup"><span data-stu-id="e3596-107">Nevertheless, the **Warehouse** column is shown on the **Demand forecast** page (**Master planning \> Forecasting \> Manual forecast entity \> Demand forecast lines**).</span></span>

## <a name="resolution"></a><span data-ttu-id="e3596-108">Upplösning</span><span class="sxs-lookup"><span data-stu-id="e3596-108">Resolution</span></span>

<span data-ttu-id="e3596-109">Inställningarna under fliken **Prognosticeringsdimensioner** på sidan **Parameter för efterfrågeprognos** påverkar inte sidan **Efterfrågeprognos**.</span><span class="sxs-lookup"><span data-stu-id="e3596-109">The settings on the **Forecast dimensions** tab of the **Demand forecasting parameter** page don't affect the **Demand forecast** page.</span></span> <span data-ttu-id="e3596-110">De styr baslinjeprognosen som skapas och visas i den justerade efterfrågeprognosen.</span><span class="sxs-lookup"><span data-stu-id="e3596-110">They control the baseline forecast that is generated and shown in the adjusted demand forecast.</span></span> <span data-ttu-id="e3596-111">De kontrollerar emellertid inte de dimensioner som krävs för den "verkliga" efterfrågeprognosen.</span><span class="sxs-lookup"><span data-stu-id="e3596-111">However, they don't control the dimensions that are required for the "real" demand forecast.</span></span> <span data-ttu-id="e3596-112">Genom att auktorisera posterna som visas på sidan **Justerad efterfrågeprognos** kan du konvertera dem till "verkliga" prognosposter för en prognosmodell.</span><span class="sxs-lookup"><span data-stu-id="e3596-112">By authorizing the records that are shown on the **Adjusted demand forecast** page, you can convert them to "real" forecast entries for a forecast model.</span></span> <span data-ttu-id="e3596-113">Den modellen kan sedan användas för huvudplanering.</span><span class="sxs-lookup"><span data-stu-id="e3596-113">That model can then be used for master planning.</span></span>

<span data-ttu-id="e3596-114">På sidan **Efterfrågeprognos** är dimensionerna för den "verkliga" prognosen som visas på efterfrågeprognosraderna del av lagerdimensionerna.</span><span class="sxs-lookup"><span data-stu-id="e3596-114">On the **Demand forecast** page, the dimensions for the "real" forecast that are shown on the demand forecast lines are part of the inventory dimensions.</span></span> <span data-ttu-id="e3596-115">(Detta beteende liknar beteendet för försäljningsorderrader.) Om ditt system inte är inställt på att använda **Lagerställe** som obligatorisk lagerdimension kan du anpassa sidan så att kolumnen döljs.</span><span class="sxs-lookup"><span data-stu-id="e3596-115">(This behavior resembles the behavior for sales order lines.) If your system isn't set up to use **Warehouse** as a mandatory inventory dimension, you can customize the page to hide the column.</span></span>
