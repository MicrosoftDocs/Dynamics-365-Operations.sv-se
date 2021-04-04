---
title: Funktionen EMPTYRECORD ER
description: Det här avsnittet innehåller information om hur funktionen EMPTYRECORD elektronisk rapportering (ER) används.
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
ms.openlocfilehash: 2d3c34cbff8551b84121201b9489250c07c7799e
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5563256"
---
# <a name="emptyrecord-er-function"></a><span data-ttu-id="ebee2-103">Funktionen EMPTYRECORD ER</span><span class="sxs-lookup"><span data-stu-id="ebee2-103">EMPTYRECORD ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ebee2-104">`EMPTYRECORD`-funktionen returnerar ett null-värde *behållare (post)* som har samma struktur som den angivna postlistan eller posten.</span><span class="sxs-lookup"><span data-stu-id="ebee2-104">The `EMPTYRECORD` function returns a null *Container (record)* value that has the same structure as the specified record list or record.</span></span>

## <a name="syntax"></a><span data-ttu-id="ebee2-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="ebee2-105">Syntax</span></span>

```vb
EMPTYRECORD (list)
```

## <a name="arguments"></a><span data-ttu-id="ebee2-106">Argument</span><span class="sxs-lookup"><span data-stu-id="ebee2-106">Arguments</span></span>

<span data-ttu-id="ebee2-107">`list`: *Postlista* eller *behållare (post)*</span><span class="sxs-lookup"><span data-stu-id="ebee2-107">`list`: *Record list* or *Container (record)*</span></span>

<span data-ttu-id="ebee2-108">Den giltiga sökvägen för en datakälla för antingen typen *Postlista* eller *Behållare (post)*.</span><span class="sxs-lookup"><span data-stu-id="ebee2-108">The valid path of a data source of either the *Record list* or *Container (record)* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="ebee2-109">Returvärden</span><span class="sxs-lookup"><span data-stu-id="ebee2-109">Return values</span></span>

<span data-ttu-id="ebee2-110">*Behållare (post)*</span><span class="sxs-lookup"><span data-stu-id="ebee2-110">*Container (record)*</span></span>

<span data-ttu-id="ebee2-111">Det resulterande postvärdet.</span><span class="sxs-lookup"><span data-stu-id="ebee2-111">The resulting record value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="ebee2-112">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="ebee2-112">Usage notes</span></span>

> [!NOTE] 
> <span data-ttu-id="ebee2-113">En noll post är en post där alla fält innehåller ett tomt värde.</span><span class="sxs-lookup"><span data-stu-id="ebee2-113">A null record is a record where all fields have an empty value.</span></span> <span data-ttu-id="ebee2-114">Ett tomt värde är **0** (noll) för tal, en tom sträng för strängar, osv.</span><span class="sxs-lookup"><span data-stu-id="ebee2-114">An empty value is **0** (zero) for numbers, an empty string for strings, and so on.</span></span>

## <a name="example"></a><span data-ttu-id="ebee2-115">Exempel</span><span class="sxs-lookup"><span data-stu-id="ebee2-115">Example</span></span>

<span data-ttu-id="ebee2-116">`EMPTYRECORD (SPLIT ("abc", 1))` returnerar en ny tom post som har samma struktur som listan som returneras från `SPLIT`-funktionen.</span><span class="sxs-lookup"><span data-stu-id="ebee2-116">`EMPTYRECORD (SPLIT ("abc", 1))` returns a new empty record that has the same structure as the list that is returned by the `SPLIT` function.</span></span> <span data-ttu-id="ebee2-117">Mer information finns i [SPLIT](er-functions-list-split.md).</span><span class="sxs-lookup"><span data-stu-id="ebee2-117">For more information, see [SPLIT](er-functions-list-split.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ebee2-118">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="ebee2-118">Additional resources</span></span>

[<span data-ttu-id="ebee2-119">Inspelningsfunktioner</span><span class="sxs-lookup"><span data-stu-id="ebee2-119">Record functions</span></span>](er-functions-category-record.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]