---
title: Produktdimensioner
description: "Det finns fyra produktdimensioner: färg, konfiguration, storlek och utförande. Du kombinerar produktdimensioner i dimensionsgrupper och tilldelar dimensionsgrupper till produktmallar. Kombinationerna av produktdimensioner bestämmer hur produktvarianter definieras."
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResProductDimension, EcoResProductDimensionGroup, EcoResProductMasterDimension, RetailEcoResColor, RetailEcoResSize, RetailEcoResStyle
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations, Retail
ms.custom: 19171
ms.assetid: 81fa3709-4ab8-4fbf-9806-359892a05985
ms.search.region: Global
ms.search.industry: Retail
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 68f4bfcf62b5e7c65cbe361b510c2769b0e9bebb
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="product-dimensions"></a>Produktdimensioner

[!include[banner](../includes/banner.md)]

[!include[Retail name](../includes/retail-name.md)]


Det finns fyra produktdimensioner: färg, konfiguration, storlek och utförande. Du kombinerar produktdimensioner i dimensionsgrupper och tilldelar dimensionsgrupper till produktmallar. Kombinationerna av produktdimensioner bestämmer hur produktvarianter definieras.

Produktdimensioner är egenskaper som används för att identifiera en produktvariant. Du kan använda kombinationer av produktdimensioner för att definiera produktvarianter. Du måste definiera minst en produktdimension för en produktmall om du vill skapa en produktvariant.
Produktvarianter
----------------

Produktvarianter kallas också för artiklar. En artikel är en materiell produkt, vilket inte är detsamma som en tjänst. Det är också möjligt att definiera en produktmall med typen Tjänst. Med typen Tjänst kan du ange produktvarianter som innehåller tjänster. Du kan till exempel ange en produktmall för konsultarbete och produktvarianter för arbete som utförs av seniorkonsulter och juniorkonsulter.

## <a name="product-dimensions"></a>Produktdimensioner
Följande produktdimensioner finns: konfiguration, färg, storlek och utförande. En produktvariant kan genereras baserat på produktdimensionsvärdena.

Produktdimensionvärden som till exempel Storlek, Färg och Utförande kan skapas på sidorna **Storlek**, **Färg** och **Utförande** som du öppnar från följande platser: **Produktinformationshantering** &gt; **Inställningar** &gt; **Dimensions- och variantgrupper** &gt; **Storlekar/Färger/Utföranden**. Produktdimensionsvärden för konfigurationsdimensionen skapas vanligtvis med hjälp av antingen produktkonfigureraren eller med den dimensionsbaserade konfigureraren. Produktdimensioner kan också skapas och underhållas på sidan **Produktdimensioner** som du öppnar från följande platser:
-   Klicka på **Produktinformationshantering** &gt; **Produkter** &gt; **Produktmallar**. I **Åtgärdsfönstret**, klicka på **Produktdimensioner**.
-   Klicka på **Produktinformationshantering** &gt; **Produkter** &gt; **Alla produkter och produktmallar**. Välj en produktmall. I **Åtgärdsfönstret**, klicka på **Produktdimensioner**.
-   Klicka på **Produktinformationshantering** &gt; **Frisläppta produkter**. Välj en produktmall. I **Åtgärdsfönstret**, klicka på **Produkt**. I gruppen **Produktmall**, klicka på **Produktdimensioner**.

Antalet varianter som du kan skapa för en artikel begränsas av antalet möjliga produktdimensionskombinationer.
| **Tips!**                                                                                                                                              |
|------------------------------------------------------------------------------------------------------------------------------------------------------|
| När du använder en produkt på till exempel en orderrad väljer du produktdimensioner för att identifiera produktvarianten du vill arbeta med. |

## <a name="example"></a>Exempel
Ett företag säljer jeans. Artikeln jeans använder produktdimensionerna för färg och storlek. Jeansen säljs i tre olika färger och i sex olika storlekar. Färger: Blått, Svart, Brunt, Storlekar: XS S, XL, L, XL. Alla storlekar är inte tillgängliga i alla tre färger. Om alla kombinationerna vore tillgängliga skulle det skapa 18 olika typer av jeans. I det här exemplet produceras bara följande nio produktvariantkombinationer.

| Färg | Storlek |
|-------|------|
| Blått  | XS   |
| Blått  | L    |
| Blått  | M    |
| Svart | M    |
| Svart | S    |
| Svart | XL   |
| Brun | S    |
| Brun | XL   |
| Brun | XXL  |






