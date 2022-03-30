---
title: Kvitta TDS-betalningar till TDS-myndigheter och generera TDS challan
description: I det här avsnittet beskrivs hur du kvittar avdragna skatter vid källan (TDS) till leverantörer inom TDS-myndigheten.
author: kailiang
ms.date: 03/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: 3e35131cf7fe28274f3f5fa3961c1ba30fdd70a0
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/12/2022
ms.locfileid: "8407724"
---
# <a name="settle-tds-payments-to-tds-authority-vendors-and-generate-tds-challan"></a>Kvitta TDS-betalningar till TDS-myndigheter och generera TDS challan

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur du kvittar avdragna skatter vid källan (TDS) till leverantörer inom TDS-myndigheten.

1. Gå till **leverantörsreskontra \> Betalningar \> Leverantörsbetalningsjournal**.

    [![Sida för leverantörsbetalningsjournal.](./media/apac-ind-TDS-51.png)](./media/apac-ind-TDS-51.png)

2. På sidan **Leverantörsbetalningsjournal** väljer du **Ny** för att skapa en journalrad.
3. I fältet **Konto** väljer du leverantör inom TDS-myndighet att kvitta TDS-betalning mot.
4. Välj **Kvittningstransaktioner** för att öppna sidan **Kvittningstransaktioner**, där du kan visa de kvittade TDS-transaktionerna för leverantören inom TDS-myndigheten.

    De kvittade TDS-transaktionerna för en kvittningsperiod visas på följande sätt:

    - TDS-transaktioner där typen av bedömningskategori är **Företag** visas som en transaktionsrad.
    - TDS-transaktioner där typen av bedömningskategori är **HUF**, **Firma**, **Individ**, **AOP**, **BOI**, **Lokal myndighet** eller **Övrigt** visas som en transaktionsrad.
    - I fältet **Belopp** visas det totala TDS-belopp som ska betalas till leverantören inom TDS-myndigheten.

5. Välj **Källskattetransaktioner** för att visa de olika TDS-transaktioner som ingår i kvittningsposten. Du kan visa uppdelningen av varje TDS-transaktion som har inkluderats i kvittningsprocessen för kvittningsperioden på den här sidan.
6. Under fliken **Översikt** markerar du kryssrutan **Markera** för TDS-transaktionerna som ska kvittas mot leverantören inom TDS-myndigheten.

    Under fliken **Översikt** visas följande information för varje öppen TDS-transaktion:

    - **Datum** – Datumet för TDS-transaktionen.
    - **Verfikation** – Verifikationsnumret.
    - **Källa** – Modulen där TDS-transaktionen bokförs.
    - **Leverantör/kund** – Leverantörs- eller kundkontonumret som TDS dras från.
    - **Namn på avdragsskapare/part** – Namnet på leverantören eller kunden som TDS dras av från.
    - **Typ av bedömare** – Typen av bedömningskategori som avdragsskaparen tillhör.
    - **Belopp** – Fakturabeloppet som TDS beräknades på.
    - **Skattebelopp** – TDS-beloppet som har beräknats för transaktionen.

    > [!NOTE]
    > Avmarkera kryssrutan **Markera** för TDS-transaktioner som inte ska kvittas mot leverantören i TDS-myndigheten.

    Under fliken **Allmänt** visar fältet **PAN** det permanenta kontonumret (PAN) för avdragsskaparen. I fältet **Datum** visas datumet för TDS-beräkningen och i fältet **Värde** visas den totala procentsats som användes för TDS-beräkningen.

7. Välj **Verifikation** för att visa verifikationsposterna för TDS-transaktionen.
8. Stäng sidan.
10. Välj **Källskattekomponenter** för att öppna sidan **Källskattekomponenter**, där du kan visa TDS som beräknades per TDS-skattekomponent för en specifik TDS-skattekod.

    Under fliken **Översikt** visar fältet **Skattekomponent** den TDS-skattekomponent som användes för transaktionen. I fältet **Belopp** visas det TDS-belopp som beräknades för TDS-skattekomponenten, i basvalutan. Fältet **Ackumulerat belopp** visar det totala TDS-beloppet som beräknades för TDS-skattekomponenten för alla kvittade transaktioner.

    Under fliken **Belopp** visar avsnittet **Standardvaluta** det TDS-belopp som beräknades för TDS-skattekomponenten, i standardvalutan. I avsnittet **Sekundär valuta** visas beloppet i en sekundär valuta.

