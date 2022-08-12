---
title: Nyheter och ändringar i Dynamics 365 Supply Chain Management 10.0.23 (januari 2022)
description: Denna artikel beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Supply Chain Management 10.0.23.
author: kamaybac
ms.date: 10/15/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-10-15
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: ded645ebaea1230b68525c247ee91e3893211774
ms.sourcegitcommit: 873d66c03a51ecb7082e269f30f5f980ccd9307f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/06/2022
ms.locfileid: "9124541"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-10023-january-2022"></a>Nyheter och ändringar i Dynamics 365 Supply Chain Management 10.0.23 (januari 2022)

[!include [banner](../includes/banner.md)]

Denna artikel anger nya eller ändrade funktioner i Microsoft Dynamics 365 Supply Chain Management-version 10.0.23. Den här versionen har ett versionsnummer för 10.0.1037 och är tillgänglig enligt följande:

- **Förhandsversion:** oktober 2021
- **Allmän tillgänglighet för frisläppning (självuppdatering):** 2021 december
- **Allmän tillgänglighet för frisläppning (automatisk uppdatering):** 2022 januari

## <a name="features-included-in-this-release"></a>Funktioner som ingår i den här versionen

Följande tabeller listar de funktioner som ingår i denna version. Kolumnen *Funktion* innehåller länkar till [versionsplanen](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features), där du kan se de officiella frisläppningsdatumen för respektive funktion. Kolumnen *Mer information* innehåller mer information och/eller länkar till relaterad dokumentation. Information om hur du aktiverar en funktion finns i kolumnen *Aktiverad av*. Mer information om hur du använder funktionshantering finns i [Översikt över funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md). Vi kan komma att uppdatera denna artikel i syfte att inkludera funktioner som kommit med i versionen efter det att denna artikel publicerades första gången.

| Funktionsområde | Funktion | Mer information | Har aktiverats av |
|---|---|---|---|
| Global adressbok | Definiera en standard delstat/region för varje land/region i adressinställningarna | Du kan nu definiera en standard delstat/region för varje land/region i adressinställningarna för den globala adressboken. När en standard delstat/region anges används standardvärdet som anges i regionfälten när du skapar en ny post för region eller ort för landet/regionen. Se även [Adressinställningar](../../fin-ops-core/fin-ops/organization-administration/global-address-book-address-setup.md?toc=/dynamics365/supply-chain/toc.json) | Aktiverad som standard. |
| Lager&nbsp;och&nbsp;logistik | [Pausa uppgifter och ansluta Warehouse Management-mobilappen](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/park-tasks-warehouse-management-mobile-app) | [Konfigurera omvägar för steg i menyalternativ för mobila enheter](../warehousing/warehouse-app-detours.md) | Funktionshantering (*Omvägar för lagerstyrningsapp)* |
| Lager&nbsp;och&nbsp;logistik | [Erbjudna fält i lagerställeapp](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/warehouse-management-mobile-app-step-instructions) | [Konfigurera stödsfält för steg i den mobila enheten](../warehousing/warehouse-app-promoted-fields.md)| Funktionshantering (*fält som stöds av lagerställeapp)* |
| Tillverkning | [Integrering av körningssystem för tillverkning](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/manufacturing-execution-systems-integration) | [Integrera med tillverkningskörningssystem från tredje part](../production-control/mes-integration.md) | Funktionshantering *(Integrering av körningssystem för tillverkning*) |
| Tillverkning | [Rapport om sam- och biprodukter från produktionsgolvets körningsgränssnitt](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/enhanced-production-floor-execution-interface-process-manufacturing) | [Hur arbetare använder körningsgränssnittet för produktionsgolvet](../production-control/production-floor-execution-use.md) | Funktionshantering (*Rapport om sam- och biprodukter från produktionsgolvets körningsgränssnitt*) |
| Planering | [Planera optimeringssupport för prioritetsbaserad planering](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planning-optimization-support-priority-based-planning) | [Prioritetsbaserad planering](../master-planning/planning-optimization/priority-based-planning.md) | Funktionshantering (*Prioritetsdriven MRP-support för Planeringsoptimering*) |

## <a name="feature-enhancements-included-in-this-release"></a>Funktionsförbättringar som ingår i den här versionen

Följande tabeller listar de funktionsförbättringar som är ny för denna version. Var och en av dessa förbättringar tillhandahåller en stegvis förbättring av en befintlig funktion. Eftersom de bara är förbättringar visas de inte i [utgivningsplanen](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features). För att säkerställa att dessa förbättringar inte står i konflikt med dina befintliga anpassningar eller inställningar stängs var och en av dem av som standard (om inget annat anges).

Om du vill aktivera eller inaktivera någon av dessa funktioner måste du göra det i [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), där de är listade med namnen som visas i *Funktionsnamn i funktionshantering* kolumn i följande tabell.

