---
title: Varför kan jag inte återföra den här transaktionen?
description: I det här avsnittet beskrivs olika orsaker till varför transaktioner inte kan återföras. Här finns också lösningar på det här problemet.
author: kweekley
ms.date: 07/21/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2021-07-21
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: e18caf1dbdf8191713c17b1793f5da44cf2f182b
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2022
ms.locfileid: "8724541"
---
# <a name="why-cant-i-reverse-this-transaction"></a>Varför kan jag inte återföra den här transaktionen?

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs olika orsaker till varför transaktioner inte kan återföras. Här finns också lösningar på det här problemet.

## <a name="symptom"></a>Symptom

Organisationer kan stöta på situationer där de måste återföra en transaktion som de har bokfört. Ibland förhindrar systemet att de återför dessa transaktioner. Detta beteende kan leda till två frågor:

- Varför kan jag inte återföra den här transaktionen?
- Hur påverkar funktionen massåterföring detta beteende?

## <a name="resolution"></a>Lösning

Transaktioner måste uppfylla specifika kriterier innan de kan återföras. De återstående avsnitten i det här avsnittet tillhandahåller validering för varje modul. Även om det här ämnet fokuserar på transaktioner i Microsoft Dynamics 365 Finance, några av begreppen och validering kan tillämpas på andra appar, t.ex. Dynamics 365 Supply Chain Management.

Ett ställe där en transaktion återförs kan dessutom påverka om den kan återföras. En leverantörsbetalning som bokförs som en check kan till exempel bara återföras från avsnittet **Kontroller** på transaktionssidan för bankkontona. Den kan inte återföras från sidan **Verifikationstransaktioner** i redovisningen.

Om **massåterföringen för flera dokumentfunktion** (eller funktionen massåterföring) är aktiverad i arbetsytan för **funktionshantering** påverkar det hur många transaktioner som kan återföras och var de kan återföras. Den här funktionen ger två fördelar när den aktiveras:

- För vissa transaktionstyper kan mer än en transaktion i taget väljas och återföras från journalen som den bokfördes från, eller från sidan **Verifikationstransaktioner**. De enskilda transaktionerna måste dock ha återförts innan funktionen aktiveras. Innan den här funktionen införas måste transaktioner återföras en i taget.
- *Vissa* transaktioner för redovisning i redovisningen kan återföras från journalen (allmän journal) eller sidan **Verifikationstransaktioner**. De behöver inte återföras från sidan med underordnade sidor. En leverantörsfakturajournal kan tidigare bara återföras från sidan **Leverantörstransaktioner**. Den kan emellertid nu även återföras från redovisningssidan, från sidan journal eller **Verifikationstransaktioner**. I varje avsnitt i det här avsnittet beskrivs de transaktionstyper som den här förmånen inte gäller för.

Vid massåterföring kan **inte** flera typer av transaktioner återföras. Om en transaktionstyp inte tidigare kunde återföras, kan den inte återföras efter att funktionen har aktiverats. Leverantörsfakturor för inköpsorder kan till exempel inte återföras, oavsett om funktionen Massåterföring är aktiverad eller inte.

Mer information om funktionen Massåterföring finns i [Återför journalbokföring](reverse-journal-posting.md).

## <a name="general-ledger"></a>Huvudbok

Redovisningsjusteringar anges bara med hjälp av redovisningskonton. Därför uppdaterar de endast Redovisning.

Om funktionen Massåterföring är inaktiverad kan de flesta redovisningsjusteringar återföras individuellt från sidan **Transaktioner för \<main account\>** för redovisning (**LedgerTransAccount**). (Den exakta rubriken på sidan varierar beroende på vilket huvudkonto du väljer.) På sidan visas varje transaktion som har bokförts på huvudkontot. Den öppnas vanligtvis från listsidan **Råbalanslista** genom att välja **Transaktioner** på sidan **Verifikationstransaktioner**.

Om funktionen Massåterföring är aktiverad kan en eller flera redovisningsverifikationer nu återföras från sidan **Verifikationstransaktioner** och från den journal som transaktionen bokförts från. Undantagen är omvärdering av utländsk valuta i utländsk valuta, konsolidering och stängning av transaktioner vid årsslut. Transaktionerna återförs från de sidor som årsbokslut körs från.

