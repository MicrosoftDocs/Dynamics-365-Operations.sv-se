---
title: Funktionen FORMAT ER
description: Det här avsnittet innehåller information om hur funktionen FORMAT elektronisk rapportering (ER) används.
author: NickSelin
manager: kfend
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
ms.openlocfilehash: fc8b0d6e25e12165e2a89f11d3c577d5ba8c7706
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5566160"
---
# <a name="format-er-function"></a><span data-ttu-id="cbbd8-103">Funktionen FORMAT ER</span><span class="sxs-lookup"><span data-stu-id="cbbd8-103">FORMAT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="cbbd8-104">`FORMAT` funktionen returnerar den angivna strängen som ett *Sträng* efter att den har formaterats genom att byta ut alla förekomster av **%N** med argumentet *N* th.</span><span class="sxs-lookup"><span data-stu-id="cbbd8-104">The `FORMAT` function returns the specified string as a *String* value after it has been formatted by substituting any occurrences of **%N** with the *N* th argument.</span></span>

## <a name="syntax"></a><span data-ttu-id="cbbd8-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="cbbd8-105">Syntax</span></span>

```vb
FORMAT (string, argument 1[, argument 2, …, argument N])
```

## <a name="arguments"></a><span data-ttu-id="cbbd8-106">Argument</span><span class="sxs-lookup"><span data-stu-id="cbbd8-106">Arguments</span></span>

<span data-ttu-id="cbbd8-107">`string`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="cbbd8-107">`string`: *String*</span></span>

<span data-ttu-id="cbbd8-108">En referens till en datakälla av datatypen *Sträng* som måste formateras.</span><span class="sxs-lookup"><span data-stu-id="cbbd8-108">A reference to a data source of the *String* type that must be formatted.</span></span> <span data-ttu-id="cbbd8-109">Detta argument krävs.</span><span class="sxs-lookup"><span data-stu-id="cbbd8-109">This argument is required.</span></span>

<span data-ttu-id="cbbd8-110">`argument 1`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="cbbd8-110">`argument 1`: *String*</span></span>

<span data-ttu-id="cbbd8-111">Det första argumentet, som används för att ersätta förekomster av **%1**.</span><span class="sxs-lookup"><span data-stu-id="cbbd8-111">The first argument, which is used to replace occurrences of **%1**.</span></span> <span data-ttu-id="cbbd8-112">Detta argument krävs.</span><span class="sxs-lookup"><span data-stu-id="cbbd8-112">This argument is required.</span></span>

<span data-ttu-id="cbbd8-113">`argument N`: *Sträng*</span><span class="sxs-lookup"><span data-stu-id="cbbd8-113">`argument N`: *String*</span></span>

<span data-ttu-id="cbbd8-114">Argumentet *N* th som används för att ersätta förekomster av **%2**, **%3**, etc.</span><span class="sxs-lookup"><span data-stu-id="cbbd8-114">The *N* th argument, which is used to replace occurrences of **%2**, **%3**, and so on.</span></span> <span data-ttu-id="cbbd8-115">Dessa ytterligare argument är valfria.</span><span class="sxs-lookup"><span data-stu-id="cbbd8-115">These additional arguments are optional.</span></span>

## <a name="return-values"></a><span data-ttu-id="cbbd8-116">Returvärden</span><span class="sxs-lookup"><span data-stu-id="cbbd8-116">Return values</span></span>

<span data-ttu-id="cbbd8-117">*Sträng*</span><span class="sxs-lookup"><span data-stu-id="cbbd8-117">*String*</span></span>

<span data-ttu-id="cbbd8-118">Det resulterande textvärdet.</span><span class="sxs-lookup"><span data-stu-id="cbbd8-118">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="cbbd8-119">Användningsanteckningar</span><span class="sxs-lookup"><span data-stu-id="cbbd8-119">Usage notes</span></span>

<span data-ttu-id="cbbd8-120">Om ett argument inte har angetts för en parameter returneras parametern som **"%N"** i strängen.</span><span class="sxs-lookup"><span data-stu-id="cbbd8-120">If an argument isn't provided for a parameter, the parameter is returned as **"%N"** in the string.</span></span> <span data-ttu-id="cbbd8-121">För värden av typen *real* är standard strängkonverteringen begränsad till två decimaler.</span><span class="sxs-lookup"><span data-stu-id="cbbd8-121">For values of the *Real* type, the default string conversion is limited to two decimal places.</span></span>

## <a name="example"></a><span data-ttu-id="cbbd8-122">Exempel</span><span class="sxs-lookup"><span data-stu-id="cbbd8-122">Example</span></span>

<span data-ttu-id="cbbd8-123">I följande illustration returnerar **PaymentModel**-datakällan en lista med kundposter med hjälp av **kund**-komponenten.</span><span class="sxs-lookup"><span data-stu-id="cbbd8-123">In the following illustration, the **PaymentModel** data source returns a list of customer records by using the **Customer** component.</span></span> <span data-ttu-id="cbbd8-124">Värdet för bearbetningsdatum returneras med hjälp av fältet **ProcessingDate**.</span><span class="sxs-lookup"><span data-stu-id="cbbd8-124">It returns the processing date value by using the **ProcessingDate** field.</span></span>

<a href="./media/picture-format-datasource.jpg"><img src="./media/picture-format-datasource.jpg" alt="PaymentModel data source" class="alignnone wp-image-290751 size-full" width="293" height="143" /></a>

