---
title: Textblockmodul
description: Det här avsnittet handlar om textblockmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 18a4226d3b8dce1b46e6612521d70a3627b517d1
ms.sourcegitcommit: ccb39767bd3430c24f4653c26560bba2cd66553c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2022
ms.locfileid: "8780499"
---
# <a name="text-block-module"></a>Textblockmodul

[!include [banner](includes/banner.md)]

Det här avsnittet handlar om textblockmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.

En textblockmodul är en modul som används för att lägga till textinnehåll. Det här innehållet kan vara information och reklam.

Textblockmoduler styrs av data från CMS-systemet (Content Management System) och kan placeras på vilken sida som helst. De är fristående moduler som inte är beroende av sidkontext eller andra moduler.

## <a name="examples-of-text-block-modules-in-e-commerce"></a>Exempel på innehållsrika textmoduler i näthandel

Innehållsrika textblockmoduler kan användas på följande sätt:

* För att presentera produktfunktioner på en produktinformationssida.
* För information på vilken sida som helst. De kan till exempel förklara fördelarna med lojalitetsprogram, beskriva leverans- och returprinciper, besvara vanliga frågor eller ge "om oss"-innehåll.
* Om du vill lägga till anpassade meddelanden på en produktinformationssida. (t.ex. "gratis frakt för order över 50 $").
* För avskrivningar och kontaktinformation på produktinformationssidor, kundvagnssidor, betalningssidor och andra sidor (t.ex. "leverans och returer" är föremål för lagringsprinciper").

Följande bild visar ett exempel på en modul för textblock som används på en startsida.

![Exempel på en modul för textblock.](./media/ecommerce-textblock.PNG)

## <a name="text-block-module-properties"></a>Egenskaper för textblockmodul

| Egenskapsnamn     | Värde                                            | beskrivning |
|-------------------|--------------------------------------------------|-------------|
| RTF-format         | RTF-format                                        | Stycketext. Vissa grundläggande RTF-funktioner stöds, t.ex. fetstil, understrykning och kursiv text. |
| Anpassat klassnamn | Ett klassnamn för Överlappande formatmallar (CSS)        | Namnet på en anpassad CSS-klass som en utvecklare använder för att formatera modulen. Klassnamnet måste definieras i temapaketet. |
| Teckenstorlek         | **Small**, **Medium**, **Large** eller **X-Large** | Teckenstorleken för innehållet. |

## <a name="add-a-text-block-module-to-a-page"></a>Lägg till en textblockmodul till en sida

Om du vill lägga till en textblockmodul på en ny sida och ställa in de obligatoriska egenskaperna följer du stegen nedan.

1. Gå till **mallar** och välj sedan **ny** för att skapa en ny mall.
1. I dialogrutan **Ny mall** under **Mallnamn** anger du **Innehållsmall**.
1. I facket **brödtext** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.
1. I dialogrutan **Välj moduler**, välj modulen **Standardsida** och klicka sedan på **OK**.
1. Välj **Spara**, välj **Slutför redigering** för att checka in mallen och välj sedan **publicera** för att publicera den.
1. Gå till **Sidor** och välj **nytt sidfragment** för att skapa en ny sida.
1. I dialogrutan **Skapa en ny sida** under **Sidnamn**, ange **Innehållssida** och välj sedan **Nästa**.
1. Under **Välj en mall**, välj **Innehållsmall** och välj sedan **Nästa**.
1. Under **Välj en layout** väljer du en sidlayout (till exempel **Flexibel layout**) och väljer sedan **Nästa**.
1. Under **Granska och slutför**, granska sidkonfiguration. Om du behöver redigera sidinformationen väljer du **Bakåt**. Om sidinformationen är korrekt väljer du **Skapa sida**. 
1. I platsen för nya sidan väljer du **Huvud**, markerar ellipsknappen (**...**) och väljer sedan **Lägg till modul**.
1. I dialogrutan **Välj moduler**, välj modulen **Behållare** och klicka sedan på **OK**.
1. I egenskapsfönstret för behållarmodulen, ange egenskapen **bredd** till **fyll behållare**.
1. I facket **behållare** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.
1. I dialogrutan **Välj moduler**, välj modulen **Textblock** och klicka sedan på **OK**. 
1. I egenskapsfönstret för textblockmodulen, lägg till text i fältet **RTF**.
1. Klicka på **Spara** och välj **Förhandsgranska** för att förhandsgranska sidan.
1. Välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över modulbibliotek](starter-kit-overview.md)

[Modul med kampanjbanderoll](add-alert.md)

[Karusellmodul](add-carousel.md)

[Innehållsblockmodul](add-hero-module.md)

[Modul för videospelare](add-video-player.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
