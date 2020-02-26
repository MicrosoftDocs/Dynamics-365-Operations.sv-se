---
title: Initiera startdata i nya detaljhandelsmiljöer
description: Den här artikeln beskriver de data som har skapats som en del av initieringsprocessen för Dynamics 365 Commerce.
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
ms.openlocfilehash: e2833c32d557ec3d2dc80808222d1d47860ce6ea
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/01/2020
ms.locfileid: "3024108"
---
# <a name="initialize-seed-data-in-new-retail-environments"></a>Initiera startdata i nya Retail-miljöer

[!include [banner](includes/banner.md)]

Den här artikeln beskriver de data som har skapats som en del av initieringsprocessen för Dynamics 365 Commerce.

Efter lösning har spridits via Microsoft Dynamics Lifecycle Services (LCS), måste du initiera handelskonfiguration för att skapa grundläggande konfigurationsuppgifter.

> [!IMPORTANT]
> Innan du initierar handelskonfiguration, kontrollera att du har angett ett språk och en postadress för varje juridisk enhet där du ställer upp butiker. Detta steg måste genomföras för varje juridisk enhet som du använder för handel.

För att initiera konfiguration, följ dessa steg.

1. Starta Handelsklienten.
2. Klicka på **Butik och handel** &gt; **Administrationsinställning** &gt; **Parametrar** &gt; **Handelparametrar**.
3. Klicka på **Initiera**.

Initiering skapar följande standard konfigurationsdata:

- Handelsschemaläggare jobb och deljobb
- Handelskanalschema
- Distributionsplaner för handel
- Standard skärmlayouter, vilket inkluderar knappen raster, bilder och teman
- Tidzonsinformation
- Pointen-of-sale (POS)
- Kassabehörigheter
- Kanalrapporter
- Attributmetadata
- Enhet validering mallar
- Batch-jobb för att ta bort Commerce Data Exchange-sessionshistorik

Dessutom loggar som är relaterad till PCI (Payment Card Industry) är aktiverad för handelsdatabasen.

> [!NOTE]
> Det finns ett alternativ till separat konfigurering av handelsschemaläggare. Det här alternativet låter dig återställa konfigurationen av handelsschemaläggare till standardinställningarna.

Efter initialiseringen är klar måste du konfigurera ytterligare handelsdata. Nedan följer några exempel:

- Handelsparametrar
- Parametrar för handelsschemaläggare
- Handelskanaler
- Register och enheter
- Sortiment
