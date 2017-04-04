---
title: "Konfigurera skärmar för kassa"
description: "Det här avsnittet innehåller information om skärmar för Microsoft Dynamics 365 för verksamhet – Retail mittpunkt erfarenheter försäljning (PO)."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application user
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 90573
ms.assetid: a6868f93-02ed-4928-9f6a-3b7383e7e399
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: d49c5c9773047940e524c71e59a674ebe8460ad7
ms.lasthandoff: 03/31/2017


---

# <a name="configure-screen-layouts-for-pos"></a>Konfigurera skärmar för kassa

Det här avsnittet innehåller information om skärmar för Microsoft Dynamics 365 för verksamhet – Retail mittpunkt erfarenheter försäljning (PO).

Microsoft Dynamics 365 för verksamhet – Retail mittpunkt försäljning (PO)-användargränssnittet kan konfigureras med en kombination av visuella profiler och Skärmlayouter, tilldelade till butiker, kassor och/eller användare.

## <a name="visual-profile"></a>Visuell profil
Visuella profiler har tilldelats register och används för att ange visuella element som är specifika för register och delade för användare. Alla användare som loggar in på registret som har samma tema, färger och bilder. **Profilnummer** -profil numret är en unik identifierare för den visuella profilen. **Beskrivning** -beskrivningen kan du ange ett beskrivande namn som gör det lättare för att identifiera korrekt profil för din situation. **Temat** -användare kan välja mellan programmappen themes ljus eller mörk. Dessa inställningar påverkar teckensnitt och bakgrundsfärg färgerna i hela programmet. **Dekorfärg färg** -tilläggsfärgen ska användas i KASSAN för att skilja eller framhäva vissa visuella element som rubriker, kommandoknappar eller hyperlänkar. Dessa element är vanligtvis redigerbart. **Färgen på rubriken** -huvudet färgen används att konfigurera färgen på sidhuvudet för att uppfylla behoven hos återförsäljaren anpassning. Den här funktionen finns bara i Dynamics 365 för operationer version 1611. **Bakgrunder inloggning** -användare kan ange en bakgrundsbild för inloggningsskärmen. Bakgrundsbilder filens storlek bör hållas så liten som möjligt, som lagring och inläsning av stora filer kan påverka programfunktioner och prestanda. **Programmets bakgrund** -The POS kan också använda en bild som bakgrund i hela programmet i stället för fasta Temafärg. Med inloggning bakgrund, rekommenderas att hålla nere filstorleken så minimal som möjligt.

## <a name="screen-layouts"></a>Skärmlayouter
Skärmen layoutdesignern konfigurationsnyckeln avgör placeringen av UI-kontrollerna i POS välkomstskärmen och transaktionen skärmen, innehåll och åtgärder. ** Välkomstskärmen **-välkomstskärmen i de flesta fall är den sida som användare ser när de först loggar in POS. Välkomstskärmen kan bestå av ett varumärke och knappsatser som ger åtkomst till POS operationer. Åtgärder som inte är specifika för den aktuella transaktionen är oftast placerade här. **Transaktionen skärmen** -Transaction skärmen är huvudskärmen i KASSAN för bearbetning av försäljningstransaktioner och order. Skärmen transaktionen kan konfigureras med Layoutdesigner för skärm. **Standard startskärmen** -återförsäljare vissa föredrar att kassören gå direkt till fönstret transaktionen efter inloggning. Standardinställningen start skärmen kan du göra detta för varje skärmlayout.

### <a name="assignment"></a>Uppdrag

Skärmar kan tilldelas på butiken, register eller användare. Tilldelningen användare åsidosätter kassan och spara tilldelningen och register tilldelningen åsidosättningar butiken tilldelningen. I ett enkelt scenario där alla användare använder samma layout oavsett registrera- eller kan skärmlayout endast anges på butiken. I de fall där vissa register eller användare kräver specialiserad layouter, kan de tilldelas på rätt sätt.

