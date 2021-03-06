---
title: Skapa en variantgrupp
description: I det här avsnittet beskrivs hur du skapar en variantgrupp för storlek, format eller färg för en produkt i Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailSizeGroupTable, ConfigGroupIdLookup, RetailStyleGroupTable
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 0462958d8225de145a8d886b096f96cd3f2cb5c5
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799551"
---
# <a name="create-a-variant-group"></a>Skapa en variantgrupp


[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du skapar en variantgrupp för storlek, format eller färg för en produkt i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

Dynamics 365 Commerce stöder flera varianter av produkter. Det är idealiskt att ställa in variantkoder för olika produktkategorier. En storleksgrupp kan till exempel skapas för t-shirts med storlekar som är extra small, small, medium, large och extra large eller en färggrupp som innehåller alla tillgängliga färger för en produkt. Du bör lägga till variantgrupper innan produkter läggs till.

I det här avsnittet skapas och konfigureras en storleksgrupp. Liknande procedurer kan användas för att lägga till och konfigurera stilgrupper och färggrupper.

## <a name="create-a-size-group"></a>Skapa en storleksgrupp

Gör så här om du vill skapa en storleksgrupp.
 
1. I Navigeringsfönstret, gå till **Moduler \> Butik och handel \> Produkter och kategorier \> Variantgrupper \> Storleksgrupper**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. I rutan **Stoleksgrupp**, ange ett namn för storleksgruppen.
1. I rutan **beskrivning** ange en lämplig beskrivning.
1. Klicka på **Spara** i åtgärdsfönstret.

## <a name="add-attributes-to-the-size-group"></a>Lägga till attribut i storleksgruppen

Följ dessa steg om du vill lägga till attribut till en storleksgrupp.

1. I Navigeringsfönstret, gå till **Moduler \> Butik och handel \> Produkter och kategorier \> Variantgrupper \> Storleksgrupper**
1. Välj en storleksgrupp i navigeringsfönstret.
1. Under **Stoleksgrupprader**, välj **Lägg till**.
1. I rutan **Stolek**, ange en sträng som representerar storleken (till exempel "XL").
1. Ange ett **Storleksnamn** för storleken (till exempel "Extra Large").
1. I rutan **Lagerpåfyllnadsvikt** ange ett nummer som representerar lagerpåfyllnadsvikt.
1. I rutan **Tal i streckkod** anger du ett tal som representerar streckkoden.
1. I rutan **Visningsordning**, ange ett nummer som representerar visningsordningen.
1. När du har lagt till alla storlekar väljer du **Spara** i åtgärdsfönstret.

I bilden nedan visas ett exempel på en storleksgrupp för "storlekar på vardagsskjortor".

![Skapa storleksgrupp](media/create-variant-group.png)

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över produktinformation](../supply-chain/pim/product-information.md?toc=/dynamics365/commerce/toc.json)

[Ställa in butiksprodukter](set-up-retail-products.md)

[Produktdimensioner](../supply-chain/pim/product-dimensions.md?toc=/dynamics365/commerce/toc.json)


[!INCLUDE[footer-include](../includes/footer-banner.md)]