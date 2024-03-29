---
title: Demodataskärmlayouter i Modern POS (MPOS) och molnbaserad kassa
description: Denna artikel innehåller information om skärmlayouterna som medföljer demonstrationsdatauppsättningen för kassaupplevelser (POS) i Dynamics 365 Commerce.
author: josaw1
ms.date: 10/05/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailTillLayout
audience: Application user
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2017-10-05
ms.dyn365.ops.version: Retail April 2017 update
ms.openlocfilehash: eb7a288b61e8b467dd8ad6a8f7dc42b7fca0d943
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8897235"
---
# <a name="demo-data-screen-layouts-in-modern-pos-mpos-and-cloud-pos"></a>Demodataskärmlayouter i Modern POS (MPOS) och molnbaserad kassa

[!include [banner](includes/banner.md)]

Denna artikel innehåller information om skärmlayouterna som medföljer demonstrationsdatauppsättningen för kassaupplevelser (POS) i Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

Exempel på de skärmlayouter som medföljer Commerce demodata ger innehåll som är optimerat för olika butikssegment, lagerarbetarroller och enheter. En enkel layout kan innehålla flera layoutstorlekar och kombinationer av knappsatser som säkerställer täckning som lagerarbetare flyttar mellan enheter och stationer. Denna artikel beskriver skillnaderna mellan dessa layouter, de åtgärder de tillhandahåller och de övergripande erfarenheter som de ger.

![Demodatalayouter mellan enheter.](../commerce/media/demo-screen-layouts-fig-1-1.png)

## <a name="anatomy-of-a-screen-layout-id"></a>Beskrivning av en skärmlayout-ID

För att hitta skärmlayouter i Retail, gå till **Butik och handel** \> **Kanalinställning** \> **Kassainställning** \> **Kassa** \> **Skärmlayouter**.

![Sidan Skärmlayouter.](../commerce/media/demo-screen-layouts-fig-2-1.png)

Skärmlayout-ID kan ha upp till 10 tecken. ID är en sträng som består av tre delar med information i följande ordning:

1. Företag
2. Layoutversion
3. Person

### <a name="company"></a>Företag

| Brev | Företag         |
|--------|-----------------|
| A      | Adventure Works |
| F      | Fabrikam        |
| C      | Contoso         |

### <a name="layout-version"></a>Layoutversion

| Versionsnummer | beskrivning                                                                                |
|----------------|--------------------------------------------------------------------------------------------|
| 3              | Grundläggande version som stöder flera olika skärmstorlekar för olika enheter och förhållandet mellan bredd och höjd |
| 3.1            | Grundläggande version som har stöd för ytterligare språk för panelen **Rekommenderade produkter**        |
| 4              | Den utökade versionen för den utökade Fabrikam-uppdaterade layouten                                  |

### <a name="persona"></a>Person

| Förkortning | Person       | Innehåll |
|--------------|---------------|----------|
| CSH          | Kassör       | Kassörlayouter inkluderar alla transaktionsrelaterade åtgärder, t.ex. kundorder, returer, rabatter, annulleringar och presentkort. Dessa layouter kan också innehålla dagliga uppgifter för lagerhantering som t.ex. priskontroller, lagersökningar och lagerinventeringar. Grundläggande hantering av skift finns också för startbelopp, skjuta upp skift och tidsklocka. |
| MGR          | Butikschef | Butikscheflayouter inkluderar alla transaktionsrelaterade åtgärder som finns i kassalayouterna men innehåller också momsåsidosättningar. Dessa layouter kan också innehålla dagliga uppgifter för lagerhantering som t.ex. priskontroller, lagersökningar och lagerinventeringar. Hantering av skift tillhandahålls för att starta, skjuta upp och stänga skift. Dessutom innehåller layouterna kassaaktiviteter för registreringar, uttag, kassaavstämningar och kassaskåp och bankinsättningar. Slutligen innehåller dessa layouter tillgång till prestandarapporter och aktivera X- och Z-rapporter som ska skrivas ut. |
| STK          | Ansvarig för lager   | Ansvarig för lager-layouter optimeras för lagerhantering. De innehåller tillgång till dagliga uppgifter för prischeckar, lagersökningar, plockning och mottagning, lagerinventeringar och paketuppdelning. Dessa layouter innehåller också grundläggande skiftåtgärder för klocka och skjuta upp skift. Även om dessa layouter huvudsakligen är avsedda för back office-uppgifter, har lagerarbetare samma åtgärder som kassörerna för transaktionsskärmar. |

