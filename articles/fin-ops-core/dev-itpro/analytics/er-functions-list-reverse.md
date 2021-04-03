---
title: REVERSE ER-funktion
description: Det här avsnittet innehåller information om hur funktionen REVERSE elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: f76582bc8b752fe0322bee8917d8649ed1c024ba
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5567376"
---
# <a name="reverse-er-function"></a><span data-ttu-id="9d322-103">REVERSE ER-funktion</span><span class="sxs-lookup"><span data-stu-id="9d322-103">REVERSE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9d322-104">`REVERSE`-funktionen returnerar den angivna listan som ett värde *postlista* i omvänd sorteringsordning.</span><span class="sxs-lookup"><span data-stu-id="9d322-104">The `REVERSE` function returns the specified list as a *Record list* value in reversed sort order.</span></span>

## <a name="syntax"></a><span data-ttu-id="9d322-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="9d322-105">Syntax</span></span>

```vb
REVERSE (list)
```

## <a name="arguments"></a><span data-ttu-id="9d322-106">Argument</span><span class="sxs-lookup"><span data-stu-id="9d322-106">Arguments</span></span>

<span data-ttu-id="9d322-107">`list`: *Post-lista*</span><span class="sxs-lookup"><span data-stu-id="9d322-107">`list`: *Record list*</span></span>

<span data-ttu-id="9d322-108">Den giltiga sökvägen av en datakälla för datatypen *Postlista*.</span><span class="sxs-lookup"><span data-stu-id="9d322-108">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="9d322-109">Returvärden</span><span class="sxs-lookup"><span data-stu-id="9d322-109">Return values</span></span>

<span data-ttu-id="9d322-110">*Post-lista*</span><span class="sxs-lookup"><span data-stu-id="9d322-110">*Record list*</span></span>

<span data-ttu-id="9d322-111">Den resulterande listan med poster.</span><span class="sxs-lookup"><span data-stu-id="9d322-111">The resulting list of records.</span></span>

## <a name="example-1"></a><span data-ttu-id="9d322-112">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="9d322-112">Example 1</span></span>

<span data-ttu-id="9d322-113">Om du anger datakällans **DS** av typen *Beräknat fält* och den innehåller uttrycket `SPLIT ("C|B|A", "|")`, kommer uttrycket `FIRST( REVERSE( ORDERBY( DS, DS. Value))).Value` att returnera textvärdet **"C"**.</span><span class="sxs-lookup"><span data-stu-id="9d322-113">If you enter data source **DS** of the *Calculated field* type, and it contains the expression `SPLIT ("C|B|A", "|")`, the expression `FIRST( REVERSE( ORDERBY( DS, DS. Value))).Value` returns the text value **"C"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="9d322-114">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="9d322-114">Example 2</span></span>

<span data-ttu-id="9d322-115">Om **Leverantör** konfigureras som en ER-datakälla som refererar till tabellen VendTable, kommer uttrycket `REVERSE (ORDERBY (Vendors, Vendors.'name()'))` returneras en lista med leverantörerna sorterade efter namn i fallande ordning.</span><span class="sxs-lookup"><span data-stu-id="9d322-115">If **Vendor** is configured as an Electronic reporting (ER) data source that refers to the VendTable table, the expression `REVERSE (ORDERBY (Vendors, Vendors.'name()'))` returns a list of vendors that is sorted by name in descending order.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9d322-116">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="9d322-116">Additional resources</span></span>

[<span data-ttu-id="9d322-117">Lista över funktioner</span><span class="sxs-lookup"><span data-stu-id="9d322-117">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]