---
title: Använd batchdispositionskoder när du vill markera batchar som tillgängliga eller inte tillgängliga
description: I den här artikeln beskrivs hur du ställer in och använder batchdispositionskoder för att markera batchar som tillgängliga eller inte är tillgängliga för användning i huvudplanering, reservation, plockning och/eller leverans.
author: t-benebo
ms.date: 09/16/2022
ms.topic: article
ms.search.form: PdsDispositionMaster, InventBatch
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-09-16
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: cfb0743a573550de93d75063df517e0c143f2568
ms.sourcegitcommit: 20ce54cb40290dd116ab8b157c0a02d6757c13f5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/20/2022
ms.locfileid: "9542478"
---
# <a name="use-batch-disposition-codes-to-mark-batches-as-available-or-unavailable"></a>Använd batchdispositionskoder när du vill markera batchar som tillgängliga eller inte tillgängliga

I denna artikel beskrivs hur du konfigurerar och använder *batchdispositionskoder*. Varje batchdispositionskod har status *Disponibel* eller *Inte tillgänglig*. Du tilldelar batchdispositionskoder till lagerbatchar för att ange om varje batch är tillgänglig för huvudplanering, reservation, plockning och/eller leverans.

Om du vill använda batchdispositionskoder måste du ställa in koderna och tilldela dem till de batchar du vill hantera.

## <a name="set-up-batch-disposition-codes"></a>Ställ in batchdispositionskoder

Du måste ställa in varje batchdispositionskod som du vill använda i systemet. Du kan skapa så många koder som du vill. (Du kan till exempel skapa koder för att identifiera de olika anledningarna till varför en batch kan vara tillgänglig eller inte). Det finns dock ofta bara två koder: en för *tillgänglig* och en för *otillgänglig*. Du kan också skapa anpassade koder som aktiverar en batch som kan användas för vissa åtgärder men inte för andra.

Följ dessa steg för att ställa in batchdispositionskoder.

1. Gå till **Lagerhantering \> Inställningar \> Batch \> Batchdispositionshuvud**.
1. Sidan **Batchdispositionshuvud** anger dina aktuella batchdispositionskoder och låter dig skapa, ta bort och redigera dem. Gör något av följande:

    - Om du vill redigera en befintlig kod markerar du den i listfönstret.
    - Om du vill skapa en ny kod väljer du **Ny** i åtgärdsfönstret.

1. Ställ in följande fält i rubriken för den nya eller valda koden:

    - **Batchdispositionskod** – Ange visningsnamnet för koden.
    - **Beskrivning** – Beskriv hur koden ska användas.
    - **Batchdispositionsstatus** – Välj status som gäller för batchar som koden har tilldelats till:

        - *Otillgänglig* – Batcharna kan inte användas för huvudplanering, reservationer, plockning eller leverans. När du väljer detta värde kommer alla alternativ för **Blockera** på snabbfliken **Inställning** anges till *Ja* och alla alternativ för **Nettoberäkning** anges till *Nej*. Du kan dock ändra vissa av de här inställningarna om du vill lägga till undantag.
        - *Tillgänglig* – Batcharna kan inte användas för huvudplanering, reservationer, plockning och/eller leverans. När du väljer detta värde kommer alla alternativ för **Blockera** på snabbfliken **Inställning** anges till *Nej* och alla alternativ för **Nettoberäkning** anges till *Ja*. Inställningarna är skrivskyddade när fältet **Batchdispositionsstatus** är *tillgängligt*.

1. Om du ställer in fältet **Batchdispositionsstatus** till *Inte tillgängligt*, du kan anpassa blockstatusen för varje operation (reservera, plocka och skicka) för varje typ av beställning (försäljning, överföring och produktion). För tillverkningsorder kan du välja att spärra eller ta bort spärren för produktionsplockjournalen. Du kan också välja att spärra eller ta bort spärren för huvudplanering. Med alternativen på snabbflikarna **inställningar** kan du spärra eller ta bort spärren för varje operation efter behov. Ange alternativet **Nettoberäkning** till *Ja* vill aktivera huvudplanering, eller ange *Nej* för att blockera huvudplaneringen.

## <a name="assign-batch-disposition-codes-to-batches"></a>Tilldela batchdispositionskoder till batchar

När du har definierat de batchdispositionskoder du behöver, följer du dessa steg och tilldelar dem till batchar.

1. Gå till **Lagerstyrning \> Inställningar \> Lager \> Batchar**.
1. Välj en eller flera batchar som du vill tilldela en batchdispositionskod till.
1. I åtgärdsrutan på fliken **Återställ**, välj **Återställ batchdispositionskod**.
1. I dialogrutan **Ändra begränsningarna för lagerbatchen**, ange fältet **Ny batchdispositionskod** till namnet på koden som du vill tilldela.
1. Välj **OK** för att tillämpa den nya inställningen och spara ändringen.

    På sidan **Batchar** uppdateras värdena i **batchdispositionskoden** och kolumnerna för **batchdispositionsstatus** så att de avspeglar de nya inställningarna för de valda batcharna.

## <a name="master-planning-example"></a>Exempel på huvudplanering

I det här exemplet visas hur batchdispositionskoder kan påverka huvudplaneringen.

I det här exemplet ställs batchdispositionskoder in på följande sätt:

- *P-tillgänglig:*

    - **Batchdispositionsstatus:** *Tillgänglig*
    - **Nettoberäkning:** *Ja*

- *P-inte tillgänglig:*

    - **Batchdispositionsstatus:** *inte tillgänglig*
    - **Nettoberäkning:** *Nej*

Det finns en produkt (*Produkt-1*) som har två batchar: *Batch-A* och *Batch-B*. Dessa batchar anges på följande sätt:

- *Batch-A:*

    - **Batchdispositionskod:** *P-tillgänglig*
    - **Lagerbehållning:** 1

- *Batch-B:*

    - **Batchdispositionskod:** *P-inte tillgänglig*
    - **Lagerbehållning:** 1

Det finns en försäljningsorder (*SO1*) för en kvantitet på 2 av produkten *produkt-1*. Leveransdatumet är tre dagar från idag.

Du kör huvudplanering och ställer in följande värden som är relevanta för det här exemplet:

- **Planerad order:** *inköpsorder*
- **Påfyllnadsstrategi:** *krav*
- **Ledtid:** *0*

Som ett resultat av planeringskörningen använder systemet den tillgängliga batchen (*Batch-A*) för att täcka kvantiteten 1 av *produkt-1* för försäljningsorder *SO1*. Det kan däremot inte använda batch *batch-B* eftersom den batchen markeras som inte tillgänglig för planering. För att täcka den återstående kvantiteten skapas därför en planerad inköpsorder (*PPO1*) för en ny batch med produkt *Produkt-1*.

Följande bild visar tidslinjen för planeringsresultatet.

![Exempel som visar hur batchdispositionskoder kan påverka huvudplaneringen.](media/batch-codes-planning-example.png "Exempel som visar hur batchdispositionskoder kan påverka huvudplaneringen")
