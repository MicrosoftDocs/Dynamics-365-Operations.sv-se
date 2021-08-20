---
title: Skapa en produktnummernomenklatur för fördefinierade produktvarianter
description: Detta avsnitt visar dig hur du skapar en produktnummernomenklatur för fördefinierade produktvarianter, samt hur du tilldelar denna till lämplig produktdimensionsgrupp.
author: ShylaThompson
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductDimensionGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fada426b03aa8a908c3351932a288c911cb8c60fa13ccbfbfd0ceed232759a88
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6736050"
---
# <a name="create-a-product-number-nomenclature-for-predefined-product-variants"></a>Skapa en produktnummernomenklatur för fördefinierade produktvarianter

[!include [banner](../../includes/banner.md)]

Detta avsnitt visar dig hur du skapar en produktnummernomenklatur för fördefinierade produktvarianter, samt hur du tilldelar denna till lämplig produktdimensionsgrupp. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF. Den nya produktnummernomenklaturen tilldelas till produktdimensionsgruppen Color and Size. Den här uppgiften utförs vanligtvis av en produktdesigner.


## <a name="create-a-product-number-nomenclature"></a>Skapa en nomenklatur för produktnummer

1. Gå till **Hantering av produktinformation \> Inställningar \> Produktnomenklatur**.
1. Välj **Ny**.
1. I fältet **Namn** anger du ett nomenklatursnamn som gör det enkelt att identifiera målproduktdimensionsgruppen, till exempel `ColorSize`.
1. I fältet **Beskrivning** anger du ett värde.
1. Markera **Lägg till**.
1. Välj **Produktmallsnummer**.
1. Markera **Lägg till**.
1. Välj **Textkonstant**.
1. Skriv ett värde i fältet **Text**.
1. Markera **Lägg till**.
1. Välj **Färg**.
1. Markera **Lägg till**.
1. Välj **Textkonstant**.
1. Skriv ett värde i fältet **Text**.
1. Markera **Lägg till**.
1. Välj **Storlek**.
1. Stäng sidan.

## <a name="assign-the-nomenclature-to-a-product-master"></a>Tilldela nummernomenklaturen till en produktmall

1. Välj **Produktdimensionsgrupper**.
2. Välj **produktdimensionsgruppen SizeCol**.
3. Välj **Redigera**.
4. Välj **Ja** i fältet **Använd nomenklatur**.
5. I fältet **Nomenklatur för produktvariantnummer**, ange eller välj ett värde.
6. Stäng sidan.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]