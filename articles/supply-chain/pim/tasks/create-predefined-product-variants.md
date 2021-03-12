---
title: Skapa fördefinierade produktvarianter
description: Den här proceduren går igenom hur du skapar produktvarianter för en produktmall med kombinationer av produktdimensioner.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductListPage, EcoResProductCreate, EcoResProductDetails, EcoResProductMasterDimension, EcoResProductVariants, EcoResProductVariantSuggestions, EcoResProductVariantsPendingReleaseFormPart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d07a090dbd41eb17e8d604887435bbb8b07e8d9e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4966940"
---
# <a name="create-predefined-product-variants"></a>Skapa fördefinierade produktvarianter

[!include [banner](../../includes/banner.md)]

Den här proceduren går igenom hur du skapar produktvarianter för en produktmall med kombinationer av produktdimensioner. Demonstrationsdataföretaget som används för att skapa den här proceduren är USMF.


## <a name="create-a-product-master"></a>Skapa en produktmall
1. Gå till Produktinformationshantering > Produkter > Produktmallar.
2. Klicka på Ny.
3. Skriv ett värde i fältet Produktnummer.
    * Att ange ett produktnummer manuellt krävs endast om ingen nummerserie har ställts in för produktnummerfältet. Hoppa över steget om nummerserien har angetts för fältet.  
4. Skriv ett värde i fältet Produktnamn.
5. Ange eller välj ett värde i fältet Produktdimensionsgrupp.
    * Välj produktdimensiongruppen SizeCol (storlek och färg).  
6. Klicka på OK.

## <a name="add-product-dimensions"></a>Lägg till Produktdimensioner
1. Klicka på produktdimensioner
    * Det här exemplet visar hur du manuellt anger produktdimensioner. Du kan också välja att markera en Storlek, Färg eller utförandegrupp som innehåller produktdimensionvärdena, som du vill använda.  
2. Klicka på Ny.
3. Markera vald rad i listan.
4. Ange eller välj ett värde i fältet Storlek.
5. Skriv ett värde i fältet Namn.
6. Klicka på Ny.
7. Markera vald rad i listan.
8. Ange eller välj ett värde i fältet Storlek.
9. Skriv ett värde i fältet Namn.
10. Klicka på fliken Färger.
11. Klicka på Ny.
12. Markera vald rad i listan.
13. Ange eller välj ett värde i fältet Färg.
14. Skriv ett värde i fältet Namn.
15. Klicka på Ny.
16. Markera vald rad i listan.
17. Ange eller välj ett värde i fältet Färg.
18. Skriv ett värde i fältet Namn.
19. Klicka på Spara.
20. Stäng sidan.

## <a name="generate-product-variants"></a>Skapa produktvarianter
1. Klicka på Produktvarianter
2. Klicka på Variantförslag
3. Klicka på Markera alla.
    * I det här exemplet väljs alla möjliga varianter. Om bara en delmängd av de möjliga produktdimensionkombinationerna ska användas för att skapa varianter, kan du välja de enskilda posterna.  
4. Klicka på Skapa.
    * Du kan generera beskrivningar av alla dina varianter baserat på kombinationen av produktdimensionvärden. Beskrivningar är valfria.  
5. Klicka på Spara.

