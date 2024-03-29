---
title: Ändra en befintlig webbplatssida
description: I denna artikel beskrivs hur du ändrar en befintlig webbplatssida i Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: fb5348c2f29625647f06e48233f877a847677486
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9286929"
---
# <a name="modify-an-existing-site-page"></a>Ändra en befintlig webbplatssida

[!include [banner](includes/banner.md)]

I denna artikel beskrivs hur du ändrar en befintlig webbplatssida i Microsoft Dynamics 365 Commerce.

När du måste ändra en sida är det första steget att öppna det i sidredigeraren. Gå till den webbplats som innehåller sidan och leta upp önskad sida i listan med sidor. Om du inte hittar sidan kan du använda redigeringsverktygets funktioner för avancerad sökning. Skriv antingen det exakta sidnamnet eller skriv de första bokstäverna i den och sedan en asterisk (\*). En filtrerad lista med sidor visas. Du kan använda den här listan för att hitta den sida du vill ha. När du har hittat rätt sida väljer du namnet på sidan så att sidan öppnas i sidredigeraren.

> [!TIP]
> Om sidan visas i sidpanelen kan du markera **Redigera** och checka ut sidan innan du öppnar den i sidredigeraren. På så sätt kan du checka ut flera sidor på samma gång.

När sidan har öppnats i sid redigeraren måste du kontrollera att den är utcheckad till dig. Kommandofältet i redigeringsverktyget är dynamiskt, sammanhangskänsligt och tillståndskänsligt. Därför visas endast de åtgärder som du för närvarande kan utföra på sidan. Om till exempel sidan inte är utcheckad till dig visas inte knapparna **Spara** och **Slutför redigering** i kommandofältet. Sidans status visas också till höger om fönstret.

Om sidan inte redan är utcheckad till dig väljer du **Redigera** i kommandofältet. Kommandofältet ändras med hänsyn till sidans nya status. Du får också ett meddelande om att sidan är utcheckad till dig.

Nästa steg är att göra de ändringar du gör. Ofta kommer du att använda siddispositionsträdet till vänster för att söka efter och välja den modul som du vill ändra och sedan göra ändringar i rutan egenskaper till höger. 

Ändringen kan emellertid ibland innebära att du lägger till eller tar bort modeller eller fragment. Om du vill lägga till ett fragment eller en modul använder du siddispositionsträdet för att hitta den plats där du vill lägga till modulen eller fragmentet. Välj sedan ellipsknappen (**...**) för den platsen. En meny visas som innehåller kommandon för att lägga till en modul eller ett fragment. Om du vill ta bort en modul eller fragment, leta reda på och markera den i siddispositionsträdet, markerar du ellipsknappen och väljer sedan kommandot för att ta bort modulen eller fragmentet.

> [!TIP]
> Du kan också visa och redigera egenskaperna för alla moduler som visas i förhandsversionen av visuell sidskapare genom att markera det direkt.

När du är klar med ändringarna och förhandsgranskningen av effekten ska du checka in sidan genom att välja **Slutför redigering** i kommandofältet. 

Om du vill publicera ändringarna direkt väljer du **publicera** i kommandofältet. Den senaste incheckade versionen av sidan som du ändrade publiceras och blir tillgänglig för externa användare som visar webbplatsen. 

## <a name="example-change-the-video-on-the-home-page"></a>Exempel: ändra videon på startsidan

Följande exempel visar hur du ändrar startsidan genom att ändra videon som visas i videospelarmodulen.

1. Under **Webbplatser**, välj **Fabrikam** (eller namnet på webbplatsen).
1. I navigeringsfönstret till vänster, välj **sidor**.
1. Sök och välj startsidan för att öppna den i sidredigeraren.
1. Klicka på **Redigera** i kommandofältet.
1. I siddispositionen, välj platsen **Huvud**.
1. Under **Huvud** för vätskebehållare under huvudplatsen.
1. Leta reda på och markera videospelarmodulen.
1. I egenskapsrutan till höger, välj egenskapen **video**. Tillgångsväljaren visas.
1. Markera en tillgänglig videoresurs i tillgångsväljaren eller välj **överför ny tillgång** om du vill överföra en ny videotillgång.
1. Välj **OK**.
1. Välj **spara** och välj sedan **Avsluta redigeringen**.
1. I fältet **kommentarer** anger du **Ändrade videon** och sedan **OK**.
1. Välj **Förhandsgranska** om du vill förhandsgranska den uppdaterade sidan. När du är klar kan du stänga fliken förhandsgranskning och återgå till redigeringsverktyget.
1. Markera **Publicera**.

## <a name="additional-resources"></a>Ytterligare resurser

[Lägga till en ny webbplatssida](add-new-page.md)

[Välj sidlayouter](select-page-layouts.md)

[Hantera SEO-metadata](manage-seo-metadata.md)

[Spara, förhandsgranska och publicera en sida](save-preview-publish-page.md)

[Utöka en produktsida](enrich-product-page.md)

[Utöka en kategorilandningssida](enrich-category-page.md)

[Kontrollera tillgängligheten för sidinnehåll](verify-accessibility.md)

[Skapa dynamiska näthandelssidor baserade på URL-parametrar](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
