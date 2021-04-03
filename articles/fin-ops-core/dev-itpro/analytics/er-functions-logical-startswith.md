---
title: STARTSWITH ER-funktionen
description: Det här avsnittet innehåller information om hur funktionen STARTSWITH elektronisk rapportering (ER) används.
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
ms.openlocfilehash: 22e99d9e131410820abd12536b8d4f3e868c6863
ms.sourcegitcommit: 08ac570bece3e4ee4a0f632f51623e328536dfcf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/08/2021
ms.locfileid: "5557555"
---
# <a name="startswith-er-function"></a><span data-ttu-id="b645e-103">STARTSWITH ER-funktionen</span><span class="sxs-lookup"><span data-stu-id="b645e-103">STARTSWITH ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b645e-104">Den här `STARTSWITH`-funktionen avgör om den angivna inmatningen startar med den angivna texten.</span><span class="sxs-lookup"><span data-stu-id="b645e-104">The `STARTSWITH` function determines whether the specified input starts with the specified text.</span></span> <span data-ttu-id="b645e-105">Det returnerar *booleskt* värde för **SANT** om den angivna inmatningen startar med den angivna texten.</span><span class="sxs-lookup"><span data-stu-id="b645e-105">It returns a *Boolean* value of **TRUE** if the specified input starts with the specified text.</span></span> <span data-ttu-id="b645e-106">Annars returnerar uttrycket värdet *boolesk* av **FALSK**.</span><span class="sxs-lookup"><span data-stu-id="b645e-106">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="b645e-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="b645e-107">Syntax</span></span>

```vb
STARTSWITH (input, start text)
```

## <a name="arguments"></a><span data-ttu-id="b645e-108">Argument</span><span class="sxs-lookup"><span data-stu-id="b645e-108">Arguments</span></span>

<span data-ttu-id="b645e-109">`input`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="b645e-109">`input`: *String*</span></span>

<span data-ttu-id="b645e-110">Den giltiga sökvägen för en artikel med en datakälla av typen *Sträng* eller en strängkonstant, vilket värdet kan starta med det andra argumentet.</span><span class="sxs-lookup"><span data-stu-id="b645e-110">The valid path of an item of a data source of the *String* type or a string constant, the value of which might start with the second argument.</span></span>

<span data-ttu-id="b645e-111">`start text`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="b645e-111">`start text`: *String*</span></span>

<span data-ttu-id="b645e-112">Den giltiga sökvägen med en datatyp *Sträng* eller en strängkonstant, vilket värdet kan ingå i början av det första argumentet.</span><span class="sxs-lookup"><span data-stu-id="b645e-112">The valid path of a data source of the *String* data type or a string constant, the value of which might be at the beginning of the first argument.</span></span>

## <a name="return-values"></a><span data-ttu-id="b645e-113">Returvärden</span><span class="sxs-lookup"><span data-stu-id="b645e-113">Return values</span></span>

<span data-ttu-id="b645e-114">*Booleskt*</span><span class="sxs-lookup"><span data-stu-id="b645e-114">*Boolean*</span></span>

<span data-ttu-id="b645e-115">Det resulterande *booleska* värdet.</span><span class="sxs-lookup"><span data-stu-id="b645e-115">The resulting *Boolean* value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="b645e-116">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="b645e-116">Usage notes</span></span>

<span data-ttu-id="b645e-117">Denna funktion kan användas för att ange ett villkorsuttryck för funktionen [FILTER](er-functions-list-filter.md) function endast när relevant mappning är konfigurerad i [Regulatory Configuration Services](../../../finance/localizations/rcs-globalization-feature.md) för att komma åt [Microsoft Dataverse](../data-entities/data-integration-cds.md).</span><span class="sxs-lookup"><span data-stu-id="b645e-117">This function can be used to specify a condition expression of the [FILTER](er-functions-list-filter.md) function only when the relevant mapping is configured in [Regulatory Configuration Services](../../../finance/localizations/rcs-globalization-feature.md) to access [Microsoft Dataverse](../data-entities/data-integration-cds.md).</span></span> <span data-ttu-id="b645e-118">I annat fall är ett undantag genereras på designtid.</span><span class="sxs-lookup"><span data-stu-id="b645e-118">Otherwise, an exception is thrown at design time.</span></span> <span data-ttu-id="b645e-119">Det meddelande du får rekommenderar att du använder [WHERE](er-functions-list-where.md)-funktionen i stället för `FILTER`-funktionen.</span><span class="sxs-lookup"><span data-stu-id="b645e-119">The message that you receive recommends that you use the [WHERE](er-functions-list-where.md) function instead of the `FILTER` function.</span></span>

## <a name="example-1"></a><span data-ttu-id="b645e-120">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="b645e-120">Example 1</span></span>

<span data-ttu-id="b645e-121">Uttrycket `STARTSWITH ("abc", "d")` returnerar **FALSE**, medan uttrycket `STARTSWITH ("abc", "A")` returnerar **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="b645e-121">The expression `STARTSWITH ("abc", "d")` returns **FALSE**, whereas the expression `STARTSWITH ("abc", "A")` returns **TRUE**.</span></span>

## <a name="example-2"></a><span data-ttu-id="b645e-122">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="b645e-122">Example 2</span></span>

<span data-ttu-id="b645e-123">Uttrycket `STARTSWITH (model.InvoiceBase.Customer.PostalAddress.Address, "123 Coffee Street")` returnerar **TRUE** om värdet i fältet **Adress** i datakällan **modell** startar med strängen **123 Coffee Street**.</span><span class="sxs-lookup"><span data-stu-id="b645e-123">The expression `STARTSWITH (model.InvoiceBase.Customer.PostalAddress.Address, "123 Coffee Street")` returns **TRUE** if the value of the **Address** field of the **model** data source starts with the string **123 Coffee Street**.</span></span> <span data-ttu-id="b645e-124">Annars returneras **FALSKT**.</span><span class="sxs-lookup"><span data-stu-id="b645e-124">Otherwise, it returns **FALSE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b645e-125">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="b645e-125">Additional resources</span></span>

[<span data-ttu-id="b645e-126">Logiska funktioner</span><span class="sxs-lookup"><span data-stu-id="b645e-126">Logical functions</span></span>](er-functions-category-logical.md)
