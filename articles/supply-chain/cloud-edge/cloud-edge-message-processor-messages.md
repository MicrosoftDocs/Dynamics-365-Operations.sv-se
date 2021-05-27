---
title: Meddelandeprocessormeddelanden
description: Detta ämne innehåller information om funktionen för meddelandebearbetning för skalningsenhetsarbetsbelastningar.
author: perlynne
ms.date: 04/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysMessageProcessorMessage, BusinessEventsWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: perlynne
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 03d8cad743ac2b2b1e7b2832b8272ca3dbf5a163
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021065"
---
# <a name="message-processor-messages"></a><span data-ttu-id="d0f17-103">Meddelandeprocessormeddelanden</span><span class="sxs-lookup"><span data-stu-id="d0f17-103">Message processor messages</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="d0f17-104">Meddelanden i meddelandeprocessorn används när molnbaserade enheter och kantskalningsenheter körs för [arbetsbelastningar inom tillverkning](cloud-edge-workload-manufacturing.md) samt [arbetsbelastningar inom lagerstyrnings](cloud-edge-workload-warehousing.md).</span><span class="sxs-lookup"><span data-stu-id="d0f17-104">Message processor messages are used when running cloud and edge scale units for [manufacturing workloads](cloud-edge-workload-manufacturing.md) and [warehouse management workloads](cloud-edge-workload-warehousing.md).</span></span>

<span data-ttu-id="d0f17-105">En stor mängd data utbyts mellan distribueringsmiljöerna för nav och skalningsenhet i syfte att hålla dem synkroniserade, men endast ett fåtal av dessa datautbyten kommer att bearbetas av *meddelandeprocessorn*.</span><span class="sxs-lookup"><span data-stu-id="d0f17-105">A large amount of data is exchanged between the hub and scale unit deployment environments to keep them in sync, but only a few of these data exchanges will be processed by the *message processor*.</span></span> <span data-ttu-id="d0f17-106">Du kan visa meddelanden som bearbetats av meddelandeprocessorn genom att gå till **Systemadministration > Meddelandeprocessor > Meddelanden i meddelandeprocessorn**.</span><span class="sxs-lookup"><span data-stu-id="d0f17-106">You can view the messages processed by the message processor by going to **System administration > Message processor > Message processor messages**.</span></span>

## <a name="message-grid-columns-and-filters"></a><span data-ttu-id="d0f17-107">Kolumner och filter i meddelanderutnät</span><span class="sxs-lookup"><span data-stu-id="d0f17-107">Message grid columns and filters</span></span>

<span data-ttu-id="d0f17-108">Med hjälp av fälten högst upp på sidan **Meddelanden i meddelandeprocessorn** kan du hitta eventuella meddelanden som du letar efter.</span><span class="sxs-lookup"><span data-stu-id="d0f17-108">You can use the fields at the top of the **Message processor messages** page to help find any particular messages you are looking for.</span></span> <span data-ttu-id="d0f17-109">De flesta filter matchar kolumnrubrikerna i meddelanderutnätet.</span><span class="sxs-lookup"><span data-stu-id="d0f17-109">Most of these filters match the column headings in the message grid.</span></span> <span data-ttu-id="d0f17-110">Följande filter och kolumnrubriker är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="d0f17-110">The following filters and column headings are available:</span></span>

- <span data-ttu-id="d0f17-111">**Meddelandetyp** – Anger meddelandetypen.</span><span class="sxs-lookup"><span data-stu-id="d0f17-111">**Message type** – Specifies the type of message.</span></span>
- <span data-ttu-id="d0f17-112">**Meddelandekö** – Anger namnet på kön där meddelandet ska bearbetas.</span><span class="sxs-lookup"><span data-stu-id="d0f17-112">**Message queue** – Specifies the name of the queue in which the message is to be processed.</span></span> <span data-ttu-id="d0f17-113">Följande köer finns:</span><span class="sxs-lookup"><span data-stu-id="d0f17-113">The following queues are provided:</span></span>
  - <span data-ttu-id="d0f17-114">*Skalningsenhet till hubb*</span><span class="sxs-lookup"><span data-stu-id="d0f17-114">*Scale unit to hub*</span></span>
  - <span data-ttu-id="d0f17-115">*Hubb till skalningsenhet för lagerställekörning*</span><span class="sxs-lookup"><span data-stu-id="d0f17-115">*Hub to warehouse execution scale unit*</span></span>
  - <span data-ttu-id="d0f17-116">*Hubb till skalningsenhet för produktionskörning*</span><span class="sxs-lookup"><span data-stu-id="d0f17-116">*Hub to manufacturing execution scale unit*</span></span>
