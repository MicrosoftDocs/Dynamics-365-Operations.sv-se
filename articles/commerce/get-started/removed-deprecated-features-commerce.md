---
title: Borttagna och utfasade funktioner i Dynamics 365 Commerce
description: I det här avsnittet beskrivs funktioner som har tagits bort, eller har planerats för borttagning från Dynamics 365 Commerce.
author: josaw
manager: AnnBe
ms.date: 05/04/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2020-04-30
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: c47c5430a8f5d67e13c95db609a95d5ad66933ae
ms.sourcegitcommit: a8b6cd799eddaf5be9aec9ea3c2b55e2c3231652
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/05/2020
ms.locfileid: "3335286"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-commerce"></a>Borttagna och utfasade funktioner i Dynamics 365 Commerce

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs funktioner som har tagits bort, eller har planerats för borttagning från Dynamics 365 Commerce.

- En *borttagen* funktion är inte längre tillgänglig i produkten.
- En *borttagen* funktion är inte i aktiv utveckling och kan tas bort i en kommande uppdatering.

Den här listan är avsedd att hjälpa dig att ta hänsyn till dessa borttagna och inaktuella funktioner för din planerings skull. 

> [!NOTE]
> Detaljerad information om objekt i Finance and Operations-appar hittas i [Tekniska referensrapporter](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep). Du kan jämföra olika versioner av rapporterna för mer information om objekt som har ändrats eller tagits bort i varje version av Finance and Operations-appar.

## <a name="features-removed-or-deprecated-in-the-commerce-10010-release"></a>Borttagna eller föråldrade funktioner i Commerce version 10.0.10
### <a name="pos-operation-803---picking-and-receiving"></a>Kassaåtgärd 803 – Plockning och mottagning
|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Plocknings- och mottagningsåtgärder föråldras på grund av att ny åtgärd har omdesignats. |
| **Ersatt av en annan funktion?**   | Ja. Den ersätts av två nya kassaåtgärder: inkommande åtgärd (804) och utgående åtgärd (805).|
| **Produktområden som påverkas**         | Program för kassa (POS) |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Inaktuell: Från version 10.0.10 kommer åtgärden för plockning och mottagning inte längre att erhålla funktionsuppdateringar. Endast viktiga felkorrigeringar kommer att utföras för den här åtgärden i framtida versioner. Alla kunder uppmuntras att flytta till de nya [Inkommande åtgärderna](https://docs.microsoft.com/dynamics365/commerce/pos-inbound-inventory-operation) och [Utgående åtgärderna](https://docs.microsoft.com/dynamics365/commerce/pos-outbound-inventory-operation) som fortsätter att ingå i vår långsiktiga produktplan. |


## <a name="features-removed-or-deprecated-in-the-commerce-1007-release"></a>Borttagna eller föråldrade funktioner i Commerce version 10.0.7
### <a name="commerce-getproductavailabilities-and-getavailableinventorynearby-apis"></a>Commerce GetProductAvailabilities och GetAvailableInventoryNearby API:er
|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Nya optimerade API:er har skapats för att ersätta GetProductAvailabilities och GetAvailableInventoryNearby API:er. |
| **Ersatt av en annan funktion?**   | Ja: Det ersätts med GetEstimatedAvailability och GetEstimatedProductWarehouseAvailability API:er. |
| **Produktområden som påverkas**         | e-handelsprogram SDK |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Inaktuell: Från version 10.0.7 kommer du inte längre att kunna göra tekniska investeringar för GetProductAvailabilities och GetAvailableInventoryNearby. Organisationer som använder dessa API:er i sina e-handelsdistributioner bör konvertera till nya GetEstimatedAvailability och GetEstimatedProductWarehouseAvailability API:er och aktivera [optimerade beräkningsfunktionen för produkttillgänglighet](https://docs.microsoft.com/dynamics365/commerce/calculated-inventory-retail-channels).  |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>Tidigare meddelanden om borttagna eller inaktuella funktioner
Om du vill veta mer om funktioner som har tagits bort eller ersatts i tidigare versioner, se [borttagna eller inaktuella funktioner i tidigare versioner](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md?toc=/dynamics365/commerce/toc.json).
