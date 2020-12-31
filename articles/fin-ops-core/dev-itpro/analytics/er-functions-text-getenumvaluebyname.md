---
title: Funktionen GETENUMVALUEBYNAME ER
description: Det här avsnittet innehåller information om hur funktionen GETENUMVALUEBYNAME elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 09/23/2020
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
ms.openlocfilehash: 29d7ec6498090ea47259303237c5a64a26e4926b
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4685942"
---
# <a name="getenumvaluebyname-er-function"></a><span data-ttu-id="1bc6d-103">Funktionen GETENUMVALUEBYNAME ER</span><span class="sxs-lookup"><span data-stu-id="1bc6d-103">GETENUMVALUEBYNAME ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1bc6d-104">`GETENUMVALUEBYNAME`-funktionen söker efter ett specifikt värde för *uppräkning* i angiven uppräkningsdatakälla med hjälp av det uppräkningsnamn som anges som ett *sträng*-värde.</span><span class="sxs-lookup"><span data-stu-id="1bc6d-104">The `GETENUMVALUEBYNAME` function searches for a specific *Enum* value in the specified enumeration data source by using the enumeration name that is specified as a *String* value.</span></span> <span data-ttu-id="1bc6d-105">Om *Enum*-värdet hittas returnerar funktionen den.</span><span class="sxs-lookup"><span data-stu-id="1bc6d-105">If the *Enum* value is found, the function returns it.</span></span> <span data-ttu-id="1bc6d-106">Annars returnerar funktionen **null**-uppräkningsvärdet.</span><span class="sxs-lookup"><span data-stu-id="1bc6d-106">Otherwise, the function returns the **null** enumeration value.</span></span>

## <a name="syntax"></a><span data-ttu-id="1bc6d-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="1bc6d-107">Syntax</span></span>

```vb
GETENUMVALUEBYNAME (enumeration data source path, enumeration value text)
```

## <a name="arguments"></a><span data-ttu-id="1bc6d-108">Argument</span><span class="sxs-lookup"><span data-stu-id="1bc6d-108">Arguments</span></span>

<span data-ttu-id="1bc6d-109">`enumeration data source path`: *Uppräkning*</span><span class="sxs-lookup"><span data-stu-id="1bc6d-109">`enumeration data source path`: *Enumeration*</span></span>

<span data-ttu-id="1bc6d-110">Den giltiga sökvägen till en datakälla för någon av följande uppräkningstyper:</span><span class="sxs-lookup"><span data-stu-id="1bc6d-110">The valid path of a data source of one of the following enumeration types:</span></span>

- <span data-ttu-id="1bc6d-111">Elektronisk rapportering (ER) modelluppräkning</span><span class="sxs-lookup"><span data-stu-id="1bc6d-111">Electronic reporting (ER) model enumeration</span></span>
- <span data-ttu-id="1bc6d-112">ER-formatuppräkning</span><span class="sxs-lookup"><span data-stu-id="1bc6d-112">ER format enumeration</span></span>
- <span data-ttu-id="1bc6d-113">Microsoft Dynamics 365 Finance uppräkning</span><span class="sxs-lookup"><span data-stu-id="1bc6d-113">Microsoft Dynamics 365 Finance enumeration</span></span>

<span data-ttu-id="1bc6d-114">`enumeration value text`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="1bc6d-114">`enumeration value text`: *String*</span></span>

<span data-ttu-id="1bc6d-115">Ett strängvärde som representerar namnet på ett enda uppräkningsvärde.</span><span class="sxs-lookup"><span data-stu-id="1bc6d-115">A string value that represents the name of a single enumeration value.</span></span>

## <a name="return-values"></a><span data-ttu-id="1bc6d-116">Returvärden</span><span class="sxs-lookup"><span data-stu-id="1bc6d-116">Return values</span></span>

<span data-ttu-id="1bc6d-117">Kan ha värdet null *Enum*</span><span class="sxs-lookup"><span data-stu-id="1bc6d-117">Nullable *Enum*</span></span>

