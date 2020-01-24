---
title: NULLCONTAINER ER-funktion
description: Det här avsnittet innehåller information om hur funktionen NULLCONTAINER elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: 1dde102acf18e451cb895b51b28d22102f38936c
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915796"
---
# <span data-ttu-id="64cd2-103"><a name="NULLCONTAINER">NULLCONTAINER ER-funktion</a></span><span class="sxs-lookup"><span data-stu-id="64cd2-103"><a name="NULLCONTAINER">NULLCONTAINER ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="64cd2-104">`NULLCONTAINER`-funktionen returnerar ett null-värde *behållare (post)* som har samma struktur som den angivna postlistan eller posten.</span><span class="sxs-lookup"><span data-stu-id="64cd2-104">The `NULLCONTAINER` function returns a null *Container (record)* value that has the same structure as the specified record list or record.</span></span>

## <a name="syntax"></a><span data-ttu-id="64cd2-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="64cd2-105">Syntax</span></span>

```
NULLCONTAINER (list)
```

## <a name="arguments"></a><span data-ttu-id="64cd2-106">Argument</span><span class="sxs-lookup"><span data-stu-id="64cd2-106">Arguments</span></span>

<span data-ttu-id="64cd2-107">`list`: *Postlista* eller *behållare (post)*</span><span class="sxs-lookup"><span data-stu-id="64cd2-107">`list`: *Record list* or *Container (record)*</span></span>

<span data-ttu-id="64cd2-108">Den giltiga sökvägen för en datakälla för antingen typen *Postlista* eller *Behållare (post)*.</span><span class="sxs-lookup"><span data-stu-id="64cd2-108">The valid path of a data source of either the *Record list* or *Container (record)* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="64cd2-109">Returvärden</span><span class="sxs-lookup"><span data-stu-id="64cd2-109">Return values</span></span>

<span data-ttu-id="64cd2-110">*Behållare (post)*</span><span class="sxs-lookup"><span data-stu-id="64cd2-110">*Container (record)*</span></span>

<span data-ttu-id="64cd2-111">Det resulterande postvärdet.</span><span class="sxs-lookup"><span data-stu-id="64cd2-111">The resulting record value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="64cd2-112">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="64cd2-112">Usage notes</span></span>

> [!NOTE] 
> <span data-ttu-id="64cd2-113">Den här funktionen är föråldrad.</span><span class="sxs-lookup"><span data-stu-id="64cd2-113">This function is obsolete.</span></span> <span data-ttu-id="64cd2-114">Använd `EMPTYRECORD`-funktionen i stället.</span><span class="sxs-lookup"><span data-stu-id="64cd2-114">Use the `EMPTYRECORD` function instead.</span></span> <span data-ttu-id="64cd2-115">Mer information finns i [EMPTYRECORD](er-functions-record-emptyrecord.md).</span><span class="sxs-lookup"><span data-stu-id="64cd2-115">For more information, see [EMPTYRECORD](er-functions-record-emptyrecord.md).</span></span>

## <a name="example"></a><span data-ttu-id="64cd2-116">Exempel</span><span class="sxs-lookup"><span data-stu-id="64cd2-116">Example</span></span>

<span data-ttu-id="64cd2-117">`NULLCONTAINER (SPLIT ("abc", 1))` returnerar en ny tom post som har samma struktur som listan som returneras från `SPLIT`-funktionen.</span><span class="sxs-lookup"><span data-stu-id="64cd2-117">`NULLCONTAINER (SPLIT ("abc", 1))` returns a new empty record that has the same structure as the list that is returned by the `SPLIT` function.</span></span> <span data-ttu-id="64cd2-118">Mer information finns i [SPLIT](er-functions-list-split.md).</span><span class="sxs-lookup"><span data-stu-id="64cd2-118">For more information, see [SPLIT](er-functions-list-split.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="64cd2-119">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="64cd2-119">Additional resources</span></span>

[<span data-ttu-id="64cd2-120">Inspelningsfunktioner</span><span class="sxs-lookup"><span data-stu-id="64cd2-120">Record functions</span></span>](er-functions-category-record.md)
