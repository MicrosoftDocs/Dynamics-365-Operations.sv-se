---
title: Produktkvalitetsscenariot
description: Denna artikel innehåller information om funktionen för scenariot produktkvalitet. I det här scenariot används en sensor för att mäta kvaliteten på en produktbatch och genererar en notifiering om en mätning faller utanför ett definierat tröskelvärde.
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
ms.openlocfilehash: c0f1c57251234921779f67faf61d47cdde119e64
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/18/2022
ms.locfileid: "9690059"
---
# <a name="the-product-quality-scenario"></a>Produktkvalitetsscenariot

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!-- KFM: Preview until further notice -->

I scenariot *produktkvalitet* ställs en sensor in för att mäta kvaliteten på en produktbatch på verkstadsgolvet. Om en mätning ligger utanför ett definierat tröskelvärde för produkten visas ett meddelande på arbetsledarens instrumentpanel. En sensor mäter till exempel produktionen av en livsmedel som kommer från produktionsraden. Om mätningen ligger utanför det tillåtna minimi- eller maxvärdet för mätning av produkten genereras ett meddelande.

## <a name="scenario-dependencies"></a>Scenarioberoenden

Scenariot *Produktkvalitet* har följande beroenden:

- En varning kan endast utlösas om en produktionsorder körs på en mappad maskin och om den maskinen producerar en produkt som har ett mappat batchattribut.
- En signal som representerar batchattributet måste skickas till IoT-hubben med ett unikt egenskapsnamn måste inkluderas.

## <a name="prepare-demo-data-for-the-product-quality-scenario"></a>Förbered demodata för scenariot med produktkvalitet

Om du vill använda ett demosystem för att testa *produktkvalitet* ska du använda ett system [demodata](../../fin-ops-core/fin-ops/get-started/demo-data.md) installeras, välj *USMF* juridisk person (företag) och förbered ytterligare demodata enligt beskrivningen i detta avsnitt. Om du använder ditt eget konto och dina egna data kan du hoppa över det här avsnittet.

I det här avsnittet kommer du att ställa in demodata så att du kan använda släppt produkt *P0111* (*Kompositfodral*) med scenariot *produktkvalitet*. I det här scenariot spårar systemet om ett batchattributvärde som mäts av en sensor ligger utanför det definierade tröskelvärdet för ett batchattribut som är associerat med produkten.

### <a name="set-up-a-sensor-simulator"></a>Ställ in sensorsimulator

Om du vill prova detta scenario utan att använda en fysisk sensor kan du ställa in en simulator för att generera de signaler som krävs. Mer information finns i [Ställ in en simulerad sensor för testning](sdi-set-up-simulated-sensor.md).

### <a name="associate-a-batch-attribute-and-resource-with-product-p0111"></a>Koppla ett batchattribut och en resurs till produkt P0111

Följ dessa anvisningar om du vill koppla ett batchattribut till produkten P *0111* (*Composite Case*) och kontrollera att resurs *3118* (*skumskärmaskin*) används för den.

1. Gå till **Produktinformationshantering \> Produkter \> Frisläppta produkter**.
1. Hitta och välj där fältet **Artikelnummer** är inställt på *P0111*.
1. I åtgärdsfönstret, på fliken **Hantera lager** i gruppen **Batchattribut**, välj **Produktspecifik**.
1. På den **produktspecifika** sidan väljer du **Ny** du vill skapa ett produktspecifikt batchattribut.
1. I rubriken anger du följande fält:

    - **Attributkod** – Välj den mängd attribut som du vill övervaka (*Tabell*, *Grupp* eller *Alla*). Välj *Tabell* i det här scenariot eftersom du alltid kommer att övervaka ett enda attribut.
    - **Attributrelation** – Välj det attribut som du vill använda för *produktkvalitetsscenariot* när du övervakar värdet. I det här exemplet ska du välja *Koncentration*, som är ett attribut som ingår i standarddemodata.

1. På snabbfliken **Värden** i fälten **Minimum** och **Maximum** definiera intervallet av acceptabla värden som attributet måste rapportera för att klara kvalitetskontrollen. Om sensor rapporterar ett värde utanför det här intervallet identifieras det som en kvalitetsbrott i systemet. De andra fälten på den här snabbflikarna är inte relevanta för *produktkvalitet* scenariot. De standardvärden som du för närvarande ser kommer från demodata. Lämna dem sedan som de är och stäng den **produktspecifika** sidan om du vill gå tillbaka till sidan **Frisläppt produktinformation för artikel** *P0111*.
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

## <a name="set-up-the-product-quality-scenario"></a>Ställ in produktkvalitetsscenariot

Gör på följande sätt för att konfigurera scenariot *produktkvalitet* i Supply Chain Management.

