---
title: Initiera startdata i nya detaljhandelsmiljöer
description: Den här artikeln beskriver de data som har skapats som en del av initieringsprocessen för Dynamics 365 Retail.
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
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
ms.openlocfilehash: 49b21d81437ebd7cc55076444ee71ae1143bfac0
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/24/2019
ms.locfileid: "2025526"
---
# <a name="initialize-seed-data-in-new-retail-environments"></a>Initiera startdata i nya Retail-miljöer

[!include [banner](includes/banner.md)]

Den här artikeln beskriver de data som har skapats som en del av initieringsprocessen för Dynamics 365 Retail.

Efter återförsäljarlösning har spridits via Microsoft Dynamics Lifecycle Services (LCS), måste du initiera butikskonfiguration för att skapa grundläggande konfigurationsuppgifter.

> [!IMPORTANT]
> Innan du initierar butikskonfiguration, kontrollera att du har angett ett språk och en postadress för varje juridisk enhet där du ställer upp butiker. Detta steg måste genomföras för varje juridisk enhet som du använder för butik.

För att initiera retail konfiguration, följ dessa steg.

1. Starta Retail-klienten.
2. Klicka på **Butiker** &gt; **Inställningar för huvudkontor** &gt; **Parametrar** &gt; **Detaljhandelsparametrar**.
3. Klicka på **Initiera**.

Initiering skapar följande standard konfigurationsdata:

- Retail scheduler jobb och subjobs
- Schema för butikskanal
- butik scheman
- Standard skärmlayouter, vilket inkluderar knappen raster, bilder och teman
- Tidzonsinformation
- Pointen-of-sale (POS)
- Kassabehörigheter
- Kanalrapporter
- Attributmetadata
- Enhet validering mallar
- Batch-jobb för att ta bort Commerce Data Exchange-sessionshistorik

Dessutom loggar som är relaterad till PCI (Payment Card Industry) är aktiverad för Retail-databasen.

> [!NOTE]
> Det finns ett alternativ till separat konfigurering av butiksplanering. Det här alternativet låter dig återställa Retail scheduler konfigurationen till standardinställningarna.

Efter initialiseringen är klar måste du konfigurera ytterligare retail data. Nedan följer några exempel:

- Butiksparametrar
- Parametrar för Butik schemaläggare
- Butikskanaler
- Register och enheter
- Sortiment
