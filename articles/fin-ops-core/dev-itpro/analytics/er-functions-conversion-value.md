---
title: VÄRDE ER-funktion
description: Det här avsnittet innehåller information om hur funktionen VALUE elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: ecbffb7e39d7f2f2bccdfe32d593512a65da163c
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745523"
---
# <a name="value-er-function"></a><span data-ttu-id="e6a0c-103">VÄRDE ER-funktion</span><span class="sxs-lookup"><span data-stu-id="e6a0c-103">VALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e6a0c-104">`VALUE`-funktionen returnerar ett *verkligt* värde som konverteras från den angivna strängen.</span><span class="sxs-lookup"><span data-stu-id="e6a0c-104">The `VALUE` function returns a *Real* value that is converted from the specified string.</span></span>

## <a name="syntax"></a><span data-ttu-id="e6a0c-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="e6a0c-105">Syntax</span></span>

```vb
VALUE (text)
```

## <a name="arguments"></a><span data-ttu-id="e6a0c-106">Argument</span><span class="sxs-lookup"><span data-stu-id="e6a0c-106">Arguments</span></span>

<span data-ttu-id="e6a0c-107">`text`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="e6a0c-107">`text`: *String*</span></span>

<span data-ttu-id="e6a0c-108">Ett strängvärde som måste konverteras till ett numeriskt värde. </span><span class="sxs-lookup"><span data-stu-id="e6a0c-108">A string value that must be converted to a numeric value.</span></span>

## <a name="return-values"></a><span data-ttu-id="e6a0c-109">Returvärden</span><span class="sxs-lookup"><span data-stu-id="e6a0c-109">Return values</span></span>

<span data-ttu-id="e6a0c-110">*Realtal*</span><span class="sxs-lookup"><span data-stu-id="e6a0c-110">*Real*</span></span>

<span data-ttu-id="e6a0c-111">Det resulterande numeriska värdet.</span><span class="sxs-lookup"><span data-stu-id="e6a0c-111">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="e6a0c-112">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="e6a0c-112">Usage notes</span></span>

<span data-ttu-id="e6a0c-113">Kommatecken och punkter (.) betraktas som decimalavgränsare och ett inledande bindestreck (-) används som ett negativt tecken.</span><span class="sxs-lookup"><span data-stu-id="e6a0c-113">Commas and dot characters (.) are considered decimal separators, and a leading hyphen (-) is used as a negative sign.</span></span> <span data-ttu-id="e6a0c-114">Ett undantag genereras vid körning om den specificerade strängen innehåller andra icke-numeriska tecken.</span><span class="sxs-lookup"><span data-stu-id="e6a0c-114">An exception is thrown at runtime if the specified string contains other non-numeric characters.</span></span>

## <a name="example-1"></a><span data-ttu-id="e6a0c-115">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="e6a0c-115">Example 1</span></span>

<span data-ttu-id="e6a0c-116">`VALUE ("1 234,56")` genererar ett undantag.</span><span class="sxs-lookup"><span data-stu-id="e6a0c-116">`VALUE ("1 234,56")` throws an exception.</span></span>

## <a name="example-2"></a><span data-ttu-id="e6a0c-117">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="e6a0c-117">Example 2</span></span>

<span data-ttu-id="e6a0c-118">`VALUE ("1234,56")` returnerar **1234.56**.</span><span class="sxs-lookup"><span data-stu-id="e6a0c-118">`VALUE ("1234,56")` returns **1234.56**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e6a0c-119">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="e6a0c-119">Additional resources</span></span>

[<span data-ttu-id="e6a0c-120">Funktioner för typkonvertering</span><span class="sxs-lookup"><span data-stu-id="e6a0c-120">Type conversion functions</span></span>](er-functions-category-type-conversion.md)
