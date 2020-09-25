---
title: FORMATELEMENTNAME ER-funktion
description: Det här avsnittet innehåller information om hur funktionen FORMATELEMENTNAME elektronisk rapportering (ER) används.
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
ms.openlocfilehash: e8be55d9a90e841d64288b0c618c0012912ddbab
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745643"
---
# <a name="formatelementname-er-function"></a><span data-ttu-id="0e39b-103">FORMATELEMENTNAME ER-funktion</span><span class="sxs-lookup"><span data-stu-id="0e39b-103">FORMATELEMENTNAME ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0e39b-104">`FORMATELEMENTNAME`-funktionen returnerar ett *sträng*-värde som representerar namnet på det aktuella elementet för elektronisk rapportering (ER)-format.</span><span class="sxs-lookup"><span data-stu-id="0e39b-104">The `FORMATELEMENTNAME` function returns a *String* value that represents the name of the current Electronic reporting (ER) format's element.</span></span>

## <a name="syntax"></a><span data-ttu-id="0e39b-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="0e39b-105">Syntax</span></span>

```vb
FORMATELEMENTNAME ()
```

## <a name="return-values"></a><span data-ttu-id="0e39b-106">Returvärden</span><span class="sxs-lookup"><span data-stu-id="0e39b-106">Return values</span></span>

<span data-ttu-id="0e39b-107">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="0e39b-107">*String*</span></span>

<span data-ttu-id="0e39b-108">Det resulterande textvärdet.</span><span class="sxs-lookup"><span data-stu-id="0e39b-108">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="0e39b-109">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="0e39b-109">Usage notes</span></span>

<span data-ttu-id="0e39b-110">Den här funktionen kan anropas i ER-uttryck som har konfigurerats för egenskaperna **Insamlade datanyckelnamn** och **Insamlat datanyckelvärde** egenskaper för en ER-formatkomponent från gruppen **Text** som finns under komponenten **gemensam\\fil** där alternativet **Samla in utgångsdetaljer** är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="0e39b-110">This function can be called in ER expressions that were configured for the **Collected data key name** and **Collected data key value** properties of an ER format component from the **Text** group that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

## <a name="example"></a><span data-ttu-id="0e39b-111">Exempel</span><span class="sxs-lookup"><span data-stu-id="0e39b-111">Example</span></span>

<span data-ttu-id="0e39b-112">För mer information om att använda den här funktionen, se uppgiftsguiden [ER Använd data från formatutmatningen för inventering och summering](tasks/er-format-counting-summing-1.md) (ingår i affärsprocessen **Införskaffa/utveckla komponenter för IT-tjänster/-lösningar**) för mer information om hur du använder dessa funktioner.</span><span class="sxs-lookup"><span data-stu-id="0e39b-112">For more information about how to use this function, see the [ER Use data of format output for counting and summing](tasks/er-format-counting-summing-1.md) task guide, which is part of the **Acquire/Develop IT service/solution components** business process.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0e39b-113">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="0e39b-113">Additional resources</span></span>

[<span data-ttu-id="0e39b-114">Datainsamlingsfunktioner</span><span class="sxs-lookup"><span data-stu-id="0e39b-114">Data collection functions</span></span>](er-functions-category-data-collection.md)