| Modul | Funktionsnamn i funktionshantering | Mer information |
|---|---|---|
| Tillgångshantering | Motkonton för utgifter i arbetsorderjournaler | Med hjälp av den här funktionen kan du ange ett motkonto för varje utgift som visas i en arbetsorderjournal. Du kanske vanligtvis kopplar ett leverantörskonto till varje utgift, men andra kontotyper stöds också. ger till två nya kolumner (**Motkontotyp** och **Motkonto**) till snabbfliken **Utgift** på sidan **Arbetsorderjournal**.|
| Kostnadshantering | Skapa relaterade verifikationer för omvärderingar av avrundningsavvikelser för standardkostnad | <p>När en ekonomisk lagerbokföring (till exempel en försäljningsorderfaktura eller lagertransaktion) görs, skapar den här funktionen en separat verifikation för alla relaterade omvärderingar av standardkostnadsavrundningar och kopplar den till den ekonomiska bokföringsverifikationen som en relaterad verifikation.</p><p>Utan den här funktionen registrerar systemet omvärderingar av standardkostnadsavrundningar på samma verifikationsbokföring. Detta beteende kan ibland skapa motstridig datuminformation eftersom omvärderingarna använder sessionen eller systemdatumet, medan ekonomiska bokföringar använder bokföringsdatumet.</p> |
| Hantering av lager och lagerstyrning | \[Ryssland\] Bokför ekonomiska lagertransaktioner för Storno enligt korrigeringsflaggan i den ekonomiska verifikationen för försäljningsorder | Den här funktionen påverkar funktionen för korrigering av kreditnotor i Ryssland. Det gör att lagertransaktioner kan bokföras för försäljningsfakturor i enlighet med korrigeringsalternativet i redovisningen. När den här funktionen är aktiverad finns det inga fler avvikelser mellan flaggan **korrigering** på den ekonomiska verifikationen för lagertransaktionen och flaggan **Storno** i lagertransaktioner. |
| Hantering av lager och lagerstyrning | (Ryssland) Kör beräkning av rapporten Omsättning för lagerbalans i batch | För ryska lokaliseringar av Supply Chain Management ger denna funktion möjlighet att köra rapporten *Omsättning för lagerbalans* i batch, lagra den och visa tidigare genererade rapporter. |
| Hantering av lager och lagerstyrning | (Ryssland) Använd översättning till lokalt språk i lands- eller regionsspecifika primära formulär i Lagerhantering | För ryska lokaliseringar av Supply Chain Management gör denna funktion det möjligt att använda ryska översättningar av produkt-/artikelnamn och måttenheter i följande specifika ryska lagerutskrifter:Inventeringslista (INV-3),Inventeringslista (INV-5),Inventeringslista (INV-6). |
| Huvudplanering | Azure Machine Learning Service för efterfrågeprognosticering | Med denna funktion kan Azure Machine Learning Service generera efterfrågeprognoser baserade på historiska data. Mer information finns i [Inställning av efterfrågeprognosticering](../master-planning/demand-forecasting-setup.md). |
| Anskaffning och källa | Rensa inköpsorderns uppdateringshistorik | Med hjälp av den här funktionen kan du rensa tillfälliga historiska poster som är relaterade till inköpsorderuppdateringar. Den lägger till en ny knapp med namnet **Rensa inköpsuppdateringshistorik** i åtgärdsfönstret på sidan **Alla inköpsorder**. Den här funktionen aktiveras som standard. |
| Produktionskontroll | (Förhandsversion) Automatisk plockning av lagerställeaktiverade material för automatiskt bokförda plocklistor | Den här funktionen gör det möjligt att välja och lösa lagerdimensioner för automatiskt bokförda, härledda/bakåtavräknade plocklistejournaler. |
| Produktionskontroll | Validera råmaterialets utgång mot planerat förbrukningsdatum | Den här funktionen ändrar hur utgångsdatum för batchar valideras när en batch med råmaterial reserveras för användning under produktionen. När den här funktionen är aktiverad valideras batchutgångsdatumet mot det planerade förbrukningsdatumet (råmaterialdatumet), enligt vad som är upprättat på produktionsstrukturlisteraden eller batchorderformelraden. När den här funktionen inaktiveras valideras batchens utgångsdatum mot det planerade leveransdatumet för tillverknings- eller batchordern (som tidigare). |
| Försäljning och marknadsföring | Rensa försäljningsuppdateringshistorik grundat på ålder | Med hjälp av den här funktionen kan du ange en högsta ålder för poster som ska behållas när den periodiska uppgiften **Rensning av försäljningsuppdateringshistorik**. Äldre poster raderas. Detta är användbart när du konfigurerar uppgiften så att den körs periodiskt, detta eftersom ålder alltid beräknas i relation till det datum då uppgiften körs. Utan den här funktionen kan du bara ange ett visst datum för de äldsta posterna som ska behållas. Mer information finns i [Schemalägga datarensning i försäljningshistorik](../sales-marketing/sales-update-history-cleanup-performance-improvements.md). |
| Försäljning och marknadsföring | Förbättra rapportresultat för de 100 främsta kunderna | Den här funktionen förbättrar prestandan hos de **100 bästa** kunderna genom att alltid köra rapporten över alla kunder (som är avsedd att användas) istället för att tillåta anpassade frågor. När den här funktionen är aktiverad, alla inställningar **Poster att inkludera** inaktiveras i rapportdialogrutan **Bästa 100**. |
| Lagerstyrning | Skalningsenhetsstöd för frisläppning till lagerställe för utgående order | När funktionen är aktiverad kan utgående ordrar frisläppas från hubben direkt till skalningsenheten, varifrån de uppfylls. |

