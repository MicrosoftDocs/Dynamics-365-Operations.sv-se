---
title: Översikt över produktinformation
description: Denna artikel innehåller information om produktinformationshantering. Produktinformationshantering fungerar med en delad produktdefinition, kategorisering och identifierare för alla juridiska personer och även särskilda konfigurationer för en produkt så att den passar i affärsprocesserna.
author: t-benebo
ms.date: 06/01/2017
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductMaintainWorkspace, EcoResProductListPage, EcoResProductVariantMaintainWorkspace, EcoResProductVariantPerCompanyImagePart, EcoResProductRelationType,EcoResProductAvailabilityPart,  EcoResProductReleasedSelect, EcoResProductLookup, EcoResProductVariantsPendingReleaseFormPart, EcoResProductSearchLookup, EcoResProductNumberRename, EcoResDimensionBasedConfigWorkspace, EcoResProductVariantImagePart, EcoResProductImagePart, EcoResProductVariantsPerCompanyPart, InventItemIdLookupByDefaultOrderSetting, EcoResProductReleaseSessions, EcoResProductVariantMaintainWorkspaceConfiguration, EcoResProductProcessManufacturingWorkspaceConfiguration, EcoResProductMasterVariantsPart, EcoResProductDiscreteManufacturingWorkspaceConfiguration, EcoResProductVariantAvailabilityPart, EcoResProductInformationFactBox, EcoResProductLookupTest, EcoResProductImageTest, EcoResProductReleasedRecentlyCreatedFormPart, EcoResPhysicalProductDimensions, PdsMRCRegulatedListItem, EcoResProductAvailabilityPart, PdsMRCRestrictionList, InventItemIdLookupAllocationId, EcoResProductAvailability, EcoResProductEntityAttributeTableFieldAssociation, EcoResProductImagePart, EcoResProductRelation, EcoResProductReleaseAddProduct, EcoResProductPerCompanyListPage, EcoResProductParameters, PdsMRCRestrictedItemByCountryState, EngChgCasePreview, InventTablePreview, PdsMRCItemDetails, EngChgCaseAssociate, PdsMRCCustomerHistory, PdsMRCVendorHistory, PdsMRCRestrictedCountryStateByItem, InventItemIdGroupLookup, InventLocationLookup, PdsMRCValidityIntervalbyCountry, PdsMRCValidityIntervalbyCountry, PdsMRCEventTracker, PdsMRCReportingCountry, PdsMRCDocument, PdsMRCReportingList, PdsMRCItemCAS, GraphicsTestForm, EngChgPicklist
audience: Application User
ms.reviewer: kamaybac
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: benebotg
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fa06e718d2acc44cfced7db842814c48fb210d1e
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8867881"
---
# <a name="product-information-overview"></a>Översikt över produktinformation

[!include [banner](../includes/banner.md)]



Denna artikel innehåller information om produktinformationshantering. Produktinformationshantering fungerar med en delad produktdefinition, kategorisering och identifierare för alla juridiska personer och även särskilda konfigurationer för en produkt så att den passar i affärsprocesserna. 

Produktinformation är den viktigaste delen i leveranskedjor och handelsapplikationer inom alla branscher. Det avser processer och tekniker som fokuserar på att centralt hantera information om produkter (t.ex. över distributionskedjor). Det är viktigt att gemensamma produktdefinitioner, dokumentation, attribut och identifierare används. I de olika modulerna för en företagslösning krävs produktspecifik information och konfiguration för att hantera de affärsprocesser som rör specifika produkter, produktfamiljer och produktkategorier.

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

Produktdefinitionen kan skapas i Supply Chain Management. Den går också att importera från system för hantering av produktlivscykel (PLM), hantering av produktdata (PDM) eller hantering av produktinformation (PIM). När du använder flera instanser av Supply Chain Management används vanligtvis en instans som en mall för produktdata för alla andra instanser. Den här metoden stöds genom ett stort antal datatabeller som aktiverar exporten och importen av definitionen för produktdata från en förekomst till en annan.

För att stödja distributionen av produktdata till många instanser tillåter Supply Chain Management användning av Microsoft Dataverse. Definitioner av produkter kan exporteras från en förekomst i Supply Chain Management till Microsoft Dataverse. Definitioner av produkter kan sedan användas för att förse andra företagsprogram såsom Dynamics 365 Sales med produktdata.

Observera att dynamiska och flexibla organisationers produktinformationsdata ändras varje dag. Underhåll av korrekta och aktuella produktdata är därför en kritisk affärsprocess i sig.

## <a name="product-masters-and-product-variants"></a>Produktmallar och produktvarianter