### <a name="reasons-why-transactions-cant-be-reversed"></a>Orsaker till varför transaktioner inte kan återföras

Transaktioner kan inte återföras av följande skäl:

- Allmän journal:

    - Räkenskapsperioden är spärr eller permanent stängd:

        - Om återföringsdatumet är en räkenskapsperiod som inte är öppen, kan transaktionen inte återföras.
        - Om transaktionen stöder inmatning av ett återföringsdatum kan transaktionen fortfarande återföras genom att återföringsdatumet ändras till en öppen period.

    - Årsbokslutsprocessen har körts:

        - Transaktionens redovisningsdatum är ett räkenskapsår som har gått igenom en stängning av året. Även om en period i räkenskapsåret fortfarande kan vara öppen, kan transaktionen inte återföras om årsbokslutsprocessen för räkenskapsåret har körts. Räkenskapsåret har en annan status än perioderna i det.
        - Årsbokslut kan återföras och transaktionen kan återföras. Det här är kanske inte ett alternativ. Det kan vara enklare att registrera en återföringstransaktion manuellt i en öppen period under antingen det stängda räkenskapsåret eller nästa räkenskapsår, beroende på statusen för stängningsprocessen. Om en ny transaktion bokförs på en öppen period under räkenskapsåret som har gått igenom årsbokslutsprocessen vid årets slut, måste årsbokslutet köras igen.

    - Transaktionsåterföringen pågår redan:

        - Om transaktionen håller på att återföras måste den processen slutföras. En separat återföringsprocess kan inte göras. 
        - När återföringen har slutförts kan en återförd transaktion återföras igen (det vill säga återföringen kan återföras).

    - Redovisningskvittning:

        - Om en eller flera rader i transaktionen har bokförts med hjälp av periodiska uppgiften **Redovisningskvittningar** (**Redovisning \> Periodiska uppgifter \> Redovisningskvittningar**), så att posten finns i tabellen LedgerTransSettlement kan transaktionen inte reverseras.
        - Redovisningskvittning kan återföras och verifikationen kan återföras.

    - Koncerninternt:

        - Om transaktionen är en koncernintern transaktion kan den inte återföras.
        - Transaktionen är **inte** en koncernintern transaktion, utan bokförs på huvudkontot "förfaller till" eller "förfaller från" som har definierats på **inställningssidan för koncernintern**.

    - Periodiseringar:

        - Om den periodiserade redovisningsverifikationen återförs den periodiserade posten och alla motsvarande periodiserade deltransaktioner.
        - De enskilda periodiserade deltransaktioner kan inte återföras.

- Intäktsredovisningsjournal:

    - Intäktsredovisningstransaktioner inte kan återföras.
    - När intäkter redovisas via intäktsredovisningsjournalen bokförs verifikationen bara på redovisningskonton. På sidor som **verifikationstransaktioner** visas därför transaktionerna som om de bara är redovisningsposter.

- Omräkning i utländsk valuta:

    - Omvärderingstransaktioner i utländsk valuta kan reverseras, men endast från huvudboken **Omräkning i utländsk valuta** som omvärderingen kördes från.
    - Återföringen kan bara slutföras om den bokförs på en öppen räkenskapsperiod.

- Konsolidering:

    - Konsolideringstransaktioner kan återföras, men endast från sidan **Konsolideringstransaktioner**.
    - Återföringen kan bara slutföras om den bokförs på en öppen räkenskapsperiod.

- Årsbokslut:

    - Transaktioner för årsbokslut (både utgående och ingående transaktioner) kan återföras på följande sätt:

        - Om funktionen förbättringar i årsbokslut är inaktiverad väljer du **Ångra tidigare bokslut** i dialogrutan **Årsbokslut**.
        - Om funktionen bokslutsförbättringar är aktiverad väljer du de företags- och räkenskapsårsposter som skapades för bokslutet i slutet av **Årsbokslut** och välj **Återföra årsbokslut**.

    - Observera att återföringen av årsbokslut i själva verket raderar utgående och ingående transaktioner. En återföringsverifikation bokförs aldrig.

