---
title: Skapa en produktnummernomenklatur för konfigurerade produktvarianter
description: I den här proceduren visas hur du ställer in en produktnummernomenklatur för konfigurerade produktvarianter, och hur denna kan kopplas till en konfigurerbar produktmall.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, EcoResNomenclature, EcoResProductListPage, EcoResProductDetails, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7ea30dc107213b1a2c6b2a109188066a6ea82159
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921021"
---
# <a name="create-a-product-number-nomenclature-for-configured-product-variants"></a>Skapa en produktnummernomenklatur för konfigurerade produktvarianter

[!include [banner](../../includes/banner.md)]

I den här proceduren visas hur du ställer in en produktnummernomenklatur för konfigurerade produktvarianter, och hur denna kan kopplas till en konfigurerbar produktmall. I den här proceduren visas även hur du kan skapa en konfigurationsnomenklatur för en modellkomponent för en produktkonfiguration. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF. Den nya produktnummernomenklaturen tilldelas produktmallen D0004. Den här uppgiften utförs vanligtvis av en produktdesigner.

## <a name="create-a-product-number-nomenclature"></a>Skapa en nomenklatur för produktnummer

1. Gå till **Hantering av produktinformation \> Inställningar \> Produktnomenklatur**.
1. Välj **Ny**.
1. Skriv ett värde i fältet **Namn**.
1. I fältet **Beskrivning** anger du ett värde.
1. Markera **Lägg till**.
1. Välj **Produktmallsnummer**.
1. Markera **Lägg till**.
1. Välj **Textkonstant**.
1. Markera vald rad i listan.
1. Skriv ett värde i fältet **Text**.
1. Markera **Lägg till**.
1. Välj **Konfiguration**.
1. Stäng sidan.

## <a name="assign-the-product-number-nomenclature-to-a-product-master"></a>Tilldela produktnummernomenklaturen till en produktmall

1. Gå till **Hantering av produktinformation \> Produkter \> Produktmallar**.
1. Använd snabbfiltret för att söka efter poster. Filtrera till exempel på fältet **Produktnummer** med värdet "D".
1. Klicka på länken på önskad rad i valda listan.
1. Välj **Redigera**.
1. Välj *Ja* i fältet **Använd nomenklatur**.
1. I fältet **Nomenklatur för produktvariantnummer**, ange eller välj ett värde.
1. Stäng sidan.
1. Stäng sidan.

## <a name="create-nomenclature-for-a-product-configuration-model-component"></a>Skapa en nomenklatur för en komponent i en produktkonfigurationsmodell

1. Gå till **Produktinformationshantering \> Produkter \> Produktkonfigurationsmodeller**.
1. Hitta och markera önskad post i listan.
1. Klicka på länken på önskad rad i valda listan.
1. Välj **Redigera**.
1. Välj *Ja* i fältet **Använd konfigurationsnomenklatur**.
1. Markera **Lägg till**.
1. Välj **Attributvärde**.
1. Markera vald rad i listan.
1. I fältet **Attribut** anger eller väljer du ett värde.
1. Markera **Lägg till**.
1. Välj **Textkonstant**.
1. Markera vald rad i listan.
1. Skriv ett värde i fältet **Text**.
1. Markera **Lägg till**.
1. Välj **Attributvärde**.
1. Markera vald rad i listan.
1. I fältet **Attribut** anger eller väljer du ett värde.
1. Markera **Lägg till**.
1. Välj **Textkonstant**.
1. Markera vald rad i listan.
1. Skriv ett värde i fältet **Text**.
1. Markera **Lägg till**.
1. Välj **Attributvärde**.
1. Markera vald rad i listan.
1. I fältet **Attribut** anger eller väljer du ett värde.
1. Markera **Lägg till**.
1. Välj **Textkonstant**.
1. Markera vald rad i listan.
1. Skriv ett värde i fältet **Text**.
1. Markera **Lägg till**.
1. Välj **Attributvärde**.
1. Markera vald rad i listan.
1. I fältet **Attribut** anger eller väljer du ett värde.
1. Markera **Lägg till**.
1. Välj **Textkonstant**.
1. Markera vald rad i listan.
1. Skriv ett värde i fältet **Text**.
1. Markera **Lägg till**.
1. Välj **Nummerserievärde**.
1. Markera vald rad i listan.
1. I fältet **Nummerserie** anger eller väljer du ett värde.
1. Stäng sidan.
1. Stäng sidan.
1. Stäng sidan.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]