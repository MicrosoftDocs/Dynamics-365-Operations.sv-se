---
title: NUMSEQVALUE ER-funktion
description: Det här avsnittet innehåller information om hur funktionen NUMSEQVALUE elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: 23dc112651e4425b8020ee5c843509b4df83e810
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5563328"
---
# <a name="numseqvalue-er-function"></a><span data-ttu-id="9e7d9-103">NUMSEQVALUE ER-funktion</span><span class="sxs-lookup"><span data-stu-id="9e7d9-103">NUMSEQVALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9e7d9-104">`NUMSEQVALUE`-funktionen returnerar ett *Sträng*-värde som representerar det nya genererade värdet för en nummerserie, baserat på den angivna nummersekvensen, omfattningen och omfattnings-ID.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-104">The `NUMSEQVALUE` function returns a *String* value that represents the new generated value of a number sequence, based on the specified number sequence, scope, and scope ID.</span></span> <span data-ttu-id="9e7d9-105">Omfattnings-ID är lika med företagskoden som tillhandahålls av kontexten som ER-formatet (elektronisk rapportering) körs under.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-105">The scope ID equals the company code that is supplied by the context that the Electronic reporting (ER) format is run under.</span></span>

## <a name="syntax-1"></a><span data-ttu-id="9e7d9-106">Syntax 1</span><span class="sxs-lookup"><span data-stu-id="9e7d9-106">Syntax 1</span></span>

```vb
NUMSEQVALUE (number sequence code)
```

## <a name="syntax-2"></a><span data-ttu-id="9e7d9-107">Syntax 2</span><span class="sxs-lookup"><span data-stu-id="9e7d9-107">Syntax 2</span></span>

```vb
NUMSEQVALUE (number sequence record ID)
```

## <a name="syntax-3"></a><span data-ttu-id="9e7d9-108">Syntax 3</span><span class="sxs-lookup"><span data-stu-id="9e7d9-108">Syntax 3</span></span>

```vb
NUMSEQVALUE (number sequence code, scope type, scope ID)
```

## <a name="arguments"></a><span data-ttu-id="9e7d9-109">Argument</span><span class="sxs-lookup"><span data-stu-id="9e7d9-109">Arguments</span></span>

<span data-ttu-id="9e7d9-110">`number sequence code`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="9e7d9-110">`number sequence code`: *String*</span></span>

<span data-ttu-id="9e7d9-111">Ett textvärde som representerar koden för den nummerserie som ett nytt värde krävs i.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-111">A text value that represents the code of the number sequence that a new value is required in.</span></span>

<span data-ttu-id="9e7d9-112">`number sequence record ID`: *Int64*</span><span class="sxs-lookup"><span data-stu-id="9e7d9-112">`number sequence record ID`: *Int64*</span></span>

<span data-ttu-id="9e7d9-113">Ett *Int64*-värde som representerar post-ID för en post i tabellen NumberSequenceTable som innehåller definitionen av den nummerserie som ett nytt värde krävs i.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-113">An *Int64* value that represents the record ID of a record in the NumberSequenceTable table that contains the definition of the number sequence that a new value is required in.</span></span>

<span data-ttu-id="9e7d9-114">`scope type`: *Uppräknat värde*</span><span class="sxs-lookup"><span data-stu-id="9e7d9-114">`scope type`: *Enum value*</span></span>

<span data-ttu-id="9e7d9-115">Ett numreringsvärde för uppräkningen **ERExpressionNumberSequenceScopeType** som definierar omfattningen för den nummerserie som ett nytt värde krävs i.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-115">An enumeration value of the **ERExpressionNumberSequenceScopeType** enumeration that defines the scope of the number sequence that a new value is required in.</span></span> <span data-ttu-id="9e7d9-116">Tillgängliga omfattningstyper är **delade**, **juridisk person** och **företag**.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-116">The available scope types are **Shared**, **Legal entity**, and **Company**.</span></span>

