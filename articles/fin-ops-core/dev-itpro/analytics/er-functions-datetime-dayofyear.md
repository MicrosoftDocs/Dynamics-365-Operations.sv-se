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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d24aabb582151b0b357b64a988cc932a9c9f3cea
ms.sourcegitcommit: 3dede95a3b17de920bb0adcb33029f990682752b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/18/2020
ms.locfileid: "3070677"
---
# <span data-ttu-id="19022-103"><a name="DAYOFYEAR">DAYOFYEAR ER-funktion</a></span><span class="sxs-lookup"><span data-stu-id="19022-103"><a name="DAYOFYEAR">DAYOFYEAR ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="19022-104">Funktionen `DAYOFYEAR` returnerar värdet *heltal* som representerar antalet dagar mellan 1 januari och det angivna datumet.</span><span class="sxs-lookup"><span data-stu-id="19022-104">The `DAYOFYEAR` function returns an *Integer* value that represents the number of days between January 1 and the specified date.</span></span>

## <a name="syntax"></a><span data-ttu-id="19022-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="19022-105">Syntax</span></span>

```vb
DAYOFYEAR (date) as Integer
```

## <a name="arguments"></a><span data-ttu-id="19022-106">Argument</span><span class="sxs-lookup"><span data-stu-id="19022-106">Arguments</span></span>

<span data-ttu-id="19022-107">`date`: *Datum*</span><span class="sxs-lookup"><span data-stu-id="19022-107">`date`: *Date*</span></span>

<span data-ttu-id="19022-108">Ett datumvärde som representerar det datum som ska användas för beräkningen av antalet dagar.</span><span class="sxs-lookup"><span data-stu-id="19022-108">A date value that represents the date to use for the calculation of the number of days.</span></span>

## <a name="return-values"></a><span data-ttu-id="19022-109">Returvärden</span><span class="sxs-lookup"><span data-stu-id="19022-109">Return values</span></span>

<span data-ttu-id="19022-110">*Heltal*</span><span class="sxs-lookup"><span data-stu-id="19022-110">*Integer*</span></span>

<span data-ttu-id="19022-111">Det resulterande numeriska värdet.</span><span class="sxs-lookup"><span data-stu-id="19022-111">The resulting numeric value.</span></span>

## <a name="example-1"></a><span data-ttu-id="19022-112">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="19022-112">Example 1</span></span>

<span data-ttu-id="19022-113">`DAYOFYEAR (DATEVALUE ("01-03-2016", "dd-MM-yyyy"))` returnerar **61**.</span><span class="sxs-lookup"><span data-stu-id="19022-113">`DAYOFYEAR (DATEVALUE ("01-03-2016", "dd-MM-yyyy"))` returns **61**.</span></span>

## <a name="example-2"></a><span data-ttu-id="19022-114">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="19022-114">Example 2</span></span>

<span data-ttu-id="19022-115">`DAYOFYEAR (DATEVALUE ("01-01-2016", "dd-MM-yyyy"))` returnerar **1**.</span><span class="sxs-lookup"><span data-stu-id="19022-115">`DAYOFYEAR (DATEVALUE ("01-01-2016", "dd-MM-yyyy"))` returns **1**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="19022-116">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="19022-116">Additional resources</span></span>

[<span data-ttu-id="19022-117">Datum- och tidsfunktioner</span><span class="sxs-lookup"><span data-stu-id="19022-117">Date and time functions</span></span>](er-functions-category-datetime.md)
