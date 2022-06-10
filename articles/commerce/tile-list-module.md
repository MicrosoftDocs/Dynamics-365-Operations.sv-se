---
title: Panellistmodul
description: Detta ämne handlar om panellistmoduler och beskriver hur du lägger till dessa på webbsidorna i Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: dd714f29fe2f9acd459be7bda1c0bfac65b72cb0
ms.sourcegitcommit: ccb39767bd3430c24f4653c26560bba2cd66553c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2022
ms.locfileid: "8780803"
---
# <a name="tile-list-module"></a>Panellistmodul

[!include [banner](includes/banner.md)]

Detta ämne handlar om panellistmoduler och beskriver hur du lägger till dessa på webbsidorna i Microsoft Dynamics 365 Commerce.

En panellistmodul är en samling paneler i en karusell. Denna används för att marknadsföra produktkategorier eller produktvarumärken via bilder och text. En återförsäljare kan till exempel lägga till en panellistmodul på startsidan för en e-handelsplats i syfte att framhäva alla bästsäljande kategorier.

Panellistmodulen drivs av data från innehållshanteringssystemet (CMS). Detta beror inte på några andra moduler eller data från Commerce-administrationen. Panellistmodulen kan läggas till på alla webbplatssidor där en återförsäljare vill marknadsföra eller framhäva något (t.ex. produkter, kategorier eller varumärken).

I följande bild visas ett exempel på en modul för panellistor och panelmoduler på startsidan för Adventure Works.

![Exempel på en panellistmodul och panelmoduler på startsidan för Adventure Works](./media/Tile_list.PNG)

> [!IMPORTANT]
> Panellistmodulen finns tillgänglig från och med Dynamics 365 Commerce-version 10.0.20.
> Panellistmodulen ingår i Adventure Works-temat.

## <a name="tile-list-modules-and-themes"></a>Moduler och teman i panellista

Panellistmodulen kan stödja olika layouter och stilar baserat på ett tema. I Adventure Works-temat visas till exempel en animeringseffekt när webbplatsanvändarna hovrar över dem. Varje tema kan innehålla ytterligare egenskaper för panellistan och panelmodulerna. Temautvecklare kan även skapa ytterligare layouter för panellistan och panelmodulerna.

## <a name="tile-list-module-properties"></a>Egenskaper för panellistmodul

| Egenskapsnamn | Värden | beskrivning |
|---------------|--------|-------------|
| Rubrik       | Rubriktext och rubriktagg | En textrubrik för panellistmodulen. |

## <a name="tile-module-properties"></a>Egenskaper för panelmodul

| Egenskapsnamn | Värden | beskrivning |
|---------------|--------|-------------|
| Bild         | Bildfil | En bild kan användas för att presentera en produkt eller en kategori. Bilden kan överföras till mediebiblioteket i Commerce-webbplatsbyggaren, eller också kan en befintlig bild användas. |
| Rubrik       | Rubriktext och rubriktagg (**H1**, **H2**, **H3**, **H4**, **H5** eller **H6**) | Som standard används rubriktaggen **H2** för rubriken, men taggen kan ändras i syfte att uppfylla tillgänglighetskraven. |
| Stycke     | Stycketext | Modulen har stöd för stycketext i RTF-format. Vissa grundläggande RTF-funktioner stöds, t.ex. hyperlänkar samt fetstil, understrykning och kursiv text. Vissa av dessa funktioner kan åsidosättas av det sidtema som används i modulen. |
| Länka          | Länktext, länk-URL, ARIA-etikett (Accessible Rich Internet Applications) och **öppna länk i ny flik** | Moduler stöder en eller flera "Uppmaning till åtgärd"-länkar. Om en länk läggs till, en länktext, en URL-adress och en ARIA-etikett krävs. ARIA-etiketter ska vara beskrivande i syfte att uppfylla tillgänglighetskraven. Länkar kan konfigureras så att de öppnas på en ny flik. |
| Panellänk     | Länktext, länk-URL, ARIA-etikett och väljaren **Öppna länk i ny flik** | Den här egenskapen används för att definiera en "Uppmaning till åtgärd"-länk. Om en länk läggs till, en länktext, en URL-adress och en ARIA-etikett krävs. ARIA-etiketter ska vara beskrivande i syfte att uppfylla tillgänglighetskraven. Länkar kan konfigureras så att de öppnas på en ny flik.|
| Ikon          | Bild | Utöver en produkt- eller kategoribild kan en ikonsymbol läggas till. Ikonsymbolbilden visas ovanför produkt- eller kategoribilden. |

## <a name="add-a-tile-list-module-to-a-new-page"></a>Lägg till en modul för panellista på en ny sida

Om du vill lägga till en modul för panellista på en ny sida och ställa in de obligatoriska egenskaperna följer du stegen nedan.

1. Gå till **Mallar** och öppna marknadsföringsmallen för webbplatsens startsida (eller skapa en ny marknadsföringsmall).
1. I platsen **Huvud** i standardsida markerar du ellipsknappen (**...**) och väljer sedan **Lägg till modul**.
1. I dialogrutan **Välj moduler**, välj modulen **panellista** och klicka sedan på **OK**.
1. Välj **Spara**, välj **Slutför redigering** för att checka in mallen och välj sedan **publicera** för att publicera den.
1. Gå till **Sidor** och öppna webbplatsens startsida (eller skapa en ny startsida med hjälp av marknadsföringsmallen).
1. I platsen för standardsidan väljer du **Huvud**, markerar ellipsknappen (**...**) och väljer sedan **Lägg till modul**.
1. I dialogrutan **Välj moduler**, välj modulen **panellista** och klicka sedan på **OK**.
1. Lägg till en rubrik i egenskapsfönstret för panellistmodulen.
1. På platsen **Panellista** väljer du ellipsknappen (**...**) och sedan **Lägg till modul**.
1. I dialogrutan **Välj moduler**, välj modulen **panelmodul** och klicka sedan på **OK**.
1. Lägg till en bild, en rubrik och en ikonsymbolbild i egenskapsfönstret i panelmodulen.
1. Lägg till och konfigurera ytterligare panelmoduler efter behov.
1. Klicka på **Spara** och välj **Förhandsgranska** för att förhandsgranska sidan.
1. Välj **Slutför redigering** för att checka in mallen och välj sedan **publicera** för att publicera den.

## <a name="additional-resources"></a>Ytterligare resurser

[Modulbibliotek – översikt](starter-kit-overview.md)

[Adventure Works-tema](adventure-works-theme.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
