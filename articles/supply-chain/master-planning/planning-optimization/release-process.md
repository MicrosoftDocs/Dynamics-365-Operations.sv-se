---
title: Frisläppningsprocess och frisläppningshistorik för Planeringsoptimering
description: Denna artikel innehåller information om frisläppningsprocessen och frisläppninghistoriken för Planeringsoptimering.
author: t-benebo
ms.date: 10/14/2022
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-07-28
ms.dyn365.ops.version: 10.0.31
ms.openlocfilehash: e2437214b4a2a850f121bb86272bf7dc3d313507
ms.sourcegitcommit: b3579ac62e1ea15664a114abcc2409cad76d4f19
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/14/2022
ms.locfileid: "9682571"
---
# <a name="planning-optimization-release-process-and-release-history"></a>Frisläppningsprocess och frisläppningshistorik för Planeringsoptimering

[!include [banner](../../includes/banner.md)]

Microsoft uppdaterar Planeringsoptimering varje månad. Utifrån affärsbehov frisläpper vi ibland ytterligare uppdateringar mellan de schemalagda versionerna.

Varje version publiceras i enskilda regioner där Planeringsoptimering är tillgänglig. Processen tar normalt tre dagar.

Medan Planeringsoptimering uppdateras, kan det gå långsammare än normalt att köra huvudplaneringen.

I de miljöer där Planeringsoptimering används får du automatiskt den senaste versionen. Det krävs ingen användaråtgärd: tjänsten uppdateras automatiskt. Men ändringar som inte är bakåt-kompatibla pushas dock aldrig automatiskt till miljöer. Som standard är alla ändringar som betraktas som inte-bakåtkompatibla inaktiverade och måste explicit aktiveras med [funktionshanteringen](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md). Därför visas inte dessa ändringar i miljön förrän du väljer att aktivera dem.

Eftersom meddelanden inte visas när Planeringsoptimering uppdateras i din miljö, kan du granska versionsinformationen i följande tabell och ta reda på när ändringar har släppts och vilka funktioner de innehåller. Tabellen visar de ändringar som släppts för Planeringsoptimering, om ändringarna är kopplade till en funktion från funktionshanteringen och datum för släppet.

| Ändringar | Information om funktionshantering | Frisläppningsdatum |
|---|---|---|
| <p>[Batchdispositionskoder](../../inventory/batch-disposition-codes.md)</p><p>Inkludera parametrar för lagerbehållning och lagertransaktion i huvudplaner</p><p>Allmän prestanda, kvalitet och förbättringar i effektivitet</p> | Ingen funktionshantering krävs | 10-14 oktober 2022 |
| <p>[Resursschemaläggning med ändlig kapacitet](finite-capacity.md)</p><p>Allmän prestanda, kvalitet och förbättringar i effektivitet</p> | Ingen funktionshantering krävs | 19-23 september 2022 |
| Allmän prestanda, kvalitet och förbättringar i effektivitet | Ingen funktionshantering krävs | 29 augusti – 3 september 2022 |
| <p>[Centraliserat kalenderunderhåll](../supply-chain-calendars-master-planning.md)</p><p>[Förslag för att optimera befintligt leverans](../action-messages.md)</p><p>[Stöd för underentreprenad](../../production-control/manage-subcontract-work-production.md)</p><p>Allmän prestanda, kvalitet och förbättringar i effektivitet</p> | Ingen funktionshantering krävs | 7-11 mars 2022 |
| Planeringsprioritet för tillverkningsorder | Tillgänglig med version 10.0.25 som en del av funktionen med namnet *Prioriterad MRP-stöd för Planeringsoptimering*. | November 12-18, 2021 |
| Allmän prestanda, kvalitet och förbättringar i effektivitet | Ingen funktionshantering krävs | November 12-18, 2021 |
| <p>Stöd för processtidsberäkningsformler, produktionsflöde med överlappning och produktionsdriftsnummer för behovstransaktioner</p><p>Förbättrade felmeddelanden för produktionsplanering tillhörande tidsgränsen, kapaciteten går inte att hitta, samt cykliskt flöde</p><p>Förbättrad överensstämmelse vid beräkning av inleverans- och utleveransdatum på både planerade order och bekräftade order</p><p>Allmän prestanda, kvalitet och förbättringar i effektivitet</p> | Funktionsnamn: *Planering med obegränsad kapacitet för Planeringsoptimering* | 22-27 oktober 2021 |
| <p>Stöd för att ta hänsyn till kassationsprocent vid beräkning av bearbetningstid</p><p>Stöd för driftsnummer och materialanvändning under tidsplanering</p> | Funktionsnamn: *Planering med obegränsad kapacitet för Planeringsoptimering* | 5-7 oktober 2021 |
| <p>Stöd för jobbtyper för produktionsflöde: **Kö före**, **Kö efter** och **Transporttid**</p><p>Allmän prestanda, kvalitet och förbättringar i effektivitet</p> | Funktionsnamn: *Planering med obegränsad kapacitet för Planeringsoptimering* | 25-30 september 2021 |
| <p>Stöd för masterplaner med **Planeringsmetod** ange *Grovplanering*</p><p>På sidan **Flödesgrupper** markerar du inställningarna för kryssrutorna **Aktivering**, **Arbetstid** och **Kapacitet** för rader med **Flödes-/jobbtyp** för *Inställningar* eller *Process* </p><p>Allmän prestanda, kvalitet och förbättringar i effektivitet</p> | <p>Grovplanering finns för funktionshantering från version 10.0.20</p><p>Funktionsnamn: *Planering med obegränsad kapacitet för Planeringsoptimering*</p> | 9-17 september 2021 |
| Allmän prestanda, kvalitet och förbättringar i effektivitet | Ingen funktionshantering krävs | 25–30 augusti 2021 |
| <p>Lade till fältet **Ledtid** i planerade order.</p><p>Allmän prestanda, kvalitet och förbättringar i effektivitet.</p> | Ingen funktionshantering krävs | 12–17 augusti 2021 |
| <p>Lade till resurstypskrav för planering med obegränsad kapacitet</p><p>Förbättrad resurs- och kalendereffektivitet för planering med obegränsad kapacitet</p><p>Mer information finns i [Tidsplanering med obegränsad kapacitet](infinite-capacity-planning.md)</p> | <p>Tillgänglig i funktionshantering från version 10.0.20</p><p>Funktionsnamn: *Planering med obegränsad kapacitet för Planeringsoptimering*</p> | 6–12 juli 2021 |
| Allmänna förbättringar av kvalitet | Ingen funktionshantering krävs | 6–12 juli 2021 |

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
