---
title: "Kvittningöversikt"
description: "Den här artikeln innehåller allmän information om kvittningsprocessen. Den beskriver de olika typer av transaktioner som kan kvittas, när och hur transaktioner kan kvittas, och resultatet av kvittningsprocessen."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym, LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 14551
ms.assetid: 0968fa71-5984-415b-8689-759a0136d5d1
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: f707d45290682e79ee439ba0d504852429defa90
ms.openlocfilehash: adbfa6f99c481129e8cbf4a2dc4b23b4be1e8b34
ms.lasthandoff: 03/31/2017


---

# <a name="settlement-overview"></a>Kvittningöversikt

Den här artikeln innehåller allmän information om kvittningsprocessen. Den beskriver de olika typer av transaktioner som kan kvittas, när och hur transaktioner kan kvittas, och resultatet av kvittningsprocessen.

Under kvittning tillämpas transaktionerna för ett dokument till transaktioner på ett annat dokument för att minska eller öka saldot för varje dokument. Exempelvis kan en betalningen kopplas till en faktura. Olika transaktionstyper kan kvittas vid olika tidpunkter och till och med olika metoder. Kvittningen kan även orsaka att nya transaktioner genereras.

## <a name="what-transactions-can-be-settled"></a>Vilka transaktioner kan kvittas
Kvittningen i Leverantörsreskontra och Kundreskontra kan inträffar mellan alla transaktionstyper som påverkar leverantörssaldot eller kundsaldot, till exempel fakturor, betalningar, kreditfakturor och avgifter. Alla transaktionstyper kan kvittas mot någon annan transaktionstyp. Du kan till exempel kvitta en betalning mot en faktura, en kreditfaktura mot en faktura, en faktura mot en faktura och en betalning mot en betalning. Du kan kvitta betalningar mot en transaktion i samma juridiska person eller i en annan juridisk person. I organisationer som använder en modell för centraliserade betalningar, [centraliserade betalningar](set-up-centralized-payments.md) hjälper dig att effektivisera betalningsprocessen.

## <a name="when-to-settle-transactions"></a>När du ska kvitta transaktioner
Transaktioner kan kvittas vid tidpunkten för betalningsposten. Till exempel när du gör betalningar till en leverantör, väljer du vanligtvis fakturor som ska betalas. Genom att välja fakturor kan markera du dem för kvittning mot betalning. När Kundreskontra betalning lagerarbetare registrerar en kundbetalning, markera de lämpliga fakturor för kvittning, utifrån den information som ingår i betalningen. Sidan **Kvitta transaktioner** används för att markera transaktioner för kvittning. Den här sidan kan öppnas från en ej bokförd faktura eller betalning. När transaktionen bokförs, bokförs även kvittningen. Transaktioner kan också kvittas, när de har bokförts. Du kan ange och bokföra en kundbetalning, utan att kvitta den mot eventuella fakturor. Du kanske emellertid måste först kontrollera att betalningen kvittas mot den korrekta fakturan. Sidan **Kvitta transaktioner** kan öppnas från sidan **Alla kunder** eller **Alla leverantörer** eller från sidan **Transaktioner** för alla kunder eller leverantörer. Du kan också reservera bokförda förskottsbetalningar för en faktura, genom att välja betalningen för kvittning mot en inköpsorder eller försäljningsorder. Då betalningen har en ingående balans, men inte kan kvittas mot en faktura. Betalningen kvittas automatiskt mot den faktura som skapas från en inköpsorder eller försäljningsorder.

## <a name="how-to-settle-transactions"></a>Så här kvittar du transaktioner
Transaktioner kan kvittas manuellt, automatiskt, eller genom att använda en kombination av de två metoderna. Valet av kvittningsmetod beror på arbetsprocesser, som sedan kan implementeras via inställningar för kvittningen i Parametrar för leverantörsreskontra och Parametrar för kundreskontra. Du kan skapa leverantörsbetalningar och autogirobetalningar för kunder genom att använda ett betalningsförslag som väljer vilka fakturor som ska betalas. Betalningsförslaget initierad manuellt, men sedan Microsoft Dynamics 365 för operationer markeras de valda fakturorna för kvittning när betalningarna skapas. Om betalningarna skapas manuellt kan du använda **Kvitta transaktioner** för att välja fakturor för kvittning. Du kan manuellt välja fakturorna, eller använda alternativet **Markera efter prioritet** om du vill att fakturor ska väljas automatiskt för kvittning. Alternativet **Markera efter prioritet** är bara tillgängligt för kundreskontra. För att aktivera det här alternativet använder du sidan **Kvittningprioritet** i Parametrar för kundreskontra. Om en betalningsansvarig registrerar en betalning, men inte kvittar den betalningen när han eller hon bokför den kan betalningen kvittas automatiskt. Du kan aktivera automatisk kvittning i parametrar för kundreskontra och parametrar för leverantörsreskontra. När du använder automatisk kvittning, kan du använda fördefinierade betalningsorder eller definiera egna prioritetsordning för kvittning i parametrar för kundreskontra. Den här funktionen är bara tillgänglig för kundreskontra.

## <a name="results-of-settlement"></a>Resultat från kvittningen
Allt eftersom transaktioner kvittas, ökas eller minskas det utestående saldot för varje transaktion. I ett typiskt scenario där en faktura och en betalning kvittas, uppdateras status och saldo för respektive transaktion enligt följande regler:

-   Om betalningsbeloppet är mer än fakturabeloppet, reduceras fakturasaldot till 0,00 och fakturan stängs. Betalningen förblir öppen och saldot är det belopp som betalningen överskrider fakturabeloppet med.
-   Om betalningsbeloppet är mindre än fakturabeloppet, reduceras betalningssaldot till 0,00 och betalningen stängs. Fakturan förblir öppen och saldot är det belopp som betalningen underbetalar fakturan med.
-   Om betalningsbeloppet är lika med fakturabeloppet, stängs både betalningen och fakturan och saldot för båda är 0,00.

Om en [betalning är mindre än fakturabeloppet](../accounts-payable/vendor-payments-partial-amount.md) på grund av kassarabatt, avskrivning, eller underbetalning, kan faktura och betalning fortfarande stängas beroende på inställningarna för kvittning i Parametrar för leverantörsreskontra och Parametrar för kundreskontra. Kvittningen kan även generera transaktioner. Till exempel kan kvittning av en faktura och en betalning producera en kassarabatt, realiserad vinst eller förlust, momsjusteringar, avskrivning, eller öresdifferenser.

