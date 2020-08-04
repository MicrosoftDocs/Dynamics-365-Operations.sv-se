---
title: Scenarioinställningar för IoT-information
description: I det här avsnittet beskrivs hur du konfigurerar ett scenario i Supply Chain Management för IoT-information.
author: robinarh
manager: tfehr
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: ''
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: ''
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 5633741fcd9c04b68e5b174447d7ead3c521ccd7
ms.sourcegitcommit: f64fce03ec52f844b05a9e8cac286cb201385002
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/16/2020
ms.locfileid: "3597178"
---
# <a name="scenario-setup-for-iot-intelligence"></a>Scenarioinställningar för IoT-information

[!include [banner](../../includes/banner.md)]

I det här avsnittet beskrivs hur du konfigurerar ett scenario i Supply Chain Management för IoT-information. Innan du kan ställa in scenarier måste du [konfigurera LCS](iot-lcs-setup.md).

I det här avsnittet konfigurerar du scenariot **Driftstopp (utrustning)** i syfte att generera ett meddelande i Supply Chain Management när en dator slutar att fungera.

## <a name="configure-the-equipment-downtime-scenario-in-supply-chain-management"></a>Konfigurera scenariot **Driftstopp (utrustning)** i Supply Chain Management

Scenariot **Driftstopp (utrustning)** mappar en signal om komponent ur funktion till ett tröskelvärde för datornotifiering. Datorn övervakas bara när den väljs ut för scenariot och ställs in för körning i Supply Chain Management. Om tiden sedan datorn senast mottagna signal för komponent ur funktion överstiger tröskelvärdet för notifiering, kommer ett meddelande om **Datorstopp** att utlösas. Om datorn fortfarande körs kommer, när nästa **KomponentUt**-signal tas emot, ett meddelande om **datorn körs** att lösas ut. Om en dator förblir ur drift i 30 minuter utlöses ett nytt meddelande om **datorstopp**.

Scenariot **Driftstopp (utrustning)** har följande beroenden:

+ En tillverkningsorder måste köras på en mappad dator för att en notifiering ska utlösas.
+ En signal som representerar en mappad datorns signal för komponentstopp måste skickas till IoT-navet med ett unikt egenskapsnamn.
+ En Unix-egenskap för tidsstämpel i millisekunder måste finnas i IoT-navmeddelandet.

Följ dessa steg för att konfigurera scenariot:

