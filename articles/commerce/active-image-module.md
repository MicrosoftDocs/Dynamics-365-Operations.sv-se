---
title: Aktiv bildmodul
description: Denna artikel omfattar aktiva bildmoduler och beskriver hur du lägger till dem på webbsidorna i Microsoft Dynamics 365 Commerce.
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
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 3d532d21f847a80a16af814eeaf097a616605795
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8853860"
---
# <a name="active-image-module"></a>Aktiv bildmodul

[!include [banner](includes/banner.md)]

Denna artikel omfattar aktiva bildmoduler och beskriver hur du lägger till dem på webbsidorna i Microsoft Dynamics 365 Commerce.

En aktiv bildmodul kan användas för att bädda in produkttaggar i en bild. Användare som använder näthandel kan sedan hovra över taggarna för att förhandsgranska produkter som visas i bilden. Förhandsgranskningarna visas i popup-fönster. Genom att välja ett förhandsgranskningsfönster kan användarna gå direkt till sidan produktinformation (PDP) för motsvarande produkt.

Taggarna definieras med X- och Y-koordinater på bilden. Varje taggad punkt bör konfigureras med produkt-ID:t för den produkt som visas i bilden.

I följande bild visas ett exempel på ett popup-fönster för förhandsgranskning i en fokusbild på startsidan för Adventure Works.

![Exempel på ett popup-fönster för förhandsgranskning i en aktiv bildmodul](./media/Active_image.PNG)

> [!IMPORTANT]
> - Den aktiva bildmodulen finns tillgänglig från och med Dynamics 365 Commerce-version 10.0.20.
> - Den aktiva modulen presenteras i Adventure Works-temat.

## <a name="active-image-module-properties"></a>Egenskaper för aktiv bildmodul

| Egenskapsnamn      | Värden | beskrivning |
|--------------------|--------|-------------|
| Bild              | Bildfil | En bild kan användas för att presentera en eller flera produkter. Bilden kan överföras till mediebiblioteket i Commerce-webbplatsbyggaren, eller också kan en befintlig bild användas. |
| Bredd              | Antal pixlar | Denna egenskap anger bildens bredd. De aktiva koordinaterna beräknas utifrån bildens bredd.|
| Aktiva koordinater | X- och Y-koordinater samt ett produkt-ID-nummer | Varje aktiv bildmatris består av X- och Y-koordinater och ett produkt-ID-nummer.|
| Rubrik            | Rubriktext och rubriktagg (**H1**, **H2**, **H3**, **H4**, **H5** eller **H6**) | Som standard används rubriktaggen **H2** för rubriken, men taggen kan ändras i syfte att uppfylla tillgänglighetskraven. |
| Stycke          | Stycketext | Modulen har stöd för stycketext i RTF-format. Vissa grundläggande RTF-funktioner stöds, t.ex. hyperlänkar samt fetstil, understrykning och kursiv text. Vissa av dessa funktioner kan åsidosättas av det sidtema som används i modulen. |
| Länka               | Länktext, länk-URL, ARIA-etikett (Accessible Rich Internet Applications) samt väljaren **Öppna länk i ny flik** | Modulen stöder en eller flera "uppmaning till åtgärd"-länkar. Om en länk läggs till, en länktext, en URL-adress och en ARIA-etikett krävs. ARIA-etiketter ska vara beskrivande i syfte att uppfylla tillgänglighetskraven. Länkar kan konfigureras så att de öppnas på en ny flik. |
| Undertext           | Rubrik, text och länkar | Du kan lägga till ytterligare kontext för bilden, till exempel namnet på författaren eller designern, eller länkar till personliga bloggar.|
| Texttema         | **Ljus** eller **Mörk** | Med denna egenskap kan en användare konfigurera texten som ljus eller mörk baserat på bakgrundsbild. Den finns som ett tematillägg för Adventure Works. |

## <a name="add-an-active-image-module-to-a-new-page"></a>Lägg till en aktiv bildmodul på en ny sida

Om du vill lägga till en aktiv bildmodul på en ny sida och konfigurera erforderliga egenskaper följer du stegen nedan.

1. Gå till **Mallar** och öppna marknadsföringsmallen för webbplatsens startsida (eller skapa en ny marknadsföringsmall).
1. I platsen **Huvud** i standardsida markerar du ellipsknappen (**...**) och väljer sedan **Lägg till modul**.
1. I dialogrutan **Välj moduler**, välj modulen **Aktiv bild** och klicka sedan på **OK**.
1. Välj **Spara**, välj **Slutför redigering** för att checka in mallen och välj sedan **publicera** för att publicera den.
1. Gå till **Sidor** och öppna webbplatsens startsida (eller skapa en ny startsida med hjälp av marknadsföringsmallen).
1. I platsen för standardsidan väljer du **Huvud**, markerar ellipsknappen (**...**) och väljer sedan **Lägg till modul**.
1. I dialogrutan **Välj moduler**, välj modulen **Aktiv bild** och klicka sedan på **OK**.
1. Lägg till en bild i egenskapsfönstret för den aktiva bildmodulen och ställ in arbetsytans bredd till bildens storlek.
1. Ställ in X- och Y-koordinaterna och lägg till lämpligt produkt-ID-nummer.
1. Lägg till och konfigurera ytterligare aktiva bildmoduler efter behov.
1. Klicka på **Spara** och välj **Förhandsgranska** för att förhandsgranska sidan.
1. Välj **Slutför redigering** för att checka in mallen och välj sedan **publicera** för att publicera den.

## <a name="additional-resources"></a>Ytterligare resurser

[Modulbibliotek – översikt](starter-kit-overview.md)

[Adventure Works-tema](adventure-works-theme.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