1. Gå till **produktionskontroll \> inställning \> Sensor Data Intelligence \> scenarier**.
1. I scenarierutan **produktkvalitet**, välj **Konfigurera** för att öppna installationsguiden för detta scenario.
1. På sidan **Sensorer** väljer du **Ny** för att lägga till en sensor i rutnätet. Ange sedan följande fält för den:

    - **Sensor-ID** – Ange ID:t för den sensor du använder. (Om du använder Raspberry PI Azure IoT Online Simulator och har ställt in den enligt beskrivningen i [Ställ in en simulerad sensor för testning](sdi-set-up-simulated-sensor.md), ange *kvalitet*.)
    - **Sensorbeskrivning** – Ange en beskrivning av sensorn.

1. Upprepa föregående steg för varje ytterligare sensor som du vill lägga till nu. Du kan komma tillbaka och lägga till fler som är anslutna när som helst.
1. Välj **Nästa**.
1. På sidan **Affärspostmappning** i avsnittet **Sensorer**, välj posten för en av sensorerna som du just lagt till.
1. I avsnittet **Affärspostmappning** section, select **New** to add a row to the grid.
1. På den nya raden ska fältet **Affärsposttyp** automatiskt ställas in *Resources(WrkCtrTable)*. Ställ in fältet **Affärspost** till resursen som du använder den valda sensorn för att övervaka. (Om du använder de demodata som du skapade tidigare i den här artikeln ställer du in den på *3118, skumskärmaskin*.)
1. Omedelbart efter att du valt en affärsposttyp för raden som du lade till i det föregående steget, läggs en andra rad automatiskt till i rutnätet. På den här raden ska fältet **Affärsposttyp** ställas in på *Batch attributes(PdsBatchAttrib)*. Ställ in fältet **Affärspost** till batchattribute som du använder den valda sensorn för att övervaka. (Om du använder de demodata som du skapade tidigare i den här artikeln ställer du in den på *Koncentration, Koncentration Procent*.)
1. Välj **Nästa**.
1. På sidan **Aktivera sensorer** i rutnätet, välj den sensor du lade till och välj sedan **Aktivera**. För varje aktiverad sensor i rutnätet visas en bockmarkering i kolumnen **Aktiv**.
1. Välj **Slutför**.

## <a name="work-with-the-product-quality-scenario"></a>Arbeta med produktkvalitetsscenariot

### <a name="view-product-quality-data-on-the-resource-status-page"></a>Visa data för produktkvalitet på sidan Resursstatus

På sidan **Resursstatus** kan arbetsledare övervaka en tidslinje för den produktkvalitetssignal som tas emot från den sensor som mappas till varje maskinresurs. Följ dessa steg för att konfigurera tidslinjen.

1. Gå till **Produktionskontroll \> Tillverkningskörning \> Resursstatus**.
1. I dialogrutan **Konfigurera** anger du följande fält:

    - **Resurs** – Välj de resurser som du vill övervaka. (Om du arbetar med demodata väljer du *3118*.)
    - **Tidsserie 1** – Välj posten (metrisk nyckel) som har följande format för sitt namn: *ProductQuality:&lt;JobId&gt;:&lt;AttributeName&gt;*
    - **Visningsnamn** – Ange *batchattributvärden*.

Följande bild visar ett exempel på produktkvalitetsdata på sidan **Resursstatus** när värdet ligger inom intervallet för godtagbara värden.

![Produktkvalitetsdata på sidan Resursstatus när värdet ligger inom intervallet.](media/sdi-product-quality-in-range.png "Produktkvalitetsdata på sidan Resursstatus när värdet ligger inom intervallet")

I följande bild visas ett exempel på produktkvalitetsdata när ett värde som ligger utanför intervallet upptäcks.

![Produktkvalitetsdata på sidan Resursstatus när värdet ligger utanför intervallet detekteras.](media/sdi-product-quality-out-of-range.png "Produktkvalitetsdata på sidan Resursstatus när värdet ligger utanför intervallet detekteras")

### <a name="view-product-quality-data-on-the-notifications-page"></a>Visa data för produktkvalitet på sidan Meddelanden

På sidan **Meddelanden** kan arbetsledare visa det meddelande som genereras när måtten har angetts för ett batchattributvärde som ligger utanför det definierade tröskelvärdet för batchattributet. Varje meddelande ger en översikt över det produktionsjobb som påverkas av avbrottet samt ger möjlighet att tilldela det berörda jobbet till en annan resurs.

För att öppna sidan **Meddelanden**, gå till **Produktionskontroll \> Förfrågningar och rapporter \> Sensor Data Intelligence \> Meddelanden**.

Illustrationen nedan visar ett exempel på sidan produktkvalitetsmeddelande.

![Exempel på en sida med kvalitetsmeddelande.](media/sdi-product-quality-notification.png "Exempel på en sida med kvalitetsmeddelande")
