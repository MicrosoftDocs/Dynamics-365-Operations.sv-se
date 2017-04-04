---
title: "Ställ in växlar"
description: "Det här avsnittet beskrivs hur du ställer in växlar."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 269964
ms.assetid: f2077165-da90-4359-ab12-e05717728dc7
ms.search.region: global
ms.author: abruer
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: ce2142d946085d8bfc577accf1bb31a89ea29156
ms.lasthandoff: 03/31/2017


---

# <a name="set-up-bills-of-exchange"></a>Ställ in växlar

Det här avsnittet beskrivs hur du ställer in växlar.

En växel är en elektronisk order från en kund som anger att en annan part, vanligen en bank, ska betala ett angivet belopp till företaget. När du använder en växel som betalningsmedel för en försäljningsorderfaktura eller fritextfaktura krediterar du kundkontot. Den krediten säkras med växeln tills kunden betalar växeln till banken. Vanligtvis kvittar du fakturan mot växeln på förfallodatumet. När du får ett meddelande från banken om att växeln har inlösts, kan du stänga den. Du kan ställa ut växlar via banken vid någon av följande tidpunkter:

-   På förfallodatumet. Den här metoden kallas för remittera för inkasso.
-   Före förfallodatumet, normalt på rabattdatumet som anges i betalningsvillkoren som ställs in för kunden. När du bokför transaktionen, bokförs rabattbeloppet på ett utgiftskonto. Det återstående beloppet är en skuld till dig, tills banken mottar betalning från kunden. Den här metoden kallas för remittera för rabatt.

## <a name="set-up-posting-profiles-for-bills-of-exchange"></a>Ställ in bokföringsprofiler för växlar
Använd den **kundbokföringsprofiler** om du vill ställa in de bokföringsprofiler som du kan använda med växlar, protesterade växlar, remissor för inkasso och remissor för rabatt. I den **samlingskonto** Välj samlingskontot som växelbelopp ska bokföras. Kontot debiteras eller krediteras beroende på växeltransaktionen:
-   Växlar debiteras det här kontot när en växel bokförs, och krediteras när en remissa för rabatt eller en remissa för inkasso bokförs.
-   När det gäller protesterade växlar debiteras det här kontot när en protesterad växel bokförs.
-   När det gäller remissor för inkasso debiteras det här kontot när en remissa för inkasso bokförs.
-   När det gäller remissor för rabatt debiteras det här kontot när en remissa för rabatt bokförs.

I den **Kvittningskonto** Välj kontantkontot som växelbelopp ska bokföras. Det här kontot debiteras när en växel löses in. I den **förskottsbetalningar av moms**, markera den sammanfattande redovisningen ska bokföras momsbelopp på när växlar används för förskottsbetalning. I den **för diskonterade skulder** väljer du kontot ska bokföras rabattbeloppet när det gäller remissor för rabatt. Det här kontot krediteras när en remissa för rabatt bokförs.

## <a name="set-up-accounts-receivable-parameters-for-bills-of-exchange"></a>Ställa in kundreskontraparametrar för växlar
I den **parametrar för kundreskontra** sidan standard bokföringsprofiler för växlar som anges på den **redovisning och moms** fliken. Nummerserier definieras i den **nummerserier** fliken.
Ställa in journalnamn för växlar
------------------------------------------

I den **namn på handelsavtalsjournaler** kan du skapa minst fem journalnamn som ska användas för växlar. Nedan följer journaltyperna:
-   **Kund ställer ut växel** – skapa ett journalnamn för journalen för utställda växlar.
-   **Kund protesterar växel** – skapa ett journalnamn för journalen för protesterade växlar.
-   **Kund ställer ut ny växel** – skapa ett journalnamn för journalen för återutställda växlar.
-   **Kundbankremissa** – skapa ett journalnamn för remissajournalen.
-   **Kund löser in växel** – skapa ett journalnamn för journalen för inlösta växlar.

Anger information om växeln på sidan journal verifikation för varje Växeljournal på de **växel** fliken. När växeln journalraderna har bokförts kan du visa dem på de **växel journalen förfrågan** sida och **Växelstatistik** sida.
Ställa in betalningsmetoder för växlar
-----------------------------------------------

I den **betalningsmetoder** sida, ställa in minst en betalningsmetod för växlar. Om du gör affärer med fler än en bank ställer du in en betalningsmetod som motsvarar remitteringsformat som krävs för respektive bank för växlar.
Ställa in betalningsavgifter för växlar
-----------------------------------------

En betalningsavgift är en avgift som associeras med betalningsinhämtningen från kunderna. Flera betalningsavgiftsinställningarna rader kan vara associerade varje betalningsavgift. Du kan använda inställningsrader för att styra hur standardbelopp för betalningsavgifter beräknas. Du kan till exempel skapa inställningsrader för betalningsmetoder, betalningsspecifikationer, valutor och tidsperioder. Du kan också skapa inställningsrader för en procentandel eller belopp som baseras på dagsintervall. Du kan till exempel ställa in en ränteprocent som baseras på hur lång tid en betalning är förfallen. Om banken debiterar olika avgifter för olika typer av remissa, t.ex **samling** eller **rabatt**, ställa in separata betalningsavgiftsrader för respektive remissatyp.
Ställa in remissaavgifter för bankremissafiler
------------------------------------------------

I den **bankkonton** sida, kan du ställa in remissaavgifter som debiterar en bank för varje remissafil som genereras. Remissaavgifterna bokförs när remissan bekräftas och de realiserade avgiftsbeloppen blir kända. Remissaavgifterna skiljer sig från betalningsavgifter, som samlas in från kunder och kopplas till journalrader.
Ställa in dokumentlayout för växlar
---------------------------------------------

I den **bankkonton** klickar du på **ställer in**, och ange den dokumentlayout som krävs för respektive bankkonto som du vill generera utskrivna växlar dokument för.
Ställa in kunder för växlar
--------------------------------------

I den **kunder** sidor, för varje kund som har avtalat att betala via en växel, som du kan ställa in en standardbetalningsmetod för växlar på den **standardvärden för betalningar** fliken.




