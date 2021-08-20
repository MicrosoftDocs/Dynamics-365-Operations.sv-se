---
title: Scenarioinställningar för IoT-information
description: I det här avsnittet beskrivs hur du konfigurerar scenarier för IoT-intelligens i Microsoft Dynamics 365 Supply Chain Management.
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
ms.openlocfilehash: 9a45ed57f1fb5e4d508c30b2f3a83dafacfb7dd870701a8f519bbc1e807ed982
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6736803"
---
# <a name="scenario-setup-for-iot-intelligence"></a>Scenarioinställningar för IoT-information

[!include [banner](../../includes/banner.md)]

I det här avsnittet beskrivs hur du konfigurerar scenarier för IoT-intelligens i Microsoft Dynamics 365 Supply Chain Management. Innan du kan ställa in scenarier måste du [konfigurera Microsoft Dynamics Lifecycle Services (LCS)](iot-lcs-setup.md).

I det här avsnittet konfigurerar du scenariot **Driftstopp (utrustning)** i syfte att generera ett meddelande i Supply Chain Management när en dator slutar att fungera. Ämnet visar också hur du konfigurerar scenariot **produktkvalitet** så att ett meddelande genereras om ett attribut för en artikel ligger utanför ett angivet intervall och hur du konfigurerar scenariot **produktionsfördröjning** så att ett meddelande genereras om produktions dataflödet sjunker under ett tröskelvärde.

## <a name="configure-the-equipment-downtime-scenario-in-supply-chain-management"></a>Konfigurera scenariot Driftstopp (utrustning) i Supply Chain Management

Scenariot **Driftstopp för utrustning** mappar en **PartOut**-signal om komponent ur funktion till ett tröskelvärde för datornotifiering. Datorn övervakas bara när den väljs ut för scenariot och ställs in för **körning** i Supply Chain Management. Om tiden sedan **PartOut**-signalen senast togs emot från maskiner överstiger tröskelvärdet för notifiering, kommer ett meddelande om **datorstopp** att utlösas. Om datorn fortfarande körs kommer meddelandet **datorn körs** att lösas ut när nästa **PartOut**-signal tas emot. Om en dator förblir ur drift i 30 minuter utlöses ett nytt meddelande om **datorstopp**.

Scenariot **Driftstopp (utrustning)** har följande beroenden:

+ En tillverkningsorder måste köras på en mappad dator för att en notifiering ska utlösas.
+ En signal som representerar en mappad datorns signal för **komponentstopp** måste skickas till IoT-hubben med ett unikt egenskapsnamn.
+ En egenskap för UNIX **tidstämpel** där värdet uttrycks i millisekunder (MS), måste finnas i meddelandet i Azure IoT-hubben.

Följ dessa steg för att konfigurera scenariot.

