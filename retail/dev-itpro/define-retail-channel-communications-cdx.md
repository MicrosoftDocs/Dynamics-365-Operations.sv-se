---
title: Definiera butikskanalkommunikationer (Commerce Data Exchange)
description: "Det här avsnittet innehåller en översikt över handelsdatautbytet och dess komponenter. Det förklarar den del varje komponent spelar vid överföringen av data mellan Microsoft Dynamics 365 för operationer och återförsäljare."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 27021
ms.assetid: 179b1629-ac90-4cfb-b46a-5bda56c4f451
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 29938d962db42a521dd8dc03b8e45e0e34410e4d
ms.openlocfilehash: d3b36ec2a3f859215d93dd7ebf1f1ecfb2731c59
ms.lasthandoff: 03/31/2017


---

# <a name="define-retail-channel-communications-commerce-data-exchange"></a>Definiera butikskanalkommunikationer (Commerce Data Exchange)

Det här avsnittet innehåller en översikt över handelsdatautbytet och dess komponenter. Det förklarar den del varje komponent spelar vid överföringen av data mellan Microsoft Dynamics 365 för operationer och återförsäljare.

<a name="overview"></a>Översikt
--------

Commerce Data Exchange är ett system som överför data mellan Dynamics 365 för operationer och återförsäljare, till exempel onlinebutiker eller bankkontor och andra butiker. Den databas som lagrar data för en butikskanal skiljer sig från Dynamics 365 för operationer databas. Kanaldatabasen innehåller bara de data som krävs för butikstransaktioner. Huvuddata konfigurerats i Dynamics 365 för operationer och distribueras till kanaler. Transaktionsdata som skapas i systemet försäljning (PO) mittpunkt eller direkthjälpen lagra och överförs sedan till Dynamics 365 för operationer. Datadistributionen är asynkron. Med andra ord sker processen med insamlings- och förpackningsdata separat vid källan separat från processen för mottagning och tillämpning av data vid destinationen. För vissa situationer, till exempel pris- och lagersökningar, måste data måste hämtas i realtid. Commerce Data Exchange innehåller också en tjänst som gör kommunikation i realtid mellan Dynamics 365 för åtgärder och en kanal för dessa scenarier. 

[![Uppdatera-retail-bild](./media/updated-retail-graphic.png)](./media/updated-retail-graphic.png)  

## <a name="async-service"></a>Async Service
Spårning i Dynamics 365 för operationer databasen Microsoft SQL Server används för att bestämma dataförändringar som måste skickas till kanaler. Utifrån en distributionsplan Dynamics 365 för operationer paketerar dessa data som sparas till central lagring (Azure blob-lagring). En separat buntprocess använder Commerce Data Exchange: Async Client-bibliotek till att infoga detta datapaket i kanaldatabasen. 

[![Async Service](./media/async-300x239.png)](./media/async.png)

### <a name="retail-scheduler"></a>Butik schemaläggare

Jobb i schemaläggare är mekanismen för att distribuera data till och från platser. Jobb består av deljobb som anger vilka register och vilka registerfält som innehåller data att fördela. Dynamics 365 för operationer innehåller fördefinierade schemaläggarjobb och deljobb som uppfyller behoven hos de flesta organisationer replikeringen. Följande typer av fördefinierade jobb skapas:

-   **Hämta jobb** – hämta jobb skickar data som har ändrats från Dynamics 365 för operationer till kanal databaser. Ändringar av poster som spåras av SQL Server ändringsspårning.
-   **Överföra jobb (P-jobb)** – försäljningstransaktioner från en kanal till Dynamics 365 för operationer databasen pull-överföringar. P-jobb överför data successivt. När ett P-jobb körs kontrollerar Async Client-biblioteket replikeringsräknaren för poster som redan har tagits emot från en plats. En post överförs bara om dess replikeringsräknare är större än det största värdet som hittats. P-jobb uppdaterar inte data som har överförts tidigare.

Fördelningen schemat används för att köra dataöverföring, manuellt eller genom planering av ett batch-jobb i Dynamics 365 för operationer. En distributionstidsplan kan innehålla en eller flera kanaldatagrupper och ett eller flera schemaläggarjobb.

## <a name="realtime-service"></a>Service i realtid
Commerce Data Exchange: Real-time Service är en integrerad tjänst som ger kommunikation i realtid mellan Dynamics 365 för operationer och återförsäljare. Real-time Service kan enskilda POS datorer och onlinebutiker för att hämta vissa data från Dynamics 365 för operationer i realtid. Även om de flesta viktiga åtgärder kan utföras i databasen med lokala kanalen, kräver direkt åtkomst till data som lagras i Dynamics 365 för operationer i följande scenarier:

-   Utfärda och lösa in presentkort.
-   Lösa in förmånspoäng.
-   Utfärda och lösa in kreditfakturor.
-   Skapa och uppdatera kundposter.
-   Skapa, uppdatera och slutför försäljningsorder.
-   Ingående lager mot en inköpsorder eller överföringsorder.
-   Utföra lagerinventeringar.
-   Hämta försäljningstransaktioner mellan butiker och slutföra returtransaktioner.

[![Real-time Service](./media/rts.png)](./media/rts.png) 

En fördefinierad Real-time Service-profil skapas.


