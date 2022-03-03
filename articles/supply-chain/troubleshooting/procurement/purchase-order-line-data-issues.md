---
title: Avvikelser mellan inköpsorderraddata
description: Du ser dataavvikelser eller data som skadas på inköpsorderraderna.
author: SmithaNataraj
ms.date: 12/07/2021
ms.topic: troubleshooting
ms.search.form: PurchLineManualCorrection, PurchTable, PurchLine, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-12-07
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: ee2cb9a07c8a00a92c71e3e99d8ec20aa27fb20e
ms.sourcegitcommit: b9799a58d6ec221df86788bc37c4fbd28b435e89
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/08/2022
ms.locfileid: "8100809"
---
# <a name="purchase-order-line-data-discrepancies"></a>Avvikelser mellan inköpsorderraddata

## <a name="symptoms"></a>Symtom

När du inspekterar raderna i en inköpsorder ser du ett eller flera av följande problem:

- Det finns dataavvikelser eller skadade rester i inköpsorderraden (leverans eller faktura).
- Skadade skador finns i en inköpsorderrad eller rubrikstatus.
- Du kan inte fakturera en inköpsorder eftersom du till exempel får ett eller flera av följande felmeddelanden:

    - "Stoppat (fel): Transaktionen har redan bokförts."
    - "Kvantiteten kan inte faktureras eftersom lagertransaktionerna med statusen Inlevererat inte är tillräckliga."
    - "Otillräcklig lagertransaktion med status "Inköpt" för artikel %0 kvantitet %1."

- Du kan inte slutföra eller stänga en inköpsorder på grund av exempelvis något av följande:

    - Knappen **Slutför** är inte tillgänglig.
    - Du kan inte annullera den beställda kvantiteten på en inköpsorderrad för en inköpsorder som är bekräftad och mottagen.

## <a name="cause"></a>Orsak

Dessa problem orsakas vanligtvis av skadade data eller avvikelser i restkvantiteterna för en eller flera inköpsorderrader.

## <a name="resolution"></a>Lösning

Du kan vanligtvis åtgärda dessa problem genom att uppdatera inköpsstatusen, leveransrest och/eller fakturarest för de relevanta inköpsorderraderna, enligt beskrivningen i följande procedur.

1. Gå till **Anskaffning och inköp \> Periodiska uppgifter \> Rensning \> Korrigera inköpsorderrader manuellt**.
1. I fältet **inköpsorder**, hitta och välj inköpsordern som ger dig problem.
1. I avsnittet **Inköpsorderrader** välj en rad om du hittade en avvikelse.
1. I avsnittet **Lagertransaktioner**, inspektera data som visas. Om du ser några inkonsekvenser mellan en inköpsorderrad och dess lagertransaktioner väljer du något av följande kommandon i åtgärdsfönstret, beroende på var inkonsekvenserna visas:

    - **Omberäkna \> Beräkna om leveranspåminnelse** – Uppdatera inköpsorderraden och rubrikstatus automatiskt. Den här funktionen fungerar endast för inköpsorderrader i lager (d.v.s. rader där artikeln är en artikel i lager). Artiklar som inte finns i lager och fångstviktartiklar stöds för närvarande inte.
    - **Omberäkna \> Beräkna om fakturapåminnelse** – Uppdatera inköpsorderraden och rubrikstatus automatiskt. Den här funktionen fungerar endast för inköpsorderrader i lager (d.v.s. rader där artikeln är en artikel i lager). Artiklar som inte finns i lager och fångstviktartiklar stöds för närvarande inte.
    - **Omberäkna \> omberäkna status** – Omberäkna status för den valda raden. Beräkningen baseras på den befintliga logiken. Rubriken på inköpsordern uppdateras då efter behov, baserat på den nya inköpsorderradens status.

1. Om inkonsekvenser fortfarande visas i de återstående kvantiteterna kan du redigera dem direkt i följande fält:

    - Leveransrest
    - Påminnelse om lagerleverans
    - Fakturarest
    - Lager ej fakturerat
