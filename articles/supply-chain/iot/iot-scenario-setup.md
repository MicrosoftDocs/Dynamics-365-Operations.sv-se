---
title: Scenarioinställningar för IoT-information
description: I det här avsnittet beskrivs hur du konfigurerar scenarier för IoT-intelligens i Microsoft Dynamics 365 Supply Chain Management.
author: robinarh
manager: tfehr
ms.date: 08/16/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: rhaertle
ms.custom: ''
ms.search.region: Global
ms.author: rhaertle
ms.search.validFrom: 2020-04-04
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 1632e6df34e2ee2558502597bb94281ab9937824
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5264832"
---
# <a name="scenario-setup-for-iot-intelligence"></a><span data-ttu-id="c0674-103">Scenarioinställningar för IoT-information</span><span class="sxs-lookup"><span data-stu-id="c0674-103">Scenario setup for IoT Intelligence</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c0674-104">I det här avsnittet beskrivs hur du konfigurerar scenarier för IoT-intelligens i Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c0674-104">This topic explains how to configure scenarios for IoT Intelligence in Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="c0674-105">Innan du kan ställa in scenarier måste du [konfigurera Microsoft Dynamics Lifecycle Services (LCS)](iot-lcs-setup.md).</span><span class="sxs-lookup"><span data-stu-id="c0674-105">Before you can set up the scenarios, you must [set up Microsoft Dynamics Lifecycle Services (LCS)](iot-lcs-setup.md).</span></span>

<span data-ttu-id="c0674-106">I det här avsnittet konfigurerar du scenariot **Driftstopp (utrustning)** i syfte att generera ett meddelande i Supply Chain Management när en dator slutar att fungera.</span><span class="sxs-lookup"><span data-stu-id="c0674-106">In this topic, you will configure the **Equipment downtime** scenario so that a notification is generated in Supply Chain Management when a machine goes down.</span></span> <span data-ttu-id="c0674-107">Ämnet visar också hur du konfigurerar scenariot **produktkvalitet** så att ett meddelande genereras om ett attribut för en artikel ligger utanför ett angivet intervall och hur du konfigurerar scenariot **produktionsfördröjning** så att ett meddelande genereras om produktions dataflödet sjunker under ett tröskelvärde.</span><span class="sxs-lookup"><span data-stu-id="c0674-107">The topic also shows how to configure the **Product quality** scenario so that a notification is generated if an attribute of an item is outside a specified range, and how to configure the **Production delays** scenario so that a notification is generated if the production throughput falls below a threshold value.</span></span>

## <a name="configure-the-equipment-downtime-scenario-in-supply-chain-management"></a><span data-ttu-id="c0674-108">Konfigurera scenariot Driftstopp (utrustning) i Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="c0674-108">Configure the Equipment downtime scenario in Supply Chain Management</span></span>

<span data-ttu-id="c0674-109">Scenariot **Driftstopp för utrustning** mappar en **PartOut**-signal om komponent ur funktion till ett tröskelvärde för datornotifiering.</span><span class="sxs-lookup"><span data-stu-id="c0674-109">The **Equipment downtime** scenario maps a **PartOut** signal to a machine alert threshold.</span></span> <span data-ttu-id="c0674-110">Datorn övervakas bara när den väljs ut för scenariot och ställs in för **körning** i Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c0674-110">The machine is monitored only when it's selected for the scenario and when is set to **Running** in Supply Chain Management.</span></span> <span data-ttu-id="c0674-111">Om tiden sedan **PartOut**-signalen senast togs emot från maskiner överstiger tröskelvärdet för notifiering, kommer ett meddelande om **datorstopp** att utlösas.</span><span class="sxs-lookup"><span data-stu-id="c0674-111">If the time since a **PartOut** signal was last received from the machine exceeds the alert threshold, a **Machine down** notification is triggered.</span></span> <span data-ttu-id="c0674-112">Om datorn fortfarande körs kommer meddelandet **datorn körs** att lösas ut när nästa **PartOut**-signal tas emot.</span><span class="sxs-lookup"><span data-stu-id="c0674-112">If the machine is still running, a **Machine up** notification is triggered when the next **PartOut** signal is received.</span></span> <span data-ttu-id="c0674-113">Om en dator förblir ur drift i 30 minuter utlöses ett nytt meddelande om **datorstopp**.</span><span class="sxs-lookup"><span data-stu-id="c0674-113">If a machine stays down for 30 minutes, a new **Machine down** notification is triggered.</span></span>

