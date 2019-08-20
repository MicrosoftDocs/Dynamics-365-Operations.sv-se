---
title: Dataintegrering nästan i realtid mellan Finance and Operations och Common Data Service.
description: Det här ämnet innehåller en översikt över integrering mellan Microsoft Dynamics 365 for Finance and Operations och Common Data Service .
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: aa614c8e6a79a3f7a4f8f2f99f1f1bd1a67ac921
ms.sourcegitcommit: efcc0dee8bde5f8f93f6291e7f059ad426843e57
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/31/2019
ms.locfileid: "1797238"
---
# <a name="near-real-time-data-integration-between-finance-and-operations-and-common-data-service"></a>Dataintegrering nästan i realtid mellan Finance and Operations och Common Data Service.

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

I den nuvarande digitala världen använder företags ekosystem Microsoft Dynamics 365-sviten som helhet. Eftersom data från personer, kunder, åtgärder och sakernas Internet (IoT)-enheter flödar till en källa finns det en möjlighet för digitala feedbackloopar. För att uppnå den här upplevelsen är integration mellan Dynamics 365 for Finance and Operations och Dynamics 365 for Customer Engagement-program viktigt. Customer Engagement-program byggs ovanpå Common Data Service. Integrering mellan Finance and Operations-data med Common Data Service låter Customer Engagement-program kommunicera konsekvent och flytande med Finance and Operations.

Finance and Operations och Common Data Service tillhandahåller datasynkronisering nästan i realtid mellan Finance and Operations och Customer Engagement-program via ett ramverk med dubbelriktad skrivning. Täckningen är bred och spänner över 28 ytområden av Finance and Operations. Målet är att ge användarupplevelsen "en Dynamics 365" genom sömlösa dataflöden som kopplar samman affärsprocesser mellan olika program.

![Diagram över arkitekturöversikt](media/dual-write-overview.jpg)

Följande värdepropositioner är tillgängliga för kunder:

+ [Organisationshierarki i Common Data Service](dual-write-organization.md)
+ [Företagskoncept i Common Data Service](dual-write-company.md)
+ [Integrerat kundhuvud](dual-write-customer.md)
+ [Integrerat leverantörshuvud](dual-write-vendor.md)
+ Enhetlig produktmall

## <a name="system-requirements"></a>Systemkrav

Synkrona, dubbelriktad, dataflöden nästan i realtid kräver följande versioner:

+ Microsoft Dynamics 365 for Finance and Operations version 10.0.4 (juli 2019) med plattformsuppdatering 28 eller senare
+ Microsoft Dynamics 365 for Customer Engagement, plattform version 9.1 (4.2) eller senare

## <a name="setup-instructions"></a>Installationsanvisningar

Följ dessa steg för att ställa in integrationen mellan med Finance and Operations och Common Data Service.
    
1. För installationen av dubbelriktad skrivningssystemet, se [stegvis guiden](https://aka.ms/dualwrite-docs) om att tillkännage förhandsgranskning av dubbelriktad skrivning.
2. Hämta och installera lösningen från gruppen [Finance and Operations, Common Data Service, och Customer Engagement-iIntegration](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=66052096) Yammer. Paketet innehåller fem lösningar:

    + Dynamics365Company
    + CurrencyExchangeRates
    + Dynamics365FinanceAndOperationsCommon
    + Dynamics365FinanceCommon
    + Dynamics365SupplyChainCommon

3. Följ körningsordningen för att [synkronisera inledande referensdata](dual-write-initial.md).
4. Om du stöter på problem med synkronisering av dubbelriktad skrivning, se [felsökningsguiden för felsökningsguiden](dual-write-troubleshooting.md).

> [!IMPORTANT]
> Du kan inte köra dubbelriktad skrivning och [potentiell kund till kontanter](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/accounts-template-mapping-direct) sida vid sida. Om du kör lösningen potentiell kund till kontanter måste du avinstallera den. Du måste också inaktivera de mallar för dubbelriktad skrivning som ingår i lösningen potentiell kund till kontanter.
