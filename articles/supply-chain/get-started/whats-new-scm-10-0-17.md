---
title: Vad är nytt och ändrat i Dynamics 365 Supply Chain Management (10.0.17 april 2021)
description: Det här ämnet beskriver nya eller ändrade funktioner i Dynamics 365 Supply Chain Management 10.0.17.
author: kamaybac
ms.date: 02/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-02-01
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: fd8c306dd6c3aeb7ef41b4eb3f6f8bad040035c2
ms.sourcegitcommit: 9283caad2d0636f98579c995784abec19fda2e3f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/22/2021
ms.locfileid: "5935615"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-10017-april-2021"></a>Vad är nytt och ändrat i Dynamics 365 Supply Chain Management (10.0.17 april 2021)

[!include [banner](../includes/banner.md)]

Det här ämnet anger nya eller ändrade funktioner i Microsoft Dynamics 365 Supply Chain Management version 10.0.17. Den här versionen har ett versionsnummer för 10.0.761 och är tillgänglig enligt följande:

- **Förhandsversion:** februari 2021
- **Allmän tillgänglighet för frisläppning (självuppdatering):** mars 2021
- **Allmän tillgänglighet för frisläppning (automatisk uppdatering):** april 2021

## <a name="features-included-in-this-release"></a>Funktioner som ingår i den här versionen

Den här versionen innehåller följande nya funktioner:  Följ länkarna till [Utgivningsplan](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/planned-features) för att se de officiella datumen för varje funktion.

De flesta av dessa funktioner måste aktiveras med [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) innan du kan använda dem.

### <a name="asset-management"></a>Tillgångshantering

- [Använd regler för att gruppera arbetsorder när du kör en underhållsplan](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/apply-rules-grouping-work-orders-while-running-maintenance-plan)<br> - Mer information finns i [Skapa arbetsorder](../asset-management/preventive-and-reactive-maintenance/creating-work-orders.md).

- [Fakturera kunder för underhållsarbete](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/bill-customers-maintenance-work)<br> - Mer information finns i [Faktura för underhåll av kundägda tillgångar](../asset-management/integration-to-project-management-and-accounting/customer-billing.md).

- [Planera underhåll baserat på ackumulerade värden för tillgångsräknare](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/plan-maintenance-based-accumulated-asset-counter-values)<br> - Mer information finns i [Underhållsplaner](../asset-management/preventive-and-reactive-maintenance/maintenance-plans.md).

### <a name="inventory-and-logistics"></a>Lager och logistik

- [Integrationsramverket för materialhanteringsutrustning för automatiska lagerprocesser (tidigare MHAX)](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/integration-framework-material-handling-equipment-automated-warehouse-processes-previously-mhax)<br> - Mer information finns i [Materialhanteringsutrustningens gränssnitt (MHAX)](../warehousing/mhax.md).

- [Hemtagningskostnad](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/landed-cost)<br> - Mer information finns i [Modul för hemtagningskostnad](../landed-cost/landed-cost-overview.md).

- [Förpackning jämfört med lagringsdimensioner](/dynamics365-release-plan/2019wave2/dynamics365-supply-chain-management/packing-vs.-storage-dimensions)<br> - Mer information finns i [Ange olika dimensioner för förpackning och lagring](../warehousing/packing-vs-storage-dimensions.md).

- [Sparade vyer för lager och logistik](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/saved-views-inventory-logistics)<br> - Mer information finns i [Standardvyer för Supply Chain Management](saved-views-scm.md).

- [Tidsplanera att skapa lagerarbete](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/schedule-warehouse-work-creation)<br> - Mer information finns i [Planera skapande av arbete under påfyllnad](../warehousing/configure-wave-schedule-work-creation.md).

- [Ange ekonomiska standarddimensioner för verifikationer för omvärdering av standardkostnad för lager](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/set-default-financial-dimensions-inventory-standard-cost-revaluation-vouchers)<br> - Mer information finns i [Hantera standardkostnadsuppdateringar](../cost-management/manage-standard-cost-updates.md).

- [Leverans av små paket (SPS)](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/small-parcel-shipping-sps)<br> - Mer information finns i [Leverans av små paket](../warehousing/small-parcel-shipping.md).

- [Lagerkörning med skalenheter i molnet](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/warehouse-execution-scale-units-cloud)<br> - För mer information, se [Arbetsbelastningar för distributionslagerhantering för moln- och kantskalningsenheter](../cloud-edge/cloud-edge-workload-warehousing.md) och [Lagerställeorder för moln- och kantskalningsenheter](../cloud-edge/cloud-edge-warehouse-order.md).

- [Mobilappen lagerställe](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/warehouse-management-mobile-application)<br> - Mer information finns i [Installera och anslut lagerställeappen](../warehousing/install-configure-warehouse-management-app.md) och [Användarinställningar för mobil enhet](../warehousing/mobile-device-user-settings.md).

- Meddelanden för påfyllnadskörning<br> - För mer information, se [Meddelande påfyllnadskörning](../warehousing/wave-execution-notifications.md)

### <a name="manufacturing"></a>Tillverkning

- [Funktionerna för tillgångshantering i gränssnittet för utförande av produktionsstyrning](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/asset-management-capabilities-production-floor-execution-interface)<br> - Mer information finns i [Konfigurera gränssnittet för körning av produktionsstyrning](../production-control/production-floor-execution-configure.md).

- [Tillverkningskörning med skalenheter i molnet](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/manufacturing-execution-scale-units-cloud)<br> - För mer information, se [Arbetsbelastningar för tillverkningskörning för moln- och kantskalningsenheter](../cloud-edge/cloud-edge-workload-manufacturing.md).