<span data-ttu-id="9e7d9-117">`scope ID`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="9e7d9-117">`scope ID`: *String*</span></span>

<span data-ttu-id="9e7d9-118">Ett *sträng* värde som identifierar scopet baserat på den angivna omfattningstypen.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-118">A *String* value that identifies the scope, based on the specified scope type.</span></span>

## <a name="return-values"></a><span data-ttu-id="9e7d9-119">Returvärden</span><span class="sxs-lookup"><span data-stu-id="9e7d9-119">Return values</span></span>

<span data-ttu-id="9e7d9-120">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="9e7d9-120">*String*</span></span>

<span data-ttu-id="9e7d9-121">Det resulterande textvärdet.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-121">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="9e7d9-122">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="9e7d9-122">Usage notes</span></span>

<span data-ttu-id="9e7d9-123">För omfattningstypen **delad**, ange en tom sträng som områdes-ID.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-123">For the **Shared** scope type, specify an empty string as the scope ID.</span></span>

<span data-ttu-id="9e7d9-124">För omfattningstypen **företag** och **juridisk person**, ange företagskoden som områdes-ID.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-124">For the **Company** and **Legal entity** scope types, specify the company code as the scope ID.</span></span> <span data-ttu-id="9e7d9-125">Om du anger en tom sträng som områdes-ID för dessa omfattningstyper, används aktuella företagskoden.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-125">If you specify an empty string as the scope ID for these scope types, the current company code is used.</span></span>

<span data-ttu-id="9e7d9-126">När syntax 1 används begärs nummerserien för omfattningstypen **företag** och företagskoden tillhandahålls av kontexten som ER-formatet körs under.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-126">When syntax 1 is used, the number sequence is requested for the **Company** scope type, and the company code is supplied by the context that the ER format is run under.</span></span>

## <a name="example-1"></a><span data-ttu-id="9e7d9-127">Exempel 1</span><span class="sxs-lookup"><span data-stu-id="9e7d9-127">Example 1</span></span>

<span data-ttu-id="9e7d9-128">I ER-format definierar du **AskNumSeq**-datakällan för parametertypen *Användarindataparametrar*.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-128">In your ER format, you define the **AskNumSeq** data source of the *User input parameter* type.</span></span> <span data-ttu-id="9e7d9-129">Den här datakällan refererar till den utökade datatypen **Beskrivning** (EDT).</span><span class="sxs-lookup"><span data-stu-id="9e7d9-129">This data source refers to the **Description** extended data type (EDT).</span></span> <span data-ttu-id="9e7d9-130">Därefter definierar **NumSeq**-datakällan för typen *beräknade fält*.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-130">Next, you define the **NumSeq** data source of the *Calculated field* type.</span></span> <span data-ttu-id="9e7d9-131">Datakällan innehåller uttrycket `NUMSEQVALUE (AskNumSeq)`.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-131">This data source contains the expression `NUMSEQVALUE (AskNumSeq)`.</span></span> <span data-ttu-id="9e7d9-132">När **NumSeq**-datakällan anropas returneras det nya genererade värdet för den nummersekvens som angavs vid körningen genom att ange dess kod i dialogrutan.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-132">When the **NumSeq** data source is called, it returns the new generated value of the number sequence that was specified at runtime by entering its code in the dialog box.</span></span> <span data-ttu-id="9e7d9-133">Nummerserien begärs för omfattningstypen **företag**.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-133">The number sequence is requested for the **Company** scope type.</span></span> <span data-ttu-id="9e7d9-134">Företagskoden tillhandahålls av kontexten som ER-formatet körs under.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-134">The company code is supplied by the context that the ER format is run under.</span></span>

## <a name="example-2"></a><span data-ttu-id="9e7d9-135">Exempel 2</span><span class="sxs-lookup"><span data-stu-id="9e7d9-135">Example 2</span></span>

