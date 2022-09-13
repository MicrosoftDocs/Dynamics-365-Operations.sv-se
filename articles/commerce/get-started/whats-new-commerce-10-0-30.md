---
title: Förhandsversion av Dynamics 365 Commerce 10.0.30 (november 2022)
description: Denna artikel innehåller en beskrivning av nya eller ändrade funktioner i Microsoft Dynamics 365 Commerce 10.0.30.
author: josaw1
ms.date: 08/31/2022
ms.topic: article
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2022-09-01
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: 0149c9671e8baeb26965b4f136ed91d09e2d039b
ms.sourcegitcommit: 1d5cebea3e05b6d758cd01225ae7f566e05698d2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/02/2022
ms.locfileid: "9405573"
---
# <a name="preview-of-dynamics-365-commerce-10030-november-2022"></a>Förhandsversion av Dynamics 365 Commerce 10.0.30 (november 2022)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Denna artikel anger nya eller ändrade funktioner i Microsoft Dynamics 365 Commerce förhandsversion version 10.0.30. Den här versionen har ett versionsnummer för 10.0.1362 på följande schema:

- **Förhandsversion:** september 2022
- **Allmän tillgänglighet för versionen (självuppdatering):** oktober 2022
- **Allmän tillgänglighet för version (automatisk uppdatering):** november 2022

## <a name="features-included-in-this-release"></a>Funktioner som ingår i den här versionen

Följande tabeller listar de funktioner som ingår i denna version. Vi kan komma att uppdatera denna artikel att inkludera funktioner somlades till i versionen efter det att denna artikel ursprungligen publicerades.

| Funktionsområde | Funktion | Mer information | Har aktiverats av |
|---------|------------------|----------------|--------------| 
| Kundsupport   | Chatta på en e-handelsplats med hjälp av en Power Virtual Agents roboten. | Med denna funktion kan användarna på e-handelsplatsen välja att använda en Power Virtual Agents chattroboten för supportförfrågningar. | Aktiveras av administratörer/beslutsfattare för slutanvändare |
| Insikter  |  Streama kassa (POS) Operational Insights händelser till din Application Insights konto. | [Komma åt loggar i Application Insights](../dev-itpro/retail-component-events-diagnostics-troubleshooting.md#enable-diagnostic-events-in-application-insights)   |  Välj IT-proffs/utvecklare   |
|  Betalningar  | PayPal-order ger stöd efter 29-dagars auktoriseringsperiod. | Den maximala auktoriseringsperioden för PayPal är 29 dagar, var därefter måste en ny auktorisering och ett nytt order-ID genereras. Alternativt erbjuder PayPal ett alternativ där en order en PayPal-order kan refereras som en allmän order, vilket innebär att flera auktoriseringar och fångar in mot samma order-ID i stället för att generera en ny auktorisering och order-ID på 29 dagar. | När du konfigurerar PayPal-betalningsanslutningsprogram i Commerce headquarters har fältet **OrderIntent** lagts till och kan ha två värden:<p><p>- **Auktorisera** – Denna konfiguration är standard (om fältet lämnas tomt kommer **Auktorisera** att fungera som standard). Konfigurera **OrderIntent** till **Auktorisera** korrelerar till PayPal **processing_instruction** värde **NO_INSTRUCTION**. Ordern godkänns tillsammans med PayPal och auktoriseringen kan inte ändras när det här värdet används.<p>- **Spara** – När värdet **OrderIntent** är inställt på **Spara**, detta korrelerar med PayPal **processing_instruction** värdet **ORDER_SAVED_EXPLICITLY**. Orderreferenser sparas i PayPal-tjänsten när det här värdet används.  |
| Logga in i kassa  | [Aktivera självbetjäning för diagnoskapaciteter för kassainloggning](/dynamics365-release-plan/2022wave2/commerce/dynamics365-commerce/enable-self-serve-diagnosis-capabilities-pos-sign-in)  |  Den här funktionen tillhandahåller självbetjäningsdiagnosfunktioner i kassa (POS) och Commerce headquarters för att hjälpa butiksanställda och chefer att snabbt identifiera och åtgärda grundorsakerna till kassainloggningsproblem.<p><p>- De felmeddelanden som visas på kassainloggningsskärmen har förbättrats för att ge rotorsaksinformation som kan hjälpa medarbetare som använder kassa att förstå vad som gick fel så att de kan vidta nödvändiga åtgärder för att lösa problemet.<p>- En funktion för **testinloggning** finns tillgänglig på sidan **Arbetare** i Commerce headquarters, så att butikschefer som ställer in kassaenheter kan simulera kassainloggning. Om ett inloggningsfel uppstår tillhandahåller den här funktionen åtgärdsbara felsökningsguider så att chefer kan kontrollera relevanta konfigurationer, korrigera problem och validera korrigeringarna.  | På som standard |


## <a name="additional-resources"></a>Ytterligare resurser

### <a name="platform-updates-for-finance-and-operations-apps"></a>Plattformsuppdatering för Ekonomi och drift-appar

Dynamics 365 Finance 10.0.30 innehåller plattformsuppdateringar. Mer information finns i [Plattformsuppdateringar för version 10.0.30 av appar för ekonomi och drift](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-30.md).

### <a name="bug-fixes"></a>Felkorrigeringar

Om du vill ha information om felkorrigeringar som ingår i varje uppdatering som ingår i version 10.0.30 loggar du in på Lifecycle Services (LCS) och visar [KB-artikel](https://fix.lcs.dynamics.com/Issue/Details?bugId=745468). 

### <a name="dynamics-365-and-industry-clouds-2022-release-wave-2-plan"></a>Dynamics 365 och branschmoln: Utgivningsvåg 2 plan för 2022

Har du frågor om nya och kommande funktioner i våra affärsappar eller plattformen?

Kolla in [Dynamics 365 och branschmoln: Utgivningsvåg 2 plan för 2022](/dynamics365-release-plan/2022wave2/). Vi har sammanställt all information som du kan tänkas behöva på ett enskilt dokument som du kan använda för din planering.

### <a name="removed-and-deprecated-features"></a>Borttagna och inaktuella funktioner

[Funktionerna som tas bort eller avskrivs i Dynamics 365 Commerce](removed-deprecated-features-commerce.md) artikeln beskriver funktioner som har tagits bort eller avskrivts för Handel.

- En *borttagen* funktion är inte längre tillgänglig i produkten.
- En *borttagen* funktion är inte i aktiv utveckling och kan tas bort i en kommande uppdatering.

Innan någon funktion tas bort från produkten kommer meddelandet om inaktualitet att meddelas i artikeln [Borttagna eller inaktuella funktioner i Dynamics 365 Commerce](removed-deprecated-features-commerce.md) 12 månader före borttagning.

För att bryta ändringar som endast påverkar kompileringen, men är binära kompatibla med begränsade lägen och produktionsmiljöer, blir utgångstiden mindre än 12 månader. Vanligtvis är dessa funktionsuppdateringar som måste göras till kompileraren.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