<span data-ttu-id="1bc6d-118">Det resulterande fasttextvärde.</span><span class="sxs-lookup"><span data-stu-id="1bc6d-118">The resulting enumeration value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="1bc6d-119">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="1bc6d-119">Usage notes</span></span>

<span data-ttu-id="1bc6d-120">Inget undantag genereras om *fasttextvärde* inte hittas med hjälp av namnet på uppräkningsvärdet som anges som ett *sträng*-värde.</span><span class="sxs-lookup"><span data-stu-id="1bc6d-120">No exception is thrown if an *Enum* value isn't found by using the name of the enumeration value that is specified as a *String* value.</span></span>

## <a name="example-1"></a><span data-ttu-id="1bc6d-121">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="1bc6d-121">Example 1</span></span>

<span data-ttu-id="1bc6d-122">I följande illustration introduceras uppräkningen **ReportDirection** i en datamodell.</span><span class="sxs-lookup"><span data-stu-id="1bc6d-122">In the following illustration, the **ReportDirection** enumeration is introduced in a data model.</span></span> <span data-ttu-id="1bc6d-123">Observera att etiketter definieras för uppräkningsvärden.</span><span class="sxs-lookup"><span data-stu-id="1bc6d-123">Notice that labels are defined for the enumeration values.</span></span>

![Tillgängliga värden för en uppräkningen för datamodell](./media/ER-data-model-enumeration-values.PNG)

<span data-ttu-id="1bc6d-125">Illustrationen som följer visar dessa detaljer:</span><span class="sxs-lookup"><span data-stu-id="1bc6d-125">The following illustration shows these details:</span></span>

- <span data-ttu-id="1bc6d-126">**$Direction** datakällan har konfigurerats i en ER-rapport.</span><span class="sxs-lookup"><span data-stu-id="1bc6d-126">The **$Direction** data source is configured in an ER report.</span></span> <span data-ttu-id="1bc6d-127">Den här datakällan konfigureras baserat på den **ReportDirection** modelluppräkning.</span><span class="sxs-lookup"><span data-stu-id="1bc6d-127">This data source is configured based on the **ReportDirection** model enumeration.</span></span>
- <span data-ttu-id="1bc6d-128">`$IsArrivals`-uttrycket är utformat för att använda modelluppräkningsbaserad **$Direction** datakälla som en parameter för denna funktion.</span><span class="sxs-lookup"><span data-stu-id="1bc6d-128">The `$IsArrivals` expression is designed to use the model enumeration–based **$Direction** data source as a parameter of this function.</span></span>
- <span data-ttu-id="1bc6d-129">Värdet för detta jämförelseuttryck är **SANT**.</span><span class="sxs-lookup"><span data-stu-id="1bc6d-129">The value of this comparison expression is **TRUE**.</span></span>

![Exempel på uppräkning av en datamodell](./media/ER-data-model-enumeration-usage.PNG)

## <a name="example-2"></a><span data-ttu-id="1bc6d-131">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="1bc6d-131">Example 2</span></span>

<span data-ttu-id="1bc6d-132">Med funktionerna `GETENUMVALUEBYNAME` och [`LISTOFFIELDS`](er-functions-list-listoffields.md) kan du hämta värden och etiketter för uppräkningar som stöds som textvärden.</span><span class="sxs-lookup"><span data-stu-id="1bc6d-132">The `GETENUMVALUEBYNAME` and [`LISTOFFIELDS`](er-functions-list-listoffields.md) functions let you fetch values and labels of supported enumerations as text values.</span></span> <span data-ttu-id="1bc6d-133">(De uppräkningar som stöds är programuppräkningar, uppräkningar av datamodeller och formatuppräkningar.)</span><span class="sxs-lookup"><span data-stu-id="1bc6d-133">(The supported enumerations are application enumerations, data model enumerations, and format enumerations.)</span></span>

