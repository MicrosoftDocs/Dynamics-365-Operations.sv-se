---
title: Förhandsversion av Dynamics 365 Commerce 10.0.29 (oktober 2022)
description: Denna artikel innehåller en beskrivning av nya eller ändrade funktioner i Microsoft Dynamics 365 Commerce 10.0.29.
author: josaw1
ms.date: 08/17/2022
ms.topic: article
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2022-08-01
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: 1e05f53f9ecb0a1994828172f6999a0bd5c208bc
ms.sourcegitcommit: f2175fe5e900d39f34167d671aab5074b09cc1b8
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/17/2022
ms.locfileid: "9306243"
---
# <a name="preview-of-dynamics-365-commerce-10029-october-2022"></a>Förhandsversion av Dynamics 365 Commerce 10.0.29 (oktober 2022)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Denna artikel anger nya eller ändrade funktioner i Microsoft Dynamics 365 Commerce förhandsversion version 10.0.29. Den här versionen har ett versionsnummer för 10.0.1326 på följande schema:

- **Förhandsversion av versionen:** Augusti 2022
- **Allmän tillgänglighet för versionen (självuppdatering):** September 2022
- **Allmän tillgänglighet för versionen (automatisk uppdatering):** Oktober 2022

## <a name="features-included-in-this-release"></a>Funktioner som ingår i den här versionen

Följande tabeller listar de funktioner som ingår i denna version. Vi kan komma att uppdatera denna artikel att inkludera funktioner somlades till i versionen efter det att denna artikel ursprungligen publicerades.

| Funktionsområde | Funktion | Mer information | Har aktiverats av |
|---------|------------------|----------------|--------------| 
| B2B | [Aktivera stöd för försäljningsavtal i kanaler](/dynamics365-release-plan/2022wave2/commerce/dynamics365-commerce/enable-b2b-sales-agreement-contract-based-pricing) | Med denna funktion kan säljare från B2B använda försäljningsavtal i Commerce headquarters för att definiera kontraktsbaserad prissättning för sina inköpare. När en B2B-köpare handlar på e-handelswebbplatsen, tillämpas det kontraktsbaserade pris som konfigureras för B2B-köparens organisation automatiskt på hela produktidentifieringen, inköpet och utcheckningsupplevelsen. | Funktionshantering<p>*Stöd för försäljningsavtal i handelskanaler* |
| Kundtjänst | [Aktivera Kundtjänst med Dynamics 365 Flerkanal för Customer Service](/dynamics365-release-plan/2022wave2/commerce/dynamics365-commerce/chat-dynamics-365-commerce-omnichannel-customer-service) | En kundsupport av högsta klass är nyckeln till att tillhandahålla en anpassad och bra handelserfarenhet för kunder. Det finns just nu flera handels kontaktpunkter, till exempel fysiska butiker, onlinekanaler och sociala kanaler. Kunderna förväntar sig en anpassad supporterfarenhet med alla dessa pekskärmar. Den här funktionen hjälper dig att öka varukorgsomvandlingarna till försäljning, öka personligt engagemang med konsumenter och förbättra kundtjänst genom att integrera med Dynamics 365 flerkanal för Customer Service. | Aktiveras av admin/tillverkare |
| Näthandel | Stöd för produktjämförelse i e-handel | Gör det möjligt för kunder att jämföra produkter inom många olika kategorier så att de kan fatta rätt inköp beslut själva. Den här funktionen är tillgänglig för både B2C- och B2B-webbplatser. | Webbplatsskaparen | 
| Presentkort | Stöd för butikspresentkortregister för datadelning mellan företag | Dynamics headquarters stöder möjligheten att aktivera datadelning mellan företag för specifika register i Dynamics-arkitekturen. I denna funktion lägger Dynamics 365 Commerce till stöd för datadelning mellan företag för butikspresentkortregister. Därför kan ett presentkort i ett företag nu kopiera data till ett annat företag i miljön. Ändringar som görs i det ursprungliga företagets presentkortsregister delas i det dubblerade registret för företagspresentkort. | Utvecklare |
| Globalisering | [Aktivera Commerce-lokaliseringsfunktioner för nya Commerce SDK](/dynamics365-release-plan/2022wave2/commerce/dynamics365-commerce/enable-commerce-localization-features-new-commerce-sdk) | Den nya funktionen ger möjlighet att aktivera Commerce-lokaliseringsfunktioner från Commerce headquarters genom att använda ramverket för funktionshantering eller parametrar. Skatteintegrationsexempel inkluderas nu i det nya Commerce SDK och stöder oberoende förpackning. Den här funktionen aktiverar även funktionen för Store Commerce-appen för globala Commerce-kunder.<p><p>Den här versionen innehåller Commerce lokaliseringsfunktioner och exempel på skatteintegration för [Österrike](../localizations/emea-aut-fi-sample.md), [Tjeckien](../localizations/emea-cze-fi-sample.md), [Frankrike](../localizations/emea-fra-cash-registers.md), [Tyskland](../localizations/emea-deu-fi-sample.md), [Italien](../localizations/emea-ita-fpi-sample.md), [Norge](../localizations/emea-nor-cash-registers.md) och [Polen](../localizations/emea-pol-fpi-sample.md). | Aktiveras av admin/tillverkare |
| Prestanda | Ta bort RTS-beroende för "redigera kund"-scenarier | Hög tillgänglighet och hög prestanda är standardförväntningar för kassa och e-handelskanaler. För att uppfylla dessa önskemål behöver Dynamics 365 Commerce kanaler inte längre vara beroende av realtidskommunikation med Commerce headquarters när kundinformation redigeras. Möjligheten att redigera kundinformation asynkront för asynkrona och icke-asynkrona kunder kan hjälpa till att reducera realtidssamtal till Commerce headquarters. | Aktiveras av admin/tillverkare |

