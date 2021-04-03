---
title: Konfigurera kvittning
description: Hur och när transaktioner kvittas kan vara komplexa ämnen så det är nödvändigt att du förstår och definierar parametrarna korrekt så att de uppfyller dina verksamhetskrav. Det här avsnittet ger en beskrivning av de parametrar som används för kvittning av både Leverantörsreskontra och Kundreskontra.
author: kweekley
manager: AnnBe
ms.date: 05/16/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustOpenTrans, CustParameters, VendOpenTrans, VendParameters
audience: Application User
ms.reviewer: roschlom
ms.custom: 14601
ms.assetid: 6b61e08c-aa8b-40c0-b904-9bca4e8096e7
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ee37bc38c1027e2b52e25b331f65be6f2f5edd98
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5254069"
---
# <a name="configure-settlement"></a>Konfigurera kvittning

[!include [banner](../includes/banner.md)]

Hur och när transaktioner kvittas kan vara komplexa ämnen så det är nödvändigt att du förstår och definierar parametrarna korrekt så att de uppfyller dina verksamhetskrav. Det här avsnittet ger en beskrivning av de parametrar som används för kvittning av både Leverantörsreskontra och Kundreskontra. 

Följande parametrar påverkar hur kvittningar bearbetas i Microsoft Dynamics 365 Finance. Kvittningen är en process som kvittar en faktura mot en betalning eller kreditfaktura. Dessa parametrar finns i området **Kvittning** på sidorna **Parametrar för leverantörsreskontra** och **Parametrar för leverantörsreskontra**.

- **Automatisk kvittning** – Ställ in det här alternativet på **Ja** om en transaktion ska kvittas automatiskt mot andra öppna transaktioner när den bokförs. Om det här alternativet ställs in på **Nej**, kan användarna manuellt kvitta transaktioner när de anger betalningar eller senare, via sidan **Kvitta transaktioner**.
- **Administration av kassarabatt** – Ange hur en [kassarabatt ska hanteras när en faktura överbetalas](cash-discount-handling-overpayments.md). För överbetalningar kan kassarabatten minskas, behandlas som en differens eller kvarstå på kontot för leverantören eller kunden.
  -   **Ospecifikt** – Kassarabattbeloppet reduceras med överbetalningsbeloppet. Det här beteendet används alltid oavsett om överbetalningsbeloppet är större än eller mindre än det belopp som angetts i fältet **Maximal över- och underbetalning** .
  -   **Specifikt** – Överbetalningsbeloppet bokförs antingen till ett redovisningskonto för kassarabattskillnad eller återstår som ett saldo på kundens konto. Det specifika beteendet beror på om överbetalningsbeloppet är mellan 0,00 och det belopp som angetts i fältet **Maximal över- och underbetalning**, eller om överbetalningsbeloppet är större än beloppet **Maximal över- och underbetalning** .
- **Maximal öresdifferens** – Ange den tillåtna maximala öresdifferensen för kvittningstransaktioner. Om öresdifferensen är lika med eller mindre än skillnaden som angetts i det här fältet, bokförs skillnaden på det redovisningskonto för öresdifferenser som är angivet på sidan **Konton för automatiska transaktioner**.
- **Maximal över- och underbetalning** – Ange accepterat belopp för över- och underbetalning. Om du vill beräkna skatt på över- och underbetalningar markerar du kryssrutan **Moms på över-/underbetalning** på fliken **Moms** i formuläret **Allmänna redovisningsparametrar**.
  -   Om över-/underbetalningen leder till en differens som är mindre än skillnaden som är definierad i fältet **Maximal öresdifferens**, bokförs öresdifferensbeloppet på öresdifferenskontot.
  -   Om över-/underbetalningen leder till en differens som är större än skillnaden som har definierats i fältet **Maximal öresdifferens**, bokförs öresdifferensbeloppet på skillnadskontot som är valt för bokföringstypen **Kundkassarabatt** eller **Leverantörskassarabatt** på sidan **Konton för automatiska transaktioner**.
- **Beräkna kassarabatter för delvisa betalningar** – Ställ in alternativet på **Ja** för att aktivera kassarabatter som automatiskt ska beräknas för delvisa betalningar.
  -   Effekten av det här alternativet beror på värdet i fältet **Använd kassarabatt** på sidan **Kvitta transaktioner**. Om det här alternativet ställs in på **Ja**, används rabatten när fältet **Använd kassarabatt** har värdet **Normalt**. När fältet **Använd kassarabatt** har värdet **Alltid** används alltid kassarabatten, oavsett vilken inställning som har angetts i det här fältet. När fältet **Använd kassarabatt** har värdet **Aldrig** används aldrig kassarabatten, oavsett vilken inställning som har angetts i det här fältet.
  -   Om det här alternativet har värdet **Ja** och en användare ändrar värdet i fältet **Belopp att kvitta** på sidan **Kvitta transaktioner**, beräknas rabatten automatiskt och visas som standardvärde i fältet **Kassarabattbelopp att utnyttja**.
  -   Om det här alternativet har värdet **Nej** och en användare ändrar värdet i fältet **Belopp att kvitta** på sidan **Kvitta transaktioner**, är standardvärdet **0** (noll) i fältet **Kassarabattbelopp att utnyttja**.
