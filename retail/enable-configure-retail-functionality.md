---
title: "Initiera data i en ny miljö för Retail"
description: "Den här artikeln beskrivs de data som skapas under initieringsprocessen för Microsoft Dynamics 365 för verksamhet – Retail."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 49621
ms.assetid: 4dc762eb-190e-4485-8f55-b0cafc81bc37
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 137c675781cf75d9ce621a84c89224019c161362
ms.lasthandoff: 03/31/2017


---

# <a name="initialize-seed-data-in-a-new-retail-environment"></a>Initiera data i en ny miljö för Retail

Den här artikeln beskrivs de data som skapas under initieringsprocessen för Microsoft Dynamics 365 för verksamhet – Retail.

Efter återförsäljarlösning har spridits via Microsoft Dynamics Lifecycle Services (LCS), måste du initiera retail konfiguration för att skapa grundläggande konfigurationsuppgifter. **Viktigt!** Innan du initierar butikskonfiguration, kontrollera att du har angett ett språk och en postadress för varje juridisk enhet där du ställer upp butiker. Detta steg måste genomföras för varje juridisk enhet som du använder för butik. För att initiera retail konfiguration, följ dessa steg.

1.  Starta Dynamics 365 operationer klient.
2.  Klickar du på **butik och handel**&gt;**Headquarters installation**&gt;**parametrar**&gt;**Detaljhandelsparametrar**.
3.  Klicka på **Initiera**.

Initiering skapar följande standard konfigurationsdata:

-   Retail scheduler jobb och subjobs
-   Schema för butikskanal
-   butik scheman
-   Standard skärmlayouter, vilket inkluderar knappen raster, bilder och teman
-   Tidzonsinformation
-   Pointen-of-sale (POS)
-   Kassabehörigheter
-   Kanalrapporter
-   Attributmetadata
-   Enhet validering mallar
-   Bakgrundsjobbet ska rensa handel Data Exchange sessionshistorik

Dessutom loggar som rör kreditkortsindustrin (PCI) är aktiverat för Dynamics 365 för operationer databas. **Obs!** Det finns ett alternativ till separat konfigurering av butiksplanering. Det här alternativet låter dig återställa Retail scheduler konfigurationen till standardinställningarna. Efter initialiseringen är klar måste du konfigurera ytterligare retail data. Nedan följer några exempel:

-   Butiksparametrar
-   Parametrar för Butik schemaläggare
-   Butikskanaler
-   Register och enheter
-   Sortiment



