---
title: Annonsbanderollmodul
description: Det här avsnittet handlar om annonsbanderollmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 1b7e7a8324c6460473e52543caf1484f9cf876a9
ms.sourcegitcommit: ccb39767bd3430c24f4653c26560bba2cd66553c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2022
ms.locfileid: "8780668"
---
# <a name="promo-banner-module"></a>Modul med kampanjbanderoll

[!include [banner](includes/banner.md)]

Det här avsnittet handlar om annonsbanderollmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.

Annonsbanderollmoduler används för att visa infogade informationsmeddelanden på en sida. De kan användas för att visa erbjudanden på hela webbplatsen som visas på alla sidor på en näthandelssajt. 

I annonsbanderollmoduler kan du använda textmeddelanden och länkar. Om flera meddelanden läggs till i en annonsbanderollmodul blir det en roterande karusellbanderoll som gör det möjligt för kunder att gå igenom alla meddelanden. 

Annonsbanderollmoduler styrs av data från CMS-systemet (Content Management System) och kan placeras på vilken sida som helst.

## <a name="usage-examples-of-promo-banners-in-e-commerce"></a>Användningsexempel för annonsbanderoller i näthandel

Annonsbanderoller kan användas i webbplatshuvudet för att visa erbjudanden som rör hela webbplatsen, som i följande exempel.

"Årlig rea slutar om 10 dagar"

"Spara stort med tillbaka till skolan-rea. Handla nu."

"Shoppa på Thanksgiving-rea!" 

Följande bild visar ett exempel på en annonsbanderoll.

![Exempel på en annonsbannermodul.](./media/ecommerce-Promobanner.PNG)

## <a name="promo-banner-module-properties"></a>Egenskaper för annonsbanderollmodul

| Egenskapsnamn             | Värde                              | beskrivning |
|---------------------------|------------------------------------|-------------|
| Banderollmeddelanden           | Text och länkar                     | En matris med text och länkar. |
| Spela upp automatiskt                  | **Sant** eller **falskt**              | Ett värde som anger om meddelanden markeras automatiskt genom, om flera meddelanden har konfigurerats. |
| Intervall för bildövergång | Ett antal millisekunder (MS)      | Det intervall som används för att flytta mellan meddelanden. |
| Tillåt avstängning             | **Sant** eller **falskt**              | Om värdet är inställt på **Sant** kan kunder stänga notifieringen. |
| Visa ikonen karusell     | **Sant** eller **falskt**              | Ett värde som anger om karusell-ikoner ska visas, så att kunder manuellt kan gå igenom flera olika banderollobjekt. |
| Textjustering            | **Höger**, **Vänster** eller **Centrera** | Textjusteringen i annonsbanderollmodulen. |
| Länka                      | En URL                              | URL:en för en valfri länk. |
|Textjustering             | **Höger**, **Vänster** eller **Centrera** | Denna egenskap finns som ett tematillägg för Adventure Works-temat. Med den kan en användare ställa in textjusteringen i kampanjbannern. |

> [!IMPORTANT]
> Adventure Works-temat finns tillgängligt från och med Dynamics 365 Commerce-version 10.0.20.

## <a name="add-a-promo-banner-module-to-a-page"></a>Lägg till annonsbanderollmodul till en sida 

Om du vill lägga till en annonsbanderollmodul på en sida och ställa in de obligatoriska egenskaperna följer du stegen nedan.

1. Gå till **mallar** och välj sedan **ny** för att skapa en ny mall.
1. I dialogrutan **Ny mall** under **Mallnamn**, ange **annonsbanderollmall** och välj sedan **OK**.
1. Under **Siddisposition**, lägg till en **Standardsida** i facket **Brödtext**. 
1. Välj **Slutför redigering** för att checka in mallen och välj sedan **publicera** för att publicera den. 
1. Använd den mall som du just skapade för att skapa en sida med namnet **sida för annonsbanderoll**. 
1. Lägg till platsen **Huvud** på ny sida, lägg till en behållarmodul. 
1. I fönstret till höger, ange värdet **Bredd** till **Fyll behållare**.
1. Under **Siddisposition**, lägg till en annonsbanderollmodul i behållarmodulen.
1. Lägg till ett eller flera banderollmeddelanden i inställningarna för banderollmodulen. Varje meddelande kan ha text tillsammans med en länk. Du kan redigera de andra egenskaperna om du vill anpassa modulen ytterligare.
1. Klicka på **Spara** och välj **Förhandsgranska** för att förhandsgranska sidan. Högst upp på sidan ska du se en notifiering med den tillagda texten.
1. Välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.

> [!NOTE]
> En annonsbanderoll används vanligtvis i sidhuvud- eller underrubrikfacket.

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över modulbibliotek](starter-kit-overview.md)

[Karusellmodul](add-carousel.md)

[Textblockmodul](add-content-rich-block.md)

[Innehållsblockmodul](add-hero-module.md)

[Modul för videospelare](add-video-player.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
