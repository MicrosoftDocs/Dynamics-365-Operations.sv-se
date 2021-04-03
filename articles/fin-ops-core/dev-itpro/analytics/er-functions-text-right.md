---
title: RIGHT ER-funktion
description: Det här avsnittet innehåller information om hur funktionen RIGHT elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/10/2019
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
ms.openlocfilehash: 75255eccf4da468b0946253f7570b1621f905cd7
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5570250"
---
# <a name="right-er-function"></a><span data-ttu-id="62a20-103">RIGHT ER-funktion</span><span class="sxs-lookup"><span data-stu-id="62a20-103">RIGHT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="62a20-104">`RIGHT`-funktionen returnerar ett *sträng*-värde som visar angivet antal tecken från slutet av den angivna strängen.</span><span class="sxs-lookup"><span data-stu-id="62a20-104">The `RIGHT` function returns a *String* value that presents the specified number of characters from the end of the specified string.</span></span>

## <a name="syntax"></a><span data-ttu-id="62a20-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="62a20-105">Syntax</span></span>

```vb
RIGHT (text, number)
```

## <a name="arguments"></a><span data-ttu-id="62a20-106">Argument</span><span class="sxs-lookup"><span data-stu-id="62a20-106">Arguments</span></span>

<span data-ttu-id="62a20-107">`text`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="62a20-107">`text`: *String*</span></span>

<span data-ttu-id="62a20-108">Ett *sträng*-värde som representerar den ursprungliga texten.</span><span class="sxs-lookup"><span data-stu-id="62a20-108">A *String* value that represents the original text.</span></span>

<span data-ttu-id="62a20-109">`number`: *Heltal*</span><span class="sxs-lookup"><span data-stu-id="62a20-109">`number`: *Integer*</span></span>

<span data-ttu-id="62a20-110">Antalet tecken som måste returneras från slutet av den ursprungliga texten.</span><span class="sxs-lookup"><span data-stu-id="62a20-110">The number of characters that must be returned from the end of the original text.</span></span>

## <a name="return-values"></a><span data-ttu-id="62a20-111">Returvärden</span><span class="sxs-lookup"><span data-stu-id="62a20-111">Return values</span></span>

<span data-ttu-id="62a20-112">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="62a20-112">*String*</span></span>

<span data-ttu-id="62a20-113">Det resulterande textvärdet.</span><span class="sxs-lookup"><span data-stu-id="62a20-113">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="62a20-114">Exempel</span><span class="sxs-lookup"><span data-stu-id="62a20-114">Example</span></span>

<span data-ttu-id="62a20-115">`RIGHT ("Sample", 3)` returnerar **"ple"**.</span><span class="sxs-lookup"><span data-stu-id="62a20-115">`RIGHT ("Sample", 3)` returns **"ple"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="62a20-116">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="62a20-116">Additional resources</span></span>

[<span data-ttu-id="62a20-117">Textfunktioner</span><span class="sxs-lookup"><span data-stu-id="62a20-117">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]