---
title: Innehållsrik blockmodul
description: Det här avsnittet handlar om innehållsrika blockmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 27dabb425b3c9a3015ffc54ff3c0e50b7ee11749
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785431"
---
# <a name="content-rich-block-module"></a>Innehållsrik blockmodul

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Det här avsnittet handlar om innehållsrika blockmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

En innehållsrik blockmodul är en speciell behållare som en eller flera innehållsrika blockobjekt kan placeras i. Innehållsrika blockmoduler används för textinnehåll på en sida. Det här innehållet kan vara både information och reklam.

Innehållsrika blockmoduler styrs av data från CMS-systemet (Content Management System) och kan placeras på vilken sida som helst. De är fristående moduler som inte är beroende av sidkontext eller andra moduler.

## <a name="examples-of-content-rich-block-modules-in-e-commerce"></a>Exempel på innehållsrika blockmoduler i e-handel

Innehållsrika blockmoduler kan användas på följande sätt:

* För att presentera produktfunktioner på en produktinformationssida.
* För information på vilken sida som helst. De kan till exempel förklara fördelarna med lojalitetsprogram, beskriva leverans- och returprinciper, besvara vanliga frågor eller ge "om oss"-innehåll.
* Om du vill lägga till anpassade meddelanden på en produktinformationssida. (t.ex. "gratis frakt för order över 50 $").
* För avskrivningar och kontaktinformation på produktinformationssidor, kundvagnssidor, betalningssidor och andra sidor (t.ex. "leverans och returer" är föremål för lagringsprinciper").

## <a name="content-rich-block-module-properties"></a>Egenskaper för innehållsrika blockmoduler

| Egenskapsnamn     | Värde                                 | Egenskap |
|-------------------|---------------------------------------|----------|
| Antal kolumner | Ett nummer mellan **1** och **4**     | Antalet kolumner i det innehållsrika blocket. Det kan finnas upp till fyra kolumner. |
| Bredd             | **Fyll behållare** eller **Fyll skärm** | Om värdet är inställt på att **Fylla behållare** begränsas behållaren till behållarens bredd. Om värdet är inställt på **Fyll skärm** begränsas inte objekten till behållarens bredd utan kan gå in i helskärmsläge. Du kan ändra värdet för att uppnå önskad layout. |

## <a name="content-rich-block-item-module-properties"></a>Egenskaper för innehållsrika blockobjektmoduler

| Egenskapsnamn | Värde          | Beskrivning |
|---------------|----------------|-------------|
| Stycke     | Stycketext | Texten som medföljer varje innehållsrikt blockobjekt. Vissa grundläggande RTF-funktioner stöds, t.ex. fetstil, understrykning och kursiv text. |

## <a name="add-a-content-rich-block-module-to-a-page"></a>Lägg till en innehållsrik blockmodul till en sida

Om du vill lägga till en innehållsrik blockmodul på en ny sida och ställa in de obligatoriska egenskaperna följer du stegen nedan.

1. Skapa en sidmall som har namnet **Innehållsmall**.
1. Lägg till platsen **Huvud** på standardsida, lägg till en innehållsrik blockmodul.
1. Checka in mallen och publicera den.
1. Använd den innehållsmall som du just skapade för att skapa en sida med namnet **Innehållssida**.
1. Lägg till platsen **Huvud** på ny sida, lägg till en innehållsrik blockmodul.
1. I egenskaperna för innehållsrika blockmodulen ange antalet kolumner till **2**.
1. I innehållsrik blockmodul, välj **Lägg till en modul** och lägg till ett innehållsrikt blockobjekt (t.ex., **objekt1**).
1. Lägg till stycketext i det nya innehållsrika blockobjektet.
1. I innehållsrik blockmodul, välj **Lägg till en modul** och lägg till ett innehållsrikt blockobjekt (t.ex., **objekt2**).
1. Lägg till stycketext i det nya innehållsrika blockobjektet.
1. Spara sidan och förhandsgranska ändringarna. Två RTF-block bör visas i en vy med två spalter.
1. Checka in sidan och publicera den.

> [!NOTE]
> Om du lägger till ett tredje innehållsrikt blockobjekt kommer det att staplas nedanför de två objekt som du har lagt till. Genom att ändra antalet kolumner och objekt i behållaren kan du uppnå olika layouter för textinnehåll.

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över startpaket](starter-kit-overview.md)

[Notifieringsmodul](add-alert.md)

[Karusellmodul](add-carousel.md)

[Modul för innehållsplacering](add-content-placement-modules.md)

[Funktionsmodul](add-feature-module.md)

[Fokusmodul](add-hero-module.md)

[Videospelar-modul](add-video-player.md)

