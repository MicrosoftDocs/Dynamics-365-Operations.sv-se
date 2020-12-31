---
title: LISTOFFIELDS ER-funktion
description: Det här avsnittet innehåller information om hur funktionen LISTOFFIELDS elektronisk rapportering (ER) används.
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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1d8d9f41d6ee5256f560c83486c95ecd47f5b081
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686522"
---
# <a name="listoffields-er-function"></a><span data-ttu-id="8d53d-103">LISTOFFIELDS ER-funktion</span><span class="sxs-lookup"><span data-stu-id="8d53d-103">LISTOFFIELDS ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8d53d-104">`LISTOFFIELDS`-funktionen returnerar ett *postlista*-värde som skapas baserat på strukturen för det angivna argumentet i typen *uppräkning* eller *behållare (post)*.</span><span class="sxs-lookup"><span data-stu-id="8d53d-104">The `LISTOFFIELDS` function returns a *Record list* value that is created based on the structure of the specified argument of the *Enumeration* or *Container (record)* type.</span></span>

## <a name="syntax-1"></a><span data-ttu-id="8d53d-105">Syntax 1</span><span class="sxs-lookup"><span data-stu-id="8d53d-105">Syntax 1</span></span>

```vb
LISTOFFIELDS (path)
```

## <a name="syntax-2"></a><span data-ttu-id="8d53d-106">Syntax 2</span><span class="sxs-lookup"><span data-stu-id="8d53d-106">Syntax 2</span></span>

```vb
LISTOFFIELDS (path, language)
```

## <a name="arguments"></a><span data-ttu-id="8d53d-107">Argument</span><span class="sxs-lookup"><span data-stu-id="8d53d-107">Arguments</span></span>

<span data-ttu-id="8d53d-108">`path`: datakällareferens</span><span class="sxs-lookup"><span data-stu-id="8d53d-108">`path`: Data source reference</span></span>

<span data-ttu-id="8d53d-109">Den giltiga referenssökvägen till en datakälla för någon av följande datatyper:</span><span class="sxs-lookup"><span data-stu-id="8d53d-109">The valid reference path of a data source of one of the following data types:</span></span>

- <span data-ttu-id="8d53d-110">Uppräkning för modell</span><span class="sxs-lookup"><span data-stu-id="8d53d-110">Model enumeration</span></span>
- <span data-ttu-id="8d53d-111">Formatuppräkning</span><span class="sxs-lookup"><span data-stu-id="8d53d-111">Format enumeration</span></span>
- <span data-ttu-id="8d53d-112">Uppräkning för program</span><span class="sxs-lookup"><span data-stu-id="8d53d-112">Application enumeration</span></span>
- <span data-ttu-id="8d53d-113">Behållare (post)</span><span class="sxs-lookup"><span data-stu-id="8d53d-113">Container (record)</span></span>

<span data-ttu-id="8d53d-114">`language`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="8d53d-114">`language`: *String*</span></span>

<span data-ttu-id="8d53d-115">Text som representerar en språkkod.</span><span class="sxs-lookup"><span data-stu-id="8d53d-115">Text that represents a language code.</span></span>

## <a name="return-values"></a><span data-ttu-id="8d53d-116">Returvärden</span><span class="sxs-lookup"><span data-stu-id="8d53d-116">Return values</span></span>

<span data-ttu-id="8d53d-117">*Post-lista*</span><span class="sxs-lookup"><span data-stu-id="8d53d-117">*Record list*</span></span>

<span data-ttu-id="8d53d-118">Den resulterande listan med poster.</span><span class="sxs-lookup"><span data-stu-id="8d53d-118">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="8d53d-119">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="8d53d-119">Usage notes</span></span>

<span data-ttu-id="8d53d-120">Listan som skapas består av poster som innehåller följande fält:</span><span class="sxs-lookup"><span data-stu-id="8d53d-120">The list that is created consists of records that have the following fields:</span></span>

- <span data-ttu-id="8d53d-121">**Namn** (*Sträng* datatyp)</span><span class="sxs-lookup"><span data-stu-id="8d53d-121">**Name** (*String* data type)</span></span>
- <span data-ttu-id="8d53d-122">**Etikett** (*Sträng* datatyp)</span><span class="sxs-lookup"><span data-stu-id="8d53d-122">**Label** (*String* data type)</span></span>
- <span data-ttu-id="8d53d-123">**Beskrivning** (*Sträng* datatyp)</span><span class="sxs-lookup"><span data-stu-id="8d53d-123">**Description** (*String* data type)</span></span>
- <span data-ttu-id="8d53d-124">**Istranslated** (*boolesk* datatyp)</span><span class="sxs-lookup"><span data-stu-id="8d53d-124">**IsTranslated** (*Boolean* data type)</span></span>

