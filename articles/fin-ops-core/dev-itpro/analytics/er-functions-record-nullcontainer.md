---
title: NULLCONTAINER ER-funktion
description: Det här avsnittet innehåller information om hur funktionen NULLCONTAINER elektronisk rapportering (ER) används.
author: NickSelin
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
ms.openlocfilehash: af6651ef3c62bd8d1285fa8179ac923d3c333ce7
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746517"
---
# <a name="nullcontainer-er-function"></a><span data-ttu-id="092b7-103">NULLCONTAINER ER-funktion</span><span class="sxs-lookup"><span data-stu-id="092b7-103">NULLCONTAINER ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="092b7-104">`NULLCONTAINER`-funktionen returnerar ett null-värde *behållare (post)* som har samma struktur som den angivna postlistan eller posten.</span><span class="sxs-lookup"><span data-stu-id="092b7-104">The `NULLCONTAINER` function returns a null *Container (record)* value that has the same structure as the specified record list or record.</span></span>

## <a name="syntax"></a><span data-ttu-id="092b7-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="092b7-105">Syntax</span></span>

```vb
NULLCONTAINER (list)
```

## <a name="arguments"></a><span data-ttu-id="092b7-106">Argument</span><span class="sxs-lookup"><span data-stu-id="092b7-106">Arguments</span></span>

<span data-ttu-id="092b7-107">`list`: *Postlista* eller *behållare (post)*</span><span class="sxs-lookup"><span data-stu-id="092b7-107">`list`: *Record list* or *Container (record)*</span></span>

<span data-ttu-id="092b7-108">Den giltiga sökvägen för en datakälla för antingen typen *Postlista* eller *Behållare (post)*.</span><span class="sxs-lookup"><span data-stu-id="092b7-108">The valid path of a data source of either the *Record list* or *Container (record)* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="092b7-109">Returvärden</span><span class="sxs-lookup"><span data-stu-id="092b7-109">Return values</span></span>

<span data-ttu-id="092b7-110">*Behållare (post)*</span><span class="sxs-lookup"><span data-stu-id="092b7-110">*Container (record)*</span></span>

<span data-ttu-id="092b7-111">Det resulterande postvärdet.</span><span class="sxs-lookup"><span data-stu-id="092b7-111">The resulting record value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="092b7-112">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="092b7-112">Usage notes</span></span>

> [!NOTE] 
> <span data-ttu-id="092b7-113">Den här funktionen är föråldrad.</span><span class="sxs-lookup"><span data-stu-id="092b7-113">This function is obsolete.</span></span> <span data-ttu-id="092b7-114">Använd `EMPTYRECORD`-funktionen i stället.</span><span class="sxs-lookup"><span data-stu-id="092b7-114">Use the `EMPTYRECORD` function instead.</span></span> <span data-ttu-id="092b7-115">Mer information finns i [EMPTYRECORD](er-functions-record-emptyrecord.md).</span><span class="sxs-lookup"><span data-stu-id="092b7-115">For more information, see [EMPTYRECORD](er-functions-record-emptyrecord.md).</span></span>

## <a name="example"></a><span data-ttu-id="092b7-116">Exempel</span><span class="sxs-lookup"><span data-stu-id="092b7-116">Example</span></span>

<span data-ttu-id="092b7-117">`NULLCONTAINER (SPLIT ("abc", 1))` returnerar en ny tom post som har samma struktur som listan som returneras från `SPLIT`-funktionen.</span><span class="sxs-lookup"><span data-stu-id="092b7-117">`NULLCONTAINER (SPLIT ("abc", 1))` returns a new empty record that has the same structure as the list that is returned by the `SPLIT` function.</span></span> <span data-ttu-id="092b7-118">Mer information finns i [SPLIT](er-functions-list-split.md).</span><span class="sxs-lookup"><span data-stu-id="092b7-118">For more information, see [SPLIT](er-functions-list-split.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="092b7-119">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="092b7-119">Additional resources</span></span>

[<span data-ttu-id="092b7-120">Inspelningsfunktioner</span><span class="sxs-lookup"><span data-stu-id="092b7-120">Record functions</span></span>](er-functions-category-record.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]