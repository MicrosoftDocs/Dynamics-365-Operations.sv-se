---
title: LEFT ER-funktion
description: Det här avsnittet innehåller information om hur funktionen LEFT elektronisk rapportering (ER) används.
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
ms.openlocfilehash: 112852ab955fdf8de9f78cc93486cc1d5f048517
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/01/2020
ms.locfileid: "3743793"
---
# <a name="left-er-function"></a><span data-ttu-id="2eb6c-103">LEFT ER-funktion</span><span class="sxs-lookup"><span data-stu-id="2eb6c-103">LEFT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2eb6c-104">`LEFT`-funktionen returnerar ett *sträng*-värde som visar angivet antal tecken från början av den angivna strängen.</span><span class="sxs-lookup"><span data-stu-id="2eb6c-104">The `LEFT` function returns a *String* value that presents the specified number of characters from the start of the specified string.</span></span>

## <a name="syntax"></a><span data-ttu-id="2eb6c-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="2eb6c-105">Syntax</span></span>

```vb
LEFT (text, number)
```

## <a name="arguments"></a><span data-ttu-id="2eb6c-106">Argument</span><span class="sxs-lookup"><span data-stu-id="2eb6c-106">Arguments</span></span>

<span data-ttu-id="2eb6c-107">`text`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="2eb6c-107">`text`: *String*</span></span>

<span data-ttu-id="2eb6c-108">Ett *sträng*-värde som representerar den ursprungliga texten.</span><span class="sxs-lookup"><span data-stu-id="2eb6c-108">A *String* value that represents the original text.</span></span>

<span data-ttu-id="2eb6c-109">`number`: *Heltal*</span><span class="sxs-lookup"><span data-stu-id="2eb6c-109">`number`: *Integer*</span></span>

<span data-ttu-id="2eb6c-110">Antalet tecken som måste returneras från början av den ursprungliga texten.</span><span class="sxs-lookup"><span data-stu-id="2eb6c-110">The number of characters that must be returned from the start of the original text.</span></span>

## <a name="return-values"></a><span data-ttu-id="2eb6c-111">Returvärden</span><span class="sxs-lookup"><span data-stu-id="2eb6c-111">Return values</span></span>

<span data-ttu-id="2eb6c-112">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="2eb6c-112">*String*</span></span>

<span data-ttu-id="2eb6c-113">Det resulterande textvärdet.</span><span class="sxs-lookup"><span data-stu-id="2eb6c-113">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="2eb6c-114">Exempel</span><span class="sxs-lookup"><span data-stu-id="2eb6c-114">Example</span></span>

<span data-ttu-id="2eb6c-115">`LEFT ("Sample", 3)` returnerar **"Sam"**.</span><span class="sxs-lookup"><span data-stu-id="2eb6c-115">`LEFT ("Sample", 3)` returns **"Sam"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2eb6c-116">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="2eb6c-116">Additional resources</span></span>

[<span data-ttu-id="2eb6c-117">Textfunktioner</span><span class="sxs-lookup"><span data-stu-id="2eb6c-117">Text functions</span></span>](er-functions-category-text.md)
