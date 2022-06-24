---
title: IoT-intelligens – startsida
description: Denna artikel innehåller länkar till information om IoT-information.
author: johanhoffmann
ms.date: 12/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.custom: intro-internal
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-04-25
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b43681b036379a6f95103d4bb17cbde018724552
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8877636"
---
# <a name="iot-intelligence-home-page"></a>IoT-intelligens – startsida

[!include [banner](../../includes/banner.md)]

> [!IMPORTANT]
> Den här funktionen finns för närvarande bara i följande länder och regioner:
>
> - USA (Amerikas förenta stater)
> - EU (Europeiska unionen)
> - AU (Australien)
> - CA (Kanada)
> - UK (Storbritannien)

IoT-information är ett tillägg för Microsoft Dynamics 365 Supply Chain Management. Det integrerar Internet of Things (IoT) med data i Supply Chain Management för att ge insikter som kan användas.

IoT-information stöder följande scenarier:

- **Produktionsförseningar** – I det här scenariot jämförs faktisk cykeltid med planerad cykeltid. Supply Chain Management meddelar dig när produktionen inte stämmer i tid, så att du kan maximera verksamhetens effektivitet och undvika orderförseningar.
- **Driftstopp (utrustning)** – I det här scenariot jämförs mättid med användardefinierade parametrar. I Supply Chain Management meddelas du om att en avbrottströskel har överskridits, så att du kan vidta åtgärder som till exempel att omplanering ska ske för en tillverkningsorder eller när du skapar en underhålls arbetsorder.
- **Produktkvalitet** – Det här scenariot jämför sensoravläsningar, såsom fukt och temperatur, med användardefinierade kvalitetsmått. Supply Chain Management meddelar dig när en avvikelse inträffar så att du kan behålla kvalitetsnormerna och minimera avfallet.

I följande bild visas samspelet mellan Azure IoT Hub, IoT-information och Supply Chain Management.

![IoT Hub, IoT-information och Supply Chain Management.](media/iot_intelligence.png)

<!-- KFM: hide setup info for now

## Setup

You can set up and configure IoT Intelligence without writing any code. Here are the basic steps.

1. [Set up Azure resources](iot-azure-setup.md) – Create an IoT hub, a Redis cache, and a key vault that can be accessed from Supply Chain Management.
2. [Message schema formats for IoT Hub](iot-schema-format.md) – Configure your devices to send messages to IoT Hub, and define the JavaScript Object Notation (JSON) message format.
3. In Feature Management, enable the IoT Intelligence feature flag. 
4. [Install the IoT Intelligence add-in in Microsoft Dynamics Lifecycle Services (LCS)](iot-lcs-setup.md) – Install the add-in in LCS, and configure the Azure secrets.
5. [Set up metrics](iot-metrics-setup.md) – Set up metrics in Supply Chain Management.
6. [Scenario setup](iot-scenario-setup.md) – Set up the scenarios in Supply Chain Management.

-->

## <a name="tracking-and-maintenance"></a>Spårning och underhåll

- [Övervaka scenarier i Dynamics 365 Supply Chain Management](iot-management.md#monitor-scenarios)
- [Inaktivera ett scenario](iot-scenario-setup.md#disable-a-scenario)
- [Ändra ett IoT-information-scenario som körs](iot-management.md#modify-a-running-iot-intelligence-scenario)
- [Simuleringsalternativ](iot-management.md#simulation-options)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]