---
title: Förhandsgranskning av Dynamics 365 Commerce 10.0.31 (2023 februari)
description: Denna artikel innehåller en beskrivning av nya eller ändrade funktioner i Microsoft Dynamics 365 Commerce 10.0.31.
author: josaw1
ms.date: 10/18/2022
ms.topic: article
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2022-10-01
ms.dyn365.ops.version: 10.0.31
ms.openlocfilehash: 05ccd9794ffeba6a09d6fec0a57ffad2b59707ad
ms.sourcegitcommit: 87e75aa6af2c3280316d7d73eafa14a52353a5e4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/21/2022
ms.locfileid: "9709866"
---
# <a name="preview-of-dynamics-365-commerce-10031-february-2023"></a>Förhandsgranskning av Dynamics 365 Commerce 10.0.31 (2023 februari)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Denna artikel anger nya eller ändrade funktioner i Microsoft Dynamics 365 Commerce förhandsversion version 10.0.31. Den här versionen har ett versionsnummer för 10.0.1406 på följande schema:

- **Förhandsversion:** oktober 2022
- **Allmän tillgänglighet för frisläppning (självuppdatering):** 2023 januari
- **Allmän tillgänglighet för frisläppning (automatisk uppdatering):** 2023 februari

## <a name="features-included-in-this-release"></a>Funktioner som ingår i den här versionen

Följande tabeller listar de funktioner som ingår i denna version. Vi kan komma att uppdatera denna artikel att inkludera funktioner somlades till i versionen efter det att denna artikel ursprungligen publicerades.

| Funktionsområde | Funktion | Mer information | Har aktiverats av |
|---|---|---|---|
| Felkoder | Commerce introducerade standardiserade felreferenser som ska inkluderas i onlinekanalutcheckningsfel som presenteras för onlineshoppare.| [Felkoder för utcheckningsmodul](../checkout-module-error-codes.md)  | På som standard |
| Betalningar | [Aktivera Apple Pay med Dynamics 365-betalningskoppling för Adyen](/dynamics365-release-plan/2022wave2/commerce/dynamics365-commerce/enable-apple-pay-dynamics-365-payment-connector-adyen)  | E-handelskunder kan använda Apple Pay på kundvagns. och kassasidor när du använder vilka enheter eller webbläsare som stöds. | Välj utvecklare |
| Betalningar  |  Commerce har lagt till möjligheten att begränsa hur användare samverkar med återkommande betalningstoken i användargränssnittet för Commerce headquarters. Betalningsformulär, till exempel sidan **Försäljningsorder för kundtjänst** visar inte längre en kunds tidigare använda återkommande betalningstoken för användning i en ny transaktion. Endast inmatning av bestämt "registrerat kort" på skärmen för Commerce **kundbetalningar**, eller med överenskommelse med en kund vid betalning genom en försäljningsorder, kommer att presenteras för kundtjänst eller Commerce headquarters-användare när en betalning för en ny transaktion behandlas. | [Begränsa användningen av betalningstoken](../dev-itpro/limit-token-usage.md)  |  Funktionshantering<p>*Begränsa användning av betalningstoken till ordersammanhang*  |
| Kassa | [Skapa inköpsorder från kassan](/dynamics365-release-plan/2022wave2/commerce/dynamics365-commerce/create-purchase-orders-pos)  |  Förbättrad inkommande lagerdrift i kassaappen (Point of Sale) för att tillåta användare att skapa, redigera och bekräfta inköpsorderförfrågningar. |  Funktionshantering<p>*Möjlighet att skapa inköpsorderbegäran i kassa*   |



## <a name="additional-resources"></a>Ytterligare resurser

### <a name="platform-updates-for-finance-and-operations-apps"></a>Plattformsuppdatering för Ekonomi och drift-appar

Microsoft Dynamics 365 Commerce 10.0.31 inkluderar plattformsuppdateringar. Mer information finns i [Plattformsuppdateringar för version 10.0.31 av appar för ekonomi och drift (februari 2023)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-31.md). 
  

### <a name="bug-fixes"></a>Felkorrigeringar

Om du vill ha information om felkorrigeringar som ingår i varje uppdatering som ingår i version 10.0.31 loggar du in på Microsoft Dynamics Lifecycle Services och läser [KB-artikel](https://fix.lcs.dynamics.com/Issue/Details?bugId=758525).

### <a name="dynamics-365-and-industry-clouds-2022-release-wave-2-plan"></a>Dynamics 365 och branschmoln: Utgivningsvåg 2 plan för 2022

Har du frågor om nya och kommande funktioner i våra affärsappar eller plattformen?

Kolla in [Dynamics 365 och branschmoln: Utgivningsvåg 2 plan för 2022](/dynamics365-release-plan/2022wave2/). Vi har sammanställt all information som du kan tänkas behöva på ett enskilt dokument som du kan använda för din planering.

### <a name="removed-and-deprecated-commerce-features"></a>Borttagna och inaktuella Commerce-funktioner

[Funktionerna som tas bort eller avskrivs i Dynamics 365 Commerce](removed-deprecated-features-commerce.md) artikeln beskriver funktioner som har tagits bort eller avskrivts för Handel.

- En *borttagen* funktion är inte längre tillgänglig i produkten.
- En *borttagen* funktion är inte i aktiv utveckling och kan tas bort i en kommande uppdatering.

Innan någon funktion tas bort från produkten kommer meddelandet om inaktualitet att meddelas i artikeln [Borttagna eller inaktuella funktioner i Dynamics 365 Commerce](removed-deprecated-features-commerce.md) 12 månader före borttagning.


För att bryta ändringar som endast påverkar kompileringen, men är binära kompatibla med begränsade lägen och produktionsmiljöer, blir utgångstiden mindre än 12 månader. Vanligtvis är dessa funktionsuppdateringar som måste göras till kompileraren.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
