--- 
title: "Skapa en produktnummernomenklatur för konfigurerade produktvarianter"
description: "I den här proceduren visas hur du ställer in en produktnummernomenklatur för konfigurerade produktvarianter, och hur denna kan kopplas till en konfigurerbar produktmall."
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductListPage, EcoResProductDetails, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 800afdf075f0675185514158f3b712a0fe7675e3
ms.contentlocale: sv-se
ms.lasthandoff: 09/14/2018

---
# <a name="create-a-product-number-nomenclature-for-configured-product-variants"></a>Skapa en produktnummernomenklatur för konfigurerade produktvarianter

[!include [task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren visas hur du ställer in en produktnummernomenklatur för konfigurerade produktvarianter, och hur denna kan kopplas till en konfigurerbar produktmall. I den här proceduren visas även hur du kan skapa en konfigurationsnomenklatur för en modellkomponent för en produktkonfiguration. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF. Den nya produktnummernomenklaturen tilldelas produktmallen D0004. Den här uppgiften utförs vanligtvis av en produktdesigner.


## <a name="create-a-product-number-nomenclature"></a>Skapa en nomenklatur för produktnummer
1. Klicka på Definition av produktvariantmodell.
2. Klicka på Product nomenclature.
3. Klicka på Ny.
4. Skriv ett värde i fältet Namn.
5. Ange ett värde i fältet Beskrivning.
6. Klicka på Lägg till.
7. Klicka på Product master number.
8. Klicka på Lägg till.
9. Klicka på Text constant.
10. Markera vald rad i listan.
11. Skriv ett värde i fältet Text.
12. Klicka på Lägg till.
13. Klicka på Configuration.
14. Stäng sidan.

## <a name="assign-the-product-number-nomenclature-to-a-product-master"></a>Tilldela produktnummernomenklaturen till en produktmall
1. Klicka på Product masters.
2. Använd snabbfiltret för att söka efter poster. Filtrera till exempel fältet Product number med värdet "D".
3. Klicka på länken på den valda raden i listan.
4. Klicka på Redigera.
5. Välj Yes i fältet Use nomenclature.
6. I nomenklatursfältet Product variant number anger eller väljer du ett värde.
7. Stäng sidan.
8. Stäng sidan.

## <a name="create-nomenclature-for-a-product-configuration-model-component"></a>Skapa en nomenklatur för en komponent i en produktkonfigurationsmodell
1. Klicka på Modeller för produktkonfiguration.
2. Hitta och markera önskad post i listan.
3. Klicka på länken på den valda raden i listan.
4. Klicka på Redigera.
5. Välj Yes i fältet Use configuration nomenclature.
6. Klicka på Lägg till.
7. Klicka på Attribute value.
8. Markera vald rad i listan.
9. Ange eller välj ett värde i fältet Attribute.
10. Klicka på Lägg till.
11. Klicka på Text constant.
12. Markera vald rad i listan.
13. Skriv ett värde i fältet Text.
14. Klicka på Lägg till.
15. Klicka på Attribute value.
16. Markera vald rad i listan.
17. Ange eller välj ett värde i fältet Attribute.
18. Klicka på Lägg till.
19. Klicka på Text constant.
20. Markera vald rad i listan.
21. Skriv ett värde i fältet Text.
22. Klicka på Lägg till.
23. Klicka på Attribute value.
24. Markera vald rad i listan.
25. Ange eller välj ett värde i fältet Attribute.
26. Klicka på Lägg till.
27. Klicka på Text constant.
28. Markera vald rad i listan.
29. Skriv ett värde i fältet Text.
30. Klicka på Lägg till.
31. Klicka på Attribute value.
32. Markera vald rad i listan.
33. Ange eller välj ett värde i fältet Attribute.
34. Klicka på Lägg till.
35. Klicka på Text constant.
36. Markera vald rad i listan.
37. Skriv ett värde i fältet Text.
38. Klicka på Lägg till.
39. Klicka på Number sequence value.
40. Markera vald rad i listan.
41. I fältet Number sequence anger eller väljer du ett värde.
42. Stäng sidan.
43. Stäng sidan.
44. Stäng sidan.


