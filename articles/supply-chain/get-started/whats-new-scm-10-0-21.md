---
title: Nyheter och ändringar i Dynamics 365 Supply Chain Management 10.0.21 (oktober 2021)
description: Det här ämnet beskriver nya eller ändrade funktioner i Dynamics 365 Supply Chain Management 10.0.21.
author: kamaybac
ms.date: 08/09/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-08-02
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: 3f586a00943e23b458ede1470b353d7c018ba923
ms.sourcegitcommit: ecd4c148287892dcd45656f273401315adb2805e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/18/2021
ms.locfileid: "7500565"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-10021-october-2021"></a>Nyheter och ändringar i Dynamics 365 Supply Chain Management 10.0.21 (oktober 2021)

[!include [banner](../includes/banner.md)]

Det här ämnet anger nya eller ändrade funktioner i Microsoft Dynamics 365 Supply Chain Management version 10.0.21. Den här versionen har ett versionsnummer för 10.0.960 och är tillgänglig enligt följande:

- **Förhandsversion av versionen:** Augusti 2021
- **Allmän tillgänglighet för versionen (självuppdatering):** September 2021
- **Allmän tillgänglighet för versionen (automatisk uppdatering):** Oktober 2021

## <a name="known-deployment-issue"></a>Känt distribueringsproblem

När du distribuerar version 10.0.21 på IaaS kan du få följande distributionsvarning:

**Varningskod:** 95017

**varningsmeddelande:** Skriptet \[SetupDiagnostics\] kunder inte köras mot VM

Distributionen fungerar trots varningen. Följande kända problem kan dock uppstå i Lifecycle Services (LCS):

- På sidan **Miljöövervakning** visas inte länken **Visa detaljerad versionsinformation**, så du kan inte se specifika versioner av de moduler som har installerats i miljön. Om du inte använder dessa data kan efterföljande snabbkorrigeringar misslyckas eftersom processen som använder snabbkorrigeringar använder dessa data för att verifiera att förutsättningarna för modulversionen är uppfyllda. Eftersom det inte går att använda PEAP/Preview-bygget i produktionen eller tillämpa snabbkorrigeringar bör påverkan bli minimal.
- Flikarna **Prestandamått** och **Indexanalys** på sidan **Miljöövervakning** under SQL Insights visar inga data. Alla andra funktioner för **Miljöövervakning** fungerar som de ska.
- Sidan **Fullständig systemdiagnostik** går inte att komma åt. Associerade data om status för nattliga insamlarkörningar och problem som upptäckts av dess regler visas inte heller.

## <a name="features-included-in-this-release"></a>Funktioner som ingår i den här versionen

Följande register lista de funktioner som ingår i denna version: Kolumnen *Funktion* innehåller länkar till [versionsplanen](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features), där du kan se de officiella frisläppningsdatumen för respektive funktion. Kolumnen *Mer information* innehåller mer information och/eller länkar till relaterad dokumentation.

De flesta av dessa funktioner måste aktiveras med [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) innan du kan använda dem.

| Funktionsområde | Funktion | Mer information |
|---|---|---|
| Lager&nbsp;och&nbsp;logistik | [Tillägget Global lagerredovisning för Dynamics 365 Supply Chain Management](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/global-inventory-accounting-add-in-dynamics-365-supply-chain-management) | [Startsida för global lagerredovisning](../global-inventory-accounting/global-inventory-accounting-home.md) |
| Lager&nbsp;och&nbsp;logistik | [Bokför behållningsjusteringar med koder kopplade till motkonton](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/post-on-hand-adjustments-using-configurable-reason-codes-connected-offset-accounts) | [Orsakskoder för lagerinventering](../warehousing/reason-codes-for-counting-journals.md) |
| Lager&nbsp;och&nbsp;logistik | [Dataexportpolicy som refereras i försäljningsoffert](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/sales-quotation-referenced-data-export-policy) | Välj om ändringar av data som refereras av offerter ska göra att dessa offerter (eller rader) inkluderas i nästa stegvisa export. Din stegvisa export går snabbare om du väljer att inte ta med sådana offerter eller rader.<br><br>Funktionen lägger till en inställning som heter **Hoppa över offertrefererad data vid ändringsspårning** på sidan **Parametrar för kundreskontra**. |
| Lager&nbsp;och&nbsp;logistik | Stängd budgivning <!-- KFM: Add RP link when available --> | [Sluten budgivning för anbudsförfrågningar](../procurement/sealed-bidding.md) |
| Lager&nbsp;och&nbsp;logistik | [Skanna streckkoder på lagerstället med standarder för GS1-format](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/scan-barcodes-warehouse-using-gs1-format-standards) | [GS1-streckkoder och QR-koder](../warehousing/gs1-barcodes.md) |
| Lager&nbsp;och&nbsp;logistik | [Preliminär reservation för tillägget Lagersynlighet](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/soft-reservation-inventory-visibility-add-in) | [Reservationer för Lagersynlighet](../inventory/inventory-visibility-reservations.md) |
| Lager&nbsp;och&nbsp;logistik | [Avdrag och ökningar av faktisk nominell vikt för Rabatthantering](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/deduction-catch-weight-enhancements-rebate-management) | [Hantera avdrag med workbench för avdrag](../rebate-management/deduction-workbench.md )<br><br>[Bearbeta, granska och bokföra rabatter](../rebate-management/process-review-post.md)<br><br>[Rabatthanteringsavtal](../rebate-management/rebate-management-deals.md) |
| Lager&nbsp;och&nbsp;logistik | [Steginstruktioner för lagerställeapp](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/warehouse-management-mobile-app-step-instructions) | [Anpassa stegpaneler och instruktioner för mobilappen Warehouse Management](../warehousing/mobile-app-titles-instructions.md) |
| Lager&nbsp;och&nbsp;logistik | [Arbetsraster och spårningsuppdateringar för hemtagningskostnad](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/work-breaks-tracking-updates-landed-cost) | [Uppdatera spårning för införsel](../landed-cost/update-tracking-putaway.md )<br><br>[Bearbetning av varor på väg](../landed-cost/in-transit-processing.md) |
| Huvudplanering | [Negativa dagar för planeringsoptimering](/dynamics365-release-plan/2021wave1/finance-operations/dynamics365-supply-chain-management/negative-days-support-planning-optimization) | [Fördröjningstolerans (negativa dagar)](../master-planning/planning-optimization/delay-tolerance.md) |

