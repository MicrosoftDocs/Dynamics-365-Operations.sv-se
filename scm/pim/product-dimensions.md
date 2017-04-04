---
title: Produktdimensioner
description: "Det finns fyra produktdimensioner - färg, konfiguration, storlek och format. Du kombinerar produktdimensioner i dimensionsgrupper och tilldelar dimensionsgrupper till produktmallar. Kombinationerna av produktdimensioner bestämmer hur produktvarianter definieras."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: EcoResProductDimension, EcoResProductDimensionGroup, EcoResProductMasterDimension, RetailEcoResColor, RetailEcoResSize, RetailEcoResStyle
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 19171
ms.assetid: 81fa3709-4ab8-4fbf-9806-359892a05985
ms.search.region: Global
ms.search.industry: Retail
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 8854ab94a71cc363bcd073d2df47bc01a243b6cd
ms.lasthandoff: 03/31/2017


---

# <a name="product-dimensions"></a>Produktdimensioner

Det finns fyra produktdimensioner - färg, konfiguration, storlek och format. Du kombinerar produktdimensioner i dimensionsgrupper och tilldelar dimensionsgrupper till produktmallar. Kombinationerna av produktdimensioner bestämmer hur produktvarianter definieras.

Produktdimensioner är egenskaper som används för att identifiera en produktvariant. Du kan använda kombinationer av produktdimensioner för att definiera produktvarianter. Du måste definiera minst en produktdimension för en produktmall om du vill skapa en produktvariant.
Produktvarianter
----------------

Produktvarianter kallas också för artiklar. En artikel är en materiell produkt, vilket inte är detsamma som en tjänst. Det är också möjligt att definiera en produktmall tjänsttypen. Med typen Tjänst kan du ange produktvarianter som innehåller tjänster. Du kan till exempel ange en produktmall för konsultarbete och produktvarianter för arbete som utförs av seniorkonsulter och juniorkonsulter.

## <a name="product-dimensions"></a>Produktdimensioner
Följande produktdimensioner finns: konfiguration, färg, storlek och format. En produktvariant genereras utifrån produkt dimensionsvärden.

Produkten dimensioner värdena exempelvis storlek, färg och utförande kan skapas på den **storlek**, **färg** och **utförande** sidor som kan nås från följande platser: **produktinformationshantering**&gt;**inställningar**&gt;**Dimension och variant grupper**&gt;**storlek-färger-format**. Produktdimensionsvärden för konfigurationsdimensionen skapas vanligtvis med hjälp av antingen produktkonfigureraren eller med den dimensionsbaserade konfigureraren. Produktdimensioner kan också skapas och underhållas på sidan **Produktdimensioner** som du öppnar från följande platser:
-   Klicka på **produktinformationshantering**&gt;**produkter**&gt;**produktmallar**. I den **åtgärdsfönstret**, klickar du på **produktdimensioner**.
-   Klicka på **produktinformationshantering**&gt;**produkter**&gt;**alla produkter och produktmallar**. Välj en produktmall. I den **åtgärdsfönstret**, klickar du på **produktdimensioner**.
-   Klicka på **produktinformationshantering**&gt;**frisläppta produkter**. Välj en produktmall. I den **åtgärdsfönstret**, klickar du på **produkt**. I gruppen **Produktmall**, klicka på **Produktdimensioner**.

Antalet varianter som du kan skapa för en artikel begränsas av antalet möjliga produktdimensionskombinationer.
| **Tips! **                                                                                                                                              |
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




