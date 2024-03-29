---
title: Nyheter och ändringar i Dynamics 365 Supply Chain Management 10.0.26 (maj 2022)
description: Denna artikel beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Supply Chain Management 10.0.26.
author: kamaybac
ms.date: 03/01/2022
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-03-01
ms.dyn365.ops.version: 10.0.26
ms.openlocfilehash: db8799aba8095c8144d878c96590e8d90276726b
ms.sourcegitcommit: 3d7ae22401b376d2899840b561575e8d5c55658c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/08/2022
ms.locfileid: "9428234"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-10026-may-2022"></a>Nyheter och ändringar i Dynamics 365 Supply Chain Management 10.0.26 (maj 2022)

[!include [banner](../includes/banner.md)]

Denna artikel anger nya eller ändrade funktioner i Microsoft Dynamics 365 Supply Chain Management version 10.0.26. Den här versionen har ett versionsnummer för 10.0.1192 och är tillgänglig enligt följande:

- **Förhandsversion:** mars 2022
- **Allmän tillgänglighet för frisläppning (självuppdatering):** april 2022
- **Allmän tillgänglighet för frisläppning (automatisk uppdatering):** maj 2022

## <a name="features-included-in-this-release"></a>Funktioner som ingår i den här versionen

Följande tabeller listar de funktioner som ingår i denna version. Vi kan komma att uppdatera denna artikel i syfte att inkludera funktioner som kommit med i versionen efter det att denna artikel publicerades första gången.

| Funktionsområde | Funktion | Mer information | Har aktiverats av |
|---|---|---|---|
| Lager och logistik | [Frågor om tillgängligt lager som stöd för avancerade artiklar för lagerstyrning](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/inventory-visibility-support-advanced-warehouse-management) | [Stöd för lagersynlighet för WMS-artiklar](../inventory/inventory-visibility-whs-support.md) | Funktionshantering:<br>*Aktivera lagerartiklar i lagersynlighet* |
| Lager och logistik | [Framtida kvatiteter för tillägget Lagersynlighet](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/available-to-promise-inventory-visibility-add-in) | [Lagersynlighet- och ändringsplan för lagerbehållning som är disponibel att lova](../inventory/inventory-visibility-available-to-promise.md) | Aktiveras via tjänstekonfiguration |
| Tillverkning | [Artiklar med nominell vikt för produktionsgolvets körningsgränssnitt](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/catch-weight-items-production-floor-execution-interface) | [Hur arbetare använder körningsgränssnittet för produktionsgolvet](../production-control/production-floor-execution-use.md) | Funktionshantering:<br>*Rapportera artiklar med faktisk/nominell vikt från körningsgränssnittet för produktionsgolvet* |
| Tillverkning | Fliken Mina jobb på körningsgränssnittet för produktionsgolvet | [Hur arbetare använder körningsgränssnittet för produktionsgolvet](../production-control/production-floor-execution-use.md) | Funktionshantering:<br>*Fliken Mina jobb på körningsgränssnittet för produktionsgolvet* |

## <a name="feature-enhancements-included-in-this-release"></a>Funktionsförbättringar som ingår i den här versionen

Följande tabeller listar de funktionsförbättringar som ingår i denna version. Var och en av dessa förbättringar tillhandahåller en stegvis förbättring av en befintlig funktion. Eftersom de bara är förbättringar visas de inte i [utgivningsplanen](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planned-features). För att säkerställa att dessa förbättringar inte står i konflikt med dina befintliga anpassningar eller inställningar stängs var och en av dem av som standard (om inget annat anges).

