---
title: Tillgångstillverkare och-modeller
description: Det här avsnittet förklarar hur du ställer in tillgångstillverkare och relaterade modeller i Tillgångshantering.
author: johanhoffmann
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetProductLookup, EntAssetModelLookup, EntAssetProduct
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 80fcb493d96209d78f842414c198a8275e4818ba365759466034faf5f3405540
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6739908"
---
# <a name="asset-manufacturers-and-models"></a>Tillgångstillverkare och-modeller

[!include [banner](../../includes/banner.md)]

 

Det här avsnittet förklarar hur du ställer in tillgångstillverkare och relaterade modeller i Tillgångshantering. Modeller kan relateras till tillgångstyper.

## <a name="set-up-product-model-relations"></a>Ställ in produktmodellrelationer

1. Välj **Tillgångshantering** \> **Inställning** \> **Tillgångar** \> **Tillverkare och modell**.
2. Skapa en ny produkt genom att välja **Nytt**.
3. I fältet **tillverkare**,ange ett namn för tillgångstillverkaren.
4. Ange en beskrivning i fältet **beskrivning**.
5. På snabbfliken **Modeller** väljer du **Lägg till** för att skapa en tillgångsmodell som ska relateras till tillgångstillverkaren.
6. I fältet **Modell**,ange ett namn för tillgångsmodellen.
7. Ange en beskrivning i fältet **beskrivning**.
8. I fältet **tillgångstyp** väljer du den tillgångstyp som tillverkarmodellen ska relateras till.

    > [!NOTE]
    > Du kan också ställa in relationer för tillgångstyper, tillverkare och modeller i sökningen **tillgångstyper**. Mer information finns i [Tillgångstyper](../setup-for-objects/object-types.md).

    På snabbfliken **Detaljer** visar fältet **Modeller** antalet tillgångsmodeller som har ställts in på den valda tillgångstillverkaren. Fältet **tillgångar** visar antalet tillgångar som använder den valda tillverkaren.
    
    Fältet **tillgångar** visar antalet objekt som använder den valda tillverkarmodellen.

> [!NOTE]
> En tillgångstyp kan inte ha någon modellrelation för tillgångstillverkare, den kan relateras till en modell för tillgångstillverkare, eller så kan den relateras till flera tillgångstillverkares modeller. Om en tillgångstyp är relaterad till minst en tillverkarmodell, kan endast de kombinationer som har ställts in i sökningen **Tillverkarmodell** väljas på dessa tillgångshanteringssidor där en kombination av en tillgångstyp, tillverkare och modell kan ställas in. Dessa sidor innehåller **Alla tillgångar**, **servicenivåer för tillgång**, **standarder för jobbtyp** och **budgetrader för underhåll**. Om vissa tillgångstyper inte är relaterade till någon tillverkarmodell visas endast de tillgångstyper och tillverkarmodeller som också har någon relation till tillgångstyper på sidorna.

## <a name="select-a-manufacturer-and-model-on-an-object"></a>Välja en tillverkare och modell på ett objekt

1. Välj **Tillgångshantering** \> **Allmänt** \> **Tillgångar** \> **Alla tillgångar**
2. I kolumnen **tillgång**, välj länken för tillgången. Sidan **Detaljer** visas.
3. Välj **Redigera**.
4. På snabbfliken **allmänt** väljer du värden i fälten **tillverkare** och **modell**.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]