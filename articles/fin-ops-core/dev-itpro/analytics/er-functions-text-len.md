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
ms.openlocfilehash: d6f2a661dd3a85c658ff85f5886d98f665e28718
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915589"
---
# <span data-ttu-id="88e2a-103"><a name="LEN">LEN ER-funktion</a></span><span class="sxs-lookup"><span data-stu-id="88e2a-103"><a name="LEN">LEN ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="88e2a-104">`LEN`-funktionen returnerar antalet tecken i den angivna strängen som ett *heltals*-värde.</span><span class="sxs-lookup"><span data-stu-id="88e2a-104">The `LEN` function returns the number of characters in the specified string as an *Integer* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="88e2a-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="88e2a-105">Syntax</span></span>

```
LEN (text)
```

## <a name="arguments"></a><span data-ttu-id="88e2a-106">Argument</span><span class="sxs-lookup"><span data-stu-id="88e2a-106">Arguments</span></span>

<span data-ttu-id="88e2a-107">`text`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="88e2a-107">`text`: *String*</span></span>

<span data-ttu-id="88e2a-108">Ett *sträng*-värde som anger texten.</span><span class="sxs-lookup"><span data-stu-id="88e2a-108">A *String* value that specifies the text.</span></span>

## <a name="return-values"></a><span data-ttu-id="88e2a-109">Returvärden</span><span class="sxs-lookup"><span data-stu-id="88e2a-109">Return values</span></span>

<span data-ttu-id="88e2a-110">*Heltal*</span><span class="sxs-lookup"><span data-stu-id="88e2a-110">*Integer*</span></span>

<span data-ttu-id="88e2a-111">Det resulterande numeriska värdet.</span><span class="sxs-lookup"><span data-stu-id="88e2a-111">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="88e2a-112">Exempel</span><span class="sxs-lookup"><span data-stu-id="88e2a-112">Example</span></span>

<span data-ttu-id="88e2a-113">`LEN ("Sample")` returnerar **6**.</span><span class="sxs-lookup"><span data-stu-id="88e2a-113">`LEN ("Sample")` returns **6**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="88e2a-114">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="88e2a-114">Additional resources</span></span>

[<span data-ttu-id="88e2a-115">Textfunktioner</span><span class="sxs-lookup"><span data-stu-id="88e2a-115">Text functions</span></span>](er-functions-category-text.md)
