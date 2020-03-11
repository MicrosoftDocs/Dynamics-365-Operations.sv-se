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
ms.openlocfilehash: 7813b0c6002e47aef6a8c119c72728a49584401b
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041248"
---
# <span data-ttu-id="d8713-103"><a name="CHAR">CHAR ER-funktion</a></span><span class="sxs-lookup"><span data-stu-id="d8713-103"><a name="CHAR">CHAR ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d8713-104">`CHAR`-funktionen returnerar ett *sträng*-värde som visar ett enstaka tecken som refereras av det angivna Unicode-numret.</span><span class="sxs-lookup"><span data-stu-id="d8713-104">The `CHAR` function returns a *String* value that presents a single character that is referenced by the specified Unicode number.</span></span>

## <a name="syntax"></a><span data-ttu-id="d8713-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="d8713-105">Syntax</span></span>

```vb
CHAR (number)
```

## <a name="arguments"></a><span data-ttu-id="d8713-106">Argument</span><span class="sxs-lookup"><span data-stu-id="d8713-106">Arguments</span></span>

<span data-ttu-id="d8713-107">`number`: *Heltal*</span><span class="sxs-lookup"><span data-stu-id="d8713-107">`number`: *Integer*</span></span>

<span data-ttu-id="d8713-108">Ett tal som motsvarar ett förväntat enstaka tecken.</span><span class="sxs-lookup"><span data-stu-id="d8713-108">A number that corresponds to an expected single character.</span></span>

## <a name="return-values"></a><span data-ttu-id="d8713-109">Returvärden</span><span class="sxs-lookup"><span data-stu-id="d8713-109">Return values</span></span>

<span data-ttu-id="d8713-110">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="d8713-110">*String*</span></span>

<span data-ttu-id="d8713-111">Det resulterande textvärdet.</span><span class="sxs-lookup"><span data-stu-id="d8713-111">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="d8713-112">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="d8713-112">Usage notes</span></span>

<span data-ttu-id="d8713-113">Den sträng som returneras beror på viken kodning som har valts i det överordnade formatelementet **FILE**.</span><span class="sxs-lookup"><span data-stu-id="d8713-113">The string that this function returns depends on the encoding that is selected in the parent **FILE** format element.</span></span> <span data-ttu-id="d8713-114">För listan över vilka koder som stöds se [Encoding class](https://msdn.microsoft.com/library/system.text.encoding(v=vs.110).aspx).</span><span class="sxs-lookup"><span data-stu-id="d8713-114">For a list of the supported encodings, see [Encoding class](https://msdn.microsoft.com/library/system.text.encoding(v=vs.110).aspx).</span></span>

## <a name="example"></a><span data-ttu-id="d8713-115">Exempel</span><span class="sxs-lookup"><span data-stu-id="d8713-115">Example</span></span>

<span data-ttu-id="d8713-116">`CHAR (255)` returnerar **"ÿ"**.</span><span class="sxs-lookup"><span data-stu-id="d8713-116">`CHAR (255)` returns **"ÿ"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d8713-117">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="d8713-117">Additional resources</span></span>

[<span data-ttu-id="d8713-118">Textfunktioner</span><span class="sxs-lookup"><span data-stu-id="d8713-118">Text functions</span></span>](er-functions-category-text.md)