I en smidig värld där produkter snabbt måste anpassas efter kundens behov specificerar produktdefinitioner en uppsättning produkter i stället för specifika produkter. I Supply Chain Management kallas dessa allmänna produkterna för *produktmallar*. Produktmallar innehåller definitionen och reglerna som anger hur olika specifika produkter beskrivs och uppträder i affärsprocesser. Utifrån dessa definitioner kan olika specifika produkter genereras. Dessa specifika produkter kallas för *produktvarianter*.

En produktmall associeras med en produktdimensionsgrupp och en konfigurationsteknik som anger affärsreglerna. Produktdimensioner (färg, storlek, utförande och konfiguration) är en särskild uppsättning attribut som kan användas i hela programmet för att definiera och spåra beteendet hos berörda produkter. Dessa dimensioner kan också hjälpa användarna att söka efter och identifiera produkten.

## <a name="configuration-technologies"></a>Konfigurationstekniker

Du kan välja mellan tre olika konfigurationstekniker:

- Fördefinierade varianter definieras av fördefinierade produktdimensioner. Variantdefinitionen innehåller definitionen av en specifik giltig kombination av dimensioner, till exempel färg, stil och storlek. Varje kombination skapar en viss specifik produktvariant.
- Dimensionsbaserad konfiguration används normalt i tillverkningenscenarier och låter dig använda konfigurationsdimensionen i definitionen av strukturlistorna. När en specifik konfiguration har valts använder systemet en underuppsättning av strukturlisterader som är giltiga för den konfigurationen för planering och produktion. Detta koncept kallas även *global strukturlista*, eftersom en delad Strukturlista används för alla konfigurationer av en produkt.
- Begränsningsbaserad konfiguration använder en modell för produktkonfiguration som beskriver alla möjliga attribut och komponenter som krävs för att beskriva alla möjliga varianter av en produkt i en enstaka modell. Begränsningar av kombinationer av attribut kan beskrivas genom reguljära uttryck eller registerbaserade begränsningar. Konfigurationsmodeller och konfiguratorer blir ännu viktigare i produktinformationshantering och används i alla branscher.

När du planerar implementeringen av Supply Chain Management är det viktigt att du väljer rätt konfigurationsteknik för en affärsprocess. En produkt kan inte konverteras från en modell till en annan efter implementeringen.

## <a name="product-variant-model-definition-workspace"></a>Arbetsyta för definition av produktvariantmodell

Arbetsytan **Definition av produktvariantmodell** ger en översikt över produktmallarna. Statusen för frisläppta original och relaterade varianter för särskilda juridiska personer visas också.

## <a name="released-products"></a>Frisläppta produkter

Produkter som släpps till en särskild juridisk person kallas *frisläppta produkter*. Produkter kan släppas i bulk till en eller flera juridiska personer samtidigt. Eftersom olika egenskaper och attribut för produkter kan behöva läggas till per juridisk person kan du använda arbetsytan **Underhåll av frisläppt produkt** för att övervaka och slutföra nysläppta produkter för varje juridisk person eller underorganisationer till en juridisk person.

### <a name="released-product-maintenance-workspace"></a>Arbtesytan Underhåll av frisläppt produkt

Du kan konfigurera arbetsytan **Underhåll av frisläppt produkt** menyobjektet **Konfigurera min arbetsyta**. Välj en kategorihierarki och kategori att filtrera listan efter. Om du vill justera relevanta produktdata på arbetsytan kan du också definiera tidsgränser i dagar för **Nyligen frisläppta produkter** och **Stoppade frisläppta produkter**.

Arbetsytan består av en sammanfattning av paneler och två listor. Listan **Öppna ärenden** visar produktändringsärenden som har produkter i den valda produktkategorihierarkin som inte är utförda och stängda. Listan **Nyligen frisläppta** visar produkter som har släppts inom tidsgränsen som anges i arbetsytans konfiguration. Validering utförs för varje artikel i listan och status för valideringen visas. Denna status kan indikera att nödvändiga konfigurationer för den juridiska personen inte är slutförda. I listan får du direkt tillgång till **Information om frisläppt produkt**, **Underhåll av produktattribut**, **Underhåll av produktkategori**, **Standardorderinställningar** och **Textöversättningar** så att du kan slutföra den nödvändiga konfiguration av produkten.

### <a name="manually-creating-a-new-released-product"></a>Skapa en ny frisläppt produkt manuellt

Du kan manuellt skapa en frisläppt produkt i en enda körning, beroende på organisationens affärsprocesser och regler om huruvida den här funktionen ska användas. Den här funktionen skapar en ny produkt och frisläpper den automatiskt till den aktuella juridiska personen. Om du vill skapa en ny produkt, klicka på **Frisläppta produkter** på arbetsytan **Underhåll av frisläppta produkter** eller på listsidan **Frisläppt produkt**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]