--- 
title: "Skapa ett produktnummer för fördefinierade produktvarianter"
description: "Denna guide visar dig hur du skapar en produktnummernomenklatur för fördefinierade produktvarianter, samt hur du tilldelar denna till lämplig produktdimensionsgrupp."
author: BibiSp
manager: AnnBe
ms.date: 09/26/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 6294e4608b31c37aa713e3a7a2028b409b5a8366
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-product-number-for-predefined-product-variants"></a>Skapa ett produktnummer för fördefinierade produktvarianter

[!include[task guide banner](../../includes/task-guide-banner.md)]

Denna guide visar dig hur du skapar en produktnummernomenklatur för fördefinierade produktvarianter, samt hur du tilldelar denna till lämplig produktdimensionsgrupp. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF. Den nya produktnummernomenklaturen tilldelas till produktdimensionsgruppen Color and Size. Den här uppgiften utförs vanligtvis av en produktdesigner.


## <a name="create-a-product-number-nomenclature"></a>Skapa en nomenklatur för produktnummer
1. Klicka på Definition av produktvariantmodell.
2. Klicka på Product nomenclature.
3. Klicka på Ny.
4. I fältet Namn anger du ett nomenklatursnamn som gör det enkelt att identifiera målproduktdimensionsgruppen, till exempel ColorSize.
5. Ange ett värde i fältet Beskrivning.
6. Klicka på Lägg till.
7. Klicka på Product master number.
8. Klicka på Lägg till.
9. Klicka på Text constant.
10. Skriv ett värde i fältet Text.
11. Klicka på Lägg till.
12. Klicka på Color.
13. Klicka på Lägg till.
14. Klicka på Text constant.
15. Skriv ett värde i fältet Text.
16. Klicka på Lägg till.
17. Klicka på Size.
18. Stäng sidan.

## <a name="assign-the-nomenclature-to-a-product-master"></a>Tilldela nummernomenklaturen till en produktmall
1. Klicka på Product dimension groups.
2. Välj produktdimensionsgruppen SizeCol.
3. Klicka på Redigera.
4. Välj Yes i fältet Use nomenclature.
5. I nomenklatursfältet Product variant number anger eller väljer du ett värde.
6. Stäng sidan.


