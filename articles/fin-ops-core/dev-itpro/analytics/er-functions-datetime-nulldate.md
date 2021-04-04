---
title: Funktionen NULLDATE ER
description: Det här avsnittet innehåller information om hur funktionen NULLDATE elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/04/2019
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
ms.openlocfilehash: 79d37247653aa297fdee2c770180916b9a9a5fc5
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5563472"
---
# <a name="nulldate-er-function"></a><span data-ttu-id="adede-103">Funktionen NULLDATE ER</span><span class="sxs-lookup"><span data-stu-id="adede-103">NULLDATE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="adede-104">`NULLDATE`-funktionen returnerar ett *Datum*-värde som representerar **null**-datumet (1 januari 1900).</span><span class="sxs-lookup"><span data-stu-id="adede-104">The `NULLDATE` function returns a *Date* value that represents the **null** date (January 1, 1900).</span></span>

## <a name="syntax"></a><span data-ttu-id="adede-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="adede-105">Syntax</span></span>

```vb
NULLDATE () as 
```

## <a name="return-values"></a><span data-ttu-id="adede-106">Returvärden</span><span class="sxs-lookup"><span data-stu-id="adede-106">Return values</span></span>

<span data-ttu-id="adede-107">*Datum*</span><span class="sxs-lookup"><span data-stu-id="adede-107">*Date*</span></span>

<span data-ttu-id="adede-108">Det resulterande datum-värdet.</span><span class="sxs-lookup"><span data-stu-id="adede-108">The resulting date value.</span></span>

## <a name="example-1"></a><span data-ttu-id="adede-109">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="adede-109">Example 1</span></span>

<span data-ttu-id="adede-110">`DATEFORMAT (NULLDATE(), "yyyy-MM-dd")` returnerar **null**-datum, 1 januari 1900, som **"1900-01-01"**, baserat på det angivna anpassade formatet.</span><span class="sxs-lookup"><span data-stu-id="adede-110">`DATEFORMAT (NULLDATE(), "yyyy-MM-dd")` returns the **null** date, January 1, 1900, as **"1900-01-01"**, based on the specified custom format.</span></span>

## <a name="example-2"></a><span data-ttu-id="adede-111">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="adede-111">Example 2</span></span>

<span data-ttu-id="adede-112">Uttrycket `IF( Invoice.DocumentDate = NULLDATE(), true, false)` returnerar **sant** när värdet i fältet **DocumentDate** är lika med **null**-datum.</span><span class="sxs-lookup"><span data-stu-id="adede-112">The expression `IF( Invoice.DocumentDate = NULLDATE(), true, false)` returns **True** when the value of the **DocumentDate** field equals the **null** date.</span></span> <span data-ttu-id="adede-113">I det här exemplet är **Faktura** är en Elektronisk rapportering (ER) datakälla av typen **Ekonomi/tabellposter** och refererar till tabellen CustInvoiceJour-tabellen.</span><span class="sxs-lookup"><span data-stu-id="adede-113">In this example, **Invoice** is an Electronic reporting (ER) data source of the **Finance/Table records** type, and it refers to the CustInvoiceJour table.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="adede-114">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="adede-114">Additional resources</span></span>

[<span data-ttu-id="adede-115">Datum- och tidsfunktioner</span><span class="sxs-lookup"><span data-stu-id="adede-115">Date and time functions</span></span>](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]