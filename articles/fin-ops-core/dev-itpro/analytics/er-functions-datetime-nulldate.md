---
title: Funktionen NULLDATE ER
description: Det här avsnittet innehåller information om hur funktionen NULLDATE elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/04/2019
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
ms.openlocfilehash: 7761342c6759c11591e06fc7c32f0ddd8bef407a
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916325"
---
# <span data-ttu-id="e574f-103"><a name="NULLDATE">Funktionen NULLDATE ER</a></span><span class="sxs-lookup"><span data-stu-id="e574f-103"><a name="NULLDATE">NULLDATE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e574f-104">`NULLDATE`-funktionen returnerar ett *Datum*-värde som representerar **null**-datumet (1 januari 1900).</span><span class="sxs-lookup"><span data-stu-id="e574f-104">The `NULLDATE` function returns a *Date* value that represents the **null** date (January 1, 1900).</span></span>

## <a name="syntax"></a><span data-ttu-id="e574f-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="e574f-105">Syntax</span></span>

```
NULLDATE () as 
```

## <a name="return-values"></a><span data-ttu-id="e574f-106">Returvärden</span><span class="sxs-lookup"><span data-stu-id="e574f-106">Return values</span></span>

<span data-ttu-id="e574f-107">*Datum*</span><span class="sxs-lookup"><span data-stu-id="e574f-107">*Date*</span></span>

<span data-ttu-id="e574f-108">Det resulterande datum-värdet.</span><span class="sxs-lookup"><span data-stu-id="e574f-108">The resulting date value.</span></span>

## <a name="example-1"></a><span data-ttu-id="e574f-109">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="e574f-109">Example 1</span></span>

<span data-ttu-id="e574f-110">`DATEFORMAT (NULLDATE(), "yyyy-MM-dd")` returnerar **null**-datum, 1 januari 1900, som **"1900-01-01"**, baserat på det angivna anpassade formatet.</span><span class="sxs-lookup"><span data-stu-id="e574f-110">`DATEFORMAT (NULLDATE(), "yyyy-MM-dd")` returns the **null** date, January 1, 1900, as **"1900-01-01"**, based on the specified custom format.</span></span>

## <a name="example-2"></a><span data-ttu-id="e574f-111">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="e574f-111">Example 2</span></span>

<span data-ttu-id="e574f-112">Uttrycket `IF( Invoice.DocumentDate = NULLDATE(), true, false)` returnerar **sant** när värdet i fältet **DocumentDate** är lika med **null**-datum.</span><span class="sxs-lookup"><span data-stu-id="e574f-112">The expression `IF( Invoice.DocumentDate = NULLDATE(), true, false)` returns **True** when the value of the **DocumentDate** field equals the **null** date.</span></span> <span data-ttu-id="e574f-113">I det här exemplet är **Faktura** är en Elektronisk rapportering (ER) datakälla av typen **Ekonomi/tabellposter** och refererar till tabellen CustInvoiceJour-tabellen.</span><span class="sxs-lookup"><span data-stu-id="e574f-113">In this example, **Invoice** is an Electronic reporting (ER) data source of the **Finance/Table records** type, and it refers to the CustInvoiceJour table.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e574f-114">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="e574f-114">Additional resources</span></span>

[<span data-ttu-id="e574f-115">Datum- och tidsfunktioner</span><span class="sxs-lookup"><span data-stu-id="e574f-115">Date and time functions</span></span>](er-functions-category-datetime.md)
