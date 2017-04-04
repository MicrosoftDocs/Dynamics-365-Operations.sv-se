---
title: "Årsbokslut"
description: "Beskriver nödvändiga inställningar och kör redovisningen Stäng årsbokslutsprocessen."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerClosingSheet
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 926ee087a0e0c4743f29315b1d82c7d37e95be28
ms.openlocfilehash: 22233cfa1df79076c8ea42f75ea309bac990d574
ms.lasthandoff: 03/31/2017


---

# <a name="year-end-close"></a>Årsbokslut

Beskriver nödvändiga inställningar och kör redovisningen Stäng årsbokslutsprocessen. 

I slutet av ett räkenskapsår måste du köra Stäng årsslutsprocessen för att överföra ingående saldon för det nya året. De flesta företag kör årsslutsprocessen nära flera gånger. Första gången skulle kunna få saldon flyttas till det nya räkenskapsåret. Årets slut stängs kan sedan köra den igen, som ofta krävs att flytta saldon från justeringsposter i det nya räkenskapsåret. 

Vid årets slut stängningsprocessen finns det två typer av möjliga transaktioner skapas. En ingående transaktion skapas alltid och används för att skapa ingående balans i det nya räkenskapsåret. Ingående transaktion visar kontosaldon redovisningskonto för balansräkning i det nya räkenskapsåret och saldon från kontosaldon resultat redovisningen i balanserade vinstmedel redovisningskonto i det nya räkenskapsåret. UB-transaktioner skapas också för att saldon för resultatkonton ner till noll i räkenskapsåret stängs.

## <a name="prepare-to-run-the-year-end-close"></a>Förbered körning av årets slut stängs
Innan du kör årsslutsprocessen Stäng verifiera inställningarna för följande: 

På sidan **Main account**:

-   Validera den **huvud kontotyp** anges korrekt för varje huvudkonto. Kontotypen huvud används för att avgöra om saldot för huvudkontot flyttas framåt som en ingående balans eller stängda till balanserade vinstmedel i den öppna transaktionen.
-   Den **öppna kontot** fältet kan användas för att föra över saldot för huvudkontot till ett nytt huvudkonto vid årets slut stängs. Nytt huvudkonto som har angetts i den **öppna kontot** fält. Vanligtvis används detta för balansräkningskonton huvudsakliga när huvudkontot är inaktiverat och ett nytt huvudkonto för det nya räkenskapsåret.

I den **allmänna redovisningsparametrar** sidan **stängning av räkenskapsår**:

-   Den **ta bort slutet av år transaktioner** alternativet används för att ange om systemgenererade ingående transaktion från föregående årsslut nära ska tas bort vid årets slut stängning körs igen. Om det här alternativet ställs in på **Ja**, föregående öppna transaktionen tas bort och en ny ingående transaktion skapas baserat på aktuella saldon. Om det här alternativet ställs in på **nr**, föregående ingående transaktion kvar och ytterligare en ingående transaktion skapas för att flytta fram saldon från justera transaktioner som har bokförts efter föregående årsslut Stäng.
-   Den **Skapa UB-transaktioner vid överföring** alternativet används för att skapa UB-transaktioner i räkenskapsåret stängas för att visa saldon på vinst-och förlustkonton till noll. Om det här alternativet ställs in på **Ja**, både ingående transaktion och UB-transaktioner skapas. Om det här alternativet ställs in på **nr**, ingående transaktion skapas i nästa räkenskapsår vill överföra saldona. Kontosaldon resultat ligger kvar i slutet av räkenskapsåret.
-   Den **ange räkenskapsårets status stängd permanent** alternativet används till statusen permanent avslutade räkenskapsåret. Inställningen används med försiktighet, eftersom alla perioder med statusen Stängd permanent inte kan öppnas igen, förhindra justeringarna bokförs för räkenskapsåret. Det är bäst om du vill ange **nr**.
-   Den **verifikationsnumret måste fyllas i** alternativet används för att bestämma om ett verifikationsnummer är obligatoriska när du kör årsslutsprocessen Stäng. Det är bäst att kräva ett verifikationsnummer för att enkelt identifiera ingående transaktion.

I den **räkenskapskalendern** sida:

-   Nästa räkenskapsår måste finnas innan du kör årets slut stängs. Nästa räkenskapsår krävs för att skapa ingående balanser i en ingående period.

I den **Redovisningskalender** sida:

-   Valfritt: Varje räkenskapsperiod för räkenskapsåret stängs kan tilldelas **fram** att nya transaktioner förs in. När justeringar identifieras vidare håller perioder kan öppnas på nytt när du bokför justeringar, även om Stäng årsslutsprocessen har redan körts.

## <a name="define-year-end-close-templates"></a>Definiera aktiviteter nära mallar
Stäng årsbokslutsprocessen kan köras när systemet är konfigurerat. I den **årsslutsstängning** sidan en mall kan definieras för gruppen med juridiska personer där årsslutsstängning processen ska köras. Mallen för huvudnycklar används på varje vid årets slut stängs, men det kan ändras om du ändrar i organisationen. 

Först definierar du den **gruppnamn** för mallen och välj räkenskapskalendern. Gruppnamnet ska identifiera gruppen av juridiska personer.  Exempelvis kan mallarna ställas in baserat på geografiska områden, med separata grupper för nordamerikanska juridiska personer och juridiska personer i EMEA APAC juridiska personer. 

