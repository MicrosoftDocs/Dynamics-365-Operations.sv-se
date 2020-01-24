---
title: CHAR ER-funktion
description: Det här avsnittet innehåller information om hur funktionen CHAR elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: d42afcf97690351763138fd9e16265aa104a6bc4
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915750"
---
# <span data-ttu-id="83074-103"><a name="CHAR">CHAR ER-funktion</a></span><span class="sxs-lookup"><span data-stu-id="83074-103"><a name="CHAR">CHAR ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="83074-104">`CHAR`-funktionen returnerar ett *sträng*-värde som visar ett enstaka tecken som refereras av det angivna Unicode-numret.</span><span class="sxs-lookup"><span data-stu-id="83074-104">The `CHAR` function returns a *String* value that presents a single character that is referenced by the specified Unicode number.</span></span>

## <a name="syntax"></a><span data-ttu-id="83074-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="83074-105">Syntax</span></span>

```
CHAR (number)
```

## <a name="arguments"></a><span data-ttu-id="83074-106">Argument</span><span class="sxs-lookup"><span data-stu-id="83074-106">Arguments</span></span>

<span data-ttu-id="83074-107">`number`: *Heltal*</span><span class="sxs-lookup"><span data-stu-id="83074-107">`number`: *Integer*</span></span>

<span data-ttu-id="83074-108">Ett tal som motsvarar ett förväntat enstaka tecken.</span><span class="sxs-lookup"><span data-stu-id="83074-108">A number that corresponds to an expected single character.</span></span>

## <a name="return-values"></a><span data-ttu-id="83074-109">Returvärden</span><span class="sxs-lookup"><span data-stu-id="83074-109">Return values</span></span>

<span data-ttu-id="83074-110">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="83074-110">*String*</span></span>

<span data-ttu-id="83074-111">Det resulterande textvärdet.</span><span class="sxs-lookup"><span data-stu-id="83074-111">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="83074-112">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="83074-112">Usage notes</span></span>

<span data-ttu-id="83074-113">Den sträng som returneras beror på viken kodning som har valts i det överordnade formatelementet **FILE**.</span><span class="sxs-lookup"><span data-stu-id="83074-113">The string that this function returns depends on the encoding that is selected in the parent **FILE** format element.</span></span> <span data-ttu-id="83074-114">För listan över vilka koder som stöds se [Encoding class](https://msdn.microsoft.com/library/system.text.encoding(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="83074-114">For a list of the supported encodings, see [Encoding class](https://msdn.microsoft.com/library/system.text.encoding(v=vs.110).aspx).</span></span>

## <a name="example"></a><span data-ttu-id="83074-115">Exempel</span><span class="sxs-lookup"><span data-stu-id="83074-115">Example</span></span>

<span data-ttu-id="83074-116">`CHAR (255)` returnerar **"ÿ"**.</span><span class="sxs-lookup"><span data-stu-id="83074-116">`CHAR (255)` returns **"ÿ"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="83074-117">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="83074-117">Additional resources</span></span>

[<span data-ttu-id="83074-118">Textfunktioner</span><span class="sxs-lookup"><span data-stu-id="83074-118">Text functions</span></span>](er-functions-category-text.md)
