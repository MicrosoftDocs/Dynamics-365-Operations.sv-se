---
title: Spara, förhandsgranska och publicera en sida
description: I det här avsnittet beskrivs hur du sparar, förhandsgranskar och publicerar en sida i Microsoft Dynamics 365 Commerce.
author: psimolin
ms.date: 04/14/2020
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
ms.openlocfilehash: 593c68e0934fa62d09c64b8d5d681697c3fb053ae6f4641ce2ae3104a03e0fba
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6718683"
---
# <a name="save-preview-and-publish-a-page"></a>Spara, förhandsgranska och publicera en sida

[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du sparar, förhandsgranskar och publicerar en sida i Microsoft Dynamics 365 Commerce.

## <a name="save-a-page"></a>Spara en sida

Om du vill spara en sida måste du ha checkat ut den till dig själv och öppnat den i sidredigeraren. För att checka ut en sida, välj **Redigera** i kommandofältet. När du har redigerat en sida bör du omedelbart spara den för att se till att dina ändringar lagras.

När du sparar en sida är ändringarna bara synliga för dig. Åtgärden Spara är i första hand avsedd att spara ändringar medan sidan inte är klar att checkas in. När du har ändrat sidan rekommenderar vi att du checkar in den, så att ändringarna blir synliga för andra. Vid den punkten kan du även checka ut sidan av andra användare som måste ändra den.

## <a name="preview-a-page"></a>Förhandsgranska en sida

I utvecklingsverktyget finns två typer av förhandsgranskningsfunktioner: visuell sidskapare som är "vad du ser är vad du får" (WYSIWYG) i sidredigeraren och ett separat förhandsgranskningsfönster.

Medan du använder sidredigeraren visas förhandsgranskningen "vad du ser är vad du få" (WYSIWYG) i mittenfönstret. Den här förhandsgranskningen uppdateras automatiskt när du sparar sidan. Du kan också uppdatera den manuellt genom att välja **uppdatera** i kommandofältet. Förhandsgranskningen visar sidan precis som användarna ser den, men redigeringshjälpare visas ovanpå den.

När du är klar med ändringarna av sidan kanske du vill förhandsgranska den för att se vad kunderna kommer att se. Om du vill förhandsgranska en sida väljer du **förhandsgranska** i kommandofältet. Förhandsgranskningen visas i ett separat webbläsarfönster. Sidan i förhandsgranskningsfönstret återges på samma sätt som webbplatsens användare kommer att se den. Du kan ändra storlek på fönstret för att säkerställa att alla tillgängliga moduler visas korrekt i alla visningsportar.

> [!NOTE]
> Autentisering och korrekta behörigheter krävs för att förhandsgranska opublicerat innehåll. Om du till exempel delar URL:en för förhandsgranskningen med någon måste personen ha rätt behörigheter för att få åtkomst till innehållet.

## <a name="publish-a-page"></a>Publicera en sida

När sidan är klar är nästa steg att publicera den, så att externa användare kan visa innehållet. Innan du kan publicera en sida måste du checka in den genom att välja **Slutför redigering** i kommandofältet.

Du kan publicera och avpublicera sidor från antingen sidpanelen eller sidredigeraren. Sidkontrollen visar en lista över sidor och tillåter massåtgärder. Sidredigeraren kan bara användas för att publicera eller avpublicera den enda sida som är öppen i den.

Om du vill publicera en eller flera sidor från sidpanelen markerar du sidorna, kontrollerar att de är incheckade och väljer sedan **publicera** i kommandofältet. Sidorna publiceras och du får ett meddelande om åtgärden i redigeringsverktyget.

Om du vill publicera en enskild sida från sidredigeraren är proceduren densamma. När sidan är öppen i sidredigeraren kontrollerar du att den har checkats in och väljer sedan **publicera** i kommandofältet. Sida publiceras och du får ett meddelande om åtgärden.

När du publicerar en sida publiceras bara sidans innehåll. Du och andra användare kan gå till sidan och visa den först när en URL har associerats till den. URL:en måste publiceras separat.

> [!IMPORTANT]
> Innan du kan publicera en sida måste alla bilder eller fragment som sid referenserna redan ha publicerats på.

## <a name="save-preview-and-publish-a-home-page"></a>Spara, förhandsgranska och publicera en startsida

Om du vill spara, förhandsgranska och publicera en startsida följer du stegen nedan.

1. Under **Webbplatser**, välj **Fabrikam** (eller namnet på webbplatsen).
1. I navigeringsfönstret till vänster, välj **sidor**.
1. Sök och välj startsidan för att öppna den i sidredigeraren.
1. Välj **Redigera**.
1. Ändra sidan efter behov.
1. Välj **spara** och välj sedan **Avsluta redigeringen**.
1. I fältet **kommentarer** anger du en notering om de ändringar som du har gjort och väljer sedan **OK**.
1. Välj **Förhandsgranska** om du vill förhandsgranska din sida. När du är klar kan du stänga fliken förhandsgranskning och återgå till redigeringsverktyget.
1. Markera **Publicera**.

## <a name="publish-a-url"></a>Publicera en URL

Gör så här om du vill publicera en URL.

1. Under **Webbplatser**, välj **Fabrikam** (eller namnet på webbplatsen).
1. I navigeringsfönstret till vänster, välj **URL:er**.
1. Hitta och markera den URL som du vill publicera.
1. Klicka på **publicera** i kommandofältet.

## <a name="additional-resources"></a>Ytterligare resurser

[Ändra en befintlig webbplatssida](modify-existing-page.md)

[Lägga till en ny webbplatssida](add-new-page.md)

[Välj sidlayouter](select-page-layouts.md)

[Hantera SEO-metadata](manage-seo-metadata.md)

[Utöka en produktsida](enrich-product-page.md)

[Utöka en kategorilandningssida](enrich-category-page.md)

[Kontrollera tillgängligheten för sidinnehåll](verify-accessibility.md)

[Skapa dynamiska näthandelssidor baserade på URL-parametrar](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]