- <span data-ttu-id="d0f17-117">**Meddelandestatus** – Anger status för meddelandet.</span><span class="sxs-lookup"><span data-stu-id="d0f17-117">**Message state** – Specifies the state of the message.</span></span> <span data-ttu-id="d0f17-118">Följande statuslägen finns:</span><span class="sxs-lookup"><span data-stu-id="d0f17-118">The following states exists:</span></span>
  - <span data-ttu-id="d0f17-119">*Köad* – Meddelandet är klart att bearbetas av meddelandeprocessorn.</span><span class="sxs-lookup"><span data-stu-id="d0f17-119">*Queued* – The message is ready to be processed by the message processor.</span></span>
  - <span data-ttu-id="d0f17-120">*Bearbetades* – Meddelandet har bearbetats av meddelandeprocessorn.</span><span class="sxs-lookup"><span data-stu-id="d0f17-120">*Processed* – The message was successfully processed by the message processor.</span></span>
  - <span data-ttu-id="d0f17-121">*Annullerat* – Meddelandet bearbetades men bearbetningen misslyckades.</span><span class="sxs-lookup"><span data-stu-id="d0f17-121">*Canceled* – The message was processed, but processing failed.</span></span>
- <span data-ttu-id="d0f17-122">**Meddelandeinnehåll** – Detta filter genomför en fulltextsökning av meddelandeinnehåll.</span><span class="sxs-lookup"><span data-stu-id="d0f17-122">**Message content** – This filter does a full-text search of message content.</span></span> <span data-ttu-id="d0f17-123">(meddelandeinnehållet visas inte i rutnätet). Filtret behandlar de flesta specialtecken (exempelvis "-") som blanksteg, och behandlar alla blanksteg som booleska OR-operatorer.</span><span class="sxs-lookup"><span data-stu-id="d0f17-123">(Message content is not shown in the grid.) The filter treats most special symbols (such as "-") as spaces, and treats all space characters as Boolean OR operators.</span></span> <span data-ttu-id="d0f17-124">T=Till exempel betyder detta att om du söker efter ett specifikt värde som är lika med `journalid` "USMF-123456", så hittar systemet alla meddelanden som innehåller "USMF" eller "123456", vilket troligen lär bli en lång lista.</span><span class="sxs-lookup"><span data-stu-id="d0f17-124">T=For example, this means if you search for a specific `journalid` value equal "USMF-123456", the system will find all messages that contain "USMF" or "123456", which is likely to be a long list.</span></span> <span data-ttu-id="d0f17-125">Därför är det bättre att enbart ange "123456" eftersom detta returnerar mer specifika resultat.</span><span class="sxs-lookup"><span data-stu-id="d0f17-125">Therefore, it would be better to enter just "123456" alone because that will return more specific results.</span></span>

## <a name="example-message-type-request-inventory-adjustment-financial-update"></a><span data-ttu-id="d0f17-126">Exempel på meddelandetyp: Begär ekonomisk uppdatering av lagerjustering</span><span class="sxs-lookup"><span data-stu-id="d0f17-126">Example message type: Request inventory adjustment financial update</span></span>

<span data-ttu-id="d0f17-127">Till exempel används **meddelandetypen** *Begär ekonomisk uppdatering av lagerjustering* för att skapa och bokföra en inventeringsjournal i navet när en medarbetare använder lagerställeappen för att [registrera en lagerjustering](cloud-edge-warehouse-inventory-adjustment.md) på en lagerstyrningsarbetsbelastning med skalningsenheter.</span><span class="sxs-lookup"><span data-stu-id="d0f17-127">For example, the **Message type** *Request inventory adjustment financial update* is used to create and post a counting journal on the hub when a worker uses the warehouse app to [register an inventory adjustment](cloud-edge-warehouse-inventory-adjustment.md) on a scale unit warehouse management workload.</span></span> <span data-ttu-id="d0f17-128">Eftersom denna specifika process har sitt ursprung i en skalningsenhet visar fältet **Meddelandekö** värdet *Skalningsenhet till nav*.</span><span class="sxs-lookup"><span data-stu-id="d0f17-128">Because this specific process originates from a scale unit, the **Message queue** field will show the value *Scale unit to hub*.</span></span>

