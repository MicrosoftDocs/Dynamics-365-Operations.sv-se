---
title: ADDDAYS ER-funktion
description: Det här avsnittet innehåller information om hur funktionen ADDDAYS elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/03/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 998cf2c0dac67040814d4a32e433b465ec51f88c
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/01/2020
ms.locfileid: "3743385"
---
# <a name="adddays-er-function"></a><span data-ttu-id="21aeb-103">ADDDAYS ER-funktion</span><span class="sxs-lookup"><span data-stu-id="21aeb-103">ADDDAYS ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="21aeb-104">`ADDDAYS`-funktionen beräknar ett *DateTime*-värde som är angivet antal dagar före eller efter ett angivet startdatum.</span><span class="sxs-lookup"><span data-stu-id="21aeb-104">The `ADDDAYS` function calculates a *DateTime* value that is the specified number of days before or after a specified start date.</span></span>

## <a name="syntax"></a><span data-ttu-id="21aeb-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="21aeb-105">Syntax</span></span>

```vb
ADDDAYS (datetime, days)
```

## <a name="arguments"></a><span data-ttu-id="21aeb-106">Argument</span><span class="sxs-lookup"><span data-stu-id="21aeb-106">Arguments</span></span>

<span data-ttu-id="21aeb-107">`datetime`: *DateTime*</span><span class="sxs-lookup"><span data-stu-id="21aeb-107">`datetime`: *DateTime*</span></span>

<span data-ttu-id="21aeb-108">Ett datum/tidsvärde som representerar startdatumet.</span><span class="sxs-lookup"><span data-stu-id="21aeb-108">A date/time value that represents the start date.</span></span>

<span data-ttu-id="21aeb-109">`days`: *Heltal*</span><span class="sxs-lookup"><span data-stu-id="21aeb-109">`days`: *Integer*</span></span>

<span data-ttu-id="21aeb-110">Antal dagar före eller efter `datetime`.</span><span class="sxs-lookup"><span data-stu-id="21aeb-110">The number of days before or after `datetime`.</span></span>

## <a name="return-values"></a><span data-ttu-id="21aeb-111">Returvärden</span><span class="sxs-lookup"><span data-stu-id="21aeb-111">Return values</span></span>

<span data-ttu-id="21aeb-112">*Datum/tid*</span><span class="sxs-lookup"><span data-stu-id="21aeb-112">*DateTime*</span></span>

<span data-ttu-id="21aeb-113">Det resulterande datum/tid-värdet.</span><span class="sxs-lookup"><span data-stu-id="21aeb-113">The resulting date/time value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="21aeb-114">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="21aeb-114">Usage notes</span></span>

<span data-ttu-id="21aeb-115">Ett positivt värde för `days` avkastning ett framtida datum.</span><span class="sxs-lookup"><span data-stu-id="21aeb-115">A positive value for `days` yields a future date.</span></span> <span data-ttu-id="21aeb-116">Ett negativt värde ger ett tidigare datum.</span><span class="sxs-lookup"><span data-stu-id="21aeb-116">A negative value yields a past date.</span></span>

## <a name="example-1"></a><span data-ttu-id="21aeb-117">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="21aeb-117">Example 1</span></span>

<span data-ttu-id="21aeb-118">`ADDDAYS (NOW(), 7)` returnerar datum och tid sju dagar framöver.</span><span class="sxs-lookup"><span data-stu-id="21aeb-118">`ADDDAYS (NOW(), 7)` returns the date and time seven days in the future.</span></span>

## <a name="example-2"></a><span data-ttu-id="21aeb-119">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="21aeb-119">Example 2</span></span>

<span data-ttu-id="21aeb-120">`ADDDAYS (NOW(), -3)` returnerar datum och tid dagar tidigare.</span><span class="sxs-lookup"><span data-stu-id="21aeb-120">`ADDDAYS (NOW(), -3)` returns the date and time three days in the past.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="21aeb-121">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="21aeb-121">Additional resources</span></span>

[<span data-ttu-id="21aeb-122">Datum- och tidsfunktioner</span><span class="sxs-lookup"><span data-stu-id="21aeb-122">Date and time functions</span></span>](er-functions-category-datetime.md)
