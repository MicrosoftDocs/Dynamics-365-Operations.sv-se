---
title: Skapa en produktnummernomenklatur för fördefinierade produktvarianter
description: Denna artikel visar dig hur du skapar en produktnummernomenklatur för fördefinierade produktvarianter, samt hur du tilldelar denna till lämplig produktdimensionsgrupp.
author: t-benebo
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductDimensionGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e77c8eabe1657f7fbfef71747627207dccff3b60
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8887324"
---
# <a name="create-a-product-number-nomenclature-for-predefined-product-variants"></a>Skapa en produktnummernomenklatur för fördefinierade produktvarianter

[!include [banner](../../includes/banner.md)]

Denna artikel visar dig hur du skapar en produktnummernomenklatur för fördefinierade produktvarianter, samt hur du tilldelar denna till lämplig produktdimensionsgrupp. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF. Den nya produktnummernomenklaturen tilldelas till produktdimensionsgruppen Color and Size. Den här uppgiften utförs vanligtvis av en produktdesigner.


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