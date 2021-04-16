---
title: GUIDVALUE ER-funktion
description: Det här avsnittet innehåller information om hur funktionen GUIDVALUE elektronisk rapportering (ER) används.
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
ms.openlocfilehash: ec8222708b999a17794a396b5bf807dab037799d
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746397"
---
# <a name="guidvalue-er-function"></a><span data-ttu-id="e27cb-103">GUIDVALUE ER-funktion</span><span class="sxs-lookup"><span data-stu-id="e27cb-103">GUIDVALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e27cb-104">`GUIDVALUE`-funktionen konverterar det angivna indata för typen *Sträng* till ett dataobjekt i typen *GUID*.</span><span class="sxs-lookup"><span data-stu-id="e27cb-104">The `GUIDVALUE` function converts the specified input of the *String* type to a data item of the *GUID* type.</span></span>

## <a name="syntax"></a><span data-ttu-id="e27cb-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="e27cb-105">Syntax</span></span>

```vb
GUIDVALUE (input)
```

## <a name="arguments"></a><span data-ttu-id="e27cb-106">Argument</span><span class="sxs-lookup"><span data-stu-id="e27cb-106">Arguments</span></span>

<span data-ttu-id="e27cb-107">`input`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="e27cb-107">`input`: *String*</span></span>

<span data-ttu-id="e27cb-108">Den giltiga sökvägen till en datakälla av typen *Sträng*.</span><span class="sxs-lookup"><span data-stu-id="e27cb-108">The valid path of a data source of the *String* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="e27cb-109">Returvärden</span><span class="sxs-lookup"><span data-stu-id="e27cb-109">Return values</span></span>

<span data-ttu-id="e27cb-110">*GUID*</span><span class="sxs-lookup"><span data-stu-id="e27cb-110">*GUID*</span></span>

<span data-ttu-id="e27cb-111">Det resulterande GUID-värdet (globalt unikt ID).</span><span class="sxs-lookup"><span data-stu-id="e27cb-111">The resulting globally unique identifier (GUID) value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="e27cb-112">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="e27cb-112">Usage notes</span></span>

<span data-ttu-id="e27cb-113">För att göra en konvertering i motsatt riktning (d.v.s. konvertera angiven indata för datatypen *GUID* till ett dataobjekt i datatypen *sträng*), kan du använda funktionen [TEXT](er-functions-text-text.md).</span><span class="sxs-lookup"><span data-stu-id="e27cb-113">To do a conversion in the opposite direction (that is, to convert specified input of the *GUID* data type to a data item of the *String* data type), you can use the [TEXT](er-functions-text-text.md) function.</span></span>

## <a name="example"></a><span data-ttu-id="e27cb-114">Exempel</span><span class="sxs-lookup"><span data-stu-id="e27cb-114">Example</span></span>

<span data-ttu-id="e27cb-115">Du definierar följande datakällor i din modellmappning:</span><span class="sxs-lookup"><span data-stu-id="e27cb-115">You define the following data sources in your model mapping:</span></span>

- <span data-ttu-id="e27cb-116">En **myID**-datakälla av typen *beräknat fält* som innehåller uttrycket `GUIDVALUE ("AF5CCDAC-F728-4609-8C8B- A4B30B0C0AA0")`</span><span class="sxs-lookup"><span data-stu-id="e27cb-116">A **myID** data source of the *Calculated field* type that contains the expression `GUIDVALUE ("AF5CCDAC-F728-4609-8C8B- A4B30B0C0AA0")`</span></span>
- <span data-ttu-id="e27cb-117">En **användar** datakälla av typen *registerposter* som refererar till tabellen UserInfo</span><span class="sxs-lookup"><span data-stu-id="e27cb-117">A **Users** data source of the *Table records* type that refers to the UserInfo table</span></span>

<span data-ttu-id="e27cb-118">Du kan sedan använda ett uttryck som `FILTER (Users, Users.objectId = myID)` för att filtrera tabellen UserInfo via fältet **objectId** för datatypen *GUID*.</span><span class="sxs-lookup"><span data-stu-id="e27cb-118">You can then use an expression such as `FILTER (Users, Users.objectId = myID)` to filter the UserInfo table by the **objectId** field of the *GUID* data type.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e27cb-119">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="e27cb-119">Additional resources</span></span>

[<span data-ttu-id="e27cb-120">Textfunktioner</span><span class="sxs-lookup"><span data-stu-id="e27cb-120">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]