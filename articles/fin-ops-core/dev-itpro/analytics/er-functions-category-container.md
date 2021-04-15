---
title: Lista över ER-funktioner i behållarkategori
description: Det här ämnet ger information om behållarfunktionerna som stöds i elektronisk rapportering (ER).
author: NickSelin
ms.date: 12/14/2020
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
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 95f207538ea4f0f7df775bf28d0dcf6529d1a91c
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5753250"
---
# <a name="list-of-er-functions-in-the-container-category"></a><span data-ttu-id="f0d24-103">Lista över ER-funktioner i behållarkategori</span><span class="sxs-lookup"><span data-stu-id="f0d24-103">List of ER functions in the container category</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f0d24-104">[Elektronisk rapportering (ER)](general-electronic-reporting.md) behållare [funktioner](er-formula-language.md#functions) kan användas för att utföra åtgärder på datakällor av datatypen *behållare*.</span><span class="sxs-lookup"><span data-stu-id="f0d24-104">[Electronic reporting (ER)](general-electronic-reporting.md) container [functions](er-formula-language.md#functions) can be used to perform operations that involve data sources of the *Container* data type.</span></span> <span data-ttu-id="f0d24-105">Dessa operationer uppstår när bearbetningen av data representerar en samling binära data i binärt stort objekt (BLOB) format.</span><span class="sxs-lookup"><span data-stu-id="f0d24-105">These operations occur when the processing data represents a collection of binary data in binary large object (BLOB) format.</span></span> <span data-ttu-id="f0d24-106">Det här avsnittet innehåller en sammanfattning av dessa funktioner.</span><span class="sxs-lookup"><span data-stu-id="f0d24-106">This topic provides a summary of these functions.</span></span>

## <a name="list-of-supported-functions"></a><span data-ttu-id="f0d24-107">Lista över funktioner som stöds</span><span class="sxs-lookup"><span data-stu-id="f0d24-107">List of supported functions</span></span>

| <span data-ttu-id="f0d24-108">Funktion</span><span class="sxs-lookup"><span data-stu-id="f0d24-108">Function</span></span> | <span data-ttu-id="f0d24-109">beskrivning</span><span class="sxs-lookup"><span data-stu-id="f0d24-109">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="f0d24-110">Base64StringToContainer</span><span class="sxs-lookup"><span data-stu-id="f0d24-110">Base64StringToContainer</span></span>](er-functions-container-base64stringtocontainer.md) | <span data-ttu-id="f0d24-111">Den här funktionen returnerar ett värde för *behållare* som består av binärt innehåll som avkodas från den angivna ASCII-strängen som representerar en Base64-grupp av kodningsscheman för binär till text.</span><span class="sxs-lookup"><span data-stu-id="f0d24-111">This function returns a *Container* value that consists of binary content that is decoded from the specified ASCII string that represents a Base64 group of binary-to-text encoding schemes.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="f0d24-112">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="f0d24-112">Additional resources</span></span>

[<span data-ttu-id="f0d24-113">Översikt över elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="f0d24-113">Electronic Reporting overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="f0d24-114">Formeldesigner i elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="f0d24-114">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)

[<span data-ttu-id="f0d24-115">Formelspråk i elektronisk rapportering</span><span class="sxs-lookup"><span data-stu-id="f0d24-115">Electronic reporting formula language</span></span>](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]