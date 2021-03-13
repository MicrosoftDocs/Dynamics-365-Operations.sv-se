---
title: Hantera SEO-metadata
description: I det här avsnittet beskrivs hur du hanterar SEO-metadata (Search Engine Optimization) i Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: c7cf9e76ffb30ee5c8bba318b2644e67c757bff0
ms.sourcegitcommit: 872600103d2a444d78963867e5e0cdc62e68c3ec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/01/2021
ms.locfileid: "5097425"
---
# <a name="manage-seo-metadata"></a>Hantera SEO-metadata


[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du hanterar SEO-metadata (Search Engine Optimization) i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

SEO-metadata för en plats kan hanteras med hjälp av webbplatskartor och sidmetadata.
    
## <a name="site-maps"></a>Webbplatskartor

En webbplatskarta är en maskinläsbar lista, i XML-format, för sidorna på din webbplats. Den är avsedd att förbrukas av sökmotorer så att de kan ge bättre sökresultat från din webbplats. Webbplatskartor kan manuellt förtäras av sökmotorer eller publiceras i en robots.txt-fil.

Dynamics 365 Commerce stöder automatisk generering av webbplatsmappningar. Webbplatsmappningar uppdateras automatiskt när sidor publiceras och avpubliceras.

### <a name="turn-on-site-map-generation"></a>Aktivera generering av webbplatskarta

1. Logga in till redigeringsverktyget.
1. Under **Webbplatser**, välj **Fabrikam** (eller namnet på webbplatsen).
1. I navigeringsfönstret till vänster, välj **Platshantering**.
1. Kontrollera att alternativet **Webbplatskartor aktiverade** är aktiverat.

## <a name="page-metadata"></a>Metadata för sida

Dynamics 365 Commerce gör att du kan hantera SEO-metadata för enskilda sidor. Du kan visa och ändra denna information i avsnittet **SEO-egenskaper** i en sidbehållare. Följande egenskaper för SEO-metadata stöds:

- Rubrik
- Beskrivning
- SEO-nyckelord
- Aria-etiketter
- noindex
- nofollow
- noarchive
- nocache
- noOpenDirectoryProject
- nosnippet
- noImageIndex
- unavailableAfter

### <a name="modify-page-metadata"></a>Ändra metadata för sidan

Om du vill ändra metadata, följ dessa steg.

1. Under **Webbplatser**, välj **Fabrikam** (eller namet på webbplatsen).
1. I navigeringsfönstret till vänster, välj **sidor**.
1. Välj startsidan för att öppna den i sidredigeraren.
1. Klicka på **Redigera** i kommandofältet.
1. I fönstret Egenskaper till höger, visa **Standardmetataggar**.
1. Om du vill lägga till en ny metatagg väljer du **Lägg till** och anger sedan taggen i fältet. Om du vill ta bort en befintlig metatagg markerar du papperskorgen till höger om den.
1. Välj **spara** och välj sedan **Avsluta redigeringen**.
1. I fältet **kommentarer** anger du **Uppdaterade metataggar** och sedan **OK**.
1. Välj **Förhandsgranska** om du vill förhandsgranska din sida. När du är klar kan du stänga fliken förhandsgranskning och återgå till redigeringsverktyget.
1. Markera **Publicera**.

## <a name="additional-resources"></a>Ytterligare resurser

[Ändra en befintlig webbplatssida](modify-existing-page.md)

[Lägga till en ny webbplatssida](add-new-page.md)

[Välj sidlayouter](select-page-layouts.md)

[Spara, förhandsgranska och publicera en sida](save-preview-publish-page.md)

[Utöka en produktsida](enrich-product-page.md)

[Utöka en kategorilandningssida](enrich-category-page.md)

[Kontrollera tillgängligheten för sidinnehåll](verify-accessibility.md)

[Skapa dynamiska näthandelssidor baserade på URL-parametrar](create-dynamic-pages.md)