<span data-ttu-id="c0674-114">Scenariot **Driftstopp (utrustning)** har följande beroenden:</span><span class="sxs-lookup"><span data-stu-id="c0674-114">The **Equipment downtime** scenario has the following dependencies:</span></span>

+ <span data-ttu-id="c0674-115">En tillverkningsorder måste köras på en mappad dator för att en notifiering ska utlösas.</span><span class="sxs-lookup"><span data-stu-id="c0674-115">An alert can be triggered only if a production order is running on a mapped machine.</span></span>
+ <span data-ttu-id="c0674-116">En signal som representerar en mappad datorns signal för **komponentstopp** måste skickas till IoT-hubben med ett unikt egenskapsnamn.</span><span class="sxs-lookup"><span data-stu-id="c0674-116">A signal that represents a mapped machine's **PartOut** signal must be sent to the IoT hub, and a unique property name must be included.</span></span>
+ <span data-ttu-id="c0674-117">En egenskap för UNIX **tidstämpel** där värdet uttrycks i millisekunder (MS), måste finnas i meddelandet i Azure IoT-hubben.</span><span class="sxs-lookup"><span data-stu-id="c0674-117">A UNIX **timestamp** property, where the value is expressed in milliseconds (ms), must be present in the Azure IoT Hub message.</span></span>

<span data-ttu-id="c0674-118">Följ dessa steg för att konfigurera scenariot.</span><span class="sxs-lookup"><span data-stu-id="c0674-118">To configure the scenario, follow these steps.</span></span>

