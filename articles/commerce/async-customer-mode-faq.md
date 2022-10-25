---
title: Vanliga frågor och svar om Skapningsläge asynkron kund
description: Denna artikel innehåller vanliga frågor och svar om det asynkrona läget för att skapa kunder i Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 10/18/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-12-17
ms.openlocfilehash: 64c895fb9f3e55f7680759fa72626be6660aa67c
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/18/2022
ms.locfileid: "9690213"
---
# <a name="asynchronous-customer-creation-mode-faq"></a>Vanliga frågor och svar om Skapningsläge asynkron kund

[!include [banner](includes/banner.md)]

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

1. Kör CDX P-jobbet i Commerce headquarters för att säkerställa att asynkron kunddata lagras i tabellerna **RETAILASYNCCUSTOMERV2**, **RETAILASYNCADDRESSV2**, **RETAILASYNCCUSTOMERCONTACT**, **RETAILASYNCCUSTOMERAFFILIATION** och **RETAILASYNCCUSTOMERATTRIBUTEV2**.
1. Kör batchjobbet **Synkronisera kunder och kanalbegäranden** i Commerce headquarters. Efter framgångsrik körning av batchjobbet kommer alla poster som framgångsrikt har bearbetats från de tidigare nämnda tabellerna att ha fältet **OnlineOperationCompleted** till **1**.

### <a name="how-do-i-know-which-customer-management-in-asynchronous-mode-operation-has-failed-and-how-do-i-make-changes-if-they-are-required"></a>Hur vet jag vilken kundhantering i asynkront lägesoperation som har misslyckats, och hur gör jag ändringar om de behövs?

För att se alla funktioner i asynkront läge och deras synkroniseringsstatus i Commerce headquarters gå till **Handel och detaljhandel \> Kunder \> Kundsynkroniseringsstatus**. Om du vill göra ändringar redigerar du en viss åtgärd, uppdaterar fälten, väljer **Spara** och **Synkroniserar** sedan ändringarna.

