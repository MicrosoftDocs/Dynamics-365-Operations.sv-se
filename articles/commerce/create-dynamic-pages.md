---
title: Skapa dynamiska näthandelssidor baserade på URL-parametrar
description: I denna artikel beskrivs hur du konfigurerar en Microsoft Dynamics 365 Commerce-näthandelssida som kan betjäna dynamiskt innehåll baserat på URL-parametrar.
author: bicyclingfool
ms.date: 05/27/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: stuharg
ms.search.validFrom: 2019-09-30
ms.openlocfilehash: 718bc099347f2924b299ccd4562d9d7055c43187
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9282887"
---
# <a name="create-dynamic-e-commerce-pages-based-on-url-parameters"></a>Skapa dynamiska näthandelssidor baserade på URL-parametrar

[!include [banner](includes/banner.md)]

I denna artikel beskrivs hur du konfigurerar en Microsoft Dynamics 365 Commerce-näthandelssida som kan betjäna dynamiskt innehåll baserat på URL-parametrar.

En näthandelssida kan konfigureras till att använda olika typer av innehåll, baserat på ett segment i URL-sökvägen. Därför kallas sidan för en "dynamisk" sida. Segmentet används som en parameter för att hämta sidinnehållet. Till exempel en sida som skapas i webbplatsskaparen och namnges **blogg\_visningsprogram** blir mappade till URL `https://fabrikam.com/blog`. Denna sida kan sedan användas för att visa annat innehåll, baserat på det sista segmentet i URL-sökvägen. Det sista segmentet i webbadressen (URL) `https://fabrikam.com/blog/article-1` är **artikel-1**.

Du kan också åsidosätta ett parameteriserat URL-segment med en sida för webbplatsskaparen. Till exempel en sida som skapas i webbplatsskaparen och namnges **blogg\_sammanfattning** blir mappade till URL `https://fabrikam.com/blog/about-this-blog`. När `https://fabrikam.com/blog` URL begärs med `/about-this-blog` segment i slutet returneras sidinnehållet **blogg\_sammanfattning** istället för `/about-this-blog` segment tolkas som en parameter som ska användas av sidan `https://fabrikam.com/blog`. 

När du väljer namn för parametrarna som ska skickas till den dynamiska sidan, kan namnet på den dynamiska sidan som visas i URL (`/blog` i exemplet ovan) inte användas som ett parameternamn eller en del av ett parameternamn. 

> [!NOTE]
> Funktionerna för värd, hämtning och visning av dynamiskt sidinnehåll implementeras med hjälp av en anpassad modul. Mer information finns i [Utbyggbarhet för onlinekanal](e-commerce-extensibility/overview.md).

## <a name="set-up-a-dynamic-e-commerce-page"></a>Ställa in en dynamisk sida för näthandel

Om du vill konfigurera en dynamisk näthandelssida måste du skapa den dynamiska sidan, skapa bas-webbadressen (URL) och konfigurera flödet till den dynamiska sidan.

### <a name="create-the-page-that-will-serve-dynamic-content"></a>Skapa sidan som ska användas för dynamiskt innehåll

Följ stegen i [Lägg till en ny webbplatssida](add-new-page.md) om du vill skapa en sida som använder dynamiskt innehåll. Den sida du skapar kräver implementering av en modul där det sista segmentet i URL-sökvägen används för att hämta innehåll från en extern datakälla. Mer information om anpassad modulutveckling finns i [Utvidgningar av onlinekanaler](e-commerce-extensibility/overview.md).

### <a name="create-the-base-url-for-the-dynamic-page"></a>Skapa bas-URL för den dynamiska sidan

Skapa bas-URL för den dynamiska sidan i Commerce-webbplatsverktyget genom att följa dessa steg.

1. Gå till **URLs** och välj sedan **Ny \> Ny URL**.
1. I dialogrutan **Skapa ny URL** väljer du **Intern sida**. Under **URL-sökväg** anger du den sökväg som ska fungera som rot för den dynamiska sidan (i detta exempel **/blog**). Välj sedan **Nästa**.
1. I dialogrutan **Välj en sida** väljer du den sida som du skapade som dynamisk sida innan du väljer **Spara**.
1. Markera **Publicera**.

### <a name="configure-the-route-to-the-dynamic-page"></a>Konfigurera flödet till den dynamiska sidan

Följ dessa steg om du vill konfigurera flödet till den dynamiska sidan i Commerce-webbplatsverktyget.

1. Gå till **Webbplatsinställningar \> Tillägg**.
1. Under **PParameteriserade URL-sökvägar** väljer du **Lägg till** och anger sedan den URL-sökväg som du angav när du skapade URL:en (i detta exempel **/blog**).
1. Välj **Spara och publicera**.

När flödet har konfigurerats kommer alla förfrågningar till den parameteriserade URL-sökvägen att returnera den sida som är kopplad till URL:en. Om en begäran innehåller ytterligare ett segment returneras den associerade sidan, och sidinnehållet hämtas med segmentet som en parameter. Till exempel kommer `https://fabrikam.com/blog/article-1` returnera sidan `https://fabrikam.com/blog` som visar innehållet som den hämtade med hjälp av parameter **/artikel-1**.

## <a name="override-a-parameterized-url-with-a-custom-page"></a>Åsidosätta en parameteriserad URL med en anpassad sida

Om du vill åsidosätta en parameteriserad URL med en anpassad sida i Commerce-webbplatsverktyget gör du så här.

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
