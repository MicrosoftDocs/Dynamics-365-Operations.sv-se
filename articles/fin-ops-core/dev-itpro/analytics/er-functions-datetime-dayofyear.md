---
title: DAYOFYEAR ER-funktion
description: Det här avsnittet innehåller information om hur funktionen DAYOFYEAR elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/04/2019
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
ms.openlocfilehash: ba63c96355a6a7a1eccaddf39e47a3edb2d1e651
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5563544"
---
# <a name="dayofyear-er-function"></a><span data-ttu-id="5916c-103">DAYOFYEAR ER-funktion</span><span class="sxs-lookup"><span data-stu-id="5916c-103">DAYOFYEAR ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5916c-104">Funktionen `DAYOFYEAR` returnerar värdet *heltal* som representerar antalet dagar mellan 1 januari och det angivna datumet.</span><span class="sxs-lookup"><span data-stu-id="5916c-104">The `DAYOFYEAR` function returns an *Integer* value that represents the number of days between January 1 and the specified date.</span></span>

## <a name="syntax"></a><span data-ttu-id="5916c-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="5916c-105">Syntax</span></span>

```vb
DAYOFYEAR (date) as Integer
```

## <a name="arguments"></a><span data-ttu-id="5916c-106">Argument</span><span class="sxs-lookup"><span data-stu-id="5916c-106">Arguments</span></span>

<span data-ttu-id="5916c-107">`date`: *Datum*</span><span class="sxs-lookup"><span data-stu-id="5916c-107">`date`: *Date*</span></span>

<span data-ttu-id="5916c-108">Ett datumvärde som representerar det datum som ska användas för beräkningen av antalet dagar.</span><span class="sxs-lookup"><span data-stu-id="5916c-108">A date value that represents the date to use for the calculation of the number of days.</span></span>

## <a name="return-values"></a><span data-ttu-id="5916c-109">Returvärden</span><span class="sxs-lookup"><span data-stu-id="5916c-109">Return values</span></span>

<span data-ttu-id="5916c-110">*Heltal*</span><span class="sxs-lookup"><span data-stu-id="5916c-110">*Integer*</span></span>

<span data-ttu-id="5916c-111">Det resulterande numeriska värdet.</span><span class="sxs-lookup"><span data-stu-id="5916c-111">The resulting numeric value.</span></span>

## <a name="example-1"></a><span data-ttu-id="5916c-112">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="5916c-112">Example 1</span></span>

<span data-ttu-id="5916c-113">`DAYOFYEAR (DATEVALUE ("01-03-2016", "dd-MM-yyyy"))` returnerar **61**.</span><span class="sxs-lookup"><span data-stu-id="5916c-113">`DAYOFYEAR (DATEVALUE ("01-03-2016", "dd-MM-yyyy"))` returns **61**.</span></span>

## <a name="example-2"></a><span data-ttu-id="5916c-114">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="5916c-114">Example 2</span></span>

<span data-ttu-id="5916c-115">`DAYOFYEAR (DATEVALUE ("01-01-2016", "dd-MM-yyyy"))` returnerar **1**.</span><span class="sxs-lookup"><span data-stu-id="5916c-115">`DAYOFYEAR (DATEVALUE ("01-01-2016", "dd-MM-yyyy"))` returns **1**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5916c-116">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="5916c-116">Additional resources</span></span>

[<span data-ttu-id="5916c-117">Datum- och tidsfunktioner</span><span class="sxs-lookup"><span data-stu-id="5916c-117">Date and time functions</span></span>](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]