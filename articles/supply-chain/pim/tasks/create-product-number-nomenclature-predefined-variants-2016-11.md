---
title: Skapa en produktnummernomenklatur för fördefinierade produktvarianter
description: Detta avsnitt visar dig hur du skapar en produktnummernomenklatur för fördefinierade produktvarianter, samt hur du tilldelar denna till lämplig produktdimensionsgrupp.
author: ShylaThompson
manager: AnnBe
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductDimensionGroup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 073b680c48855b2a8902c19cedfbf98cdbfdf17d
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3150066"
---
# <a name="create-a-product-number-nomenclature-for-predefined-product-variants"></a>Skapa en produktnummernomenklatur för fördefinierade produktvarianter

[!include [banner](../../includes/banner.md)]

Detta avsnitt visar dig hur du skapar en produktnummernomenklatur för fördefinierade produktvarianter, samt hur du tilldelar denna till lämplig produktdimensionsgrupp. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF. Den nya produktnummernomenklaturen tilldelas till produktdimensionsgruppen Color and Size. Den här uppgiften utförs vanligtvis av en produktdesigner.


## <a name="create-a-product-number-nomenclature"></a>Skapa en nomenklatur för produktnummer
1. Välj **Definition av produktvariantmodell**.
2. Välj **Produktnomenklatur**.
3. Välj **Ny**.
4. I fältet **Namn** anger du ett nomenklatursnamn som gör det enkelt att identifiera målproduktdimensionsgruppen, till exempel `ColorSize`.
5. I fältet **Beskrivning** anger du ett värde.
6. Markera **Lägg till**.
7. Välj **Produktmallsnummer**.
8. Markera **Lägg till**.
9. Välj **Textkonstant**.
10. Skriv ett värde i fältet **Text**.
11. Markera **Lägg till**.
12. Välj **Färg**.
13. Markera **Lägg till**.
14. Välj **Textkonstant**.
15. Skriv ett värde i fältet **Text**.
16. Markera **Lägg till**.
17. Välj **Storlek**.
18. Stäng sidan.

## <a name="assign-the-nomenclature-to-a-product-master"></a>Tilldela nummernomenklaturen till en produktmall
1. Välj **Produktdimensionsgrupper**.
2. Välj **produktdimensionsgruppen SizeCol**.
3. Välj **Redigera**.
4. Välj **Ja** i fältet **Använd nomenklatur**.
5. I fältet **Nomenklatur för produktvariantnummer**, ange eller välj ett värde.
6. Stäng sidan.

