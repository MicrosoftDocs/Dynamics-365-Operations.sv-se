---
title: Övervaka och hantera IoT-information
description: I det här avsnittet beskrivs hur du övervakar och hanterar IoT-information.
author: robinarh
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: rhaertle
ms.custom: ''
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 94665b3646456b689a8e65e94b098e86e467d5e3
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5813085"
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


[!INCLUDE[footer-include](../../includes/footer-banner.md)]