1. Logga in på Supply Chain Management.
2. Aktivera funktionsflaggan för IoT-information. Mer information finns i [Översikt för funktionshantering](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).
3. Konfigurera måtten. Mer information finns i [Konfigurera mått](iot-metrics-setup.md#configure-metrics).
4. Navigera till **Tillverkningsstyrning**.
5. Navigera till **Konfiguration \> IoT-information \> Scenariohantering**.
6. Klicka på **Konfigurera** på panelen **Driftstopp (utrustning)**. Konfigurationsguiden startar med sidan **Schemadefinition för utrustningssensor**. Målet här är att ställa in schemat i Supply Chain Management så att det matchar formatet JSON i IoT-meddelandena. Du kan definiera flera meddelandescheman. Mer information finns i [Format för meddelandeschema för IoT-nav](iot-schema-format.md). I det här exemplet innehåller meddelandets nyttolasten en batch med meddelanden med detta format:

    ```json
    {
        "timestamp": 1576016821614,
        "payload": [
            {
                "id": "IoTInt.Machine1225.PartOut",
                "timestamp": 1576016821614,
                "value": True
            },
            {
                "id": "IoTInt.Machine1226.PartOut",
                "timestamp": 1576016991616,
                "value": True
            }
        ]
    }
    ```

7. Lägg till en rad i registret.

    1. Ange **Schemanamn** som **ID**.
    2. Ange **Schemasökväg** som **/payload[\*]/id**.
    3. Ange **Beskrivning** som **Meddelande-ID**.

8. Lägg till en rad i registret.

    1. Ange **Schemanamn** som **Tidsstämpel**.
    2. Ange **Schemasökväg** som **/payload[\*]/timestamp**.
    3. Ange **Beskrivning** som **Tidsstämpel för meddelande**.

9. Lägg till en rad i registret.

    1. Ange **Schemanamn** som **Värde**.
    2. Ange **Schemasökväg** som **/payload[\*]/värde**.
    3. Ange **Beskrivning** som **Meddelandevärde**.

    Du behöver inte definiera alla egenskaper i meddelandet, bara dem du behöver. I det här exemplet skapades ingen rad för **Rottidsstämpel**. Sökvägen för **Rottidsstämpel** skulle bli **/timestamp**.
  
10. Klicka på **Nästa** för att gå till sidan **Schemaöversikt för utrustningssensor**.
11. I raden för **Resurs-ID för utrustning** anger du **schemanamnet** som **ID**. Giltiga värden visas i ett listruteregister.
12. I raden för **UTC-tid** anger du **schemanamnet** som **Tidsstämpel**. Giltiga värden visas i ett listruteregister.
13. I raden för **Komponentgenererad signal** anger du **schemanamnet** som **Värde**. Giltiga värden visas i ett listruteregister.
14. Klicka på **Nästa** för sidan **ID-konfiguration för utrustningsresurs**.
15. I det här steget mappar du IoT-navets meddelandevärden till resurserna för Supply Chain Management.

    1. I registret **Värden för signaldata** lägger du till en ny rad och anger **IoTInt.Machine1225.PartOut** i kolumnen **Värde**. Värdet **IoTInt.Machine1225.PartOut** kommer från egenskapen **id** för JSON i IoT-navmeddelandet.
    2. Klicka på **Spara**.
    3. I registret **Mappning av affärspost** klickar du på **Ny**. Standardvärdet för **Affärsposttyp** fylls i automatiskt, och du behöver inte ändra det.
    4. I kolumnen **Affärspost** väljer du den Supple Chain Management-datorresurs som detta signalvärde skickas ifrån.
    5. Klicka på **Spara**.
    6. Upprepa stegen och lägg till en ny mappning för affärspost för **Machine1226**. Du kan mappa flera signaldatavärden till en enda post i Supply Chain Management.

16. Använd kolumnen **Vald** för att välja vilka datorer som ska bearbetas. Du behöver inte definiera alla signalvärden och du behöver inte välja alla datorer.
17. Klicka på **Nästa** om du vill gå till sidan för den **komponentproducerade signalkonfigurationen**.
18. I registret **Signaldatavärden** lägger du till en rad och anger **Värde** som **True**. Värdet **True** kommer från JSON-egenskapen **värde** i IoT-meddelande. Du kan lägga till så många värden som du behöver i scenariot.
19. Klicka på **Spara**.
20. Klicka på **Nästa** för att gå till sidan **Tröskelvärde för driftstopp (utrustning)**. De angivna datorerna är de som tidigare har mappats till signalvärden. I det här steget definierar du ett tröskelvärde för att fastställa om en dator inte är tillgänglig. Om du till exempel ställer in tröskelvärdet på 10 genererar Supply Chain Management ett meddelande om det inte finns något meddelande om defekt komponent från en maskin på 10 minuter.
21. Klicka på **Nästa** för att öppna sidan **Aktivera scenario**. Aktivera scenariot genom att förflytta skjutreglaget.
22. Klicka på **Avsluta**.

Scenariokonfigurationen har slutförts. IoT-information kommer automatiskt att börja bearbeta IoT-navmeddelandena.

## <a name="configure-the-product-quality-scenario-in-supply-chain-management"></a>Konfigurera scenariot **Produktkvalitet** i Supply Chain Management

Scenariot **Produktkvalitet** genererar ett meddelande om ett attribut för en artikel ligger utanför ett angivet intervall. En sensor kan t.ex. skicka vikten för varje enskilt objekt till IoT-navet. Ett meddelande genereras i Supply Chain Management om artikeln är för tungt eller för lätt.

Scenariot har följande beroenden:

+ En tillverkningsorder måste köras på en mappad dator och framställa en produkt med mappat batchattibut för att en notifiering ska utlösas.
+ En signal som representerar batchattributet måste skickas till IoT-navet med ett unikt egenskapsnamn.
+ En Unix-egenskap för tidsstämpel i millisekunder måste finnas i IoT-navmeddelandet.

## <a name="configure-the-production-delays-scenario-in-supply-chain-management"></a>Konfigurera scenariot **Tillverkningsfördröjning** i Supply Chain Management

I scenariot **Tillverkningsfördröjningar** genereras ett meddelande om tillverkningsgenomflödet sjunker under ett visst tröskelvärde. I det här scenariot skickas en **KomponentUt**-signal till IoT-navet för varje objekt som tillverkas. I Supply Chain Management beräknas orderförseningen baserat på hur lång tid tillverkningsordern är schemalagd att köras, hur många artiklar som ska tillverkas, hur länge jobbet har körts och hur många **KomponentUt**-signaler som tas emot. Ett fördröjningsmeddelande genereras om antalet **KomopnentUt**-signaler för jobbet sjunker under tröskelvärdet för det förväntade värdet.

Scenariot har följande beroenden:

+ En tillverkningsorder måste köras på en mappad dator för att en notifiering ska utlösas.
+ En signal som representerar en mappad datorns signal för komponentstopp måste skickas till IoT-navet med ett unikt egenskapsnamn.
+ En Unix-egenskap för tidsstämpel i millisekunder måste finnas i IoT-navmeddelandet.

## <a name="how-to-disable-a-scenario"></a>Inaktivera ett scenario

Följ dessa steg om du vill inatkivera ett scenario:

1. I Supply Chain Management navigerar du till **Tillverkningsstyrning \> Inställningar \> IoT-information \> Scenariohantering**.
2. Klicka på **Konfigurera** i scenariot.
3. Klicka på **Nästa** för att komma till den sista fliken i guiden.
4. Inaktivera scenariot genom att förflytta skjutreglaget.