### <a name="example-layout"></a>Exempel på layout

Här följer ett exempel på en skärmlayout-ID för företaget Fabrikam, layoutversion 4 och butikschefen:

F4MGR

Följande illustration visar ett exempel på välkomstskärmen för Fabrikam butikschefen.

![Välkomstskärm för Fabrikam-butikschefen.](../commerce/media/demo-screen-layouts-fig-2-2.png)

## <a name="layout-sizes"></a>Layoutstorlekar

### <a name="full-vs-compact-layouts"></a>Fullständig jämfört med kompakt layout

En skärmlayout kan ha konfigurationer för både fullstora och kompakta enheter. Därför kan en användare tilldelas till en enda skärmlayout som fungerar för olika storlekar och formfaktorer i butiken.

- **Modern POS – fullständig** – Vanligtvis används fullständiga layouter bäst till större skärmar, till exempel datorskärmar eller surfplattor. Användare kan markera de UI-element som layouten innehåller, ange storlek och placering av elementen och konfigurera de detaljerade egenskaperna. Fullständiga layouter stöder både stående och liggande konfigurationer.
- **Modern POS – komprimerad** – Vanligtvis är komprimerad layout bäst för telefoner eller små surfplattor. Designmöjligheter är begränsade för kompakta enheter. Användare kan konfigurera kolumner och fält för kvitto- och summarfönster.

### <a name="screen-resolutions-that-are-provided"></a>Skärmupplösning som tillhandahålls

Följande tabell visar layoutstorlek för normal skärmupplösning.

| Layouttyp | Upplösning | Förhållandet mellan bredd och höjd | Måldisplay          |
|-------------|------------|--------------|-------------------------|
| Komprimera\*   | 480 × 853  | 16:9         | Telefon                  |
| Fullständig        | 1024 × 768 | 4:3          | Surfplatta                 |
| Fullständig\*      | 1280 × 720 | 16:9         | Surfplatta                 |
| Fullständig        | 1366 × 768 | 16:9         | Surfplattor, större skärmar |
| Fullständig        | 1440 × 960 | 3:2          | Surfplattor, större skärmar |
| Fullständig\*      | 1536 × 864 | 16:9         | Surfplattor, större skärmar |

\*Dessa ytterligare layoutstorlekar är bara tillgängliga i Adventure Works och Fabrikam layouter.

> [!TIP]
> POS väljer automatiskt layoutstorlekar, baserat på närmaste storleken för skärmupplösningen för det aktuella appfönstret. Öppna den layout-ID och layoutskärmupplösning som för närvarande används i Modern POS (MOPS) eller Retail Cloud POS (CPOS), öppna sidan **inställningar** och titta i avsnittet **sessionsinformation**. Du kan också hitta den aktuella upplösningen för fönster för ditt aktuella program eller webbläsarram. När du har den här informationen hittar du källan för layoutinnehållet genom att gå till **kanalinställning** \> **kassainställningar** \> **kassa** \> **skärmlayouter**.

![Skärmlayouter och layoutlösningar/storlekar i Commerce och kassa.](../commerce/media/demo-screen-layouts-fig-3-1.png)

## <a name="companies-and-brands"></a>Företag och varumärken

Varje fiktivt företag är avsett för ett annat butikssegment och innehåller produktkataloger som är anpassade för företagets marknad. Varje företag har ett unikt visuellt varumärke som medföljer produkter. Varumärkesanpassade element omfattar tilläggsfärg, mörkt eller ljust tema och medföljande fotografier som ger realistiska upplevelser.

