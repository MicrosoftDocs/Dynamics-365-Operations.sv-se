---
title: Textblockmodul
description: Det här avsnittet handlar om textblockmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 01/23/2020
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
ms.openlocfilehash: fc5b2fa35633b1ce7f7ffefacec318e14fa8db3f
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025607"
---
# <a name="text-block-module"></a>Textblockmodul


[!include [banner](includes/banner.md)]

Det här avsnittet handlar om textblockmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

En textblockmodul är en modul som används för att lägga till textinnehåll. Det här innehållet kan vara information och reklam.

Textblockmoduler styrs av data från CMS-systemet (Content Management System) och kan placeras på vilken sida som helst. De är fristående moduler som inte är beroende av sidkontext eller andra moduler.

## <a name="examples-of-text-block-modules-in-e-commerce"></a>Exempel på innehållsrika textmoduler i e-handel

Innehållsrika textblockmoduler kan användas på följande sätt:

* För att presentera produktfunktioner på en produktinformationssida.
* För information på vilken sida som helst. De kan till exempel förklara fördelarna med lojalitetsprogram, beskriva leverans- och returprinciper, besvara vanliga frågor eller ge "om oss"-innehåll.
* Om du vill lägga till anpassade meddelanden på en produktinformationssida. (t.ex. "gratis frakt för order över 50 $").
* För avskrivningar och kontaktinformation på produktinformationssidor, kundvagnssidor, betalningssidor och andra sidor (t.ex. "leverans och returer" är föremål för lagringsprinciper").

## <a name="text-block-module-properties"></a>Egenskaper för textblockmodul

| Egenskapsnamn     | Value                                            | Beskrivning |
|-------------------|--------------------------------------------------|-------------|
| RTF-format         | RTF-format                                        | Stycketext. Vissa grundläggande RTF-funktioner stöds, t.ex. fetstil, understrykning och kursiv text. |
| Anpassat klassnamn | Ett klassnamn för Överlappande formatmallar (CSS)        | Namnet på en anpassad CSS-klass som en utvecklare använder för att formatera modulen. Klassnamnet måste definieras i temapaketet. |
| Teckenstorlek         | **Small**, **Medium**, **Large** eller **X-Large** | Teckenstorleken för innehållet. |

## <a name="add-a-text-block-module-to-a-page"></a>Lägg till en textblockmodul till en sida

Om du vill lägga till en textblockmodul på en ny sida och ställa in de obligatoriska egenskaperna följer du stegen nedan.

1. Skapa en sidmall som har namnet **Innehållsmall**. 
1. I facket **Brödtext**, lägg till en **standardsida**-modul.
1. Avsluta redigeringen i mallen och publicera den.
1. Använd den innehållsmall som du just skapade för att skapa en sida med namnet **Innehållssida**.
1. Lägg till platsen **Huvud** på ny sida, lägg till en behållarmodul.
1. I egenskapsfönstret för behållarmodulen, ange egenskapen **bredd** till **fyll behållare**.
1. I textblockmodulen, lägg till en behållarmodul. 
1. I egenskapsfönstret för textblockmodulen, lägg till text i fältet **RTF**.
1. Avsluta redigeringen av sidan och publicera den.

## <a name="additional-resources"></a>Ytterligare resurser

[Startpaket – översikt](starter-kit-overview.md)

[Annonsbanderollmodul](add-alert.md)

[Karusellmodul](add-carousel.md)

[Innehållsblockmodul](add-hero-module.md)

[Modul för videospelare](add-video-player.md)

