---
title: Förhandsgranskning av Dynamics 365 Supply Chain Management 10.0.19 (juli 2021)
description: Det här ämnet beskriver nya eller ändrade funktioner i Dynamics 365 Supply Chain Management 10.0.19.
author: kamaybac
ms.date: 04/23/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-04-23
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 8bb4a7c8085b40ab3eca72675dbe7a3be412d8c1
ms.sourcegitcommit: 2eb7a9ae544f504155657c5c584cbac66c21dba4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/29/2021
ms.locfileid: "5961691"
---
# <a name="preview-of-dynamics-365-supply-chain-management-10019-july-2021"></a>Förhandsgranskning av Dynamics 365 Supply Chain Management 10.0.19 (juli 2021)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Det här ämnet anger nya eller ändrade funktioner i Microsoft Dynamics 365 Supply Chain Management förhandsversion 10.0.19. Den här versionen har ett versionsnummer för 10.0.837 och är tillgänglig enligt följande:

- **Förhandgranskning av version:** april 2021
- **Allmän tillgänglighet för version (självuppdatering):** juni 2021
- **Allmän tillgänglighet för version (automatisk uppdatering):** juli 2021

## <a name="features-included-in-this-release"></a>Funktioner som ingår i den här versionen

Följande register lista de funktioner som ingår i denna version: Kolumnen *Funktion* innehåller länkar till [versionsplanen](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/planned-features), där du kan se de officiella frisläppningsdatumen för respektive funktion. Kolumnen *Mer information* innehåller länkar till relaterad dokumentation.

De flesta av dessa funktioner måste aktiveras med [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) innan du kan använda dem. Vissa av funktionerna visas fortfarande i en förhandsversion, men andra användare kan redan vara tillgängliga i allmänhet.

| Funktionsområde | Funktion | Mer information |
|---|---|---|
| Lager och logistik | [Optimering av kontaktpersons datatabellsexport](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/contact-person-data-entity-export-optimization)  | *Inte tillgänglig* |
| Lager och logistik | [Stegvisa förbättringar av lagerställekörningskapaciteter med skalningsenheter](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/incremental-enhancements-warehouse-execution-capabilities-scale-units) |[Meddelandeprocessormeddelanden](../cloud-edge/cloud-edge-message-processor-messages.md)<br><br>[Lagerställets lagerjustering](../cloud-edge/cloud-edge-warehouse-inventory-adjustment.md)<br><br>[Arbetsbelastningar för distributionslagerhantering för moln- och kantskalningsenheter](../cloud-edge/cloud-edge-workload-warehousing.md) |
| Lager och logistik | [Sökfunktion för dokumentintroduktion och fält för dokumentsammanfattning på sidan dör försäljningsoffert](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/lookup-functionality-document-introduction-document-conclusion-fields-sales-quotation-page) | *Inte tillgänglig* |
| Lager och logistik | [Lagerställekörning med kantskalningsenheter på din anpassade maskinvara](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/warehouse-execution-edge-scale-units-custom-hardware) | [Distribuera kantskalningsenheter på anpassad maskinvara med HJÄLP LBD](../cloud-edge/cloud-edge-edge-scale-units-lbd.md) |
| Tillverkning | [Tillverkningskörning med kantskalningsenheter på din anpassade maskinvara](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/manufacturing-execution-edge-scale-units-custom-hardware) | [Distribuera kantskalningsenheter på anpassad maskinvara med HJÄLP LBD](../cloud-edge/cloud-edge-edge-scale-units-lbd.md) |
| Planering | Frågebaserad planerad order som bekräftar | [Bekräfta planerade order](../master-planning/planning-optimization/planned-order-firming.md) |
| Produktinformationshantering | [Förbättringar av sidan med variantförslag](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/variant-suggestions-page-improvements) | [Skapa fördefinierade produktvarianter](../pim/tasks/create-predefined-product-variants.md) |

## <a name="new-and-updated-documentation-resources"></a>Nya och uppdaterade dokumentationsresurser

Följande hjälpavsnitt har nyligen lagts till eller uppdaterats väsentligt. De är inte nödvändigtvis relaterade till de nya funktioner som har lagts till för den här versionen, vilket visas i föregående avsnitt, men de kan hjälpa dig att få ut mer av befintliga funktioner.

| Funktionsområde | Nya eller uppdaterade ämnen |
|---|---|
| Konstruktionsändringshantering | [Vanliga frågor och svar om konstruktionsändringshantering](../engineering-change-management/change-management-faq.md) |
| Anskaffning och källa | [Kategoribegäranden från leverantörer](../procurement/category-requests-from-vendors.md) |
| Produktinformationshantering | [Hantera måttenhet](../pim/tasks/manage-unit-measure.md)<br><br>[Beräkningar för produktkonfigurationsmodell](../pim/config-model-calculations.md) |
| Produktionskontroll | [Enhetlig nummerserie för jobb-ID:n](../production-control/unified-job-ids.md) |
| Transporthantering | [LTL-klasser](../transportation/ltl-class.md)<br><br>[NMFC-koder](../transportation/nmfc-codes.md) |
| Lagerstyrning | [Felsöka batch- och seriereservationshierarkier för distributionslager](../warehousing/troubleshoot-warehouse-batch-and-serial-reservation-hierarchies.md) |
| Lagerhantering, skapa och bearbeta cykel | [Skapa och bearbeta påfyllnad](../warehousing/wave-processing.md)<br><br>[Distributionslagerparametrar för påfyllnadsbearbetning](../warehousing/wave-warehouse-parameters.md)<br><br>[Påfyllnadsmallar](../warehousing/wave-templates.md)<br><br>[Påfyllnadsallokering](../warehousing/wave-allocation-method.md)<br><br>[Tidsplanera att skapa arbete under påfyllnad](../warehousing/configure-wave-schedule-work-creation.md)<br><br>[Skapande av behållare](../warehousing/wave-containerization.md)<br><br>[Meddelanden för påfyllnadskörning](../warehousing/wave-execution-notifications.md) |

## <a name="additional-resources"></a>Ytterligare resurser

### <a name="platform-updates-for-finance-and-operations-apps"></a>Plattformsuppdateringar för Finance and Operations-appar

Microsoft Dynamics 365 Supply Chain Management 10.0.19 inkluderar plattformsuppdateringar. Mer information finns i [plattformsuppdateringar för version 10.0.19 av Finance and Operations appar (juli 2021)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-19.md).

### <a name="bug-fixes"></a>Felkorrigeringar

Om du vill ha information om felkorrigeringar som ingår i varje uppdatering som ingår i 10.0.19 loggar du in på Lifecycle Services (LCS) och visar [KB-artikel](https://fix.lcs.dynamics.com/Issue/Details?bugId=575415).

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
