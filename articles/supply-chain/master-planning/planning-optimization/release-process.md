---
title: Frisläppningsprocess och frisläppningshistorik för Planeringsoptimering
description: Avsnittet innehåller information om frisläppningsprocessen och frisläppninghistoriken för Planeringsoptimering.
author: ChristianRytt
ms.date: 09/21/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-07-28
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: b2e0145c28b40f4fbfb54ad7e7ed32fbc130c569
ms.sourcegitcommit: 8afd0cdb39ec443fb7631c39401967cce0fac34e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/01/2021
ms.locfileid: "7727442"
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
| <p>Lade till stöd för processtidsberäkningsformler, produktionsflöde med överlappning och produktionsdriftsnummer för behovstransaktioner.</p><p>Förbättrade felmeddelanden för produktionsplanering tillhörande tidsgränsen, kapaciteten går inte att hitta, samt cykliskt flöde.</p><p>Förbättrad överensstämmelse vid beräkning av inleverans- och utleveransdatum på både planerade order och bekräftade order.</p><p>Allmän prestanda, kvalitet och förbättringar i effektivitet. | Funktionsnamn: *Planering med obegränsad kapacitet för Planeringsoptimering* | 22-27 oktober 2021 |
| <p>Lade till stöd för att ta hänsyn till kassationsprocent vid beräkning av bearbetningstid.</p><p>Lade till stöd för driftsnummer och materialanvändning under tidsplanering. | Funktionsnamn: *Planering med obegränsad kapacitet för Planeringsoptimering* | 5-7 oktober 2021 |
| <p>Lade till stöd för jobbtyper för produktionsflöde: **Kö före**, **Kö efter** och **Transporttid**.</p><p>Allmän prestanda, kvalitet och förbättringar i effektivitet. | Funktionsnamn: *Planering med obegränsad kapacitet för Planeringsoptimering* | 25-30 september 2021 |
| <p>Lagt till stöd för masterplaner med **Planeringsmetod** ange *Grovplanering*.</p><p>På sidan **Flödesgrupper** markerar du inställningarna för kryssrutorna **Aktivering**, **Arbetstid** och **Kapacitet** för rader med **Flödes-/jobbtyp** för *Inställningar* eller *Process*. </p><p>Allmän prestanda, kvalitet och förbättringar i effektivitet. | <p>Grovplanering finns för funktionshantering från version 10.0.20.</p><p>Funktionsnamn: *Planering med obegränsad kapacitet för Planeringsoptimering*</p>  | 9-17 september 2021 |
| Allmän prestanda, kvalitet och förbättringar i effektivitet. | Ingen funktionshantering krävs. | 25–30 augusti 2021 |
| <p>Lade till fältet **Ledtid** i planerade order.</p><p>Allmän prestanda, kvalitet och förbättringar i effektivitet.</p> | Ingen funktionshantering krävs. | 12–17 augusti 2021 |
| <p>Lade till resurstypskrav för planering med obegränsad kapacitet.</p><p>Förbättrad resurs- och kalendereffektivitet för planering med obegränsad kapacitet.</p><p>Mer information finns i [Tidsplanering med obegränsad kapacite](infinite-capacity-planning.md). | <p>Tillgänglig i funktionshantering från version 10.0.20.</p><p>Funktionsnamn: *Planering med obegränsad kapacitet för Planeringsoptimering*</p> | 6–12 juli 2021 |
| Allmänna kvalitetsförbättringar. | Ingen funktionshantering krävs. | 6–12 juli 2021 |

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]