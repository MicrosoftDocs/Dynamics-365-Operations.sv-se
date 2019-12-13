---
title: Modul för innehållsplacering
description: Det här avsnittet handlar om innehållsplacering och moduler för innehållsplaceringsobjekt och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 1b64e930628c969334ff6e643ba23b77445e6e4c
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785310"
---
# <a name="content-placement-module"></a>Modul för innehållsplacering

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Det här avsnittet handlar om innehållsplacering och moduler för innehållsplaceringsobjekt och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

En modul för innehållsplacering är en särskild behållare som andra moduler kan placeras i en viss layout. Moduler för innehållsplacering har stöd för följande typer av moduler som underordnade moduler: innehålletsplaceringsobjekt, kontots välkomstobjekt, kontoorderobjekt, objekt för kontoönskelista och kontoprofilsobjekt.

Moduler för innehållsplacering hämtar data från de underordnade moduler som de stöder. Därför kan moduler för innehållsplacering användas på olika sätt beroende på vilka moduler som läggs till i det.

moduler för innehållsplaceringsobjekt använder både bilder och text för att visa kampanjer, policyer och produktfunktioner. En modul för innehållsplacering kan till exempel användas på en startsida för att visa butiksprinciper eller leveransinformation. moduler för innehållsplaceringsobjekt styrs av data från CMS-systemet (Content Management System) och kan placeras på vilken sida som helst. De kan dock bara användas i en modul för innehållsplacering.

## <a name="examples-of-content-placement-modules-in-e-commerce"></a>Exempel på moduler för innehållsplacering i e-handel

* Moduler för innehållsplacering som innehåller moduler för innehållsplaceringsobjekt kan användas på en startsida eller på marknadsföringssidor för att visa produktfunktioner, erbjudanden, butiksprinciper, leveransinformation och annan information via både bilder och text.
* Moduler för innehållsplacering som innehåller moduler för innehållsplaceringsobjekt kan användas på produktinformationssidor för att visa produktfunktioner.
* Moduler för innehållsplacering som innehåller välkomstobjekt eller objektmoduler för kontoorder kan användas på kontohanteringssidor.

## <a name="content-placement-module-properties"></a>Egenskaper för modul för innehållsplacering

| Egenskapsnamn | Värde | Beskrivning |
|---------------|-------|-------------|
| Bredd         | **Passa behållare** eller **Fyll skärm** | Om värdet är inställt på att **passa behållare** begränsas modul för innehållsplacering till bredden för modulen för innehållsplacering. Om värdet är inställt på **Fyll skärm** begränsas inte objekten till bredden för modulen för innehållsplacering utan kan gå in i helskärmsläge. |

## <a name="content-placement-item-module-properties"></a>Egenskaper för objektmodul för innehållsplacering

| Egenskapsnamn | Värde | Beskrivning |
|---------------|-------|-------------|
| Rubrik       | Rubriktext och rubriktaggar (**H1**, **H2**, **H3**, **H4**, **H5** eller **H6**) | Alla objekt i modulen för innehållsplacering kan ha en rubrik. Egenskapen **rubrik** stöder rubrikkoder. Som standard används rubriktaggen **H2**, men rubriktaggen rubrikerna kan ändras så att den uppfyller tillgänglighetskraven. |
| Stycke     | Stycketext | moduler för innehållsplaceringsobjekt har stöd för stycketext i RTF-format. Vissa grundläggande RTF-funktioner stöds, t.ex. fetstil, understrykning och kursiv text och hyperlänkar. Vissa av dessa funktioner kan åsidosättas av det sidtema som används i modulen. |
| Bild         | Bildfil | En bild kan vara kopplad till texten. |
| Länka          | Länk-URL och länktext | En länk kan läggas till i texten för att omdirigera användare till en viss sida. |
| Panelstorlek     | Ett nummer mellan **1** och **12** | För varje objekt för innehållsplacering definierar den här egenskapen antalet platser som objekten ska fylla i modulen innehållsplacering. Maximal storlek för modulen för innehållsplacering är 12 platser. Om den totala panelstorleken för de första *n* objekten i modulen för innehållsplacering överskrider 12 platser, objekten är radbrutna till nästa rad. |

## <a name="add-a-content-placement-module-that-contains-a-content-placement-item-module-to-a-page"></a>Lägga till en modul för innehållsplacering som innehåller moduler för innehållsplaceringsobjekt på en sida

Om du vill lägga till en modul för innehållsplacering som innehåller moduler för innehållsplaceringsobjekt på en ny sida och ange de obligatoriska egenskaperna följer du dessa steg.

1. Skapa en sidmall som har namnet **Innehållsplaceringsmall**.
1. Lägg till platsen **Huvud** på standardsida, lägg till en modulen för innehållsplacering.
1. I modulen för innehållsplacering, lägg till moduler för innehållsplaceringsobjekt.
1. Checka in mallen och publicera den.
1. Använd den innehållsplaceringsmall som du just skapade för att skapa en sida med namnet **innehållsplaceringssida**.
1. Lägg till platsen **Huvud** på den nya sidan, lägg till en modulen för innehållsplacering.
1. I modulen för innehållsplacering, lägg till moduler för innehållsplaceringsobjekt.
1. I egenskapsrutan för moduler för innehållsplaceringsobjekt väljer du en bild, lägger till en rubrik, lägger till ett stycke, lägger till en länk, anger länkens URL och ställer in panelstorleken till **6**.
1. Upprepa steg 7 och 8 om du vill lägga till en annan modul för innehållsplaceringsobjekt som har samma panelstorlek.
1. Spara och förhandsgranska sidan. Du bör se två objekt för innehållsplacering som visas sida vid sida. Du kan justera egenskapen **panelstorlek** för varje modul för innehållsplacering eller lägga till fler moduler för att uppnå önskad layout.
1. Checka in sidan och publicera den.

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över startpaket](starter-kit-overview.md)

[Notifieringsmodul](add-alert.md)

[Karusellmodul](add-carousel.md)

[Innehållsrik blockmodul](add-content-rich-block.md)

[Funktionsmodul](add-feature-module.md)

[Fokusmodul](add-hero-module.md)

[Modul för videospelare](add-video-player.md)
