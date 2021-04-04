---
title: JSONVALUE ER-funktion
description: Det här avsnittet innehåller information om hur funktionen JSONVALUE elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
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
ms.openlocfilehash: 203fe1b1616f724ddf3015258306e0d9e8d4f599
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5570026"
---
# <a name="jsonvalue-er-function"></a><span data-ttu-id="884eb-103">JSONVALUE ER-funktion</span><span class="sxs-lookup"><span data-stu-id="884eb-103">JSONVALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="884eb-104">`JSONVALUE`-funktionen analyserar data i JSON-format (JavaScript Object Notation) som används av den angivna sökvägen och som extraherar ett skalärvärde som baseras på angivet-ID.</span><span class="sxs-lookup"><span data-stu-id="884eb-104">The `JSONVALUE` function parses data in JavaScript Object Notation (JSON) format that is accessed at the specified path, and it extracts a scalar value that has the specified ID.</span></span> <span data-ttu-id="884eb-105">Den returnerar sedan det extraherade skalärvärdet som ett *sträng* värde.</span><span class="sxs-lookup"><span data-stu-id="884eb-105">It then returns the extracted scalar value as a *String* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="884eb-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="884eb-106">Syntax</span></span>

```vb
JSONVALUE (input, path)
```

## <a name="arguments"></a><span data-ttu-id="884eb-107">Argument</span><span class="sxs-lookup"><span data-stu-id="884eb-107">Arguments</span></span>

<span data-ttu-id="884eb-108">`input`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="884eb-108">`input`: *String*</span></span>

<span data-ttu-id="884eb-109">Den giltiga sökvägen till en datakälla av typen *Sträng* som innehåller JSON-data.</span><span class="sxs-lookup"><span data-stu-id="884eb-109">The valid path of a data source of the *String* type that contains JSON data.</span></span>

<span data-ttu-id="884eb-110">`path`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="884eb-110">`path`: *String*</span></span>

<span data-ttu-id="884eb-111">Identifierare för ett skalärvärde av JSON-data.</span><span class="sxs-lookup"><span data-stu-id="884eb-111">The identifier of a scalar value of JSON data.</span></span>

## <a name="return-values"></a><span data-ttu-id="884eb-112">Returvärden</span><span class="sxs-lookup"><span data-stu-id="884eb-112">Return values</span></span>

<span data-ttu-id="884eb-113">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="884eb-113">*String*</span></span>

<span data-ttu-id="884eb-114">Det resulterande textvärdet.</span><span class="sxs-lookup"><span data-stu-id="884eb-114">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="884eb-115">Exempel</span><span class="sxs-lookup"><span data-stu-id="884eb-115">Example</span></span>

<span data-ttu-id="884eb-116">**JsonField** datakälla innehåller följande data JSON-format: **{"BuildNumber":"7.3.1234.1", "KeyThumbprint":"7366E"}**.</span><span class="sxs-lookup"><span data-stu-id="884eb-116">The **JsonField** data source contains the following data in JSON format: **{"BuildNumber":"7.3.1234.1", "KeyThumbprint":"7366E"}**.</span></span> <span data-ttu-id="884eb-117">I det här fallet returnerar uttrycket `JSONVALUE (JsonField, "BuildNumber")` följande värde av datatypen *Sträng*: **"7.3.1234.1"**.</span><span class="sxs-lookup"><span data-stu-id="884eb-117">In this case, the expression `JSONVALUE (JsonField, "BuildNumber")` returns the following value of the *String* data type: **"7.3.1234.1"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="884eb-118">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="884eb-118">Additional resources</span></span>

[<span data-ttu-id="884eb-119">Textfunktioner</span><span class="sxs-lookup"><span data-stu-id="884eb-119">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]