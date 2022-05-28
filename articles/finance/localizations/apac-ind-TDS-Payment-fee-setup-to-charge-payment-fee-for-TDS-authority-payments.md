---
title: Ställ in betalningsavgifter för TDS-myndighetsbetalningar
description: I det här avsnittet beskrivs hur du ställer in betalningsavgifter som debiteras för myndighetsbetalningar vid skatteavdrag vid källa (TDS).
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
ms.openlocfilehash: 290606201eff7aee985983603e7895a8a59233ac
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2022
ms.locfileid: "8725579"
---
# <a name="set-up-payment-fees-for-tds-authority-payments"></a>Ställ in betalningsavgifter för TDS-myndighetsbetalningar

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs hur du ställer in betalningsavgifter som debiteras för myndighetsbetalningar vid skatteavdrag vid källa (TDS).

1. Gå till **Leverantörsreskontra \> Betalningsinställning \> Betalningsavgift**.

    [![Sidan Betalningsavgift.](./media/apac-ind-TDS-28.png)](./media/apac-ind-TDS-28.png)

2. Välj **Ny** för att skapa en betalningsavgift och ange den information som krävs.
3. I fältet **Avgiftstyp** väljer du typ av betalningsavgift:

    - **None**
    - **Ränta** – Ränta debiteras på försenade betalningar som görs till TDS-myndigheten.
    - **Övrigt** – Övriga avgifter debiteras på försenade betalningar som görs till TDS-myndigheten.

    Om du väljer **Ränta** eller **Övrigt** ställs fältet **Avgift** automatiskt in på **Redovisning**.

4. Om du har valt **Ränta** eller **Övrigt** i fältet **Fälttyp**, i fältet **Huvudkonto**, väljer du huvudbokskonto för att bokföra ränta eller övrigt.
5. Ange andra uppgifter som behövs.
6. I åtgärdsfönstret väljer du **Inställning av betalningsavgift** för att öppna sidan **Inställning av betalningsavgift**, där du kan ställa in betalningsavgifter för olika kombinationer av banker, betalningsmetoder, betalningsspecifikationer, valutor och datumintervall.

    [![Konfigurationssida för Betalningsavgift.](./media/apac-ind-TDS-21.png)](./media/apac-ind-TDS-21.png)

7. På fliken **Översikt**, i fältet **Grupperingar**, anger du vilka banker som du ställer in betalningsavgiften för:

    - **Tabell** – Avgiften är giltig för ett specifikt bankkonto.
    - **Grupp** – Avgiften är giltig för en specifik grupp.
    - **Alla** - Avgiften är giltig för alla bankkonton.

8. Om du har valt **Tabell** eller **Grupp** i fältet **Grupperingar**, i fältet **Bankrelation**, väljer du det specifika bankkonto eller den specifika bankgrupp som du ställer in betalningsavgiften för.
9. I fältet **Betalningsmetod** väljer du betalningsmetod för betalning av avgifter.
10. I fältet **Betalningsspecifikation** väljer eller anger du betalningsspecifikationskoden som genererades på sidan **Betalningsspecifikation**.
    - Betalningsspecifikationen används med överföringsbetalsätt av elektronisk fond.
12. I fältet **Betalningsvaluta** väljer du den valuta som aktiverar avgiften. Endast transaktioner med den valda valutan kan aktivera avgiften. Om du lämnar det här fältet tomt aktiveras avgiften av alla valutor.
13. I fältet **Procentandel/belopp** väljer du beräkningsmetod. Alternativen är **Belopp**, **Procent** och **Intervall**.
14. I fältet **Avgiftsbelopp** anger du avgiftsbeloppet som antingen en procentandel av betalningen eller som beloppet för en betalning.
15. I fältet **Avgiftsvaluta** anger du valutakoden för avgiften.
16. Välj fliken **Allmänt** för att visa eller modifiera informationen för det valda bankkontot.

    [![Fliken Allmänt.](./media/apac-ind-TDS-22.png)](./media/apac-ind-TDS-22.png)

16. I fältet **Minimum** anger du det minsta transaktionsbeloppet som aktiverar avgiften.
17. I fältet **Maximum** anger du det högsta transaktionsbeloppet som aktiverar avgiften.
18. I fälten **Från datum** och **Till datum** definierar du ett datumintervall för avgiftsberäkning.
19. I fältet **Minsta avgift** anger du avgiftsbeloppet som antingen en procentandel av betalningen eller som beloppet för en betalning.
20. I fältet **Momsgrupp** väljer du den momsgrupp som ska användas för att beräkna moms för avgiften.
21. I fältet **Momsgrupp för artikel** väljer du den momsgrupp för artikel som ska användas för att beräkna moms för artikeln för avgiften.
22. Välj fliken **Intervall**. 

    [![Fliken Intervall.](./media/apac-ind-TDS-23.png)](./media/apac-ind-TDS-23.png)

23. I fältet **Dagar** anger du antalet dagar mellan bokföringsdatumet (diskonteringsdatumet) för betalningen och förfallodatumet för skuldsedeln.
24. I fältet **Procentandel/belopp** väljer du om specifikationen är en procentandel eller ett fast belopp.
25. I fältet **Avgiftsbelopp** anger du avgiftsbeloppet som antingen en procentandel av betalningen eller som beloppet för en betalning.
26. Stäng sidan **Inställning av betalningsavgift**.
27. Stäng sidan **Betalningsavgift**.
