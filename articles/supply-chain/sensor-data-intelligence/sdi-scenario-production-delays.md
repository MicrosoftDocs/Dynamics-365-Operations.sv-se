---
title: Scenariot för produktionsförseningar
description: Denna artikel beskriver produktionen genereras ett meddelande om tillverkningsgenomflödet sjunker under ett visst tröskelvärde.
author: johanhoffmann
ms.date: 09/02/2022
ms.topic: article
ms.search.form: IoTIntCoreScenarioManagement, IoTIntCoreScenarioConfigurationWizardV2, IoTIntMfgResourceStatusConfiguration, IoTIntMfgResourceStatus
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-09-02
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: 073762581d84646ba12b570e57327b7cab8efd3b
ms.sourcegitcommit: 3d7ae22401b376d2899840b561575e8d5c55658c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/08/2022
ms.locfileid: "9428419"
---
# <a name="the-production-delays-scenario"></a>Scenariot för produktionsförseningar

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

I scenariot *Tillverkningsfördröjningar* genereras ett meddelande om tillverkningsgenomflödet sjunker under ett visst tröskelvärde. I det här scenariot *part-out* signal skickas till Microsoft Azure IoT Hub för varje vara som produceras. I Dynamics 365 Supply Chain Management, orderfördröjningen beräknas baserat på hur lång tid som produktionsordern är schemalagd att köras, antalet artiklar som ska produceras, hur lång tid jobbet har körts och antalet *del ut* signaler som tas emot. Ett fördröjningsmeddelande genereras om antalet *del ut*-signaler för jobbet sjunker under tröskelvärdet för det förväntade värdet.

## <a name="scenario-dependencies"></a>Scenarioberoenden

Scenariot *Tillverkningsfördröjningar* har följande beroenden:

- En tillverkningsorder måste köras på en mappad dator för att en notifiering ska utlösas.
- En signal som representerar en mappad datorns signal för *del ut* måste skickas till IoT-hubben med ett unikt egenskapsnamn.
- En egenskap för UNIX tidstämpel där värdet uttrycks i millisekunder (MS), måste finnas i meddelandet i Azure IoT-hubben.

## <a name="prepare-demo-data-for-the-product-delays-scenario"></a>Förbered demodata för scenariot med produktförseningar

Om du vill använda ett demosystem för att testa *produktionsförseningar* ska du använda ett system [demodata](../../fin-ops-core/fin-ops/get-started/demo-data.md) installeras, välj *USMF* juridisk person (företag) och förbered ytterligare demodata enligt beskrivningen i detta avsnitt. Om du använder ditt eget konto och dina egna data kan du hoppa över det här avsnittet.

### <a name="set-up-sensor-simulator"></a>Ställ in sensorsimulator

Om du vill prova detta scenario utan att använda en fysisk sensor kan du ställa in en simulator för att generera de signaler som krävs. Mer information finns i [Ställ in en simulerad sensor för testning](sdi-set-up-simulated-sensor.md).

### <a name="verify-that-resource-3118-is-used-for-product-p0111"></a>Kontrollera att resurs 3118 används för produkt P0111

En tillverkningsorder tidsplanerades och frisläpps. Därför frisläpps ett produktionsjobb till resurs *3118* (*Skum skärmaskin*). Följ dessa steg för att kontrollera att resurs *3118* används för produkt *P0111* i dina demodata.

1. Gå till **Produktinformationshantering \> Produkter \> Frisläppta produkter**.
1. Hitta och välj där fältet **Artikelnummer** är inställt på *P0111*.
1. I Åtgärdsfönstret, på fliken **Konstruera**, i gruppen **Visa**, markerar du **Rutt**.
1. På fliken **Rutt** på fliken **Översikt** längst ned på sidan, välj raden där **Oper.nr.** är inställt på *30*.
1. På fliken **Resursbehov** längst ned på sidan kontrollerar du att resurs *3118* (*Skumskärmaskin*) är kopplad till operationen.

### <a name="create-and-release-a-production-order-for-product-p0111"></a>Skapa och frisläppa en produktionsorder för produkten P0111

Följ dessa steg om du vill skapa och frisläppa en tillverkningsorder för produkt *P0111*.

1. Gå till **Produktionskontroll \> Produktionsorder \> Alla produktionsorder**.
1. På sidan **Alla tillverkningsorder** i åtgärdsfönstret **Ny batchorder**.
1. I dialogrutan **Skapa batch** ange följande värden:

    - **Artikelnummer:** *P0111*
    - **Kvantitet:** *10*

1. Välj **Skapa** för att skapa ordern och återgå till sidan **alla produktionsorder**.
1. Använd fältet **Filter** för att söka efter tillverkningsorder där fältet **Artikelnummer** är inställt på *P0111*. Hitta och välj sedan den produktionsorder som du just skapade.
1. I Åtgärdsfönstret, på fliken **Produktionsorder**, i gruppen **Process**, markerar du **Uppskatta**.
1. I dialogrutan **Uppskatta**, välj **OK** för att köra uppskattningen.
1. I Åtgärdsfönstret, på fliken **Produktionsorder**, i gruppen **Process**, markerar du **Frisläpp**.
1. Observera numret på batchordern som du just skapade i dialogrutan **Frisläpp**.
1. Välj **OK** för att frisläppa ordern.

