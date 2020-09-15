---
title: Flikmodulen
description: Det här avsnittet handlar om flikmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 06/01/2020
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
ms.openlocfilehash: b4187dfd704c78d506d7840b04c986687fe807a3
ms.sourcegitcommit: 4a981ee4be6d7e6c0e55541535d386bce2565cba
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/27/2020
ms.locfileid: "3621023"
---
# <a name="tab-module"></a>Flikmodulen

[!include [banner](includes/banner.md)]

Det här avsnittet handlar om flikmoduler och beskriver hur du lägger till dem till webbsidorna i Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Översikt

Flikmoduler är behållarmoduler som används för att ordna informationen på en webbplatssida på flikar. De kan användas på alla sidor där information måste visas på flikar.

I alla flikmoduler kan du lägga till en eller flera flikartikelmoduler. Varje flikartikelmodul representerar en enda flik. I varje modul kan en eller flera moduler läggas till. Det finns inga begränsningar för vilka typer av moduler som kan läggas till i flikartikelmodulen.

Följande bild visar ett exempel på en flikmodul på en webbplatssida. I det här exemplet är fliken **leverans** vald.

![Exempel på en flikmodul](./media/ecommerce-tab.PNG)

## <a name="tab-module-properties"></a>Flikmodulegenskaper

| Egenskapsnamn | Värden | beskrivning |
|---------------|--------|-------------|
| Rubrik | Text | Den här egenskapen anger en valfri textrubrik för modulen. |
| Aktivt flikindex | Antal | Den här egenskapen anger vilken flik som ska vara aktiv som standard när en sida läses in. Om inget värde anges är det första objektet i den första fliken aktivt som standard. |

## <a name="tab-item-module-properties"></a>Egenskaper för flikartikelmodul

| Egenskapsnamn | Värden | beskrivning |
|---------------|--------|-------------|
| Befattning | Text | Den här egenskapen anger en rubriktext för flikartikelmodulen. |

## <a name="add-a-tab-module-to-a-page"></a>Lägg till en flikmodul på en ny sida

Om du vill lägga till en flikmodul på en sida och ställa in de obligatoriska egenskaperna följer du stegen nedan.

1. Använd Fabrikam-marknadsföringsmallen (eller en mall utan begränsningar) om du vill skapa en ny sida med namnet **Sida för butikspolicyer**.
1. I platsen **Huvud** i **Standardsida** markerar du ellipsknappen (**...**) och väljer sedan **Lägg till modul**.
1. I dialogrutan **Lägg till modul**, välj modulen **Behållare** och klicka sedan på **OK**.
1. I facket **behållare** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.
1. I dialogrutan **Lägg till modul**, välj modulen **Flik** och klicka sedan på **OK**.
1. I egenskapsrutan i flikmodulen väljer du **rubrik** bredvid pennsymbolen.
1. I dialogrutan **Rubrik**, under **Rubriktext**, ange rubriktext (t.ex. **Policyer**). Välj sedan **OK**.
1. I facket **Flik** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.
1. I dialogrutan **Lägg till modul** välj modulen **Flikartikel** och sedan **OK**.
1. I egenskapsfönstret på flikartikelmodulen under **Rubrik**, ange rubriktext (till exempel **Leverans**).
1. I facket **Flikartikel** välj ellips-knappen (**...**) och välj sedan **Lägg till modulen**.
1. I dialogrutan **Lägg till modul**, välj modulen **Textblock** och klicka sedan på **OK**.
1. I egenskapsfönstret för textblockmodulen under **RTF**, ange en paragraf med text.
1. På platsen **flik** lägger du till ytterligare flikartikelmoduler som har titlar. Lägg till en textblockmodul som innehåller innehåll i varje flikartikelmodul.
1. Klicka på **Spara** och välj **Förhandsgranska** för att förhandsgranska sidan. På sidan visas en flik som innehåller flikartikelmoduler som har det innehåll du lagt till.
1. Välj **Slutför redigering** för att checka in sidan och välj sedan **publicera** för att publicera den.

## <a name="additional-resources"></a>Ytterligare resurser

[Startpaket – översikt](starter-kit-overview.md)

[Behållarmodul](add-container-module.md)

[Dragspelsmodulen](add-accordion.md)

[Textblockmodul](add-content-rich-block.md)