<span data-ttu-id="1bc6d-134">I följande illustration introduceras datakällan **TransType** i en modellmappning.</span><span class="sxs-lookup"><span data-stu-id="1bc6d-134">In the following illustration, the **TransType** data source is introduced in a model mapping.</span></span> <span data-ttu-id="1bc6d-135">Den här datakällan refererar till uppräkningen **LedgerTransType** för program.</span><span class="sxs-lookup"><span data-stu-id="1bc6d-135">This data source refers to the **LedgerTransType** application enumeration.</span></span>

![Datakälla för en modellmappning som refererar till ett programuppräkning](./media/er-functions-text-getenumvaluebyname-example2-1.png)

<span data-ttu-id="1bc6d-137">Följande bild visar datakällan **TransTypeList** som konfigureras i en modellmappning.</span><span class="sxs-lookup"><span data-stu-id="1bc6d-137">The following illustration shows the **TransTypeList** data source that is configured in a model mapping.</span></span> <span data-ttu-id="1bc6d-138">Den här datakällan konfigureras baserat på den **TransType** programuppräkning.</span><span class="sxs-lookup"><span data-stu-id="1bc6d-138">This data source is configured based on the **TransType** application enumeration.</span></span> <span data-ttu-id="1bc6d-139">Funktionen `LISTOFFIELDS` används för att returnera alla uppräkningsvärden som en lista med poster som innehåller fält.</span><span class="sxs-lookup"><span data-stu-id="1bc6d-139">The `LISTOFFIELDS` function is used to return all enumeration values as a list of records that contain fields.</span></span> <span data-ttu-id="1bc6d-140">På så sätt visas information om varje uppräkningsvärde.</span><span class="sxs-lookup"><span data-stu-id="1bc6d-140">In this way, the details of every enumeration value are exposed.</span></span>

> [!NOTE]
> <span data-ttu-id="1bc6d-141">Fälteet **EnumValue** konfigureras för datakällan **TransTypeList** med hjälp av `GETENUMVALUEBYNAME(TransType, TransTypeList.Name)`-uttrycket.</span><span class="sxs-lookup"><span data-stu-id="1bc6d-141">The **EnumValue** field is configured for the **TransTypeList** data source by using the `GETENUMVALUEBYNAME(TransType, TransTypeList.Name)` expression.</span></span> <span data-ttu-id="1bc6d-142">Det här fältet returnerar ett uppräkningsvärde för varje post i den här listan.</span><span class="sxs-lookup"><span data-stu-id="1bc6d-142">This field returns an enumeration value for every record in this list.</span></span>

![Datakälla för en modellmappning som returnerar alla uppräkningsvärden för en markerad uppräkning som en lista med poster](./media/er-functions-text-getenumvaluebyname-example2-2.png)

<span data-ttu-id="1bc6d-144">Följande bild visar datakällan **VendTrans** som konfigureras i en modellmappning.</span><span class="sxs-lookup"><span data-stu-id="1bc6d-144">The following illustration shows the **VendTrans** data source that is configured in a model mapping.</span></span> <span data-ttu-id="1bc6d-145">Den här datakällan returnerar transaktionsposter för leverantörer från programregistret **VendTrans**.</span><span class="sxs-lookup"><span data-stu-id="1bc6d-145">This data source returns vendor transaction records from the **VendTrans** application table.</span></span> <span data-ttu-id="1bc6d-146">Redovisningstypen för varje transaktion definieras av värdet i fältet **TransType**.</span><span class="sxs-lookup"><span data-stu-id="1bc6d-146">The ledger type of every transaction is defined by the value of the **TransType** field.</span></span>

