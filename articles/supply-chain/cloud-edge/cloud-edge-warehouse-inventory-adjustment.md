---
title: Lagerställets lagerjustering
description: Detta ämne tillhandahåller information om lagerjusteringsjournal och bearbetning när du använder skalningsenheter.
author: perlynne
manager: tfehr
ms.date: 04/22/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: be386539ea7addf20256ac2b1f8a2a72736fcbec
ms.sourcegitcommit: cd9016e9787169cb800889d335b9c5919ddbe4af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/23/2021
ms.locfileid: "5938236"
---
# <a name="warehouse-inventory-adjustment"></a>Lagerställets lagerjustering

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Funktionen för lagerjustering används när molnbaserade enheter och kantskalningsenheter körs för [arbetsbelastningar inom tillverkning](cloud-edge-workload-manufacturing.md) samt [arbetsbelastningar inom lagerstyrning](cloud-edge-workload-warehousing.md).

När en medarbetare utför en lagerjustering med hjälp av lagerstyrningsappen mot en lagerstyrningsarbetsbelastning med skalningsenheter, måste den fysiska uppdateringen av lagerbehållningen bearbetas av batchjobbet **Justeringsjournal för lager**, som du kör och schemalägger via **Lagerstyrning > Periodiska uppgifter > Justeringsjournal för lagerställe**.

Följande arbetsprocesser i appar för lagerställe använder för närvarande **lagerjusteringsjournalen för lagerställe** på arbetsbelastningar med skalning:

- Justering in/ut
- Rullande inventering
- Läs in registreringsskylt

Ett flertal lagertransaktioner skapas som ett led i lagerjusteringsprocessen för moln- och edge-teknologi, detta eftersom distributionen för nav och skalningsenheter delar samma lagerposter.

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
1. Gå till **Lagerstyrning \> Periodiska uppgifter \> Lagerjusteringsjournal**.
1. På sidan **Lagerjusteringsjournal** hittar och öppnar du journalen som registrerade lagerbehållningsändringen. I avsnittet **Journalradet** visas varje justering som registrerats i den här journalen.
1. Logga in på navet.
1. Gå till **Lagerstyrning \> Periodiska uppgifter \> Lagerjusteringsjournal**.
1. På sidan **Lagerjusteringsjournal** bör du se samma journal i listan om navet och skalningsenheten har synkroniserats.
1. Öppna journalen. Om [meddelandena i meddelandeprocessorn](cloud-edge-message-processor-messages.md) har bearbetats visas länkar till **inventeringsjournalen** och **motbokningsjournalen** i rubriken.
    - **Inventeringsjournalen** ska visa samma dimensionsvärden som journalraderna.
    - **Motbokningsjournalen** ska visa motbokningen, vilket tar bort den dubbla lagerjusteringen.
    > [!NOTE]
    > När all synkronisering och bearbetning är klar synkroniseras **inventeringsjournalen** och **motbokningsjournalen** tillbaka till skalningsenheten. Dessa kan även visas från relevant **journalsida för lagerjustering**.
