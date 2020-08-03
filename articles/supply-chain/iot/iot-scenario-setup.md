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
# <a name="scenario-setup-for-iot-intelligence"></a><span data-ttu-id="a748e-103">Scenarioinställningar för IoT-information</span><span class="sxs-lookup"><span data-stu-id="a748e-103">Scenario setup for IoT Intelligence</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a748e-104">I det här avsnittet beskrivs hur du konfigurerar ett scenario i Supply Chain Management för IoT-information.</span><span class="sxs-lookup"><span data-stu-id="a748e-104">This topic describes how to configure a scenario in Supply Chain Management for IoT Intelligence.</span></span> <span data-ttu-id="a748e-105">Innan du kan ställa in scenarier måste du [konfigurera LCS](iot-lcs-setup.md).</span><span class="sxs-lookup"><span data-stu-id="a748e-105">Before you can setup the scenarios, you must [setup LCS](iot-lcs-setup.md).</span></span>

<span data-ttu-id="a748e-106">I det här avsnittet konfigurerar du scenariot **Driftstopp (utrustning)** i syfte att generera ett meddelande i Supply Chain Management när en dator slutar att fungera.</span><span class="sxs-lookup"><span data-stu-id="a748e-106">In this topic, you will configure the **Equipment downtime** scenario to generate a notification in Supply Chain Management when a machine goes down.</span></span>

## <a name="configure-the-equipment-downtime-scenario-in-supply-chain-management"></a><span data-ttu-id="a748e-107">Konfigurera scenariot **Driftstopp (utrustning)** i Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="a748e-107">Configure the **Equipment downtime** scenario in Supply Chain Management</span></span>

<span data-ttu-id="a748e-108">Scenariot **Driftstopp (utrustning)** mappar en signal om komponent ur funktion till ett tröskelvärde för datornotifiering.</span><span class="sxs-lookup"><span data-stu-id="a748e-108">The **Equipment downtime** scenario maps a part out signal to a machine alert threshold.</span></span> <span data-ttu-id="a748e-109">Datorn övervakas bara när den väljs ut för scenariot och ställs in för körning i Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="a748e-109">The machine is monitored only when the machine is selected for the scenario and is set to running in Supply Chain Management.</span></span> <span data-ttu-id="a748e-110">Om tiden sedan datorn senast mottagna signal för komponent ur funktion överstiger tröskelvärdet för notifiering, kommer ett meddelande om **Datorstopp** att utlösas.</span><span class="sxs-lookup"><span data-stu-id="a748e-110">If the time since the machine’s last received Part Out signal is greater than the alert threshold, then a **Machine down** notification is triggered.</span></span> <span data-ttu-id="a748e-111">Om datorn fortfarande körs kommer, när nästa **KomponentUt**-signal tas emot, ett meddelande om **datorn körs** att lösas ut.</span><span class="sxs-lookup"><span data-stu-id="a748e-111">If the machine is still running, when the next **PartOut** signal is received a **Machine up** notification is triggered.</span></span> <span data-ttu-id="a748e-112">Om en dator förblir ur drift i 30 minuter utlöses ett nytt meddelande om **datorstopp**.</span><span class="sxs-lookup"><span data-stu-id="a748e-112">If a machine stays down for 30 mins a new **Machine down** notification is triggered.</span></span>

<span data-ttu-id="a748e-113">Scenariot **Driftstopp (utrustning)** har följande beroenden:</span><span class="sxs-lookup"><span data-stu-id="a748e-113">The **Equipment downtime** scenario has these dependencies:</span></span>

+ <span data-ttu-id="a748e-114">En tillverkningsorder måste köras på en mappad dator för att en notifiering ska utlösas.</span><span class="sxs-lookup"><span data-stu-id="a748e-114">A production order must be running on a mapped machine for an alert to be triggered.</span></span>
+ <span data-ttu-id="a748e-115">En signal som representerar en mappad datorns signal för komponentstopp måste skickas till IoT-navet med ett unikt egenskapsnamn.</span><span class="sxs-lookup"><span data-stu-id="a748e-115">A signal representing a mapped machine's part out signal must be sent to the IoT Hub with a unique property name.</span></span>
+ <span data-ttu-id="a748e-116">En Unix-egenskap för tidsstämpel i millisekunder måste finnas i IoT-navmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="a748e-116">A Unix milliseconds timestamp property must be present in the IoT hub message.</span></span>

