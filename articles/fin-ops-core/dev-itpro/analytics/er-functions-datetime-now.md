---
title: NOW ER-funktion
description: Det här avsnittet innehåller information om hur funktionen NOW elektronisk rapportering (ER) används.
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
ms.openlocfilehash: cffb23afa4cb347d2840b099b0b49a71150d87d8
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917567"
---
# <span data-ttu-id="4129d-103"><a name="NOW">NOW ER-funktion</a></span><span class="sxs-lookup"><span data-stu-id="4129d-103"><a name="NOW">NOW ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4129d-104">`NOW`-funktionen returnerar ett *DateTime*-värde som representerar aktuella programmets serverdatum och -tid.</span><span class="sxs-lookup"><span data-stu-id="4129d-104">The `NOW` function returns a *DateTime* value that represents the current application server date and time.</span></span>

## <a name="syntax"></a><span data-ttu-id="4129d-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="4129d-105">Syntax</span></span>

```
NOW ()
```

## <a name="return-values"></a><span data-ttu-id="4129d-106">Returvärden</span><span class="sxs-lookup"><span data-stu-id="4129d-106">Return values</span></span>

<span data-ttu-id="4129d-107">*Datum/tid*</span><span class="sxs-lookup"><span data-stu-id="4129d-107">*DateTime*</span></span>

<span data-ttu-id="4129d-108">Det resulterande datum/tid-värdet.</span><span class="sxs-lookup"><span data-stu-id="4129d-108">The resulting date/time value.</span></span>

## <a name="example"></a><span data-ttu-id="4129d-109">Exempel</span><span class="sxs-lookup"><span data-stu-id="4129d-109">Example</span></span>

<span data-ttu-id="4129d-110">`DATETIMEFORMAT (NOW(), "dd-MM-yyyy")` returnerar det aktuella datum/tidsvärdet för serverprogrammet 24 december 2015, som strängen **"2015-12-24"**, baserat på det definierade och anpassade formatet.</span><span class="sxs-lookup"><span data-stu-id="4129d-110">`DATETIMEFORMAT (NOW(), "dd-MM-yyyy")` returns the current application server date/time value, December 24, 2015, as **"24-12-2015"**, based on the specified custom format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4129d-111">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="4129d-111">Additional resources</span></span>

[<span data-ttu-id="4129d-112">Datum- och tidsfunktioner</span><span class="sxs-lookup"><span data-stu-id="4129d-112">Date and time functions</span></span>](er-functions-category-datetime.md)