- **Beräkna kassarabatter för kreditfakturor** – Ställ in alternativet på **Ja** för att automatiskt beräkna en kassarabatt för kreditfakturor. I leverantörsreskontra är en kreditfakturatransaktion en negativ transaktion som har ett värde i fältet **Faktura** på sidan **Fritextfaktura** eller en retur på sidan **Försäljningsorder**.
  - Effekten av det här alternativet beror på värdet i fältet <strong>Använd kassarabatt</strong> på sidan <strong>Kvitta transaktioner</strong>. Om det här alternativet ställs in på <strong>Ja</strong> används rabatten när fältet *<strong><em>Använd kassarabatt</em></strong>* är inställt på <strong>Normal</strong>. När fältet *<strong><em>Använd kassarabatt</em></strong>* anges som <strong>Alltid</strong> används alltid kassarabatten, oavsett vilken inställning som har angetts i det här fältet. När fältet *<strong><em>Använd kassarabatt</em></strong>* anges som <strong>Aldrig</strong> används aldrig kassarabatten, oavsett vilken inställning som har angetts för det här fältet.
  - Om det här alternativet får värdet **Ja** och en kreditfaktura markeras på sidan **Kvitta transaktioner** beräknas rabatten automatiskt och visas som standardvärde i fältet **Kassarabattbelopp att utnyttja**.
  - Om det här alternativet har värdet **Nej** och en kreditfaktura markeras på sidan **Kvitta transaktioner** är standardvärdet **0** (noll) i fältet **Kassarabattbelopp att utnyttja**.

- **Rabattmotkonton (endast LR)** – Definiera standardhuvudbokskontot för kassarabatten som ska användas för redovisningsposten för kassarabatter.
  -   **Använd huvudkontot för leverantörrabatter** – Kassarabatten bokförs på huvudkontot som definieras på sidan **Kassarabattinställningar**.
  -   **Konton på fakturaraderna** – Kassarabatten bokförs på redovisningskontona för den ursprungliga fakturan.
- **Markera rader på fritextfakturor och räntefakturor (endast KR)** – Ställ in alternativet på **Ja** för att aktivera knappen **Markera fakturarader** på sidorna **Ange kundbetalningar**, **Verifikation för betalningsjournal** och **Kvitta transaktioner**. Med den här knappen kan användaren välja enskilda rader för kvittning.
- **Prioritera betalning (endast KR)** – Ställ in alternativet på **Ja** för att aktivera knappen **Markera efter prioritet** på sidorna **Ange kundbetalningar** och **Kvitta transaktioner**. Den här knappen låter användare tilldela fördefinierade kvittningsorder till transaktioner.  När kvittningsordern har tillämpats på en transaktion kan ordern och betalningsallokeringen ändras innan du bokför.
- **Använd prioritering för automatiska kvittningar** – Ange detta alternativ som **Ja** för att använda angiven prioritetsordning när transaktionerna har kvittats automatiskt. Det här fältet visas endast om alternativen **Prioritera kvittning** och **Automatisk kvittning** ställs in på **Ja**.

## <a name="fixed-dimensions-on-accounts-receivableaccounts-payable-main-accounts"></a>Fasta dimensioner för huvudkontona kundreskontra/leverantörsreskontra

När fasta dimensioner används på det huvudkontona kundreskontra/leverantörsreskontra ska ytterligare redovisningsposter och två ytterligare leverantörstransaktioner bokföras av kvittningsprocessen. Kvittning jämför kontona för kundreskontra/leverantörsreskontra från faktura och betalning.  När betalning och kvittning slutförs tillsammans, vilket är ett vanligt scenario, bokförs betalningens redovisningpost inte i huvudboken förrän kvittningsprocessen också har slutförts. På grund av händelser för bearbetning går inte kvittning att fastställa det faktiska huvudbokskontot för kundreskontra/leverantörsreskontra från betalningens redovisningspost. Kvittning återskapar vad redovisningskontot ska vara för betalningen. Detta är ett problem när en fast dimension används för huvudkontot för kundreskontra/leverantörsreskontra.

Om du vill återskapa redovisningskontot huvudkontot för kundreskontra/leverantörsreskontra hämtas från bokföringsprofilen och ekonomiska dimensioner hämtas från betalningens leverantörstransaktionspost enligt definitionen i betalningsjournalen. Fasta dimensioner är inte är standard för betalningsjournaler, men tillämpas i stället på huvudkontot som ett sista steg i bokföringsprocessen. Därför är det sannolikt att det fasta dimensionsvärdet inte ingår i leverantörstransaktionen, såvida det inte hämtas som standard från en annan källa, t.ex. leverantören. Det återskapade kontot inkluderar inte fast dimension. Kvittningsbearbetning bestämmer att en justerande post måste skapas, eftersom fakturan bokförs med det fasta dimensionsvärdet och det återskapade kontot gör inte detta.  När kvittningen fortsätter med bokföring av justerande post, är det sista steget i bokföringen att använda fast dimension. Genom att lägga till fast dimension till justeringsposten bokförs den med en debet och kredit till samma redovisningskonto. Kvittning kan inte återställa redovisningsposten.

För att undvika ytterligare redovisningsposter, debet och kredit till samma redovisningskonto, bör följande lösningar övervägas beroende på företagets behov. 

-   Organisationer använder ofta fasta dimensioner som fylls i med nollvärden en finansiell dimension som inte krävs. Detta är ofta fallet för balansräkningskonton, till exempel Kundreskontra/Leverantörsreskontra. Kontostrukturer kan användas för att spåra ekonomiska dimensioner som vanligtvis fylls i med nollvärden.  Du kan ta bort den ekonomiska dimensionen för balansräkningskonton, utan att behöva använda fasta dimensioner.
-   Om din organisation kräver fasta dimensioner på huvudkontot för Kundreskontra/Leverantörsreskontra, hitta ett sätt att ställa in fast dimension till betalning som standard så att fasta dimensionsvärdet lagras på leverantörstransaktionen för betalningen. På så sätt kan systemet återställa huvudkontona för Kundreskontra/Leverantörsreskontra att inkludera de fasta dimensionsvärdena. Fast dimensionsvärden kan definieras som standard på antingen leverantörer eller journalnamnet för betalningsjournalen.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]