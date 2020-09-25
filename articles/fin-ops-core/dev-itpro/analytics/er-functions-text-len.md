---
title: LEN ER-funktion
description: Det här avsnittet innehåller information om hur funktionen LEN elektronisk rapportering (ER) används.
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
ms.openlocfilehash: e51e181de53cd185679110e99b9f89695bacdf92
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744273"
---
# <a name="len-er-function"></a><span data-ttu-id="5d527-103">LEN ER-funktion</span><span class="sxs-lookup"><span data-stu-id="5d527-103">LEN ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5d527-104">`LEN`-funktionen returnerar antalet tecken i den angivna strängen som ett *heltals*-värde.</span><span class="sxs-lookup"><span data-stu-id="5d527-104">The `LEN` function returns the number of characters in the specified string as an *Integer* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="5d527-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="5d527-105">Syntax</span></span>

```vb
LEN (text)
```

## <a name="arguments"></a><span data-ttu-id="5d527-106">Argument</span><span class="sxs-lookup"><span data-stu-id="5d527-106">Arguments</span></span>

<span data-ttu-id="5d527-107">`text`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="5d527-107">`text`: *String*</span></span>

<span data-ttu-id="5d527-108">Ett *sträng*-värde som anger texten.</span><span class="sxs-lookup"><span data-stu-id="5d527-108">A *String* value that specifies the text.</span></span>

## <a name="return-values"></a><span data-ttu-id="5d527-109">Returvärden</span><span class="sxs-lookup"><span data-stu-id="5d527-109">Return values</span></span>

<span data-ttu-id="5d527-110">*Heltal*</span><span class="sxs-lookup"><span data-stu-id="5d527-110">*Integer*</span></span>

<span data-ttu-id="5d527-111">Det resulterande numeriska värdet.</span><span class="sxs-lookup"><span data-stu-id="5d527-111">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="5d527-112">Exempel</span><span class="sxs-lookup"><span data-stu-id="5d527-112">Example</span></span>

<span data-ttu-id="5d527-113">`LEN ("Sample")` returnerar **6**.</span><span class="sxs-lookup"><span data-stu-id="5d527-113">`LEN ("Sample")` returns **6**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5d527-114">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="5d527-114">Additional resources</span></span>

[<span data-ttu-id="5d527-115">Textfunktioner</span><span class="sxs-lookup"><span data-stu-id="5d527-115">Text functions</span></span>](er-functions-category-text.md)
