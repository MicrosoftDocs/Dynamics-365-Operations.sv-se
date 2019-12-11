---
title: Fokusmodul
description: Det här avsnittet handlar om fokusmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: c43704992e9759e7207f1b1c9bc958449daa6d1d
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785408"
---
# <a name="hero-module"></a>Fokusmodul

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Det här avsnittet handlar om fokusmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

En fokusmodul används för att marknadsföra produkter eller erbjudanden genom en kombination av bilder och text. En återförsäljare kan till exempel lägga till en fokusmodul på startsidan för en näthandelsplats för att marknadsföra en ny produkt och locka kundernas uppmärksamhet.

En fokusmodul drivs av data från innehållshanteringssystemet (CMS). Det är en fristående modul som inte är beroende av andra moduler på sidan. En fokusmodul kan placeras på alla webbplatssidor där en återförsäljare vill marknadsföra eller främja något (t.ex. produkter, försäljning eller funktioner).

## <a name="examples-of-hero-module-in-e-commerce"></a>Exempel på fokusmodul i e-handel

- En fokusmodul kan användas på startsidan för en näthandelsplats för att framhäva erbjudanden och nya produkter.
- En fokusmodul kan användas på en produktinformationssida för att visa upp produktinformation.
- Flera fokusmoduler kan placeras i en karusellmodul för att framhäva flera produkter eller erbjudanden.

## <a name="hero-module-properties"></a>Egenskaper för fokusmodul

| Egenskapsnamn  | Värden | Beskrivning |
|----------------|--------|-------------|
| Bild          | Bildfil | En bild kan användas för att presentera en produkt eller ett erbjudande. En bild kan överföras till bildgalleriet, eller så kan en befintlig bild användas. |
| Rubrik        | Rubriktext och rubriktagg (**H1**, **H2**, **H3**, **H4**, **H5** eller **H6**) | Varje fokusmodul kan ha en rubrik. Som standard används rubriktaggen **H2** för rubriken. Taggen kan emellertid ändras så att den uppfyller tillgänglighetskraven. |
| Stycke      | Stycketext | Fokusmoduler har stöd för stycketext i RTF-format. Vissa grundläggande RTF-funktioner stöds, t.ex. fetstil, understrykning och kursiv text och hyperlänkar. Vissa av dessa funktioner kan åsidosättas av det sidtema som används i modulen. |
| Länka           | Länktext, länk-URL, ARIA-etikett (Accessible Rich Internet Applications) och **öppna länk i ny flik** | Fokusmoduler stöder en eller flera "Uppmaning till åtgärd"-länkar. Om en länk läggs till, en länktext, en URL-adress och en ARIA-etikett krävs. ARIA-etiketter ska vara beskrivande för att uppfylla tillgänglighetskraven. Länkar kan konfigureras så att de öppnas på en ny flik. |
| Textplacering | **Högst upp till vänster**, **Högst upp till höger**, **Högst upp i mitten**, **Längst ned till vänster**, **Längst ned till höger**, **Längst ned i mitten**, **Mitten till vänster**, **Mitten till höger** eller **Mitten mitten** | Den här egenskapen definierar bildens placering i förhållande till texten. Om till exempel **höger** är markerad visas bilden till höger om texten. |
| Texttema     | **Ljus** eller **Mörk** | Ett färgschema kan definieras för texten, baserat på bakgrundsbilden. Om bilden t.ex. har en mörk bakgrund kan ett ljust tema användas för att göra texten mer synlig och för att uppfylla färg kontrastförhållandena för hjälpmedelssyfte. |
| Toning       | **Sant** eller **falskt** | En övertoning kan användas på bilden för att uppfylla färgkontrastförhållanden för hjälpmedelssyfte. |

## <a name="add-a-hero-module-to-a-new-page"></a>Lägg till en fokusmodul på en ny sida

Om du vill lägga till en fokusmodul på en ny sida och ställa in de obligatoriska egenskaperna följer du stegen nedan.

1. Gå till **mallar**och skapa en sidmall med namnet **fokusmall**.
1. Lägg till platsen **Huvud** på standardsida, lägg till fokusmodul.
1. Checka in mallen och publicera den.
1. Använd den fokusmall som du just skapade för att skapa en sida med namnet **fokussida**.
1. I platsen för standardsidan väljer du **Huvud**, markerar ellipsknappen (**...**) och väljer sedan **Lägg till modul**.
1. I dialogrutan **Lägg till modul**, under **Välj moduler**, välj fokusmodul och sedan **OK**.
1. I dispositionsträdet till vänster väljer du fokusmodulen.
1. I egenskapsrutan till höger, välj egenskapen **Lägg till en bild**. Välj antingen en befintlig bild eller överför en ny avbildning.
1. Välj **Rubrik**.
1. I dialogrutan **rubrik** lägg till rubriktexten, välj rubrik nivå och klicka sedan på **OK**.
1. Under **oformaterad text** lägger du till text efter behov.
1. Välj **Lägg till åtgärdslänk**.
1. I dialogrutan **åtgärdslänk** lägg till länktext, en länk-URL och en ARIA-etikett för länken och välj sedan **OK**.
1. Spara sidan och förhandsgranska ändringarna.
1. Checka in sidan och publicera den.

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över startpaket](starter-kit-overview.md)

[Notifieringsmodul](add-alert.md)

[Karusellmodul](add-carousel.md)

[Innehållsrik blockmodul](add-content-rich-block.md)

[Modul för innehållsplacering](add-content-placement-modules.md)

[Funktionsmodul](add-feature-module.md)

[Videospelar-modul](add-video-player.md)
