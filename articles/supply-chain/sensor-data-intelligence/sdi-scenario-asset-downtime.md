---
title: Tillgångens stilleståndsscenario
description: I den här artikeln beskrivs scenario stilleståndstid för tillgångar, som du kan använda för att använda sensordata för att övervaka tillgängligheten för dina tillgångar.
author: johanhoffmann
ms.date: 09/02/2022
ms.topic: article
ms.search.form: IoTIntCoreScenarioManagement, IoTIntCoreScenarioConfigurationWizardV2, EntAssetObjectProductionStop
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-09-02
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: 944818557deebed06c02c00fd69de6e8f08bda83
ms.sourcegitcommit: 3d7ae22401b376d2899840b561575e8d5c55658c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/08/2022
ms.locfileid: "9428450"
---
# <a name="the-asset-downtime-scenario"></a>Tillgångens stilleståndsscenario

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

Scenariot för tillgänglighetstid genererar en post för underhållsstopp om ingen signal tas emot från en maskin inom en angiven tidströskel sedan den senaste signalen togs emot. Scenariot kräver att du passar din maskin med en sensor som periodiskt skickar en signal till din Azure IoT Hub medan maskinen används, men som inte skickar någon signal när maskinen inte används.

## <a name="set-up-the-asset-downtime-scenario"></a>Ange scenario stilleståndstid för tillgång

Gör på följande sätt för att konfigurera scenariot *tillgångsdriftstopp* i Supply Chain Management.

1. Gå till **tillgångsunderhåll \> inställning \> Sensor Data Intelligence \> scenarier** för att du öppna sidan **scenarier**.
2. I scenarierutan **stilleståndstid för tillgång**, välj **Konfigurera** för att öppna installationsguiden för detta scenario.
3. På sidan **Sensorer** väljer du **Ny** för att lägga till en sensor i rutnätet. Ange sedan följande fält för den:

    - **Sensor-ID** – Ange ID:t för den sensor du använder. (Om du använder Raspberry PI Azure IoT Online Simulator och har ställt in den enligt beskrivningen i [Ställ in en simulerad sensor för testning](sdi-set-up-simulated-sensor.md), ange *AssetDownTime*.)
    - **Sensorbeskrivning** – Ange en beskrivning av sensorn.

4. Upprepa föregående steg för varje ytterligare sensor som du vill lägga till nu. Du kan komma tillbaka och lägga till fler som är anslutna när som helst.
5. Välj **Nästa**.
6. På sidan **Affärspostmappning** i avsnittet **Sensorer**, välj posten för en av sensorerna som du just lagt till.
7. I avsnittet **Affärspostmappning** section, select **New** to add a row to the grid.
8. På den nya raden, ställ in fältet **Affärspost** till resursen som du använder den valda sensorn för att övervaka. (Om du använder demodata väljer du *AK-101, luftkniv för rad 1*.)
9. Välj **Nästa**.
10. På sidan för **Tröskel för tillgångsdriftstopp** för tillgångar definierar du hur länge efter den senaste signal som systemet ska vänta innan ett meddelande om tillgänglighetsaviseringar skickas. Det finns två sätt att definiera tröskeln:

    - **Standardtröskel (minuter)** – Ange det här fältet om du vill definiera standardtröskeln. Det här värdet gäller för alla resurser där fältet **Meddelandetröskel (minuter)** är inställt på två minuter eller mindre. Minsta värdet är *2* (minuter).
    - **Tröskelvärde som avgör om datorn inte svarar (minuter)** – För varje resurs i rutnätet som du inte vill använda standardtröskeln för anger du ett åsidosättningsvärde i det här fältet. Resurser som har ett tröskelvärde på två minuter eller mindre använder inställningen **Standardtröskel (minuter)** istället.
11. Välj **Nästa**.
12. På sidan **Aktivera sensorer** i rutnätet, välj den sensor du ställde in och välj sedan **Aktivera**. För varje aktiverad sensor i rutnätet visas en bockmarkering i kolumnen **Aktiv**.
13. Välj **Slutför**.

## <a name="work-with-the-asset-downtime-scenario"></a>Arbeta med stilleståndstid för tillgång

Om ingen sensor signal tas emot från en tillgång inom den tröskel som anges i scenarioskonfigurationen, skapas en post för underhållstid för tillgången. Chefer bör regelbundet granska nedtidsposterna (till exempel en gång under varje arbetsskift) och tillämpa lämpliga orsakskoder och sluttider för varje registrering av drifttid. Följ de här stegen när du vill visa poster för underhåll av drifttid för en tillgång:

1. Gå till **Tillgångshantering > Tillgångar > Alla tillgångar**.
2. Sök reda på och välj den tillgång som du vill granska. (Om du använder med demodata väljer du *AK 101*.)
3. I åtgärdsfönstret, fliken **Tillgång** och från gruppen **Arbetsorder** välj **Underhållsstopp** för att öppna sidan för underhållsavbrottstid för den valda tillgången.
