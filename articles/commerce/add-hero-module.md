---
title: Innehållsblockmodul
description: Denna artikel handlar om innehållsblockmoduler och beskriver hur du lägger till dem på webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.industry: ''
ms.openlocfilehash: dc6d728f49befd0c156340379dba05f592ca7919
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9277011"
---
# <a name="content-block-module"></a>Innehållsblockmodul

[!include [banner](includes/banner.md)]

Denna artikel handlar om innehållsblockmoduler och beskriver hur du lägger till dem på webbsidorna i Microsoft Dynamics 365 Commerce.

En innehållsblockmodul används för att marknadsföra produkter eller erbjudanden genom en kombination av bilder och text. En återförsäljare kan till exempel lägga till en innehållsblockmodul på startsidan för en näthandelssajt för att marknadsföra en ny produkt och locka kundernas uppmärksamhet.

En innehållsblockmodul drivs av data från innehållshanteringssystemet (CMS). Det är en fristående modul som inte är beroende av andra moduler på sidan. En innehållsblockmodul kan placeras på alla webbplatssidor där en återförsäljare vill marknadsföra eller främja något (t.ex. produkter, försäljning eller funktioner).

## <a name="examples-of-content-block-module-in-e-commerce"></a>Exempel på innehållsblockmoduler i näthandel

- En innehållsblockmodul kan användas på startsidan för en näthandelssajt för att framhäva erbjudanden och nya produkter.
- En innehållsblockmodul kan användas på en produktinformationssida för att visa upp produktinformation.
- Flera innehållsblockmoduler kan placeras i en karusellmodul för att framhäva flera produkter eller erbjudanden.

## <a name="content-block-modules-and-themes"></a>Innehållsblockmoduler och teman

Innehållsblockmoduler kan stödja olika layouter och stilar som baseras på ett tema. Temat Fabrikam har till exempel stöd för tre layoutändringar för en innehållsblockmodul: fokus, funktion och panel. I fokuslayouten visas en bild på bakgrunden med textöverlägg. I funktionslayouten visas en bild och text sida vid sida. Med hjälp av panellayouten kan du använda flera innehållsblock i ett panelformat.

Dessutom kan temat visa olika egenskaper för varje layout. En temautvecklare kan bygga fler layouter med fler stilar med hjälp av innehållsblockmodulen.

Följande bild visar ett exempel på en innehållsblockmodul med en fokuslayout.

![Exempel på en fokusmodul.](./media/Hero.PNG)

Följande bild visar ett exempel på en innehållsblockmodul med en funktionslayout.

![Exempel på funktionsmoduler.](./media/Feature.PNG)

## <a name="content-block-module-properties"></a>Egenskaper för innehållsblockmoduler

| Egenskapsnamn  | Värden | beskrivning |
|----------------|--------|-------------|
| Bild          | Bildfil | En bild kan användas för att presentera en produkt eller ett erbjudande. En bild kan överföras till bildgalleriet, eller så kan en befintlig bild användas. |
| Rubrik        | Rubriktext och rubriktagg (**H1**, **H2**, **H3**, **H4**, **H5** eller **H6**) | Varje fokusmodul kan ha en rubrik. Som standard används rubriktaggen **H2** för rubriken. Taggen kan emellertid ändras så att den uppfyller tillgänglighetskraven. |
| Stycke      | Stycketext | Fokusmoduler har stöd för stycketext i RTF-format. Vissa grundläggande RTF-funktioner stöds, t.ex. fetstil, understrykning och kursiv text och hyperlänkar. Vissa av dessa funktioner kan åsidosättas av det sidtema som används i modulen. |
| Länka           | Länktext, länk-URL, ARIA-etikett (Accessible Rich Internet Applications) och **öppna länk i ny flik** | Fokusmoduler stöder en eller flera "Uppmaning till åtgärd"-länkar. Om en länk läggs till, en länktext, en URL-adress och en ARIA-etikett krävs. ARIA-etiketter ska vara beskrivande för att uppfylla tillgänglighetskraven. Länkar kan konfigureras så att de öppnas på en ny flik. |

## <a name="content-block-module-properties-exposed-by-the-fabrikam-theme"></a>Egenskaper för innehållsblockmoduler som visas av Fabrikam-temat 

| Egenskapsnamn  | Värden | Beskrivning |
|----------------|--------|-------------|
| Textplacering | **Vänster**, **Höger**, **Centrera** | Den här egenskapen definierar placeringen av texten på bilden. Det gäller endast fokuslayout. |
| Texttema     | **Ljus** eller **Mörk** | Ett färgschema kan definieras för texten, baserat på bakgrundsbilden. Om bilden t.ex. har en mörk bakgrund kan ett ljust tema användas för att göra texten mer synlig och för att uppfylla färg kontrastförhållandena för hjälpmedelssyfte. Det gäller endast fokuslayout.|
| Bildplacering       | **Vänster**, **höger** | Den här egenskapen anger om bilden ska placeras till vänster eller till höger om texten. Det gäller endast funktionslayout.  |

## <a name="add-a-content-block-module-to-a-new-page"></a>Lägg till en innehållsblockmodul till en ny sida

Om du vill lägga till en fokusmodul på en ny sida och konfigurera de obligatoriska egenskaperna följer du stegen nedan.

1. Gå till **mallar** och skapa en sidmall med namnet **innehållsblockmall**.
1. Lägg till platsen **Huvud** på standardsida, lägg till fokusmodul.
1. Välj **Spara**, välj **Slutför redigering** för att checka in mallen och välj sedan **publicera** för att publicera den.
1. Använd den fokusmall som du just skapade för att skapa en sida med namnet **innehållsblocksida**.
1. I platsen för standardsidan väljer du **Huvud**, markerar ellipsknappen (**...**) och väljer sedan **Lägg till modul**.
1. I dialogrutan **Välj moduler**, välj heromodul oh välj **OK**.
1. I dispositionsträdet till vänster väljer du innehållsblockmodulen.
1. I egenskapsrutan till höger, välj egenskapen **Lägg till en bild**. Välj antingen en befintlig bild eller överför en ny avbildning.
1. Välj **Rubrik**.
1. I dialogrutan **rubrik** lägg till rubriktexten, välj rubrik nivå och klicka sedan på **OK**.
1. Under **oformaterad text** lägger du till text efter behov.
1. Välj **Markera länk**.
1. I dialogrutan **länk** lägg till länktext, en länk-URL och en ARIA-etikett för länken och välj sedan **OK**.
1. Välj layout **fokus**.
1. Klicka på **Spara** och välj **Förhandsgranska** för att förhandsgranska sidan.
1. Välj **Slutför redigering** för att checka in mallen och välj sedan **publicera** för att publicera den. 

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över modulbibliotek](starter-kit-overview.md)

[Modul med kampanjbanderoll](add-alert.md)

[Karusellmodul](add-carousel.md)

[Textblockmodul](add-content-rich-block.md)

[Modul för videospelare](add-video-player.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
