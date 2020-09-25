---
title: Övervaka och hantera IoT-information
description: I det här avsnittet beskrivs hur du övervakar och hanterar IoT-information.
author: robinarh
manager: tfehr
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 15021281b9ec33cd0552bca16e3054d0d3cdd589
ms.sourcegitcommit: 5bb36b74935ffe140367fd6ecf956b4857ad12e5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/14/2020
ms.locfileid: "3803075"
---
# <a name="monitor-and-manage-iot-intelligence"></a>Övervaka och hantera IoT-information

[!include [banner](../../includes/banner.md)]

I det här avsnittet beskrivs hur du övervakar och hanterar IoT-information.

## <a name="monitor-scenarios-in-microsoft-dynamics-365-supply-chain-management"></a><a id="monitor-scenarios"></a>Övervaka scenarier i Microsoft Dynamics 365 Supply Chain Management

Du kan övervaka IoT-information-bearbetningen från flera olika platser:

+ **Moduler \> Tillverkningsstyrning \> Förfrågningar och rapporter \> IoT-information \> Meddelanden** – Visa listan över olösta meddelanden.
+ **Moduler \> Tillverkningsstyrning \> Förfrågningar och rapporter \> IoT-information \> Stängda meddelanden** – Visa listan över meddelanden som har lösts eller stängts.
+ **Moduler \> Tillverkningsstyrning \> Förfrågningar och rapporter \> IoT-information \> Metriska nycklar** – Visa måttnycklarna för **Resursstatus**-diagrammen för tidsserier.
+ **Moduler \> Tillverkningsstyrning \> Tillverkning \> Resursstatus** – Spåra specifika mått med hjälp av dialogrutan **Konfigurera**. Om ett scenario upptäcker ett undantag, visar ett meddelande information om undantaget.
+ **Arbetsytor \> Tillverkningsgolvsledning \> Meddelanden** – Visa listan över olösta meddelanden.

## <a name="modify-a-running-iot-intelligence-scenario"></a>Ändra ett IoT-information-scenario som körs

När ett scenario körs kan du göra följande ändringar:

+ Lägg till nya definitioner för sensorschema.
+ Välj nya värden för signaldata.
+ Avbryt urvalet av befintliga signaldatavärden.
+ Lägg till och mappa nya värden för signaldata.
+ Uppdatera tröskelvärden.

När ett scenario körs är följande ändringar förbjudna:

+ Ta bort eller ändra alla schemadefinitioner som för närvarande används av ett aktiverat scenario.
+ Ändra det aktiverade scenariots valda schemasökvägar.

## <a name="simulation-options"></a>Simuleringsalternativ

Du kan simulera fabriksdatorsignaler. Mer information finns i följande ämnen:

+ [Anslut IoT DevKit AZ3166 till Azure IoT Hub](https://docs.microsoft.com/azure/iot-hub/iot-hub-arduino-iot-devkit-az3166-get-started)
+ [Anslut Raspberryte PI online Simulator till Azure IoT-navet (Node.js)](https://docs.microsoft.com/azure/iot-hub/iot-hub-raspberry-pi-web-simulator-get-started)
+ [Översikt över lösningsaccelerator för enhetssimulering](https://docs.microsoft.com/azure/iot-accelerators/iot-accelerators-device-simulation-overview)