## <a name="feature-state-changes-in-this-release"></a>Funktionstillstånd ändras i den här versionen

Följande tabell listar funktioner som blev obligatoriska eller aktiverade som standard i version 10.0.29. Alla dessa funktioner aktiveras automatiskt för ditt system så snart du uppdaterar till version 10.0.29. Obligatoriska funktioner kan inte stängas av, men funktioner som är på som standard kan fortfarande stängas av med [Funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

Tabellen visar även funktioner som tidigare var offentliga, men som har ändrats till att bli allmänt tillgängliga i version 10.0.29. Den här ändringen indikerar att funktionerna nu rekommenderas för användning i produktionsmiljöer. Dessa funktioner är avstängda som standard om inget annat anges. Därför måste du använda [Funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att aktivera dem om du vill använda dem.

| Funktion | Titel | Nytt funktionstillstånd |
| --- | --- | --- |
| BrazilRetailLocalizationFeature_BR |(Brasilien) Commerce-funktionalitet som är specifik för Brasilien | På som standard |
| RetailAdvancedGTETaxAdjustmentFeature | (Indien) Tillämpa GST beräknat för butikstransaktioner i Retail POS till butiksutdrag | På som standard |
| RetailChronologicalInvoicePostingFeature_IT | (Italien) Aktivera butiksfakturor bokförda utan att vara i kronologisk ordning | På som standard |
| RetailDiscountWithoutTaxAdjustingFeature_MX | (Mexiko) Rabattjustering i CFDI-global för detaljhandel. | På som standard |
| RetailFiscalIntegrationConfigurationEnhancementFeature | Åsidosättningar av räkenskapsintegration för teknisk profil | På som standard |
| RetailFiscalIntegrationConnectorLocationFeature | Direkt räkenskapsintegration från kassaregister | På som standard |
| RetailFiscalIntegrationLocalStorageBackupEnableFeature | Säkerhetskopiering av lokal datalagring för bokföringsintegrering | På som standard |
| RetailFiscalIntegrationPostponeFiscalRegistrationFeature | Senareläggning av registrering av dokument | På som standard |
| RetailFiscalIntegrationRegistrationProcessTerminalExceptionFeature | Räkenskapsregistreringstillstånd för kassaregister | På som standard |
| RetailGSTInvoiceAddressTaxCalculationFeature_IN | (Indien) Beräkna GST baserat på fakturaadress för näthandelsorder | På som standard |
| RetailInvoicesDefaultSalesDocumentStatusFeature_PL | (Polen) Standardstatus för försäljningsdokument för butiksfakturor | På som standard |
| RetailRecalculateRoundingOfTaxBaseAmountsFeature_MX | (Mexiko) Avrundning av omberäkning för skattebasbelopp i CFDI-global för Retail. | På som standard |
| RetailSupplementaryInvoiceFeature | Aktivera kompletterande fakturor för hämtköpstransaktioner som genomförs i butiker | På som standard |
| RetailInventoryBufferAndInventoryLevelEnableFeature   |  Aktivera lagerbuffertar och lagernivåer    |  På som standard|
|RetailInboundOutboundInventoryValidationFeature|   Aktivera validering i kassa inkommande och utgående lageråtgärder   |   På som standard   |
|  RetailInventoryChannelCalculationConsolidationFeature    |  Förbättrad lagerberäkningslogik för näthandel på kanalsidan |   På som standard   |
|RetailInventoryAdjustmentsInPointOfSaleFeature|    Lagerjusteringar i kassan   |  På som standard  |
| RetailMultiplePickupDeliveryModeFeature |  Stöd för flera upphämtningssätt för leverans     |   Obligatoriskt    |
|  RetailProductAvailabilityOptimizationFeature |   Optimerad beräkning av produkttillgänglighet  |  Obligatoriskt |
|   RetailPricingDataManagerV2Feature   |   Förbättra prestanda för Commerce-prissättningsmotor |   Obligatoriskt |
|  RetailPricingPreventUnintendedRecalculationFeature   | Förhindra oavsiktlig prisberäkning för handelsorder    |  Obligatoriskt  |
| RetailTeamsIntegration    |   Aktivera Microsoft Teams-integration| Obligatoriskt   |  
| ConsumerEFDSyncProcessFeature_BR | (Brasilien) NFC-e-synkron bearbetning | På som standard |
| RetailFiscalIntegrationInternalAndExternalServicesEnableFeature | Stöd för interna och externa kopplingar i ramverket för skatteintegration | Obligatoriskt |
| RetailTaxRegistrationIdEnableFeature_BR | (Brasilien) Sök efter kunder i Retail POS efter momsregistreringsnummer | Obligatoriskt |
| RetailTaxRegistrationIdEnableFeature_IN | (Indien) Sök efter kunder i Retail POS efter momsregistreringsnummer | Obligatoriskt |
| RetailTaxRegistrationIdEnableFeature_IT | (Italien) Kundinformationshantering i Retail POS | Obligatoriskt |
| RetailTaxRegistrationIdEnableFeature_PL | (Polen) Kundinformationshantering i Retail POS | Obligatoriskt |
| RetailUpdateReturnOriginalTransactionIdGlobalEnableFeature_IN | (Butik, GST (moms) för Indien) Uppdatera kreditfakturor med referenser till ursprungliga fakturor | Obligatoriskt |
| RetailUserDefinedCertificateProfileFeature | Användardefinierade certifikatprofiler för butiker | Obligatoriskt |
  

## <a name="additional-resources"></a>Ytterligare resurser

### <a name="platform-updates-for-finance-and-operations-apps"></a>Plattformsuppdatering för Ekonomi och drift-appar

Microsoft Dynamics 365 Commerce 10.0.29 inkluderar plattformsuppdateringar. Mer information finns i [Plattformsuppdateringar för version 10.0.29 av Ekonomi och Drift-appar (oktober 2022)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-29.md). 

### <a name="bug-fixes"></a>Felkorrigeringar

Om du vill ha information om felkorrigeringar som ingår i varje uppdatering som ingår i version 10.0.29 loggar du in på Lifecycle Services (LCS) och visar [KB-artikel](https://fix.lcs.dynamics.com/Issue/Details?bugId=726559&dbType=3&qc=ec3e3846199f5d3a27a0c4949e3902ffdbc87560f0cf928c4838b3bdd421633c). 

### <a name="dynamics-365-and-industry-clouds-2022-release-wave-2-plan"></a>Dynamics 365 och branschmoln: Utgivningsvåg 2 plan för 2022

Har du frågor om nya och kommande funktioner i våra affärsappar eller plattformen?

Kolla in [Dynamics 365 och branschmoln: Utgivningsvåg 2 plan för 2022](/dynamics365-release-plan/2022wave2/). Vi har sammanställt all information som du kan tänkas behöva på ett enskilt dokument som du kan använda för din planering.

### <a name="removed-and-deprecated-features"></a>Borttagna och inaktuella funktioner

[Funktionerna som tas bort eller avskrivs i Dynamics 365 Commerce](removed-deprecated-features-commerce.md) artikeln beskriver funktioner som har tagits bort eller avskrivts för Handel.

- En *borttagen* funktion är inte längre tillgänglig i produkten.
- En *borttagen* funktion är inte i aktiv utveckling och kan tas bort i en kommande uppdatering.

Innan någon funktion tas bort från produkten kommer meddelandet om inaktualitet att meddelas i artikeln [Borttagna eller inaktuella funktioner i Dynamics 365 Commerce](removed-deprecated-features-commerce.md) 12 månader före borttagning.

För att bryta ändringar som endast påverkar kompileringen, men är binära kompatibla med begränsade lägen och produktionsmiljöer, blir utgångstiden mindre än 12 månader. Vanligtvis är dessa funktionsuppdateringar som måste göras till kompileraren.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
