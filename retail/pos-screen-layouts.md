---
title: "Konfigurera skärmlayouter för kassa"
description: "Det här avsnittet innehåller information om skärmlayouter för Microsoft Dynamics 365 for Operations – Butikskassaupplevelser ."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application user
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 90573
ms.assetid: a6868f93-02ed-4928-9f6a-3b7383e7e399
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 7dee20166ea89b56523e3ef38e66de53d6e4a621
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017


---

# <a name="configure-screen-layouts-for-pos"></a>Konfigurera skärmlayouter för kassa

[!include[banner](includes/banner.md)]


Det här avsnittet innehåller information om skärmlayouter för Microsoft Dynamics 365 for Operations – Butikskassaupplevelser .

Microsoft Dynamics 365 for Operations – användargränssnittet för kassa kan konfigureras med en kombination av visuella profiler och skärmlayouter, tilldelade till butiker, kassor och/eller användare.

## <a name="visual-profile"></a>Visuell profil
Visuella profiler tilldelas till kassor och används för att ange visuella element som är kassaspecifika och delade för användare. Alla användare som loggar in på kassan har samma tema, färger och bilder. 

**Profilnummer** - Profilnumret är en unik identifierare för den visuella profilen. 

**Beskrivning** - Med beskrivningen kan du ange ett beskrivande namn som gör det lättare att identifiera korrekt profil för din situation.

**Tema** - Användare kan välja mellan programtema Ljus eller Mörk. Dessa inställningar påverkar teckensnitt och bakgrundsfärg i hela programmet.

**Accentfärg** - Accentfärgen används i hela kassan för att åtskilja eller framhäva vissa visuella element som rubriker, kommandoknappar eller hyperlänkar. Dessa element är vanligtvis åtgärdbara.

**Rubrikfärg** - Rubrikfärgen används att konfigurera färgen på sidhuvudet för att uppfylla återförsäljarens behov av varumärkesanpassning. Den här funktionen finns bara i Dynamics 365 for Operations version 1611.

**Inloggningsbakgrunder** - Användare kan ange en bakgrundsbild för inloggningsskärmen. Bakgrundsbildfilens storlek bör hållas så liten som möjligt, eftersom lagring och inläsning av stora filer kan påverka programfunktioner och prestanda.

**Programmets bakgrund** - Kassan kan också använda en bild som bakgrund i hela programmet i stället den fasta temafärgen. Med inloggningsbakgrunder rekommenderas du att hålla filstorleken så minimal som möjligt.

## <a name="screen-layouts"></a>Skärmlayouter
Skärmlayoutkonfigurationen avgör åtgärderna, innehållet i och placeringen av UI-kontrollerna på kassavälkomstskärmen och transaktionsskärmen. 

**Välkomstskärm**- I de flesta fall är välkomstskärmen den sida som användare ser när de först loggar in i kassan. Välkomstskärmen kan bestå av ett varumärke och knappsatser som ger åtkomst till kassaåtgärder. Åtgärder som inte är specifika för den aktuella transaktionen är oftast placerade här. 

**Transaktionsskärm** - Transaktionsskärmen är huvudskärmen i kassan för bearbetning av försäljningstransaktioner och order. Transaktionsskärmen kan konfigureras med skärmlayoutdesignern. 

**Standardstartskärm** - Vissa återförsäljare föredrar att kassören går direkt till transaktionsskärmen efter inloggning. Standardinställningarna för startskärmen gör att användare kan ställa in detta för varje skärmlayout.

### <a name="assignment"></a>Uppdrag

Skärmlayouter kan tilldelas på butik-, kassa- och användarnivå. Användartilldelningen åsidosätter kassa- och butikstilldelningen, och kassatilldelningen åsidosättningar butikstilldelningen. I ett enkelt scenario där alla användare använder samma layout oavsett kassa eller roll kan skärmlayouten endast anges för butiken. I de fall där vissa kassor eller användare kräver specialiserade layouter, kan de tilldelas på därefter.

### <a name="layout-sizes"></a>Layoutstorlekar