<span data-ttu-id="d0f17-129">För denna meddelandetyp registrerar en skalningsenhetsarbetsbelastning meddelandet som en del av en lagerjusteringsfunktion för ett lagerställe.</span><span class="sxs-lookup"><span data-stu-id="d0f17-129">For this message type, a scale unit workload records the message as part of a warehouse app inventory adjustment operation.</span></span> <span data-ttu-id="d0f17-130">Meddelandedata överförs sedan till navet som ett led i samma process som används för [arkitekturen för Commerce Data Exchange](../../commerce/commerce-architecture.md).</span><span class="sxs-lookup"><span data-stu-id="d0f17-130">The message data is then transferred to the hub as part of the same process used for the [Commerce data exchange architecture](../../commerce/commerce-architecture.md).</span></span> <span data-ttu-id="d0f17-131">Meddelandet uppdateras så att **Meddelandestatus** anges som *Köad*.</span><span class="sxs-lookup"><span data-stu-id="d0f17-131">The message will be updated to show **Message state** as *Queued*.</span></span> <span data-ttu-id="d0f17-132">Meddelandeprocessorn försöker sedan att bearbeta meddelandet och uppdaterar **Meddelandestatus** till *Bearbetad* vid slutförande, eller till *Annullerad* vid fel.</span><span class="sxs-lookup"><span data-stu-id="d0f17-132">The message processor then attempts to process the message and updates the **Message state** to *Processed* on success, or *Canceled* on failure.</span></span>

## <a name="view-the-message-log-message-content-and-details"></a><span data-ttu-id="d0f17-133">Visa meddelandelogg, meddelandeinnehåll och detaljerad information</span><span class="sxs-lookup"><span data-stu-id="d0f17-133">View the message log, message content, and details</span></span>

<span data-ttu-id="d0f17-134">Du hittar detaljerad information om ett meddelande genom att markera det i rutnätet och sedan öppna flikarna **Logg** eller **Meddelandeinnehåll** under meddelanderutnätet, där respeltive bearbetningshändelse visas.</span><span class="sxs-lookup"><span data-stu-id="d0f17-134">You can find detailed information about a message by selecting it in the grid and then opening the **Log** or **Message content** tabs under the message grid, where each processing event is shown.</span></span>

<span data-ttu-id="d0f17-135">**Meddelandeinnehållet** vilar på **Meddelandetypen** och kommer därför att hat olika textlängd.</span><span class="sxs-lookup"><span data-stu-id="d0f17-135">The **Message content** depends on the **Message type** and will therefore have different text length.</span></span> <span data-ttu-id="d0f17-136">En normal meddelandetext börjar med **{** och slutar med **}**, odh där emellan finns fältnamn som exempelvis `journalId` följt av en **.** och ett värde som exempelvis *EN-123456*.</span><span class="sxs-lookup"><span data-stu-id="d0f17-136">A typical message content text will start with a **{** and end with a **}** and in between have field names such as `journalId` followed by a **:** and a value such as *USMF-123456*.</span></span>

<span data-ttu-id="d0f17-137">Verktygsfältet på fliken **Logg** innehåller följande knappar:</span><span class="sxs-lookup"><span data-stu-id="d0f17-137">The toolbar on the **Log** tab includes the following buttons:</span></span>

- <span data-ttu-id="d0f17-138">**Logg** – Visar bearbetningsresultaten.</span><span class="sxs-lookup"><span data-stu-id="d0f17-138">**Log** – Displays the processing results.</span></span> <span data-ttu-id="d0f17-139">Detta är särskilt användbart om du vill förstå anledningarna till ett bearbetningsfel för meddelanden där **Bearbetningsresultat** anges som *Misslyckades*.</span><span class="sxs-lookup"><span data-stu-id="d0f17-139">This is especially helpful for understanding the reasons for a processing failure for messages having a **Processing result** of *Failed*.</span></span>
- <span data-ttu-id="d0f17-140">**Bunt** – Flera funktioner för meddelandebearbetning kan köras som en del i samma batchprocess.</span><span class="sxs-lookup"><span data-stu-id="d0f17-140">**Bundle** – Multiple message processing operations can run as part of the same batch process.</span></span> <span data-ttu-id="d0f17-141">Välj den här knappen om du vill visa denna detaljerade information.</span><span class="sxs-lookup"><span data-stu-id="d0f17-141">Select this button to view this detailed data.</span></span> <span data-ttu-id="d0f17-142">Du kan till exempel se om det finns beroenden som kräver att systemet bearbetar vissa meddelanden i en viss sekvens.</span><span class="sxs-lookup"><span data-stu-id="d0f17-142">For example, you can see whether dependencies exist that require the system to process certain messages in a specific sequence.</span></span>