11. Stäng sidan **Källskattekomponenter**.
12. På sidan **Öppna transaktionsredigering**, i fältet **Belopp**, noterar du att det totala beloppet som ska kvittas mot leverantören inom TDS-myndigheten för kvittningsperioden har uppdaterats.
13. Om du vill kvitta TDS-transaktionerna för olika TDS-kvittningsperioder mot leverantören i TDS-myndigheten markerar du kryssrutan **Markera** för transaktionerna.
14. Stäng sidan **Öppna transaktionsredigering**.

    > [!NOTE]
    > Om bara ett par transaktioner väljs för kvittning på sidan **Källskattetransaktioner** uppdateras det totala TDS-beloppet för de valda transaktionerna i fältet **Korrigering** på sidan **Öppna transaktionsredigering**. Korrigeringsbeloppet uppdateras på journalraden på sidan **Journalverifikation** och sidan **Öppna transaktionsredigering** stängs.

    På sidan **Journalverifikation** visar fältet **Debet** det totala beloppet som ska betalas till leverantören inom TDS-myndigheten.

15. Ange detaljer för motkontot.

    > [!NOTE]
    > Om TDS-transaktioner har olika skattekontonummer (TAN) skapas journalrader per TAN på sidan **Journalverifikation**.

16. Under fliken **Betalningsavgift**, i fältet **Avgifts-ID**, väljer du ett avgifts-ID som har avgiftstypen **Ränta** eller **Övrigt** för att debitera betalningsavgiften för försenade betalningar som görs till leverantören inom TDS-myndigheten.

    Under fliken **Skatteinformation**, i avsnittet **Företagsinformation**, visar fältet **Namn** företagsnamnet. I avsnittet **Källskatt** visar fältet **Skattekontonummer (TAN)** det TAN som är kopplat till transaktionsraden.

17. Validera och bokför journalen.
18. Välj **Källskatt \> Challan-information** för att ange challan-uppgifter för transaktionen.

    I fältet **Verifikation** visas verifikationsnumret för transaktionen.
    
19. Markera kryssrutan **TDS som sätts in genom bokföringspost** om TDS-beloppet sätts in genom bokföring.
20. I fältet **Challan-nummer** anger du challan-numret som används för att genomföra betalningen till leverantören inom TDS-myndigheten.
21. I fältet **Datum** anger du challan-datum.
22. I fältet **Banknamn** väljer du namnet på banken som TDS-beloppet som ska betalas till leverantören inom TDS-myndigheten ska sättas in på. Det här fältet visar alla bankkonton som har ställts in för TDS-myndighetens leverantör i **Leverantörsreskontra \> Alla leverantörer \> Konfigurera \> Bankkonton**.
23. I fältet **BSR-kod** anger du BSR-koden (Basic Statistical Return) för banken.
24. Stäng sidan.

### <a name="example"></a>Exempel

Perioden 2009/04/01 kvittas för TDS-komponentgruppen **Hyra** med hjälp av den periodiska TDS-kvittningsprocessen. Det totala TDS-beloppet 141 625,00 bokförs på TDS-leverantörsmyndighetskontot för TDS-kvittningsperioden. Du kan visa beloppet i fältet **Belopp** på sidan **Öppna transaktionsredigering** för leverantören inom TDS-myndigheten.

Om du väljer **Källskattetransaktioner** för att visa de olika TDS-transaktionerna som kvittades för perioden, visas följande information.

| TDS-belopp |
|------------|
| 16 995,00  |
| 22 660,00  |
| 28 325,00  |
| 16 995,00  |
| 28 325,00  |
| 16 995,00  |
| 11 330,00  |

För ett specfikt TDS-belopp kan du välja **Källskattekomponenter** för att visa TDS som beräknades per TDS-skattekomponent för en specifik TDS-skattekod. I det här exemplet väljer du **Källskattekomponenter** för TDS-beloppet 16 995,00. Skattebeloppet som beräknades per komponent för transaktionen visas.

| Momskomponent | Mängd    | Ackumulerat belopp |
|---------------|-----------|--------------------|
| TDS           | 1 500,00 | 125 000,00         |
| Tillägg     | 1 500,00  | 12 500,00          |
| PE-Cess       | 330,00    | 2 750,00           |
| SHE Cess      | 165,00    | 1 375,00           |

Om du endast har valt TDS-beloppen 16 995,00, 22 660,00 och 28 325,00 för kvittning på sidan **Källskattetransaktioner**, visas det totala kvittningsbeloppet som **67 980,00** i fältet **Korrigering** på sidan **Öppna transaktionsredigering**. Om den här transaktionen markeras för kvittning och sidan **Öppna transaktionsredigering** är stängd, visas beloppet **67 980,00** i fältet **Debet** på sidan **Journalverifikation**.

Du kan nu bokföra journalen och generera TDS-challan.

### <a name="adjustment-of-advance-payments-that-are-made-to-tds-authority-vendors"></a>Justering av förskottsbetalningar som görs till leverantörer inom TDS-myndigheter

yOm du vill justera en förskottsbetalning som gjorts till TDS-myndigheten till en faktisk betalning, går du till **Leverantörsreskontra \> Leverantörer \> Alla leverantörer \> Transaktionsredigering**. Om den faktiska betalningen som görs överskrider förskottsbetalningen genereras två challan-nummer för transaktionen. Det är dock endast det första challan-numret som visas i TDS-frågan.
