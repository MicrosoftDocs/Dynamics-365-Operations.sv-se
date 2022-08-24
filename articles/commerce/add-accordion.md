---
title: Dragspelsmodul
description: Denna artikel handlar om dragspelsmoduler och beskriver hur du lägger till dem på webbsidorna i Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: ec895476770f297825d6c88d0b0a5fef43a5c6ef
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9279167"
---
# <a name="accordion-module"></a>Dragspelsmodul

[!include [banner](includes/banner.md)]

Denna artikel handlar om dragspelsmoduler och beskriver hur du lägger till dem på webbsidorna i Microsoft Dynamics 365 Commerce.

Dragspelsmoduler är sådana moduler som används för att organisera informationen eller modulerna på en sida genom att tillhandahålla en komprimerbar kassalådeliknande funktion. En dragspelsmodul kan användas på valfri sida.

Inne i alla dragspelsmoduler kan du lägga till en eller flera dragspelsartikelmoduler. Varje dragspelsartikelmodul representerar en komprimerbar kassalåda. Inne i alla dragspelsartikelmoduler kan du lägga till en eller flera moduler. Det finns inga begränsningar för vilka typer av moduler som kan läggas till i dragspelsartikelmodulen.

Följande bild visar ett exempel på en dragspelsartikelmodul som används för att ordna information på en butikssida med vanliga frågor (FAQ).

![Exempel på en dragspelsmodul.](./media/ecommerce-accordion.PNG)

## <a name="accordion-module-properties"></a>Egenskaper för dragspelsmodul

| Egenskapsnamn | Värden | beskrivning |
|---------------|--------|-------------|
| Rubrik | Text | Den här egenskapen anger en valfri textrubrik för dragspelsmodul. |
| Expandera alla | **Sant** eller **falskt** | Om värdet är inställt på **True** är funktionen visa/dölj aktiverad, så att alla artiklar i dragspelsmodulen kan expanderas och komprimeras. |
| Interaktionsstil | **Oberoende** eller **expandera endast en artikel** | Den här egenskapen definierar interaktionstypen för dragspelsartiklar. Om värdet är inställt på **oberoende** kan varje dragspelsartikel expanderas eller komprimeras separat. Om värdet är inställt på att **expandera endast en artikel**, kan endast en artikel expanderas åt gången. När artiklar expanderas, döljs tidigare expanderade artiklar. |

## <a name="accordion-item-module-properties"></a>Egenskaper för dragspelsartikelmodul

| Egenskapsnamn | Värden | beskrivning |
|----------------|--------|-------------|
| Befattning | Text | Den här egenskapen anger en rubriktext för dragspelsartikelmodulen. Genom att välja rubrikområdet kan användarna utöka eller komprimera avsnittet. |
| Expandera som standard | **Sant** eller **falskt** | Om värdet är inställt på **True** expanderas dragspelsartikeln som standard när sidan läses in. |

## <a name="add-an-accordion-module-to-a-faq-page"></a>Lägg till dragspelsartikelmodul till en sida med vanliga frågor

Om du vill lägga till en dragspelsmodul på en sida för vanliga frågor och konfigurera egenskaperna i webbplatsskaparen följer du stegen nedan.

1. Gå till **Sidor** och använd Fabrikam-marknadsföringsmallen (eller en mall utan begränsningar) om du vill skapa en ny sida med namnet **Vanliga frågor om butiken**.
1. I platsen **Huvud** i **Standardsida** markerar du ellipsknappen (**...**) och väljer sedan **Lägg till modul**.
1. I dialogrutan **Välj moduler**, välj modulen **Behållare** och klicka sedan på **OK**.
1. I facket **behållare** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.
1. I dialogrutan **Välj moduler**, välj modulen **Dragspel** och klicka sedan på **OK**.
1. I egenskapsrutan i dragspelsmodulen väljer du **rubrik** bredvid pennsymbolen.
1. I dialogrutan **Rubrik** under **Rubriktext**, ange **Vanliga frågor**. Välj sedan **OK**.
1. Välj egenskapspanelen för dragspelsmodulen, markera kryssrutan **Visa expandera alla** och sedan i fältet **interaktionsstil** väljer du **oberoende**.
1. I facket **dragspel** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.
1. I dialogrutan **Välj moduler**, välj modulen **Dragspelsartikel** och klicka sedan på **OK**.
1. I egenskapsfönstret på dragspelsartikelmodulen under **Rubrik**, ange rubriktext (till exempel **Hur du returnerar arbete**).
1. I facket **dragspelsartikeln** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.
1. I dialogrutan **Välj moduler**, välj modulen **Textblock** och klicka sedan på **OK**.
1. Skriv ett textstycke i egenskapsfönstret för textblockmodulen (till exempel **returerna måste t.ex. ha bearbetats via kundtjänst. Kontakt 1-800-FABRIKAM för returer. Produkter har en policy på 30 dagar. Returer måste initieras inom denna tidsram.**).
1. På platsen **Dragspel**, lägg till fler dragspelsartikelmoduler. Lägg till en textblockmodul som innehåller innehåll i varje dragspelsartikelmodul.
1. Klicka på **Spara** och välj **Förhandsgranska** för att förhandsgranska sidan. Sidan visar en dragspelsmodul som har det innehåll du har lagt till.
1. Välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt över modulbibliotek](starter-kit-overview.md)

[Behållarmodul](add-container-module.md)

[Flikmodul](add-tab.md)

[Textblockmodul](add-content-rich-block.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