## <a name="message-processor-batch-job"></a><span data-ttu-id="d0f17-143">Batchjobb för meddelandeprocessor</span><span class="sxs-lookup"><span data-stu-id="d0f17-143">Message processor batch job</span></span>

<span data-ttu-id="d0f17-144">När du kör en molnbaserad distribution eller en edge-distribution hämtas batchjobbet för *Meddelandeprocessor* automatiskt när ett nytt meddelande skapas för bearbetning, varför du inte ska behöva schemalägga det här jobbet manuellt.</span><span class="sxs-lookup"><span data-stu-id="d0f17-144">When running a cloud and edge deployment, the *Message processor* batch job will automatically be evoked when a new message is created for processing, so you should not need to schedule this job manually.</span></span>

<span data-ttu-id="d0f17-145">Om det behövs kan du öppna batchjobbet genom att gå till **Systemadministration > Meddelandeprocessor > Meddelandeprocessor**.</span><span class="sxs-lookup"><span data-stu-id="d0f17-145">If necessary, you can access the batch job by going to **System administration > Message  processor > Message processor**.</span></span>

## <a name="manually-process-or-cancel-a-message"></a><span data-ttu-id="d0f17-146">Bearbeta eller avbryta ett meddelande manuellt</span><span class="sxs-lookup"><span data-stu-id="d0f17-146">Manually process or cancel a message</span></span>

<span data-ttu-id="d0f17-147">Om det behövs kan du manuellt bearbeta eller avbryta ett meddelande, beroende på dess aktuella status.</span><span class="sxs-lookup"><span data-stu-id="d0f17-147">If needed, you can manually process or cancel a message, depending on its current state.</span></span> <span data-ttu-id="d0f17-148">Detta gör du genom att markera meddelandet i rutnätet och sedan välja **Bearbeta** eller **Avbryt** i åtgärdsfönstret</span><span class="sxs-lookup"><span data-stu-id="d0f17-148">To do so, select the message in the grid and then select **Process** or **Cancel** on the Action Pane</span></span>

## <a name="set-up-business-events-to-deliver-alerts-for-failed-processing-results"></a><span data-ttu-id="d0f17-149">Ställa in affärshändelser för leverans av notifieringar för misslyckade bearbetningsresultat</span><span class="sxs-lookup"><span data-stu-id="d0f17-149">Set up business events to deliver alerts for failed processing results</span></span>

<span data-ttu-id="d0f17-150">Förutom filtrering av **Meddelandestatus**-värdet *Annullerad* för att söka efter misslyckade meddelanden kan du även konfigurera [Affärshändelser](../../fin-ops-core/dev-itpro/business-events/home-page.md) i navet i syfte att varna dig om misslyckade bearbetningsresultat.</span><span class="sxs-lookup"><span data-stu-id="d0f17-150">In addition to filtering on the **Message state** value *Canceled* to inquire for failed messages, you can set up [Business events](../../fin-ops-core/dev-itpro/business-events/home-page.md) on the hub to alert you to failed processing results.</span></span> <span data-ttu-id="d0f17-151">Du gör detta genom att aktivera affärshändelsen med namnet *Meddelandeprocessormeddelande som bearbetas* på sidan **Katalog för affärshändelser** (**Systemadministration > Inställningar > Affärshändelser > Katalog för affärshändelser**).</span><span class="sxs-lookup"><span data-stu-id="d0f17-151">To do so, activate the business event named *Message processor message processed*  on the **Business events catalog** page (**System administration > Setup > Business events > Business events catalog**).</span></span>

<span data-ttu-id="d0f17-152">Som en del av aktiveringsprocessen får du vägledning när du anger huruvida händelsen är specifik för en eller alla juridiska personer och anger ett **slutpunktsnamn**, som måste definieras först.</span><span class="sxs-lookup"><span data-stu-id="d0f17-152">As part of the activation process, you will be guided to specify whether the event is specific to one or all legal entities and provide an **Endpoint name**, which must be defined first.</span></span>

