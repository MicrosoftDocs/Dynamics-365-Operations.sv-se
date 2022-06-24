---
title: Schemaformat för IoT Hub-meddelanden
description: I denna artikel beskrivs hur du bör designa ett meddelandeschema som du kan använda i IoT-information.
author: johanhoffmann
ms.date: 04/25/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-04-25
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 705a2150042f9b65f1f4528d6f2699f7306996f5
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8887469"
---
# <a name="schema-formats-for-iot-hub-messages"></a>Schemaformat för IoT Hub-meddelanden

[!include [banner](../../includes/banner.md)]

I denna artikel beskrivs hur du bör designa ett meddelandeschema som du kan använda i IoT-information.

## <a name="message-requirements"></a>Meddelandekrav

Följande regler gäller för övervakning av meddelanden i IoT-information:

+ Meddelandescheman måste vara i JSON-format (JavaScript Object Notation).
+ En egenskap för UNIX **tidstämpel** där värdet uttrycks i millisekunder (MS), måste finnas i meddelandet i Microsoft Azure IoT Hub.
+ Ett meddelande spåras endast om det innehåller alla egenskaper som är definierade i scenarioinställningarna. Om du till exempel definierar egenskaper **id**, **tidsstämpel** och **värde** visas följande meddelande.

    ```json
    {
        "id": "IoTInt.Machine1225.PartOut",
        "timestamp": 1576016821614,
        "value": True
    }
    ```

    Meddelandet övervakas inte eftersom egenskapen **värde** saknas.

    ```json
    {
        "id": "IoTInt.Machine1225.PartOut",
        "timestamp": 1576016821614,
    }
    ```

+ IoT-information ignorerar egenskaper i meddelandet som inte anges i scenariokonfigurationen. Om du till exempel definierar egenskaper **id**, **tidsstämpel** och **värde** IoT-information kommer att övervaka alla följande meddelanden.

    ```json
    {
        "id": "IoTInt.Machine1225.PartOut",
        "timestamp": 1576016821614,
        "value": True
    },
    {
        "id": "IoTInt.Machine1225.PartOut",
        "timestamp": 1576016821614,
        "value": True,
        "machine" : "Machine1225",
    },
    {
        "id": "IoTInt.Machine1225.PartOut",
        "timestamp": 1576016821614,
        "value": True,
         "activity": "PartOut"
    },
    ```

+ IoT-information ignorerar i tyst fall meddelanden som inte matchar scenario konfigurationskriteriet.
+ Du kan definiera och använda flera typer av meddelandescheman.
+ Alla typer av meddelandescheman måste inte definieras. Det är bara scheman som ska användas för IoT-information scenarier som måste definieras.

## <a name="id-value-pair-schema"></a>ID-värdeparschema

Ett ID-värdepar är ett vanligt mönster för meddelandescheman för IoT-information. Genom att använda ett ID-värdepar ser du till att ditt meddelandeschema är det samma i alla scenarier. Här finns till exempel ett meddelande om scenariot **Driftstopp (utrustning)** eller **Produktionsförseningar**.

```json
{
    "id": "IoTInt.Machine1225.PartOut",
    "timestamp": 1576016821614,
    "value": True
}
```

Här finns ett meddelande för scenariot **Produktkvalitet**.

```json
{
    "id": "IoTInt.Machine1225.Temperature",
    "timestamp": 1576016821614,
    "value": 105
}
```

Både föregående meddelanden innehåller egenskaperna **ID** och **värde**. **ID** kan mappas i registret **Signaldatavärden** under inställningen av scenario. För scenariot **Driftstopp (utrustning)** kommer du att mappa värdet **IoTInt.Machine1225.PartOut**. För scenariot **Produktkvalitet** kommer du att mappa värdet **IoTInt.Machine1225.Temperature**.

Mer information finns i [Azure IoT Hub-dokumentationen](/azure/iot-hub/).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]