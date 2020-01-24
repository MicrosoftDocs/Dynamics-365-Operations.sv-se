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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 01718f9b153c1d6c46d50a9b17e899ccfba16915
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916739"
---
# <span data-ttu-id="c175c-103"><a name="RIGHT">RIGHT ER-funktion</a></span><span class="sxs-lookup"><span data-stu-id="c175c-103"><a name="RIGHT">RIGHT ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c175c-104">`RIGHT`-funktionen returnerar ett *sträng*-värde som visar angivet antal tecken från slutet av den angivna strängen.</span><span class="sxs-lookup"><span data-stu-id="c175c-104">The `RIGHT` function returns a *String* value that presents the specified number of characters from the end of the specified string.</span></span>

## <a name="syntax"></a><span data-ttu-id="c175c-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="c175c-105">Syntax</span></span>

```
RIGHT (text, number)
```

## <a name="arguments"></a><span data-ttu-id="c175c-106">Argument</span><span class="sxs-lookup"><span data-stu-id="c175c-106">Arguments</span></span>

<span data-ttu-id="c175c-107">`text`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="c175c-107">`text`: *String*</span></span>

<span data-ttu-id="c175c-108">Ett *sträng*-värde som representerar den ursprungliga texten.</span><span class="sxs-lookup"><span data-stu-id="c175c-108">A *String* value that represents the original text.</span></span>

<span data-ttu-id="c175c-109">`number`: *Heltal*</span><span class="sxs-lookup"><span data-stu-id="c175c-109">`number`: *Integer*</span></span>

<span data-ttu-id="c175c-110">Antalet tecken som måste returneras från slutet av den ursprungliga texten.</span><span class="sxs-lookup"><span data-stu-id="c175c-110">The number of characters that must be returned from the end of the original text.</span></span>

## <a name="return-values"></a><span data-ttu-id="c175c-111">Returvärden</span><span class="sxs-lookup"><span data-stu-id="c175c-111">Return values</span></span>

<span data-ttu-id="c175c-112">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="c175c-112">*String*</span></span>

<span data-ttu-id="c175c-113">Det resulterande textvärdet.</span><span class="sxs-lookup"><span data-stu-id="c175c-113">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="c175c-114">Exempel</span><span class="sxs-lookup"><span data-stu-id="c175c-114">Example</span></span>

<span data-ttu-id="c175c-115">`RIGHT ("Sample", 3)` returnerar **"ple"**.</span><span class="sxs-lookup"><span data-stu-id="c175c-115">`RIGHT ("Sample", 3)` returns **"ple"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c175c-116">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="c175c-116">Additional resources</span></span>

[<span data-ttu-id="c175c-117">Textfunktioner</span><span class="sxs-lookup"><span data-stu-id="c175c-117">Text functions</span></span>](er-functions-category-text.md)
