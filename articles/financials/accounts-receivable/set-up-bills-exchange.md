---
title: "Ställ in växlar"
description: "Det här avsnittet beskriver hur du ställer in växlar."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 01/12/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustBillOfExchangeJour
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 269964
ms.assetid: f2077165-da90-4359-ab12-e05717728dc7
ms.search.region: global
ms.author: shpandey
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 4dfc6cc2fcbca18f3dde833917ae68a5f254643b
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="set-up-bills-of-exchange"></a>Ställ in växlar

[!include[banner](../includes/banner.md)]


Det här avsnittet beskriver hur du ställer in växlar.

En växel är en elektronisk order från en kund som anger att en annan part, vanligen en bank, ska betala ett angivet belopp till företaget. När du använder en växel som betalningsmedel för en försäljningsorderfaktura eller fritextfaktura krediterar du kundkontot. Den krediten säkras med växeln tills kunden betalar växeln till banken. Vanligtvis kvittar du fakturan mot växeln på förfallodatumet. När du får ett meddelande från banken om att växeln har inlösts, kan du stänga den. Du kan ställa ut växlar via banken vid någon av följande tidpunkter:

-   På förfallodatumet. Denna metod kallas för remittera för inkasso.
-   Före förfallodatumet, normalt på rabattdatumet som anges i betalningsvillkoren som ställs in för kunden. När du bokför transaktionen, bokförs rabattbeloppet på ett utgiftskonto. Det återstående beloppet är en skuld till dig, tills banken mottar betalning från kunden. Denna metod kallas för remittera för rabatt.

## <a name="set-up-posting-profiles-for-bills-of-exchange"></a>Ställ in bokföringsprofiler för växlar
Använd sidan **Kundbokföringsprofiler** när du ställer in de bokföringsprofiler som ska användas med växlar, protesterade växlar, remissor för inkasso och remissor för rabatt. Välj samlingskontot som växelbelopp ska bokföras på i fältet **Samlingskonto**. Det här kontot debiteras eller krediterat baserat på typ av växeltransaktionen:
-   När det gäller växlar debiteras det här kontot när en växel bokförs, och krediteras när en remissa för rabatt eller remissa för inkasso bokförs.
-   När det gäller protesterade växlar debiteras det här kontot när en protesterad växel bokförs.
-   När det gäller remissor för inkasso debiteras det här kontot när en remissa för inkasso bokförs.
-   När det gäller remissor för rabatt debiteras det här kontot när en remissa för rabatt bokförs.

Välj kontantkontot som växelbelopp ska bokföras på i fältet **Kvittningskonto**. Det här kontot debiteras när en växel löses in. Välj **Förskottsbetalningar av moms** som momsbelopp ska bokföras på när växlar används för förskottsbetalning. I fältet **Skulder för diskonteringskonto** välj kontot som du vill bokföra rabattbeloppet för remissor för rabatt. Det här kontot krediteras när en remissa för rabatt bokförs.

## <a name="set-up-accounts-receivable-parameters-for-bills-of-exchange"></a>Ställa in kundreskontraparametrar för växlar
På sidan **Parametrar för kundreskontra** anges förvalda bokföringsprofiler för växlingsnotor på fliken **Redovisning och moms**. Nummersekvensen anges i fliken **Nummersekvenser**. Skapa journalnamn för växlingsnotor
------------------------------------------

På sidan **Journalnamn** skapar du minst fem journalnamn som ska användas för växlar. Här är journaltyperna:
-   **Kund ställer ut växel** – skapa ett journalnamn för journalen för utställda växlar.
-   **Kund protesterar växel** – skapa ett journalnamn för journalen för växelprotester.
-   **Kund ställer ut ny växel** – skapa ett journalnamn för journalen för nyutställda växlar.
-   **Kundbankremissa** – skapa ett journalnamn för remissajournalen.
-   **Kund löser in växeln** – skapa ett journalnamn för journalen för inlösta växlar.

Ange information om växlingsnotan på fliken **Växlingsnota** på journalvärdekupongssidan för respektive växlingsnotejournal. När journalraderna för växlingsnotan har bokförts kan du se dem på sidan **Journalfråga för växlingsnota** samt sidan **Växlingsnotestatistik**.
Ställa in betalningsmetoder för växlar
-----------------------------------------------

På sidan **Betalningsmetoder** ställer du in minst en betalningsmetod för växlar. Om du gör affärer med fler än en bank ställer du in en betalningsmetod som motsvarar det remissaformat som respektive bank kräver för växlar.
Ställa in betalningsavgifter för växlar
-----------------------------------------

En betalningsavgift är en avgift som associeras med betalningsinhämtningen från kunderna. Flera inställningsrader för betalningsavgift kan associeras till varje betalningsavgift. Du kan använda inställningsraderna när du vill styra hur standardbelopp för betalningsavgifter beräknas. Du kan till exempel skapa inställningsrader för betalningsmetoder, betalningsspecifikationer, valutor och tidsperioder. Du kan också skapa inställningsrader för en procentandel eller ett belopp som baseras på dagsintervall. Du kan till exempel ställa in en ränteprocent som baseras på hur lång tid en betalning är förfallen. Om banken debiterar olika avgifter för olika remissatyper, till exempel **Inkasso** eller **Rabatt** ställer du in separata betalningsavgiftsrader för respektive remissatyp.
Ställa in remissaavgifter för bankremissafiler
------------------------------------------------

På sidan **Bankkonton** kan du ställa in remissaavgifter som debiteras av en bank för varje remissafil som genereras. Remissaavgifterna bokförs när remissan bekräftas och de realiserade avgiftsbeloppen blir kända. Remissaavgifter skiljer sig från betalningsavgifter, som samlas in från kunder och kopplas till journalrader.
Ställa in dokumentlayout för växlar
---------------------------------------------

På sidan **Bankkonton** klickar du på **Ställ in** anger du den dokumentlayout som krävs för respektive bankkonto som du vill generera utskrivna växlar för.
Ställa in kunder för växlar
--------------------------------------

På sidan **Kunder**, för varje kund som har avtalat att betala via en växel, kan du ställa in en standardbetalningsmetod för växlar på fliken **Standardvärden för betalningar**.






