---
title: Skapningsläge asynkron kund
description: Denna artikel beskriver det asynkrona läget för att skapa kunder i Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 12/10/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-12-17
ms.openlocfilehash: 4ca63fe06a804035e976a3432454078c1cca0020
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8880150"
---
# <a name="asynchronous-customer-creation-mode"></a>Skapningsläge asynkron kund

[!include [banner](includes/banner.md)]

Denna artikel beskriver det asynkrona läget för att skapa kunder i Microsoft Dynamics 365 Commerce.

I Commerce finns det två sätt att skapa kunder: Synkron (eller Synk) och Asynkron (eller Asynk). Kunder skapas som standard synkront. Med andra ord skapas de i Commerce headquarters i realtid. Synkroniseringsläget för kunder är fördelaktigt eftersom nya kunder kan sökas omedelbart över kanaler. Den har emellertid även ett problem. Eftersom det genererar [Commerce Data Exchange: realtidstjänst](dev-itpro/define-retail-channel-communications-cdx.md#realtime-service) anropar till Commerce headquarters kan prestanda påverkas om många samtidiga kundsamtal görs.

Om alternativet **Skapa kund i asynkront läge** anges till **Ja** i butikens funktionsprofil (**Retail och Commerce \> Kanalinställning \> Inställning av online-butik \> Funktionsprofiler**), realtidssamtal används inte för att skapa kundposter i kanaldatabasen. Asynkront kundgenereringsläge påverkar inte prestandan i Commerce headquarters. En tillfällig, global unik identifierare (GUID) tilldelas varje ny asynkron kundpost och används som kundkonto-ID. Denna GUID inte visas för kassaanvändare. I stället visas **väntande synkronisering** som kundkonto-ID.

> [!IMPORTANT]
> När kassan är offline växlar systemet automatiskt till läget för asynkron kundgenerering, även om läget för asynkron kundgenerering är inaktiverat. Oavsett om du väljer synkron eller asynkron kundgenerering måste Commerce headquarters-administratörer därför skapa och schemalägga ett återkommande batchjobb för **P-jobbet**, jobbet **Synkronisera kunder och affärspartner från asynkront läge** (kallades tidigare jobbet **Synkronisera kunder och affärspartner från asynkront läge**) och **1010**-jobbet, så att alla asynkrona kunder konverteras till synkrona kunder i Commerce headquarters.

## <a name="async-customer-limitations"></a>Asynkrona kundbegränsningar

Asynkrona kundfunktionen har för närvarande följande begränsningar:

- Asynkrona kundposter kan inte redigeras om inte kunden har skapats i Commerce headquarters och det nya kundkonto-ID:t har synkroniserats tillbaka till kanalen.
- Förmånskort kan inte utfärdas till asynkrona kunder såvida inte det nya kundkonto-ID:t har synkroniserats tillbaka till kanalen.

## <a name="async-customer-enhancements"></a>Asynkrona kundbegränsningar

Från och med versionen av Commerce 10.0.24, kan du aktivera funktionen **Aktivera förbättrad asynkronisering av skapa kunder** i arbetsytan **Funktionshantering**. Den här funktionen överlappar skillnaden mellan asynkron och synkronisera lägen för kundskapande i kassa och näthandel på följande sätt:

- Anknytningar kan inte associeras med asynkrona kunder.
- Titlar kan läggas till i asynkrona kunder.
- Sekundära e-postadresser och telefonnummer kan inte fångas in för asynkrona kunder.

Från och med versionen av Commerce 10.0.22, kan du aktivera funktionen **Aktivera asynkron generering för kundadresser** i arbetsytan **Funktionshantering**. Med denna funktion kan nya kundadresser sparas asynkront för både synkronisera kunder och async-kunder.

När du har aktiverat de tidigare nämnda funktionerna måste du schemalägga ett återkommande batchjobb för **P-jobb**, jobb **Synkronisera kunder och affärspartner från det asynkrona läget** och jobbet **1010** så att alla asynkroniserade kunder konverteras till synkroniseringskunder i Commerce headquarters.

### <a name="customer-creation-in-pos-offline-mode"></a>Kundskapa i kassa offlineläge

Som nämndes tidigare, när kassan är offline växlar systemet automatiskt till läget för asynkron kundgenerering, även om läget för asynkron kundgenerering är inaktiverat. Därför måste kommersiella administratörer för Commerce headquarters skapa och schemalägga ett återkommande batchjobb för **P-jobbet**, jobbet **Synkronisera kunder och affärspartners från asynkront läge** och jobbet **1010** så att eventuella asynkrona kunder konverteras till synkrona kunder i Commerce headquarters.

> [!NOTE]
> Om alternativet **Filtrera delade kunddatatabeller** anger **Ja** på sidan **Commerce kanalschema** (**Retail och Commerce \> Administrationsinställning \> Commerce schemaläggare \> Kanaldatabasgrupp**), kundposter skapas inte i kassa offline-läge. Mer information finns i [Offline uteslutande av data](dev-itpro/implementation-considerations-cdx.md#offline-data-exclusion).

## <a name="additional-resources"></a>Ytterligare resurser

[Kundhantering i butiker](customer-mgmt-stores.md)

[Konvertera asynkrona kunder till synkrona kunder](convert-async-to-sync.md)

[Kundattribut](dev-itpro/customer-attributes.md)

[Offline uteslutande av data](dev-itpro/implementation-considerations-cdx.md#offline-data-exclusion)
