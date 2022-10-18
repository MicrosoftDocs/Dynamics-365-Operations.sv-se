---
title: Ställ in en simulerad sensor för testning
description: I den här artikeln beskrivs hur du ställer in en uppsättning som du kan använda för att testa Sensor Data Intelligence utan att installera några fysiska skador.
author: johanhoffmann
ms.date: 09/02/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-09-02
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: dc8bd020a53214abab28ec51ffc6d6be74979932
ms.sourcegitcommit: c5f2cba3c2b0758e536eeaaa40506659a53085e1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/12/2022
ms.locfileid: "9643987"
---
# <a name="set-up-a-simulated-sensor-for-testing"></a>Ställ in en simulerad sensor för testning

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

Om du vill testa Sensor Data Intelligence utan att installera någon fysiskt beroende, kan du använda tjänsten *Raspberry PI Azure IoT Online Simulator* för att emulera sensorsignaler och skicka dem till din Sakernas Internet-lösning (IoT) på Microsoft Azure. För mer information om simulatorn, se [Connect Raspberry Pi online simulator till Azure IoT Hub (Node.js)](/azure/iot-hub/iot-hub-raspberry-pi-web-simulator-get-started).

## <a name="video-instructions"></a>Videoanvisningar

Följande video visar hur du ställer in en simulerad sensor för testning. De återstående avsnitten i den här artikeln tillhandahåller samma instruktioner i ett textbaserat format.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE588g6]

## <a name="create-a-device-in-azure-iot-hub"></a>Skapa en enhet i Azure IoT Hub

Du måste först ställa in en enhet för att autentisera sensoren till Azure IoT Hub.

1. Gå till listan över resurser för resursgruppen som du har skapat för användning med Sensor Data Intelligence i Azure. (Mer information finns i [Distribuera en IoT-lösning på Azure](sdi-deploy-iot-solution-on-azure.md).)
1. Sök efter posten i resurslistan där fältet **Typ** är inställt på *IoT Hub*. I kolumnen **Namn** välj namnet för att öppna informationssidan för resursen.
1. I navigeringsfönstret till vänster välj er du **Enheter**.
1. På sidan **Enheter** markerar du **Lägg till enhet**.
1. På sidan **Skapa en enhet** anger du följande fält:

    - **Enhets-ID** – Ange ett namn på den nya enheten (t.ex. *My-IoT-Device*).
    - **Autentiseringstyp** – Välj *symmetriska nycklar*.
    - **Generera nycklar automatiskt** – Markera den här kryssrutan.
    - **Koppla den här enheten till en IoT** – välj *Aktivera*.

1. Välj **Spara** om du vill gå tillbaka till sidan **Enheter**.
1. Hitta den nya enheten i listan. I kolumnen **Enhets-ID** välj namnet för att öppna informationssidan för enheten. Uppdatera sidan om den nya enheten inte visas i listan.
1. Kopiera värdet **Primär anslutningssträng** (genom att t.ex. välja knappen **Kopiera till Urklipp**). Du kommer att behöva detta värde senare när du ställer in Raspberry Pi IoT-simulatorn för att emulera sensorsignaler. Överväg därför att klistra in den i en textfil för nu.

## <a name="add-the-azure-connection-string-to-the-raspberry-pi-iot-simulator"></a>Lägg till Azure-anslutningssträngen till Raspberry Pi IoT-simulatorn

Följ dessa steg om du vill lägga till anslutningssträngen från enheten i Azure IoT Hub till skriptet i Raspberry-tjänst.

1. Öppna [Raspberry Pi IoT-simulatorn](https://azure-samples.github.io/raspberry-pi-web-simulator/).
1. Leta reda på raden som innehåller följande kommando i kodredigeraren.

    `const connectionString = '[Your IoT hub device connection string]';`

1. Ersätt hjälptexten, inklusive hakparenteser, med värdet **primära anslutningssträng** som du kopierade i föregående avsnitt. Resultatet bör likna följande exempel:

    `const connectionString = 'HostName=XXX;DeviceId=YYY;SharedAccessKey=ZZZ';`

## <a name="add-sensor-ids-and-values-to-the-payload-in-the-raspberry-pi-iot-simulator"></a>Lägg till id:ar och värden för sensoren i Raspberry Pi IoT-simulatorn

Du måste nu ställa in Raspberry Pi IoT-simulatorn med simulerade sensorer och de värden som de kommer att skicka som nyttolaster.

- Hitta funktionen i kodredigeraren för Raspberry Pi IoT-simulatorn `getMessage` och redigera den så att den matchar följande kod. (Sensorerna är inställda i `cb()` raderna.)

    ```cpp
    function getMessage(cb) {
        messageId++;
        sensor.readSensorData()
        .then(function (data) {
            cb(JSON.stringify({ value: 1, sensorId: 'MachineStatus' }), false);
            cb(JSON.stringify({ value: 70, sensorId: 'Quality' }), false);
            cb(JSON.stringify({ value: 1, sensorId: 'AssetMaintenance' }), false);
            cb(JSON.stringify({ value: 1, sensorId: 'ProductionDelay' }), false);
            cb(JSON.stringify({ value: 20, sensorId: 'AssetDowntime' }), false);
        })
        .catch(function (err) {
            console.error('Failed to read out sensor data: ' + err);
        });
    }
    ```

    > [!IMPORTANT]
    > Sensor-ID:n som definieras i kodredigeraren för Raspberry Pi IoT-simulatorn måste vara identiska med sensor-ID:n som du kommer att ange senare för scenarierna i Supply Chain Management. I föregående exempelkod används person läsbara sensor-/ID:er. I ett faktiskt scenario blir dock id:n för avkännar-ID:n globala unika identifierare (GUID) som tillhandahålls av sensortillverkaren. De mänskligt läsbara sensor-ID:n som används i denna exempelkod används också i exemplen i [produktkvalitetsscenariot](sdi-scenario-product-quality.md), [underhållsscenario för tillgång](sdi-scenario-asset-maintenance.md), [scenariot för produktionsförseningar](sdi-scenario-production-delays.md) och [underhållsscenario för tillgång](sdi-scenario-equipment-downtime.md)). Därför ska du använda den här koden om du arbetar dig igenom dessa scenarier.

## <a name="edit-the-interval-for-sending-sensor-signals"></a>Redigera intervallet för att skicka sensorsignaler

Du måste nu ställa in intervallet med vilket Raspberry Pi IoT-simulatorn ska skicka de emulerade sensorsignalerna.

1. Du måste nu ställa in intervallet med vilket Raspberry Pi IoT-simulatorn ska skicka de emulerade sensorsignalerna.

    `setInterval(sendMessage, 2000);`

2. Som standard skickar Raspberry Pi IoT-simulatorn en sensorsignal var 2 000:e millisekund (två sekunder). Du kan justera värdet som du vill.

## <a name="run-the-raspberry-pi-iot-simulator"></a>Kör Raspberry Pi IoT-simulator

- Välj **Kör** för att starta den och börja skicka simulerade sensordata.
