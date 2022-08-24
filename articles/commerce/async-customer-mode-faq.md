---
title: Vanliga frågor och svar om Skapningsläge asynkron kund
description: Denna artikel innehåller vanliga frågor och svar om det asynkrona läget för att skapa kunder i Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 08/04/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-12-17
ms.openlocfilehash: 35c999695ed33c4fc9731a5b8dd4d679cf55fa44
ms.sourcegitcommit: e0905a3af85d8cdc24a22e0c041cb3a391c036cb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/06/2022
ms.locfileid: "9229880"
---
# <a name="asynchronous-customer-creation-mode-faq"></a>Vanliga frågor och svar om Skapningsläge asynkron kund

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

denna artikel innehåller vanliga frågor och svar om det asynkrona läget för att skapa kunder i Microsoft Dynamics 365 Commerce.

### <a name="why-cant-i-enable-the-enable-editing-customers-in-asynchronous-mode-feature"></a>Varför kan jag inte aktivera funktionen "Aktivera redigering av kunder i asynkront läge"?

Innan du aktiverar funktionen **Aktivera redigering av kunder i asynkront läge** måste du aktivera följande funktioner:

- Prestandaförbättringar för kundorder och kundtransaktioner
- Aktivera utökat skapa asynkron kund
- Aktivera att skapa kundadresser asynkront

### <a name="why-do-i-still-see-real-time-service-calls-made-to-commerce-headquarters-after-the-enable-editing-customers-in-asynchronous-mode-feature-is-enabled"></a>Varför visas fortfarande servicesamtal i realtid som har gjorts till Commerce Headquarters efter att funktionen "Aktivera redigering av kunder i asynkront läge" har aktiverats?

Det här problemet uppstår när Commerce Data Exchange (CDX)-jobb inte har körts för att säkerställa att funktionsläge och andra kanalmetadata synkroniseras med kanalen. Innan du gör ett nytt försök till scenariot måste följande CDX-jobb köras i Commerce headquarters:

- 1110 (Global konfiguration)
- 1010 (Kunder)
- 1070 (Kanalkonfiguration)

Data som cachelagras i CSU (Commerce Scale Unit) kanske inte visas direkt i Commerce headquarters efter att CDX-jobben har körts.

### <a name="why-doesnt-commerce-headquarters-show-customer-creation-or-updates-from-the-point-of-sale-pos-or-e-commerce-channel"></a>Varför visar inte Commerce headquarters kundskapa eller uppdateringar från kassan (POS) eller e-handelskanal?

Se till att följande åtgärder har utförts i den ordning som de visas här.

1. Kör CDX P-jobbet i Commerce headquarters för att säkerställa att kunddata i tabellerna **RETAILASYNCCUSTOMERV2**, **RETAILASYNCADDRESSV2**, **RETAILASYNCCUSTOMERCONTACT**, **RETAILASYNCCUSTOMERAFFILIATION** och **RETAILASYNCCUSTOMERATTRIBUTEV2** är tillgängliga i Commerce headquarters.
1. Kör batchjobbet **Synkronisera kunder och kanalbegäranden** i Commerce headquarters. Efter framgångsrik körning av batchjobbet kommer alla poster som framgångsrikt har bearbetats från de tidigare nämnda tabellerna att ha fältet **OnlineOperationCompleted** till **1**.