## <a name="accounts-payable"></a>Leverantörsreskontra

Med flera transaktionstyper uppdateras redovisningsjournal för leverantörsreskontra. Till exempel leverantörsfakturor, leverantörsfakturajournaler och utgiftsrapporter.

Om funktionen Massomvändning är avstängd kan transaktioner reverseras individuellt från antingen sida **Leverantörstransaktioner** för fakturor på sidan **Bankkonto** för checkbetalningar.

Om funktionen Massåterföring är aktiverad kan en eller flera leverantörsreskontratransaktioner nu återföras från sidan **Verifikationstransaktioner** och från den journal som transaktionerna bokfördes från. Leverantörsbetalningar kan dock bara återföras från bankkontot. Dessutom kan leverantörstransaktioner inte återföras från sidan **Transaktioner för \<main account\>** för redovisningen. De kan bara återföras från sidan **Verifikationstransaktioner**.

Observera att vissa transaktioner inte alls kan återföras. Exempel på detta är leverantörsfakturor för inköpsorder och elektroniska leverantörsbetalningar.

### <a name="reasons-why-vouchers-cant-be-reversed"></a>Orsaker till varför verifikationer inte kan återföras

Verifikationer kan inte återföras av följande skäl:

- Räkenskapsperioden är spärr eller stängd:

    - Om återföringsdatumet är en räkenskapsperiod som inte är öppen, kan transaktionen inte återföras.
    - Om transaktionen stöder inmatning av ett återföringsdatum kan transaktionen fortfarande återföras genom att återföringsdatumet ändras till en öppen period.

- Årsbokslutsprocessen har körts:

    - Transaktionens redovisningsdatum är ett räkenskapsår som har stängts i redovisningen. Även om en period i räkenskapsåret fortfarande kan vara öppen, kan transaktionen inte återföras om årsbokslutsprocessen för räkenskapsåret har körts. Räkenskapsåret har en annan status än perioderna i det.
    - Årsbokslut kan återföras och transaktionen kan återföras. Det här är kanske inte ett alternativ. Det kan vara enklare att registrera en återföringstransaktion manuellt i en öppen period under antingen det stängda räkenskapsåret eller nästa räkenskapsår, beroende på statusen för stängningsprocessen. Om en ny transaktion bokförs på en öppen period under räkenskapsåret som har gått igenom årsbokslutsprocessen vid årets slut, måste årsbokslutet köras igen.

- Journalposten i redovisningen har inte överförts till redovisningen:

    - Detta gäller endast för leverantörsfakturor som inte är inköpsorder.
    - Använd sidan **Poster i redovisningsjournal som ännu inte har överförts** om du vill överföra posten till redovisningen. Leverantörsfakturan för icke inköpsorder kan sedan återföras från sidan **Leverantörstransaktioner**. 

- Kvittning:

    - Transaktionen (till exempel en faktura eller betalning) kvittas eller markeras för kvittning.

        - Du kan verifiera om en transaktion är avgjord eller markerad för avveckling genom att välja **Visa kvittningar** eller **Kvittning \> Kvittningshistorik** på sidan **Leverantörstransaktioner**.
        - Du kan också återföra en kvittning från sidan **Leverantörstransaktioner** (**Kvittning \>Ångra kvittning**) om en av transaktionerna måste återföras.

- Verifikationen innehåller fler än en transaktion med flera undergrupper som har registrerats med samma verifikationsnummer (en verifikationstransaktion).
- Fakturan har inte godkänts:

    - Om kryssrutan **Godkännande** inte är markerad på fakturan går fakturan inte att återföra.

        - I det här fallet avser godkännande inte godkännanden i arbetsflödesprocessen utan alternativet **godkännanden** på fakturan. Det här alternativet används för att förhindra att en faktura betalas. Den används normalt för leverantörsfaktura registerfakturor.

