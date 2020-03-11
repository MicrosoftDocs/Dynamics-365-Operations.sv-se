---
title: JSONVALUE ER-funktion
description: Det här avsnittet innehåller information om hur funktionen JSONVALUE elektronisk rapportering (ER) används.
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
ms.openlocfilehash: 75f20632074cb4dead98991fd6522ab9b20b9965
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041245"
---
# <span data-ttu-id="e0e46-103"><a name="JSONVALUE">JSONVALUE ER-funktion</a></span><span class="sxs-lookup"><span data-stu-id="e0e46-103"><a name="JSONVALUE">JSONVALUE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e0e46-104">`JSONVALUE`-funktionen analyserar data i JSON-format (JavaScript Object Notation) som används av den angivna sökvägen och som extraherar ett skalärvärde som baseras på angivet-ID.</span><span class="sxs-lookup"><span data-stu-id="e0e46-104">The `JSONVALUE` function parses data in JavaScript Object Notation (JSON) format that is accessed at the specified path, and it extracts a scalar value that has the specified ID.</span></span> <span data-ttu-id="e0e46-105">Den returnerar sedan det extraherade skalärvärdet som ett *sträng* värde.</span><span class="sxs-lookup"><span data-stu-id="e0e46-105">It then returns the extracted scalar value as a *String* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="e0e46-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="e0e46-106">Syntax</span></span>

```vb
JSONVALUE (input, path)
```

## <a name="arguments"></a><span data-ttu-id="e0e46-107">Argument</span><span class="sxs-lookup"><span data-stu-id="e0e46-107">Arguments</span></span>

<span data-ttu-id="e0e46-108">`input`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="e0e46-108">`input`: *String*</span></span>

<span data-ttu-id="e0e46-109">Den giltiga sökvägen till en datakälla av typen *Sträng* som innehåller JSON-data.</span><span class="sxs-lookup"><span data-stu-id="e0e46-109">The valid path of a data source of the *String* type that contains JSON data.</span></span>

<span data-ttu-id="e0e46-110">`path`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="e0e46-110">`path`: *String*</span></span>

<span data-ttu-id="e0e46-111">Identifierare för ett skalärvärde av JSON-data.</span><span class="sxs-lookup"><span data-stu-id="e0e46-111">The identifier of a scalar value of JSON data.</span></span>

## <a name="return-values"></a><span data-ttu-id="e0e46-112">Returvärden</span><span class="sxs-lookup"><span data-stu-id="e0e46-112">Return values</span></span>

<span data-ttu-id="e0e46-113">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="e0e46-113">*String*</span></span>

<span data-ttu-id="e0e46-114">Det resulterande textvärdet.</span><span class="sxs-lookup"><span data-stu-id="e0e46-114">The resulting text value.</span></span>

## <a name="example"></a><span data-ttu-id="e0e46-115">Exempel</span><span class="sxs-lookup"><span data-stu-id="e0e46-115">Example</span></span>

<span data-ttu-id="e0e46-116">**JsonField** datakälla innehåller följande data JSON-format: **{"BuildNumber":"7.3.1234.1", "KeyThumbprint":"7366E"}**.</span><span class="sxs-lookup"><span data-stu-id="e0e46-116">The **JsonField** data source contains the following data in JSON format: **{"BuildNumber":"7.3.1234.1", "KeyThumbprint":"7366E"}**.</span></span> <span data-ttu-id="e0e46-117">I det här fallet returnerar uttrycket `JSONVALUE (JsonField, "BuildNumber")` följande värde av datatypen *Sträng*: **"7.3.1234.1"**.</span><span class="sxs-lookup"><span data-stu-id="e0e46-117">In this case, the expression `JSONVALUE (JsonField, "BuildNumber")` returns the following value of the *String* data type: **"7.3.1234.1"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e0e46-118">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="e0e46-118">Additional resources</span></span>

[<span data-ttu-id="e0e46-119">Textfunktioner</span><span class="sxs-lookup"><span data-stu-id="e0e46-119">Text functions</span></span>](er-functions-category-text.md)
