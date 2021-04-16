---
title: JSONVALUE ER-funktion
description: Det här avsnittet innehåller information om hur funktionen JSONVALUE elektronisk rapportering (ER) används.
author: NickSelin
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
ms.openlocfilehash: e8336e43a236e3f3b875fb3cb81bc139507673c2
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746373"
---
# <a name="jsonvalue-er-function"></a><span data-ttu-id="92828-103">JSONVALUE ER-funktion</span><span class="sxs-lookup"><span data-stu-id="92828-103">JSONVALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="92828-104">`JSONVALUE`-funktionen analyserar data i JSON-format (JavaScript Object Notation) som används av den angivna sökvägen och som extraherar ett skalärvärde som baseras på angivet-ID.</span><span class="sxs-lookup"><span data-stu-id="92828-104">The `JSONVALUE` function parses data in JavaScript Object Notation (JSON) format that is accessed at the specified path, and it extracts a scalar value that has the specified ID.</span></span> <span data-ttu-id="92828-105">Den returnerar sedan det extraherade skalärvärdet som ett *sträng* värde.</span><span class="sxs-lookup"><span data-stu-id="92828-105">It then returns the extracted scalar value as a *String* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="92828-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="92828-106">Syntax</span></span>

```vb
JSONVALUE (input, path)
```

## <a name="arguments"></a><span data-ttu-id="92828-107">Argument</span><span class="sxs-lookup"><span data-stu-id="92828-107">Arguments</span></span>

<span data-ttu-id="92828-108">`input`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="92828-108">`input`: *String*</span></span>

<span data-ttu-id="92828-109">Den giltiga sökvägen till en datakälla av typen *Sträng* som innehåller JSON-data.</span><span class="sxs-lookup"><span data-stu-id="92828-109">The valid path of a data source of the *String* type that contains JSON data.</span></span>

<span data-ttu-id="92828-110">`path`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="92828-110">`path`: *String*</span></span>

<span data-ttu-id="92828-111">Identifierare för ett skalärvärde av JSON-data.</span><span class="sxs-lookup"><span data-stu-id="92828-111">The identifier of a scalar value of JSON data.</span></span>

## <a name="return-values"></a><span data-ttu-id="92828-112">Returvärden</span><span class="sxs-lookup"><span data-stu-id="92828-112">Return values</span></span>

<span data-ttu-id="92828-113">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="92828-113">*String*</span></span>

<span data-ttu-id="92828-114">Det resulterande textvärdet.</span><span class="sxs-lookup"><span data-stu-id="92828-114">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="92828-115">Exempel</span><span class="sxs-lookup"><span data-stu-id="92828-115">Example</span></span>

<span data-ttu-id="92828-116">**JsonField** datakälla innehåller följande data JSON-format: **{"BuildNumber":"7.3.1234.1", "KeyThumbprint":"7366E"}**.</span><span class="sxs-lookup"><span data-stu-id="92828-116">The **JsonField** data source contains the following data in JSON format: **{"BuildNumber":"7.3.1234.1", "KeyThumbprint":"7366E"}**.</span></span> <span data-ttu-id="92828-117">I det här fallet returnerar uttrycket `JSONVALUE (JsonField, "BuildNumber")` följande värde av datatypen *Sträng*: **"7.3.1234.1"**.</span><span class="sxs-lookup"><span data-stu-id="92828-117">In this case, the expression `JSONVALUE (JsonField, "BuildNumber")` returns the following value of the *String* data type: **"7.3.1234.1"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="92828-118">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="92828-118">Additional resources</span></span>

[<span data-ttu-id="92828-119">Textfunktioner</span><span class="sxs-lookup"><span data-stu-id="92828-119">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]