- [Åsidosätta standardreservationsprincipen för material i produktion](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/override-default-reservation-principle-materials-production)<br> - Mer information finns i [Åsidosätt standardreservationsprincipen för material i produktionen](../production-control/override-default-reservation-principle.md).

- [Sparade vyer för produktionskontroll](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/saved-views-production-control)<br> - Mer information finns i [Standardvyer för Supply Chain Management](saved-views-scm.md).

- Enhetlig nummerserie för jobb-ID:n<br> - Mer information finns i [Enhetlig nummerserie för jobb-ID](../production-control/unified-job-ids.md).

### <a name="planning"></a>Planering

- [Tidsgräns för disponering för planeringsoptimering](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/coverage-time-fence-support-planning-optimization)<br> - Mer information finns i [tidsgränser för disponering](../master-planning/planning-optimization/coverage-time-fence.md).

- [Prognosunderstöd för planeringsoptimering](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/forecast-submodel-support-planning-optimization)<br> - För mer information, se [Huvudplanering med efterfrågeprognoser](../master-planning/planning-optimization/demand-forecast.md).

- [Stöd för inköpsrekvisition för planeringsoptimering](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/purchase-requisition-support-planning-optimization)<br> - Mer information finns i [inköpsrekvisition](../master-planning/planning-optimization/purchase-requisitions.md).

- [Sparade vyer för planerade order](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/saved-views-planned-orders)<br> - Mer information finns i [Standardvyer för Supply Chain Management](saved-views-scm.md).

### <a name="product-information-management"></a>Produktinformationshantering

- [Aktivera ändringshantering för befintliga produkter](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/enable-change-management-existing-products)<br> - För mer information, se [Aktivera förändringshantering på befintliga produkter](../engineering-change-management/change-management-existing-products.md).

## <a name="new-and-updated-documentation-resources"></a>Nya och uppdaterade dokumentationsresurser

Följande hjälpavsnitt har nyligen lagts till eller uppdaterats väsentligt. De är inte nödvändigtvis relaterade till de nya funktioner som har lagts till för den här versionen, vilket visas i föregående avsnitt, men de kan hjälpa dig att få ut mer av befintliga funktioner.

### <a name="cost-management"></a>Kostnadshantering

- [Felsöka kostnadshantering](../cost-management/troubleshoot-costmanagement.md)

### <a name="asset-management"></a>Tillgångshantering

- [Konfigurera mobil arbetsyta för tillgångshantering](../asset-management/set-up-asset-management-mobile.md)

### <a name="inventory-and-logistics"></a>Lager och logistik

- [Konfigurera produktfilter för distributionslagertransaktioner](../warehousing/filters-and-filter-codes.md)

- [Rullande inventering av del av platser](../warehousing/partial-location-cycle-counting.md)

- [Plockradsgruppering](../warehousing/pick-line-grouping.md)

- [Felsöka lageråtgärder](../inventory/troubleshoot-inventory-operations.md)

- [Artikelplacering för lagerställe](../warehousing/warehouse-slotting.md)

### <a name="manufacturing"></a>Tillverkning

- [Designa körningsgränssnittet för produktionsgolvet](../production-control/production-floor-execution-tabs.md)

### <a name="planning"></a>Planering

- [Koncernintern planering](../master-planning/planning-optimization/Intercompany-planning.md)

- [Lagermarkeringen med Planeringsoptimering](../master-planning/planning-optimization/marking.md)

- [Produktionsplanering](../master-planning/planning-optimization/production-planning.md)

- [Inköpsrekvisitioner i huvudplaneringen](../master-planning/planning-optimization/purchase-requisitions.md)

## <a name="additional-resources"></a>Ytterligare resurser

### <a name="platform-updates-for-finance-and-operations-apps"></a>Plattformsuppdateringar för Finance and Operations-appar

Microsoft Dynamics 365 Supply Chain Management 10.0.17 inkluderar plattformsuppdateringar. Mer information finns i [plattformsuppdateringar för version 10.0.17 av Finance and Operations appar (april 2021)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-17.md).

### <a name="bug-fixes"></a>Felkorrigeringar

Om du vill ha information om felkorrigeringar som ingår i varje uppdatering som ingår i 10.0.17 loggar du in på Lifecycle Services (LCS) och visar [KB-artikel](https://fix.lcs.dynamics.com/Issue/Details?bugId=551039&dbType=3&qc=91219e7c3fc585acb17b810c915c3cbea499403538520c40e54de43a53aea6a8).

### <a name="dynamics-365-2021-release-wave-1-plan"></a>Dynamics 365: 2021 utgivningsvåg 1 plan

Har du frågeställningar om nya och kommande funktioner i våra affärsappar eller plattformen?

Se [Dynamics 365: 2021 utgivningsvåg 1 plan](/dynamics365-release-plan/2021wave1/). Vi har sammanställt all information som du kan tänkas behöva på ett enskilt dokument som du kan använda för din planering.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>Borttagna och inaktuella funktioner för Supply Chain Management

De [borttagna eller föråldrade funktionerna i Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) i ämnet beskriver funktioner som har schemalagts eller är planerade att tas bort eller inaktuellt för Supply Chain Management.

- En *borttagen* funktion är inte längre tillgänglig i produkten.
- En *borttagen* funktion är inte i aktiv utveckling och kan tas bort i en kommande uppdatering.

Innan någon funktion tas bort från produkten visas understrykningsmeddelandet i ämnet [borttagna eller inaktuella funktionerna i Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) 12 månader före avhämtningen.

För att bryta ändringar som endast påverkar kompileringen, men är binära kompatibla med begränsade lägen och produktionsmiljöer, blir utgångstiden mindre än 12 månader. Vanligtvis är dessa funktionsuppdateringar som måste göras till kompileraren.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
