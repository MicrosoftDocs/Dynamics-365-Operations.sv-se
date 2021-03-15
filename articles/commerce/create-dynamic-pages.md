---
title: Skapa dynamiska näthandelssidor baserade på URL-parametrar
description: I detta ämne beskrivs hur du ställer in en Microsoft Dynamics 365 Commerce-näthandelssida som kan använda dynamiskt innehåll baserat på URL-parametrar.
author: StuHarg
manager: AnnBe
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ROBOTS: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.author: stuharg
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: e72b738133b396848848d167cace80fe23694334
ms.sourcegitcommit: 872600103d2a444d78963867e5e0cdc62e68c3ec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/01/2021
ms.locfileid: "5098649"
---
# <a name="create-dynamic-e-commerce-pages-based-on-url-parameters"></a>Skapa dynamiska näthandelssidor baserade på URL-parametrar

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

I detta ämne beskrivs hur du ställer in en Microsoft Dynamics 365 Commerce-näthandelssida som kan använda dynamiskt innehåll baserat på URL-parametrar.

En näthandelssida kan konfigureras till att använda olika typer av innehåll, baserat på ett segment i URL-sökvägen. Därför kallas sidan för en "dynamisk" sida. Segmentet används som en parameter för att hämta sidinnehållet. En sida kallad **blog\_viewer** skapas exempelvis och kopplas till webbadressen (URL) `https://fabrikam.com/blog`. Denna sida kan sedan användas för att visa annat innehåll, baserat på det sista segmentet i URL-sökvägen. Det sista segmentet i webbadressen (URL) `https://fabrikam.com/blog/article-1` är **artikel-1**.

Separata anpassade sidor som åsidosätter den dynamiska sidan kan också associeras med segment i URL-sökvägen. En sida kallad **blog\_summary** skapas exempelvis och kopplas till webbadressen (URL) `https://fabrikam.com/blog/about-this-blog`. När denna URL begärs kommer den **blog\_summary**-sida som associeras med **/about-this-blog**-parametern att returneras istället för **blog\_viewer**-sidan.

> [!NOTE]
> Funktionerna för värd, hämtning och visning av dynamiskt sidinnehåll implementeras med hjälp av en anpassad modul. Mer information finns i [Utbyggbarhet för onlinekanal](e-commerce-extensibility/overview.md).

## <a name="set-up-a-dynamic-e-commerce-page"></a>Ställa in en dynamisk sida för näthandel

Om du vill konfigurera en dynamisk e-handelssida måste du skapa den dynamiska sidan, skapa bas-webbadressen (URL) och konfigurera flödet till den dynamiska sidan.

### <a name="create-the-page-that-will-serve-dynamic-content"></a>Skapa sidan som ska användas för dynamiskt innehåll

Följ stegen i [Lägg till en ny webbplatssida](add-new-page.md) om du vill skapa en sida som använder dynamiskt innehåll. Den sida du skapar kräver implementering av en modul där det sista segmentet i URL-sökvägen används för att hämta innehåll från en extern datakälla. Mer information om anpassad modulutveckling finns i [Utvidgningar av onlinekanaler](e-commerce-extensibility/overview.md).

### <a name="create-the-base-url-for-the-dynamic-page"></a>Skapa bas-URL för den dynamiska sidan

Skapa bas-URL för den dynamiska sidan i Commerce-webbplatsbyggaren genom att följa dessa steg.

1. Gå till **URLs** och välj sedan **Ny \> Ny URL**.
1. I dialogrutan **Skapa ny URL** väljer du **Intern sida**. Under **URL-sökväg** anger du den sökväg som ska fungera som rot för den dynamiska sidan (i detta exempel **/blog**). Välj sedan **Nästa**.
1. I dialogrutan **Välj en sida** väljer du den sida som du skapade som dynamisk sida innan du väljer **Spara**.
1. Markera **Publicera**.

### <a name="configure-the-route-to-the-dynamic-page"></a>Konfigurera flödet till den dynamiska sidan

Följ dessa steg om du vill konfigurera flödet till den dynamiska sidan i Commerce-webbplatsbyggaren.

1. Gå till **Webbplatsinställningar \> Tillägg**.
1. Under **PParameteriserade URL-sökvägar** väljer du **Lägg till** och anger sedan den URL-sökväg som du angav när du skapade URL:en (i detta exempel **/blog**).
1. Välj **Spara och publicera**.

När flödet har konfigurerats kommer alla förfrågningar till den parameteriserade URL-sökvägen att returnera den sida som är kopplad till URL:en. Om en begäran innehåller ytterligare ett segment returneras den associerade sidan, och sidinnehållet hämtas med segmentet som en parameter. `https://fabrikam.com/blog/article-1` kommer exempelvis att returnera sidan **blog\_summary**, och sidinnehållet kommer att hämtas genom att använda parametern **/article-1**.

## <a name="override-a-parameterized-url-with-a-custom-page"></a>Åsidosätta en parameteriserad URL med en anpassad sida

Om du vill åsidosätta en parameteriserad URL med en anpassad sida i Commerce-webbplatsbyggaren gör du så här.

1. Gå till **URLs** och välj sedan **Ny \> Ny URL**.
1. I dialogrutan **Skapa ny URL** väljer du **Intern sida**. Under **URL-sökväg** anger du den sökväg som omfattar det segment som ska åsidosättas (i detta exempel **/blog/about-this-blog**). Välj sedan **Nästa**.
1. I dialogrutan **Välj en sida** väljer du den anpassade sidan och sedan **Spara**.
1. Markera **Publicera**.
1. Om den anpassade sidan ännu inte har publicerats går du till **Sidor** pch väljer den anpassade sidan och sedan **Publicera**.

När den anpassade sidan har publiceras visas den istället för den dynamiska sidan som har parameteriserat innehåll.

## <a name="additional-resources"></a>Ytterligare resurser

[Ändra en befintlig webbplatssida](modify-existing-page.md)

[Lägga till en ny webbplatssida](add-new-page.md)

[Välj sidlayouter](select-page-layouts.md)

[Hantera SEO-metadata](manage-seo-metadata.md)

[Spara, förhandsgranska och publicera en sida](save-preview-publish-page.md)

[Utöka en produktsida](enrich-product-page.md)

[Utöka en kategorilandningssida](enrich-category-page.md)

[Kontrollera tillgängligheten för sidinnehåll](verify-accessibility.md)

[Utbyggbarhet för onlinekanal](e-commerce-extensibility/overview.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]