>[!NOTE]
> <span data-ttu-id="d0f17-153">Om **När en affärshändelse inträffar** anges som *Microsoft Power Automate* (snarare än exempelvis *HTTPS*) kommer **Slutpunktsnamn** automatiskt att skapas i Supply Chain Management baserat på *Microsoft Power Automate*-inställningarna.</span><span class="sxs-lookup"><span data-stu-id="d0f17-153">If **When a Business Event occurs** is set to *Microsoft Power Automate* (rather than *HTTPS*, for example), the **Endpoint name** will automatically be created in Supply Chain Management based on the *Microsoft Power Automate* setup.</span></span>

### <a name="microsoft-power-automate-example"></a><span data-ttu-id="d0f17-154">Microsoft Power Automate-exempel</span><span class="sxs-lookup"><span data-stu-id="d0f17-154">Microsoft Power Automate example</span></span>

<span data-ttu-id="d0f17-155">I detta exempel använder du **När en affärshändelse inträffar** tillsammans med *Microsoft Power Automate* för att skicka e-postmeddelanden som innehåller InfoLog-meddelanden och hyperlänkar för att öppna sidan **Meddelanden i meddelandebearbetaren** för ett specifikt meddelande som misslyckats i navdistributionen.</span><span class="sxs-lookup"><span data-stu-id="d0f17-155">In this example, use **When a Business Event occurs** with *Microsoft Power Automate* sends emails containing InfoLog messages and hyperlinks to open the **Message processor messages** page for a specific failed message on the hub deployment.</span></span> <span data-ttu-id="d0f17-156">Om det behövs kan du lägga till extra logik så att meddelandena skickas parallellt med hjälp av olika kanaler och styra mottagarna utifrån händelsedata.</span><span class="sxs-lookup"><span data-stu-id="d0f17-156">If needed, you can add extra logic to send the notifications in parallel using different channels and control the recipients based on the event data.</span></span>