- Transaktionen finns i fakturapoolen: 

    - En faktura i poolen kan inte återföras direkt från sidan **Leverantörstransaktioner**. Det måste i stället återföras via annulleringsprocessen på sidan **Fakturagodkännandejournal**.

- Transaktionen har en överordnad faktura som korrigerats (indiskt lokalisering).
- Transaktionen har skuldsedelns status **Faktura remitterade**.
- Transaktionen används för en delskattekvittning.
- Transaktionen innehåller ett leverantörskonto men återställs från en felaktig sida, till exempel sidan **Transaktioner för \<main account\>**:

    - Som det här orsaken föreslås kan vissa transaktioner i underordnade lager bara återföras från vissa sidor, även om funktionen Massåterföringar är aktiverad.

### <a name="types-of-transactions-that-cant-be-reversed"></a>Typer av transaktioner som inte kan återföras

Följande typer av transaktioner kan inte reverseras:

- Omräkning i utländsk valuta:

    - Till skillnad från omvärdering av utländsk valuta i redovisningen kan omvärdering inte återföras i kundreskontra och leverantörsreskontra. I stället måste omvärderingen köras igen med fakturadatumet. I det här fallet använder omvärderingen valutakursen från fakturans datum och leder i grund och botten till den orealiserade vinsten eller förlusten till 0 (noll). Därför liknar resultatet resultatet när föregående omvärdering återförs. Observera dock att samma belopp inte kommer att återföras om standardkursen ändrades på fakturan.

- Inköpsorder, leverantörsfaktura:

    - En kreditfaktura måste skapas för att du ska kunna återföra leverantörsfakturan. Mer information om hur du skapar en återföringstransaktion finns i [Skapa en returorder för inköp](../../supply-chain/procurement/tasks/create-purchase-return-order.md).

- Skuldsedel
- Exportera leverans för en remburs

## <a name="accounts-receivable"></a>Kundreskontra

Flera transaktionstyper uppdateras redovisningsjournal för kundreskontra. Exempel: kundfakturor från försäljningsorder, kundfakturor som förs in via den allmänna journalen, fritextfakturor, kundbetalningar och avskrivningar.

