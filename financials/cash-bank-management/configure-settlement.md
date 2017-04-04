---
title: Konfigurera kvittning
description: "Hur och när transaktioner kvittas kan vara komplexa ämnen så det är nödvändigt att du förstår och definierar parametrarna korrekt så att de uppfyller dina verksamhetskrav. Det här avsnittet ger en beskrivning av de parametrar som används för kvittning av både Leverantörsreskontra och Kundreskontra."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: CustOpenTrans, CustParameters, VendOpenTrans, VendParameters
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 14601
ms.assetid: 6b61e08c-aa8b-40c0-b904-9bca4e8096e7
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: f707d45290682e79ee439ba0d504852429defa90
ms.openlocfilehash: 6927ed98c82f174a18d3d8821fbdb302801835c4
ms.lasthandoff: 03/31/2017


---

# <a name="configure-settlement"></a>Konfigurera kvittning

Hur och när transaktioner kvittas kan vara komplexa ämnen så det är nödvändigt att du förstår och definierar parametrarna korrekt så att de uppfyller dina verksamhetskrav. Det här avsnittet ger en beskrivning av de parametrar som används för kvittning av både Leverantörsreskontra och Kundreskontra. 

Följande parametrar som påverkar hur kvittningar ska bearbetas i Microsoft Dynamics 365 för operationer. Kvittningen är en process som kvittar en faktura mot en betalning eller kreditfaktura. Dessa parametrar finns i området **Kvittning** på sidorna **Parametrar för leverantörsreskontra** och **Parametrar för leverantörsreskontra**.

-   **Automatisk kvittning** – Ställ in det här alternativet på **Ja** om en transaktion ska kvittas automatiskt mot andra öppna transaktioner när den bokförs. Om det här alternativet ställs in på **Nej**, kan användarna manuellt kvitta transaktioner när de anger betalningar eller senare, via sidan **Kvitta transaktioner**.
-   **Administration av kassarabatt** – ange hur ett [kassarabatt ska hanteras när en faktura har betalat för mycket för](cash-discount-handling-overpayments.md). En överbetalning kassarabatten minskas, de kan behandlas som en differens eller kvarstå på konto för leverantören eller kunden.
    -   **Ospecifikt** – Kassarabattbeloppet reduceras med överbetalningsbeloppet. Det här beteendet används alltid oavsett om överbetalningsbeloppet är större än eller mindre än det belopp som angetts i fältet **Maximal över- och underbetalning** .
    -   **Specifikt** – Överbetalningsbeloppet bokförs antingen till ett redovisningskonto för kassarabattskillnad eller återstår som ett saldo på kundens konto. Det specifika beteendet beror på om överbetalningsbeloppet är mellan 0,00 och det belopp som angetts i fältet **Maximal över- och underbetalning**, eller om överbetalningsbeloppet är större än beloppet **Maximal över- och underbetalning** .
-   **Maximal öresdifferens** – Ange den tillåtna maximala öresdifferensen för kvittningstransaktioner. Om öresdifferensen är lika med eller mindre än skillnaden som angetts i det här fältet, bokförs skillnaden på det redovisningskonto för öresdifferenser som är angivet på sidan **Konton för automatiska transaktioner**.
-   **Maximal över- och underbetalning** – Ange accepterat belopp för över- och underbetalning. Om du vill beräkna moms på över- och underbetalningar markerar du kryssrutan **Moms på över-/underbetalning** på fliken **Moms** i formuläret **Allmänna redovisningsparametrar**.
    -   Om över-/underbetalningen leder till en differens som är mindre än skillnaden som är definierad i fältet **Maximal öresdifferens**, bokförs öresdifferensbeloppet på öresdifferenskontot.
    -   Om över-/underbetalningen leder till en differens som är större än skillnaden som har definierats i fältet **Maximal öresdifferens**, bokförs öresdifferensbeloppet på skillnadskontot som är valt för bokföringstypen **Kundkassarabatt** eller **Leverantörskassarabatt** på sidan **Konton för automatiska transaktioner**.
