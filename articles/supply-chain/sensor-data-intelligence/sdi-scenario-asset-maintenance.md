---
title: Underhållsscenario för tillgång
description: Den här artikeln beskriver scenariot för underhåll av tillgångar, som gör att du kan använda sensordata för att skapa räknarposter som spårar användning av en maskintillgång.
author: johanhoffmann
ms.date: 09/02/2022
ms.topic: article
ms.search.form: IoTIntCoreScenarioManagement, IoTIntCoreScenarioConfigurationWizardV2, EntAssetCounter
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-09-02
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: 2d103406118be4385177b678de424df12af69c2e
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/18/2022
ms.locfileid: "9689411"
---
# <a name="the-asset-maintenance-scenario"></a>Underhållsscenario för tillgång

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!-- KFM: Preview until further notice -->

Med *scenariot för underhåll* av tillgångar kan du använda sensordata för att skapa räknareposter. Motposter spårar användningen av en maskintillgång och används som indata för att generera underhållsplanen för maskintillgångar.

## <a name="video-instructions"></a>Videoanvisningar

Följande video visar hur du ställer in och försöker med ett scenario för tillgångsunderhåll med hjälp av standard [demodata](../../fin-ops-core/fin-ops/get-started/demo-data.md). De återstående avsnitten i den här artikeln tillhandahåller samma instruktioner i ett textbaserat format.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE58aRW]

## <a name="prepare-demo-data-for-the-asset-maintenance-scenario"></a>Förbered demodata för scenariot för underhåll av tillgångar

Om du vill använda ett demosystem för att testa *tillgångsunderhåll* ska du använda ett system [demodata](../../fin-ops-core/fin-ops/get-started/demo-data.md) installeras, välj *USMF* juridisk person (företag) och förbered ytterligare demodata enligt beskrivningen i detta avsnitt. Om du använder ditt eget konto och dina egna data kan du hoppa över det här avsnittet.

I det här avsnittet ställer du in *AK-101, luftkniv* tillgång i demodata som ett exempel. Du kommer då att se hur det kommande underhållsarbetet kan förutsägas baserat på sensoren som mäter antalet timmar som flyget har körts. Du ställer också in en underhållsplan där flyget måste underhållas var 10 000:e timme.

### <a name="set-up-a-sensor-simulator"></a>Ställ in sensorsimulator

Om du vill prova detta scenario utan att använda en fysisk sensor kan du ställa in en simulator för att generera de signaler som krävs. Mer information finns i [Ställ in en simulerad sensor för testning](sdi-set-up-simulated-sensor.md).

### <a name="create-an-asset-counter-to-track-production-hours"></a>Skapa en tillgångsräknare för att spåra produktionstimmar

Följ dessa steg för att skapa en tillgångsräknare för att spåra produktionstimmar.

1. Gå till **Tillgångshantering \> Konfigurera \> Tillgångstyper \> Räknare**.
1. I åtgärdsfönstret, välj **Ny** för att skapa en räknare.
1. I rubriken anger du följande värden:

    - **Räknare:** *ProductionHr*
    - **Namn:** *Produktionstimmar*

1. Ange följande värden på snabbfliken **Allmänt**:

    - **Enhet:** *hr*
    - **Uppdatera:** *Manell*
    - **Totalt aggregerat:** *Sum*

1. På snabbfliken **Tillgångstyper** klickar du på **Lägg till rad**.
1. På den nya raden ställer du in fältet **Tillgångstyp** till *Luftkniv*.

### <a name="create-a-maintenance-plan-for-the-asset"></a>Skapa en underhållsplan för tillgången

Följ dessa steg för att skapa en underhållsplan för tillgången.

1. Gå till **Tillgångshantering \> Inställning \> Förebyggande underhåll \> Underhållsplan**.
1. I åtgärdsfönstret, välj **Ny** för att skapa en ny underhållsplan.
1. I rubriken anger du följande värden:

    - **Underhållsplan:** *AirKnife*
    - **Namn:** *Planera för luftknivar*

1. Ange följande värden på snabbfliken **Detaljer**:

    - **Plandatum:** Ange dagens datum.
    - **Aktiv:** *Ja*

