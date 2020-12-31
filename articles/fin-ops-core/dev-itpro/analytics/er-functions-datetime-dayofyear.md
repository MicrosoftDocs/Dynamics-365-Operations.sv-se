---
title: DAYOFYEAR ER-funktion
description: Det här avsnittet innehåller information om hur funktionen DAYOFYEAR elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: b9b937e7fae3e90d1a87196fab653dfac8e94179
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4682399"
---
# <a name="dayofyear-er-function"></a><span data-ttu-id="cec84-103">DAYOFYEAR ER-funktion</span><span class="sxs-lookup"><span data-stu-id="cec84-103">DAYOFYEAR ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="cec84-104">Funktionen `DAYOFYEAR` returnerar värdet *heltal* som representerar antalet dagar mellan 1 januari och det angivna datumet.</span><span class="sxs-lookup"><span data-stu-id="cec84-104">The `DAYOFYEAR` function returns an *Integer* value that represents the number of days between January 1 and the specified date.</span></span>

## <a name="syntax"></a><span data-ttu-id="cec84-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="cec84-105">Syntax</span></span>

```vb
DAYOFYEAR (date) as Integer
```

## <a name="arguments"></a><span data-ttu-id="cec84-106">Argument</span><span class="sxs-lookup"><span data-stu-id="cec84-106">Arguments</span></span>

<span data-ttu-id="cec84-107">`date`: *Datum*</span><span class="sxs-lookup"><span data-stu-id="cec84-107">`date`: *Date*</span></span>

<span data-ttu-id="cec84-108">Ett datumvärde som representerar det datum som ska användas för beräkningen av antalet dagar.</span><span class="sxs-lookup"><span data-stu-id="cec84-108">A date value that represents the date to use for the calculation of the number of days.</span></span>

## <a name="return-values"></a><span data-ttu-id="cec84-109">Returvärden</span><span class="sxs-lookup"><span data-stu-id="cec84-109">Return values</span></span>

<span data-ttu-id="cec84-110">*Heltal*</span><span class="sxs-lookup"><span data-stu-id="cec84-110">*Integer*</span></span>

<span data-ttu-id="cec84-111">Det resulterande numeriska värdet.</span><span class="sxs-lookup"><span data-stu-id="cec84-111">The resulting numeric value.</span></span>

## <a name="example-1"></a><span data-ttu-id="cec84-112">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="cec84-112">Example 1</span></span>

<span data-ttu-id="cec84-113">`DAYOFYEAR (DATEVALUE ("01-03-2016", "dd-MM-yyyy"))` returnerar **61**.</span><span class="sxs-lookup"><span data-stu-id="cec84-113">`DAYOFYEAR (DATEVALUE ("01-03-2016", "dd-MM-yyyy"))` returns **61**.</span></span>

## <a name="example-2"></a><span data-ttu-id="cec84-114">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="cec84-114">Example 2</span></span>

<span data-ttu-id="cec84-115">`DAYOFYEAR (DATEVALUE ("01-01-2016", "dd-MM-yyyy"))` returnerar **1**.</span><span class="sxs-lookup"><span data-stu-id="cec84-115">`DAYOFYEAR (DATEVALUE ("01-01-2016", "dd-MM-yyyy"))` returns **1**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="cec84-116">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="cec84-116">Additional resources</span></span>

[<span data-ttu-id="cec84-117">Datum- och tidsfunktioner</span><span class="sxs-lookup"><span data-stu-id="cec84-117">Date and time functions</span></span>](er-functions-category-datetime.md)
