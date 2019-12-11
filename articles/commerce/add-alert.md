---
title: Notifieringsmodul
description: Det här avsnittet handlar om notifieringsmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 82138dd7f0934f732215f67a3726638eb87075d4
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785362"
---
# <a name="alert-module"></a>Notifieringsmodul

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Det här avsnittet handlar om notifieringsmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

En notifieringsmodul används för att visa infogade informationsmeddelanden på en sida. I notifieringsmoduler kan du använda textmeddelanden och länkar. De kan användas för att visa erbjudanden på hela webbplatsen som visas på alla sidor på en e-handelswebbplats. 

Notifieringsmoduler styrs av data från CMS-systemet (Content Management System) och kan placeras på vilken sida som helst.

## <a name="examples-of-alert-modules-in-e-commerce"></a>Exempel på notifieringsmoduler i e-handel

Du kan använda notifieringsmoduler i webbplatsrubriken för att ange reklamerbjudanden eller meddelanden som gäller hela webbplatsen. Nedan följer några exempel:

"Årlig rea slutar om 10 dagar"

"Spara stort med tillbaka till skolan-rea. Handla nu."

## <a name="alert-module-properties"></a>Egenskaper för notifieringsmodul

| Egenskapsnamn  | Värde                              | Beskrivning |
|----------------|------------------------------------|-------------|
| Text           | Text                               | Textmeddelandet som visas i notifieringsmodulen. |
| Textjustering | **Höger**, **Vänster** eller **Centrera** | Ett värde som definierar hur text justeras i notifieringsmodulen. |
| Avfärda notifiering  | **Sant** eller **falskt**              | Om värdet är inställt på **Sant** kan kunden stänga notifieringen. |
| Länka           | URL                                | URL:en för en valfri länk. |

## <a name="add-an-alert-module-to-a-page"></a>Lägg till notifieringsmodul till en sida 

Om du vill lägga till en notifieringsmodul på en sida och ställa in de obligatoriska egenskaperna följer du stegen nedan.

1. Skapa en sidmall som har namnet **notifieringsmall**.
1. Lägg till platsen **Huvud** på standardsida, lägg till notifieringsmodul.
1. Checka in mallen och publicera den. 
1. Använd den notifieringsmall som du just skapade för att skapa en sida med namnet **notifieringssida**. 
1. Lägg till platsen **Huvud** på den nya sidan, lägg till notifieringsmodul.
1. I inställningarna för notifieringsmodulen anger du notifieringstexten. Du kan redigera de andra egenskaperna om du vill anpassa notifieringsmodulen ytterligare.
1. Spara och förhandsgranska sidan. Högst upp på sidan ska du se en notifiering med den tillagda texten.
1. Checka in sidan och publicera den. 

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över startpaket](starter-kit-overview.md)

[Karusellmodul](add-carousel.md)

[Innehållsrik blockmodul](add-content-rich-block.md)

[Modul för innehållsplacering](add-content-placement-modules.md)

[Funktionsmodul](add-feature-module.md)

[Fokusmodul](add-hero-module.md)

[Videospelar-modul](add-video-player.md)
