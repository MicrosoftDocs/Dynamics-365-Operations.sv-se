---
title: ENDSWITH ER-funktionen
description: Det här avsnittet innehåller information om hur funktionen ENDSWITH elektronisk rapportering (ER) används.
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
ms.openlocfilehash: bdd2f364e2d0b80d3df20592ec827dcabf99a06c
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5745411"
---
# <a name="endswith-er-function"></a><span data-ttu-id="5ac11-103">ENDSWITH ER-funktionen</span><span class="sxs-lookup"><span data-stu-id="5ac11-103">ENDSWITH ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5ac11-104">Funktionen `ENDSWITH` avgör om den angivna inmatningen slutar med den angivna texten.</span><span class="sxs-lookup"><span data-stu-id="5ac11-104">The `ENDSWITH` function determines whether the specified input ends with the specified text.</span></span> <span data-ttu-id="5ac11-105">Det returnerar *booleskt* värde för **SANT** om den angivna inmatningen slutar med den angivna texten.</span><span class="sxs-lookup"><span data-stu-id="5ac11-105">It returns a *Boolean* value of **TRUE** if the specified input ends with the specified text.</span></span> <span data-ttu-id="5ac11-106">Annars returnerar uttrycket värdet *boolesk* av **FALSK**.</span><span class="sxs-lookup"><span data-stu-id="5ac11-106">Otherwise, it returns a *Boolean* value of **FALSE**.</span></span>

## <a name="syntax"></a><span data-ttu-id="5ac11-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="5ac11-107">Syntax</span></span>

```vb
ENDSWITH (input, end text)
```

## <a name="arguments"></a><span data-ttu-id="5ac11-108">Argument</span><span class="sxs-lookup"><span data-stu-id="5ac11-108">Arguments</span></span>

<span data-ttu-id="5ac11-109">`input`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="5ac11-109">`input`: *String*</span></span>

<span data-ttu-id="5ac11-110">Den giltiga sökvägen för en artikel med en datakälla av typen *Sträng* eller en strängkonstant, vilket värdet kan sluta med det andra argumentet.</span><span class="sxs-lookup"><span data-stu-id="5ac11-110">The valid path of an item of a data source of the *String* type or a string constant, the value of which might end with the second argument.</span></span>

<span data-ttu-id="5ac11-111">`start text`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="5ac11-111">`start text`: *String*</span></span>

<span data-ttu-id="5ac11-112">Den giltiga sökvägen med en datatyp *Sträng* eller en strängkonstant, vilket värdet kan ingå i slutet av det första argumentet.</span><span class="sxs-lookup"><span data-stu-id="5ac11-112">The valid path of a data source of the *String* data type or a string constant, the value of which might be at the end of the first argument.</span></span>

## <a name="return-values"></a><span data-ttu-id="5ac11-113">Returvärden</span><span class="sxs-lookup"><span data-stu-id="5ac11-113">Return values</span></span>

<span data-ttu-id="5ac11-114">*Booleskt*</span><span class="sxs-lookup"><span data-stu-id="5ac11-114">*Boolean*</span></span>

<span data-ttu-id="5ac11-115">Det resulterande *booleska* värdet.</span><span class="sxs-lookup"><span data-stu-id="5ac11-115">The resulting *Boolean* value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="5ac11-116">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="5ac11-116">Usage notes</span></span>

<span data-ttu-id="5ac11-117">Denna funktion kan användas för att ange ett villkorsuttryck för funktionen [FILTER](er-functions-list-filter.md) function endast när relevant mappning är konfigurerad i [Regulatory Configuration Services](../../../finance/localizations/rcs-globalization-feature.md) för att komma åt [Microsoft Dataverse](../data-entities/data-integration-cds.md).</span><span class="sxs-lookup"><span data-stu-id="5ac11-117">This function can be used to specify a condition expression of the [FILTER](er-functions-list-filter.md) function only when the relevant mapping is configured in [Regulatory Configuration Services](../../../finance/localizations/rcs-globalization-feature.md) to access [Microsoft Dataverse](../data-entities/data-integration-cds.md).</span></span> <span data-ttu-id="5ac11-118">I annat fall är ett undantag genereras på designtid.</span><span class="sxs-lookup"><span data-stu-id="5ac11-118">Otherwise, an exception is thrown at design time.</span></span> <span data-ttu-id="5ac11-119">Det meddelande du får rekommenderar att du använder [WHERE](er-functions-list-where.md)-funktionen i stället för `FILTER`-funktionen.</span><span class="sxs-lookup"><span data-stu-id="5ac11-119">The message that you receive recommends that you use the [WHERE](er-functions-list-where.md) function instead of the `FILTER` function.</span></span>

## <a name="example-1"></a><span data-ttu-id="5ac11-120">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="5ac11-120">Example 1</span></span>

<span data-ttu-id="5ac11-121">Uttrycket `ENDSWITH ("abc", "d")` returnerar **FALSE**, medan uttrycket `ENDSWITH ("abc", "C")` returnerar **TRUE**.</span><span class="sxs-lookup"><span data-stu-id="5ac11-121">The expression `ENDSWITH ("abc", "d")` returns **FALSE**, whereas the expression `ENDSWITH ("abc", "C")` returns **TRUE**.</span></span>

## <a name="example-2"></a><span data-ttu-id="5ac11-122">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="5ac11-122">Example 2</span></span>

<span data-ttu-id="5ac11-123">Uttrycket `ENDSWITH (model.InvoiceBase.Customer.PostalAddress.Address, "USA")` returnerar **TRUE** om värdet i fältet **Adress** i datakällan **modell** slutar med strängen **USA**.</span><span class="sxs-lookup"><span data-stu-id="5ac11-123">The expression `ENDSWITH (model.InvoiceBase.Customer.PostalAddress.Address, "USA")` returns **TRUE** if the value of the **Address** field of the **model** data source ends with the string **USA**.</span></span> <span data-ttu-id="5ac11-124">Annars returneras **FALSKT**.</span><span class="sxs-lookup"><span data-stu-id="5ac11-124">Otherwise, it returns **FALSE**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5ac11-125">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="5ac11-125">Additional resources</span></span>

[<span data-ttu-id="5ac11-126">Logiska funktioner</span><span class="sxs-lookup"><span data-stu-id="5ac11-126">Logical functions</span></span>](er-functions-category-logical.md)
