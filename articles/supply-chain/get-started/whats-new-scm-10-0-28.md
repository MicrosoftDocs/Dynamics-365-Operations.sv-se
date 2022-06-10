---
title: Förhandsversion av Dynamics 365 Supply Chain Management 10.0.28 (augusti 2022)
description: Det här ämnet beskriver nya eller ändrade funktioner i Microsoft Dynamics 365 Supply Chain Management 10.0.28.
author: kamaybac
ms.date: 05/27/2022
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2022-05-27
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: 306ff9be80c7a7a947b9132e3c9b4b9ec799b265
ms.sourcegitcommit: 611202adaa080250636efabb3b3b32b850d92d04
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/28/2022
ms.locfileid: "8813116"
---
# <a name="preview-of-dynamics-365-supply-chain-management-10028-august-2022"></a>Förhandsversion av Dynamics 365 Supply Chain Management 10.0.28 (augusti 2022)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Detta ämne anger nya eller ändrade funktioner i Microsoft Dynamics 365 Supply Chain Management, förhandsversion 10.0.28. Den här versionen har ett versionsnummer för 10.0.1264 på följande schema:

- **Förhandsversion:** maj 2022
- **Allmän tillgänglighet för version (självuppdatering):** juli 2022
- **Allmän tillgänglighet för version (automatisk uppdatering):** juli 2022

## <a name="features-included-in-this-release"></a>Funktioner som ingår i den här versionen

Följande tabeller listar de funktioner som ingår i denna version. Vi kan komma att uppdatera detta ämne i syfte att lades till i bygget efter att detta ämne ursprungligen publicerades.

| Funktionsområde | Funktion | Mer information | Har aktiverats av |
|---|---|---|---|
| Lager och logistik | [Landade kostnadsintegrationsenheter för tredjeparts speditörer](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/landed-cost-integration-third-party-freight-forwarders) | [Landade kostnadsenheter – översikt](../landed-cost/landed-cost-entities-overview.md) | Aktiverad som standard |
| Planering | [Planering Optimeringsstöd för hållbarhetstid](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planning-optimization-support-shelf-life) | Kommer snart <!-- KFM: Vendor is preparing this. Expected May 20. --> | Aktiverad som standard |

<!-- KFM: Confirm status of this feature:
| Planning | [Demand Driven Material Requirements Planning (DDMRP)](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/demand-driven-material-requirements-planning-ddmrp) | Coming soon | Feature management:<br>*(Preview) DDMRP for Planning Optimization* | -->

## <a name="feature-enhancements-included-in-this-release"></a>Funktionsförbättringar som ingår i den här versionen

Följande tabeller listar de funktionsförbättringar som ingår i denna version. Var och en av dessa förbättringar tillhandahåller en stegvis förbättring av en befintlig funktion. Eftersom de bara är förbättringar visas de inte i [utgivningsplanen](/dynamics365-release-plan/2022wave1/finance-operations/dynamics365-supply-chain-management/planned-features). För att säkerställa att dessa förbättringar inte står i konflikt med dina befintliga anpassningar eller inställningar stängs var och en av dem av som standard (om inget annat anges).

