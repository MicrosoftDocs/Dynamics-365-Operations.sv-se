---
title: "Order – översikt"
description: "Det här avsnittet innehåller information om kundorder i Retail Modern POS (MOPS). Kundorder kallas specialorder. Avsnittet innehåller en beskrivning av de relevanta parametrarna och transaktionsflöden."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 260594
ms.assetid: 6fc835ef-d62e-4f23-9d49-50299be642ca
ms.search.region: global
ms.search.industry: Retail
ms.author: anpurush
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 2f466dfe53ccf0be15ed0793b4a6dd371bdacc0d
ms.lasthandoff: 03/31/2017


---

# <a name="customer-orders-overview"></a>Order – översikt

Det här avsnittet innehåller information om kundorder i Retail Modern POS (MOPS). Kundorder kallas specialorder. Avsnittet innehåller en beskrivning av de relevanta parametrarna och transaktionsflöden.

I en butik värld omni kanaler finns många återförsäljare möjligheten att kunden order eller specialorder för att uppfylla kraven för olika produkter och utförande. Här följer några vanliga scenarier:

-   En kund vill ha produkter som skall levereras till en specifik adress på ett visst datum.
-   En kund vill hämta produkter från en butik eller en plats som skiljer sig från butiken eller plats där kunden har köpt varorna.
-   En kund vill ha någon annan för produkter som kunden har köpt.

Återförsäljare kan du också använda kundorder minimera förlorade försäljningar som lager fel medföra annars eftersom varorna levereras eller Plockad vid en annan tidpunkt eller plats.

## <a name="set-up-customer-orders"></a>Skapa kundorder
Här är några av de parametrar som anges på den **RETUR** sidan för att definiera hur kundorder är uppfyllda:

-   **Standard insättning procent** – ange det belopp som kunden måste betala som en insättning innan en order kan bekräftas. Standardbeloppet insättning beräknas som en procentandel av värdet för ordern. Beroende på behörighet, associera en butik kan eventuellt åsidosätta beloppet med **Insättningsåsidosättning**.
-   **Annulleringsavgift i procent** – om en avgift används när kundorder annulleras, ange hur lång den omkostnaden.
-   **Kod för Annulleringsavgift** – om en avgift används när kundorder annulleras att tillägget visas under en avgiftskod på försäljningsorder i Microsoft Dynamics AX. Använd denna parameter om du vill definiera tilläggskoden annulleringen.
-   **Leveransavgiftskoden** – återförsäljare kan debiteras en extra avgift för leverans av varor till en kund. Hur lång den fraktkostnaden återspeglas under en avgiftskod på försäljningsordern i Dynamics AX. Använd denna parameter för att mappa leveransavgift till fraktkostnader på kundens beställning.
-   **Återbetala leveransavgifter** – ange om leveransavgifter som associeras med kundorder återbetalas.
-   **Maxbelopp utan godkännande** – leveransavgifter om återbetalning, ange maxbelopp för tillägget bidrag över returorder. Om detta värde överskrids krävs åsidosättningen manager för att fortsätta med bidraget. Återbetalning av leveransavgifter kan överstiga det belopp som ursprungligen har betalats för följande scenarier:
    -   Tillägg tillämpas på nivå försäljningsorderrubriken och när en produktlinje samt ett antal returneras det högsta bidraget för fraktkostnader som tillåts för produkterna och kvantiteten inte kan fastställas på ett sätt som passar alla butikskunder.
    -   Leveransavgifterna infaller efter alla förekomster av transportföretaget. Om en kund lämnar tillbaka varor flera gånger och återförsäljarens principen anger att återförsäljaren ska stå för RETUR leveransavgifterna, att RETUR fraktkostnaderna vara större än faktiska fraktkostnaderna.

## <a name="transaction-flow-for-customer-orders"></a>Transaktionsflöde för kundorder
### <a name="create-a-customer-order-in-retail-modern-pos"></a>Skapa kundorder i Modern Retail POS

1.  Lägg till en kund i transaktionen.
2.  Lägga till produkter till kundvagnen.
3.  Klicka på **skapa kundorder**, och välj ordertypen. Ordertypen kan antingen vara **kundordern** eller **offert**.
4.  Klicka på **transport som valts** eller **leverera allt** du vill sända produkter till en adress på kundkontot, ange Begärt speditionsdatum och fraktkostnader.
5.  Klicka på **valt upphämtningsdatum** eller **vill hämta alla** att välja produkter som hanteras från den aktuella butiken eller en annan butik vid ett visst datum.
6.  Inkassering av Insättningsbeloppet, om en säkerhet krävs.

### <a name="edit-an-existing-customer-order"></a>Redigera en befintlig kundorder

1.  Klicka på startsidan, **söka efter en order**.
2.  Hitta och markera ordern som du vill redigera. Längst ner på sidan klickar du på den **redigera**.

### <a name="pick-up-an-order"></a>Hämta en order

1.  Klicka på startsidan, **söka efter en order**.
2.  Markera ordern som du vill hämta. Längst ner på sidan klickar du på **plocka och packa**.
3.  Klicka på **hämtar**.

### <a name="cancel-an-order"></a>Annullera en order

1.  Klicka på startsidan, **söka efter en order**.
2.  Markera ordern som du vill avbryta. Längst ner på sidan klickar du på **Avbryt**.

#### <a name="create-a-return-order"></a>Skapa en returorder

1.  Klicka på startsidan, **söka efter en order**.
2.  Markera ordern som du vill returnera fakturan för ordern och välj Välj produktlinje bestämmelser ska returneras.
3.  Längst ner på sidan klickar du på den **returorder**.

## <a name="asynchronous-transaction-flow-for-customer-orders"></a>Asynkrona transaktionsflöde för kundorder
Kundorder kan skapas från klienten (PO) för försäljning punkt i antingen synkront eller asynkront läge.

### <a name="enable-customer-orders-to-be-created-in-asynchronous-mode"></a>Aktivera kundorder skapas i asynkrona läge

1.  I Dynamics AX klickar du på **butik och handel**&gt;**kanal**&gt;**POS inställningar**&gt;**POS profil**&gt;**Funktionsprofiler**.
2.  I den **allmänna** på snabbfliken ställa den **skapa kundorder läget asynkrona** att **Ja**.

När den **skapa kundorder läget asynkrona** är inställt på **Ja**, kundorder skapas alltid asynkrona läget, även om detaljhandlare Transaction Service (RTS) är tillgänglig. Om du väljer det här alternativet **nr**, kundorder skapas alltid i synkront läge med hjälp av RTS. När en order skapas asynkrona läget de hämtas och infogas i Dynamics AX genom att dra P-jobb. Motsvarande försäljningsorder skapas i Dynamics AX när **synkronisera order** körs antingen manuellt eller via en batchprocess.

<a name="see-also"></a>Se även
--------

[Kombinerade kundorder](hybrid-customer-orders.md)


