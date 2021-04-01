---
title: Borttagna och utfasade funktioner i Dynamics 365 Commerce
description: I det här avsnittet beskrivs funktioner som har tagits bort, eller har planerats för borttagning från Dynamics 365 Commerce.
author: josaw
manager: AnnBe
ms.date: 01/11/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2020-04-30
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 357f4673d77ee990c4e1b0ce84a704fd4d778402
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5240229"
---
# <a name="removed-or-deprecated-features-in-dynamics-365-commerce"></a>Borttagna och utfasade funktioner i Dynamics 365 Commerce

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs funktioner som har tagits bort, eller har planerats för borttagning från Dynamics 365 Commerce.

- En *borttagen* funktion är inte längre tillgänglig i produkten.
- En *borttagen* funktion är inte i aktiv utveckling och kan tas bort i en kommande uppdatering.

Den här listan är avsedd att hjälpa dig att ta hänsyn till dessa borttagna och inaktuella funktioner för din planerings skull. 

> [!NOTE]
> Detaljerad information om objekt i Finance and Operations-appar hittas i [Tekniska referensrapporter](https://docs.microsoft.com/dynamics/s-e/). Du kan jämföra olika versioner av rapporterna för mer information om objekt som har ändrats eller tagits bort i varje version av Finance and Operations-appar.

## <a name="features-removed-or-deprecated-in-the-commerce-10017-release"></a>Borttagna eller föråldrade funktioner i Commerce version 10.0.17

> [!Important]
> Version 10.0.17 finns tillgänglig i en förhandsversion. Funktionen och dess innehåll kan ändras. Mer information om förhandsversioner finns i [Frågor och svar om tjänstuppdateringar för en version](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/one-version).

### <a name="full-dataset-generation-interval-is-deprecated"></a>Fullständigt genereringsintervall för datauppsättning blir inaktuellt

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | I formuläret **Parametrar för handelsschema** i Dynamics 365-administationen kommer från och med denna version fältet **Intervall för komplett datauppsättningsgenerering** att bli inaktuellt. Från och med denna version tas fältet även bort visuellt så att värdet inte kan redigeras. Detta förblir värdet **0**. |
| **Ersatt av en annan funktion?**   | Nr |
| **Produktområden som påverkas**         | Dynamics 365 Commerce |
| **Distribueringsalternativ**              | Allt|
| **Status**                         | Inaktuell. Använd inte detta fält, och ändra heller inte värdet i det.|

## <a name="features-removed-or-deprecated-in-the-commerce-10015-release"></a>Borttagna eller föråldrade funktioner i Commerce version 10.0.15

### <a name="internet-explorer-11-support-for-dynamics-365-is-deprecated"></a>Internet Explorer 11-stöd för Dynamics 365 är inaktuellt

|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Från och med december 2020 kommer Microsoft Internet Explorer 11-stöd för samtliga Dynamics 365-produkter att betraktas som inaktuellt, och Internet Explorer 11 kommer inte att stödjas efter augusti 2021.<br><br>Detta påverkar kunder som använder Dynamics 365-produkter som har utformats för användning med ett Internet Explorer 11-gränssnitt. Efter augusti 2021 stöds inte Internet Explorer 11 för sådana Dynamics 365-produkter. |
| **Ersatt av en annan funktion?**   | Vi rekommenderar våra kunder att övergå till Microsoft Edge.|
| **Produktområden som påverkas**         | Alla Dynamics 365-produkter |
| **Distribueringsalternativ**              | Allt|
| **Status**                         | Inaktuell. Internet Explorer 11 kommer inte att stödjas efter augusti 2021.|

## <a name="features-removed-or-deprecated-in-the-commerce-10011-release"></a>Borttagna eller föråldrade funktioner i Commerce version 10.0.11
### <a name="data-action-hooks"></a>Dataåtgärdshookar
|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Funktionen dataåtgärdshookar har föråldrats på grund av prestandaproblem. |
| **Ersatt av en annan funktion?**   | Vi rekommenderar att du använder [dataåtgärdsåsidosättningar](../e-commerce-extensibility/data-action-overrides.md) för att ändra affärslogiken i dataåtgärdsskiktet.|
| **Produktområden som påverkas**         | Dataåtgärder för utbyggbarhet för näthandel |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Inaktuell: Från version 10.0.11 |

### <a name="retail-sdk-support-for-visual-studio-2015-msbuild-140-and-retail-sdkreference-libraries-and-tools"></a>Stöd för SDK för Retail för Visual Studio 2015, msbuild 14.0 och Retail SDK\Referensbibliotek och verktyg
|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Stöd för Retail SDK för Visual Studio 2015 har föråldrats och uppdaterats till att stödja VS 2017, msbuild 15.0 och alla referensbibliotek och verktyg för Commerce och proxy-generator i mappen RetailSDK\References har flyttat till NuGet-paket för att förenkla tilläggsmodellen och SDK-uppgraderingsprocessen.|
| **Ersatt av en annan funktion?**   | Vi rekommenderar att du följer informationen i [Flytta SDK för Retail från Visual Studio 2015 till Visual Studio 2017](../dev-itpro/retail-sdk/migrate-sdk.md) för att uppdatera systemet. |
| **Produktområden som påverkas**         | SDK-tillägg för Retail |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Inaktuell: Från version 10.0.11 |

### <a name="retail-server-extension-using-iedmmodelextender-and-commercecontroller"></a>Tillägg i Retail Server med IEdmModelExtender och CommerceController
|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Tillägg Retail Server med IEdmModelExtender och CommerceController har ersatts för att ge förenklad tilläggsmodell. Den nya implementeringen har bara styrenhetsklassen utan ytterligare IEdmModelExtender klassimplementering. Detta eliminerar också beroendet med en särskild OData-version (om OData-versionen uppdateras kan det innebära att tillägg avbryts.) |
| **Ersatt av en annan funktion?**   |  Vi rekommenderar att du använder klasstilläggsmodellen IController genom att importera NuGet-paketet (Microsoft.Dynamics.Commerce.Hosting.Contracts). |
| **Produktområden som påverkas**         | Tillägg för Retail Server |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Inaktuell: Från version 10.0.11 |

### <a name="hardware-station-extension-using-ihardwarestationcontroller"></a>Tillägget Hardware station med IHardwareStationController
|   |  |
|------------|--------------------|
| **Orsak till inaktuell/borttagning** | Tillägget Hardware station med IHardwareStationController har ersatts för att ge förenklad tilläggsmodell. Den nya implementeringen har bara IController-klassen utan någon ytterligare klassimplementering och för att undvika beroendet av kärnbibliotek för Hardware station, måste du använda tidigare tillägg för att referera flera bibliotek.) |
| **Ersatt av en annan funktion?**   | Vi rekommenderar att du använder klasstilläggsmodellen IController genom att importera NuGet-paketet (Microsoft.Dynamics.Commerce.Hosting.Contracts). |
| **Produktområden som påverkas**         | Tillägg för Hardware Station |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Inaktuell: Från version 10.0.11 |

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
| **Produktområden som påverkas**         | näthandelsprogram SDK |
| **Distribueringsalternativ**              | Allt |
| **Status**                         | Inaktuell: Från version 10.0.7 kommer du inte längre att kunna göra tekniska investeringar för GetProductAvailabilities och GetAvailableInventoryNearby. Organisationer som använder dessa API:er i sina näthandelsdistributioner bör konvertera till nya GetEstimatedAvailability och GetEstimatedProductWarehouseAvailability API:er och aktivera [optimerade beräkningsfunktionen för produkttillgänglighet](https://docs.microsoft.com/dynamics365/commerce/calculated-inventory-retail-channels).  |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a>Tidigare meddelanden om borttagna eller inaktuella funktioner
Om du vill veta mer om funktioner som har tagits bort eller ersatts i tidigare versioner, se [borttagna eller inaktuella funktioner i tidigare versioner](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md?toc=/dynamics365/commerce/toc.json).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]