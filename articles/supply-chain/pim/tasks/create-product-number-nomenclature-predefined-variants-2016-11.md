---
title: Skapa en produktnummernomenklatur för fördefinierade produktvarianter
description: Denna guide visar dig hur du skapar en produktnummernomenklatur för fördefinierade produktvarianter, samt hur du tilldelar denna till lämplig produktdimensionsgrupp.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductDimensionGroup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4b49e96677b94d5f669ea41861f64e62e118938c
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1550593"
---
# <a name="create-a-product-number-nomenclature-for-predefined-product-variants"></a>Skapa en produktnummernomenklatur för fördefinierade produktvarianter

[!include [task guide banner](../../includes/task-guide-banner.md)]

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

