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
ms.openlocfilehash: dd1290538c506cd0db6eb21a304ff9812c808f17
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916463"
---
# <span data-ttu-id="b4b3a-103"><a name="ADDDAYS">ADDDAYS ER-funktion</a></span><span class="sxs-lookup"><span data-stu-id="b4b3a-103"><a name="ADDDAYS">ADDDAYS ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b4b3a-104">`ADDDAYS`-funktionen beräknar ett *DateTime*-värde som är angivet antal dagar före eller efter ett angivet startdatum.</span><span class="sxs-lookup"><span data-stu-id="b4b3a-104">The `ADDDAYS` function calculates a *DateTime* value that is the specified number of days before or after a specified start date.</span></span>

## <a name="syntax"></a><span data-ttu-id="b4b3a-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b4b3a-105">Syntax</span></span>

```
ADDDAYS (datetime, days)
```

## <a name="arguments"></a><span data-ttu-id="b4b3a-106">Argument</span><span class="sxs-lookup"><span data-stu-id="b4b3a-106">Arguments</span></span>

<span data-ttu-id="b4b3a-107">`datetime`: *DateTime*</span><span class="sxs-lookup"><span data-stu-id="b4b3a-107">`datetime`: *DateTime*</span></span>

<span data-ttu-id="b4b3a-108">Ett datum/tidsvärde som representerar startdatumet.</span><span class="sxs-lookup"><span data-stu-id="b4b3a-108">A date/time value that represents the start date.</span></span>

<span data-ttu-id="b4b3a-109">`days`: *Heltal*</span><span class="sxs-lookup"><span data-stu-id="b4b3a-109">`days`: *Integer*</span></span>

<span data-ttu-id="b4b3a-110">Antal dagar före eller efter `datetime`.</span><span class="sxs-lookup"><span data-stu-id="b4b3a-110">The number of days before or after `datetime`.</span></span>

## <a name="return-values"></a><span data-ttu-id="b4b3a-111">Returvärden</span><span class="sxs-lookup"><span data-stu-id="b4b3a-111">Return values</span></span>

<span data-ttu-id="b4b3a-112">*Datum/tid*</span><span class="sxs-lookup"><span data-stu-id="b4b3a-112">*DateTime*</span></span>

<span data-ttu-id="b4b3a-113">Det resulterande datum/tid-värdet.</span><span class="sxs-lookup"><span data-stu-id="b4b3a-113">The resulting date/time value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="b4b3a-114">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="b4b3a-114">Usage notes</span></span>

<span data-ttu-id="b4b3a-115">Ett positivt värde för `days` avkastning ett framtida datum.</span><span class="sxs-lookup"><span data-stu-id="b4b3a-115">A positive value for `days` yields a future date.</span></span> <span data-ttu-id="b4b3a-116">Ett negativt värde ger ett tidigare datum.</span><span class="sxs-lookup"><span data-stu-id="b4b3a-116">A negative value yields a past date.</span></span>

## <a name="example-1"></a><span data-ttu-id="b4b3a-117">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="b4b3a-117">Example 1</span></span>

<span data-ttu-id="b4b3a-118">`ADDDAYS (NOW(), 7)` returnerar datum och tid sju dagar framöver.</span><span class="sxs-lookup"><span data-stu-id="b4b3a-118">`ADDDAYS (NOW(), 7)` returns the date and time seven days in the future.</span></span>

## <a name="example-2"></a><span data-ttu-id="b4b3a-119">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="b4b3a-119">Example 2</span></span>

<span data-ttu-id="b4b3a-120">`ADDDAYS (NOW(), -3)` returnerar datum och tid dagar tidigare.</span><span class="sxs-lookup"><span data-stu-id="b4b3a-120">`ADDDAYS (NOW(), -3)` returns the date and time three days in the past.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b4b3a-121">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="b4b3a-121">Additional resources</span></span>

[<span data-ttu-id="b4b3a-122">Datum- och tidsfunktioner</span><span class="sxs-lookup"><span data-stu-id="b4b3a-122">Date and time functions</span></span>](er-functions-category-datetime.md)