1. <span data-ttu-id="c0674-119">Logga in på Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c0674-119">Sign in to Supply Chain Management.</span></span>
2. <span data-ttu-id="c0674-120">Aktivera funktionsflaggan för IoT-information.</span><span class="sxs-lookup"><span data-stu-id="c0674-120">Enable the IoT Intelligence feature flag.</span></span> <span data-ttu-id="c0674-121">Mer information finns i [Översikt för funktionshantering](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).</span><span class="sxs-lookup"><span data-stu-id="c0674-121">For more information, see [Feature management overview](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).</span></span>
3. <span data-ttu-id="c0674-122">Konfigurera måtten.</span><span class="sxs-lookup"><span data-stu-id="c0674-122">Configure the metrics.</span></span> <span data-ttu-id="c0674-123">Mer information finns i [Konfigurera mått](iot-metrics-setup.md#configure-metrics).</span><span class="sxs-lookup"><span data-stu-id="c0674-123">For more information, see [How to configure metrics](iot-metrics-setup.md#configure-metrics).</span></span>
4. <span data-ttu-id="c0674-124">Gå till **produktionskontroll \> inställning \> IoT-intelligens \> scenariohantering**.</span><span class="sxs-lookup"><span data-stu-id="c0674-124">Go to **Production control \> Setup \> IoT Intelligence \> Scenario management**.</span></span>
6. <span data-ttu-id="c0674-125">På panelen **Driftstopp (utrustning)** välj **konfigurera** för att öppna konfigurationsguiden.</span><span class="sxs-lookup"><span data-stu-id="c0674-125">On the **Equipment downtime** tile, select **Configure** to open the configuration wizard.</span></span>

   <span data-ttu-id="c0674-126">Första sidan i guiden är **Schemadefinition för utrustningssensor**.</span><span class="sxs-lookup"><span data-stu-id="c0674-126">The first page in the wizard is the **Equipment sensor schema definition** page.</span></span> <span data-ttu-id="c0674-127">På den här sidan är ditt mål att ställa in schemat i Supply Chain Management så att det matchar JSON-formatet (JavaScript Object Notation) för IoT-hubb-meddelandena.</span><span class="sxs-lookup"><span data-stu-id="c0674-127">On this page, your goal is to set up the schema in Supply Chain Management so that it matches the JavaScript Object Notation (JSON) format of the IoT Hub messages.</span></span> <span data-ttu-id="c0674-128">Du kan definiera flera meddelandescheman.</span><span class="sxs-lookup"><span data-stu-id="c0674-128">Multiple message schemas can be defined.</span></span> <span data-ttu-id="c0674-129">Mer information finns i [Schemaformat för IoT-hubb-meddelande](iot-schema-format.md).</span><span class="sxs-lookup"><span data-stu-id="c0674-129">For more information, see [Schema formats for IoT Hub messages](iot-schema-format.md).</span></span> <span data-ttu-id="c0674-130">I det här exemplet innehåller meddelandets nyttolasten en batch med meddelanden med detta format.</span><span class="sxs-lookup"><span data-stu-id="c0674-130">In this example, the message payload contains a batch of messages that has the following format.</span></span>

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

7. <span data-ttu-id="c0674-131">Lägg till en rad till tabellen och ange följande värden:</span><span class="sxs-lookup"><span data-stu-id="c0674-131">Add a row to the table, and set the following values:</span></span>

    1. <span data-ttu-id="c0674-132">Ange fältet **Schemanamn** som **ID**.</span><span class="sxs-lookup"><span data-stu-id="c0674-132">Set the **Schema name** field to **ID**.</span></span>
    2. <span data-ttu-id="c0674-133">Ange fältet **Schemasökväg** till **/payload\[\*\]/id**.</span><span class="sxs-lookup"><span data-stu-id="c0674-133">Set the **Schema path** field to **/payload\[\*\]/id**.</span></span>
    3. <span data-ttu-id="c0674-134">Ange fältet **Beskrivning** som **Meddelande-ID**.</span><span class="sxs-lookup"><span data-stu-id="c0674-134">Set the **Description** field to **Message ID**.</span></span>

8. <span data-ttu-id="c0674-135">Lägg till en rad till tabellen och ange följande värden:</span><span class="sxs-lookup"><span data-stu-id="c0674-135">Add another row to the table, and set the following values:</span></span>

    1. <span data-ttu-id="c0674-136">Ange fältet **Schemanamn** som **Tidsstämpel**.</span><span class="sxs-lookup"><span data-stu-id="c0674-136">Set the **Schema name** field to **Timestamp**.</span></span>
    2. <span data-ttu-id="c0674-137">Ange fältet **Schemasökväg** till **/payload\[\*\]/timestamp**.</span><span class="sxs-lookup"><span data-stu-id="c0674-137">Set the **Schema path** field to **/payload\[\*\]/timestamp**.</span></span>
    3. <span data-ttu-id="c0674-138">Ange fältet **Beskrivning** som **Tidsstämpel för meddelande**.</span><span class="sxs-lookup"><span data-stu-id="c0674-138">Set the **Description** field to **Message timestamp**.</span></span>

9. <span data-ttu-id="c0674-139">Lägg till en rad till tabellen och ange följande värden:</span><span class="sxs-lookup"><span data-stu-id="c0674-139">Add another row to the table, and set the following values:</span></span>

    1. <span data-ttu-id="c0674-140">Ange fältet **Schemanamn** som **Värde**.</span><span class="sxs-lookup"><span data-stu-id="c0674-140">Set the **Schema name** field to **Value**.</span></span>
    2. <span data-ttu-id="c0674-141">Ange fältet **Schemasökväg** till **/payload\[\*\]/value**.</span><span class="sxs-lookup"><span data-stu-id="c0674-141">Set the **Schema path** field to **/payload\[\*\]/value**.</span></span>
    3. <span data-ttu-id="c0674-142">Ange fältet **Beskrivning** som **Meddelandevärde**.</span><span class="sxs-lookup"><span data-stu-id="c0674-142">Set the **Description** field to **Message value**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c0674-143">Du behöver inte definiera alla egenskaper i meddelandet.</span><span class="sxs-lookup"><span data-stu-id="c0674-143">You don't have to define all the properties in the message.</span></span> <span data-ttu-id="c0674-144">Definiera endast de egenskaper som du behöver.</span><span class="sxs-lookup"><span data-stu-id="c0674-144">Define only the properties that you require.</span></span> <span data-ttu-id="c0674-145">I föregående steg har du inte skapat någon rad för **Rottidsstämpel**.</span><span class="sxs-lookup"><span data-stu-id="c0674-145">In the preceding steps, you didn't create a row for **Root timestamp**.</span></span> <span data-ttu-id="c0674-146">Sökvägen för **Rottidsstämpel** skulle bli **/timestamp**.</span><span class="sxs-lookup"><span data-stu-id="c0674-146">The path of **Root timestamp** would be **/timestamp**.</span></span>

10. <span data-ttu-id="c0674-147">Klicka på **Nästa** för att gå till sidan **Schemaöversikt för utrustningssensor**.</span><span class="sxs-lookup"><span data-stu-id="c0674-147">Select **Next** to go to the **Equipment sensor schema map** page.</span></span>
11. <span data-ttu-id="c0674-148">I raden för **Resurs-ID för utrustning** anger du fältet **schemanamnet** som **ID**.</span><span class="sxs-lookup"><span data-stu-id="c0674-148">In the row for **Equipment resource ID**, in the **Schema name** field, select **ID**.</span></span>
12. <span data-ttu-id="c0674-149">I raden för **UTC-tid** anger du fältet **schemanamnet** som **Tidsstämpel**.</span><span class="sxs-lookup"><span data-stu-id="c0674-149">In the row for **UTC time**, in the **Schema name** field, select **Timestamp**.</span></span>
13. <span data-ttu-id="c0674-150">I raden för **Komponentgenererad signal** anger du fältet **schemanamnet** som **Värde**.</span><span class="sxs-lookup"><span data-stu-id="c0674-150">In the row for **Part produced signal**, in the **Schema name** field, select **Value**.</span></span>
14. <span data-ttu-id="c0674-151">Klicka på **Nästa** för sidan **ID-konfiguration för utrustningsresurs**.</span><span class="sxs-lookup"><span data-stu-id="c0674-151">Select **Next** to go to the **Equipment resource ID configuration** page.</span></span>
15. <span data-ttu-id="c0674-152">Följ dessa steg för att mappa värdena i IoT-hubbens meddelandevärden till resurserna för Supply Chain Management:</span><span class="sxs-lookup"><span data-stu-id="c0674-152">Follow these steps to map the values in the IoT Hub message to the Supply Chain Management resources:</span></span>

    1. <span data-ttu-id="c0674-153">I tabellen **Signaldatavärden** lägg till en ny rad.</span><span class="sxs-lookup"><span data-stu-id="c0674-153">In the **Signal Data Values** table, add a new row.</span></span> <span data-ttu-id="c0674-154">I fältet **Värde** ange **IoTInt.Machine1225.PartOut**.</span><span class="sxs-lookup"><span data-stu-id="c0674-154">In the **Value** field, enter **IoTInt.Machine1225.PartOut**.</span></span> <span data-ttu-id="c0674-155">Detta värde kommer från JSON **id**-egenskapen i IoT-hubb-meddelande.</span><span class="sxs-lookup"><span data-stu-id="c0674-155">This value  comes from the JSON **id** property in the IoT Hub message.</span></span>
    2. <span data-ttu-id="c0674-156">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="c0674-156">Select **Save**.</span></span>
    3. <span data-ttu-id="c0674-157">I registret **Mappning av affärspost** klickar du på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="c0674-157">In the **Business Record Mapping** table, select **New**.</span></span> <span data-ttu-id="c0674-158">Standardvärdet för **Affärsposttyp** fylls i automatiskt, och du behöver inte ändra det.</span><span class="sxs-lookup"><span data-stu-id="c0674-158">A default value for the **Business record type** field is automatically filled in, and you don't have to change it.</span></span>
    4. <span data-ttu-id="c0674-159">I fältet **Affärspost** väljer du den Supply Chain Management-datorresurs som detta signalvärde skickas ifrån.</span><span class="sxs-lookup"><span data-stu-id="c0674-159">In the **Business record** field, select the Supply Chain Management machine resource that the signal value is being sent from.</span></span>
    5. <span data-ttu-id="c0674-160">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="c0674-160">Select **Save**.</span></span>
    6. <span data-ttu-id="c0674-161">Upprepa stegen och lägg till en ny mappning för affärspost för **Machine1226**.</span><span class="sxs-lookup"><span data-stu-id="c0674-161">Repeat these steps to add a new business record mapping for **Machine1226**.</span></span> <span data-ttu-id="c0674-162">Du kan mappa flera signaldatavärden till en enda post i Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c0674-162">You can map multiple signal data values to a single record in Supply Chain Management.</span></span>

16. <span data-ttu-id="c0674-163">Använd kolumnen **Vald** för att välja vilka datorer som ska bearbetas.</span><span class="sxs-lookup"><span data-stu-id="c0674-163">Use the **Selected** column to select the machines that you want to process.</span></span> <span data-ttu-id="c0674-164">Du behöver inte definiera alla signalvärden och du behöver inte välja alla datorer.</span><span class="sxs-lookup"><span data-stu-id="c0674-164">You don't have to define all signal values, and you don't have to select all machines.</span></span>
17. <span data-ttu-id="c0674-165">Klicka på **Nästa** om du vill gå till sidan för den **komponentproducerade signalkonfigurationen**.</span><span class="sxs-lookup"><span data-stu-id="c0674-165">Select **Next** to go to the **Part produced signal configuration** page.</span></span>
18. <span data-ttu-id="c0674-166">I registret **Signaldatavärden** lägger du till en rad och anger fältet **Värde** som **True**.</span><span class="sxs-lookup"><span data-stu-id="c0674-166">In the **Signal Data Values** table, add a row, and set the **Value** field to **True**.</span></span> <span data-ttu-id="c0674-167">Detta värde kommer från JSON **värde**-egenskapen i IoT-hubb-meddelande.</span><span class="sxs-lookup"><span data-stu-id="c0674-167">This value comes from the JSON **value** property in the IoT Hub message.</span></span> <span data-ttu-id="c0674-168">Du kan lägga till så många värden som du behöver i scenariot.</span><span class="sxs-lookup"><span data-stu-id="c0674-168">You can add as many values as you require for your scenario.</span></span>
19. <span data-ttu-id="c0674-169">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="c0674-169">Select **Save**.</span></span>
20. <span data-ttu-id="c0674-170">Klicka på **Nästa** för att gå till sidan **Tröskelvärde för driftstopp (utrustning)**.</span><span class="sxs-lookup"><span data-stu-id="c0674-170">Select **Next** to go to the **Equipment downtime threshold** page.</span></span> <span data-ttu-id="c0674-171">De angivna datorerna är de som tidigare har mappats till signalvärden.</span><span class="sxs-lookup"><span data-stu-id="c0674-171">The machines that are listed are the machines that were previously mapped to signal values.</span></span> <span data-ttu-id="c0674-172">I det här steget definierar du ett tröskelvärde för att fastställa om en dator inte är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="c0674-172">On this page, you will define a threshold to determine whether a machine is down.</span></span> <span data-ttu-id="c0674-173">Om du till exempel ställer in tröskelvärdet på **10**, Supply Chain Management genererar ett meddelande om det inte finns någon **KomponentUt**-signal från en maskin på 10 minuter.</span><span class="sxs-lookup"><span data-stu-id="c0674-173">For example, if you set the threshold to **10**, Supply Chain Management will generate a notification if no **PartOut** signal is received from a machine for 10 minutes.</span></span>
21. <span data-ttu-id="c0674-174">Klicka på **Nästa** för att öppna sidan **Aktivera scenario**.</span><span class="sxs-lookup"><span data-stu-id="c0674-174">Select **Next** to go to the **Enable scenario** page.</span></span> <span data-ttu-id="c0674-175">Ange alternativet för att aktivera scenariot.</span><span class="sxs-lookup"><span data-stu-id="c0674-175">Set the option to enable the scenario.</span></span>
22. <span data-ttu-id="c0674-176">Välj **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="c0674-176">Select **Finish**.</span></span>

<span data-ttu-id="c0674-177">Scenariokonfigurationen har slutförts.</span><span class="sxs-lookup"><span data-stu-id="c0674-177">The scenario setup is now completed.</span></span> <span data-ttu-id="c0674-178">IoT-information kommer automatiskt att börja bearbeta IoT-navmeddelandena.</span><span class="sxs-lookup"><span data-stu-id="c0674-178">IoT Intelligence will automatically start to process the IoT Hub messages.</span></span>

## <a name="configure-the-product-quality-scenario-in-supply-chain-management"></a><span data-ttu-id="c0674-179">Konfigurera scenariot Produktkvalitet i Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="c0674-179">Configure the Product quality scenario in Supply Chain Management</span></span>

<span data-ttu-id="c0674-180">Scenariot **Produktkvalitet** genererar ett meddelande om ett attribut för en artikel ligger utanför ett angivet intervall.</span><span class="sxs-lookup"><span data-stu-id="c0674-180">The **Product quality** scenario generates a notification if an attribute of an item is outside a specified range.</span></span> <span data-ttu-id="c0674-181">En sensor kan t.ex. skicka vikten för varje enskilt objekt till IoT-hubb.</span><span class="sxs-lookup"><span data-stu-id="c0674-181">For example, a sensor sends the weight of each item to IoT Hub.</span></span> <span data-ttu-id="c0674-182">Om ett objekt är för tungt eller för lätt genereras ett meddelande i Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="c0674-182">If an item is too heavy or too light, a notification is generated in Supply Chain Management.</span></span>

<span data-ttu-id="c0674-183">Scenariot **Produktkvalitet** har följande beroenden:</span><span class="sxs-lookup"><span data-stu-id="c0674-183">The **Product quality** scenario has the following dependencies:</span></span>

+ <span data-ttu-id="c0674-184">En varning kan endast utlösas om en produktionsorder körs på en mappad maskin och producerar en produkt som har ett mappat batchattribut.</span><span class="sxs-lookup"><span data-stu-id="c0674-184">An alert can be triggered only if a production order is running on a mapped machine and producing a product that has a mapped batch attribute.</span></span>
+ <span data-ttu-id="c0674-185">En signal som representerar batchattributet måste skickas till IoT-hubben med ett unikt egenskapsnamn måste inkluderas.</span><span class="sxs-lookup"><span data-stu-id="c0674-185">A signal that represents the batch attribute must be sent to the IoT hub, and a unique property name must be included.</span></span>
+ <span data-ttu-id="c0674-186">En egenskap för UNIX **tidstämpel** där värdet uttrycks i millisekunder måste finnas i meddelandet i IoT-hubb.</span><span class="sxs-lookup"><span data-stu-id="c0674-186">A UNIX **timestamp** property, where the value is expressed in ms, must be present in the IoT Hub message.</span></span>

## <a name="configure-the-production-delays-scenario-in-supply-chain-management"></a><span data-ttu-id="c0674-187">Konfigurera scenariot Tillverkningsfördröjning i Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="c0674-187">Configure the Production delays scenario in Supply Chain Management</span></span>

<span data-ttu-id="c0674-188">I scenariot **Tillverkningsfördröjningar** genereras ett meddelande om tillverkningsgenomflödet sjunker under ett visst tröskelvärde.</span><span class="sxs-lookup"><span data-stu-id="c0674-188">The **Production delays** scenario generates a notification if the production throughput falls below a threshold value.</span></span> <span data-ttu-id="c0674-189">I det här scenariot skickas en **KomponentUt**-signal till IoT-hubben för varje objekt som tillverkas.</span><span class="sxs-lookup"><span data-stu-id="c0674-189">In this scenario, a **PartOut** signal is sent to IoT Hub for each item that is produced.</span></span> <span data-ttu-id="c0674-190">I Supply Chain Management beräknas order förseningen utifrån den tid som tillverkningsordern är schemalagd att köras, antalet artiklar som ska produceras, hur lång tid jobbet har körts och antalet **KomponentUt**-signaler som tas emot.</span><span class="sxs-lookup"><span data-stu-id="c0674-190">In Supply Chain Management, the order delay is calculated based on the amount of time that the production order is scheduled to run, the number of items that should be produced, the amount of time that the job has been running, and the number of **PartOut** signals that are received.</span></span> <span data-ttu-id="c0674-191">Ett fördröjningsmeddelande genereras om antalet **KomponentUt**-signaler för jobbet sjunker under tröskelvärdet för det förväntade värdet.</span><span class="sxs-lookup"><span data-stu-id="c0674-191">A delay notification is generated if the number of **PartOut** signals for the job falls below the threshold value.</span></span>

<span data-ttu-id="c0674-192">Scenariot **Tillverkningsfördröjningar** har följande beroenden:</span><span class="sxs-lookup"><span data-stu-id="c0674-192">The **Production delays** scenario has the following dependencies:</span></span>

+ <span data-ttu-id="c0674-193">En tillverkningsorder måste köras på en mappad dator för att en notifiering ska utlösas.</span><span class="sxs-lookup"><span data-stu-id="c0674-193">An alert can be triggered only if a production order is running on a mapped machine.</span></span>
+ <span data-ttu-id="c0674-194">En signal som representerar en mappad datorns signal för **komponentstopp** måste skickas till Azure IoT-hubben med ett unikt egenskapsnamn.</span><span class="sxs-lookup"><span data-stu-id="c0674-194">A signal that represents a mapped machine's **PartOut** signal must be sent to the Azure IoT hub, and a unique property name must be included.</span></span>
+ <span data-ttu-id="c0674-195">En egenskap för UNIX **tidstämpel** där värdet uttrycks i millisekunder måste finnas i meddelandet i IoT-hubb.</span><span class="sxs-lookup"><span data-stu-id="c0674-195">A UNIX **timestamp** property, where the value is expressed in ms, must be present in the IoT Hub message.</span></span>

## <a name="disable-a-scenario"></a><span data-ttu-id="c0674-196">Inaktivera ett scenario</span><span class="sxs-lookup"><span data-stu-id="c0674-196">Disable a scenario</span></span>

<span data-ttu-id="c0674-197">Följ dessa steg om du vill inaktivera ett scenario.</span><span class="sxs-lookup"><span data-stu-id="c0674-197">To disable a scenario, follow these steps.</span></span>

1. <span data-ttu-id="c0674-198">I Supply Chain Management navigerar du till **Tillverkningsstyrning \> Inställningar \> IoT-information \> Scenariohantering**.</span><span class="sxs-lookup"><span data-stu-id="c0674-198">In Supply Chain Management, go to **Production control \> Setup \> IoT Intelligence \> Scenario management**.</span></span>
2. <span data-ttu-id="c0674-199">På panel för scenariot väljer du **Konfigurera**.</span><span class="sxs-lookup"><span data-stu-id="c0674-199">On the tile for the scenario, select **Configure**.</span></span>
3. <span data-ttu-id="c0674-200">Klicka på **Nästa** för att öppna sidan för den senaste guiden.</span><span class="sxs-lookup"><span data-stu-id="c0674-200">Select **Next** to go to the last wizard page.</span></span>
4. <span data-ttu-id="c0674-201">Ange alternativet för att inaktivera scenariot.</span><span class="sxs-lookup"><span data-stu-id="c0674-201">Set the option to disable the scenario.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]