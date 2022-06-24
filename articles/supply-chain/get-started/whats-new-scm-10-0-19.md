---
title: Nyheter och ändringar i Dynamics 365 Supply Chain Management version 10.0.19 (juni 2021)
description: Denna artikel innehåller en beskrivning av nya eller ändrade funktioner i Dynamics 365 Supply Chain Management 10.0.19.
author: kamaybac
ms.date: 04/23/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-04-23
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 1ea0f2dae2f558f1ee5c0d2b94a4b926263b7de7
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8893422"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-version-10019-june-2021"></a>Nyheter och ändringar i Dynamics 365 Supply Chain Management version 10.0.19 (juni 2021)

[!include [banner](../includes/banner.md)]

Denna artikel anger nya eller ändrade funktioner i Microsoft Dynamics 365 Supply Chain Management version 10.0.19. Den här versionen har ett versionsnummer för 10.0.837 och är tillgänglig enligt följande:

- **Förhandgranskning av version:** april 2021
- **Allmän tillgänglighet för version (självuppdatering):** juni 2021
- **Allmän tillgänglighet för version (automatisk uppdatering):** juni 2021

## <a name="features-included-in-this-release"></a>Funktioner som ingår i den här versionen

Följande register lista de funktioner som ingår i denna version: Kolumnen *Funktion* innehåller länkar till [versionsplanen](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/planned-features), där du kan se de officiella frisläppningsdatumen för respektive funktion. Kolumnen *Mer information* innehåller mer information och/eller länkar till relaterad dokumentation.

De flesta av dessa funktioner måste aktiveras med [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) innan du kan använda dem.

| Funktionsområde | Funktion | Mer information |
|---|---|---|
| Lager&nbsp;och&nbsp;logistik | [Godkänna och spara bankinformation från leverantör](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/approve-save-vendor-submitted-bank-details) | [Hantera bankkontoinformation om leverantör](../../finance/accounts-payable/maintain-vendor-bank-info.md) |
| Lager och logistik | [Optimering av kontaktpersons datatabellsexport](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/contact-person-data-entity-export-optimization)  | När denna funktion aktiveras orsakar ändringar i refererade data inte att relaterade kontakter inkluderas i nästa stegvisa export. När denna funktion inaktiveras orsakar ändringar i refererade data att relaterade kontakter inkluderas i nästa stegvisa export. |
| Lager och logistik | [Stegvisa förbättringar av lagerställekörningskapaciteter med skalningsenheter](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/incremental-enhancements-warehouse-execution-capabilities-scale-units) |[Meddelandeprocessormeddelanden](../cloud-edge/cloud-edge-message-processor-messages.md)<br><br>[Lagerställets lagerjustering](../cloud-edge/cloud-edge-warehouse-inventory-adjustment.md)<br><br>[Arbetsbelastningar för distributionslagerhantering för moln- och kantskalningsenheter](../cloud-edge/cloud-edge-workload-warehousing.md) |
| Lager och logistik | [Sökfunktion för dokumentintroduktion och fält för dokumentsammanfattning på sidan dör försäljningsoffert](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/lookup-functionality-document-introduction-document-conclusion-fields-sales-quotation-page) | Den här funktionen lägger till sökfunktionalitet för fälten **dokumentintroduktion** och **dokumentsammanfattning** på sidan **försäljningsoffert**.<br><br>Den här funktionen aktiveras som standard. |
| Lager och logistik | [Lagerställekörning med kantskalningsenheter på din anpassade maskinvara](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/warehouse-execution-edge-scale-units-custom-hardware) | [Distribuera kantskalningsenheter på anpassad maskinvara med HJÄLP LBD](../cloud-edge/cloud-edge-edge-scale-units-lbd.md) |
| Tillverkning | [Tillverkningskörning med kantskalningsenheter på din anpassade maskinvara](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/manufacturing-execution-edge-scale-units-custom-hardware) | [Distribuera kantskalningsenheter på anpassad maskinvara med HJÄLP LBD](../cloud-edge/cloud-edge-edge-scale-units-lbd.md) |
| Planering | Frågebaserad planerad order som bekräftar | [Bekräfta planerade order](../master-planning/planning-optimization/planned-order-firming.md) |
| Produktinformationshantering | [Förbättringar av sidan med variantförslag](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/variant-suggestions-page-improvements) | [Skapa fördefinierade produktvarianter](../pim/tasks/create-predefined-product-variants.md) |

