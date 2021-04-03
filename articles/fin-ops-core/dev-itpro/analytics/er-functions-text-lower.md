---
title: LOWER ER-funktion
description: Det här avsnittet innehåller information om hur funktionen LOWER elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/11/2019
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
ms.openlocfilehash: e507a17f5125a3cba0d2434a1aaec0f04f0cd388
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5562793"
---
# <a name="lower-er-function"></a><span data-ttu-id="cb261-103">LOWER ER-funktion</span><span class="sxs-lookup"><span data-stu-id="cb261-103">LOWER ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="cb261-104">`LOWER`-funktionen returnerar den angivna textsträngen som ett *sträng* värde efter att den har konverterats till gemener.</span><span class="sxs-lookup"><span data-stu-id="cb261-104">The `LOWER` function returns the specified text string as a *String* value after it has been converted to lowercase letters.</span></span>

## <a name="syntax"></a><span data-ttu-id="cb261-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="cb261-105">Syntax</span></span>

```vb
LOWER (text)
```

## <a name="arguments"></a><span data-ttu-id="cb261-106">Argument</span><span class="sxs-lookup"><span data-stu-id="cb261-106">Arguments</span></span>

<span data-ttu-id="cb261-107">`text`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="cb261-107">`text`: *String*</span></span>

<span data-ttu-id="cb261-108">Ett *sträng*-värde som anger texten.</span><span class="sxs-lookup"><span data-stu-id="cb261-108">A *String* value that specifies the text.</span></span>

## <a name="return-values"></a><span data-ttu-id="cb261-109">Returvärden</span><span class="sxs-lookup"><span data-stu-id="cb261-109">Return values</span></span>

<span data-ttu-id="cb261-110">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="cb261-110">*String*</span></span>

<span data-ttu-id="cb261-111">Det resulterande textvärdet.</span><span class="sxs-lookup"><span data-stu-id="cb261-111">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="cb261-112">Exempel</span><span class="sxs-lookup"><span data-stu-id="cb261-112">Example</span></span>

<span data-ttu-id="cb261-113">`LOWER ("Sample")` returnerar **"exempel"**.</span><span class="sxs-lookup"><span data-stu-id="cb261-113">`LOWER ("Sample")` returns **"sample"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="cb261-114">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="cb261-114">Additional resources</span></span>

[<span data-ttu-id="cb261-115">Textfunktioner</span><span class="sxs-lookup"><span data-stu-id="cb261-115">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]