1. <span data-ttu-id="d0f17-157">I [Power Automate](https://preview.flow.microsoft.com) skapar du ett nytt, automatiserat molnflöde för flödesutlösaren **När en affärshändelse inträffar - Appen Fin & Ops (Dynamics 365)** följt av stegen **Parse JSON** och **Skicka ett e-postmeddelande** enligt följande bild.</span><span class="sxs-lookup"><span data-stu-id="d0f17-157">In [Power Automate](https://preview.flow.microsoft.com), create a new automated cloud flow for the flow trigger **When a Business Event occurs - Fin & Ops App (Dynamics 365)** followed by the **Parse JSON** and **Send an email** steps, as shown in the following illustration.</span></span>

    :::image type="content" source="./media/cloud-edge-power-automate-example1.png" alt-text="Power Automate automatiskt molnbaserat flöde":::

1. <span data-ttu-id="d0f17-159">I steget **När en affärshändelse inträffar** kan du söka efter eller öppna navet **Instans** efter **Kategori** och därefter **Affärshändelse** > *Meddelandeprocessormeddelande som bearbetas* enligt följande bild.</span><span class="sxs-lookup"><span data-stu-id="d0f17-159">In the **When a Business Event occurs** step, you can look up or enter the hub **Instance** following the **Category** and then the **Business event** *Message processor message processed*, as shown in the following illustration.</span></span>

    :::image type="content" source="./media/cloud-edge-power-automate-example2.png" alt-text="Power Automate Steget När en affärshändelse inträffar":::

1. <span data-ttu-id="d0f17-161">För steget **Parse JSON** anger du ett **Schema** som definierar de utökade fälten.</span><span class="sxs-lookup"><span data-stu-id="d0f17-161">For the **Parse JSON** step, enter a **Schema** that defines the extended fields.</span></span> <span data-ttu-id="d0f17-162">Du kan använda alternativet *Hämta schema* på sidan **Katalog för affärshändelser** i Supply Chain Management eller börja genom att klistra in exempelschematexten.</span><span class="sxs-lookup"><span data-stu-id="d0f17-162">You can use the *Download schema* option on the **Business events catalog** page in Supply Chain Management or start by pasting in the example schema text.</span></span> <span data-ttu-id="d0f17-163">Exempeltexten innehåller följande bild.</span><span class="sxs-lookup"><span data-stu-id="d0f17-163">This example text is provided after the following illustration.</span></span>

    :::image type="content" source="./media/cloud-edge-power-automate-example3.png" alt-text="Power Automate Parse JSON-steg":::

    ```json
    {
        "properties": {
            "BusinessEventId": {
                "type": "string"
            },
            "ControlNumber": {
                "type": "integer"
            },
            "EventId": {
                "type": "string"
            },
            "EventTime": {
                "type": "string"
            },
            "MajorVersion": {
                "type": "integer"
            },
            "MessageContent": {
                "type": "string"
            },
            "MessageDestinationCompanyId": {
                "type": "string"
            },
            "MessageDestinationOperationalSiteId": {
                "type": "string"
            },
            "MessageDestinationWarehouseId": {
                "type": "string"
            },
            "MessageDestinationWorkloadName": {
                "type": "string"
            },
            "MessageInfolog": {
                "type": "string"
            },
            "MessageProcessingResult": {
                "type": "string"
            },
            "MessageProcessingResultLabel": {
                "type": "string"
            },
            "MessageProcessorMessagePageUrl": {
                "type": "string"
            },
            "MessageQueue": {
                "type": "string"
            },
            "MessageQueueLabel": {
                "type": "string"
            },
            "MessageSourceCompanyId": {
                "type": "string"
            },
            "MessageSourceOperationalSiteId": {
                "type": "string"
            },
            "MessageSourceWarehouseId": {
                "type": "string"
            },
            "MessageSourceWorkloadName": {
                "type": "string"
            },
            "MessageState": {
                "type": "string"
            },
            "MessageStateLabel": {
                "type": "string"
            },
            "MessageType": {
                "type": "string"
            },
            "MessageTypeLabel": {
                "type": "string"
            },
            "MinorVersion": {
                "type": "integer"
            }
        },
        "type": "object"
    }
    ```

1. <span data-ttu-id="d0f17-165">I steget **Skicka ett e-postmeddelande** kan du välja individuella fält eller börja med att klista in e-postmeddelandets brödtextexemplet i fältet **Brödtext**.</span><span class="sxs-lookup"><span data-stu-id="d0f17-165">In the **Send an email** step, you can select the individual fields or start by pasting the email body example into the **Body** field.</span></span> <span data-ttu-id="d0f17-166">Detta exempel tillhandahålls efter följande bild.</span><span class="sxs-lookup"><span data-stu-id="d0f17-166">This example is provided after the following illustration.</span></span>

    :::image type="content" source="./media/cloud-edge-power-automate-example4.png" alt-text="Power Automate steget skicka ett e-postmeddelande":::

    ```plaintext
    Message queue: @{body('Parse_JSON')?['MessageQueue']}
    Message queue label: @{body('Parse_JSON')?['MessageQueueLabel']}
    Message type: @{body('Parse_JSON')?['MessageQueueType']}
    Message type label: @{body('Parse_JSON')?['MessageQueueTypeLabel']}
    Message content: @{body('Parse_JSON')?['MessageContent']}
    Message state: @{body('Parse_JSON')?['MessageState']}
    Message state label: @{body('Parse_JSON')?['MessageStateLabel']}
    Message processing result: @{body('Parse_JSON')?['MessageProcessingResult']}
    Message processing result label: @{body('Parse_JSON')?['MessageProcessingResultLabel']}
    Message infolog: @{body('Parse_JSON')?['MessageInfolog']}
    Message source company ID: @{body('Parse_JSON')?['MessageSourceCompanyId']}
    Message source workload name: @{body('Parse_JSON')?['MessageSourceWorkloadName']}
    Message source site ID: @{body('Parse_JSON')?['MessageSourceOperationalSiteId']}
    Message source warehouse ID: @{body('Parse_JSON')?['MessageSourceWarehouseId']}
    Message destination company ID: @{body('Parse_JSON')?['MessageDestinationCompanyId']}
    Message destination workload name: @{body('Parse_JSON')?['MessageDestinationWorkloadName']}
    Message destination site ID: @{body('Parse_JSON')?['MessageDestinationOperationalSiteId']}
    Message destination warehouse ID: @{body('Parse_JSON')?['MessageDestinationWarehouseId']}
    Message processor message page URL: @{body('Parse_JSON')?['MessageProcessorMessagePageUrl']}
    ```

1. <span data-ttu-id="d0f17-168">När du sparar affärshändelsen aktiveras den automatiskt och kan användas som en del av Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="d0f17-168">When you save the business event, it will automatically be activated and ready to use as part of Supply Chain Management.</span></span>