## <a name="feature-enhancements-included-in-this-release"></a>Funktionsförbättringar som ingår i den här versionen

Följande register lista de funktionsförbättringar som ingår i denna version: Var och en av dessa tillhandahåller en stegvis förbättring av en befintlig funktion. Eftersom de bara är förbättringar visas de inte i [frisläppningsplanen](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/planned-features). För att säkerställa att dessa förbättringar inte står i konflikt med dina befintliga anpassningar eller inställningar stängs var och en av dem av som standard (om inget annat anges). Om du vill använda någon av dessa funktioner måste du explicit aktivera dem i [Funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Modul | Funktionsnamn&nbsp;&nbsp;i&nbsp;funktionshantering | Mer information |
|---|---|---|
| Försäljning och marknadsföring | Förbättringar i försäljningshistorik | Rensningen av försäljningshistorik kan ta lång tid om den körs sällan i miljöer med stora försäljningsuppdateringar. Om du vill minska tidslängden och förbättra tillförlitligheten, delar den här funktionen upp rensningen i batchar som körs under en begränsad tid. Om det är möjligt kommer databaskapaciteter att användas för att minimera låsning och undvika att transaktionsregister sammanfogas under rensningen. Mer information finns i [Schemalägga datarensning i försäljningshistorik](../sales-marketing/sales-update-history-cleanup-performance-improvements.md). |
| Försäljning och marknadsföring | Uppdatera begärt inleveransdatum med bekräftat datum för koncerninterna order | Med denna funktion kan du kontrollera vad som ska hända med fältvärden för försäljning och inköpsdatum vid koncernintern direktleverans. Du kan välja om systemet ska uppdatera de begärda datumen eller hoppa över att uppdatera dem. Om du hoppar över uppdateringen representerar de begärda datumen det som kunden har begärt. Om du aktiverar uppdatering representerar de begärda datumen (vid användning av leveransdatumkontroll) endast det som kunden begärt. Leveransdatumkontrollen, som skiljer sig från *Ingen*, går före det som ursprungligen begärdes. Du kan konfigurera detta alternativ med hjälp av den nya inställningen **Uppdatera begärt inleveransdatum med bekräftat datum** i inställningarna för koncernintern leverantör eller kund.<br><br>Om funktionen inaktiveras skriver systemet över begärt inleveransdatum på ursprungliga försäljningsorder baserat på kontrollregeln för leveransdatum, men det begärda leveransdatumet förblir som det är. |
| Warehouse management | Avrunda kvantiteter neråt till närmaste försäljningsenhet vid frisläpp till lagerställe | Med den här funktionen läggs ett alternativ till som kan begränsa orderkvantiteter vid frisläppning till lagerställe. När den här aktiveras avrundas orderkvantiteter nedåt till närmaste hela försäljningsenhet, och order som inkluderar kvantiteter för mindre än en försäljningsenhet avvisas för frisläppning. |
| Warehouse management | Påfyllnadsmetoden "Schemalägg skapande av arbete" för hela organisationen | När du aktiverar den här funktionen, *Skapa tidsplan för arbete* läggs till och konfigureras att köra parallellt över alla juridiska enheter. Flera ytterligare inställningar påverkas också. Mer information finns i [Planera skapande av arbete under påfyllnad](../warehousing/configure-wave-schedule-work-creation.md). |

## <a name="new-and-updated-documentation-resources"></a>Nya och uppdaterade dokumentationsresurser

Följande hjälpartiklar har nyligen lagts till eller uppdaterats väsentligt. De är inte nödvändigtvis relaterade till de nya funktioner som har lagts till för den här versionen, vilket visas i föregående avsnitt, men de kan hjälpa dig att få ut mer av befintliga funktioner.

| Funktionsområde | Nya eller uppdaterade artiklar |
|---|---|
| Konstruktionsändringshantering | [Vanliga frågor och svar om konstruktionsändringshantering](../engineering-change-management/change-management-faq.md) |
| Anskaffning och källa | [Kategoribegäranden från leverantörer](../procurement/category-requests-from-vendors.md) |
| Produktinformationshantering | [Hantera måttenhet](../pim/tasks/manage-unit-measure.md)<br><br>[Beräkningar för produktkonfigurationsmodell](../pim/config-model-calculations.md) |
| Produktionskontroll | [Enhetlig nummerserie för jobb-ID:n](../production-control/unified-job-ids.md) |
| Transporthantering | [LTL-klasser](../transportation/ltl-class.md)<br><br>[NMFC-koder](../transportation/nmfc-codes.md) |
| Lagerhantering, skapa och bearbeta påfyllnad | [Skapa och bearbeta påfyllnad](../warehousing/wave-processing.md)<br><br>[Distributionslagerparametrar för påfyllnadsbearbetning](../warehousing/wave-warehouse-parameters.md)<br><br>[Påfyllnadsmallar](../warehousing/wave-templates.md)<br><br>[Påfyllnadsallokering](../warehousing/wave-allocation-method.md)<br><br>[Tidsplanera att skapa arbete under påfyllnad](../warehousing/configure-wave-schedule-work-creation.md)<br><br>[Skapande av behållare](../warehousing/wave-containerization.md)<br><br>[Meddelanden för påfyllnadskörning](../warehousing/wave-execution-notifications.md) |

## <a name="additional-resources"></a>Ytterligare resurser

### <a name="platform-updates-for-finance-and-operations-apps"></a>Plattformsuppdatering för appar för ekonomi och drift

Microsoft Dynamics 365 Supply Chain Management 10.0.19 inkluderar plattformsuppdateringar. Mer information finns i [Plattformsuppdateringar för version 10.0.19 av appar för ekonomi och drift (juni 2021)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-19.md).

### <a name="bug-fixes"></a>Felkorrigeringar

Om du vill ha information om felkorrigeringar som ingår i varje uppdatering som ingår i 10.0.19 loggar du in på Lifecycle Services (LCS) och visar [KB-artikel](https://fix.lcs.dynamics.com/Issue/Details?bugId=575415).

### <a name="dynamics-365-2021-release-wave-1-plan"></a>Dynamics 365: 2021 utgivningsvåg 1 plan

Har du frågeställningar om nya och kommande funktioner i våra affärsappar eller plattformen?

Se [Dynamics 365: 2021 utgivningsvåg 1 plan](/dynamics365-release-plan/2021wave1/). Vi har sammanställt all information som du kan tänkas behöva på ett enskilt dokument som du kan använda för din planering.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>Borttagna och inaktuella funktioner för Supply Chain Management

Artikeln [Borttagna eller inaktuella funktionerna i Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) beskriver funktioner som har tagits bort eller planeras tas bort eller göras inaktuella för Supply Chain Management.

- En *borttagen* funktion är inte längre tillgänglig i produkten.
- En *borttagen* funktion är inte i aktiv utveckling och kan tas bort i en kommande uppdatering.

Innan någon funktion tas bort från produkten kommer meddelandet om inaktualitet att meddelas i artikeln [Borttagna eller inaktuella funktioner i Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) 12 månader före borttagning.

För att bryta ändringar som endast påverkar kompileringen, men är binära kompatibla med begränsade lägen och produktionsmiljöer, blir utgångstiden mindre än 12 månader. Vanligtvis är dessa funktionsuppdateringar som måste göras till kompileraren.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
