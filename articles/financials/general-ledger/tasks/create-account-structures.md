---
title: Skapa kontostrukturer
description: Den här uppgiften leder dig genom stegen för att skapa en kontostruktur.
author: aprilolson
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DimensionConfigureAccountStructure, DimensionCreateAccountStructure, DimensionHierarchyAddLevel, DimensionHierarchyConstraintActivate
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8b100d5da6ec26dc386c0c6cb0793245531eb0d8
ms.sourcegitcommit: cbcf344b3b552acca56c3e27606eac7f2f124afe
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/22/2019
ms.locfileid: "1916240"
---
# <a name="create-account-structures"></a>Skapa kontostrukturer

[!include [task guide banner](../../includes/task-guide-banner.md)]

Den här uppgiften leder dig genom stegen för att skapa en kontostruktur. Demoföretaget USMF används i stegen.

1. Gå till **Navigeringsfönster > Moduler > Redovisning > Kontoplaner > Strukturer > Konfigurera kontostrukturer**.
2. Klicka på **Ny** i **åtgärdsfönstret** för att öppna dialogrutan.
3. Ange ett namn som beskriver syftet med kontostrukturen i fältet **Kontostruktur**.
4. Ange en beskrivning för att ange syftet med kontostrukturen i fältet **Beskrivning**.
5. Klicka på **Skapa**.
6. Klicka på **Lägg till segment** i **Segment och tillåtna värden**.
7. I listan Dimensioner väljer du den dimension du vill lägga till i kontostrukturen.
8. Klicka på **Lägg till segment** i slutet av listan.
9. Upprepa steg 6 till 9 efter behov.
10. I avsnittet **Information om tillåtna värden** väljer du segmentet för att redigera de tillåtna värdena.
    Klicka till exempel i fältet **Huvudkonto**.  
11. Välj ett alternativ i fältet **Operator**, till exempel ligger mellan eller inkluderar.
12. Ange ett värde i fältet **Värde**. Exempelvis 600000.  
13. Skriv ett värde i fältet **via**. Exempelvis 699999.  
14. Klicka på **Använd** i avsnittet **Information om tillåtna värden**.
15. Upprepa steg 10 till 15 efter behov.  
16. Klicka på **Lägg till nya kriterier** i avsnittet **Information om tillåtna värden**.
17. Välj ett alternativ i fältet Operator, t.ex. är mellan och inkluderar.
18. Ange ett värde i fältet **Värde**. Exempelvis 033.  
19. Skriv ett värde i fältet **via**. Exempelvis 034.  
20. Klicka på **Använd**.
21. I rutnätet väljer du segmentet för att redigera de tillåtna värdena. Till exempel Kostnadsställe  
22. Skriv ett värde i fältet **CostCenter**. Till exempel 007..021.  
23. Klicka på **Lägg till** i **Segment och tillåtna värden**.
24. Ange ett värde i fältet **MainAccount**. Till exempel 600000..699999  
25. I rutnätet väljer du segmentet för att redigera de tillåtna värdena. Till exempel Avdelning.  
26. Ange ett värde i fältet Avdelning. Exempelvis 032.  
27. Skriv ett värde i fältet CostCenter. Exempelvis 086.  
28. Klicka på **Validera** i **åtgärdsfönstret**.
29. Klicka på **Aktivera** i **åtgärdsfönstret**.
30. Klicka på **Aktivera**.

