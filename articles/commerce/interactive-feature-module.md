---
title: Interaktiv funktionsmodul
description: Denna artikel innehåller interaktiva funktionsmoduler och beskriver hur du lägger till dem på webbsidor i Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: deee7c35cfc4293480fda74665429121b71bbfab
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8898529"
---
# <a name="interactive-feature-module"></a>Interaktiv funktionsmodul

[!include [banner](includes/banner.md)]

Denna artikel innehåller interaktiva funktionsmoduler och beskriver hur du lägger till dem på webbsidor i Microsoft Dynamics 365 Commerce.

Interaktiva funktionsmoduler är mosaikliknande moduler som kan användas för att marknadsföra flera olika produktkategorier eller produktmärken genom en kombination av bilder och text. En återförsäljare kan till exempel lägga till en interaktiv funktionsmodul på startsidan för en näthandelsplats i syfte att framhäva bästsäljande kategorier. Den interaktiva funktionsmodulen liknar modulen i ikonlistan men har en annan layout och olika interaktionsfunktioner.

Varje modul för interaktiva funktioner är en samling interaktiva artikelmoduler. Varje modul för funktionsartikel drivs av data från innehållshanteringssystemet (CMS). Detta beror inte på några andra moduler eller data från Commerce headquarters. Den interaktiva funktionsmodulen kan läggas till på alla webbplatssidor där en återförsäljare vill marknadsföra eller framhäva något (t.ex. produkter, kategorier eller varumärken).

> [!IMPORTANT]
> - Den interaktiva funktionsmodulen finns tillgänglig från och med Dynamics 365 Commerce-version 10.0.20.
> - Den interaktiva funktionsmodulen presenteras i Adventure Works-temat.

I följande bild visas ett exempel på en interaktiv funktionsmodul på startsidan för Adventure Works.

![Exempel på en interaktiv funktionsmodul på startsidan för Adventure Works](./media/Feature.PNG)

## <a name="interactive-feature-module-and-themes"></a>Interaktiv funktionsmodul och teman

Den interaktiva funktionsmodulen kan stödja olika layouter och stilar baserat på ett tema. I till exempel Adventure Works-temat innehåller den interaktiva funktionsmodulen en tvåkolumnslayout som visar animationseffekter när en webbplatsanvändare hovrar över varje objekt. Den interaktiva funktionsmodulen är optimerad för ett jämnt antal bilder som finns placerade i en layout med två kolumner.

## <a name="interactive-feature-module-properties"></a>Egenskaper för interaktiv funktionsmodul

| Egenskapsnamn | Värden | beskrivning |
|---------------|--------|-------------|
| Rubrik       | Rubriktext och rubriktagg (**H1**, **H2**, **H3**, **H4**, **H5** eller **H6**) | En textrubrik för den interaktiva funktionsmodulen. |

## <a name="interactive-feature-item-module-properties"></a>Egenskaper för interaktiv funktionsartikelmodul

| Egenskapsnamn | Värden | beskrivning |
|---------------|--------|-------------|
| Bild         | Bildfil | En bild som representerar en produkt eller en kategori. Bilden kan överföras till mediebiblioteket i Commerce-webbplatsbyggaren, eller också kan en befintlig bild användas. |
| Rubrik       | Rubriktext och rubriktagg (**H1**, **H2**, **H3**, **H4**, **H5** eller **H6**) | Som standard används rubriktaggen **H2** för rubriken, men taggen kan ändras i syfte att uppfylla tillgänglighetskraven. |
| Stycke     | Stycketext | Modulen har stöd för stycketext i RTF-format. Vissa grundläggande RTF-funktioner stöds, t.ex. hyperlänkar samt fetstil, understrykning och kursiv text. Vissa av dessa funktioner kan åsidosättas av det sidtema som används i modulen. |
| Länka          | Länktext, länk-URL, ARIA-etikett (Accessible Rich Internet Applications) samt väljaren **Öppna länk i ny flik** | Modulen stöder en eller flera "uppmaning till åtgärd"-länkar. Om en länk läggs till, en länktext, en URL-adress och en ARIA-etikett krävs. ARIA-etiketter ska vara beskrivande i syfte att uppfylla tillgänglighetskraven. Länkar kan konfigureras så att de öppnas på en ny flik. |

## <a name="add-an-interactive-feature-module-to-a-new-page"></a>Lägg till en interaktiv funktionsmodul på en ny sida

Om du vill lägga till en interaktiv funktionsmodul på en ny sida och konfigurera erforderliga egenskaper i Commerce-webbplatsskaparen följer du stegen nedan.

1. Gå till **Mallar** och öppna marknadsföringsmallen för webbplatsens startsida (eller skapa en ny marknadsföringsmall).
1. I platsen **Huvud** i standardsida markerar du ellipsknappen (**...**) och väljer sedan **Lägg till modul**.
1. I dialogrutan **Välj moduler** väljer du modulen **Interaktiv funktion** och sedan **OK**.
1. Välj **Spara**, välj **Slutför redigering** för att checka in mallen och välj sedan **publicera** för att publicera den.
1. Gå till **Sidor** och öppna webbplatsens startsida (eller skapa en ny startsida med hjälp av marknadsföringsmallen).
1. I platsen för standardsidan väljer du **Huvud**, markerar ellipsknappen (**...**) och väljer sedan **Lägg till modul**.
1. I dialogrutan **Välj moduler**, under **Välj moduler**, väljer du modulen **Interaktiv funktion** och sedan **OK**.
1. Lägg till en rubrik i egenskapsfönstret för den interaktiva funktionsmodulen.
1. På platsen **Interaktiv funktion** väljer du ellipsknappen (**...**) och sedan **Lägg till modul**.
1. I dialogrutan **Välj moduler** väljer du modulen **Interaktiv funktionsartikel** och sedan **OK**.
1. Lägg till en bild, en rubriktext, ett textstycke och en URL i egenskapsfönstret för den interaktiva funktionens artikelmodul.
1. Lägg till och konfigurera ytterligare interaktiva funktionsartikelmoduler efter behov.
1. Klicka på **Spara** och välj **Förhandsgranska** för att förhandsgranska sidan.
1. Välj **Slutför redigering** för att checka in mallen och välj sedan **publicera** för att publicera den.

## <a name="additional-resources"></a>Ytterligare resurser

[Modulbibliotek – översikt](starter-kit-overview.md)

[Adventure Works-tema](adventure-works-theme.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
