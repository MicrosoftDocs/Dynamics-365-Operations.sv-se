---
title: TDS-beräkning av betalningar och skuldsedlar
description: Den här artikeln innehåller referensinformation om de olika betalningstransaktioner som skatteavdrag vid källan (TDS) beräknas på.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: f5e9447924a17b96b7a4a5cdd1ef1547145d6ea1
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8906330"
---
# <a name="tds-calculation-on-payments-and-promissory-notes"></a>TDS-beräkning av betalningar och skuldsedlar

[!include [banner](../includes/banner.md)]

Den här artikeln innehåller referensinformation om de olika betalningstransaktioner som skatteavdrag vid källan (TDS) beräknas på.

| Serienummer | Transaktionstyp | Transaktionsbelopp | Sidnamn och sökväg | Kontotyp och motkontotyp |
|---------------|------------------|--------------------|--------------------|--------------------------------------|
| 1             | Förskottsbetalning/betalning mot faktura (TDS-skuld) | Debet eller kredit | <ul><li>Allmän journal (**Redovisning \> Journalposter \> Allmänna journaler**)</li><li>Fakturajournal (**Leverantörsreskontra \> Fakturor \> Fakturajournal**)</li><li>Betalningsjournal (**Leverantörsreskontra \> Betalningar \> Leverantörsbetalningsjournal**)</li></ul> | Leverantör (Dr.), Bank (Cr.) |
| 2             | Förskottsbetalning/betalning mot faktura (Inköp från kund – TDS-skuld) | Debet eller kredit | <ul><li>Allmän journal (**Redovisning \> Journalposter \> Allmänna journaler**)</li><li>Fakturajournal (**Leverantörsreskontra \> Fakturor \> Fakturajournal**)</li><li>Betalningsjournal (**Leverantörsreskontra \> Betalningar \> Leverantörsbetalningsjournal**)</li></ul> | Kund (Dr.), Bank (Cr.) |
| 3             | Skuldsedlar | Debet | Journal för skuldsedlar (**Leverantörsreskontra \> Betalningar \> Skuldsedlar \> Journal för skuldsedlar**) | Leverantör (Dr.) Redovisning (Cr.) |
| 4             | Diverse intäkter (TDS-fordran) | Debet eller kredit | Allmän journal (**Redovisning \> Journalposter \> Allmänna journaler**) | Bank (Dr.), Redovisning (Cr.) |
| 5             | Övriga utgifter (TDS-skuld) | Debet eller kredit | Allmän journal (**Redovisning \> Journalposter \> Allmänna journaler**) | Bank (Dr.), Redovisning (Cr.) |

Följ dessa steg när du vill beräkna TDS för betalningar och skuldsedlar.

1. Skapa journalrader på journalsidorna. Välj kontotyp och motkontotyp.
2. Välj **Funktioner \> Kvittning** för att öppna sidan **Öppna transaktionsredigering**. Välj sedan en specifik faktura som måste kvittas. Om TDS redan ahr beräknats på fakturanivå, visar fältet **Beloppursprung** grundbeloppet som TDS beräknades på. I fältet **TDS-belopp** visas TDS-beloppet som beräknades för transaktionen. I fältet **Belopp** visas nettobetalningsbeloppet (det vill säga betalningsbeloppet efter avdragen TDS).

    > [!NOTE]
    > För en betalning som gjorts mot en faktura gäller följande villkor:
    >
    > - Om betalningsbeloppet och fakturabeloppet är desamma, beräknas TDS inte om det redan har beräknats på fakturanivå.
    > - Om fakturabeloppet efter det att TDS-beloppet har dragits av är större än betalningsbeloppet, beräknas inte TDS.
    > - Om fakturabeloppet efter det att TDS-beloppet har dragits av är mindre än betalningsbeloppet, beräknas TDS på det belopp som överstiger fakturabeloppet.

3. På sidan **Journalverifikation**, under fliken **Översikt**, i fältet **TDS-grupper**, granskar eller ändrar du standard-TDS-gruppen som har definierats för leverantören eller kunden. TDS-beloppet som beräknas på journalrader baseras på formeln som definierats för TDS-skattekoderna i TDS-gruppen.

    > [!NOTE]
    > TDS beräknas endast om alternativet **Beräkna källskatt** har ställts in på **Ja** för leverantören på sidan **Leverantörer**.

4. Under fliken **Skatteinformation**, i avsnittet **Företagsinformation**, i fältet **Namn**, kan du välja ett företagsnamn för alternativa adresser som har konfigurerats för företaget.

    I avsnittet **Källskatt** visar fältet **Typ av bedömare** typen av bedömningskategori för leverantören eller kunden. I fältet **Skattekontonummer (TAN)** visas skattekontonumret (TAN) för det valda företaget.

5. Välj **knappen Källskatt \> källskatt** för att öppna sidan **Temporära källskattetransaktioner**. Den övre delen av den här sidan har följande fält:

    - **Totalt källskattebelopp** – Total TDS beräknad för transaktionen för TDS-gruppen.
    - **Värde** – Den totala procentsatsen som används för att beräkna TDS för transaktionen. Den totala procentsatsen baseras på formeln som definieras för TDS-skattekoder som är kopplade till TDS-gruppen.
    - **Justerat totalt källskattebelopp** – Det totala justerade TDS-beloppet för alla momskoder i TDS-gruppen.
    - **TDS** – En markerad kryssruta anger att en TDS-grupp är kopplad till transaktionen.

    Fälten under flikarna **Översikt**, **Allmänt** och **Justering** visar det beräknade TDS-beloppet och information om justerat TDS-belopp för varje TDS-skattekod som är kopplad till TDS-gruppen.

6. Välj **Tröskel** för att öppna sidan **Tröskel**, där du kan granska tröskelgränsen som har definierats för TDS-skattekomponenten som är kopplad till en specifik TDS-skattekod.
7. Välj **Formeldesigner** för att öppna sidan **Formeldesigner**, där du kan granska formeln som definierats för en specifik TDS-skattekod.
8. Stäng sidorna **Formeldesigner** och **Temporära källskattetransaktioner** för att återgå till sidan **Journalverifikation**.
9. Validera och bokför journalen. Det TDS-belopp som beräknats bokförs på det leverantörsreskontrakonto som har definierats för varje TDS-skattekod i TDS-gruppen. Kundreskontrakontona för TDS-skattekoder definieras på sidan **Källskattekoder**.
10. Välj **Bokförd källskatt** för att öppna sidan **Källskattetransaktioner**. I fältet **Värde** visas den totala procentsatsen som användes för att beräkna TDS för transaktionen.

    I fälten under flikarna **Översikt**, **Allmänt** och **Belopp** visas de TDS-belopp som beräknades för TDS-gruppen som är kopplad till transaktionen.

11. Granska TDS-beräkningsinformation för varje TDS-skattekod som är kopplad till TDS-gruppen.

## <a name="generate-payments"></a>Generera betalningar

Gör på följande sätt om du vill generera betalningar.

1. Gör något av följande:

    - Gå till **leverantörsreskontra \> Betalningar \> Leverantörsbetalningsjournal**.
    - Gå till **kundreskontra \> Betalningar \> Kundbetalningsjournal**.
    - Gå till **Leverantörsreskontra \> Betalningar \> Skuldsedlar \> Journal för skuldsedlar**.
    - Gå till **Kundreskontra \> Betalningar \> Växel \> Journal för växel**.
    - Gå till **Kundreskontra \> Betalningar \> Växel \> Gör om journal för växel**.

2. Markera **rader**
3. Välj **Funktioner \> Generera betalningar**.
