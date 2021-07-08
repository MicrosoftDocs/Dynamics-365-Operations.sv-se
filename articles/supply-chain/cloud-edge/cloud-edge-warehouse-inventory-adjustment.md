---
title: Lagerställets lagerjustering
description: Detta ämne tillhandahåller information om lagerjusteringsjournal och bearbetning när du använder skalningsenheter.
author: perlynne
ms.date: 04/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSInventoryAdjustmentJournal, InventJournalCount
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: perlynne
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 1bf147ce430d84980516d8d4824081ee2a9321a2
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2021
ms.locfileid: "6271242"
---
# <a name="warehouse-inventory-adjustment"></a>Lagerställets lagerjustering

[!include [banner](../includes/banner.md)]

Funktionen för lagerjustering används när molnbaserade enheter och kantskalningsenheter körs för [arbetsbelastningar inom tillverkning](cloud-edge-workload-manufacturing.md) samt [arbetsbelastningar inom Warehouse management](cloud-edge-workload-warehousing.md).

När en medarbetare utför en lagerjustering med hjälp av Warehouse managementsappen mot en Warehouse managementsarbetsbelastning med skalningsenheter, måste den fysiska uppdateringen av lagerbehållningen bearbetas av batchjobbet **Justeringsjournal för lager**, som du kör och schemalägger via **Warehouse management > Periodiska uppgifter > Justeringsjournal för lagerställe**.

Följande arbetsprocesser i appar för lagerställe använder för närvarande **lagerjusteringsjournalen för lagerställe** på arbetsbelastningar med skalning:

- Justering in/ut
- Rullande inventering
- Läs in registreringsskylt

Ett flertal lagertransaktioner skapas som ett led i varje lagerjusteringsprocess, eftersom distributionen för nav och skalningsenheter delar samma lagerposter.

## <a name="inventory-adjustment-example"></a>Lagerjusteringsexempel

I det här exemplet har en lagerställearbetare använt lagerställeappen för att registrera tillägget av lagerbehållning.

Först skapar arbetsbelastningen för skalningsenheten en lagerjusteringstransaktion för den positiva fysiska justeringen, som sedan synkroniseras med navet och leder till en ökning av lagerbehållningen i navet.

| Typ                                    | Skalningsenhet | Riktning | Hubb |
|-----------------------------------------|------------|-----------|-----|
| Lagerställets lagerjustering          | +1         | ->        | +1  |

Navet bearbetar sedan en inventeringsjournalbokföring som tas emot via [meddelanden i meddelandeprocessorn](cloud-edge-message-processor-messages.md). Då uppdateras den ytterligare lagerbehållningen. För att förhindra dubbel lagerbehållning skapar navet en mottransaktion som en del i processen, och tar bort den tidigare registrerade lagerbehållningen som är kopplad till lagerjusteringen av lagerstället.

| Typ                                    | Skalningsenhet | Riktning | Hubb |
|-----------------------------------------|------------|-----------|-----|
| Inventering                                | +1         | <-        | +1  |
| Lagerjustering för lagerställe (motbokning) | -1         | <-        | -1  |

När en skalningsenhet har skapat en **lagerjusteringsjournal** i navet kan du granska både **Inventeringsjournal** och **Motbokningsjournal** som skapas av navet som ett led i justeringsprocessen.

Du kan granska alla dessa journalposter och transaktioner i Supply Chain Management genom att göra följande:

1. Logga in på skalningsenheten.
1. Gå till **Warehouse management \> Periodiska uppgifter \> Lagerjusteringsjournal**.
1. På sidan **Lagerjusteringsjournal** hittar och öppnar du journalen som registrerade lagerbehållningsändringen. I avsnittet **Journalradet** visas varje justering som registrerats i den här journalen.
1. Logga in på navet.
1. Gå till **Warehouse management \> Periodiska uppgifter \> Lagerjusteringsjournal**.
1. På sidan **Lagerjusteringsjournal** bör du se samma journal i listan om navet och skalningsenheten har synkroniserats.
1. Öppna journalen. Om [meddelandena i meddelandeprocessorn](cloud-edge-message-processor-messages.md) har bearbetats visas länkar till **inventeringsjournalen** och **motbokningsjournalen** i rubriken.
    - **Inventeringsjournalen** ska visa samma dimensionsvärden som journalraderna.
    - **Motbokningsjournalen** ska visa motbokningen, vilket tar bort den dubbla lagerjusteringen.
    > [!NOTE]
    > När all synkronisering och bearbetning är klar synkroniseras **inventeringsjournalen** och **motbokningsjournalen** tillbaka till skalningsenheten. Dessa kan även visas från relevant **journalsida för lagerjustering**.