### <a name="configure-the-production-floor-execution-interface"></a>Konfigurera körningsgränssnittet för produktionsgolvet

Om du inte redan har gjort det ska du konfigurera gränssnittet för produktionsgolvkörning så att det visar jobb som tilldelats resurs *3118* (*Skumskärmaskin*). Instruktioner finns i följande avsnitt:

- [Konfigurera körningsgränssnittet för produktionsgolvet](sdi-scenario-equipment-downtime.md#config-pfe)
- [Aktivera sökalternativet för produktionsgolvets körningsgränssnitt](sdi-scenario-equipment-downtime.md#enable-pfe-search)

### <a name="start-the-first-job-in-the-batch-order"></a>Starta det första jobbet i batchordern

Följ dessa steg för att starta det första jobbet i batchordern.

1. Gå till **Produktionskontroll \> Tillverkningskörning \> Körningsgränssnittet för produktionsgolvet**.
1. I fältet **ID-bricka** ange *123*. Välj sedan **Logga in**.
1. Om du tillfrågas om en frånvaroorsak väljer du ett av korten för frånvaro och väljer **OK**.
1. I fältet **sök** anger du det batchordernummer som du tidigare gjorde en notering om. Välj sedan nyckeln **Retur**.
1. Välj ordern och klicka sedan på **Starta ett jobb**.
1. I dialogrutan **Starta jobb** välj **Starta**.

## <a name="set-up-the-production-delays-scenario"></a>Konfigurera scenariot för produktionsförseningar

Gör på följande sätt för att konfigurera scenariot *produktionsförseningar* i Supply Chain Management.

1. Gå till **produktionskontroll \> inställning \> Sensor Data Intelligence \> scenarier**.
1. I scenarierutan **produktionsförseningar**, välj **Konfigurera** för att öppna installationsguiden för detta scenario.
1. På sidan **Sensorer** väljer du **Ny** för att lägga till en sensor i rutnätet. Ange sedan följande fält för den:

    - **Sensor-ID** – Ange ID:t för den sensor du använder. (Om du använder Raspberry PI Azure IoT Online Simulator och har ställt in den enligt beskrivningen i [Ställ in en simulerad sensor för testning](sdi-set-up-simulated-sensor.md), ange *ProductionDelay*.)
    - **Sensorbeskrivning** – Ange en beskrivning av sensorn.

1. Upprepa föregående steg för varje ytterligare sensor som du vill lägga till nu. Du kan komma tillbaka och lägga till fler som är anslutna när som helst.
1. Välj **Nästa**.
1. På sidan **Affärspostmappning** i avsnittet **Sensorer**, välj posten för en av sensorerna som du just lagt till.
1. I avsnittet **Affärspostmappning** section, select **New** to add a row to the grid.
1. På den nya raden, ställ in **Affärspost** till resursen som du använder den valda sensorn för att övervaka. (Om du använder de demodata som du skapade tidigare i den här artikeln ställer du in den på *3118, skumskärmaskin*.)
1. Välj **Nästa**.
1. På sidan **Tröskelvärde för produktionsfördröjning**, om du använder de demodata som du skapade tidigare i den här artikeln, följer du dessa steg:

    1. Markera kolumnrubriken **Artikelrelation** om du vill öppna en dialogruta med sökfiltren för kolumnen. Ange *P0111* i sökrutan och välj sedan **Apply**.
    2. Välj raden där fältet **Operation** är inställt på *Trimma/klippa*. Ange fältet **Aviseringströskel för försening (%)** till den tröskel (i procent) som ett meddelande ska skickas till.

1. Välj **Nästa**.
1. På sidan **Aktivera sensorer** i rutnätet, välj den sensor du lade till och välj sedan **Aktivera**. För varje aktiverad sensor i rutnätet visas en bockmarkering i kolumnen **Aktiv**.
1. Välj **Slutför**.

## <a name="work-with-the-production-delays-scenario"></a>Arbeta med scenariot för produktionsförseningar

### <a name="view-production-delay-data-on-the-resource-status-page"></a>Visa data för produktionsfördröjning på sidan Resursstatus

På sidan **Resursstatus** kan arbetsledare övervaka en tidslinje för seder som tas emot från den sensor som mappas till varje maskinresurs. Följ dessa steg för att konfigurera tidslinjen.

1. Gå till **Produktionskontroll \> Tillverkningskörning \> Resursstatus**.
1. I dialogrutan **Konfigurera** anger du följande fält:

    - **Resurs** – Välj de resurser som du vill övervaka. (Om du arbetar med demodata väljer du *3118*.)
    - **Tidsserie 1** – Välj posten (metrisk nyckel) som har följande format för sitt namn: *ProductionJobDelayed:ActualQuantity:&lt;JobId&gt;*
    - **Visningsnamn** – Ange ut *signal för del ut*.