<span data-ttu-id="cbbd8-125">I ER-formatet (elektronisk rapportering), som har utformats för att generera en elektronisk fil för utvalda kunder, väljs **PaymentModel** som en datakälla och styr processflödet.</span><span class="sxs-lookup"><span data-stu-id="cbbd8-125">In the Electronic reporting (ER) format that is designed to generate an electronic file for selected customers, **PaymentModel** is selected as a data source, and it controls the process flow.</span></span> <span data-ttu-id="cbbd8-126">Om en utvald kund stoppas för det datum då rapporten behandlas erhålls ett undantag för att meddela användaren.</span><span class="sxs-lookup"><span data-stu-id="cbbd8-126">If a selected customer is stopped for the date when the report is processed, an exception is thrown to notify the user.</span></span> <span data-ttu-id="cbbd8-127">Formeln, som utformats för denna typ av bearbetningsstyrning, kan endast använda följande resurser:</span><span class="sxs-lookup"><span data-stu-id="cbbd8-127">The formula that is designed for this type of processing control can use the following resources:</span></span>

- <span data-ttu-id="cbbd8-128">Label SYS70894, som har följande text:</span><span class="sxs-lookup"><span data-stu-id="cbbd8-128">Label SYS70894, which has the following text:</span></span>

    - <span data-ttu-id="cbbd8-129">**För språket EN-US:** "Nothing to print"</span><span class="sxs-lookup"><span data-stu-id="cbbd8-129">**For the EN-US language:** "Nothing to print"</span></span>
    - <span data-ttu-id="cbbd8-130">**För språket SV-SE:** "Inget att skriva ut"</span><span class="sxs-lookup"><span data-stu-id="cbbd8-130">**For the DE language:** "Nichts zu drucken"</span></span>

- <span data-ttu-id="cbbd8-131">Label SYS18389, som har följande text:</span><span class="sxs-lookup"><span data-stu-id="cbbd8-131">Label SYS18389, which has the following text:</span></span>

    - <span data-ttu-id="cbbd8-132">**För språket EN-US:** "Kund %1 stoppas för %2."</span><span class="sxs-lookup"><span data-stu-id="cbbd8-132">**For the EN-US language:** "Customer %1 is stopped for %2."</span></span>
    - <span data-ttu-id="cbbd8-133">**För språket DE:** "Debitor '%1' wird für %2 gesperrt."</span><span class="sxs-lookup"><span data-stu-id="cbbd8-133">**For the DE language:** "Debitor '%1' wird für %2 gesperrt."</span></span>

<span data-ttu-id="cbbd8-134">Här följer uttrycket som kan utformas.</span><span class="sxs-lookup"><span data-stu-id="cbbd8-134">Here is the expression that can be designed.</span></span>

```vb
FORMAT (CONCATENATE (@"SYS70894", ". ", @"SYS18389"), model.Customer.Name, DATETIMEFORMAT (model.ProcessingDate, "d"))
```

<span data-ttu-id="cbbd8-135">Om en rapport bearbetas för kunden **Litware-butikskund** en 17 december 2015 i kulturen **SV-SV** och på språket **SV-SV**, kommer denna formel att returnera följande text som kan presenteras som ett undantagsmeddelande för slutanvändaren:</span><span class="sxs-lookup"><span data-stu-id="cbbd8-135">If a report is processed for the **Litware Retail** customer on December 17, 2015, in the **EN-US** culture and the **EN-US** language, this formula returns the following text, which can be presented to the user as an exception message:</span></span>

<span data-ttu-id="cbbd8-136">*Inget att skriva ut. Customer Litware Retail is stopped for 12/17/2015.*</span><span class="sxs-lookup"><span data-stu-id="cbbd8-136">*Nothing to print. Customer Litware Retail is stopped for 12/17/2015.*</span></span>

<span data-ttu-id="cbbd8-137">Om samma rapport bearbetas för **Litware-butikskunden** den 17 december 2015, i kulturen **DE** och på språket **DE**, kommer denna formel att returnera följande text som använder ett annat datumformat:</span><span class="sxs-lookup"><span data-stu-id="cbbd8-137">If the same report is processed for the **Litware Retail** customer on December 17, 2015, in the **DE** culture and the **DE** language, the formula returns the following text, which uses a different date format:</span></span>

<span data-ttu-id="cbbd8-138">*Nichts zu drucken. Debitor 'Litware Retail' wird für 17.12.2015 gesperrt.*</span><span class="sxs-lookup"><span data-stu-id="cbbd8-138">*Nichts zu drucken. Debitor 'Litware Retail' wird für 17.12.2015 gesperrt.*</span></span>

>[!NOTE]
> <span data-ttu-id="cbbd8-139">Följande syntax tillämpas i ER-formler för etiketter:</span><span class="sxs-lookup"><span data-stu-id="cbbd8-139">The following syntax is applied in ER formulas for labels:</span></span>
>
> - <span data-ttu-id="cbbd8-140">**För etiketter från resurser i Microsoft Dynamics 365 Finance-app:** **\@X**, där **X** är etikett-ID i programobjektträdet (AOT)</span><span class="sxs-lookup"><span data-stu-id="cbbd8-140">**For labels from resources in the Microsoft Dynamics 365 Finance app:** **\@X**, where **X** is the label ID in the Application Object Tree (AOT)</span></span>
> - <span data-ttu-id="cbbd8-141">**För etiketter i ER-konfigurationer:** **@"GER_LABEL:X"**, där **X** är etikett-ID i ER-konfiguration</span><span class="sxs-lookup"><span data-stu-id="cbbd8-141">**For labels that reside in ER configurations:** **@"GER_LABEL:X"**, where **X** is the label ID in the ER configuration</span></span>

## <a name="additional-resources"></a><span data-ttu-id="cbbd8-142">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="cbbd8-142">Additional resources</span></span>

[<span data-ttu-id="cbbd8-143">Textfunktioner</span><span class="sxs-lookup"><span data-stu-id="cbbd8-143">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]