<span data-ttu-id="8d53d-125">Om `path`-argumentet refererar till en datakälla för typen *behållare (post)*, läggs en ny post till i listan som skapas för varje fält i den refererade behållarposten.</span><span class="sxs-lookup"><span data-stu-id="8d53d-125">If the `path` argument refers to a data source of the *Container (Record)* type, for every field of the referenced container record, a new record is added to the list that is created.</span></span> <span data-ttu-id="8d53d-126">För varje post som skapas returnerar fältet **namn** namnet på fältet för den refererade behållarposten som den aktuella posten skapades för.</span><span class="sxs-lookup"><span data-stu-id="8d53d-126">For every record that is created, the **Name** field returns the name of the field of the referenced container record that the current record was created for.</span></span>

<span data-ttu-id="8d53d-127">Om `path`-argumentet refererar till en datakälla för en av typerna *Uppräkning*, för varje uppräkningsvärde för den refererade uppräkningen läggs en ny post till i listan som skapades.</span><span class="sxs-lookup"><span data-stu-id="8d53d-127">If the `path` argument refers to a data source of one of the *Enumeration* types, for every enumeration value of the referenced enumeration, a new record is added to the list that is created.</span></span> <span data-ttu-id="8d53d-128">För varje post som skapades returnerar fältet **Namn** fältet returnerar värdet på den refererade uppräkningen som den aktuella posten skapades för, fältet **beskrivning** returnerar beskrivningen av uppräkningen och fältet **etikett** returnerar etiketten för den uppräkningen.</span><span class="sxs-lookup"><span data-stu-id="8d53d-128">For every record that is created, the **Name** field returns the value of the referenced enumeration that the current record was created for, the **Description** field returns the description of that enumeration, and the **Label** field returns the label of that enumeration.</span></span>

<span data-ttu-id="8d53d-129">Vid körning, när syntax 1 används, måste fälten **etikett** och **beskrivning** returnera värden som baseras på språkinställningarna för det format för elektronisk rapportering (ER) som körs:</span><span class="sxs-lookup"><span data-stu-id="8d53d-129">At runtime, when syntax 1 is used, the **Label** and **Description** fields must return values that are based on the language settings of the Electronic reporting (ER) format that is running:</span></span>

- <span data-ttu-id="8d53d-130">Om etiketterna och beskrivningarna för det begärda språket är tillgängliga returnerar fälten **etikett** och **beskrivning** värden som baseras på det språket, och fältet **IsTranslated** returneras **sant**.</span><span class="sxs-lookup"><span data-stu-id="8d53d-130">If the labels and descriptions for the requested language are available, the **Label** and **Description** fields return values that are based on that language, and the **IsTranslated** field returns **True**.</span></span>
- <span data-ttu-id="8d53d-131">Om etiketterna och beskrivningarna för det begärda språket inte är tillgängliga returnerar fälten **etikett** och **beskrivning** värden som baseras på standardspråket **EN-US** och fältet **IsTranslated** returneras **falskt**.</span><span class="sxs-lookup"><span data-stu-id="8d53d-131">If the labels and descriptions for the requested language aren't available, the **Label** and **Description** fields return values that are based on the default **EN-US** language, and the **IsTranslated** field returns **False**.</span></span>

<span data-ttu-id="8d53d-132">Vid körning, när syntax 2 används, måste fälten **etikett** och **beskrivning** returnera värden som baseras på språket som definieras som det andra argumentet av de anropade funktionerna:</span><span class="sxs-lookup"><span data-stu-id="8d53d-132">At runtime, when syntax 2 is used, the **Label** and **Description** fields must return values that are based on the language that is defined as the second argument of the called function:</span></span>

- <span data-ttu-id="8d53d-133">Om etiketterna och beskrivningarna för det begärda språket är tillgängliga returnerar fälten **etikett** och **beskrivning** värden som baseras på det språket, och fältet **IsTranslated** returneras **sant**.</span><span class="sxs-lookup"><span data-stu-id="8d53d-133">If the labels and descriptions for the requested language are available, the **Label** and **Description** fields return values that are based on that language, and the **IsTranslated** field returns **True**.</span></span>
- <span data-ttu-id="8d53d-134">Om etiketterna och beskrivningarna för det begärda språket inte är tillgängliga returnerar fälten **etikett** och **beskrivning** värden som baseras på språket **EN-US** och fältet **IsTranslated** returneras **falskt**.</span><span class="sxs-lookup"><span data-stu-id="8d53d-134">If the labels and descriptions for the requested language aren't available, the **Label** and **Description** fields return values that are based on the **EN-US** language, and the **IsTranslated** field returns **False**.</span></span>

## <a name="example-1"></a><span data-ttu-id="8d53d-135">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="8d53d-135">Example 1</span></span>

<span data-ttu-id="8d53d-136">I följande illustration introduceras en uppräkning i en ER-datamodell.</span><span class="sxs-lookup"><span data-stu-id="8d53d-136">In the following illustration, an enumeration is introduced in an ER data model.</span></span>

<a href="./media/ger-listoffields-function-model-enumeration.png"><img src="./media/ger-listoffields-function-model-enumeration-e1474545790761.png" alt="Enumeration in a model" class="alignnone wp-image-1203943 size-full" width="514" height="155" /></a>