> [!NOTE]
> <span data-ttu-id="1bc6d-147">Fälteet **TransTypeTitle** konfigureras för datakällan **VendTrans** med hjälp av `FIRSTORNULL(WHERE(TransTypeList, TransTypeList.EnumValue = @.TransType)).Label`-uttrycket.</span><span class="sxs-lookup"><span data-stu-id="1bc6d-147">The **TransTypeTitle** field is configured for the **VendTrans** data source by using the `FIRSTORNULL(WHERE(TransTypeList, TransTypeList.EnumValue = @.TransType)).Label` expression.</span></span> <span data-ttu-id="1bc6d-148">Det här fältet returnerar etiketten för ett uppräkningsvärde för den aktuella transaktionen som text, om detta uppräkningsvärde är tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="1bc6d-148">This field returns the label of an enumeration value of the current transaction as text, if this enumeration value is available.</span></span> <span data-ttu-id="1bc6d-149">Annars returneras ett tomt strängvärde.</span><span class="sxs-lookup"><span data-stu-id="1bc6d-149">Otherwise, it returns a blank string value.</span></span>
>
> <span data-ttu-id="1bc6d-150">Fältet **TransTypeTitle** är bundet till **LedgerType** för en datamodell som gör att informationen kan användas i alla ER-format där datamodellen används som datakälla.</span><span class="sxs-lookup"><span data-stu-id="1bc6d-150">The **TransTypeTitle** field is bound to the **LedgerType** field of a data model that enables this information to be used in every ER format that uses the data model as a source of data.</span></span>

![Datakälla för en modellmappning som returnerar leverantörstransaktioner](./media/er-functions-text-getenumvaluebyname-example2-3.png)

<span data-ttu-id="1bc6d-152">Följande bild visar hur du kan använda [datakällans felsökare](er-debug-data-sources.md) för att testa den konfigurerade modellmappningen.</span><span class="sxs-lookup"><span data-stu-id="1bc6d-152">The following illustration shows how you can use the [data source debugger](er-debug-data-sources.md) to test the configured model mapping.</span></span>

![Använda datakällans felsökare för att testa den konfigurerade modellmappningen](./media/er-functions-text-getenumvaluebyname-example2-4.gif)

<span data-ttu-id="1bc6d-154">Fältet **LedgerType** i en datamodell visar etiketter för de transaktionstyper som förväntas.</span><span class="sxs-lookup"><span data-stu-id="1bc6d-154">The **LedgerType** field of a data model exposes labels of transaction types as expected.</span></span>

<span data-ttu-id="1bc6d-155">Om du planerar att använda den här metoden för en stor mängd transaktionsdata måste du överväga att köra prestanda.</span><span class="sxs-lookup"><span data-stu-id="1bc6d-155">If you plan to use this approach for a large amount of transactional data, you must consider execution performance.</span></span> <span data-ttu-id="1bc6d-156">För mer information, se [Spåra körningen av ER-format för att felsöka prestandaproblem](trace-execution-er-troubleshoot-perf.md).</span><span class="sxs-lookup"><span data-stu-id="1bc6d-156">For more information, see [Trace the execution of ER formats to troubleshoot performance issues](trace-execution-er-troubleshoot-perf.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1bc6d-157">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="1bc6d-157">Additional resources</span></span>

[<span data-ttu-id="1bc6d-158">Textfunktioner</span><span class="sxs-lookup"><span data-stu-id="1bc6d-158">Text functions</span></span>](er-functions-category-text.md)

[<span data-ttu-id="1bc6d-159">Spåra körningen av ER-format för att felsöka prestandaproblem</span><span class="sxs-lookup"><span data-stu-id="1bc6d-159">Trace the execution of ER formats to troubleshoot performance issues</span></span>](trace-execution-er-troubleshoot-perf.md)

[<span data-ttu-id="1bc6d-160">LISTOFFIELDS ER-funktion</span><span class="sxs-lookup"><span data-stu-id="1bc6d-160">LISTOFFIELDS ER function</span></span>](er-functions-list-listoffields.md)

[<span data-ttu-id="1bc6d-161">FIRSTORNULL ER-funktion</span><span class="sxs-lookup"><span data-stu-id="1bc6d-161">FIRSTORNULL ER function</span></span>](er-functions-list-firstornull.md)

[<span data-ttu-id="1bc6d-162">WHERE ER-funktionen</span><span class="sxs-lookup"><span data-stu-id="1bc6d-162">WHERE ER function</span></span>](er-functions-list-where.md)