<span data-ttu-id="9e7d9-136">Du definierar följande datakällor i din modellmappning:</span><span class="sxs-lookup"><span data-stu-id="9e7d9-136">The following data sources are defined in your model mapping:</span></span>

- <span data-ttu-id="9e7d9-137">Datakällan **LedgerParms** för typen *tabell*.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-137">The **LedgerParms** data source of the *Table* type.</span></span> <span data-ttu-id="9e7d9-138">Den här datakällan refererar till tabellen LedgerParameters.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-138">This data source refers to the LedgerParameters table.</span></span>
- <span data-ttu-id="9e7d9-139">**NumSeq**-datakällan för typen *beräknade fält*.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-139">The **NumSeq** data source of the *Calculated field* type.</span></span> <span data-ttu-id="9e7d9-140">Datakällan innehåller uttrycket `NUMSEQVALUE ( LedgerParameters.'numRefJournalNum()'.NumberSequenceId)`.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-140">This data source contains the expression `NUMSEQVALUE ( LedgerParameters.'numRefJournalNum()'.NumberSequenceId)`.</span></span>

<span data-ttu-id="9e7d9-141">När datakällan **NumSeq** kallas, returneras det nya genererade värdet för nummerserien som har konfigurerats i Redovisningsparametrar för det företag som tillhandahåller den kontext som ER-formatet körs under.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-141">When the **NumSeq** data source is called, it returns the new generated value of the number sequence that has been configured in the General ledger parameters for the company that supplies the context that the ER format is run under.</span></span> <span data-ttu-id="9e7d9-142">Den här nummerserien identifierar unikt journaler och fungerar som ett batchnummer som kopplar ihop transaktionerna.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-142">This number sequence uniquely identifies journals and acts as a batch number that links the transactions together.</span></span>

## <a name="example-3"></a><span data-ttu-id="9e7d9-143">Exempel 3</span><span class="sxs-lookup"><span data-stu-id="9e7d9-143">Example 3</span></span>

<span data-ttu-id="9e7d9-144">Du definierar följande datakällor i din modellmappning:</span><span class="sxs-lookup"><span data-stu-id="9e7d9-144">The following data sources are defined in your model mapping:</span></span>

- <span data-ttu-id="9e7d9-145">**enumScope**-datakällan för Microsoft Dynamics 365 Finance typen *uppräkning*.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-145">The **enumScope** data source of the Microsoft Dynamics 365 Finance *enumeration* type.</span></span> <span data-ttu-id="9e7d9-146">Den här datakällan refererar till den utökade uppräkningen **ERExpressionNumberSequenceScopeType**.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-146">This data source refers to the **ERExpressionNumberSequenceScopeType** enumeration.</span></span>
- <span data-ttu-id="9e7d9-147">**NumSeq**-datakällan för typen *beräknade fält*.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-147">The **NumSeq** data source of the *Calculated field* type.</span></span> <span data-ttu-id="9e7d9-148">Datakällan innehåller uttrycket `NUMSEQVALUE ("Gene_1", enumScope.Company, "")`.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-148">This data source contains the expression `NUMSEQVALUE ("Gene_1", enumScope.Company, "")`.</span></span>

<span data-ttu-id="9e7d9-149">När datakällan **NumSeq** kallas, returneras det nya genererade värdet för nummerserien **Gen\_1** som har konfigurerats för det företag som tillhandahåller den kontext som ER-formatet körs under.</span><span class="sxs-lookup"><span data-stu-id="9e7d9-149">When the **NumSeq** data source is called, it returns the new generated value of the **Gene\_1** number sequence that has been configured for the company that supplies the context that the ER format is run under.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9e7d9-150">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="9e7d9-150">Additional resources</span></span>

[<span data-ttu-id="9e7d9-151">Andra (företagsdomänspecifika) funktioner</span><span class="sxs-lookup"><span data-stu-id="9e7d9-151">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]