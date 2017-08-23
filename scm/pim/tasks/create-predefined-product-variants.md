--- 
title: "Skapa fördefinierade produktvarianter"
description: "Den här proceduren går igenom hur du skapar produktvarianter för en produktmall med kombinationer av produktdimensioner."
author: BibiSp
manager: AnnBe
ms.date: 10/27/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bibis
ms.search.scope: Operations
ms.search.region: Global
ms.author: bibis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: fd6e6844b5920ba1364fa0fd5865d89d83789973
ms.contentlocale: sv-se
ms.lasthandoff: 07/28/2017

---
# <a name="create-predefined-product-variants"></a>Skapa fördefinierade produktvarianter

[!include[task guide banner](../../includes/task-guide-banner.md)]

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