1. Logga in på Supply Chain Management.
2. Aktivera funktionsflaggan för IoT-information. Mer information finns i [Översikt för funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).
3. Konfigurera måtten. Mer information finns i [Konfigurera mått](iot-metrics-setup.md#configure-metrics).
4. Gå till **produktionskontroll \> inställning \> IoT-intelligens \> scenariohantering**.
6. På panelen **Driftstopp (utrustning)** välj **konfigurera** för att öppna konfigurationsguiden.

   Första sidan i guiden är **Schemadefinition för utrustningssensor**. På den här sidan är ditt mål att ställa in schemat i Supply Chain Management så att det matchar JSON-formatet (JavaScript Object Notation) för IoT-hubb-meddelandena. Du kan definiera flera meddelandescheman. Mer information finns i [Schemaformat för IoT-hubb-meddelande](iot-schema-format.md). I det här exemplet innehåller meddelandets nyttolasten en batch med meddelanden med detta format.

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

7. Lägg till en rad till tabellen och ange följande värden:

    1. Ange fältet **Schemanamn** som **ID**.
    2. Ange fältet **Schemasökväg** till **/payload\[\*\]/id**.
    3. Ange fältet **Beskrivning** som **Meddelande-ID**.

8. Lägg till en rad till tabellen och ange följande värden:

    1. Ange fältet **Schemanamn** som **Tidsstämpel**.
    2. Ange fältet **Schemasökväg** till **/payload\[\*\]/timestamp**.
    3. Ange fältet **Beskrivning** som **Tidsstämpel för meddelande**.

9. Lägg till en rad till tabellen och ange följande värden:

    1. Ange fältet **Schemanamn** som **Värde**.
    2. Ange fältet **Schemasökväg** till **/payload\[\*\]/value**.
    3. Ange fältet **Beskrivning** som **Meddelandevärde**.

    > [!NOTE]
    > Du behöver inte definiera alla egenskaper i meddelandet. Definiera endast de egenskaper som du behöver. I föregående steg har du inte skapat någon rad för **Rottidsstämpel**. Sökvägen för **Rottidsstämpel** skulle bli **/timestamp**.

10. Klicka på **Nästa** för att gå till sidan **Schemaöversikt för utrustningssensor**.
11. I raden för **Resurs-ID för utrustning** anger du fältet **schemanamnet** som **ID**.
12. I raden för **UTC-tid** anger du fältet **schemanamnet** som **Tidsstämpel**.
13. I raden för **Komponentgenererad signal** anger du fältet **schemanamnet** som **Värde**.
14. Klicka på **Nästa** för sidan **ID-konfiguration för utrustningsresurs**.
15. Följ dessa steg för att mappa värdena i IoT-hubbens meddelandevärden till resurserna för Supply Chain Management:

    1. I tabellen **Signaldatavärden** lägg till en ny rad. I fältet **Värde** ange **IoTInt.Machine1225.PartOut**. Detta värde kommer från JSON **id**-egenskapen i IoT-hubb-meddelande.
    2. Välj **Spara**.
    3. I registret **Mappning av affärspost** klickar du på **Ny**. Standardvärdet för **Affärsposttyp** fylls i automatiskt, och du behöver inte ändra det.
    4. I fältet **Affärspost** väljer du den Supply Chain Management-datorresurs som detta signalvärde skickas ifrån.
    5. Välj **Spara**.
    6. Upprepa stegen och lägg till en ny mappning för affärspost för **Machine1226**. Du kan mappa flera signaldatavärden till en enda post i Supply Chain Management.

16. Använd kolumnen **Vald** för att välja vilka datorer som ska bearbetas. Du behöver inte definiera alla signalvärden och du behöver inte välja alla datorer.
17. Klicka på **Nästa** om du vill gå till sidan för den **komponentproducerade signalkonfigurationen**.
18. I registret **Signaldatavärden** lägger du till en rad och anger fältet **Värde** som **True**. Detta värde kommer från JSON **värde**-egenskapen i IoT-hubb-meddelande. Du kan lägga till så många värden som du behöver i scenariot.
19. Välj **Spara**.
20. Klicka på **Nästa** för att gå till sidan **Tröskelvärde för driftstopp (utrustning)**. De angivna datorerna är de som tidigare har mappats till signalvärden. I det här steget definierar du ett tröskelvärde för att fastställa om en dator inte är tillgänglig. Om du till exempel ställer in tröskelvärdet på **10**, Supply Chain Management genererar ett meddelande om det inte finns någon **KomponentUt**-signal från en maskin på 10 minuter.
21. Klicka på **Nästa** för att öppna sidan **Aktivera scenario**. Ange alternativet för att aktivera scenariot.
22. Välj **Slutför**.

Scenariokonfigurationen har slutförts. IoT-information kommer automatiskt att börja bearbeta IoT-navmeddelandena.

## <a name="configure-the-product-quality-scenario-in-supply-chain-management"></a>Konfigurera scenariot Produktkvalitet i Supply Chain Management

Scenariot **Produktkvalitet** genererar ett meddelande om ett attribut för en artikel ligger utanför ett angivet intervall. En sensor kan t.ex. skicka vikten för varje enskilt objekt till IoT-hubb. Om ett objekt är för tungt eller för lätt genereras ett meddelande i Supply Chain Management.

Scenariot **Produktkvalitet** har följande beroenden:

+ En varning kan endast utlösas om en produktionsorder körs på en mappad maskin och producerar en produkt som har ett mappat batchattribut.
+ En signal som representerar batchattributet måste skickas till IoT-hubben med ett unikt egenskapsnamn måste inkluderas.
+ En egenskap för UNIX **tidstämpel** där värdet uttrycks i millisekunder måste finnas i meddelandet i IoT-hubb.

## <a name="configure-the-production-delays-scenario-in-supply-chain-management"></a>Konfigurera scenariot Tillverkningsfördröjning i Supply Chain Management

I scenariot **Tillverkningsfördröjningar** genereras ett meddelande om tillverkningsgenomflödet sjunker under ett visst tröskelvärde. I det här scenariot skickas en **KomponentUt**-signal till IoT-hubben för varje objekt som tillverkas. I Supply Chain Management beräknas order förseningen utifrån den tid som tillverkningsordern är schemalagd att köras, antalet artiklar som ska produceras, hur lång tid jobbet har körts och antalet **KomponentUt**-signaler som tas emot. Ett fördröjningsmeddelande genereras om antalet **KomponentUt**-signaler för jobbet sjunker under tröskelvärdet för det förväntade värdet.

Scenariot **Tillverkningsfördröjningar** har följande beroenden:

+ En tillverkningsorder måste köras på en mappad dator för att en notifiering ska utlösas.
+ En signal som representerar en mappad datorns signal för **komponentstopp** måste skickas till Azure IoT-hubben med ett unikt egenskapsnamn.
+ En egenskap för UNIX **tidstämpel** där värdet uttrycks i millisekunder måste finnas i meddelandet i IoT-hubb.

## <a name="disable-a-scenario"></a>Inaktivera ett scenario

Följ dessa steg om du vill inaktivera ett scenario.

1. I Supply Chain Management navigerar du till **Tillverkningsstyrning \> Inställningar \> IoT-information \> Scenariohantering**.
2. På panel för scenariot väljer du **Konfigurera**.
3. Klicka på **Nästa** för att öppna sidan för den senaste guiden.
4. Ange alternativet för att inaktivera scenariot.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]