<span data-ttu-id="8d53d-137">Illustrationen som följer visar dessa detaljer:</span><span class="sxs-lookup"><span data-stu-id="8d53d-137">The following illustration shows these details:</span></span>

- <span data-ttu-id="8d53d-138">Modelluppräkningen har infogats i en rapport som en datakälla.</span><span class="sxs-lookup"><span data-stu-id="8d53d-138">The model enumeration is inserted into a report as a data source.</span></span>
- <span data-ttu-id="8d53d-139">ER-uttryck använder uppräkningsmodellen som en parameter för funktionen `LISTOFFIELDS`.</span><span class="sxs-lookup"><span data-stu-id="8d53d-139">An ER expression uses the model enumeration as a parameter of the `LISTOFFIELDS` function.</span></span>
- <span data-ttu-id="8d53d-140">En datakälla av typen *postlista* infogas i en rapport med hjälp av det ER-uttryck som skapats.</span><span class="sxs-lookup"><span data-stu-id="8d53d-140">A data source of the *Record list* type is inserted into a report by using the ER expression that is created.</span></span>

<a href="./media/ger-listoffields-function-in-format-expression.png"><img src="./media/ger-listoffields-function-in-format-expression-e1474546110395.png" alt="Format" class="alignnone wp-image-1204033 size-full" width="549" height="318" /></a>

<span data-ttu-id="8d53d-141">Följande exempel visar de ER-formatelement som är kopplade till en datakälla av typen *postlista* som skapats med funktionen `LISTOFFIELDS`.</span><span class="sxs-lookup"><span data-stu-id="8d53d-141">The following example shows the ER format elements that are bound to the data source of the *Record list* type that was created by using the `LISTOFFIELDS` function.</span></span>

<a href="./media/ger-listoffields-function-format-design.png"><img src="./media/ger-listoffields-function-format-design.png" alt="Format design" class="alignnone size-full wp-image-1204043" width="466" height="221" /></a>

<span data-ttu-id="8d53d-142">Följande illustration visar resultatet när det designade formatet har körts.</span><span class="sxs-lookup"><span data-stu-id="8d53d-142">The following illustration shows the result when the designed format is run.</span></span>

<a href="./media/ger-listoffields-function-format-output.png"><img src="./media/ger-listoffields-function-format-output.png" alt="Format output" class="alignnone size-full wp-image-1204053" width="585" height="158" /></a>

> [!NOTE] 
> <span data-ttu-id="8d53d-143">Baserat på språkinställningarna i de överordnade **FILE**- och **FOLDER**-elementen infogas översatt text för etiketter och beskrivningar i utdata till ER-formatet.</span><span class="sxs-lookup"><span data-stu-id="8d53d-143">Based on the language settings of the parent **FILE** and **FOLDER** format elements, translated text for labels and descriptions is entered in the output of the ER format.</span></span>

## <a name="example-2"></a><span data-ttu-id="8d53d-144">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="8d53d-144">Example 2</span></span>

<span data-ttu-id="8d53d-145">Till exempel kan du använda datakälltypen *Beräknat fält* för att konfigurera datakällor för **enumType\_de** och **enumType\_deCH** för uppräkning av datamodell **enumType**:</span><span class="sxs-lookup"><span data-stu-id="8d53d-145">You use the *Calculated field* data source type to configure **enumType\_de** and **enumType\_deCH** data sources for the **enumType** data model enumeration:</span></span>

- <span data-ttu-id="8d53d-146">**enumType\_de** = `LISTOFFIELDS (enumType, "de")`</span><span class="sxs-lookup"><span data-stu-id="8d53d-146">**enumType\_de** = `LISTOFFIELDS (enumType, "de")`</span></span>
- <span data-ttu-id="8d53d-147">**enumType\_deCH** = `LISTOFFIELDS (enumType, "de-CH")`</span><span class="sxs-lookup"><span data-stu-id="8d53d-147">**enumType\_deCH** = `LISTOFFIELDS (enumType, "de-CH")`</span></span>

<span data-ttu-id="8d53d-148">I det här fallet kan du använda följande uttryck för att få etiketten på uppräkningsvärdet på tyska (Schweiz), om denna översättning är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="8d53d-148">In this case, you can use the following expression to get the label of the enumeration value in Swiss German, if that translation is available.</span></span> <span data-ttu-id="8d53d-149">Om schweizisk tysk översättning inte är tillgänglig är etiketten på tyska.</span><span class="sxs-lookup"><span data-stu-id="8d53d-149">If the Swiss German translation isn't available, the label is in German.</span></span>

```vb
IF (NOT (enumType_deCH.IsTranslated), enumType_de.Label, enumType_deCH.Label)
```

## <a name="additional-resources"></a><span data-ttu-id="8d53d-150">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="8d53d-150">Additional resources</span></span>

[<span data-ttu-id="8d53d-151">Lista över funktioner</span><span class="sxs-lookup"><span data-stu-id="8d53d-151">List functions</span></span>](er-functions-category-list.md)
