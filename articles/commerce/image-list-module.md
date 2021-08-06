---
title: Bildlistmodul
description: Detta ämne handlar om bildlistmoduler och beskriver hur du lägger till dessa på webbsidor i Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 07/08/2021
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
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: b7e070bfe562bb1a28b10d4632725b53a090cda4
ms.sourcegitcommit: e42c7dd495829b0853cebdf827b86a7cf655cf86
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/17/2021
ms.locfileid: "6638840"
---
# <a name="image-list-module"></a>Bildlistmodul

[!include [banner](includes/banner.md)]

Detta ämne handlar om bildlistmoduler och beskriver hur du lägger till dessa på webbsidor i Microsoft Dynamics 365 Commerce.

Bildlistmodulen kan användas för att på ett enkelt sätt lägga till en samling (matris) av bilder på webbplatssidor. Varje bild i matrisen kan konfigureras med textstycken och länk-webbadresser (URL). Bildlistmodulen är bäst lämpad för visning av märkeslogotyper eller en lista som innehåller logotyper.

> [!IMPORTANT]
> - Bildlistmodulen finns tillgänglig i modulbiblioteket för Commerce per Dynamics 365 Commerce-version 10.0.20.
> - Bildlistmodulen ingår i Adventure Works-temat.

I följande bild visas ett exempel där en bildlistmodul visar en lista med text som innehåller logotyper på en Adventure Works-webbplats för Business-to-consumer (B2C).

![Exempel på en bildlistmodul som visar en lista med text som innehåller logotyper](./media/Image_list.PNG)

I följande bild visas ett exempel där en bildlistmodul visar varumärkeslogotyper på en Adventure Works-webbplats för Business-to-business (B2B).

![Exempel på en modul för bildlista som visar märkeslogotyp](./media/Image_list_B2B.PNG)

## <a name="image-list-module-properties"></a>Egenskaper för bildlistmodul

| Egenskapsnamn | Värden | beskrivning |
|---------------|--------|-------------|
| Rubrik       | Rubriktext och rubriktagg (**H1**, **H2**, **H3**, **H4**, **H5** eller **H6**) | En textrubrik för bildlistmodulen. |
| Bildlista    | Bilder, text och URL-adresser | Varje artikel i matrisen är en bild som medföljer stycketext och en URL-adress. |

## <a name="add-an-image-list-module-to-a-new-page"></a>Lägg till en bildlistmodul på en ny sida

Om du vill lägga till en modul för bildlista på en ny sida och ställa in erforderliga egenskaper i Commerce-webbplatsskaparen följer du stegen nedan.

1. Gå till **Mallar** och öppna marknadsföringsmallen för webbplatsens startsida (eller skapa en ny marknadsföringsmall).
1. I platsen **Huvud** i standardsida markerar du ellipsknappen (**...**) och väljer sedan **Lägg till modul**.
1. I dialogrutan **Lägg till modul** väljer du modulen **Bildlista** och sedan **OK**.
1. Välj **Spara**, välj **Slutför redigering** för att checka in mallen och välj sedan **publicera** för att publicera den.
1. Gå till **Sidor** och öppna webbplatsens startsida (eller skapa en ny startsida med hjälp av marknadsföringsmallen).
1. I platsen för standardsidan väljer du **Huvud**, markerar ellipsknappen (**...**) och väljer sedan **Lägg till modul**.
1. I dialogrutan **Lägg till modul** väljer du **Bildlista** och sedan **OK**.
1. Lägg till en rubrik (till exempel **Våra varumärken**) i egenskapsfönstret för bildlistmodulen.
1. Lägg till en bildlistartikel och ange en bild, lite stycketext och en omdirigerings-URL.
1. Lägg till och konfigurera ytterligare moduler för bildlistartiklar efter behov.
1. Klicka på **Spara** och välj **Förhandsgranska** för att förhandsgranska sidan.
1. Välj **Slutför redigering** för att checka in mallen och välj sedan **publicera** för att publicera den.

## <a name="additional-resources"></a>Ytterligare resurser

[Modulbibliotek – översikt](starter-kit-overview.md)

[Adventure Works-tema](adventure-works-theme.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
