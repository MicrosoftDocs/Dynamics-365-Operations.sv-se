---
title: Maskinens statusscenario
description: I den här artikeln beskrivs maskinstatusscenariot, som du kan använda för att använda sensordata för att övervaka tillgängligheten för din utrustning.
author: johanhoffmann
ms.date: 09/02/2022
ms.topic: article
ms.search.form: IoTIntCoreScenarioManagement, IoTIntCoreNotification, IoTIntMfgResourceStatusConfiguration, IoTIntMfgResourceStatus
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2022-09-02
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: 30fdfb898384aea4c1f8cb2f36f9e104cd316f90
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/18/2022
ms.locfileid: "9689650"
---
# <a name="the-machine-status-scenario"></a>Maskinens statusscenario

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!-- KFM: Preview until further notice -->

*Maskinstatus* scenariot, som du kan använda för att använda sensordata för att övervaka tillgängligheten för din utrustning. Om du ställer in en sensor som skickar en signal när ett produktionsjobb på en maskinresurs producerar utleverans, men ingen sensor signal tas emot inom ett angivet intervall, visas ett meddelande på administratörsinstrumentpanelen.

## <a name="scenario-dependencies"></a>Scenarioberoenden

Scenariot *maskinstatus* har följande beroenden:

- Ett meddelande kan bara utlösas om ett produktionsjobb pågår på en mappad maskin.
- En signal som representerar en *del ut* signal måste skickas till IoT-hubb.

## <a name="prepare-demo-data-for-the-machine-status-scenario"></a>Förbered demodata för scenariot med maskinstatus

Om du vill använda ett demosystem för att testa *maskinstatus* ska du använda ett system [demodata](../../fin-ops-core/fin-ops/get-started/demo-data.md) installeras, välj *USMF* juridisk person (företag) och förbered ytterligare demodata enligt beskrivningen i detta avsnitt. Om du använder ditt eget konto och dina egna data kan du hoppa över det här avsnittet.

### <a name="set-up-a-sensor-simulator"></a>Ställ in sensorsimulator

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

### <a name="configure-the-production-floor-execution-interface"></a><a name="config-pfe"></a>Konfigurera körningsgränssnittet för produktionsgolvet

Du använder gränssnittet för produktionsgolvskörning när du startar jobbet som planerades och frisläppts för artikelnummer *P0111* i föregående avsnitt. Följ dessa steg för att konfigurera gränssnittet för produktionsgolvet.

1. Gå till **Produktionskontroll \> Tillverkningskörning \> Körningsgränssnittet för produktionsgolvet**.
1. Om du inte tidigare har ställt in gränssnittet visas en inloggningssida. Ange dina autentiseringsuppgifter.
1. På välkomstsidan väljer du **Konfigurera** så att guiden **Konfigurera enhet** öppnas.
1. På sidan **Konfigurera enhet - Steg 1 - Välj konfiguration** välj *Standard* konfiguration.
1. Välj **Nästa**.
1. På sidan **Konfigurera enhet - Steg 2 - Definiera sidan produktionsgolv** ange fältet **Resurs** till *3118*.
1. Välj **OK**.

### <a name="enable-the-search-option-in-the-production-floor-execution-interface"></a><a name="enable-pfe-search"></a>Aktivera sökalternativet för produktionsgolvets körningsgränssnitt

Gör det enklare att hitta produktionsjobbet för tillverkningsordern som frisläppdes tidigare genom att följa dessa steg för att aktivera sökalternativet i gränssnittet för produktionsgolvskörning.

1. Gå till **Produktionskontroll \> Inställningar \> Tillverkningskörning \> Konfigurera körningsgränssnittet för produktionsgolvet**.
1. Välj *Standard* konfiguration.
1. I åtgärdsfönstret väljer du **Redigera**.
1. På snabbfliken **allmänt** anger du alternativet **Aktivera sökning** till *Ja*.
1. Stäng sidan.

### <a name="start-the-first-job-in-the-batch-order"></a>Starta det första jobbet i batchordern

Följ de här stegen för att starta det jobb som har tidsplanerats för resurs *3118*.

1. Gå till **Produktionskontroll \> Tillverkningskörning \> Körningsgränssnittet för produktionsgolvet**.
1. I fältet **ID-bricka** ange *123*. Välj sedan **Logga in**.
1. Om du tillfrågas om en frånvaroorsak väljer du ett av korten för frånvaro och väljer **OK**.
1. I fältet **sök** anger du det batchordernummer som du tidigare gjorde en notering om. Välj sedan nyckeln **Retur**.
1. Välj ordern och klicka sedan på **Starta ett jobb**.
1. I dialogrutan **Starta jobb** välj **Starta**.

## <a name="set-up-the-machine-status-scenario"></a>Konfigurera maskinens statusscenario

Gör på följande sätt för att konfigurera scenariot *maskinstatus* i Supply Chain Management.

