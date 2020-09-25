---
title: Funktionen ENUMERATE ER
description: Det här avsnittet innehåller information om hur funktionen ENUMERATE elektronisk rapportering (ER) används.
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
ms.openlocfilehash: e1871ee41267c2c0e8b35007a47c9601079f05d7
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745259"
---
# <a name="enumerate-er-function"></a><span data-ttu-id="7744d-103">Funktionen ENUMERATE ER</span><span class="sxs-lookup"><span data-stu-id="7744d-103">ENUMERATE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7744d-104">`ENUMERATE`-funktionen returnerar ett nytt *postlist*-värde som består av fasta poster i den angivna listan.</span><span class="sxs-lookup"><span data-stu-id="7744d-104">The `ENUMERATE` function returns a new *Record list* value that consists of enumerated records of the specified list.</span></span>

## <a name="syntax"></a><span data-ttu-id="7744d-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="7744d-105">Syntax</span></span>

```vb
ENUMERATE (list)
```

## <a name="arguments"></a><span data-ttu-id="7744d-106">Argument</span><span class="sxs-lookup"><span data-stu-id="7744d-106">Arguments</span></span>

<span data-ttu-id="7744d-107">`list`: *Post-lista*</span><span class="sxs-lookup"><span data-stu-id="7744d-107">`list`: *Record list*</span></span>

<span data-ttu-id="7744d-108">Den giltiga sökvägen av en datakälla för datatypen *Postlista*.</span><span class="sxs-lookup"><span data-stu-id="7744d-108">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="7744d-109">Returvärden</span><span class="sxs-lookup"><span data-stu-id="7744d-109">Return values</span></span>

<span data-ttu-id="7744d-110">*Post-lista*</span><span class="sxs-lookup"><span data-stu-id="7744d-110">*Record list*</span></span>

<span data-ttu-id="7744d-111">Den resulterande listan med poster.</span><span class="sxs-lookup"><span data-stu-id="7744d-111">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="7744d-112">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="7744d-112">Usage notes</span></span>

<span data-ttu-id="7744d-113">Listan över fasta poster som returneras exponerar följande ytterligare element:</span><span class="sxs-lookup"><span data-stu-id="7744d-113">The list of enumerated records that is returned exposes the following additional elements:</span></span>

- <span data-ttu-id="7744d-114">Posten av fält (komponenten **Värde**)</span><span class="sxs-lookup"><span data-stu-id="7744d-114">The record of fields (**Value** component)</span></span>
- <span data-ttu-id="7744d-115">Den aktuella postens index (**Number** component)</span><span class="sxs-lookup"><span data-stu-id="7744d-115">The current record index (**Number** component)</span></span>

## <a name="example"></a><span data-ttu-id="7744d-116">Exempel</span><span class="sxs-lookup"><span data-stu-id="7744d-116">Example</span></span>

<span data-ttu-id="7744d-117">I följande illustration har datakällan **Enumerated** skapat en numrerad lista över leverantörsposter från datakällan **Vendors** som refererar till tabellen VendTable.</span><span class="sxs-lookup"><span data-stu-id="7744d-117">In the following illustration, an **Enumerated** data source is created as an enumerated list of vendor records from the **Vendors** data source that refers to the VendTable table.</span></span>

<a href="./media/picture-enumerate-datasource.jpg"><img src="./media/picture-enumerate-datasource.jpg" alt="Enumerated data source" class="alignnone wp-image-290711 size-full" width="387" height="136" /></a>

<span data-ttu-id="7744d-118">Följande illustration visar flödet av ER-format (elektronisk rapportering).</span><span class="sxs-lookup"><span data-stu-id="7744d-118">The following illustration shows the Electronic reporting (ER) format.</span></span> <span data-ttu-id="7744d-119">I den här formatlayouten skapas bindningar för att skapa utdata i XML-format.</span><span class="sxs-lookup"><span data-stu-id="7744d-119">In this format, data bindings are created to generate output in XML format.</span></span> <span data-ttu-id="7744d-120">Dessa utdata visar enskilda leverantörer som fasta noder.</span><span class="sxs-lookup"><span data-stu-id="7744d-120">This output presents individual vendors as enumerated nodes.</span></span>

<a href="./media/picture-enumerate-format.jpg"><img src="./media/picture-enumerate-format.jpg" alt="Format that has data bindings" class="alignnone wp-image-290721 size-full" width="414" height="138" /></a>

<span data-ttu-id="7744d-121">Följande illustration visar resultatet när det designade formatet har körts.</span><span class="sxs-lookup"><span data-stu-id="7744d-121">The following illustration shows the result when the designed format is run.</span></span>

<a href="./media/picture-enumerate-result.jpg"><img src="./media/picture-enumerate-result.jpg" alt="Result of running the format" class="alignnone wp-image-290731 size-full" width="567" height="176" /></a>

## <a name="additional-resources"></a><span data-ttu-id="7744d-122">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="7744d-122">Additional resources</span></span>

[<span data-ttu-id="7744d-123">Lista över funktioner</span><span class="sxs-lookup"><span data-stu-id="7744d-123">List functions</span></span>](er-functions-category-list.md)
