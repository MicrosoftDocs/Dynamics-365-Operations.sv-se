---
title: Lägga till en ny webbplatssida
description: I det här avsnittet beskrivs hur du lägger till en ny webbplatssida i Microsoft Dynamics 365 Commerce.
author: psimolin
ms.date: 02/03/2022
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
ms.openlocfilehash: e0c2a73ae9e85cb299e7cb6fc70562659cdfadc5
ms.sourcegitcommit: 1eef00796f7c5511f432b01800cdf8920992d7d5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/04/2022
ms.locfileid: "8090729"
---
# <a name="add-a-new-site-page"></a>Lägga till en ny webbplatssida

[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du lägger till en ny webbplatssida i Microsoft Dynamics 365 Commerce.

När du har skapat mallar och fragment för din webbplats, är nästa steg att börja skapa sidor som använder dem. Du måste välja en mall eller layout, ett sidnamn och en sidadress för att komma igång.

## <a name="template-or-layout"></a>Mall eller layout

Du kan använda antingen en mall eller en layout för den nya sidan. Mer information finns i [Översikt över mallar och layouter](templates-layouts-overview.md).

## <a name="specify-the-page-name"></a>Ange sidnamnet

Sidnamnet måste vara unikt för din webbplats och bör vara beskrivande så att du enkelt kan hitta det och andra vet vad sidan är avsedd för. Du kan byta namn på sidan senare genom att redigera den och sedan välja pennsymbolen bredvid sidnamnet i egenskapsfönstret.

## <a name="specify-the-page-url"></a>Ange sid-URL

Du kan välja att ange en URL för den nya sidan. När du skapar en sida kan du ange en sträng som ska användas för att skapa en fullständig URL. Den här strängen kallas för en relativ URL eller en URL-instruktion. En fullständig URL genereras sedan utifrån URL-instruktionen och den nya sidan tilldelas den. Du kan ändra URL-instruktionen senare innan du publicerar sidan. Mer information finns i [Skapa en sid-URL](create-page-URL.md).

> [!NOTE]
> Dynamics 365 Commerce kopplas från URL och innehåll. Med andra ord kan en sida skapas som inte är kopplad till en URL adress, och en URL kan skapas som inte är kopplad till en sida. Därför kan innehållsbyte ske för en URL-adress och det kräver inte driftstopp och omdirigeringar är enklare att hantera.

## <a name="add-a-new-page"></a>Lägga till en ny sida

Gör så här om du vill lägga till en ny webbplatssida till din webbplats:

1. Under **Webbplatser**, välj **Fabrikam** (eller namnet på webbplatsen).
1. Välj **Ny sida**.
1. I dialogrutan **Ny sida** väljer du en strukturlistemall och klickar på **OK**.
1. I fältet **Sidnamn** anger du ett sidnamn (till exempel **Min nya sida**).
1. I fältet **URL** anger du en sträng (URL-instruktion) för att slutföra URL:en (t.ex. **mynewpage**).
1. Välj **OK**. Sidredigeraren visas. Observera att ett sidhuvud och en sidfot läggs till automatiskt på sidan, baserat på den valda mallen.
1. I siddispositionen väljer du platsen **Huvud**, markerar ellipsknappen (**...**) och väljer sedan **Lägg till modul**.
1. Välj **Behållare** och välj sedan **OK**.
1. Markera knappen med punkter för **vätskebehållare** och välj sedan **Lägg till modul**.
1. Välj **Innehållsrikt block** och välj sedan **OK**.
1. Markera knappen med punkter för **Innehållsrikt block** och välj sedan **Lägg till modul**.
1. Välj **Artikeln innehållsrikt block** och välj sedan **OK**.
1. I egenskapsrutan till höger, välj **Paragraf** och ange sedan **Min testtext** i fältet.
1. Välj **spara** och välj sedan **Avsluta redigeringen**.
1. I fältet **kommentarer** anger du **Ny sida tillagd** och sedan **OK**.
1. Välj **Förhandsgranska** om du vill förhandsgranska din sida. När du är klar kan du stänga fliken förhandsgranskning och återgå till redigeringsverktyget.
1. Markera **Publicera**.
1. I navigeringssökvägen (navigeringssökvägar), välj **Fabrikam** (eller namnet på platsen).
1. I navigeringsfönstret till vänster, välj **URL:er**.
1. Hitta och välj din URL (**mynewpage**) i listan.
1. Markera **Publicera**.

## <a name="additional-resources"></a>Ytterligare resurser

[Ändra en befintlig webbplatssida](modify-existing-page.md)

[Välj sidlayouter](select-page-layouts.md)

[Hantera SEO-metadata](manage-seo-metadata.md)

[Spara, förhandsgranska och publicera en sida](save-preview-publish-page.md)

[Utöka en produktsida](enrich-product-page.md)

[Utöka en kategorilandningssida](enrich-category-page.md)

[Kontrollera tillgängligheten för sidinnehåll](verify-accessibility.md)

[Skapa dynamiska näthandelssidor baserade på URL-parametrar](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