### <a name="layout-sizes"></a>Layoutstorlekar

Den här funktionen gäller endast Dynamics 365 för operationer version 1611. Eftersom det i många fall skärmar kan användas över flera skärmstorlekar och lösningar, konfigurera användare layout och innehåll för alla. POS-programmet väljer automatiskt layout närmast storlek för enheten vid tiden för start. En skärmlayout kan även innehålla konfigurationer för både full och komprimera enheter. Låter en användare måste tilldelas till en enda skärmlayout fungerar i olika storlekar och formfaktorer i butiken. **Modern POS - Full** -fullständig layouter används oftast bäst för större visar till exempel datorskärm eller Tablet PC. Du kan välja vilka gränssnittselement att inkluderar bestämmer deras storlek och placering och konfigurera de detaljerade egenskaperna. Fullständig layouter stöder både stående och liggande konfigurationer. **Komprimera modern POS -** -kompakt layout används oftast bäst för telefoner eller små Tablet-datorer. Kreativa möjligheter begränsas för kompakta enheter. Användare kan konfigurera kolumner och fält för kvitto- och rutor.

### <a name="screen-layout-designer"></a>Layoutdesigner för skärm

Varje layout storlek inom en skärmlayout måste konfigureras med Layoutdesigner för skärm. Designern kan användarna ange och konfigurera de UI-element på skärmen transaktionen. Layoutdesigner för skärm använder ClickOnce för att hämta, installera och öppna den senaste versionen av programmet varje gång användaren öppnar den. Kontrollera att nödvändiga webbläsarfunktioner för med en klickning – vissa webbläsare, t ex krom, kräver filnamnstillägg. **Numeriska** -numeriskt tangentbord är den huvudsakliga användarindata i transaktionen POS-skärmen. Den kan konfigureras så att hela skärmen pad som är perfekt för pekskärmar, eller bara de fält som kan användas med ett fysiskt tangentbord. Inställningarna knappsats finns i hela layouten. I Dynamics 365 för operationer version 1611 ha komprimera layout alltid fullständig knappsats via skärmen transaktionen. **Summor panel** - panelen summor kan konfigureras i något av alternativen två kolumner för att visa fält som raden eller antal, rabattbelopp, tillägg, delsumma och moms. I Dynamics 365 för operationer version 1611 stöd komprimera layout endast för en enda summor kolumn. **Inleverans** -** ** innehåller panelen inleverans försäljningsrader, betalningsraderna och leveransinformation för produkterna och tjänsterna bearbetas i KASSAN. Användare kan ange kolumner, bredd och placering. Du kan också konfigurera ytterligare information som visas i en rad under raden i huvudfönstret i kompakt layout i Dynamics 365 operationer version 1611. **Kundkort** - kortet visar kundinformationen som hör till kunden som är kopplade till transaktionen. Kund kan konfigureras för att dölja eller visa ytterligare information. **Flikkontroller** - kontrollen kan placeras på skärmlayout och andra kontroller, till exempel numeriskt tangentbord, kundkort eller knappsatser kan placeras inuti på fliken. Kontrollen är en behållare som hjälper användarna att mer innehåll får plats på skärmen. Kontrollen är bara tillgänglig för hela layouter. ** Bild **-bildkontrollen kan användas för att visa en logotyp eller annat varumärke på skärmen transaktionen. Bildkontrollen är bara tillgänglig för hela layouter. **Rekommenderade produkter** - om konfigurerade för miljön, rekommenderade produkter produktförslag utifrån maskin utbildning visas i kontrollen. Rekommenderade produkter kontrollen är bara tillgänglig för hela layouten i Dynamics 365 för operationer version 1611. ** Kontroll **-anpassad kontroll som fungerar som platshållare i layouten på skärmen kan du reservera utrymme för anpassat innehåll. Den anpassade kontrollen är bara tillgänglig för hela layouter.

<a name="see-also"></a>Se även
--------

[Install the Retail POS Layout designer](install-pos-layout-designer.md)


