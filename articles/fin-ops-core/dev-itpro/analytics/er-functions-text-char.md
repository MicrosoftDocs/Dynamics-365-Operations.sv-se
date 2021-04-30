---
title: CHAR ER-funktion
description: Det här avsnittet innehåller information om hur funktionen CHAR elektronisk rapportering (ER) används.
author: NickSelin
ms.date: 12/12/2019
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
ms.openlocfilehash: f83dfe19e442b9e81d63a2b1dd3dd44aa2f594bc
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2021
ms.locfileid: "5891193"
---
# <a name="char-er-function"></a><span data-ttu-id="356a7-103">CHAR ER-funktion</span><span class="sxs-lookup"><span data-stu-id="356a7-103">CHAR ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="356a7-104">`CHAR`-funktionen returnerar ett *sträng*-värde som visar ett enstaka tecken som refereras av det angivna Unicode-numret.</span><span class="sxs-lookup"><span data-stu-id="356a7-104">The `CHAR` function returns a *String* value that presents a single character that is referenced by the specified Unicode number.</span></span>

## <a name="syntax"></a><span data-ttu-id="356a7-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="356a7-105">Syntax</span></span>

```vb
CHAR (number)
```

## <a name="arguments"></a><span data-ttu-id="356a7-106">Argument</span><span class="sxs-lookup"><span data-stu-id="356a7-106">Arguments</span></span>

<span data-ttu-id="356a7-107">`number`: *Heltal*</span><span class="sxs-lookup"><span data-stu-id="356a7-107">`number`: *Integer*</span></span>

<span data-ttu-id="356a7-108">Ett tal som motsvarar ett förväntat enstaka tecken.</span><span class="sxs-lookup"><span data-stu-id="356a7-108">A number that corresponds to an expected single character.</span></span>

## <a name="return-values"></a><span data-ttu-id="356a7-109">Returvärden</span><span class="sxs-lookup"><span data-stu-id="356a7-109">Return values</span></span>

<span data-ttu-id="356a7-110">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="356a7-110">*String*</span></span>

<span data-ttu-id="356a7-111">Det resulterande textvärdet.</span><span class="sxs-lookup"><span data-stu-id="356a7-111">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="356a7-112">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="356a7-112">Usage notes</span></span>

<span data-ttu-id="356a7-113">Den sträng som returneras beror på viken kodning som har valts i det överordnade formatelementet **FILE**.</span><span class="sxs-lookup"><span data-stu-id="356a7-113">The string that this function returns depends on the encoding that is selected in the parent **FILE** format element.</span></span> <span data-ttu-id="356a7-114">För listan över vilka koder som stöds se [Encoding class](/dotnet/api/system.text.encoding).</span><span class="sxs-lookup"><span data-stu-id="356a7-114">For a list of the supported encodings, see [Encoding class](/dotnet/api/system.text.encoding).</span></span>

## <a name="example"></a><span data-ttu-id="356a7-115">Exempel</span><span class="sxs-lookup"><span data-stu-id="356a7-115">Example</span></span>

<span data-ttu-id="356a7-116">`CHAR (255)` returnerar **"ÿ"**.</span><span class="sxs-lookup"><span data-stu-id="356a7-116">`CHAR (255)` returns **"ÿ"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="356a7-117">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="356a7-117">Additional resources</span></span>

[<span data-ttu-id="356a7-118">Textfunktioner</span><span class="sxs-lookup"><span data-stu-id="356a7-118">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]