---
title: IoT-intelligens – startsida
description: Det här ämnet innehåller länkar till information om IoT-information.
author: tonyafehr
ms.date: 12/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: tfehr
ms.custom: intro-internal
ms.search.region: Global
ms.author: tfehr
ms.search.validFrom: 2020-04-25
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6b6c179052cdb9d1ca808d9cba089163bde0d5d5
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/10/2021
ms.locfileid: "7782691"
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

+ **Produktionsförseningar** – I det här scenariot jämförs faktisk cykeltid med planerad cykeltid. Supply Chain Management meddelar dig när produktionen inte stämmer i tid, så att du kan maximera verksamhetens effektivitet och undvika orderförseningar.
+ **Driftstopp (utrustning)** – I det här scenariot jämförs mättid med användardefinierade parametrar. I Supply Chain Management meddelas du om att en avbrottströskel har överskridits, så att du kan vidta åtgärder som till exempel att omplanering ska ske för en tillverkningsorder eller när du skapar en underhålls arbetsorder.
+ **Produktkvalitet** – Det här scenariot jämför sensoravläsningar, såsom fukt och temperatur, med användardefinierade kvalitetsmått. Supply Chain Management meddelar dig när en avvikelse inträffar så att du kan behålla kvalitetsnormerna och minimera avfallet.

I följande bild visas samspelet mellan Azure IoT Hub, IoT-information och Supply Chain Management.

![IoT Hub, IoT-information och Supply Chain Management.](media/iot_intelligence.png)

## <a name="setup"></a>Ställ in

Du kan ställa in och konfigurera IoT-information utan att skriva någon kod. Här är de grundläggande stegen.

1. [Ställ in Azure-resurser](iot-azure-setup.md) – Skapa en IoT hub, en Redis-cache och ett nyckelvalv som du får åtkomst till från Supply Chain Management.
2. [Meddelandeschemaformat för IoT Hub](iot-schema-format.md) – Konfigurera dina enheter så att de skickar meddelanden till IoT Hub och definiera JavaScript Object Notation (JSON) meddelandeformat.
3. Aktivera funktionen IoT-information i Funktionshantering. 
4. [Installera tillägget IoT-information i Microsoft Dynamics Lifecycle Services (LCS)](iot-lcs-setup.md) – Installera tillägget i LCS och konfigurera Azure-hemligheter.
5. [Ställ in mått](iot-metrics-setup.md) – Ställ in mått i Supply Chain Management.
6. [Scenarioinställningar](iot-scenario-setup.md) – Ange scenarier i Supply Chain Management.

## <a name="tracking-and-maintenance"></a>Spårning och underhåll

+ [Övervaka scenarier i Dynamics 365 Supply Chain Management](iot-management.md#monitor-scenarios)
+ [Inaktivera ett scenario](iot-scenario-setup.md#disable-a-scenario)
+ [Avinstallera tillägget](iot-lcs-setup.md#uninstall-addin)
+ [Ändra ett IoT-information-scenario som körs](iot-management.md#modify-a-running-iot-intelligence-scenario)
+ [Simuleringsalternativ](iot-management.md#simulation-options)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]