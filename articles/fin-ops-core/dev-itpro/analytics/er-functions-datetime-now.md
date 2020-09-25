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
ms.openlocfilehash: e8c411e1ce9656ffa35986f1ceef712c9def1e6b
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/01/2020
ms.locfileid: "3743529"
---
# <a name="now-er-function"></a><span data-ttu-id="f9aad-103">NOW ER-funktion</span><span class="sxs-lookup"><span data-stu-id="f9aad-103">NOW ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f9aad-104">`NOW`-funktionen returnerar ett *DateTime*-värde som representerar aktuella programmets serverdatum och -tid.</span><span class="sxs-lookup"><span data-stu-id="f9aad-104">The `NOW` function returns a *DateTime* value that represents the current application server date and time.</span></span>

## <a name="syntax"></a><span data-ttu-id="f9aad-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f9aad-105">Syntax</span></span>

```vb
NOW ()
```

## <a name="return-values"></a><span data-ttu-id="f9aad-106">Returvärden</span><span class="sxs-lookup"><span data-stu-id="f9aad-106">Return values</span></span>

<span data-ttu-id="f9aad-107">*Datum/tid*</span><span class="sxs-lookup"><span data-stu-id="f9aad-107">*DateTime*</span></span>

<span data-ttu-id="f9aad-108">Det resulterande datum/tid-värdet.</span><span class="sxs-lookup"><span data-stu-id="f9aad-108">The resulting date/time value.</span></span>

## <a name="example"></a><span data-ttu-id="f9aad-109">Exempel</span><span class="sxs-lookup"><span data-stu-id="f9aad-109">Example</span></span>

<span data-ttu-id="f9aad-110">`DATETIMEFORMAT (NOW(), "dd-MM-yyyy")` returnerar det aktuella datum/tidsvärdet för serverprogrammet 24 december 2015, som strängen **"2015-12-24"**, baserat på det definierade och anpassade formatet.</span><span class="sxs-lookup"><span data-stu-id="f9aad-110">`DATETIMEFORMAT (NOW(), "dd-MM-yyyy")` returns the current application server date/time value, December 24, 2015, as **"24-12-2015"**, based on the specified custom format.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f9aad-111">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="f9aad-111">Additional resources</span></span>

[<span data-ttu-id="f9aad-112">Datum- och tidsfunktioner</span><span class="sxs-lookup"><span data-stu-id="f9aad-112">Date and time functions</span></span>](er-functions-category-datetime.md)
