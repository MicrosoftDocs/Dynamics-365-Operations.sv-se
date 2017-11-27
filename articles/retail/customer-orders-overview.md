---
title: "Kundorderöversikt"
description: "Det här avsnittet innehåller information om kundorder i Retail Modern POS (MOPS). Kundorder kallas även specialorder. Avsnittet innehåller en beskrivning av relaterade parametrar och transaktionsflöden."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 260594
ms.assetid: 6fc835ef-d62e-4f23-9d49-50299be642ca
ms.search.region: global
ms.search.industry: Retail
ms.author: anpurush
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: ce6774ede836eb29e6ef2cd8d4baa9efb931020c
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="customer-orders-overview"></a>Kundorderöversikt

[!include[banner](includes/banner.md)]


Det här avsnittet innehåller information om kundorder i Retail Modern POS (MOPS). Kundorder kallas även specialorder. Avsnittet innehåller en beskrivning av relaterade parametrar och transaktionsflöden.

I en handelsvärld kännetecknad av omnikanaler erbjuder många återförsäljare möjlighet till kundorder (eller specialorder) för att uppfylla kraven för olika produkter och utföranden. Här följer några vanliga scenarier:

-   En kund vill att produkterna ska levereras till en specifik adress på ett visst datum.
-   En kund vill hämta produkter från en butik eller en plats som skiljer sig från den butiken eller plats där kunden har köpt produkterna.
-   En kund vill ha någon annan ska hämta produkterna som kunden har köpt.

Återförsäljare använder också kundorder för att minimera förlorade försäljningar som lagerfel annars kan medföra, detta eftersom varorna kan levereras eller avhämtas vid en annan tidpunkt eller på en annan plats.

## <a name="set-up-customer-orders"></a>Skapa kundorder
Här följer några av de parametrar som kan anges på sidan **Handelsparametrar** för att definiera hur kundorder uppfylls:

-   **Standardinsättningsprocent** – Ange det belopp som kunden måste betala som en insättning innan en order kan bekräftas. Standardinsättningsbeloppet anges som en procentandel av ordervärdet. Beroende på behörighet kan en butiksmedarbetare kringgå beloppet genom att använda funktionen **Insättningsåsidosättning**.
-   **Annulleringsavgift i procent** – Om en avgift ska användas när en kundorder annulleras, ange då avgiftsbeloppet.
-   **Kod för annulleringsavgift** – Om en avgift används när kundorder annulleras, kommer denna avgift att återspeglas under en avgiftskod på försäljningsordern. Använd denna parameter om du vill definiera avgiftskoden för annulleringen.
-   **Leveransavgiftskod** – Återförsäljare kan debitera en extra avgift för leverans av varor till en kund. Leveransavgiften återspeglas under en avgiftskod på försäljningsordern. Använd denna parameter för att mappa leveransavgiftskoden till fraktkostnader på kundordern.
-   **Återbetala leveransavgifter** – Ange om leveransavgifter som associeras med en kundorder kan återbetalas.
-   **Maxbelopp utan godkännande** – Om leveransavgifter kan återbetalas, ange då maxbelopp för återbetalning av leveransavgifter för returorder. Om detta värde överskrids krävs åsidosättning utförd av chef för att fortsätta med återbetalningen. Återbetalning av leveransavgifter kan överstiga det ursprungligen betalade beloppet i följande scenarier:
    -   Avgifter tillämpas på nivån för försäljningsorderrubrik, och när en viss kvantitet av en produktlinje returneras, kan maxbeloppet för återbetalning av leveranskostnader som tillåts för produkterna och kvantiteten inte fastställas på ett sätt som passar alla butikskunder.
    -   Leveransavgifterna infaller efter alla leveransförekomster. Om en kund returnerar varor flera gånger och återförsäljarens policy anger att återförsäljaren ska stå för kostnaderna för returleveranser, kommer kostnaderna för returleveranser att överstiga de faktiska leveranskostnaderna.

## <a name="transaction-flow-for-customer-orders"></a>Transaktionsflöde för kundorder
### <a name="create-a-customer-order-in-retail-modern-pos"></a>Skapa en kundorder i Retail Modern POS

1.  Lägg till en kund i transaktionen.
2.  Lägg till produkter i kundvagnen.
3.  Klicka på **Skapa kundorder** och välj sedan ordertypen. Ordertypen kan antingen vara **Kundorder** eller **Offert**.
4.  Klicka på **Leverera val** eller **Leverera alla** om du vill sända produkterna till en adress på kundkontot, ange begärt speditionsdatum och fraktkostnaderna.
5.  Klicka på **Hämta valda** eller **Hämta alla** för att välja produkter som hämtas från den aktuella butiken eller en annan butik vid ett visst datum.
6.  Inkassera av insättningsbeloppet, om en deposition krävs.

### <a name="edit-an-existing-customer-order"></a>Redigera en befintlig kundorder

1.  Klicka på **Hitta en order** på startsidan.
2.  Hitta och markera den order som du vill redigera. Klicka på **Redigera** längst ner på sidan.

### <a name="pick-up-an-order"></a>Hämta en order

1.  Klicka på **Hitta en order** på startsidan.
2.  Välj den order som ska hämtas. Klicka på **Hämtning och paketering** längst ner på sidan.
3.  Klicka på **Hämta**.

### <a name="cancel-an-order"></a>Avbryt en order

1.  Klicka på **Hitta en order** på startsidan.
2.  Markera ordern som ska avbrytas. Klicka på **Avbryt** längst ner på sidan.

#### <a name="create-a-return-order"></a>Skapa en returorder

1.  Klicka på **Hitta en order** på startsidan.
2.  Markera den order som du vill returnera, välj fakturan för ordern och välj sedan produktlinje för de varor som ska returneras.
3.  Klicka på **Returnera order** längst ner på sidan.

## <a name="asynchronous-transaction-flow-for-customer-orders"></a>Asynkront transaktionsflöde för kundorder
Kundorder kan skapas från kassaklienten i antingen synkront eller asynkront läge.

### <a name="enable-customer-orders-to-be-created-in-asynchronous-mode"></a>Aktivera skapande av kundorder i asynkront läge

1.  Klicka på **Butik** &gt; **Kanalinställningar** &gt; **Kassainställningar** &gt; **Kassaprofil** &gt; **Funktionsprofiler**.
2.  I snabbfliken **Allmänt** anger du alternativet för **Skapa kundorder i asynkront läge** som **Ja**.

När alternativet **Skapa kundorder i asynkront läge** är inställt på **Ja**, skapas kundorder alltid i asynkront läge, även om tjänsten för handelstransaktioner (Retail Transaction Service, RTS) är tillgänglig. Om du anger detta alternativ som **Nej**, skapas kundorder alltid i synkront läge med hjälp av RTS. När kundorder skapas i asynkront läget hämtas och infogas de i Retail genom hämtningsjobb. Motsvarande försäljningsorder skapas i Retail när **Synkronisera order** körs antingen manuellt eller via en batchprocess.

<a name="see-also"></a>Se även
--------

[Hybridkundorder](hybrid-customer-orders.md)




