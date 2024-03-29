---
title: Funktionen FORMAT ER
description: Den här artikeln innehåller information om hur funktionen FORMAT elektronisk rapportering (ER) används.
author: kfend
ms.date: 12/12/2019
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: a7eb3d4a4c72e8faf40d28a724cda5ba7d7e8a47
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9286012"
---
# <a name="format-er-function"></a>Funktionen FORMAT ER

[!include [banner](../includes/banner.md)]

`FORMAT` funktionen returnerar den angivna strängen som ett *Sträng* efter att den har formaterats genom att byta ut alla förekomster av **%N** med argumentet *N* th.

## <a name="syntax"></a>Syntax

```vb
FORMAT (string, argument 1[, argument 2, …, argument N])
```

## <a name="arguments"></a>Argument

`string`: *Sträng*

En referens till en datakälla av datatypen *Sträng* som måste formateras. Detta argument krävs.

`argument 1`: *Sträng*

Det första argumentet, som används för att ersätta förekomster av **%1**. Detta argument krävs.

`argument N`: *Sträng*

Argumentet *N* th som används för att ersätta förekomster av **%2**, **%3**, etc. Dessa ytterligare argument är valfria.

## <a name="return-values"></a>Returvärden

*Sträng*

Det resulterande textvärdet.

## <a name="usage-notes"></a>Användningsanteckningar

Om ett argument inte har angetts för en parameter returneras parametern som **"%N"** i strängen. För värden av typen *real* är standard strängkonverteringen begränsad till två decimaler.

## <a name="example"></a>Exempel

I följande illustration returnerar **PaymentModel**-datakällan en lista med kundposter med hjälp av **kund**-komponenten. Värdet för bearbetningsdatum returneras med hjälp av fältet **ProcessingDate**.

<a href="./media/picture-format-datasource.jpg"><img src="./media/picture-format-datasource.jpg" alt="PaymentModel data source" class="alignnone wp-image-290751 size-full" width="293" height="143" /></a>

I ER-formatet (elektronisk rapportering), som har utformats för att generera en elektronisk fil för utvalda kunder, väljs **PaymentModel** som en datakälla och styr processflödet. Om en utvald kund stoppas för det datum då rapporten behandlas erhålls ett undantag för att meddela användaren. Formeln, som utformats för denna typ av bearbetningsstyrning, kan endast använda följande resurser:

- Label SYS70894, som har följande text:

    - **För språket EN-US:** "Nothing to print"
    - **För språket SV-SE:** "Inget att skriva ut"

- Label SYS18389, som har följande text:

    - **För språket EN-US:** "Kund %1 stoppas för %2."
    - **För språket DE:** "Debitor '%1' wird für %2 gesperrt."

Här följer uttrycket som kan utformas.

```vb
FORMAT (CONCATENATE (@"SYS70894", ". ", @"SYS18389"), model.Customer.Name, DATETIMEFORMAT (model.ProcessingDate, "d"))
```

Om en rapport bearbetas för kunden **Litware-butikskund** en 17 december 2015 i kulturen **SV-SV** och på språket **SV-SV**, kommer denna formel att returnera följande text som kan presenteras som ett undantagsmeddelande för slutanvändaren:

*Inget att skriva ut. Customer Litware Retail is stopped for 12/17/2015.*

Om samma rapport bearbetas för **Litware-butikskunden** den 17 december 2015, i kulturen **DE** och på språket **DE**, kommer denna formel att returnera följande text som använder ett annat datumformat:

*Nichts zu drucken. Debitor 'Litware Retail' wird für 17.12.2015 gesperrt.*

>[!NOTE]
> Följande syntax tillämpas i ER-formler för etiketter:
>
> - **För etiketter från resurser i Microsoft Dynamics 365 Finance-app:** **\@X**, där **X** är etikett-ID i programobjektträdet (AOT)
> - **För etiketter i ER-konfigurationer:** **@"GER_LABEL:X"**, där **X** är etikett-ID i ER-konfiguration

## <a name="additional-resources"></a>Ytterligare resurser

[Textfunktioner](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
