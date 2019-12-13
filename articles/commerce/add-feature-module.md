---
title: Funktionsmodul
description: Det här avsnittet innehåller moduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 76b59681d0bda11446f6db8b2685d1a0656f8f55
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785316"
---
# <a name="feature-module"></a>Funktionsmodul 

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Det här avsnittet innehåller moduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

En funktionsmodul används för att marknadsföra produkter eller erbjudanden genom en kombination av bilder och text. En åter försäljare kan t.ex. lägga till en modul på en produktinformationssida för att framhäva produktens funktioner.

En funktionsmodul drivs av data från innehållshanteringssystemet (CMS). Det är en fristående modul som inte är beroende av andra moduler på sidan. En funktionsmodul kan placeras på alla webbplatssidor där en återförsäljare vill marknadsföra eller främja något (t.ex. produkter, försäljning eller funktioner).

## <a name="examples-of-feature-modules-in-e-commerce"></a>Exempel på funktionsmoduler i e-handel

En funktionsmodul kan användas på följande sidor:

- För att presentera produktfunktioner på en produktinformationssida
- För att främja produkter på startsidan
- För att markera en produktkategori på en kategorisida

## <a name="feature-module-properties"></a>Egenskaper för funktionsmodul

| Egenskapsnamn     | Värden | Beskrivning |
|-------------------|--------|-------------|
| Bild             | Bildfil | En bild kan användas för att marknadsföra en produkt eller ett erbjudande. En bild kan överföras till bildgalleriet, eller så kan en befintlig bild användas. |
| Rubrik           | Rubriktext och rubriktagg (**H1**, **H2**, **H3**, **H4**, **H5** eller **H6**) | Varje funktionsmodul kan ha en rubrik. Som standard används rubriktaggen **H2** för rubriken. Taggen kan emellertid ändras så att den uppfyller tillgänglighetskraven. |
| Stycke         | Stycketext | Funktionsmoduler har stöd för stycketext i RTF-format. Vissa grundläggande RTF-funktioner stöds, t.ex. fetstil, understrykning och kursiv text och hyperlänkar. Vissa av dessa funktioner kan åsidosättas av det sidtema som används i modulen. |
| Länka              | Länktext, länk-URL, ARIA-etikett (Accessible Rich Internet Applications) och **öppna länk i ny flik** | Funktionsmoduler stöder en eller flera "Uppmaning till åtgärd"-länkar. Om en länk läggs till, en länktext, en URL-adress och en ARIA-etikett krävs. ARIA-etiketter ska vara beskrivande för att uppfylla tillgänglighetskraven. Länkar kan konfigureras så att de öppnas på en ny flik. |
| Bildplacering   | **Höger**, **vänster**, **över**eller **under** | Den här egenskapen definierar bildens placering i förhållande till texten. Om till exempel **höger** är markerad visas bilden till höger om texten. |
| Storlek på bildkolumn | Ett värde mellan **1** och **12** | Den här egenskapen definierar bildens storlek i förhållande till texten. Storleken uttrycks som ett antal kolumner på sidan. Det finns 12 kolumner på en sida. Som standard har bilden och texten samma storlek (sex kolumner vardera). Storleken kan dock justeras efter behov. |

## <a name="add-a-feature-module-to-a-new-page"></a>Lägg till en funktionsmodul på en ny sida 

Om du vill lägga till en funktionsmodul på en ny sida och ställa in de obligatoriska egenskaperna följer du stegen nedan.

1. Gå till **mallar**och skapa en sidmall med namnet **funktionsmall**.
1. Lägg till platsen **Huvud** på standardsida, lägg till en funktionsmodul.
1. Checka in mallen och publicera den.
1. Använd den funktionsmall som du just skapade för att skapa en sida med namnet **funktionssida**.
1. I platsen för standardsidan väljer du **Huvud**, markerar ellipsknappen (**...**) och väljer sedan **Lägg till modul**.
1. I dialogrutan **Lägg till modul**, under **Välj moduler**, välj funktionsmodul och sedan **OK**.
1. I dispositionsträdet till vänster väljer du funktionsmodulen.
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

[Fokusmodul](add-hero-module.md)

[Modul för videospelare](add-video-player.md)
