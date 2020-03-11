---
title: UPPER ER-funktion
description: Det här avsnittet innehåller information om hur funktionen UPPER elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: 77854d645ba5b65a2819437af510fcd67be6d99d
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/12/2020
ms.locfileid: "3040950"
---
# <span data-ttu-id="4a7bb-103"><a name="UPPER">UPPER ER-funktion</a></span><span class="sxs-lookup"><span data-stu-id="4a7bb-103"><a name="UPPER">UPPER ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4a7bb-104">`UPPER`-funktionen returnerar den angivna textsträngen som ett *sträng* värde efter att den har konverterats till versaler.</span><span class="sxs-lookup"><span data-stu-id="4a7bb-104">The `UPPER` function returns the specified text string as a *String* value after it has been converted to uppercase letters.</span></span>

## <a name="syntax"></a><span data-ttu-id="4a7bb-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="4a7bb-105">Syntax</span></span>

```vb
UPPER (text )
```

## <a name="arguments"></a><span data-ttu-id="4a7bb-106">Argument</span><span class="sxs-lookup"><span data-stu-id="4a7bb-106">Arguments</span></span>

<span data-ttu-id="4a7bb-107">`text`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="4a7bb-107">`text`: *String*</span></span>

<span data-ttu-id="4a7bb-108">Den giltiga sökvägen till en datakälla av typen *Sträng*.</span><span class="sxs-lookup"><span data-stu-id="4a7bb-108">The valid path of a data source of the *String* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="4a7bb-109">Returvärden</span><span class="sxs-lookup"><span data-stu-id="4a7bb-109">Return values</span></span>

<span data-ttu-id="4a7bb-110">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="4a7bb-110">*String*</span></span>

<span data-ttu-id="4a7bb-111">Det resulterande textvärdet.</span><span class="sxs-lookup"><span data-stu-id="4a7bb-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="4a7bb-112">Exempel</span><span class="sxs-lookup"><span data-stu-id="4a7bb-112">Example</span></span>

<span data-ttu-id="4a7bb-113">`UPPER ("Sample")` returnerar **"EXEMPEL"**.</span><span class="sxs-lookup"><span data-stu-id="4a7bb-113">`UPPER ("Sample")` returns **"SAMPLE"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4a7bb-114">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="4a7bb-114">Additional resources</span></span>

[<span data-ttu-id="4a7bb-115">Textfunktioner</span><span class="sxs-lookup"><span data-stu-id="4a7bb-115">Text functions</span></span>](er-functions-category-text.md)