1. Gå till **produktionskontroll \> inställning \> Sensor Data Intelligence \> scenarier**.
1. I scenarierutan **maskinstatus**, välj **Konfigurera** för att öppna installationsguiden för detta scenario.
1. På sidan **Sensorer** väljer du **Ny** för att lägga till en sensor i rutnätet. Ange sedan följande fält för den:

    - **Sensor-ID** – Ange ID:t för den sensor du använder. (Om du använder Raspberry PI Azure IoT Online Simulator och har ställt in den enligt beskrivningen i [Ställ in en simulerad sensor för testning](sdi-set-up-simulated-sensor.md), ange *MachineStatus*.)
    - **Sensorbeskrivning** – Ange en beskrivning av sensorn.

1. Upprepa föregående steg för varje ytterligare sensor som du vill lägga till nu. Du kan komma tillbaka och lägga till fler som är anslutna när som helst.
1. Välj **Nästa**.
1. På sidan **Affärspostmappning** i avsnittet **Sensorer**, välj posten för en av sensorerna som du just lagt till.
1. I avsnittet **Affärspostmappning** section, select **New** to add a row to the grid.
1. På den nya raden, ställ in fältet **Affärspost** till resursen som du använder den valda sensorn för att övervaka. (Om du använder de demodata som du skapade tidigare i den här artikeln ställer du in den på *3118, skumskärmaskin*.)
1. Välj **Nästa**.
1. På sidan **Maskinens statuströskel** anger du hur länge efter den senaste *del ut* signal ska skicka ett meddelande om maskinstatus. Det finns två sätt att definiera tröskeln:

    - **Standardtröskel (minuter)** – Ange det här fältet om du vill definiera standardtröskeln. Värdet kommer då att gälla för alla resurser där fältet **Tröskel för att fastställa att maskinen inte svarar (minuter)** är inställd på två minuter eller mindre. Minsta värdet är *2* (minuter).
    - **Tröskelvärde som avgör om datorn inte svarar (minuter)** – För varje resurs i rutnätet som du inte vill använda standardtröskeln för anger du ett åsidosättningsvärde i det här fältet. Resurser som har ett tröskelvärde på två minuter eller mindre använder inställningen **Standardtröskel (minuter)** istället.

    > [!NOTE]
    > Normalt använder du en *del ut* signal för att övervaka maskinstatus. Därför ska du kontrollera att tröskelvärdet för varje maskinresurs är längre än vad som krävs för att varje del ska tillverkas med maskinen.

1. Välj **Nästa**.
1. På sidan **Aktivera sensorer** i rutnätet, välj den sensor du lade till och välj sedan **Aktivera**. För varje aktiverad sensor i rutnätet visas en bockmarkering i kolumnen **Aktiv**.
1. Välj **Slutför**.

## <a name="work-with-the-machine-status-scenario"></a>Arbeta med maskinens statusscenario

När du har installerat systemet för verksamhetsstyrning och konfigurerat scenariot kan du visa händelser för maskinstatus i Supply Chain Management. I det här avsnittet beskrivs var och hur du visar den här informationen.

### <a name="view-machine-status-data-on-the-resource-status-page"></a>Visa maskinstatus data för produktkvalitet på sidan Resursstatus

På sidan **Resursstatus** kan arbetsledare övervaka en tidslinje för den *del ut* signal som tas emot från den sensor som mappas till varje maskinresurs. Följ dessa steg för att konfigurera tidslinjen.

1. Gå till **Produktionskontroll \> Tillverkningskörning \> Resursstatus**.
1. I dialogrutan **Konfigurera** anger du följande fält:

    - **Resurs** – Välj de resurser som du vill övervaka. (Om du arbetar med demodata väljer du *3118*.)
    - **Tidsserie 1** – Välj posten (metrisk nyckel) som har följande format för sitt namn: *MachineReportingStatus:&lt;Sensor&gt;*
    - **Visningsnamn** – Ange ut *signal för del ut*.

I följande bild visas ett exempel på maskinstatusdata på sidan **Resursstatus** under standardoperationer.

![Maskinstatus data för produktkvalitet på sidan Resursstatus under standard operation.](media/sdi-resource-status-downtime-up.png "Maskinstatus data för produktkvalitet på sidan Resursstatus under standard operation")

I följande bild visas ett exempel på maskinstatusdata när drifttid upptäcks.

![Maskinstatusdata på sidan Resursstatus när drifttid upptäcks.](media/sdi-resource-status-downtime-down.png "Maskinstatusdata på sidan Resursstatus när drifttid upptäcks")

### <a name="view-machine-status-on-the-notifications-page"></a>Visa maskinstatus på meddelandena

På sidan **Meddelanden** kan arbetsledare visa de meddelanden som genereras när det har gått för mycket tid sedan mätaren senast levererade en *del ut* signal. Varje meddelande ger en översikt över det produktionsjobb som påverkas av avbrottet samt ger möjlighet att tilldela det berörda jobbet till en annan resurs.

För att öppna sidan **Meddelanden**, gå till **Produktionskontroll \> Förfrågningar och rapporter \> Sensor Data Intelligence \> Meddelanden**.

Illustrationen nedan visar ett exempel på sidan maskinstatus meddelande.

![Exempel på meddelande om maskinstatus.](media/sdi-resource-status-downtime-notification.png "Exempel på meddelande om maskinstatus")
