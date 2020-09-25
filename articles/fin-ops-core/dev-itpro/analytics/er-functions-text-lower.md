---
title: LOWER ER-funktion
description: Det här avsnittet innehåller information om hur funktionen LOWER elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/11/2019
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
ms.openlocfilehash: 12577e571c8e87db79395895e2a22e66ee7df32c
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745691"
---
# <a name="lower-er-function"></a><span data-ttu-id="f367b-103">LOWER ER-funktion</span><span class="sxs-lookup"><span data-stu-id="f367b-103">LOWER ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f367b-104">`LOWER`-funktionen returnerar den angivna textsträngen som ett *sträng* värde efter att den har konverterats till gemener.</span><span class="sxs-lookup"><span data-stu-id="f367b-104">The `LOWER` function returns the specified text string as a *String* value after it has been converted to lowercase letters.</span></span>

## <a name="syntax"></a><span data-ttu-id="f367b-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f367b-105">Syntax</span></span>

```vb
LOWER (text)
```

## <a name="arguments"></a><span data-ttu-id="f367b-106">Argument</span><span class="sxs-lookup"><span data-stu-id="f367b-106">Arguments</span></span>

<span data-ttu-id="f367b-107">`text`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="f367b-107">`text`: *String*</span></span>

<span data-ttu-id="f367b-108">Ett *sträng*-värde som anger texten.</span><span class="sxs-lookup"><span data-stu-id="f367b-108">A *String* value that specifies the text.</span></span>

## <a name="return-values"></a><span data-ttu-id="f367b-109">Returvärden</span><span class="sxs-lookup"><span data-stu-id="f367b-109">Return values</span></span>

<span data-ttu-id="f367b-110">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="f367b-110">*String*</span></span>

<span data-ttu-id="f367b-111">Det resulterande textvärdet.</span><span class="sxs-lookup"><span data-stu-id="f367b-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="f367b-112">Exempel</span><span class="sxs-lookup"><span data-stu-id="f367b-112">Example</span></span>

<span data-ttu-id="f367b-113">`LOWER ("Sample")` returnerar **"exempel"**.</span><span class="sxs-lookup"><span data-stu-id="f367b-113">`LOWER ("Sample")` returns **"sample"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f367b-114">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="f367b-114">Additional resources</span></span>

[<span data-ttu-id="f367b-115">Textfunktioner</span><span class="sxs-lookup"><span data-stu-id="f367b-115">Text functions</span></span>](er-functions-category-text.md)