-   **Beräkna kassarabatter för delvisa betalningar** – Ställ in alternativet på **Ja** för att aktivera kassarabatter som automatiskt ska beräknas för delvisa betalningar.
    -   Effekten av det här alternativet beror på värdet i fältet **Använd kassarabatt** på sidan **Kvitta transaktioner**. Om det här alternativet ställs in på **Ja**, används rabatten när fältet **Använd kassarabatt** har värdet **Normalt**. När fältet **Använd kassarabatt** har värdet **Alltid** används alltid kassarabatten, oavsett vilken inställning som har angetts i det här fältet. När fältet **Använd kassarabatt** har värdet **Aldrig** används aldrig kassarabatten, oavsett vilken inställning som har angetts i det här fältet.
    -   Om det här alternativet har värdet **Ja** och en användare ändrar värdet i fältet **Belopp att kvitta** på sidan **Kvitta transaktioner**, beräknas rabatten automatiskt och visas som standardvärde i fältet **Kassarabattbelopp att utnyttja**.
    -   Om det här alternativet har värdet **Nej** och en användare ändrar värdet i fältet **Belopp att kvitta** på sidan **Kvitta transaktioner**, är standardvärdet **0** (noll) i fältet **Kassarabattbelopp att utnyttja**.
-   **Beräkna kassarabatter för kreditfakturor** – Ställ in alternativet på **Ja** för att automatiskt beräkna en kassarabatt för kreditfakturor. I leverantörsreskontra är en kreditfakturatransaktion en negativ transaktion som har ett värde i fältet **Faktura** på sidan **Fritextfaktura** eller en retur på sidan **Försäljningsorder**.
    -   Effekten av det här alternativet beror på värdet i fältet **Använd kassarabatt** på sidan **Kvitta transaktioner**. Om det här alternativet ställs in på **Ja**, rabatten hämtas när den *** Använd kassarabatt *** anges till **Normal**. När den *** Använd kassarabatt *** anges till **alltid**, kassarabatten tas alltid, oavsett inställningen i det här fältet. När den *** Använd kassarabatt *** anges till ****, kassarabatten aldrig hämtas, oavsett inställningen i det här fältet.
    -   Om det här alternativet får värdet **Ja** och en kreditfaktura markeras på sidan **Kvitta transaktioner** beräknas rabatten automatiskt och visas som standardvärde i fältet **Kassarabattbelopp att utnyttja**.
    -   Om det här alternativet har värdet **Nej** och en kreditfaktura markeras på sidan **Kvitta transaktioner** är standardvärdet **0** (noll) i fältet **Kassarabattbelopp att utnyttja**.
-   **Rabattmotkonton (endast LR)** – Definiera standardhuvudbokskontot för kassarabatten som ska användas för redovisningsposten för kassarabatter.
    -   **Använd huvudkontot för leverantörrabatter** – Kassarabatten bokförs på huvudkontot som definieras på sidan **Kassarabattinställningar**.
    -   **Konton på fakturaraderna** – Kassarabatten bokförs på redovisningskontona för den ursprungliga fakturan.
-   **Markera rader på fritextfakturor och räntefakturor (endast KR)** – Ställ in alternativet på **Ja** för att aktivera knappen **Markera fakturarader** på sidorna **Ange kundbetalningar**, **Verifikation för betalningsjournal** och **Kvitta transaktioner**. Med den här knappen kan användaren välja enskilda rader för kvittning.
-   **Prioritera betalning (endast KR)** – Ställ in alternativet på **Ja** för att aktivera knappen **Markera efter prioritet** på sidorna **Ange kundbetalningar** och **Kvitta transaktioner**. Den här knappen kan användare tilldela fördefinierade betalningsorder till transaktioner.  När betalningsorder har kopplats till en transaktion, kan ordern och betalning fördelningen ändras före bokföring.
-   **Använd prioritet för automatiska betalningar** – ange **Ja** ska användas när transaktionerna har kvittats automatiskt definierade prioritetsordning. Det här fältet visas endast om den **prioritera betalning** och **automatisk kvittning** alternativ ställs in på **Ja**.


