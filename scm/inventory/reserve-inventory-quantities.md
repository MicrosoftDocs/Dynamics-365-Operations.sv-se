---
title: Reservera lagerkvantiteter
description: "I det här avsnittet beskrivs de olika alternativ som är tillgängliga för att reservera lager."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: InventModelGroup
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 207264
ms.assetid: 47537e4f-cdf6-4813-96fd-c945b2dfe9d4
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: f77012e7b64b7f153103e9bbe91e8ded202b509a
ms.openlocfilehash: 7361b2e04376284238c8c9b1f91d03d18b121d24
ms.lasthandoff: 03/31/2017


---

# <a name="reserve-inventory-quantities"></a>Reservera lagerkvantiteter

I det här avsnittet beskrivs de olika alternativ som är tillgängliga för att reservera lager.

Du kan reservera lagerkvantiteter automatiskt för en viss försäljningsorder. Detta innebär att reserverade lager inte kan hämtas från lagerstället för andra order om inte lagerreservationen, eller delar av den, annulleras.

Det finns flera skäl att reservera lager:
-   Först beställd, först levererad, vilket innebär att kunder får tillgängliga artiklar i samma ordning som de beställer.
-   Brist på artiklar på grund av lång eller okänd leveranstid från leverantören. Det kan vara en god idé att försäkra sig om att vissa kunder eller order får leverans av de första tillgängliga artiklarna.
-   Vissa kunder och vissa ordertyper har högst prioritet för leverans.
-   Artiklar med serie- eller batchnummer. Du kan markera vissa artiklar som har levererats eller kommer att levereras till vissa order.
-   Specialbeställda artiklar som har reserverats för vissa order.
-   Tillverkningsorder. Du kan till exempel markera artiklar som produceras för och justeras till specifika order.

Lager kan reserveras automatiskt när en ny orderrad skapas, eller manuellt på enskilda order. Det går också att reservera lager vid olika faser i en process. Endast produkter i lager kan reserveras. Tjänster kan inte reserveras eftersom det inte finns någon lagerbehållning. Både fysisk lagerbehållning och beställt, men ännu inte inkommet, lager kan reserveras. Om en större kvantitet reserveras än lagerbehållningen innehåller, visas ett meddelande om att det inte går att reservera en så stor kvantitet. Du kan då välja att antingen reservera kvantiteten ändå eller att ändra den beställda kvantiteten. Kvantiteten kan antingen reserveras eller ändras. Om fler artiklar än de som är tillgängliga reserveras, täcks bristen nästa gång artiklar finns tillgängliga för leverans.

## <a name="inventory-reservation-policies"></a>Policyer för lagerreservation
Policyer för lagerreservation anges på sidan **Item model groups**, sidan **Inventory and warehouse management parameters**, samt på sidan **Production parameters**.
### <a name="policies-on-the-item-model-groups-page"></a>Policyer på sidan Item model groups