## <a name="new-and-updated-documentation-resources"></a>Nya och uppdaterade dokumentationsresurser

Följande hjälpartiklar har nyligen lagts till eller uppdaterats väsentligt. Dessa artiklar är inte nödvändigtvis relaterade till de nya funktionerna som lagts till för denna version, enligt vad som beskrivs i det föregående avsnittet. De kan dock hjälpa dig att få ut mer av befintliga funktioner.

| Funktionsområde | Nya eller uppdaterade artiklar |
|---|---|
| Konstruktionsändringshantering | [Tekniska attribut och sökning efter tekniska attribut](../engineering-change-management/engineering-attributes-and-search.md) beskriver nu hur konstruktionsattributsarv fungerar. |
| Huvudplanering | [Huvudplanering med efterfrågeprognoser](../master-planning/planning-optimization/demand-forecast.md) och [reduceringsnycklar för prognoser](../master-planning/reduction-keys.md) ger nu mer information om hur du arbetar med reduceringsnycklar. |
| Huvudplanering | [Säkerhet för artiklar i lageruppfyllelse](../master-planning/safety-stock-replenishment.md) ger nu mer information om användning av minimum-/maximumnycklar. |
| Huvudplanering | [Lagerprognoser](../master-planning/inventory-forecast.md) ger nu mer information om fördelning av prognoser. |
| Huvudplanering | [Leveranstidsplan](../master-planning/supply-schedule.md) |
| Lagerstyrning | [Globala parametrar för mobilenheter](../warehousing/mobile-device-parameters.md) |
| Lagerstyrning | [Förankring](../warehousing/anchoring.md) |
| Försäljning och marknadsföring | Koncernintern handel beskrivs nu i detalj, börjar med [Ställa in koncernintern handel](../sales-marketing/intercompany-trade-set-up.md) och dess relaterade artiklar. |
| Försäljning och marknadsföring | [Förbättringar i prestanda för rensning av försäljningshistorik](../sales-marketing/sales-update-history-cleanup-performance-improvements.md) |
| Lagerhantering | Dokumentation för lagersynlighet har utökats och uppdaterats från och med [Tillägg för lagersynlighet – översikt](../inventory/inventory-visibility.md) och tillhörande artiklar. |
| Warehouse management | [Användarkonton för mobil enhet](../warehousing/mobile-device-work-users.md) |

## <a name="additional-resources"></a>Ytterligare resurser

### <a name="platform-updates-for-finance-and-operations-apps"></a>Plattformsuppdatering för appar för ekonomi och drift

Microsoft Dynamics 365 Supply Chain Management 10.0.23 inkluderar plattformsuppdateringar. Mer information finns i [Plattformsuppdateringar för version 10.0.23 av appar för ekonomi och drift (november 2021)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-23.md).

### <a name="bug-fixes"></a>Felkorrigeringar

Om du vill ha information om felkorrigeringar som ingår i varje uppdatering som ingår i 10.0.23 loggar du in på Lifecycle Services (LCS) och visar [KB-artikel](https://fix.lcs.dynamics.com/Issue/Details?bugId=627874&dbType=3&qc=9b7e01944eb8b43f9c3aac4be26811c27be205847d6d2a240424f34f7e722910).

### <a name="dynamics-365-and-industry-clouds-2021-release-wave-2-plan"></a>Dynamics 365 och branschmoln: Utgivningsvåg 2 plan för 2021

Har du frågor om nya och kommande funktioner i våra affärsappar eller plattformen?

Kolla in [Dynamics 365 och branschmoln: Utgivningsvåg 2 plan för 2021](/dynamics365-release-plan/2021wave2/). Vi har sammanställt all information som du kan tänkas behöva på ett enskilt dokument som du kan använda för din planering.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>Borttagna och inaktuella funktioner för Supply Chain Management

Artikeln [Borttagna eller inaktuella funktionerna i Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) beskriver funktioner som har tagits bort eller planeras tas bort eller göras inaktuella för Supply Chain Management.

- En *borttagen* funktion är inte längre tillgänglig i produkten.
- En *borttagen* funktion är inte i aktiv utveckling och kan tas bort i en kommande uppdatering.

Innan någon funktion tas bort från produkten kommer meddelandet om inaktualitet att meddelas i artikeln [Borttagna eller inaktuella funktioner i Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) 12 månader före borttagning.

För att bryta ändringar som endast påverkar kompileringen, men är binära kompatibla med begränsade lägen och produktionsmiljöer, blir utgångstiden mindre än 12 månader. Vanligtvis är dessa funktionsuppdateringar som måste göras till kompileraren.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