### <a name="company-segment-and-visual-characteristics"></a>Företagssegment och visuella komponenter

| Företag         | Plats | Segment        | Accent | Tema |
|-----------------|----------|----------------|--------|-------|
| Adventure Works | Seattle  | Sportutrustning | Blått   | Mörk  |
| Fabrikam        | San Francisco  | Mode        | Grönt  | Ljus |
| Contoso         | Boston   | Elektronik    | Röd    | Mörk  |

> [!NOTE]
> Adventure Works och Fabrikam är två framstående varumärken. Contoso finns tillgänglig, men alla layouter har inte tillhandahållits.

I följande illustrationer visas exempel på välkomstsidan och transaktionssidan för de tre fiktiva företagen.

### <a name="adventure-works"></a>Adventure Works

![Demodata-välkomstsida för Adventure Works.](../commerce/media/demo-screen-layouts-fig-4-1a.png)

![Demodata-transaktionssida för Adventure Works.](../commerce/media/demo-screen-layouts-fig-4-1b.png)

### <a name="fabrikam"></a>Fabrikam

![Demodata-välkomstsida för Fabrikam.](../commerce/media/demo-screen-layouts-fig-4-2a.png)

![Demodata-transaktionssida för Fabrikam.](../commerce/media/demo-screen-layouts-fig-4-2b.png)

### <a name="contoso"></a>Contoso

![Layouter för Contoso-demonstationsdata.](../commerce/media/demo-screen-layouts-fig-4-3.png)

## <a name="user-sign-in-matrix"></a>Matris för användarinloggning

Användare har angetts för de olika layouterna för skärmen. Med hjälp av tabellen nedan kan vara du få tillgång till skärmarna. Logga bara in med lämpligt operatörs-ID.

| Företag         | Skärmlayout-id | Person       | Operatörs-ID           |
|-----------------|------------------|---------------|------------------------|
| Adventure Works | A3MGR            | Butikschef | 000154, 000137, 000073 |
| Adventure Works | A3CSH            | Kassör       | 000150, 000175, 000165 |
| Adventure Works | A3STK            | Ansvarig för lager   | 000155, 000181, 000152 |
| Fabrikam        | F4MGR            | Butikschef | 000160, 000713         |
| Fabrikam        | F3CSH            | Kassör       | 000161, 000113, 000114 |
| Fabrikam        | F3STK            | Ansvarig för lager   | 000164, 000112, 000123 |
| Contoso         | C3MGR            | Butikschef | 000100, 000111         |
| Contoso         | C3CSH            | Kassör       | 000110, 000120         |
| Contoso         | Inte tillämpligt   | Ansvarig för lager   | Inte tillämpligt         |

> [!TIP]
> För bästa resultat, aktivera ett register i motsvarande lagringsplats och ange vilket företag för den person som du tänker använda när du loggar in. På så sätt kan du garantera den visuella profilen och varumärkesanpassade bilder är justerade genom erfarenheten. Om du till exempel vill visa Fabrikam-layouten Fabrikam för en kassör, bör du aktivera en kassa i Houston-butiken.

<!-- Hiding until the content page is available on CustomerSource -->

<!-- ## Reference icons and images -->

<!-- The screen layouts, button grids, and visual profiles were created using images and icons that can be found in **Retail and Commerce \> Channel setup \> POS setup \> POS \> Images**. -->

<!-- ![Images in Dynamics 365 Commerce.](../commerce/media/demo-screen-layouts-fig-5-1.png) -->

<!-- Use the [POS Icon and Image Mapping](../commerce/media/POS_Icon_and_Image_Mapping.xlsx) reference spreadsheet to locate operation icons, reference photos, swap logos, or provide new images of your own that can be referenced in custom designs. -->

<!-- END HIDDEN CONTENT -->


[!INCLUDE[footer-include](../includes/footer-banner.md)]