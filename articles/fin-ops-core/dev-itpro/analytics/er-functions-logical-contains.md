---
title: CONTAINS ER funktion
description: Det här avsnittet innehåller information om hur funktionen CONTAINS elektronisk rapportering (ER) används.
author: NickSelin
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
ms.openlocfilehash: c1d2d761a38d0edfb9abd439e0f710b336f54927
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5745435"
---
# <a name="contains-er-function"></a><span data-ttu-id="ae0db-103">CONTAINS ER funktion</span><span class="sxs-lookup"><span data-stu-id="ae0db-103">CONTAINS ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ae0db-104">Funktionen `CONTAINS` avgör om den angivna inmatningen innehåller den angivna texten.</span><span class="sxs-lookup"><span data-stu-id="ae0db-104">The `CONTAINS` function determines whether the specified input contains the specified text.</span></span> <span data-ttu-id="ae0db-105">Det returnerar *booleskt* värde för **SANT** om den angivna inmatningen innehåller den angivna texten.</span><span class="sxs-lookup"><span data-stu-id="ae0db-105">It returns a *Boolean* value of **TRUE** if the specified input contains the specified text.</span></span> <span data-ttu-id="ae0db-106">Annars returnerar uttrycket värdet *boolesk* av **FALSK**.</span><span class="sxs-lookup"><span data-stu-id="ae0db-106">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="ae0db-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="ae0db-107">Syntax</span></span>

```vb
CONTAINS (input, search text)
```

## <a name="arguments"></a><span data-ttu-id="ae0db-108">Argument</span><span class="sxs-lookup"><span data-stu-id="ae0db-108">Arguments</span></span>

<span data-ttu-id="ae0db-109">`input`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="ae0db-109">`input`: *String*</span></span>

<span data-ttu-id="ae0db-110">Den giltiga sökvägen för en artikel med en datakälla av typen *Sträng* eller en strängkonstant, vilket värdet kan innehålla det andra argumentet.</span><span class="sxs-lookup"><span data-stu-id="ae0db-110">The valid path of an item of a data source of the *String* type or a string constant, the value of which might contain the second argument.</span></span>

<span data-ttu-id="ae0db-111">`search text`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="ae0db-111">`search text`: *String*</span></span>

<span data-ttu-id="ae0db-112">Den giltiga sökvägen med en datatyp *Sträng* eller en strängkonstant, vilket värdet kan ingå i det första argumentet.</span><span class="sxs-lookup"><span data-stu-id="ae0db-112">The valid path of a data source of the *String* data type or a string constant, the value of which might be contained in the first argument.</span></span>

## <a name="return-values"></a><span data-ttu-id="ae0db-113">Returvärden</span><span class="sxs-lookup"><span data-stu-id="ae0db-113">Return values</span></span>

<span data-ttu-id="ae0db-114">*Booleskt*</span><span class="sxs-lookup"><span data-stu-id="ae0db-114">*Boolean*</span></span>

<span data-ttu-id="ae0db-115">Det resulterande *booleska* värdet.</span><span class="sxs-lookup"><span data-stu-id="ae0db-115">The resulting *Boolean* value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="ae0db-116">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="ae0db-116">Usage notes</span></span>

<span data-ttu-id="ae0db-117">Denna funktion kan användas för att ange ett villkorsuttryck för funktionen [FILTER](er-functions-list-filter.md) function endast när relevant mappning är konfigurerad i [Regulatory Configuration Services](../../../finance/localizations/rcs-globalization-feature.md) för att komma åt [Microsoft Dataverse](../data-entities/data-integration-cds.md).</span><span class="sxs-lookup"><span data-stu-id="ae0db-117">This function can be used to specify a condition expression of the [FILTER](er-functions-list-filter.md) function only when the relevant mapping is configured in [Regulatory Configuration Services](../../../finance/localizations/rcs-globalization-feature.md) to access [Microsoft Dataverse](../data-entities/data-integration-cds.md).</span></span> <span data-ttu-id="ae0db-118">I annat fall är ett undantag genereras på designtid.</span><span class="sxs-lookup"><span data-stu-id="ae0db-118">Otherwise, an exception is thrown at design time.</span></span> <span data-ttu-id="ae0db-119">Det meddelande du får rekommenderar att du använder [WHERE](er-functions-list-where.md)-funktionen i stället för `FILTER`-funktionen.</span><span class="sxs-lookup"><span data-stu-id="ae0db-119">The message that you receive recommends that you use the [WHERE](er-functions-list-where.md) function instead of the `FILTER` function.</span></span>

## <a name="example-1"></a><span data-ttu-id="ae0db-120">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="ae0db-120">Example 1</span></span>

<span data-ttu-id="ae0db-121">Uttrycket `CONTAINS ("abc", "d")` returnerar **FALSE**, medan uttrycket `CONTAINS ("abc", "C")` returnerar **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="ae0db-121">The expression `CONTAINS ("abc", "d")` returns **FALSE**, whereas the expression `CONTAINS ("abc", "C")` returns **TRUE**.</span></span>

## <a name="example-2"></a><span data-ttu-id="ae0db-122">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="ae0db-122">Example 2</span></span>

<span data-ttu-id="ae0db-123">Uttrycket `CONTAINS (model.InvoiceBase.Customer.PostalAddress.Address, "DEU")` returnerar **TRUE** om värdet i fältet **Adress** i datakällan **modell** innehåller strängen **DEU**.</span><span class="sxs-lookup"><span data-stu-id="ae0db-123">The expression `CONTAINS (model.InvoiceBase.Customer.PostalAddress.Address, "DEU")` returns **TRUE** if the value of the **Address** field of the **model** data source contains the string **DEU**.</span></span> <span data-ttu-id="ae0db-124">Annars returneras **FALSKT**.</span><span class="sxs-lookup"><span data-stu-id="ae0db-124">Otherwise, it returns **FALSE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ae0db-125">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="ae0db-125">Additional resources</span></span>

[<span data-ttu-id="ae0db-126">Logiska funktioner</span><span class="sxs-lookup"><span data-stu-id="ae0db-126">Logical functions</span></span>](er-functions-category-logical.md)