Om du vill slå på eller stänga av någon av dessa funktioner måste du göra detta i [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Modul | Funktionsnamn i funktionshantering | Mer information |
|---|---|---|
| Anskaffning och källa | Bokför registrerade kvantiteter av produkter i lager och rester av produkter som inte finns i lager för inleveranser och leverantörsfakturor | Denna funktion ändrar hur kvantiteter av produkter som inte finns i lager (t.ex. tjänster) bokförs vid bearbetning av leverantörsfakturor och inkommande försändelser mot inköpsorder. Funktionen ändrar beteendet för kvantitetsalternativet *Registrerad kvantitet och registrerade tjänster* för bokföring av inleveranser och leverantörsfakturor genom att matcha det med beteendet för det alternativ för *Registrerad kvantitet och produkter som inte finns i lager* som redan tillhandahållits vid bokföring av kvantiteter för försäljningsföljesedlar.<br><br>När du bokför en produktinleverans- eller leverantörsfaktura med kvantitetsalternativet *Registrerad kvantitet och registrerade tjänster* bokför systemet den registrerade kvantiteten av lagrade produkter och bokför resterande kvantitet av produkter som inte finns i lager (inklusive både tjänster och icke-tjänster). Utan denna funktion bokför systemet fortfarande den registrerade kvantiteten av produkter i lager (inklusive tjänster som konfigurerats lagerartiklar) men bokför alltid den fullständiga beställda kvantiteten av tjänsteprodukter som inte finns i lager (och ignorerar icke-lagerförda produkter som inte är av typen *Tjänst*). |
| Anskaffning och källa | Synkronisera spårningsdimensioner på koncerninterna försäljnings- och inköpsorderrader | Med den här funktionen kan du kontrollera huruvida spårningsdimensionerna för serie- och batchnummer synkroniseras över koncerninterna försäljnings- och inköpsorderrader. Den lägger till nya inställningar på både fliken **Inköpsorderpolicyer** och fliken **Försäljningsorderpolicy** på inställningssidan **Koncernintern** för kunder och leverantörer. I tydlighetssyfte uppdaterar den även namnen på några relaterade, närliggande inställningar.<br><br>Om du använder lagerstyrningsprocesser (WMS), notera då att denna funktion endast synkroniserar batch- och löpnummer när dessa mått ligger ovanför platsen i målets reservationshierarki. |
| Produktinformationshantering | Rensa produktattributvärden | Denna funktion lägger till den periodiska uppgiften **Rensa produktattributvärden**, som rensar värdeposter för produktattribut som inte längre är associerade med en produkt genom produktkategori. |
| Hantering av lager och lagerstyrning | (Ryssland) Förhindra avvikelser vid utfärdande av GTD för inköpsorder som inkluderar WMS-aktiverade artiklar | Denna funktion är bara tillgänglig för Ryssland. Den förhindrar avvikelser som uppstår vid utfärdande av ryska tulldeklarationsnummer (GTD) för importinköpsorder som omfattar artiklar som har aktiverats för lagerstyrningsprocesser (WMS). GTD-utfärdandeprocessen ändrar vissa lagerdimensionsvärden på relaterade lagertransaktioner för fakturor som är inkluderade i den anpassade journalen, vilket leder till avvikelser mellan arbetsposterna för inköpsordern och lagertransaktionerna för inköpet. När den här funktionen är aktiverad genererar GTD-utfärdandeprocessen justeringsarbete som eliminerar sådana avvikelser. |
| Lagerstyrning | Utökad parser för GS1-streckkoder | Denna funktion lägger till en förbättrad parser för GS1-symboldata. Den nya parsern implementerar GS1 General Specification-algoritmen för parsning av GS1-symboler och ger starkare datavalidering. Mer information finns i [Skanning av GS1-streckkoder](../warehousing/gs1-barcodes.md). |
| Warehouse management | Lagerstyrningsprogram – tom GTD | Denna funktion är bara tillgänglig för Ryssland. Medarbetare som använder mobilapplikationen Lagerstyrning kan lämna numren för ryska tulldeklarationer (GTD) tomma vid behov. Om GTD-spårningsdimensionen har ställts in för att tillåta tomma värden, accepterar systemet tomma värden för GTD för lageråtgärder under förutsättning att lagerbehållning är tillgänglig. |

## <a name="new-and-updated-documentation-resources"></a>Nya och uppdaterade dokumentationsresurser

Följande hjälpartiklar har nyligen lagts till eller uppdaterats väsentligt. Dessa artiklar är inte nödvändigtvis relaterade till de nya funktioner som lagts till för denna version, enligt vad som beskrivs i de föregående avsnitten. De kan dock hjälpa dig att få ut mer av befintliga funktioner.

| Funktionsområde | Nya eller uppdaterade artiklar |
|---|---|
| Kostnadshantering | Uppdaterade exempel och diagram har lagts till i följande artiklar:<ul><li>[FIFO med fysiskt värde och markering](../cost-management/fifo-physical-value-marking.md)</li><li>[LIFO med fysiskt värde och markering](../cost-management/lifo-physical-value-marking.md)</li><li>[LIFO-datum med fysiskt värde och markering](../cost-management/lifo-date-physical-value-marking.md)</li><li>[Löpande genomsnittlig självkostnad](../cost-management/running-average-cost-price.md)</li><li>[Viktat genomsnitt med fysiskt värde och markering](../cost-management/weighted-average-physical-value-marking.md)</li></ul> |

## <a name="additional-resources"></a>Ytterligare resurser

### <a name="platform-updates-for-finance-and-operations-apps"></a>Plattformsuppdatering för appar för ekonomi och drift

Microsoft Dynamics 365 Supply Chain Management 10.0.26 inkluderar plattformsuppdateringar. Mer information finns i [Plattformsuppdateringar för version 10.0.26 av appar för ekonomi och drift (maj 2022)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-26.md).

### <a name="bug-fixes"></a>Felkorrigeringar

Om du vill ha information om felkorrigeringar som ingår i varje uppdatering som ingår i 10.0.26 loggar du in på Lifecycle Services (LCS) och visar [KB-artikel](https://fix.lcs.dynamics.com/Issue/Details?bugId=662864).

### <a name="dynamics-365-and-industry-clouds-2022-release-wave-1-plan"></a>Dynamics 365 och branschmoln: Utgivningsvåg 1 plan för 2022

Har du frågor om nya och kommande funktioner i våra affärsappar eller plattformen?

Kolla in [Dynamics 365 och branschmoln: Utgivningsvåg 1 plan för 2022](/dynamics365-release-plan/2022wave1/). Vi har sammanställt all information som du kan tänkas behöva på ett enskilt dokument som du kan använda för din planering.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>Borttagna och inaktuella funktioner för Supply Chain Management

Artikeln [Borttagna eller inaktuella funktionerna i Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) beskriver funktioner som har tagits bort eller planeras tas bort eller göras inaktuella för Supply Chain Management.

- En *borttagen* funktion är inte längre tillgänglig i produkten.
- En *borttagen* funktion är inte i aktiv utveckling och kan tas bort i en kommande uppdatering.

Innan någon funktion tas bort från produkten kommer meddelandet om inaktualitet att meddelas i artikeln [Borttagna eller inaktuella funktioner i Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) 12 månader före borttagning.

För att bryta ändringar som endast påverkar kompileringen, men är binära kompatibla med begränsade lägen och produktionsmiljöer, blir utgångstiden mindre än 12 månader. Vanligtvis är dessa funktionsuppdateringar som måste göras till kompileraren.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]

