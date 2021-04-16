---
title: LIST ER-funktion
description: Det här avsnittet innehåller information om hur funktionen LIST elektronisk rapportering (ER) används.
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
ms.openlocfilehash: 50cb8858301c030df07ad4af9fe2a9513f41fead
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750422"
---
# <a name="list-er-function"></a><span data-ttu-id="01da4-103">LIST ER-funktion</span><span class="sxs-lookup"><span data-stu-id="01da4-103">LIST ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="01da4-104">`LIST`-funktionen returnerar ett *postlist*-värde som består av en ny lista med poster som skapas från de angivna argumenten.</span><span class="sxs-lookup"><span data-stu-id="01da4-104">The `LIST` function returns a *Record list* value that consists of a new list of records that is created from the specified arguments.</span></span>

## <a name="syntax"></a><span data-ttu-id="01da4-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="01da4-105">Syntax</span></span>

```vb
LIST (record 1 [, record 2, …, record N])
```

## <a name="arguments"></a><span data-ttu-id="01da4-106">Argument</span><span class="sxs-lookup"><span data-stu-id="01da4-106">Arguments</span></span>

<span data-ttu-id="01da4-107">`record 1`: *Behållare (post)*</span><span class="sxs-lookup"><span data-stu-id="01da4-107">`record 1`: *Container (record)*</span></span>

<span data-ttu-id="01da4-108">En referens till en datakälla av datatypen *Post*.</span><span class="sxs-lookup"><span data-stu-id="01da4-108">A reference to a data source of the *Record* data type.</span></span> <span data-ttu-id="01da4-109">Detta argument krävs.</span><span class="sxs-lookup"><span data-stu-id="01da4-109">This argument is required.</span></span>

<span data-ttu-id="01da4-110">`record N`: *Behållare (post)*</span><span class="sxs-lookup"><span data-stu-id="01da4-110">`record N`: *Container (record)*</span></span>

<span data-ttu-id="01da4-111">En referens till en datakälla av datatypen *Post*.</span><span class="sxs-lookup"><span data-stu-id="01da4-111">A reference to a data source of the *Record* data type.</span></span> <span data-ttu-id="01da4-112">Dessa ytterligare argument är valfria.</span><span class="sxs-lookup"><span data-stu-id="01da4-112">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="01da4-113">Returvärden</span><span class="sxs-lookup"><span data-stu-id="01da4-113">Return values</span></span>

<span data-ttu-id="01da4-114">*Post-lista*</span><span class="sxs-lookup"><span data-stu-id="01da4-114">*Record list*</span></span>

<span data-ttu-id="01da4-115">Den resulterande listan med poster.</span><span class="sxs-lookup"><span data-stu-id="01da4-115">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="01da4-116">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="01da4-116">Usage notes</span></span>

<span data-ttu-id="01da4-117">Strukturen för listan som skapas innehåller endast de fält som presenteras i strukturen för varje post som nämns i argumenten.</span><span class="sxs-lookup"><span data-stu-id="01da4-117">The structure of the list that is created contains only the fields that are presented in the structure of every record that is mentioned in the arguments.</span></span>

## <a name="example"></a><span data-ttu-id="01da4-118">Exempel</span><span class="sxs-lookup"><span data-stu-id="01da4-118">Example</span></span>

<span data-ttu-id="01da4-119">Du anger datakälla **post 1** av typen *behållare*.</span><span class="sxs-lookup"><span data-stu-id="01da4-119">You enter data source **Record 1** of the *Container* type.</span></span> <span data-ttu-id="01da4-120">Den här datakällan innehåller följande kapslade fält av typen *beräknat fält*:</span><span class="sxs-lookup"><span data-stu-id="01da4-120">This data source contains the following nested fields of the *Calculated field* type:</span></span>

- <span data-ttu-id="01da4-121">**Kod:** det här fältet innehåller ett uttryck som returnerar ett värde av typen *Sträng*.</span><span class="sxs-lookup"><span data-stu-id="01da4-121">**Code:** This field contains an expression that returns a value of the *String* type.</span></span>
- <span data-ttu-id="01da4-122">**Belopp:** det här fältet innehåller ett uttryck som returnerar ett värde av typen *Realtal*.</span><span class="sxs-lookup"><span data-stu-id="01da4-122">**Amount:** This field contains an expression that returns a value of the *Real* type.</span></span>

<span data-ttu-id="01da4-123">Du anger datakälla **post 2** av typen *behållare*.</span><span class="sxs-lookup"><span data-stu-id="01da4-123">You then enter data source **Record 2** of the *Container* type.</span></span> <span data-ttu-id="01da4-124">Den här datakällan innehåller följande kapslade fält av typen *beräknat fält*:</span><span class="sxs-lookup"><span data-stu-id="01da4-124">This data source contains the following nested fields of the *Calculated field* type:</span></span>

- <span data-ttu-id="01da4-125">**Belopp:** det här fältet innehåller ett uttryck som returnerar ett värde av typen *Realtal*.</span><span class="sxs-lookup"><span data-stu-id="01da4-125">**Amount:** This field contains an expression that returns a value of the *Real* type.</span></span>
- <span data-ttu-id="01da4-126">**IsValid:** det här fältet innehåller ett uttryck som returnerar ett värde av typen *Boolesk*.</span><span class="sxs-lookup"><span data-stu-id="01da4-126">**IsValid:** This field contains an expression that returns a value of the *Boolean* type.</span></span>

<span data-ttu-id="01da4-127">I det här fallet returnerar uttrycket `LIST('Record 1', 'Record 2')` en ny lista som innehåller två poster.</span><span class="sxs-lookup"><span data-stu-id="01da4-127">In this case, the expression `LIST('Record 1', 'Record 2')` returns a new list that contains two records.</span></span> <span data-ttu-id="01da4-128">Strukturen för den här listan består av ett enda fält **belopp** av typen *Realtal*, eftersom det här fältet är det enda fält som presenteras i alla argument i den anropade funktionen.</span><span class="sxs-lookup"><span data-stu-id="01da4-128">The structure of this list consists of a single **Amount** field of the *Real* type, because this field is the only field that is presented in every argument of the called function.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="01da4-129">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="01da4-129">Additional resources</span></span>

[<span data-ttu-id="01da4-130">Lista över funktioner</span><span class="sxs-lookup"><span data-stu-id="01da4-130">List functions</span></span>](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]