---
title: "Översikt över produktinformation"
description: "Det här avsnittet innehåller information om hur du hanterar produktinformation. Produktinformationshantering fungerar med en delad produktdefinition, kategorisering och identifierare för alla juridiska personer och även särskilda konfigurationer för en produkt så att den passar i affärsprocesserna."
author: cvocph
manager: AnnBe
ms.date: 06/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResProductMaintainWorkspace, EcoResProductListPage, EcoResProductVariantMaintainWorkspace
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Core, Operations, Retail
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.search.industry: 
ms.author: cvocph
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 3a6a41f192b1c79f0f8ee40bf62c8b30ee7200c8
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="product-information-overview"></a>Översikt över produktinformation

[!include[banner](../includes/banner.md)]

[!include[retail name](../includes/retail-name.md)]

Det här avsnittet innehåller information om hur du hanterar produktinformation. Produktinformationshantering fungerar med en delad produktdefinition, kategorisering och identifierare för alla juridiska personer och även särskilda konfigurationer för en produkt så att den passar i affärsprocesserna. 

Produktinformation är den viktigaste delen i leveranskedjor och butiksapplikationer inom alla branscher. Det avser processer och tekniker som fokuserar på att centralt hantera information om produkter (t.ex. över distributionskedjor). Det är viktigt att gemensamma produktdefinitioner, dokumentation, attribut och identifierare används. I de olika modulerna för en företagslösning krävs produktspecifik information och konfiguration för att hantera de affärsprocesser som rör specifika produkter, produktfamiljer och produktkategorier.

## <a name="product-definition"></a>Produktdefinition

En produkt definieras i första hand med hjälp av ett produktnummer, ett namn och en beskrivning. Andra data är också nödvändiga för att beskriva en produkt eller tjänst:

- Typ av produkt: artikel eller tjänst
- Produktundergrupp: specifika produkter och produktmallar
- Definition av produktvariantmodellen:

     - Produktdimensioner och dimensionsgrupper
     - Produktnomenklatur
     - Modeller för produktkonfiguration

- Koppling mellan produkten och en eller flera kategorier
- Definition av produkt- och kategoriattribut
- Produktbilder
- Bilagor
- Måttenheter och relaterade konverteringar
- Översättningar av alla namn och beskrivningar

## <a name="distribution-export-and-import-of-product-data"></a>Distribution, export och import av produktdata

Produktdefinitionen kan skapas i Microsoft Dynamics 365 for Finance and Operations, Enterprise edition. Den går också att importera från system för hantering av produktlivscykel (PLM), hantering av produktdata (PDM) eller hantering av produktinformation (PIM). När du använder flera instanser av Finance and Operations används vanligtvis en instans som en mall för produktdata för alla andra instanser. Den här metoden stöds genom ett stort antal datatabeller som aktiverar exporten och importen av definitionen för produktdata från en förekomst till en annan.

För att stödja distributionen av produktdata till många instanser tillåter Finance and Operations användning av Common Data Service. Definitioner av produkter kan exporteras från en förekomst i Finance and Operations till Common Data Service. Definitioner av produkter kan sedan användas för att förse andra företagsprogram såsom Microsoft Dynamics 365 for Sales med produktdata.

Observera att dynamiska och flexibla organisationers produktinformationsdata ändras varje dag. Underhåll av korrekta och aktuella produktdata är därför en kritisk affärsprocess i sig.

## <a name="product-masters-and-product-variants"></a>Produktmallar och produktvarianter

I en smidig värld där produkter snabbt måste anpassas efter kundens behov specificerar produktdefinitioner en uppsättning produkter i stället för specifika produkter. I Microsoft Dynamics 365 for Finance and Operations kallas de generiska produkterna för *produktmallar*. Produktmallar innehåller definitionen och reglerna som anger hur olika specifika produkter beskrivs och uppträder i affärsprocesser. Utifrån dessa definitioner kan olika specifika produkter genereras. Dessa specifika produkter kallas för *produktvarianter*.