Avsnittet **Lagerpolicyer** innehåller följande reservationspolicyer.
|                         |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|-------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Reservationspolicy**  | **Beskrivning**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| FIFO-datumkontrollerad    | Om du väljer alternativet **FIFO date-controlled**, kommer lagerreservationen att styras av ett sorteringsdatum i enlighet med bästa FIFO-princip. En batch reserveras baserat på det tidigaste datumet för inleverans av artiklar, enligt principen först in-först ut (FIFO).                                                                                                                                                                                                                                                                       |
| Bakåt från transportdatum | Det här alternativet blir tillgängligt först när du väljer alternativet **FIFO date-controlled**. Om du väljer **Backward from ship date** reserveras lager bakåt från önskat leveransdatum enligt principen sist in, först ut (LIFO). Om inga inleveranser är tillgängliga före leveransdatum används en FIFO-reservation.                                                                                                                                                                                                           |
| Reservering av artikelförsäljning  | Bestämmer om artikelreservation sker manuellt eller automatiskt. Om reservation sker automatiskt kommer lager att reserveras när orderrader skapas. Det är möjligt att skapa reservationer på artikelnummernivå för strukturlistor (alternativet **Automatic**), eller för individuella element i en strukturlista (alternativet **Explosion**). Standardvärdet för **artikel förs.reservation** ärvas från **parametrar för kundreskontra.** På den här sidan har värdet i fältet Reservation i den **standardvärden för försäljning****avsnitt** på de **allmänna** fliken. |
| Urval från samma batch    | Samma batchreservation gör att du kan du reservera lager för en försäljningsorderrad mot en enda lagerbatch. Om du vill använda detta alternativ måste du också ange alternativet **Consolidate requirement** som **Yes**. Det finns ytterligare inställningar som krävs för spårningsdimensionsgruppen och lagringsdimensionsgruppen. Mer information finns i [Reserving the same batch for a sales order](../sales-marketing/reserve-same-batch-sales-order.md).                                                          |
| Konsolidera behov | Detta alternativ liknar alternativet **Same batch selection**, och det konsoliderar lager som har reserverats för försäljningsorderrader till ett enskilt behov.                                                                                                                                                                                                                                                                                                                                                                                      |
| FEFO-datumkontrollerad    | Detta alternativ låter dig reservera batchar som närmar sig sina utgångsdatum eller bäst före-datum. Du måste också ange fältet **Pick criteria** som antingen **Expiration date** eller **Best before date**.                                                                                                                                                                                                                                                                                                                              |

#### <a name="example-for-fifo-date-controlled-and-backward-from-ship-date"></a>Exempel för FIFO-datumkontroll och bakåt från leveransdatum

I det här exemplet finns lagerbehållningen för artikelnummer A för tre olika batchnummer.
| Artikelnummer | Batchnummer | Kvantitet | Datum             |
|-------------|--------------|----------|------------------|
| A           | 1 000         | 5        | 2 februari 2016 |
| A           | 1001         | 3        | 1 januari 2016  |
| A           | 1002         | 7        | 3 mars 2016    |

En försäljningsorder som ska reserveras automatiskt och levereras 2016-04-04 reserverar följande batch:
-   Om både kryssrutan **FIFO date-controlled** och kryssrutan **Backward from ship date** rensas, reserveras batch 1000 eftersom detta är batchen med lägst nummer.
-   Om kryssrutan **FIFO date-controlled** väljs och **Bakåt från transportdatum** markerad, reserveras batch 1001 eftersom den har tidigast inleveransdatum (FIFO).
-   Om både kryssrutan **FIFO date-controlled** och kryssrutan **Backward from ship date** väljs, reserveras batch 1002 eftersom detta är batchinleveransen närmast försäljningsorderns leveransdatum.

### <a name="policies-on-the-inventory-and-warehouse-management-parameter-page"></a>Policyer på parametersidan för lager- och lagerställehantering

Det finns två alternativ som är relaterade till reservationer på sidan **Inventory and warehouse management parameters**:
-   Alternativet **Reserve ordered items** på fliken **General** låter dig reservera artikelinleveranser som beställs mot artikelproblem i Accounts receivable, Project management and accounting, samt Production control. Om du avmarkerar detta alternativ kan du bara reservera artiklar som fysiskt har mottagits. Om en viss artikel har ställts in för att acceptera negativt lager, är detta fält inte relevant.
-   Alternativet **Reserve items automatically** på fliken **Transport** bestämmer standardinställningen, om artiklar reserveras automatiskt för överföringsorder. Standardinställningen kan åsidosättas på enskilda överföringsorder.

### <a name="inventory-reservation-policies-on-the-production-parameters-page"></a>Lagerreservationpolicyer på sidan för produktparametrar

Värdet i fältet **Reservation** i fliken **General** på sidan **Production parameters** avgör den förvalda punkten i produktionsprocessen då lager bör reserveras. Till exempel kan lager reserveras när arbete schemaläggs eller när jobbet startas.


