---
title: Måttenhetskonvertering per produktvariant
description: Det här avsnittet beskriver hur måttenhetskonvertering kan ställas in på produktvarianter.
author: johanhoffmann
manager: AnnBe
ms.date: 01/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: UnitOfMeasureConversion
ROBOTS: noindex, nofollow
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-04-01
ms.dyn365.ops.version: 10
ms.openlocfilehash: c8181f0bda9b781a6c2b0feb0aba1beb51bfea65
ms.sourcegitcommit: af36eb17b36092a3101bbfc96486b25036676558
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/06/2020
ms.locfileid: "2935109"
---
# <a name="unit-of-measure-conversion-per-product-variant"></a>Måttenhetskonvertering per produktvariant

[!include [banner](../includes/banner.md)]

Det här avsnittet beskriver hur måttenhetskonvertering kan ställas in på produktvarianter. Den innehåller ett exempel på inställningarna.

Den här funktionen gör det möjligt för företag att definiera olika enhetskonverteringar mellan varianter av samma produkt. Följande exempel används i det här avsnittet. Ett företag säljer t-shirts i storlek Small, Medium, Large och Extra large. T-shirten definieras som en produkt och de olika storlekarna definieras som varianter av produkten. T-shirts förpackas i lådor och det kan finnas fem T-shirts i en låda, med undantag för Extra large som endast kan fyra T-shirts. Företaget vill spåra olika varianter av T-shirts i enheten **enheter** men säljer T-shirts i enheten **lådor**. Konverteringen mellan lagerenheten och försäljningsenheten är 1 låda = 5 enheter utom varianten Extra large där konverteringen är 1 låda = 4 enheter.

### <a name="set-up-a-product-for-unit-conversion-per-variant"></a>Konfigurera en produkt för enhetskonvertering per variant

Produktvarianter kan bara skapas för produkter av **undertypen Produkt**: **produktmall**. Mer information finns i [Skapa en produktmall](tasks/create-product-master.md).

Funktionen är inte aktiverad för produkter som har ställts in för faktisk/nominell vikt-processer. 

När produktmallen med frisläppta produktvarianter skapas kan enhetskonverteringar per varianter ställas in. Du hittar alternativet för att öppna sidan enhetskonvertering i samband med en produkt eller en produktvariant på följande sidor.

-   Sidan **Produktinformation**
-   Sidan **Uppgifter om frisläppta produkter**
-   Sidan **Frisläppta produktvarianter**

När du öppnar sidan **Enhetskonvertering** i samband med en produktmall eller frisläppt produktvariant kan du välja om du vill ställa in enhetskonvertering för produkten eller för en produktvariant. Du gör detta genom att välja antingen **Produktvariant** eller **Produkt** i fältet **Skapa konvertering för**.

### <a name="product-variant"></a>Produktvariant

Om du väljer **Produktvariant** kan du sedan välja vilken variant du vill ställa in enhetskonvertering i fältet **Produktvariant**.

### <a name="product"></a>Produkt

Om du väljer **Produkt** kan du ställa in en enhetskonvertering för produktmallen. Denna enhetskonvertering gäller för alla produktvarianter utan definierad enhetskonvertering.

### <a name="example"></a>Exempel

En produktmall **T-Shirt** har fyra frisläppta produktvarianter Small, Medium, Large och X-Large. T-shirts förpackas i lådor och det kan finnas fem T-shirts i en låda, med undantag för Extra large som endast kan fyra T-shirts.

Öppna först sidan **Enhetskonvertering** från sidan Information om frisläppt produkt för **T-shirt.**

På sidan **Enhetskonvertering**, ställ in enhetskonvertering för den frisläppta produktvarianten X-Large.

| **Fält**             | **Inställning**             |
|-----------------------|-------------------------|
| Skapa konvertering för | Produktvariant         |
| Produktvariant       | T-Shirt : : X-Large : : |
| Från enhet             | Lådor                   |
| Faktor                | 4                       |
| Till enhet               | Antal                  |

De frisläppta produktvarianten Small, Medium och Large har samma enhetskonvertering mellan enheten Låda och Enheter, vilket innebär att du kan definiera enhetskonvertering för dessa produktvarianter för produktmallen.

| **Fält**             | **Inställning** |
|-----------------------|-------------|
| Skapa konvertering för | Produkt     |
| Produkt               | T-shirt     |
| Från enhet             | Lådor       |
| Faktor                | 5           |
| Till enhet               | Antal      |

### <a name="using-excel-to-update-the-unit-conversions"></a>Uppdatera enhetskonverteringarna med Excel

Om en produkt har många produktvarianter med olika enhetskonverteringar, är det en bra idé att exportera enhetskonverteringar från sidan **Enhetskonvertering** till ett Excel-kalkylblad, uppdatera konverteringar och publicera tillbaka dem i Supply Chain Mangement.

Alternativet för att exportera till Excel och publicera ändringarna tillbaka till Supply Chain Mangement aktiveras från menyobjektet **Öppna i Microsoft Office** i åtgärdsfönstret på sidan **Enhetskonverteringar**.