## <a name="feature-enhancements-included-in-this-release"></a>Funktionsförbättringar som ingår i den här versionen

Följande register lista de funktionsförbättringar som ingår i denna version: Var och en av dessa tillhandahåller en stegvis förbättring av en befintlig funktion. Eftersom de bara är förbättringar visas de inte i [frisläppningsplanen](/dynamics365-release-plan/2021wave2/finance-operations/dynamics365-supply-chain-management/planned-features). För att säkerställa att dessa förbättringar inte står i konflikt med dina befintliga anpassningar eller inställningar stängs var och en av dem av som standard (om inget annat anges). Om du vill använda någon av dessa funktioner måste du explicit aktivera dem i [Funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Funktionsområde | Funktionsnamn&nbsp;&nbsp;i&nbsp;funktionshantering | Mer information |
|---|---|---|
| Kostnadshantering | Information om lagerstängningsförlopp | Förhandsgranskningsfunktionen ger en detaljerad vy över förloppet för lagerstängning. |
| Anskaffning och källa | Förhindra överkonsumering av huvudbudgetreservationer när flera inköpsrekvisitioner finns i arbetsflöde | Förhandsgranskningsfunktionen förbättrar felkontrollen när användarna skickar och godkänner inköpsrekvisitioner som överskrider återstående saldo på en generell budgetreserveringsrad. Det förhindrar att generella budgetreserveringar överkonsumeras när flera inköpsrekvisitioner är i ett arbetsflöde. |
| Produktionskontroll | Visa fullständiga serienummer, batch- och ID-nummer i gränssnittet för produktionsgolvkörning | Funktionen ger en förbättrad upplevelse av att visa listor med serie-, batch- och ID-nummer i gränssnittet för körning på produktionsgolv. Visningen ändras från en kortvy med begränsat antal tecken till en listvy som har tillräckligt utrymme för att visa de fullständiga värdena. Du kan också söka efter särskilda nummer i listan. |
| Försäljning och marknadsföring | Begränsa antalet försäljningsorder som går att välja för bokföring | Med hjälp av den här funktionen kan du definiera det högsta antalet försäljningsorder som kan väljas när du bokför bekräftelser, plocklistor, följesedlar och fakturor från listsidan för försäljningsorder. Den aktiveras automatiskt. Funktionen lägger till en inställning med namnet **Max. antal försäljningsorder för bokföring** på sidan **Parametrar för kundreskontra**. Den nya inställningen får standardvärdet *100*. Funktionen hjälper till att förbättra prestandan för listsidan för försäljningsorder när ett visst antal försäljningsorder väljs. Den påverkar inte antalet försäljningsorder som kan bearbetas med en periodisk uppgift. |
| Lagerstyrning | Avkoda platsarbete från ASN:er | Funktionen måste skicka och ta emot avancerade leveransmeddelanden (ASNs) när du kör en arbetsbelastning för lagerhantering på en skalningsenhet (som en del av en distribuerad topologi). Det lägger till ett nytt databasregister avsett att lagra information om införselarbete. Tidigare lagrades denna information i register som även används för ASNs. |
| Lagerstyrning | Blandade enheter i fack | Gör att systemet kan placera artiklar på platser med blandade enheter (till exempel både rutor och lådor). För varje placeringsmallrad kan du med funktionen välja om raden ska placera artiklar på platser med mixade enheter eller platser med enstaka enhet. |
| Lagerstyrning | Använd snabbare API för behållare som stängs/öppnas igen på förpackningsstationen | När förhandsgranskningsfunktionen är aktiverad skapas lagertransaktioner som är relaterade till behållare med hjälp av en ny lättviktsprocess som förbättrar prestandan när behållare stängs eller öppnas igen under manuell packningsbearbetning. |

## <a name="new-and-updated-documentation-resources"></a>Nya och uppdaterade dokumentationsresurser

Följande hjälpavsnitt har nyligen lagts till eller uppdaterats väsentligt. De är inte nödvändigtvis relaterade till de nya funktioner som har lagts till för den här versionen, vilket visas i föregående avsnitt, men de kan hjälpa dig att få ut mer av befintliga funktioner.

| Funktionsområde | Nya eller uppdaterade ämnen |
|---|---|
| Huvudplanering | [Lagerprognoser](../master-planning/inventory-forecast.md) |
| Huvudplanering | [Parametrar som inte används i Planeringsoptimering](../master-planning/planning-optimization/not-used-parameters.md) |
| Huvudplanering | [Lagerpåfyllnadsmetoder och kvantitetsändring](../master-planning/planning-optimization/replenishment-methods-quantity-modification.md) |
| Huvudplanering | [Tidsplanering med obegränsad kapacitet](../master-planning/planning-optimization/infinite-capacity-planning.md) |
| Huvudplanering | [Visa planhistorik och planeringsloggar](../master-planning/planning-optimization/plan-history-logs.md) |
| Lagerstyrning | [Strategier för förpackning av behållare](../warehousing/container-packing-strategy-overview.md) |
| Lagerstyrning | [Exempelscenarier för rullande inventering](../warehousing/cycle-counting-scenarios.md) |
| Lagerstyrning | [Importera inkommande ASN:er via V2-datatabellen](../warehousing/import-asn-v2-data-entity.md) |
| Lagerstyrning | [Överplockning för försäljningsorder och överföringsorder](../warehousing/over-picking-for-sales-and-transfer-orders.md) |
| Lagerstyrning | [Schemalägga utskrift av påfyllnadsetikett under cykel](../warehousing/configure-task-based-wave-label-printing.md) |
| Lagerstyrning | [Vad är nytt eller ändrat i mobilappen Warehouse Management](../warehousing/whats-new-wma.md) |

## <a name="additional-resources"></a>Ytterligare resurser

### <a name="platform-updates-for-finance-and-operations-apps"></a>Plattformsuppdateringar för Finance and Operations-appar

Microsoft Dynamics 365 Supply Chain Management 10.0.21 inkluderar plattformsuppdateringar. Mer information finns i [plattformsuppdateringar för version 10.0.21 av Finance and Operations appar (oktober 2021)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-21.md).

### <a name="bug-fixes"></a>Felkorrigeringar

Om du vill ha information om felkorrigeringar som ingår i varje uppdatering som ingår i 10.0.21 loggar du in på Lifecycle Services (LCS) och visar [KB-artikel](https://fix.lcs.dynamics.com/Issue/Details?bugId=605166&dbType=3&qc=4b9449bf0d947113983bd0697140bf4d8727bfafd5566aa682cb38db343374de).

### <a name="dynamics-365-and-industry-clouds-2021-release-wave-2-plan"></a>Dynamics 365 och branschmoln: Utgivningsvåg 2 plan för 2021

Har du frågor om nya och kommande funktioner i våra affärsappar eller plattformen?

Kolla in [Dynamics 365 och branschmoln: Utgivningsvåg 2 plan för 2021](/dynamics365-release-plan/2021wave2/). Vi har sammanställt all information som du kan tänkas behöva på ett enskilt dokument som du kan använda för din planering.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>Borttagna och inaktuella funktioner för Supply Chain Management

De [borttagna eller föråldrade funktionerna i Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) i ämnet beskriver funktioner som har schemalagts eller är planerade att tas bort eller inaktuellt för Supply Chain Management.

- En *borttagen* funktion är inte längre tillgänglig i produkten.
- En *borttagen* funktion är inte i aktiv utveckling och kan tas bort i en kommande uppdatering.

Innan någon funktion tas bort från produkten visas understrykningsmeddelandet i ämnet [borttagna eller inaktuella funktionerna i Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) 12 månader före avhämtningen.

För att bryta ändringar som endast påverkar kompileringen, men är binära kompatibla med begränsade lägen och produktionsmiljöer, blir utgångstiden mindre än 12 månader. Vanligtvis är dessa funktionsuppdateringar som måste göras till kompileraren.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
