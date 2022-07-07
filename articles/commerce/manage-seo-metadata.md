---
title: Hantera SEO-metadata
description: I denna artikel beskrivs hur du hanterar SEO-metadata (Search Engine Optimization) i Microsoft Dynamics 365 Commerce.
author: psimolin
ms.date: 04/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 99c28c2bff7b683f3e92dea4ba24d8bead556443
ms.sourcegitcommit: 6616b969afd6beb11a79d8e740560bf00016ea7f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2022
ms.locfileid: "9027319"
---
# <a name="manage-seo-metadata"></a>Hantera SEO-metadata

[!include [banner](includes/banner.md)]

I denna artikel beskrivs hur du hanterar SEO-metadata (Search Engine Optimization) i Microsoft Dynamics 365 Commerce.

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
1. I sidredigeraren, högst upp på sidkonturkontrollen till vänster, välj **Dispositionslägesalternativ** (växelsymbol) och välj **Avancerad dispositionsvy**.
1. Utvidga trädkontrollerna i huvudvyn så att innehållet på **HTML-huvud** visas.
1. I **HTML-huvud** plats, välj önskad SEO-modul (till exempel **Sidsammanfattning**, **Sammanfattning för produktsida**, **Sammanfattning av kategorisida** eller **Metataggar**).
1. I egenskapsrutan till höger, redigera önskad SEO-data för den valda SEO-modulen (till exempel, **Rubrik**, **Beskrivning** eller **Dela bild**).
1. Välj **spara** och välj sedan **Avsluta redigeringen**.
1. I fältet **kommentarer** anger du **Uppdaterade SEO-data** och sedan **OK**.
1. Välj **Förhandsgranska** om du vill förhandsgranska din sida. När du är klar kan du stänga fliken förhandsgranskning och återgå till redigeringsverktyget.
1. Markera **Publicera**.

> [!TIP]
> Författare kan använda alternativet **Dispositionslägesalternativ** (kugghjulssymbolen) överst på den vänstra konturkontrollen i sidredigeraren för att växla mellan **Grundläggande dispositionsvy** och **Avancerad dispositionsvy**. **Den grundläggande dispositionsvyn** är standardinställningen och filtrerar dispositionen så att endast moduler på **brödtext**-HTML-platsen visas för en sida. **Avancerad dispositionsvy** visar hela sidmodulen, inklusive **HTML-huvud**, **brödtextens början** och **brödtextens slut**. Denna vy är användbar när författare måste redigera specifika SEO- eller skriptmodulinställningar för en sida.

## <a name="additional-resources"></a>Ytterligare resurser

[Ändra en befintlig webbplatssida](modify-existing-page.md)

[Lägga till en ny webbplatssida](add-new-page.md)

[Välj sidlayouter](select-page-layouts.md)

[Spara, förhandsgranska och publicera en sida](save-preview-publish-page.md)

[Utöka en produktsida](enrich-product-page.md)

[Utöka en kategorilandningssida](enrich-category-page.md)

[Kontrollera tillgängligheten för sidinnehåll](verify-accessibility.md)

[Skapa dynamiska näthandelssidor baserade på URL-parametrar](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