Om funktionen Massomvändning är avstängd kan transaktioner reverseras individuellt från antingen sida **Kundtransaktioner** för fakturor på sidan **Bankkonton** för insättningar. Mer information om hur du återbetalar en betalning finns i avsnittet [Kassa- och bankhantering](cant-reverse-transctns.md#cash-and-bank-management) senare i detta ämne.

Om funktionen Massåterföring är aktiverad kan en eller flera kundreskontratransaktioner nu återföras från sidan **Verifikationstransaktioner** och från den journal som transaktionerna bokfördes från. Insättningar kan dock bara återföras från bankkontot och fritextfakturor kan bara återföras från den ursprungliga sidan (om funktionen som tillåter korrigeringar är aktiverad). Dessutom kan kundtransaktioner inte återföras från sidan **Transaktioner för \<main account\>** för redovisningen. De kan återföras från sidan **Verifikationstransaktioner**.

Observera att vissa transaktioner inte kan återföras. Till exempel försäljningsorderfakturor och avskrivningar.

### <a name="reasons-why-transactions-cant-be-reversed"></a>Orsaker till varför transaktioner inte kan återföras

Transaktioner kan inte återföras av följande skäl:

- Räkenskapsperioden är spärr eller permanent stängd:

    - Om återföringsdatumet är en räkenskapsperiod som inte är öppen, kan transaktionen inte återföras.
    - Om transaktionen stöder inmatning av ett återföringsdatum kan transaktionen fortfarande återföras genom att återföringsdatumet ändras till en öppen period.

- Årsbokslutsprocessen har körts:

    - Transaktionens redovisningsdatum är ett räkenskapsår som har gått igenom en redovisningens årsbokslut. Även om en period i räkenskapsåret fortfarande kan vara öppen, kan transaktionen inte återföras om årsbokslutsprocessen för räkenskapsåret har körts. Räkenskapsåret har en annan status än perioderna i det.
    - Årsbokslut kan återföras och transaktionen kan återföras. Det här är kanske inte ett alternativ. Det kan vara enklare att registrera en återföringstransaktion manuellt i en öppen period under antingen det stängda räkenskapsåret eller nästa räkenskapsår, beroende på statusen för stängningsprocessen. Om en ny transaktion bokförs på en öppen period under räkenskapsåret som har gått igenom årsbokslutsprocessen vid årets slut, måste årsbokslutet köras igen.

- Journalposten i redovisningen har inte överförts till redovisningen:

    - Orsaken gäller endast för fritextfakturor.
    - Använd sidan **Poster i redovisningsjournal som ännu inte har överförts** om du vill överföra posten till redovisningen. Fritextfakturan kan sedan återföras eller korrigeras om korrigeringsfunktionen är aktiverad.

- Kvittning:

    - Transaktionen (till exempel en faktura eller betalning) kvittas eller markeras för kvittning.

        - Du kan verifiera om en transaktion är avgjord eller markerad för avveckling genom att välja **Visa kvittningar** eller **Kvittning \> Kvittningshistorik** på sidan **Kundtransaktioner**.
        - Du kan också återföra en kvittning från sidan **Kundtransaktioner** (**Kvittning \>Ångra kvittning**) om en av transaktionerna måste återföras.

- Transaktioner innehåller fler än en transaktion med flera undergrupper som har registrerats med samma verifikationsnummer (en verifikationstransaktion).
- Fakturan har inte godkänts:

    - Om kryssrutan **Godkännande** inte är markerad på fakturan går fakturan inte att återföra.

        - I det här fallet avser godkännande inte godkännanden i arbetsflödesprocessen utan alternativet **godkännanden** verifikationsraderna. Det här alternativet används för att förhindra att en faktura betalas. Även om det här alternativet normalt används i Leverantörsreskontra, är det också tillgängligt för kundreskontrafakturor som registreras via journaler.

- Transaktionen har en överordnad faktura som korrigerats (indiskt lokalisering).
- Transaktionen innehåller ett kundkonto men återställs från en felaktig sida, till exempel sidan **Transaktioner för \<main account\>**:

    - Som det här orsaken föreslås kan vissa transaktioner i underordnade lager bara återföras från vissa sidor, även om funktionen Massåterföringar är aktiverad.

### <a name="types-of-transactions-that-cant-be-reversed"></a>Typer av transaktioner som inte kan återföras

Följande typer av transaktioner kan inte reverseras:

- Omräkning i utländsk valuta:

    - Till skillnad från omvärdering av utländsk valuta i redovisningen kan omvärdering inte återföras i kundreskontra och leverantörsreskontra. I stället måste omvärderingen köras igen med fakturadatumet. I det här fallet använder omvärderingen valutakursen från fakturans datum och leder i grund och botten till den orealiserade vinsten eller förlusten till 0 (noll). Därför liknar resultatet resultatet när föregående omvärdering återförs. Observera dock att samma belopp inte kommer att återföras om standardkursen ändrades på fakturan.

- En transaktion som har justerat källskatt
- Försäljningsorder, kundfaktura:

    - En kreditfaktura eller retur måste skapas för att du ska kunna återföra transaktionen. Information om hur du skapar återföringstransaktionen finns i [Försäljningsreturer](../../supply-chain/warehousing/sales-returns.md).

- Växel
- Kassatransaktioner
- Avancerad justering
- Räntefaktura
- Kravbrev
- Remburs
- Exportera försändelse
- Intäktsredovisningsjournal:

    - När intäkter identifieras via intäktsredovisningsjournalen bokförs verifikationerna på redovisningskonton. Därför visas de som om de bara är huvudboksposter. Dessa poster kan inte återföras eftersom intäktsplanen inte kommer att öppnas igen för att redovisa intäkten igen.

## <a name="cash-and-bank-management"></a>Kassa- och bankhantering

Flera transaktionstyper uppdaterar bankredovisningen via den allmänna journalen. Det kan till exempel vara leverantörsbetalningar, kundbetalningar och banköverföringar.

Om funktionen Massomvändning är avstängd kan transaktioner reverseras individuellt från sidan **Bankkonton** för checkar och insättningar eller från sidan **Kundtransaktioner** för kundbetalningar.

Om funktionen Massåterföring är aktiverad kan en eller flera betalningstransaktioner nu återföras från sidan **Verifikationstransaktioner** och från den journal som transaktionerna bokfördes från. Insättningar kan dock bara återföras från bankkontot. Dessutom kan banktransaktioner fortfarande inte återföras från redovisningssidan **Transaktioner för \<main account\>**. De kan återföras från sidan **Verifikationstransaktioner**.

Observera att vissa transaktioner inte kan återföras. Elektroniska leverantörsbetalningar kan till exempel vara exempel.

### <a name="reasons-why-transactions-cant-be-reversed"></a>Orsaker till varför transaktioner inte kan återföras

Transaktioner kan inte återföras av följande skäl:

- Räkenskapsperioden är spärr eller permanent stängd:

    - Om återföringsdatumet är en räkenskapsperiod som inte är öppen, kan transaktionen inte återföras.
    - Om transaktionen stöder inmatning av ett återföringsdatum kan transaktionen fortfarande återföras genom att återföringsdatumet ändras till en öppen period.

- Årsbokslutsprocessen har körts:

    - Transaktionens redovisningsdatum är ett räkenskapsår som har gått igenom en redovisningens årsbokslut. Även om en period i räkenskapsåret fortfarande kan vara öppen, kan transaktionen inte återföras om årsbokslutsprocessen för räkenskapsåret har körts. Räkenskapsåret har en annan status än perioderna i det.
    - Årsbokslut kan återföras och transaktionen kan återföras. Det här är kanske inte ett alternativ. Det kan vara enklare att registrera en återföringstransaktion manuellt i en öppen period under antingen det stängda räkenskapsåret eller nästa räkenskapsår, beroende på statusen för stängningsprocessen. Om en ny transaktion bokförs på en öppen period under räkenskapsåret som har gått igenom årsbokslutsprocessen vid årets slut, måste årsbokslutet köras igen.

- Kvittning:

    - Transaktionen (betalning) kvittas eller markeras för kvittning.

        - Du kan verifiera om en transaktion är avgjord eller markerad för avveckling genom att välja **Visa kvittningar** eller **Kvittningar \> Kvittningshistorik** på sidan **Leverantörstransaktioner** eller **Kundtransaktioner**.
        - Du kan också återföra en kvittning från sidan **Leverantörstransaktioner** eller **Kundtransaktioner** (**Kvittning \> Ångra kvittning**) om en av transaktionerna måste återföras.

- Transaktioner innehåller fler än en transaktion med flera undergrupper som har registrerats med samma verifikationsnummer (en verifikationstransaktion).
- Interimstransaktioner:

    - Om transaktionen är relaterad till en övergångsbetalning kan den inte återföras.
    - Om den återförda betalningen måste återföras måste betalningen först rensas från övergångskontot till banken. Betalningen kan sedan återföras om den uppfyller de andra valideringskriterierna.

- Transaktionen innehåller ett bankkonto, men återförs från sidan **Transaktioner för \<main account\>** eller från en felaktig delbok, till exempel kundfordringar eller leverantörsskulder:

    - Som det här orsaken föreslås kan vissa transaktioner i underordnade lager bara återföras från vissa sidor, även om funktionen Massåterföringar är aktiverad.

- Bank – omräkning i utländsk valuta:

    - Omvärdering av utländsk valuta i bank kan återföras. Återföringen kan dock förhindras om du utför återföringsstegen i kronologisk ordning. Om du till exempel körde omvärderingen i mars och april kan omvärderingen inte återföras förrän omvärderingen i april återförs.

### <a name="types-of-transactions-that-cant-be-reversed"></a>Typer av transaktioner som inte kan återföras

Följande typer av transaktioner kan inte reverseras:

- Leverantörsbetalningar som gjorts som elektroniska betalningsöverföringar
- Skuldsedlar
- Växlar

## <a name="fixed-assets"></a>Anläggningstillgångar

Flera transaktionstyper uppdaterar lager med anläggningstillgångar. Exempel på detta är anskaffningar och avskrivningar.

Om funktionen massomvändning är avstängd kan transaktioner reverseras individuellt från **Leverantörstransaktioner** från sidan **Transaktioner för anläggningstillgång** eller från Leasing av tillgångar beroende på transaktionstyp.

Om funktionen Massåterföring är aktiverad kan en eller flera transaktioner för anläggningstillgång nu återföras från sidan **Verifikationstransaktioner** och från den journal som transaktionerna bokfördes från.

### <a name="reasons-why-transactions-cant-be-reversed"></a>Orsaker till varför transaktioner inte kan återföras

Transaktioner kan inte återföras av följande skäl:

- Räkenskapsperioden är spärr eller permanent stängd:

    - Om återföringsdatumet är en räkenskapsperiod som inte är öppen, kan transaktionen inte återföras.
    - Om transaktionen stöder inmatning av ett återföringsdatum kan transaktionen fortfarande återföras genom att återföringsdatumet ändras till en öppen period.

- Årsbokslutsprocessen har körts:

    - Transaktionens redovisningsdatum är ett räkenskapsår som har stängts i redovisningen. Även om en period i räkenskapsåret fortfarande kan vara öppen, kan transaktionen inte återföras om årsbokslutsprocessen för räkenskapsåret har körts. Räkenskapsåret har en annan status än perioderna i det.
    - Årsbokslut kan återföras och transaktionen kan återföras. Det här är kanske inte ett alternativ. Det kan vara enklare att registrera en återföringstransaktion manuellt i en öppen period under antingen det stängda räkenskapsåret eller nästa räkenskapsår, beroende på statusen för stängningsprocessen. Om en ny transaktion bokförs på en öppen period under räkenskapsåret som har gått igenom årsbokslutsprocessen vid årets slut, måste årsbokslutet köras igen.

- Anskaffningar:

    - Om anskaffningen inträffade på en inköpsorderleverantörsfaktura måste återföringen göras genom att en leverantörskreditfaktura fördes in. Mer information om hur du går till återföringstransaktion finns i [Skapa en returorder för inköp](../../supply-chain/procurement/tasks/create-purchase-return-order.md).
    - Anskaffningen genomfördes på en projekttransaktion.
    - Anskaffningen kan inte återföras efter att avskrivningen bokförts för tillgången. Avskrivningen måste återföras innan anskaffningen kan återföras.
    - Om status för värdemodellen eller avskrivningsregel för en anläggningstillgång inte är öppen kan transaktionen inte återföras.

- Avyttringar:

    - Avyttrande sker via en fritextfaktura:

        - Korrigeringen av en fritextfaktura blockeras om den innehåller en anläggningstillgång. Om tillgången avyttras via en journal kan fritextfakturan återföras från anläggningstillgångsposten.

    - Om status för värdemodellen eller avskrivningsregel för en anläggningstillgång inte är öppen kan transaktionen inte återföras.

- Avskrivning:

    - Avskrivningen **kan** återföras om efterföljande avskrivning också bokförs. Du får dock en varning eftersom det här sättet inte är ett bra tillvägagångssätt.
    - Om status för värdemodellen eller avskrivningsregel för en anläggningstillgång inte är öppen kan transaktionen inte återföras.

- Det finns transaktioner (eller återföringstransaktioner) för en viss tillgång och tillgångsbok för verifikationens transaktionsdatum eller senare.
- Transaktionen innehåller ett tillgångskonto, men återförs från sidan **Transaktioner för \<main account\>** eller från en felaktig delbok, till exempel kundfordringar eller leverantörsskulder:

    - Som det här orsaken föreslås kan vissa transaktioner i underordnade lager bara återföras från vissa sidor, även om funktionen Massåterföringar är aktiverad.
    - Om ett förvärv sker på en leverantörsfaktura som inte är inköpsorder eller en leverantörsfakturajournal kan den endast återställas från sidan **Leverantörstransaktioner** i Leverantörsreskontra.
    - Om en tillgång har anskaffats från Leasing av tillgång kan den återföras från sidan **Skuldtransaktioner** i Tillgångsleasing.