I Finance and Operations associeras en produktmall med en produktdimensionsgrupp och en konfigurationsteknik som anger affärsreglerna. Produktdimensioner (färg, storlek, utförande och konfiguration) är en särskild uppsättning attribut som kan användas i hela programmet för att definiera och spåra beteendet hos berörda produkter. Dessa dimensioner kan också hjälpa användarna att söka efter och identifiera produkten.

## <a name="configuration-technologies"></a>Konfigurationstekniker

Du kan välja mellan tre olika konfigurationstekniker:

- Fördefinierade varianter definieras av fördefinierade produktdimensioner. Variantdefinitionen innehåller definitionen av en specifik giltig kombination av dimensioner, till exempel färg, stil och storlek. Varje kombination skapar en viss specifik produktvariant.
- Dimensionsbaserad konfiguration används normalt i tillverkningenscenarier och låter dig använda konfigurationsdimensionen i definitionen av strukturlistorna. När en specifik konfiguration har valts använder systemet en underuppsättning av strukturlisterader som är giltiga för den konfigurationen för planering och produktion. Detta koncept kallas även *global strukturlista*, eftersom en delad Strukturlista används för alla konfigurationer av en produkt.
- Begränsningsbaserad konfiguration använder en modell för produktkonfiguration som beskriver alla möjliga attribut och komponenter som krävs för att beskriva alla möjliga varianter av en produkt i en enstaka modell. Begränsningar av kombinationer av attribut kan beskrivas genom reguljära uttryck eller registerbaserade begränsningar. Konfigurationsmodeller och konfiguratorer blir ännu viktigare i produktinformationshantering och används i alla branscher.

När du planerar implementeringen av Finance and Operations är det viktigt att du väljer rätt konfigurationsteknik för en affärsprocess. En produkt kan inte konverteras från en modell till en annan efter implementeringen.

## <a name="product-variant-model-definition-workspace"></a>Arbetsyta för definition av produktvariantmodell

Arbetsytan **Definition av produktvariantmodell** ger en översikt över produktmallarna. Statusen för frisläppta original och relaterade varianter för särskilda juridiska personer visas också.

## <a name="released-products"></a>Frisläppta produkter

Produkter som släpps till en särskild juridisk person kallas *frisläppta produkter*. Produkter kan släppas i bulk till en eller flera juridiska personer samtidigt. Eftersom olika egenskaper och attribut för produkter kan behöva läggas till per juridisk person kan du använda arbetsytan **Underhåll av frisläppt produkt** för att övervaka och slutföra nysläppta produkter för varje juridisk person eller underorganisationer till en juridisk person.

### <a name="released-product-maintenance-workspace"></a>Arbtesytan Underhåll av frisläppt produkt

Du kan konfigurera arbetsytan **Underhåll av frisläppt produkt** menyobjektet **Konfigurera min arbetsyta**. Välj en kategorihierarki och kategori att filtrera listan efter. Om du vill justera relevanta produktdata på arbetsytan kan du också definiera tidsgränser i dagar för **Nyligen frisläppta produkter** och **Stoppade frisläppta produkter**.

Arbetsytan består av en sammanfattning av paneler och två listor. Listan **Öppna ärenden** visar produktändringsärenden som har produkter i den valda produktkategorihierarkin som inte är utförda och stängda. Listan **Nyligen frisläppta** visar produkter som har släppts inom tidsgränsen som anges i arbetsytans konfiguration. Validering utförs för varje artikel i listan och status för valideringen visas. Denna status kan indikera att nödvändiga konfigurationer för den juridiska personen inte är slutförda. I listan får du direkt tillgång till **Information om frisläppt produkt**, **Underhåll av produktattribut**, **Underhåll av produktkategori**, **Standardorderinställningar** och **Textöversättningar** så att du kan slutföra den nödvändiga konfiguration av produkten.

### <a name="manually-creating-a-new-released-product"></a>Skapa en ny frisläppt produkt manuellt

Du kan manuellt skapa en frisläppt produkt i en enda körning, beroende på organisationens affärsprocesser och regler om huruvida den här funktionen ska användas. Den här funktionen skapar en ny produkt och frisläpper den automatiskt till den aktuella juridiska personen. Om du vill skapa en ny produkt, klicka på **Frisläppta produkter** på arbetsytan **Underhåll av frisläppta produkter** eller på listsidan **Frisläppt produkt**.

