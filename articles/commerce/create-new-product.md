---
title: Skapa en ny produkt
description: I det här avsnittet beskrivs hur du skapar en ny produkt i Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 356bf91b2a946e7c0f5d5af9e2fe0b64342b856e
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/01/2020
ms.locfileid: "3001977"
---
# <a name="create-a-new-product"></a>Skapa en ny produkt


[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du skapar en ny produkt i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

En produkt definieras i första hand med hjälp av ett produktnummer, ett namn och en beskrivning. Andra data är också nödvändiga för att beskriva en produkt eller tjänst:

## <a name="create-a-new-product"></a>Skapa en ny produkt

1. I navigeringsfönstret, gå till **Moduler \> Butik och handel \> Produkter och kategorier \> Produkter per kategori**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. I listrutan **Produkttyp**, välj antingen **Objekt** eller **Tjänst**.
1. I listrutan **Delprodukttyp**, välj antingen **Produkt** (om produkten inte har några varianter) eller **Produktmall** (om produkten har varianter).
1. I rutan **produktnummer** ange ett produktnummer om ett inte redan är förifyllt.
1. I rutan **Produktnamn** anger du ett produktnamn.
1. I rutan **Söknamn**, ange ett söknamn.
1. I listrutan **Butikskategori**, välj en lämplig kategori.
1. Om produkten är ett paket, välj **Ja** för **Produktpaket**.
1. Om undertypen för produkt är produktmall ställer du in **produktdimensionsgrupp** så att de varianter som stöds inkluderas. Alternativ inkluderar **färg**, **storlek**, **utförande** och **konfiguration**. Du kan behöva skapa ytterligare produktdimensionsgrupper om det behövs.
1. I listrutan **Konfigurationsteknik**, välj ett lämpligt alternativ.
1. Välj **OK**.

Följande bild visar en exempelprodukt som läggs till.

![Skapa en produkt](media/create-new-product.png)

När en produkt har lagts till kan ytterligare data ställas in för den, t.ex. **produktbeskrivning**, **variantgrupper**, **dimensionsgrupper**, **produktattribut** och **relaterade produkter**.

Följande bild visar en produkts ytterligare information.

![Produktdetaljer](media/create-new-product-2.png)

### <a name="create-product-variants"></a>Skapa produktvarianter

Om undertypen för produkt är **produktmall** måste specifika varianter skapas. 

Följ dessa steg för att skapa en produktvariant.

1. Välj **Produktvarianter** i åtgärdsfönstret.
1. Om variantgrupper har valts i åtgärdsfönstret väljer du **variantförslag*.
1. Välj vilka varianter du vill stödja för produkten.
1. Markera **Skapa**.

## <a name="release-a-product"></a>Frisläpp en produkt

Om du vill sälja en produkt måste den först frisläppas till en juridisk person.

1. Välj **frisläppta produkter** på sidan produkt.

    ![Frisläpp produkt](media/create-new-product-3.png)

1. Välj produkten som ska frisläppas och välj sedan **nästa**.

    ![Välj produkt som ska frisläppas](media/create-new-product-4.png)

1. Välj uppsättningen med produktvarianter som ska frisläppas och välj sedan **nästa**.

    ![Välj varianter som ska frisläppas](media/create-new-product-5.png)

1. Välj den juridiska personen och välj sedan **Nästa**.

    ![Välj juridisk person](media/create-new-product-6.png)

1. Välj **Slutför**.

    ![Slutför produktfrisläppning](media/create-new-product-7.png)

## <a name="configure-a-released-product"></a>Konfigurera en frisläppt produkt

När en produkt har frisläppts kräver den ytterligare konfiguration som omfattar att lägga till ett pris för produkten.

1. I Navigeringsfönstret, gå till **Moduler \> Butik och handel \> Produkter och kategorier \> Frisläppta produkter per kategori**.
1. Välj nod för produktkategori för produkten som släpptes och välj sedan produkten i produktlistan.
1. Klicka på **Redigera** i åtgärdsfönstret.
1. I avsnittet **inköp** konfigurerar du alla obligatoriska egenskaper inklusive **enhet**, **pris** och **kvantitet**.
1. Välj **validera** i åtgärdsfönstret för att se till att inga fel rapporteras för saknade fält.
1. Klicka på **Spara** i åtgärdsfönstret.

Följande bild visar ett exempel på en konfiguration för en frisläppt produkt.

![Konfigurera en frisläppt produkt](media/create-new-product-8.png)

## <a name="additional-resources"></a>Ytterligare resurser

[Skapa juridiska personer](channels-legal-entities.md)

[Skapa en variantgrupp](create-variant-group.md) 
