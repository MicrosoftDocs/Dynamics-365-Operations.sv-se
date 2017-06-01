---
title: Definiera butikskanalkommunikationer (Commerce Data Exchange)
description: "Det här avsnittet innehåller en översikt över handelsdatautbytet och dess komponenter. Den beskriver de olika komponenternas betydelse vid överföringen av data mellan Microsoft Dynamics 365 for Operations och butikskanaler."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 27021
ms.assetid: 179b1629-ac90-4cfb-b46a-5bda56c4f451
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 6b1f91f863c8da35362ebb3036e76aa10d95ba65
ms.openlocfilehash: ba1bb54a29250a2bb59622ee4391b64ac455af33
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017


---

# <a name="define-retail-channel-communications-commerce-data-exchange"></a>Definiera butikskanalkommunikationer (Commerce Data Exchange)

[!include[banner](../includes/banner.md)]


Det här avsnittet innehåller en översikt över handelsdatautbytet och dess komponenter. Den beskriver de olika komponenternas betydelse vid överföringen av data mellan Microsoft Dynamics 365 for Operations och butikskanaler.

<a name="overview"></a>Översikt
--------

Commerce Data Exchange är ett system som överför data mellan Dynamics 365 for Operations och detaljhandelskanaler, till exempel onlinebutiker och fysiska butiker. Databasen som lagrar data för en butikskanal är separat från Dynamics 365 for Operations-databasen. Kanaldatabasen innehåller bara de data som krävs för butikstransaktioner. Huvuddata konfigureras i Dynamics 365 for Operations och fördelas till kanaler. Transaktionsdata skapas i kassasystemet (POS) eller i onlinebutiken, och överförs sedan till Dynamics 365 for Operations. Datadistributionen är asynkron. Med andra ord sker processen med insamlings- och förpackningsdata separat vid källan separat från processen för mottagning och tillämpning av data vid destinationen. För vissa situationer, till exempel pris- och lagersökningar, måste data måste hämtas i realtid. Till stöd av dessa scenarier innehåller Commerce Data Exchange även en tjänst som aktiverar realtidskommunikation mellan Dynamics 365 for Operations och en kanal. 

[![uppdatera-butiksbild](./media/updated-retail-graphic.png)](./media/updated-retail-graphic.png)  

## <a name="async-service"></a>Async Service
Microsoft SQL Server-ändringsspårning på Dynamics 365 for Operations-databasen används för att bestämma de dataändringar som måste skickas till kanaler. Baserat på en distributionstidsplan förpackar Dynamics 365 for Operations dessa data och sparar dem i central lagring (Azure Blob-lagring). En separat buntprocess använder Commerce Data Exchange: Async Client-bibliotek till att infoga detta datapaket i kanaldatabasen. 

[![Async Service](./media/async-300x239.png)](./media/async.png)

### <a name="retail-scheduler"></a>Butik schemaläggare

Jobb i schemaläggare är mekanismen för att distribuera data till och från platser. Jobb består av deljobb som anger vilka register och vilka registerfält som innehåller data att fördela. Dynamics 365 for Operations omfattar fördefinierade schemaläggarjobb och deljobb som uppfyller replikationskraven för de flesta organisationer. Följande typer av fördefinierade jobb skapas:

-   **Hämtningsjobb** – Hämtningsjobb skickar data som har ändrats från Dynamics 365 for Operations till kanaldatabaser. Ändringar av poster som spåras av SQL Server ändringsspårning.
-   **Överföringsjobb (P-jobb)** – Överföringsjobb drar försäljningstransaktioner från en kanal till Dynamics 365 for Operations-databasen. P-jobb överför data successivt. När ett P-jobb körs kontrollerar Async Client-biblioteket replikeringsräknaren för poster som redan har tagits emot från en plats. En post överförs bara om dess replikeringsräknare är större än det största värdet som hittats. P-jobb uppdaterar inte data som har överförts tidigare.

Distributionstidsplanen används för att köra dataöverföringen, antingen manuellt eller genom att planera ett batchtjobb i Dynamics 365 for Operations. En distributionstidsplan kan innehålla en eller flera kanaldatagrupper och ett eller flera schemaläggarjobb.

## <a name="realtime-service"></a>Realtidstjänst
Commerce Data Exchange: Real-time Service är en integrerad tjänst som ger synkroniserad kommunikation i realtid mellan Dynamics 365 for Operations och butikskanalerna. Real-time Service aktiverar enskilda kassadatorer och onlinebutiker för att hämta specifika data från Dynamics 365 for Operations i realtid. Även om de flesta viktiga åtgärder kan utföras i den lokala kanaldatabasen, kräver följande scenarier direkt åtkomst till data som lagras i Dynamics 365 for Operations:

-   Utfärda och lösa in presentkort.
-   Lösa in förmånspoäng.
-   Utfärda och lösa in kreditfakturor.
-   Skapa och uppdatera kundposter.
-   Skapa, uppdatera och slutför försäljningsorder.
-   Ingående lager mot en inköpsorder eller överföringsorder.
-   Utföra lagerinventeringar.
-   Hämta försäljningstransaktioner mellan butiker och slutföra returtransaktioner.

[![Realtidstjänst](./media/rts.png)](./media/rts.png) 

En fördefinierad realtidstjänsteprofil skapas.




