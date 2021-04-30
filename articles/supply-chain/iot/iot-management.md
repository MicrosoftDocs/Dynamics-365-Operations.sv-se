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
ms.openlocfilehash: 86e20b9e60e890833c0eb8573e92c0fbb27f8c9a
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2021
ms.locfileid: "5908429"
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

+ [Anslut IoT DevKit AZ3166 till Azure IoT Hub](/azure/iot-hub/iot-hub-arduino-iot-devkit-az3166-get-started)
+ [Anslut Raspberryte PI online Simulator till Azure IoT-navet (Node.js)](/azure/iot-hub/iot-hub-raspberry-pi-web-simulator-get-started)
+ [Översikt över lösningsaccelerator för enhetssimulering](/azure/iot-accelerators/iot-accelerators-device-simulation-overview)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]