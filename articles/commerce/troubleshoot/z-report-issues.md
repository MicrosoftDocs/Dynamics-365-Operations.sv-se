---
title: Problem med dataavstämning av en Z-rapport
description: I den här artikeln beskrivs problem som användare kan ha erfarenhet av dataavstämningen av en Z-rapport i Commerce headquarters. Här beskrivs också möjliga rotorsaker och lösningar som kan hjälpa till att förhindra framtida förekomster.
author: Shajain
ms.date: 12/06/2022
ms.topic: Troubleshooting
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: shajain
ms.search.validFrom: 2021-01-31
ms.openlocfilehash: 9803134c4c77233e565525e96fd82af293d4c829
ms.sourcegitcommit: 0c927fcb3afd34d870391f05b5393a4673d916e5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/08/2022
ms.locfileid: "9832147"
---
# <a name="issues-with-the-data-reconciliation-of-a-z-report"></a>Problem med dataavstämning av en Z-rapport

[!include [banner](../../includes/banner.md)]

Den här artikeln innehåller felsökningsvägledning som kan vara till hjälp om du stöter på problem med dataavstämningen av en Z-rapport i Microsoft Dynamics 365 Commerce headquarters. Det beskriver problem som användarna kan ha erfarenhet av dataavstämningen, möjliga rotorsaker och lösningar som kan hjälpa till att förhindra framtida förekomster.

## <a name="description"></a>beskrivning

- Det finns en skillnad mellan beloppen som visas i Z-rapporten och summorna som visas på det beräknade utdraget.
- Transaktionen i administration har fel antal radartiklar, eller så finns det en skillnad mellan radsumma och summa för transaktionen.
- Antalet transaktioner som visas i ett skift i huvudkontoret är mindre än antalet transaktioner i Z-rapporten.
- Bokföringsprocess misslyckades av någon av de föregående orsakerna.

### <a name="root-cause"></a>Rotorsaken

Den vanligaste grundorsaken till de tidigare beskrivna symptomen är genereringen av dubbla transaktions-ID:n i kanaldatabasen. Dubbletttransaktions-ID:n kan genereras av följande skäl:

- Den lokala databaslagringen av Modern Point of Sale (MPOS) är skadad.
- MPOS har vissa transaktioner i offlineläge och aktiveras igen med ett konto som inte har åtkomst till offlinedatabasen.
- Det finns ett problem med anpassning som är relaterat till genereringen av transaktions-ID:n.

## <a name="resolution"></a>Lösning

Vanligtvis använder Handel en nummerserie för att generera serienummer. Om det av någon anledning inte går att fastställa att en nummerserie använts, genereras ett dubblettransaktions-ID. 

Om du vill åtgärda problemet med en dubblettransaktions-ID skapar du en supportbiljett för att kontrollera om transaktionsdata kan fastställas. I vissa fall, till exempel när det inte finns någon dataförlust i administration, är ingen datakorrigering möjlig eller obligatorisk.

För att förhindra detta problem i framtiden måste du aktivera funktionen **Aktivera nytt transaktions-ID i syfte att undvika dubbletter av transaktions-ID:n** i administration. Den här funktionen introduceras i Commerce version 10.0.19. Det förhindrar att sekventiella transaktions-ID:n skapas genom att ett unikt transaktions-ID skapas för varje transaktion. Mer information om denna funktion finns i [Förhindra dubbletter av transaktions-ID:n](../channel-setup-retail.md#ensure-unique-transaction-ids).
