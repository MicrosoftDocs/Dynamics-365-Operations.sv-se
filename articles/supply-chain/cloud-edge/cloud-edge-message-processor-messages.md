---
title: Meddelandeprocessormeddelanden
description: Denna artikel innehåller information om funktionen för meddelandebearbetning för skalningsenhetsarbetsbelastningar.
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
ms.openlocfilehash: a5f8d48ba697df389150f70ac159e690156de33b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8893625"
---
# <a name="message-processor-messages"></a>Meddelandeprocessormeddelanden

[!include [banner](../includes/banner.md)]

Meddelanden i meddelandeprocessorn används när molnbaserade enheter och kantskalningsenheter körs för [arbetsbelastningar inom tillverkning](cloud-edge-workload-manufacturing.md) samt [arbetsbelastningar inom Warehouse managements](cloud-edge-workload-warehousing.md).

Utbyggnadsmiljöerna för hubb och skalningsenhet utbyter en stor mängd data för att förbli synkroniserade. En del av de utbytta uppgifterna kommer att utlösa ytterligare logik i *meddelandeprocessorn*. Du kan visa meddelanden som bearbetats av meddelandeprocessorn genom att gå till **Systemadministration > Meddelandeprocessor > Meddelanden i meddelandeprocessorn**.

## <a name="message-grid-columns-and-filters"></a>Kolumner och filter i meddelanderutnät

Med hjälp av fälten högst upp på sidan **Meddelanden i meddelandeprocessorn** kan du hitta eventuella meddelanden som du letar efter. De flesta filter matchar kolumnrubrikerna i meddelanderutnätet. Följande filter och kolumnrubriker är tillgängliga:

- **Meddelandetyp** – Anger meddelandetypen.
- **Meddelandekö** – Anger namnet på kön där meddelandet ska bearbetas. Följande köer finns:
  - *Skalningsenhet till hubb*
  - *Hubb till skalningsenhet för lagerställekörning*
  - *Hubb till skalningsenhet för produktionskörning*
- **Meddelandestatus** – Anger status för meddelandet. Följande statuslägen finns:
  - *Köad* – Meddelandet är klart att bearbetas av meddelandeprocessorn.
  - *Bearbetades* – Meddelandet har bearbetats av meddelandeprocessorn.
  - *Annullerat* – Meddelandet bearbetades men bearbetningen misslyckades.
- **Meddelandeinnehåll** – Detta filter genomför en fulltextsökning av meddelandeinnehåll. (meddelandeinnehållet visas inte i rutnätet). Filtret behandlar de flesta specialtecken (exempelvis "-") som blanksteg, och behandlar alla blanksteg som booleska OR-operatorer. Till exempel betyder detta att om du söker efter ett specifikt värde som är lika med `journalid` "USMF-123456", så hittar systemet alla meddelanden som innehåller "USMF" eller "123456", vilket troligen lär bli en lång lista. Därför är det bättre att enbart ange "123456" eftersom detta returnerar mer specifika resultat.

## <a name="example-message-type-request-inventory-adjustment-financial-update"></a>Exempel på meddelandetyp: Begär ekonomisk uppdatering av lagerjustering

Till exempel används **meddelandetypen** *Begär ekonomisk uppdatering av lagerjustering* för att skapa och bokföra en inventeringsjournal i hubben när en medarbetare använder lagerställeappen för att [registrera en lagerjustering](cloud-edge-warehouse-inventory-adjustment.md) på en Warehouse managementsarbetsbelastning med skalningsenheter. Eftersom denna specifika process har sitt ursprung i en skalningsenhet visar fältet **Meddelandekö** värdet *Skalningsenhet till nav*.

För denna meddelandetyp registrerar en skalningsenhetsarbetsbelastning meddelandet som en del av en lagerjusteringsfunktion för ett lagerställe. Meddelandedata överförs sedan till hubben som ett led i samma process som används för [arkitekturen för Commerce Data Exchange](../../commerce/commerce-architecture.md). Meddelandet uppdateras så att **Meddelandestatus** anges som *Köad*. Meddelandeprocessorn försöker sedan att bearbeta meddelandet och uppdaterar **Meddelandestatus** till *Bearbetad* vid slutförande, eller till *Annullerad* vid fel.

## <a name="view-the-message-log-message-content-and-details"></a>Visa meddelandelogg, meddelandeinnehåll och detaljerad information

Du hittar detaljerad information om ett meddelande genom att markera det i rutnätet och sedan öppna flikarna **Logg** eller **Meddelandeinnehåll** under meddelanderutnätet, där respeltive bearbetningshändelse visas.

**Meddelandeinnehållet** vilar på **Meddelandetypen** och kommer därför att hat olika textlängd. En normal meddelandetext börjar med **{** och slutar med **}**, odh där emellan finns fältnamn som exempelvis `journalId` följt av en **.** och ett värde som exempelvis *EN-123456*.

Verktygsfältet på fliken **Logg** innehåller följande knappar:

- **Logg** – Visar bearbetningsresultaten. Detta är särskilt användbart om du vill förstå anledningarna till ett bearbetningsfel för meddelanden där **Bearbetningsresultat** anges som *Misslyckades*.
- **Bunt** – Flera funktioner för meddelandebearbetning kan köras som en del i samma batchprocess. Välj den här knappen om du vill visa denna detaljerade information. Du kan till exempel se om det finns beroenden som kräver att systemet bearbetar vissa meddelanden i en viss sekvens.

## <a name="message-processor-batch-job"></a>Batchjobb för meddelandeprocessor

När du kör en distribuerad hybridtopologi med skalningsenheter hämtas batchjobbet för *Meddelandeprocessor* automatiskt när ett nytt meddelande skapas för bearbetning, varför du inte ska behöva schemalägga det här jobbet manuellt.

Om det behövs kan du öppna batchjobbet genom att gå till **Systemadministration > Meddelandeprocessor > Meddelandeprocessor**.

## <a name="manually-process-or-cancel-a-message"></a>Bearbeta eller avbryta ett meddelande manuellt

Om det behövs kan du manuellt bearbeta eller avbryta ett meddelande, beroende på dess aktuella status. Detta gör du genom att markera meddelandet i rutnätet och sedan välja **Bearbeta** eller **Avbryt** i åtgärdsfönstret

## <a name="set-up-business-events-to-deliver-alerts-for-failed-processing-results"></a>Ställa in affärshändelser för leverans av notifieringar för misslyckade bearbetningsresultat

Förutom filtrering av **Meddelandestatus**-värdet *Annullerad* för att söka efter misslyckade meddelanden kan du även konfigurera [Affärshändelser](../../fin-ops-core/dev-itpro/business-events/home-page.md) i hubben i syfte att varna dig om misslyckade bearbetningsresultat. Du gör detta genom att aktivera affärshändelsen med namnet *Meddelandeprocessormeddelande som bearbetas* på sidan **Katalog för affärshändelser** (**Systemadministration > Inställningar > Affärshändelser > Katalog för affärshändelser**).

Som en del av aktiveringsprocessen får du vägledning när du anger huruvida händelsen är specifik för en eller alla juridiska personer och anger ett **slutpunktsnamn**, som måste definieras först.

>[!NOTE]
> Om **När en affärshändelse inträffar** anges som *Microsoft Power Automate* (snarare än exempelvis *HTTPS*) kommer **Slutpunktsnamn** automatiskt att skapas i Supply Chain Management baserat på *Microsoft Power Automate*-inställningarna.

### <a name="microsoft-power-automate-example"></a>Microsoft Power Automate-exempel

I detta exempel använder du **När en affärshändelse inträffar** tillsammans med *Microsoft Power Automate* för att skicka e-postmeddelanden som innehåller InfoLog-meddelanden och hyperlänkar för att öppna sidan **Meddelanden i meddelandebearbetaren** för ett specifikt meddelande som misslyckats i navdistributionen. Om det behövs kan du lägga till extra logik så att meddelandena skickas parallellt med hjälp av olika kanaler och styra mottagarna utifrån händelsedata.

1. I [Power Automate](https://preview.flow.microsoft.com) skapar du ett nytt, automatiserat molnflöde för flödesutlösaren **När en affärshändelse inträffar - Appen Fin & Ops (Dynamics 365)** följt av stegen **Parse JSON** och **Skicka ett e-postmeddelande** enligt följande bild.

    :::image type="content" source="./media/cloud-edge-power-automate-example1.png" alt-text="Automatiskt Power Automate-molnflöde.":::

1. I steget **När en affärshändelse inträffar** kan du söka efter eller öppna hubben **Instans** efter **Kategori** och därefter **Affärshändelse** > *Meddelandeprocessormeddelande som bearbetas* enligt följande bild.

    :::image type="content" source="./media/cloud-edge-power-automate-example2.png" alt-text="Power Automate Steget När en affärshändelse inträffar.":::

1. För steget **Parse JSON** anger du ett **Schema** som definierar de utökade fälten. Du kan använda alternativet *Hämta schema* på sidan **Katalog för affärshändelser** i Supply Chain Management eller börja genom att klistra in exempelschematexten. Exempeltexten innehåller följande bild.

    :::image type="content" source="./media/cloud-edge-power-automate-example3.png" alt-text="Power Automate Parsa JSON-steg.":::

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

1. I steget **Skicka ett e-postmeddelande** kan du välja individuella fält eller börja med att klista in e-postmeddelandets brödtextexemplet i fältet **Brödtext**. Detta exempel tillhandahålls efter följande bild.

    :::image type="content" source="./media/cloud-edge-power-automate-example4.png" alt-text="Power Automate-steget Skicka ett e-postmeddelande.":::

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

1. När du sparar affärshändelsen aktiveras den automatiskt och kan användas som en del av Supply Chain Management.
