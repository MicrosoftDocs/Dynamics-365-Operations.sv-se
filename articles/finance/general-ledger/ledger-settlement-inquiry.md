---
title: Förfrågan om redovisningskvittning
description: Den här artikeln beskriver fönstret för förfrågan om redovisningskvittning
author: kweekley
ms.date: 12/15/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerClosingSheet
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 33ae49d9503c0a83bda7e0093ab6ef69fb4aef0a
ms.sourcegitcommit: 9f3a60a583da21382a14f32ce146fc9ce03f2a09
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/15/2022
ms.locfileid: "9853146"
---
# <a name="ledger-settlement-inquiry"></a>Förfrågan om redovisningskvittning

[!include [banner](../includes/banner.md)]

I den här artikeln beskrivs fönstret för **förfrågan om redovisningskvittning** som kan användas för att visa kvittade, oreglerade eller både kvittade och oreglerade redovisningstransaktioner för en räkenskapsperiod.

## <a name="view-ledger-settlement-transactions"></a>Visa transaktioner för redovisningskvittning
1.  Gå till **Redovisning > Förfrågningar och rapporter > Förfrågan om redovisningskvittning**.
2.  Använd fälten **Från datum** och **Till datum** eller fältet **Datumintervall** för att ange ett datumintervall. Vad gäller råbalansen måste datumintervallet infalla inom ett enda räkenskapsår.
3.  Välj ett eller flera huvudkonton i fältet **Huvudkonton** som du vill visa redovisningstransaktioner för. Listrutan visar bara huvudkonton som har ställts in för redovisningskvittning på sidan **Allmänna redovisningsparametrar** .
4.  Använd fältet **Ekonomisk dimensionsuppsättning** för att visa de ekonomiska dimensionerna i rutnätet. Eftersom huvudkontot krävs visas fältvärdet för **huvudkontot** alltid som den första kolumnen, även om du väljer en ekonomisk dimensionsuppsättning som inte inkluderar huvudkontot.
5.  I fältet **Status**, välj:
-   **Alla** för att visa både kvittade och oreglerade transaktioner
-   **Oreglerad** för att endast visa oreglerade transaktioner 
-   **Kvittad** för att endast visa kvittade transaktioner
6.  Välj **Visa transaktioner**. Redovisningstransaktioner visas i rutnätet baserat på kriteriet du angav. Du kan exportera resultaten från förfrågan till Microsoft Excel för vidare analys. Välj och håll ned (eller högerklicka) i rutnätet.

### <a name="column-details"></a>Kolumndetaljer
Rutnätet på sidan **Förfrågan om redovisningskvittning** innehåller följande kolumner:
-   **Huvudkonto**  – Det här fältet är obligatoriskt och visas alltid.
-   **Ekonomiska dimensioner**  – Ekonomiska dimensioner visas baserat på den ekonomiska dimensionsuppsättning som har valts.
-   **Transaktionsdatum** – Bokföringsdatum för de redovisningstransaktionen.
-   **Ursprungligt transaktionsdatum** – Om årsbokslutet har körts och redovisningskvittning har ställts in så att den behåller information för ett huvudkonto, kommer de oreglerade transaktionerna att föras över i detalj som en ingående balans. Det ursprungliga bokföringsdatumet för redovisningstransaktionen underhålls i fältet **Ursprungligt transaktionsdatum** .
-   **Transaktionsålder**  – Värdet är 0 (noll) för alla kvittade transaktioner. För oreglerade transaktioner beräknas värdet som antalet dagar från det ursprungliga transaktionsdatumet eller transaktionsdatumet till det datum då förfrågan körs.
En redovisningstransaktion har till exempel transaktionsdatumet 1 januari 2022 (1/1/2022) och det ursprungliga transaktionsdatumet 30 december 2021 (12/30/2021). Om frågan körs den 2 januari 2022 (1/2/2022) för räkenskapsåret 2022 blir **transaktionsåldervärdet** 4. Det här värdet beräknas som antalet dagar mellan det ursprungliga transaktionsdatumet (12/30/2021) och 1/2/2022.

Om det inte finns något ursprungligt transaktionsdatum används transaktionsdatumet istället.
-   **(Annan transaktionsinformation)**  – Ytterligare kolumner visar information som verifikationsnummer, beskrivning och debet- och kreditbelopp i alla tre valutor (transaktion, redovisning och rapportering).
-   **Status** – Detta värde är antingen **Kvittad** eller **Oreglerad**.
-   **Kvittnings-ID** – Det ID som har tilldelats de kvittade transaktionerna.

[![Sidan förfrågan om redovisningskvittning](./media/Inquiry1.png)](./media/Inquiry1.png)

 
Summor kan visas under rutnätet.
1.  Markera ellipsen (...) till höger om rutnätet och välj **Visa sidfot**.
2.  Välj och håll ned (eller högerklicka) i varje beloppskolumn och välj sedan **Gruppera efter denna kolumn** för att visa summorna. Summorna visas i sidfoten. Om frågan filtreras så att den bara visar oreglerade transaktioner kan du använda summorna för att stämma av beloppen med råbalansen.