Om du vill slå på eller stänga av någon av dessa funktioner måste du göra detta i [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

| Modul | Funktionsnamn i funktionshantering | Mer information |
|---|---|---|
| Hantering av lager och lagerstyrning | Aktivera koncernintern behållning om du endast vill visa lagerbehållning som inte är noll | Med hjälp av den här funktionen kan du välja om artiklar med noll lagerkvantitet ska inkluderas i den koncerninterna lagerlistan. Du kan styra det här alternativet med hjälp av inställning **Visa inte artiklar med noll beställningskvantitet i den koncernintern beredskapslistan** som denna funktion lägger till sida **Parametrar för lager- och lagerhantering**. |
| Hantering av lager och lagerstyrning | (Indien) Ignorera plats för överföringsprisregler när ”Från lagerställekod” är inställt på ”Alla” | <p>Den här funktionen gäller endast för platser i Indien. Det underlättar inställningen av överföringspriser för artiklar i lageröverföringar.</p><p>Du ställer in överföringspriser genom att konfigurera varje artikel med överföringsprisersregler. Ett sätt att göra den här konfigurationen är att inkludera en regelrad där fältet **Från lagerställekod** är inställt på *Alla*. Inställningen visar att överföringspriset som definieras av raden ska gälla oavsett vilket lagerställe artikeln plockas från. När den här funktionen är aktiverad ignoreras inställningen fält **Från lagerställekod** anges till *Alla* ignorerar inställning **Plats**. Därför gäller regeln oavsett vilken plats som angetts på överföringsordern. Det här beteendet förväntades troligen eftersom platsen ligger under lagerstället i lagerställedimensionshierarkin.</p><p>Om den här funktionen inte används används bara regler av den här typen när platsen för överföringsordern exakt matchar platsen som ställts in för regeln. (Om en tom plats har angetts för regeln använder systemet regeln endast för överföringsorder som även har ett tomt värde för platsen.)</p> |
| Hantering av lager och lagerstyrning | Rensning av data i lagerbehållningsrapport | Den här funktionen ger ett sätt att rensa upp data som används för att skapa rapporter *Lagring av lagerbehållningsrapport*. |
| Produktionskontroll | Tilldela projektaktiviteter för serviceavtal och serviceorderrader | Med den här funktionen läggs ett fält med namnet **Projektaktivitet** till serviceavtal och serviceorderrader, så att du kan ställa in en projektaktivitet för dem. Funktionen hjälper till att förhindra spärrfel när du bokför projektjournaler för tjänstehantering som kräver att en projektaktivitet ställs in.  |
| Warehouse management | Manuell plockningstjänst för överföringsrad för admin eller liknande betrodda användare | Med den här funktionen kan administratörer plocka lagertransaktioner manuellt som hör till överföringsrader. Dessa rader inkluderar rader som redan har släppts till lagret. Administratörer bör endast välja detta i sällsynta fall, till exempel när systemet är i ett skadade tillstånd. |

## <a name="new-and-updated-documentation-resources"></a>Nya och uppdaterade dokumentationsresurser

Följande hjälpavsnitt har nyligen lagts till eller uppdaterats väsentligt. Dessa ämnen är inte nödvändigtvis relaterade till de nya funktioner som lagts till för denna version, enligt vad som beskrivs i de föregående avsnitten. De kan dock hjälpa dig att få ut mer av befintliga funktioner.

| Funktionsområde | Nya eller uppdaterade ämnen |
|---|---|
| Kostnadshantering | [Fast inleveranspris](../cost-management/fixed-receipt-price.md) |
| Kostnadshantering | [Vanliga frågor och svar om lagerkostnad](../cost-management/inventory-costing-faq.md) |
| Kostnadshantering | [Bokföringsprincip för att bokföra på debiteringskonto](../cost-management/post-to-charge-account-accounting-principle.md) |
| Lagerhantering | [Lagertransaktion – information](../inventory/inventory-transactions-details.md) |

## <a name="additional-resources"></a>Ytterligare resurser

### <a name="platform-updates-for-finance-and-operations-apps"></a>Plattformsuppdatering för Ekonomi och drift-appar

Microsoft Dynamics 365 Supply Chain Management 10.0.28 inkluderar plattformsuppdateringar. Mer information finns i [Plattformsuppdateringar för version 10.0.28 av appar för ekonomi och drift (juni 2022)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-28.md).<!-- KFM Confirm link -->

### <a name="bug-fixes"></a>Felkorrigeringar

Om du vill ha information om felkorrigeringar som ingår i varje uppdatering som ingår i 10.0.28 loggar du in på Lifecycle Services (LCS) och visar [KB-artikel](https://fix.lcs.dynamics.com/Issue/Details?bugId=694438).

### <a name="dynamics-365-and-industry-clouds-2022-release-wave-1-plan"></a>Dynamics 365 och branschmoln: Utgivningsvåg 1 plan för 2022

Har du frågor om nya och kommande funktioner i våra affärsappar eller plattformen?

Kolla in [Dynamics 365 och branschmoln: Utgivningsvåg 1 plan för 2022](/dynamics365-release-plan/2022wave1/). Vi har sammanställt all information som du kan tänkas behöva på ett enskilt dokument som du kan använda för din planering.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>Borttagna och inaktuella funktioner för Supply Chain Management

De [borttagna eller föråldrade funktionerna i Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) i ämnet beskriver funktioner som har schemalagts eller är planerade att tas bort eller inaktuellt för Supply Chain Management.

- En *borttagen* funktion är inte längre tillgänglig i produkten.
- En *borttagen* funktion är inte i aktiv utveckling och kan tas bort i en kommande uppdatering.

Innan någon funktion tas bort från produkten visas understrykningsmeddelandet i ämnet [borttagna eller inaktuella funktionerna i Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) 12 månader före avhämtningen.

För att bryta ändringar som endast påverkar kompileringen, men är binära kompatibla med begränsade lägen och produktionsmiljöer, blir utgångstiden mindre än 12 månader. Vanligtvis är dessa funktionsuppdateringar som måste göras till kompileraren.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
