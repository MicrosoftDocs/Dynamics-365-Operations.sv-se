---
title: CONTAINS ER funktion
description: Det här avsnittet innehåller information om hur funktionen CONTAINS elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 02/11/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2021-02-01
ms.dyn365.ops.version: AX 10.0.18
ms.openlocfilehash: 81964681688cebf870bc9b6c59aff0b7fdd82449
ms.sourcegitcommit: 08ac570bece3e4ee4a0f632f51623e328536dfcf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/08/2021
ms.locfileid: "5557554"
---
# <a name="contains-er-function"></a><span data-ttu-id="56156-103">CONTAINS ER funktion</span><span class="sxs-lookup"><span data-stu-id="56156-103">CONTAINS ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="56156-104">Funktionen `CONTAINS` avgör om den angivna inmatningen innehåller den angivna texten.</span><span class="sxs-lookup"><span data-stu-id="56156-104">The `CONTAINS` function determines whether the specified input contains the specified text.</span></span> <span data-ttu-id="56156-105">Det returnerar *booleskt* värde för **SANT** om den angivna inmatningen innehåller den angivna texten.</span><span class="sxs-lookup"><span data-stu-id="56156-105">It returns a *Boolean* value of **TRUE** if the specified input contains the specified text.</span></span> <span data-ttu-id="56156-106">Annars returnerar uttrycket värdet *boolesk* av **FALSK**.</span><span class="sxs-lookup"><span data-stu-id="56156-106">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="56156-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="56156-107">Syntax</span></span>

```vb
CONTAINS (input, search text)
```

## <a name="arguments"></a><span data-ttu-id="56156-108">Argument</span><span class="sxs-lookup"><span data-stu-id="56156-108">Arguments</span></span>

<span data-ttu-id="56156-109">`input`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="56156-109">`input`: *String*</span></span>

<span data-ttu-id="56156-110">Den giltiga sökvägen för en artikel med en datakälla av typen *Sträng* eller en strängkonstant, vilket värdet kan innehålla det andra argumentet.</span><span class="sxs-lookup"><span data-stu-id="56156-110">The valid path of an item of a data source of the *String* type or a string constant, the value of which might contain the second argument.</span></span>

<span data-ttu-id="56156-111">`search text`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="56156-111">`search text`: *String*</span></span>

<span data-ttu-id="56156-112">Den giltiga sökvägen med en datatyp *Sträng* eller en strängkonstant, vilket värdet kan ingå i det första argumentet.</span><span class="sxs-lookup"><span data-stu-id="56156-112">The valid path of a data source of the *String* data type or a string constant, the value of which might be contained in the first argument.</span></span>

## <a name="return-values"></a><span data-ttu-id="56156-113">Returvärden</span><span class="sxs-lookup"><span data-stu-id="56156-113">Return values</span></span>

<span data-ttu-id="56156-114">*Booleskt*</span><span class="sxs-lookup"><span data-stu-id="56156-114">*Boolean*</span></span>

<span data-ttu-id="56156-115">Det resulterande *booleska* värdet.</span><span class="sxs-lookup"><span data-stu-id="56156-115">The resulting *Boolean* value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="56156-116">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="56156-116">Usage notes</span></span>

<span data-ttu-id="56156-117">Denna funktion kan användas för att ange ett villkorsuttryck för funktionen [FILTER](er-functions-list-filter.md) function endast när relevant mappning är konfigurerad i [Regulatory Configuration Services](../../../finance/localizations/rcs-globalization-feature.md) för att komma åt [Microsoft Dataverse](../data-entities/data-integration-cds.md).</span><span class="sxs-lookup"><span data-stu-id="56156-117">This function can be used to specify a condition expression of the [FILTER](er-functions-list-filter.md) function only when the relevant mapping is configured in [Regulatory Configuration Services](../../../finance/localizations/rcs-globalization-feature.md) to access [Microsoft Dataverse](../data-entities/data-integration-cds.md).</span></span> <span data-ttu-id="56156-118">I annat fall är ett undantag genereras på designtid.</span><span class="sxs-lookup"><span data-stu-id="56156-118">Otherwise, an exception is thrown at design time.</span></span> <span data-ttu-id="56156-119">Det meddelande du får rekommenderar att du använder [WHERE](er-functions-list-where.md)-funktionen i stället för `FILTER`-funktionen.</span><span class="sxs-lookup"><span data-stu-id="56156-119">The message that you receive recommends that you use the [WHERE](er-functions-list-where.md) function instead of the `FILTER` function.</span></span>

## <a name="example-1"></a><span data-ttu-id="56156-120">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="56156-120">Example 1</span></span>

<span data-ttu-id="56156-121">Uttrycket `CONTAINS ("abc", "d")` returnerar **FALSE**, medan uttrycket `CONTAINS ("abc", "C")` returnerar **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="56156-121">The expression `CONTAINS ("abc", "d")` returns **FALSE**, whereas the expression `CONTAINS ("abc", "C")` returns **TRUE**.</span></span>

## <a name="example-2"></a><span data-ttu-id="56156-122">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="56156-122">Example 2</span></span>

<span data-ttu-id="56156-123">Uttrycket `CONTAINS (model.InvoiceBase.Customer.PostalAddress.Address, "DEU")` returnerar **TRUE** om värdet i fältet **Adress** i datakällan **modell** innehåller strängen **DEU**.</span><span class="sxs-lookup"><span data-stu-id="56156-123">The expression `CONTAINS (model.InvoiceBase.Customer.PostalAddress.Address, "DEU")` returns **TRUE** if the value of the **Address** field of the **model** data source contains the string **DEU**.</span></span> <span data-ttu-id="56156-124">Annars returneras **FALSKT**.</span><span class="sxs-lookup"><span data-stu-id="56156-124">Otherwise, it returns **FALSE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="56156-125">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="56156-125">Additional resources</span></span>

[<span data-ttu-id="56156-126">Logiska funktioner</span><span class="sxs-lookup"><span data-stu-id="56156-126">Logical functions</span></span>](er-functions-category-logical.md)
