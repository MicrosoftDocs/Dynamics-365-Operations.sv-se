---
title: "Initiera startdata i en ny detaljhandelsmiljö"
description: "Den här artikeln beskriver de data som skapas under initieringsprocessen för Microsoft Dynamics 365 for Retail."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 49621
ms.assetid: 4dc762eb-190e-4485-8f55-b0cafc81bc37
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 7388324fe8a9abc8fc3d723b7c8df2c73d76a2ae
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="initialize-seed-data-in-a-new-retail-environment"></a>Initiera startdata i en ny detaljhandelsmiljö

[!include [banner](includes/banner.md)]

Den här artikeln beskriver de data som skapas under initieringsprocessen för Microsoft Dynamics 365 for Retail.

Efter återförsäljarlösning har spridits via Microsoft Dynamics Lifecycle Services (LCS), måste du initiera retail konfiguration för att skapa grundläggande konfigurationsuppgifter. **Viktigt!** Innan du initierar butikskonfiguration, kontrollera att du har angett ett språk och en postadress för varje juridisk enhet där du ställer upp butiker. Detta steg måste genomföras för varje juridisk enhet som du använder för butik. För att initiera retail konfiguration, följ dessa steg.

1.  Starta Dynamics 365 for Retail-klienten.
2.  Klicka på **Butiker** &gt; **Inställningar för huvudkontor** &gt; **Parametrar** &gt; **Detaljhandelsparametrar**.
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

Dessutom aktiveras loggar som är relaterade till PCI (Payment Card Industry; betalkortsbranschen) för Dynamics 365 for Retail-databasen. **Obs!** Det finns ett alternativ till separat konfigurering av butiksplanering. Det här alternativet låter dig återställa Retail scheduler konfigurationen till standardinställningarna. Efter initialiseringen är klar måste du konfigurera ytterligare retail data. Nedan följer några exempel:

-   Butiksparametrar
-   Parametrar för Butik schemaläggare
-   Butikskanaler
-   Register och enheter
-   Sortiment





