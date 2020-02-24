---
title: Dataintegrering nästan i realtid med Common Data Service
description: Det här ämnet innehåller en översikt över integrering mellan Finance and Operations och Common Data Service .
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
ms.openlocfilehash: 1c09b0c0bb695e7695acb7a8821ffb99ae1f6f06
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/04/2020
ms.locfileid: "3020022"
---
# <a name="near-real-time-data-integration-with-common-data-service"></a>Dataintegrering nästan i realtid med Common Data Service

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

I den nuvarande digitala världen använder företags ekosystem Microsoft Dynamics 365-appar som helhet. Eftersom data från personer, kunder, åtgärder och sakernas Internet (IoT)-enheter flödar till en källa finns det en möjlighet för digitala feedbackloopar. För att uppnå den här upplevelsen är integration mellan Finance and Operations-appar och andra Dynamics 365-program viktigt. Vissa appar byggs ovanpå Common Data Service. Integration mellan Finance and Operations-appdata med Common Data Service låter våra andra program kommunicera konsekvent och flytande med Finance and Operations.

Finance and Operations-appar och Common Data Service tillhandahåller datasynkronisering nästan i realtid mellan Finance and Operations-appar och andra Dynamics 365-program via ett ramverk med dubbelriktad skrivning. Täckningen är bred och spänner över 28 ytområden av appen. Målet är att ge användarupplevelsen "en Dynamics 365" genom sömlösa dataflöden som kopplar samman affärsprocesser mellan olika program.

![Diagram över arkitekturöversikt](media/dual-write-overview.jpg)

Följande värdepropositioner är tillgängliga:

+ [Organisationshierarki i Common Data Service](organization-mapping.md)
+ [Företagskoncept i Common Data Service](company-data.md)
+ [Integrerat kundhuvud](customer-mapping.md)
+ [Integrerad redovisning](ledger-mapping.md)
+ [Enhetlig produktupplevelse](product-mapping.md)
+ [Integrerat leverantörshuvud](vendor-mapping.md)
+ [Integrerade platser och lagerställen](sites-warehouses-mapping.md)
+ [Integrerad huvudskatt](tax-mapping.md)

## <a name="system-requirements"></a>Systemkrav

Synkrona, dubbelriktad, dataflöden nästan i realtid kräver följande versioner:

+ Microsoft Dynamics 365 for Finance and Operations version 10.0.4 (juli 2019) med plattformsuppdatering 28 eller senare
+ Microsoft Dynamics 365 for Customer Engagement, plattform version 9.1 (4.2) eller senare

## <a name="setup-instructions"></a>Installationsanvisningar

Följ dessa steg för att ställa in integration mellan Finance and Operations-appar och Common Data Service.
    
1. För installationen av dubbelriktad skrivningssystemet, se [stegvis guiden](https://aka.ms/dualwrite-docs) om att tillkännage förhandsgranskning av dubbelriktad skrivning.
2. Ladda ned och installera lösningen från [Fin Ops och CD/CE-integration via dubbelriktad](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=66052096)Yammer-gruppen. Paketet innehåller fem lösningar:

    + Dynamics365Company
    + CurrencyExchangeRates
    + Dynamics365FinanceAndOperationsCommon
    + Dynamics365FinanceCommon
    + Dynamics365SupplyChainCommon

3. Följ körningsordningen för att [synkronisera inledande referensdata](initial-sync.md).
4. Om du stöter på problem med synkronisering av dubbelriktad skrivning, se [felsökningsguiden för felsökningsguiden](dual-write-troubleshooting.md).

> [!IMPORTANT]
> Du kan inte köra dubbelriktad skrivning och [potentiell kund till kontanter](../../../../supply-chain/sales-marketing/prospect-to-cash.md) sida vid sida. Om du kör lösningen potentiell kund till kontanter måste du avinstallera den. Du måste också inaktivera de mallar för dubbelriktad skrivning som ingår i lösningen potentiell kund till kontanter.
