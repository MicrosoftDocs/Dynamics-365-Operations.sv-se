---
title: Lägga till en ny webbplatssida
description: I det här avsnittet beskrivs hur du lägger till en ny webbplatssida i Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: b0f1e290526c25aa6e6300c65e24044a325bee53
ms.sourcegitcommit: 7a1d01122790b904e2d96a7ea9f1d003392358a6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/17/2020
ms.locfileid: "3269968"
---
# <a name="add-a-new-site-page"></a>Lägga till en ny webbplatssida


[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du lägger till en ny webbplatssida i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

När du har skapat mallar och fragment för din webbplats, är nästa steg att börja skapa sidor som använder dem. Du måste välja en mall eller layout, ett sidnamn och en sidadress för att komma igång.

## <a name="template-or-layout"></a>Mall eller layout

Du kan använda antingen en mall eller en layout för den nya sidan. Mer information finns i [Översikt över mallar och layouter](templates-layouts-overview.md).

## <a name="page-name"></a>Sidnamn

Sidnamnet måste vara unikt för sidan. Den ska vara beskrivande, så att du lätt kan hitta den och andra personer som vet vad sidan är avsedd för. Välj ett sidnamn noggrant eftersom det inte kan ändras vid ett senare tillfälle.

## <a name="page-url"></a>Sid-URL

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
1. Välj **Behållare**och välj sedan **OK**.
1. Markera knappen med punkter för **vätskebehållare** och välj sedan **Lägg till modul**.
1. Välj **Innehållsrikt block** och välj sedan **OK**.
1. Markera knappen med punkter för **Innehållsrikt block** och välj sedan **Lägg till modul**.
1. Välj **Artikeln innehållsrikt block** och välj sedan **OK**.
1. I egenskapsrutan till höger, välj **Paragraf** och ange sedan **Min testtext** i fältet.
1. Välj **spara**och välj sedan **Avsluta redigeringen**.
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