Den här funktionen gäller bara Dynamics 365 for Operations version 1611. Eftersom skärmlayouter i många fall kan användas för flera skärmstorlekar och upplösningar, kan användare konfigurera sin layout och sitt innehåll för var och en. Kassaprogrammet väljer automatiskt den närmaste layoutstorleken för enheten vid tiden för start. En skärmlayout kan även innehålla konfigurationer för både fullstora och kompakta enheter. Med den här konfigurationen kan en användare tilldelas till en enda skärmlayout som fungerar för olika storlekar och formfaktorer i butiken. 

**Modern POS - fullständig** - Fullständig layouter används oftast bäst för större skärmar, till exempel datorskärmar eller surfplattor. Du kan välja vilka gränssnittselement som ska ingå, bestämma deras storlek och placering och konfigurera de detaljerade egenskaperna. Fullständiga layouter stöder både stående och liggande konfigurationer. 

**Modern POS - komprimerad** - Komprimerad layout används oftast bäst för telefoner eller små surfplattor. Designmöjligheter är begränsade för kompakta enheter. Användare kan konfigurera kolumner och fält för kvitto- och summarfönster.

### <a name="screen-layout-designer"></a>Layoutdesigner för skärm

Varje layoutstorlek inom en skärmlayout måste konfigureras med skärmlayoutdesignern. Med designern kan användarna ange och konfigurera UI-elementen på transaktionsskärmen. Skärmlayoutdesignern använder ClickOnce för att hämta, installera och starta den senaste versionen av programmet varje gång användaren öppnar den. Kontrollera webbläsarkraven för ClickOnce. Vissa webbläsare, t ex Chrome, kräver tillägg. 

**Numerisk knappsats** - Den numeriska knappsatsen är den huvudsakliga användarinmatningen på kassans transaktionsskärm. Den kan konfigureras så att hela knappsatsen visas på skärmen, vilket är perfekt för pekskärmar, eller bara de inmatningsfältet, som kan användas med ett fysiskt tangentbord. Inställningarna för knappsats finns bara i den fullständiga layouten. I Dynamics 365 for Operations version 1611 har komprimerade layouter alltid den fullständig knappsats tillgänglig via transaktionsskärmen.

**Summapanel** - Summapanelen kan konfigureras i en eller två kolumner för att visa fält som radantal, rabattbelopp, avgifter, delsumma och moms. I Dynamics 365 for Operations version 1611 stöder komprimerade layouter endast summor i en kolumn. 

**Kvitto** - Kvittopanelen innehåller försäljningsrader, betalningsraderna och leveransinformation för produkterna och tjänsterna som bearbetas i kassan. Användare kan ange kolumner, bredd och placering. I komprimerade layouter för Dynamics 365 for Operations version 1611 kan du också konfigurera ytterligare information som visas i en rad under huvudraden. 

**Kundkort** - Kundkortet visar information som hör till kunden som är kopplade till transaktionen. Kundkortet kan konfigureras för att dölja eller visa ytterligare information. 

**Flikkontroll** - Flikkontrollen kan placeras på skärmlayouten, och andra kontroller, till exempel numeriskt knappsats, kundkort eller knapprutnät kan placeras på fliken. Flikkontrollen är en behållare som hjälper användarna att få plats med mer innehåll på skärmen. Flikkontrollen är bara tillgänglig för fullständiga layouter. 

**Bild** - Bildkontrollen kan användas för att visa butikens logotyp eller annat varumärke på transaktionsskärmen. Bildkontrollen är bara tillgänglig för fullständiga layouter. 

**Rekommenderade produkter** - Om det är konfigurerat för miljön, visar kontrollen för rekommenderade produkter produktförslag baserade på maskininlärning. Kontrollen för rekommenderade produkter är bara tillgänglig för fullständiga layouter i Dynamics 365 for Operations version 1611. **Anpassad kontroll **- Den anpassade kontrollen fungerar som platshållare i skärmlayouten så att du kan reservera utrymme för anpassat innehåll. Den anpassade kontrollen är bara tillgänglig för fullständiga layouter.

<a name="see-also"></a>Se även
--------

[Installera layoutdesignern Retail POS](install-pos-layout-designer.md)