1. På snabbfliken **Rader** välj **Lägg till rad för tillgångsräknare** för att lägga till en rad i rutnätet. Ange följande värden för den:

    - **Beskrivning av arbetsorder:** *Underhåll av flygunderhåll*
    - **Typ av underhållsjobb:** *Förebyggande*
    - **Intervalltyp:** *Upprepas från senaste arbetsorder*
    - **Periodfrekvens:** *10000*
    - **Räknare:** *ProductionHr*

## <a name="set-up-the-asset-maintenance-scenario"></a>Ange underhållsscenario för tillgång

Gör på följande sätt för att konfigurera scenariot *tillgångsunderhåll* i Supply Chain Management.

1. Gå till **tillgångsunderhåll \> inställning \> Sensor Data Intelligence \> scenarier**.
1. I scenarierutan **tillgångsunderhåll**, välj **Konfigurera** för att öppna installationsguiden för detta scenario.
1. På sidan **Sensorer** väljer du **Ny** för att lägga till en sensor i rutnätet. Ange sedan följande fält för den:

    - **Sensor-ID** – Ange ID:t för den sensor du använder. (Om du använder Raspberry PI Azure IoT Online Simulator och har ställt in den enligt beskrivningen i [Ställ in en simulerad sensor för testning](sdi-set-up-simulated-sensor.md), ange *AssetMaintenance*.)
    - **Sensorbeskrivning** – Ange en beskrivning av sensorn.

1. Upprepa föregående steg för varje ytterligare sensor som du vill lägga till nu. Du kan komma tillbaka och lägga till fler som är anslutna när som helst.
1. Välj **Nästa**.
1. På sidan **Affärspostmappning** i avsnittet **Sensorer**, välj posten för en av sensorerna som du just lagt till.
1. I avsnittet **Affärspostmappning** section, select **New** to add a row to the grid.
1. På den nya raden ska fältet **Affärsposttyp** automatiskt ställas in *Assets(EntAssetObjectTable)*. Ställ in fältet **Affärspost** till resursen som du använder den valda sensorn för att övervaka. (Om du använder de demodata som du skapade tidigare i den här artikeln ställer du in den på *AK-101, AK-101 luftkniv för rad 1*.)
1. Omedelbart efter att du valt en affärsposttyp för raden som du lade till i det föregående steget, läggs en andra rad automatiskt till i rutnätet. På den här raden ska fältet **Affärsposttyp** ställas in på *Counters(EntAssetCounterType)*. Ställ in **affärspostfältet** till den tillgångsräknare som du uppdaterar baserat på den valda räknaren. (Om du använder de demodata som du skapade tidigare i den här artikeln ställer du in den på *ProductionHr, Produktionstimmar*.)
1. Välj **Nästa**.
1. På sidan **Aktivera sensorer** i rutnätet, välj den sensor du lade till och välj sedan **Aktivera**. För varje aktiverad sensor i rutnätet visas en bockmarkering i kolumnen **Aktiv**.
1. Välj **Slutför**.

## <a name="work-with-the-asset-maintenance-scenario"></a>Arbeta med underhållsscenario för tillgång

### <a name="view-counter-values"></a>Visa räknarens värden

När data har förberetts och scenariot för *tillgångsunderhåll* har konfigurerats och aktiverats, kan du se hur poster för en tillgångsräknare infogas baserat på sensordata.

1. Gå till **Tillgångshantering \> Tillgångar \> Alla tillgångar**.
1. Sök reda på och välj den tillgång som du vill granska. (Om du använder de demodata som du skapade tidigare i den här artikeln väljer du *AK-101*.)
1. I åtgärdsfönstret, på fliken **Tillgång** i gruppen **Förebyggande**, välj **Räknare** för att öppna sidan för motposter för tillgång *AK-101*.

> [!NOTE]
> Räknarposterna konfigureras som standard till att infogas var tredje timme, vilket innebär att sensordata aggregeras med det intervallet. Du kan ändra intervallet genom att redigera frågan i komponenten Azure Stream Analytics.

### <a name="generate-maintenance-work-orders"></a>Generera underhållsarbetsorder

När du har aktivera scenariot för *tillgångsunderhåll* och ställt in underhållsplanen, kan du köra underhållsplanen för att generera arbetsorder för underhåll. Mer information om hur du arbetar med förebyggande underhåll finns i [Översikt över förebyggande underhåll](../asset-management/preventive-and-reactive-maintenance/preventive-maintenance-overview.md).