<span data-ttu-id="a748e-117">Följ dessa steg för att konfigurera scenariot:</span><span class="sxs-lookup"><span data-stu-id="a748e-117">To configure the scenario, follow these steps:</span></span>

1. <span data-ttu-id="a748e-118">Logga in på Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="a748e-118">Log into Supply Chain Management.</span></span>
2. <span data-ttu-id="a748e-119">Aktivera funktionsflaggan för IoT-information.</span><span class="sxs-lookup"><span data-stu-id="a748e-119">Enable the IoT Intelligence feature flag.</span></span> <span data-ttu-id="a748e-120">Mer information finns i [Översikt för funktionshantering](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a748e-120">For more information, see [Feature management overview](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span></span>
3. <span data-ttu-id="a748e-121">Konfigurera måtten.</span><span class="sxs-lookup"><span data-stu-id="a748e-121">Configure the metrics.</span></span> <span data-ttu-id="a748e-122">Mer information finns i [Konfigurera mått](iot-metrics-setup.md#configure-metrics).</span><span class="sxs-lookup"><span data-stu-id="a748e-122">For more information, see [How to configure metrics](iot-metrics-setup.md#configure-metrics).</span></span>
4. <span data-ttu-id="a748e-123">Navigera till **Tillverkningsstyrning**.</span><span class="sxs-lookup"><span data-stu-id="a748e-123">Navigate to **Production control**.</span></span>
5. <span data-ttu-id="a748e-124">Navigera till **Konfiguration \> IoT-information \> Scenariohantering**.</span><span class="sxs-lookup"><span data-stu-id="a748e-124">Navigate to **Setup \> IoT Intelligence \> Scenario management**.</span></span>
6. <span data-ttu-id="a748e-125">Klicka på **Konfigurera** på panelen **Driftstopp (utrustning)**.</span><span class="sxs-lookup"><span data-stu-id="a748e-125">Click **Configure** on the **Equipment downtime** tile.</span></span> <span data-ttu-id="a748e-126">Konfigurationsguiden startar med sidan **Schemadefinition för utrustningssensor**.</span><span class="sxs-lookup"><span data-stu-id="a748e-126">The configuration wizard starts with the **Equipment sensor schema definition** page.</span></span> <span data-ttu-id="a748e-127">Målet här är att ställa in schemat i Supply Chain Management så att det matchar formatet JSON i IoT-meddelandena.</span><span class="sxs-lookup"><span data-stu-id="a748e-127">The goal here is to setup the schema in Supply Chain Management to match the JSON format of the IoT messages.</span></span> <span data-ttu-id="a748e-128">Du kan definiera flera meddelandescheman.</span><span class="sxs-lookup"><span data-stu-id="a748e-128">Multiple message schemas can be defined.</span></span> <span data-ttu-id="a748e-129">Mer information finns i [Format för meddelandeschema för IoT-nav](iot-schema-format.md).</span><span class="sxs-lookup"><span data-stu-id="a748e-129">For more information, see [Message schema formats for IoT Hub](iot-schema-format.md).</span></span> <span data-ttu-id="a748e-130">I det här exemplet innehåller meddelandets nyttolasten en batch med meddelanden med detta format:</span><span class="sxs-lookup"><span data-stu-id="a748e-130">In this example, the message payload contains a batch of messages with this format:</span></span>

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

7. <span data-ttu-id="a748e-131">Lägg till en rad i registret.</span><span class="sxs-lookup"><span data-stu-id="a748e-131">Add a row to the table.</span></span>

    1. <span data-ttu-id="a748e-132">Ange **Schemanamn** som **ID**.</span><span class="sxs-lookup"><span data-stu-id="a748e-132">Set the **Schema name** to **ID**.</span></span>
    2. <span data-ttu-id="a748e-133">Ange **Schemasökväg** som **/payload[\*]/id**.</span><span class="sxs-lookup"><span data-stu-id="a748e-133">Set the **Schema path** to **/payload[\*]/id**.</span></span>
    3. <span data-ttu-id="a748e-134">Ange **Beskrivning** som **Meddelande-ID**.</span><span class="sxs-lookup"><span data-stu-id="a748e-134">Set the **Description** to **Message ID**.</span></span>

8. <span data-ttu-id="a748e-135">Lägg till en rad i registret.</span><span class="sxs-lookup"><span data-stu-id="a748e-135">Add a row to the table.</span></span>

    1. <span data-ttu-id="a748e-136">Ange **Schemanamn** som **Tidsstämpel**.</span><span class="sxs-lookup"><span data-stu-id="a748e-136">Set the **Schema name** to **Timestamp**.</span></span>
    2. <span data-ttu-id="a748e-137">Ange **Schemasökväg** som **/payload[\*]/timestamp**.</span><span class="sxs-lookup"><span data-stu-id="a748e-137">Set the **Schema path** to **/payload[\*]/timestamp**.</span></span>
    3. <span data-ttu-id="a748e-138">Ange **Beskrivning** som **Tidsstämpel för meddelande**.</span><span class="sxs-lookup"><span data-stu-id="a748e-138">Set the **Description** to **Message timestamp**.</span></span>

9. <span data-ttu-id="a748e-139">Lägg till en rad i registret.</span><span class="sxs-lookup"><span data-stu-id="a748e-139">Add a row to the table.</span></span>

    1. <span data-ttu-id="a748e-140">Ange **Schemanamn** som **Värde**.</span><span class="sxs-lookup"><span data-stu-id="a748e-140">Set the **Schema name** to **Value**.</span></span>
    2. <span data-ttu-id="a748e-141">Ange **Schemasökväg** som **/payload[\*]/värde**.</span><span class="sxs-lookup"><span data-stu-id="a748e-141">Set the **Schema path** to **/payload[\*]/value**.</span></span>
    3. <span data-ttu-id="a748e-142">Ange **Beskrivning** som **Meddelandevärde**.</span><span class="sxs-lookup"><span data-stu-id="a748e-142">Set the **Description** to **Message value**.</span></span>

    <span data-ttu-id="a748e-143">Du behöver inte definiera alla egenskaper i meddelandet, bara dem du behöver.</span><span class="sxs-lookup"><span data-stu-id="a748e-143">You don't need to define all the properties in the message, only the ones that you need.</span></span> <span data-ttu-id="a748e-144">I det här exemplet skapades ingen rad för **Rottidsstämpel**.</span><span class="sxs-lookup"><span data-stu-id="a748e-144">In this example, you did not create a row for **Root timestamp**.</span></span> <span data-ttu-id="a748e-145">Sökvägen för **Rottidsstämpel** skulle bli **/timestamp**.</span><span class="sxs-lookup"><span data-stu-id="a748e-145">The path for **Root timestamp** would be **/timestamp**.</span></span>
  
10. <span data-ttu-id="a748e-146">Klicka på **Nästa** för att gå till sidan **Schemaöversikt för utrustningssensor**.</span><span class="sxs-lookup"><span data-stu-id="a748e-146">Click **Next** to go to the **Equipment sensor schema map** page.</span></span>
11. <span data-ttu-id="a748e-147">I raden för **Resurs-ID för utrustning** anger du **schemanamnet** som **ID**.</span><span class="sxs-lookup"><span data-stu-id="a748e-147">In the row for **Equipment resource ID** set the **Schema name** to **ID**.</span></span> <span data-ttu-id="a748e-148">Giltiga värden visas i ett listruteregister.</span><span class="sxs-lookup"><span data-stu-id="a748e-148">The valid values are displayed in a dropdown table.</span></span>
12. <span data-ttu-id="a748e-149">I raden för **UTC-tid** anger du **schemanamnet** som **Tidsstämpel**.</span><span class="sxs-lookup"><span data-stu-id="a748e-149">In the row for **UTC time** set the **Schema name** to **Timestamp**.</span></span> <span data-ttu-id="a748e-150">Giltiga värden visas i ett listruteregister.</span><span class="sxs-lookup"><span data-stu-id="a748e-150">The valid values are displayed in a dropdown table.</span></span>
13. <span data-ttu-id="a748e-151">I raden för **Komponentgenererad signal** anger du **schemanamnet** som **Värde**.</span><span class="sxs-lookup"><span data-stu-id="a748e-151">In the row for **Part produced signal** set the **Schema name** to **Value**.</span></span> <span data-ttu-id="a748e-152">Giltiga värden visas i ett listruteregister.</span><span class="sxs-lookup"><span data-stu-id="a748e-152">The valid values are displayed in a dropdown table.</span></span>
14. <span data-ttu-id="a748e-153">Klicka på **Nästa** för sidan **ID-konfiguration för utrustningsresurs**.</span><span class="sxs-lookup"><span data-stu-id="a748e-153">Click **Next** for the **Equipment resource ID configuration** page.</span></span>
15. <span data-ttu-id="a748e-154">I det här steget mappar du IoT-navets meddelandevärden till resurserna för Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="a748e-154">In this step, you map the IoT Hub message values to the Supply Chain Management resources.</span></span>

    1. <span data-ttu-id="a748e-155">I registret **Värden för signaldata** lägger du till en ny rad och anger **IoTInt.Machine1225.PartOut** i kolumnen **Värde**.</span><span class="sxs-lookup"><span data-stu-id="a748e-155">In the **Signal Data Values** table, add a new row, and enter **IoTInt.Machine1225.PartOut** in the **Value** column.</span></span> <span data-ttu-id="a748e-156">Värdet **IoTInt.Machine1225.PartOut** kommer från egenskapen **id** för JSON i IoT-navmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="a748e-156">The value **IoTInt.Machine1225.PartOut** comes from the JSON **id** property in the IoT hub message.</span></span>
    2. <span data-ttu-id="a748e-157">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="a748e-157">Click **Save**.</span></span>
    3. <span data-ttu-id="a748e-158">I registret **Mappning av affärspost** klickar du på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="a748e-158">In the **Business Record Mapping** table, click **New**.</span></span> <span data-ttu-id="a748e-159">Standardvärdet för **Affärsposttyp** fylls i automatiskt, och du behöver inte ändra det.</span><span class="sxs-lookup"><span data-stu-id="a748e-159">The default value for the **Business record type** is autopopulated, and you don't need to change it.</span></span>
    4. <span data-ttu-id="a748e-160">I kolumnen **Affärspost** väljer du den Supple Chain Management-datorresurs som detta signalvärde skickas ifrån.</span><span class="sxs-lookup"><span data-stu-id="a748e-160">In the **Business record** column, select the Supple Chain Management machine resource this signal value is being sent from.</span></span>
    5. <span data-ttu-id="a748e-161">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="a748e-161">Click **Save**.</span></span>
    6. <span data-ttu-id="a748e-162">Upprepa stegen och lägg till en ny mappning för affärspost för **Machine1226**.</span><span class="sxs-lookup"><span data-stu-id="a748e-162">Repeat these steps, adding a new business record mapping for **Machine1226**.</span></span> <span data-ttu-id="a748e-163">Du kan mappa flera signaldatavärden till en enda post i Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="a748e-163">You can map multiple signal data values to a single record in Supply Chain Management.</span></span>

16. <span data-ttu-id="a748e-164">Använd kolumnen **Vald** för att välja vilka datorer som ska bearbetas.</span><span class="sxs-lookup"><span data-stu-id="a748e-164">Use the **Selected** column to choose which machines you want to process.</span></span> <span data-ttu-id="a748e-165">Du behöver inte definiera alla signalvärden och du behöver inte välja alla datorer.</span><span class="sxs-lookup"><span data-stu-id="a748e-165">You do not have to define all signal values and you do not have to select all machines.</span></span>
17. <span data-ttu-id="a748e-166">Klicka på **Nästa** om du vill gå till sidan för den **komponentproducerade signalkonfigurationen**.</span><span class="sxs-lookup"><span data-stu-id="a748e-166">Click **Next** to go to the **Part produced signal configuration** page.</span></span>
18. <span data-ttu-id="a748e-167">I registret **Signaldatavärden** lägger du till en rad och anger **Värde** som **True**.</span><span class="sxs-lookup"><span data-stu-id="a748e-167">In the **Signal Data Values** table, add a row, and set **Value** to **True**.</span></span> <span data-ttu-id="a748e-168">Värdet **True** kommer från JSON-egenskapen **värde** i IoT-meddelande.</span><span class="sxs-lookup"><span data-stu-id="a748e-168">The value **True** comes from the JSON **value** property in the IoT hub message.</span></span> <span data-ttu-id="a748e-169">Du kan lägga till så många värden som du behöver i scenariot.</span><span class="sxs-lookup"><span data-stu-id="a748e-169">You can add as many values as you need for your scenario.</span></span>
19. <span data-ttu-id="a748e-170">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="a748e-170">Click **Save**.</span></span>
20. <span data-ttu-id="a748e-171">Klicka på **Nästa** för att gå till sidan **Tröskelvärde för driftstopp (utrustning)**.</span><span class="sxs-lookup"><span data-stu-id="a748e-171">Click **Next** to go to the **Equipment downtime threshold** page.</span></span> <span data-ttu-id="a748e-172">De angivna datorerna är de som tidigare har mappats till signalvärden.</span><span class="sxs-lookup"><span data-stu-id="a748e-172">The machines listed are the machines previously mapped to signal values.</span></span> <span data-ttu-id="a748e-173">I det här steget definierar du ett tröskelvärde för att fastställa om en dator inte är tillgänglig.</span><span class="sxs-lookup"><span data-stu-id="a748e-173">In this step, you define a threshold to determine if a machine is down.</span></span> <span data-ttu-id="a748e-174">Om du till exempel ställer in tröskelvärdet på 10 genererar Supply Chain Management ett meddelande om det inte finns något meddelande om defekt komponent från en maskin på 10 minuter.</span><span class="sxs-lookup"><span data-stu-id="a748e-174">For example, if you set the threshold to 10, Supply Chain Management generates a notification if there is no part out message from a machine for 10 minutes.</span></span>
21. <span data-ttu-id="a748e-175">Klicka på **Nästa** för att öppna sidan **Aktivera scenario**.</span><span class="sxs-lookup"><span data-stu-id="a748e-175">Click **Next** to go to the **Enable scenario** page.</span></span> <span data-ttu-id="a748e-176">Aktivera scenariot genom att förflytta skjutreglaget.</span><span class="sxs-lookup"><span data-stu-id="a748e-176">Toggle the slider to enable the scenario.</span></span>
22. <span data-ttu-id="a748e-177">Klicka på **Avsluta**.</span><span class="sxs-lookup"><span data-stu-id="a748e-177">Click **Finish**.</span></span>

<span data-ttu-id="a748e-178">Scenariokonfigurationen har slutförts.</span><span class="sxs-lookup"><span data-stu-id="a748e-178">The scenario setup is complete.</span></span> <span data-ttu-id="a748e-179">IoT-information kommer automatiskt att börja bearbeta IoT-navmeddelandena.</span><span class="sxs-lookup"><span data-stu-id="a748e-179">IoT Intelligence will automatically start processing the IoT Hub messages.</span></span>

## <a name="configure-the-product-quality-scenario-in-supply-chain-management"></a><span data-ttu-id="a748e-180">Konfigurera scenariot **Produktkvalitet** i Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="a748e-180">Configure the **Product quality** scenario in Supply Chain Management</span></span>

<span data-ttu-id="a748e-181">Scenariot **Produktkvalitet** genererar ett meddelande om ett attribut för en artikel ligger utanför ett angivet intervall.</span><span class="sxs-lookup"><span data-stu-id="a748e-181">The **Product quality** scenario generates a notification if an attribute of an item is outside a specified range.</span></span> <span data-ttu-id="a748e-182">En sensor kan t.ex. skicka vikten för varje enskilt objekt till IoT-navet.</span><span class="sxs-lookup"><span data-stu-id="a748e-182">For example, a sensor could send the weight of each item to IoT Hub.</span></span> <span data-ttu-id="a748e-183">Ett meddelande genereras i Supply Chain Management om artikeln är för tungt eller för lätt.</span><span class="sxs-lookup"><span data-stu-id="a748e-183">In Supply Chain Management, a notification would be generated if the item was too heavy or too light.</span></span>

<span data-ttu-id="a748e-184">Scenariot har följande beroenden:</span><span class="sxs-lookup"><span data-stu-id="a748e-184">The scenario has these dependencies:</span></span>

+ <span data-ttu-id="a748e-185">En tillverkningsorder måste köras på en mappad dator och framställa en produkt med mappat batchattibut för att en notifiering ska utlösas.</span><span class="sxs-lookup"><span data-stu-id="a748e-185">A Production Order must be running on a mapped machine and producing a product with a mapped batch attribute for an alert to be triggered.</span></span>
+ <span data-ttu-id="a748e-186">En signal som representerar batchattributet måste skickas till IoT-navet med ett unikt egenskapsnamn.</span><span class="sxs-lookup"><span data-stu-id="a748e-186">A signal representing the batch attribute must be sent to the IoT Hub with a unique property name.</span></span>
+ <span data-ttu-id="a748e-187">En Unix-egenskap för tidsstämpel i millisekunder måste finnas i IoT-navmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="a748e-187">A Unix milliseconds timestamp property must be present in the IoT Hub message.</span></span>

## <a name="configure-the-production-delays-scenario-in-supply-chain-management"></a><span data-ttu-id="a748e-188">Konfigurera scenariot **Tillverkningsfördröjning** i Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="a748e-188">Configure the **Production delays** scenario in Supply Chain Management</span></span>

<span data-ttu-id="a748e-189">I scenariot **Tillverkningsfördröjningar** genereras ett meddelande om tillverkningsgenomflödet sjunker under ett visst tröskelvärde.</span><span class="sxs-lookup"><span data-stu-id="a748e-189">The **Production delays** scenario generates a notification if the production throughput falls below a threshold value.</span></span> <span data-ttu-id="a748e-190">I det här scenariot skickas en **KomponentUt**-signal till IoT-navet för varje objekt som tillverkas.</span><span class="sxs-lookup"><span data-stu-id="a748e-190">In this scenario, a **PartOut** signal is sent to IoT Hub for each item produced.</span></span> <span data-ttu-id="a748e-191">I Supply Chain Management beräknas orderförseningen baserat på hur lång tid tillverkningsordern är schemalagd att köras, hur många artiklar som ska tillverkas, hur länge jobbet har körts och hur många **KomponentUt**-signaler som tas emot.</span><span class="sxs-lookup"><span data-stu-id="a748e-191">In Supply Chain Management, the order delay is calculated based on how long the production order is scheduled to run, how many items should be produced, how long the job has been running, and how many **PartOut** signals are received.</span></span> <span data-ttu-id="a748e-192">Ett fördröjningsmeddelande genereras om antalet **KomopnentUt**-signaler för jobbet sjunker under tröskelvärdet för det förväntade värdet.</span><span class="sxs-lookup"><span data-stu-id="a748e-192">A delay notification would be generated if the number of the **PartOut** signals for the job falls below the threshold value of the expected value.</span></span>

<span data-ttu-id="a748e-193">Scenariot har följande beroenden:</span><span class="sxs-lookup"><span data-stu-id="a748e-193">The scenario has these dependencies:</span></span>

+ <span data-ttu-id="a748e-194">En tillverkningsorder måste köras på en mappad dator för att en notifiering ska utlösas.</span><span class="sxs-lookup"><span data-stu-id="a748e-194">A Production Order must be running on a mapped machine for an alert to be triggered.</span></span>
+ <span data-ttu-id="a748e-195">En signal som representerar en mappad datorns signal för komponentstopp måste skickas till IoT-navet med ett unikt egenskapsnamn.</span><span class="sxs-lookup"><span data-stu-id="a748e-195">A signal representing a mapped machine's part out signal must be sent to the IoT Hub with a unique property name.</span></span>
+ <span data-ttu-id="a748e-196">En Unix-egenskap för tidsstämpel i millisekunder måste finnas i IoT-navmeddelandet.</span><span class="sxs-lookup"><span data-stu-id="a748e-196">A Unix milliseconds timestamp property must be present in the IoT Hub message.</span></span>

## <a name="how-to-disable-a-scenario"></a><span data-ttu-id="a748e-197">Inaktivera ett scenario</span><span class="sxs-lookup"><span data-stu-id="a748e-197">How to disable a scenario</span></span>

<span data-ttu-id="a748e-198">Följ dessa steg om du vill inatkivera ett scenario:</span><span class="sxs-lookup"><span data-stu-id="a748e-198">To disable a scenario, follow these steps:</span></span>

1. <span data-ttu-id="a748e-199">I Supply Chain Management navigerar du till **Tillverkningsstyrning \> Inställningar \> IoT-information \> Scenariohantering**.</span><span class="sxs-lookup"><span data-stu-id="a748e-199">In Supply Chain Management, navigate to **Production control \> Setup \> IoT Intelligence \> Scenario management**.</span></span>
2. <span data-ttu-id="a748e-200">Klicka på **Konfigurera** i scenariot.</span><span class="sxs-lookup"><span data-stu-id="a748e-200">Click **Configure** on the scenario.</span></span>
3. <span data-ttu-id="a748e-201">Klicka på **Nästa** för att komma till den sista fliken i guiden.</span><span class="sxs-lookup"><span data-stu-id="a748e-201">Click **Next** to get to the last wizard tab.</span></span>
4. <span data-ttu-id="a748e-202">Inaktivera scenariot genom att förflytta skjutreglaget.</span><span class="sxs-lookup"><span data-stu-id="a748e-202">Toggle the slider to disable the scenario.</span></span>