Juridiska personer kan sedan lägga till mallen. Juridiska personer kan läggas till genom att välja en organisationshierarki eller välja de juridiska personerna. Överför en organisationshierarki läggs endast juridiska personer i hierarkin som använder vald räkenskapskalender till mallen. Om du använder juridiska personer som vill lägga till mallen kan endast juridiska personer med samma räkenskapskalender läggas till. Samma räkenskapskalender krävs eftersom årets slut stängning körs genom att välja ett räkenskapsår kan variera från en kalender till en kalender. 

Definiera när de juridiska personerna läggs balanserade vinstmedel huvudkonton för varje juridisk person. Den **dag förra årets slut stänger** uppdateras varje gång årsslut stängning körs för den juridiska personen. 

Den **ekonomiska dimensionen** fliken används för att definiera vilka ekonomiska dimensioner som ska användas på den öppna transaktionen. Observera att du definierar inställningarna gäller endast den valda juridiska personen i den **juridiska personer** rutnät. Inställningen upprepas för varje juridisk person i rutnätet. 

Den **överför dimensioner i balansräkningen** används för att definiera om de ekonomiska dimensionerna i transaktioner som bokförts på balansräkningskonton ska hanteras på ingående transaktion. Det är bäst att ange **Ja**. Den **överför resultat dimensioner** används för att definiera vilka ekonomiska dimensionerna i transaktioner bokförda vinst- och förlustkontot överförs till huvudkontot balanserade vinstmedel. Först identifiera de ekonomiska dimensionerna som är relevanta för den valda juridiska personen. Detta kan bero på ekonomiska dimensioner bokförs mot under året, även om den ekonomiska dimensionen inte är en del av en aktiv kontostruktur. Härnäst definierar du varje dimension som **nära en** eller **stänga alla**.  Standardvärdet är **stänga alla**, som har den ekonomiska dimensionen ursprungliga värden från bokförda transaktioner och använder dem för att skapa ingående saldon för balanserad vinst eller förlust. Separata balanserade vinstmedel ingående saldon skapas för varje unik kombination av värden för ekonomiska dimensioner. Om **nära en** är markerat alla transaktioner som bokförs med den ekonomiska dimensionen sammanfattas i en balanserade vinstmedel ingående balans för det dimensionsvärde som angetts i fältet efter **nära en**. Anta att alla transaktioner för räkenskapsåret har bokförts med kontostrukturen för huvudkontot - avdelning. I den ekonomiska dimensionen avdelning på mallen, **nära en** är markerad och värdet 100. Om den totala intäkten för alla transaktioner som bokförts till avdelningar 200 300 och 400 $100,000, skapas en ingående balans för Retained intäkter - 100. Om du väljer **nära en** och inget värde för ekonomisk dimension, alla transaktioner bokförs till balanserade vinstmedel med det dimensionsvärdet är tomt. 

Stäng årsbokslutsprocessen följer inte kontostrukturer. Detta beror på att kontostrukturer kan ändras under ett räkenskapsår och det är inte alltid möjligt att identifiera relevanta kontostrukturen på grund av dessa ändringar.  När IB-transaktioner skapas flyttas saldona framåt med ekonomiska dimensioner enligt års slut Stäng mallen. Posterna i början saldon inkluderar ekonomiska dimensioner inte längre i aktuellt konto struktur kombinationerna av och segment som inte längre är giltig i aktuell kontostrukturen. Om organisationen vill utesluta en ekonomisk dimension för balanserade med ingående balans, ekonomiska dimensionen **nära en** och lämna det tomt dimensionsvärdet.

## <a name="run-the-year-end-close-process"></a>Kör årsslutsprocessen Stäng
När aktiviteter nära mallarna skapas Stäng årsbokslutsprocessen initieras genom att välja **räkenskapsåret kör** i åtgärdsfönstret. Välj alla eller en del av rättssubjekt från mallen som du vill köra årets slut stängs. När du kör årets slut stänger för första gången i ett räkenskapsår, kommer troligen du de juridiska personerna Skapa ingående balanser för de juridiska personerna. Om du kör årets slut stängs igen måste du raderingen för endast de juridiska personerna som justera transaktionerna bokfördes. 

Välj det räkenskapsår som du vill köra den nära årsslutsprocess mot. Om det finns fler än en UB-period för den första perioden på räkenskapsåret, den **namnet på den** fält blir tillgängliga så att du kan välja vilken UB-period som UB-transaktioner om inställningarna har definierats för att skapa UB-transaktioner. 

Ange en verifikation numrera som eller utelämnas, beroende på inställningarna i allmänna redovisningsparametrar. Samma verifikationsnummer används för alla juridiska personer som har valts för nära årsslutsprocess. Verifikationsnummer genereras inte med hjälp av en nummerserie. Det är bäst att ange ett verifikationsnummer, även om det inte är nödvändigt. Ange ett verifikationsnummer gör det enklare att hitta ingående transaktion i det nya räkenskapsåret. Om ett verifikationsnummer inte angett vara verifikationen tomt för ingående transaktion. 

Om du vill återföra en föregående årsslut nära för valt räkenskapsår **Ångra tidigare nära** till **Ja**. Årets slut stängs återställs, men processen kan köras när som helst. Om du återför en vid årets slut, Stäng den **dag förra årets slut stänger** är inte tillgänglig. 

Stäng årsbokslutsprocessen standard körs i batchläge. Det är bäst att raderingen i batchläge ge användaren möjlighet att återgå till andra aktiviteter. Efter Stäng årsslutsprocess den **dag förra årets slut stänger** uppdateras med datum för klientsessionen.

Mer information finns i [Stäng redovisningen vid periodslut](close-general-ledger-at-period-end.md).


