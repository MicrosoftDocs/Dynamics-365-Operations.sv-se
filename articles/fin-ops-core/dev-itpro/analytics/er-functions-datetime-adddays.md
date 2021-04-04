---
title: ADDDAYS ER-funktion
description: Det här avsnittet innehåller information om hur funktionen ADDDAYS elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/03/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 85ad6508c0d16796efbf1ad81e25d74365de8f30
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5570782"
---
# <a name="adddays-er-function"></a><span data-ttu-id="a1c10-103">ADDDAYS ER-funktion</span><span class="sxs-lookup"><span data-stu-id="a1c10-103">ADDDAYS ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a1c10-104">`ADDDAYS`-funktionen beräknar ett *DateTime*-värde som är angivet antal dagar före eller efter ett angivet startdatum.</span><span class="sxs-lookup"><span data-stu-id="a1c10-104">The `ADDDAYS` function calculates a *DateTime* value that is the specified number of days before or after a specified start date.</span></span>

## <a name="syntax"></a><span data-ttu-id="a1c10-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="a1c10-105">Syntax</span></span>

```vb
ADDDAYS (datetime, days)
```

## <a name="arguments"></a><span data-ttu-id="a1c10-106">Argument</span><span class="sxs-lookup"><span data-stu-id="a1c10-106">Arguments</span></span>

<span data-ttu-id="a1c10-107">`datetime`: *DateTime*</span><span class="sxs-lookup"><span data-stu-id="a1c10-107">`datetime`: *DateTime*</span></span>

<span data-ttu-id="a1c10-108">Ett datum/tidsvärde som representerar startdatumet.</span><span class="sxs-lookup"><span data-stu-id="a1c10-108">A date/time value that represents the start date.</span></span>

<span data-ttu-id="a1c10-109">`days`: *Heltal*</span><span class="sxs-lookup"><span data-stu-id="a1c10-109">`days`: *Integer*</span></span>

<span data-ttu-id="a1c10-110">Antal dagar före eller efter `datetime`.</span><span class="sxs-lookup"><span data-stu-id="a1c10-110">The number of days before or after `datetime`.</span></span>

## <a name="return-values"></a><span data-ttu-id="a1c10-111">Returvärden</span><span class="sxs-lookup"><span data-stu-id="a1c10-111">Return values</span></span>

<span data-ttu-id="a1c10-112">*Datum/tid*</span><span class="sxs-lookup"><span data-stu-id="a1c10-112">*DateTime*</span></span>

<span data-ttu-id="a1c10-113">Det resulterande datum/tid-värdet.</span><span class="sxs-lookup"><span data-stu-id="a1c10-113">The resulting date/time value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="a1c10-114">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="a1c10-114">Usage notes</span></span>

<span data-ttu-id="a1c10-115">Ett positivt värde för `days` avkastning ett framtida datum.</span><span class="sxs-lookup"><span data-stu-id="a1c10-115">A positive value for `days` yields a future date.</span></span> <span data-ttu-id="a1c10-116">Ett negativt värde ger ett tidigare datum.</span><span class="sxs-lookup"><span data-stu-id="a1c10-116">A negative value yields a past date.</span></span>

## <a name="example-1"></a><span data-ttu-id="a1c10-117">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="a1c10-117">Example 1</span></span>

<span data-ttu-id="a1c10-118">`ADDDAYS (NOW(), 7)` returnerar datum och tid sju dagar framöver.</span><span class="sxs-lookup"><span data-stu-id="a1c10-118">`ADDDAYS (NOW(), 7)` returns the date and time seven days in the future.</span></span>

## <a name="example-2"></a><span data-ttu-id="a1c10-119">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="a1c10-119">Example 2</span></span>

<span data-ttu-id="a1c10-120">`ADDDAYS (NOW(), -3)` returnerar datum och tid dagar tidigare.</span><span class="sxs-lookup"><span data-stu-id="a1c10-120">`ADDDAYS (NOW(), -3)` returns the date and time three days in the past.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a1c10-121">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="a1c10-121">Additional resources</span></span>

[<span data-ttu-id="a1c10-122">Datum- och tidsfunktioner</span><span class="sxs-lookup"><span data-stu-id="a1c10-122">Date and time functions</span></span>](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]