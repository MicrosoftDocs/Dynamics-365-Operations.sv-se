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
ms.openlocfilehash: ea71bfc4b30164fd32e804bf83a46c49cd18d155
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041479"
---
# <span data-ttu-id="39700-103"><a name="NULLCONTAINER">NULLCONTAINER ER-funktion</a></span><span class="sxs-lookup"><span data-stu-id="39700-103"><a name="NULLCONTAINER">NULLCONTAINER ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="39700-104">`NULLCONTAINER`-funktionen returnerar ett null-värde *behållare (post)* som har samma struktur som den angivna postlistan eller posten.</span><span class="sxs-lookup"><span data-stu-id="39700-104">The `NULLCONTAINER` function returns a null *Container (record)* value that has the same structure as the specified record list or record.</span></span>

## <a name="syntax"></a><span data-ttu-id="39700-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="39700-105">Syntax</span></span>

```vb
NULLCONTAINER (list)
```

## <a name="arguments"></a><span data-ttu-id="39700-106">Argument</span><span class="sxs-lookup"><span data-stu-id="39700-106">Arguments</span></span>

<span data-ttu-id="39700-107">`list`: *Postlista* eller *behållare (post)*</span><span class="sxs-lookup"><span data-stu-id="39700-107">`list`: *Record list* or *Container (record)*</span></span>

<span data-ttu-id="39700-108">Den giltiga sökvägen för en datakälla för antingen typen *Postlista* eller *Behållare (post)*.</span><span class="sxs-lookup"><span data-stu-id="39700-108">The valid path of a data source of either the *Record list* or *Container (record)* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="39700-109">Returvärden</span><span class="sxs-lookup"><span data-stu-id="39700-109">Return values</span></span>

<span data-ttu-id="39700-110">*Behållare (post)*</span><span class="sxs-lookup"><span data-stu-id="39700-110">*Container (record)*</span></span>

<span data-ttu-id="39700-111">Det resulterande postvärdet.</span><span class="sxs-lookup"><span data-stu-id="39700-111">The resulting record value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="39700-112">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="39700-112">Usage notes</span></span>

> [!NOTE] 
> <span data-ttu-id="39700-113">Den här funktionen är föråldrad.</span><span class="sxs-lookup"><span data-stu-id="39700-113">This function is obsolete.</span></span> <span data-ttu-id="39700-114">Använd `EMPTYRECORD`-funktionen i stället.</span><span class="sxs-lookup"><span data-stu-id="39700-114">Use the `EMPTYRECORD` function instead.</span></span> <span data-ttu-id="39700-115">Mer information finns i [EMPTYRECORD](er-functions-record-emptyrecord.md).</span><span class="sxs-lookup"><span data-stu-id="39700-115">For more information, see [EMPTYRECORD](er-functions-record-emptyrecord.md).</span></span>

## <a name="example"></a><span data-ttu-id="39700-116">Exempel</span><span class="sxs-lookup"><span data-stu-id="39700-116">Example</span></span>

<span data-ttu-id="39700-117">`NULLCONTAINER (SPLIT ("abc", 1))` returnerar en ny tom post som har samma struktur som listan som returneras från `SPLIT`-funktionen.</span><span class="sxs-lookup"><span data-stu-id="39700-117">`NULLCONTAINER (SPLIT ("abc", 1))` returns a new empty record that has the same structure as the list that is returned by the `SPLIT` function.</span></span> <span data-ttu-id="39700-118">Mer information finns i [SPLIT](er-functions-list-split.md).</span><span class="sxs-lookup"><span data-stu-id="39700-118">For more information, see [SPLIT](er-functions-list-split.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="39700-119">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="39700-119">Additional resources</span></span>

[<span data-ttu-id="39700-120">Inspelningsfunktioner</span><span class="sxs-lookup"><span data-stu-id="39700-120">Record functions</span></span>](er-functions-category-record.md)
