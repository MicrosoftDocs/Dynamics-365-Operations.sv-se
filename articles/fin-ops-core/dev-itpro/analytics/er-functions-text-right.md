---
title: RIGHT ER-funktion
description: Det här avsnittet innehåller information om hur funktionen RIGHT elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/10/2019
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
ms.openlocfilehash: 13884182cb986564e81f310993747997341ffc07
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4682953"
---
# <a name="right-er-function"></a><span data-ttu-id="2488b-103">RIGHT ER-funktion</span><span class="sxs-lookup"><span data-stu-id="2488b-103">RIGHT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2488b-104">`RIGHT`-funktionen returnerar ett *sträng*-värde som visar angivet antal tecken från slutet av den angivna strängen.</span><span class="sxs-lookup"><span data-stu-id="2488b-104">The `RIGHT` function returns a *String* value that presents the specified number of characters from the end of the specified string.</span></span>

## <a name="syntax"></a><span data-ttu-id="2488b-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="2488b-105">Syntax</span></span>

```vb
RIGHT (text, number)
```

## <a name="arguments"></a><span data-ttu-id="2488b-106">Argument</span><span class="sxs-lookup"><span data-stu-id="2488b-106">Arguments</span></span>

<span data-ttu-id="2488b-107">`text`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="2488b-107">`text`: *String*</span></span>

<span data-ttu-id="2488b-108">Ett *sträng*-värde som representerar den ursprungliga texten.</span><span class="sxs-lookup"><span data-stu-id="2488b-108">A *String* value that represents the original text.</span></span>

<span data-ttu-id="2488b-109">`number`: *Heltal*</span><span class="sxs-lookup"><span data-stu-id="2488b-109">`number`: *Integer*</span></span>

<span data-ttu-id="2488b-110">Antalet tecken som måste returneras från slutet av den ursprungliga texten.</span><span class="sxs-lookup"><span data-stu-id="2488b-110">The number of characters that must be returned from the end of the original text.</span></span>

## <a name="return-values"></a><span data-ttu-id="2488b-111">Returvärden</span><span class="sxs-lookup"><span data-stu-id="2488b-111">Return values</span></span>

<span data-ttu-id="2488b-112">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="2488b-112">*String*</span></span>

<span data-ttu-id="2488b-113">Det resulterande textvärdet.</span><span class="sxs-lookup"><span data-stu-id="2488b-113">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="2488b-114">Exempel</span><span class="sxs-lookup"><span data-stu-id="2488b-114">Example</span></span>

<span data-ttu-id="2488b-115">`RIGHT ("Sample", 3)` returnerar **"ple"**.</span><span class="sxs-lookup"><span data-stu-id="2488b-115">`RIGHT ("Sample", 3)` returns **"ple"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2488b-116">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="2488b-116">Additional resources</span></span>

[<span data-ttu-id="2488b-117">Textfunktioner</span><span class="sxs-lookup"><span data-stu-id="2488b-117">Text functions</span></span>](er-functions-category-text.md)
