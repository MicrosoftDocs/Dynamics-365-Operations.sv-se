---
title: Funktionen EMPTYRECORD ER
description: Det här avsnittet innehåller information om hur funktionen EMPTYRECORD elektronisk rapportering (ER) används.
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
ms.openlocfilehash: e614c06b4cfad628bbd8a966719ed994ce05b792
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746541"
---
# <a name="emptyrecord-er-function"></a><span data-ttu-id="87d42-103">Funktionen EMPTYRECORD ER</span><span class="sxs-lookup"><span data-stu-id="87d42-103">EMPTYRECORD ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="87d42-104">`EMPTYRECORD`-funktionen returnerar ett null-värde *behållare (post)* som har samma struktur som den angivna postlistan eller posten.</span><span class="sxs-lookup"><span data-stu-id="87d42-104">The `EMPTYRECORD` function returns a null *Container (record)* value that has the same structure as the specified record list or record.</span></span>

## <a name="syntax"></a><span data-ttu-id="87d42-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="87d42-105">Syntax</span></span>

```vb
EMPTYRECORD (list)
```

## <a name="arguments"></a><span data-ttu-id="87d42-106">Argument</span><span class="sxs-lookup"><span data-stu-id="87d42-106">Arguments</span></span>

<span data-ttu-id="87d42-107">`list`: *Postlista* eller *behållare (post)*</span><span class="sxs-lookup"><span data-stu-id="87d42-107">`list`: *Record list* or *Container (record)*</span></span>

<span data-ttu-id="87d42-108">Den giltiga sökvägen för en datakälla för antingen typen *Postlista* eller *Behållare (post)*.</span><span class="sxs-lookup"><span data-stu-id="87d42-108">The valid path of a data source of either the *Record list* or *Container (record)* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="87d42-109">Returvärden</span><span class="sxs-lookup"><span data-stu-id="87d42-109">Return values</span></span>

<span data-ttu-id="87d42-110">*Behållare (post)*</span><span class="sxs-lookup"><span data-stu-id="87d42-110">*Container (record)*</span></span>

<span data-ttu-id="87d42-111">Det resulterande postvärdet.</span><span class="sxs-lookup"><span data-stu-id="87d42-111">The resulting record value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="87d42-112">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="87d42-112">Usage notes</span></span>

> [!NOTE] 
> <span data-ttu-id="87d42-113">En noll post är en post där alla fält innehåller ett tomt värde.</span><span class="sxs-lookup"><span data-stu-id="87d42-113">A null record is a record where all fields have an empty value.</span></span> <span data-ttu-id="87d42-114">Ett tomt värde är **0** (noll) för tal, en tom sträng för strängar, osv.</span><span class="sxs-lookup"><span data-stu-id="87d42-114">An empty value is **0** (zero) for numbers, an empty string for strings, and so on.</span></span>

## <a name="example"></a><span data-ttu-id="87d42-115">Exempel</span><span class="sxs-lookup"><span data-stu-id="87d42-115">Example</span></span>

<span data-ttu-id="87d42-116">`EMPTYRECORD (SPLIT ("abc", 1))` returnerar en ny tom post som har samma struktur som listan som returneras från `SPLIT`-funktionen.</span><span class="sxs-lookup"><span data-stu-id="87d42-116">`EMPTYRECORD (SPLIT ("abc", 1))` returns a new empty record that has the same structure as the list that is returned by the `SPLIT` function.</span></span> <span data-ttu-id="87d42-117">Mer information finns i [SPLIT](er-functions-list-split.md).</span><span class="sxs-lookup"><span data-stu-id="87d42-117">For more information, see [SPLIT](er-functions-list-split.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="87d42-118">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="87d42-118">Additional resources</span></span>

[<span data-ttu-id="87d42-119">Inspelningsfunktioner</span><span class="sxs-lookup"><span data-stu-id="87d42-119">Record functions</span></span>](er-functions-category-record.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]