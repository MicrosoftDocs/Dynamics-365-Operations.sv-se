---
title: Årsbokslut
description: I det här avsnittet beskrivs den nödvändiga inställningen och stegen för att köra årsslutsprocessen i redovisningen.
author: kweekley
manager: AnnBe
ms.date: 04/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerClosingSheet
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3f5b81ed788536a8b81ca53d6b6f12200836b6f5
ms.sourcegitcommit: dbff1c6bb371a443a0cd2a310f5a48d5c21b08ca
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/13/2020
ms.locfileid: "3259781"
---
# <a name="year-end-close"></a>Årsbokslut

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs den nödvändiga inställningen och stegen för att köra årsslutsprocessen i redovisningen. 

I slutet av ett räkenskapsår måste du köra årslutslutprocessen för att överföra ingående saldon till det nya året. De flesta företag kör årsbokslutsprocessen flera gånger. Första gången skulle vara för att få saldon flyttade till det nya räkenskapsåret. Årsbokslutet kan sedan köras igen så många gånger som krävs för att flytta saldon från justeringsposter till det nya räkenskapsåret. 

Vid årsbokslutsprocessen skapas två typer av möjliga transaktioner. En IB-transaktion skapas alltid och används för att skapa ingående balans i det nya räkenskapsåret. IB-transaktionen visar balansräkningarna under det nya räkenskapsåret och saldon från resultaträkningen i det reserverade resultatbokförarkontot under det nya räkenskapsåret. UB-transaktioner skapas eventuellt för att resultaträkningens saldon ska nollställas under räkenskapsåret som avslutas

## <a name="prepare-to-run-the-year-end-close"></a>Förbered körning av årsbokslut
Innan du kör årsslutsprocessen verifierar du inställningarna för följande: 

På sidan **Huvudkonto**:

-   Validera att **huvudkontotyp** anges korrekt för varje huvudkonto. Huvudkontotypen används för att avgöra om saldot för huvudkontot flyttas framåt som ett ingående saldo eller avslutas till balanserade vinstmedel i IB-transaktionen.
-   Fältet **IB-konto** kan användas för att föra över saldot för huvudkontot till ett nytt huvudkonto vid årsbokslutet. Det nya huvudkontot som har angetts i fältet **IB- kontot**. Vanligtvis används detta för balansräkningens huvudkonton när huvudkontot är inaktiverat och ett nytt huvudkonto används för det nya räkenskapsåret.

På sidan **Redovisningsparametrar** under **Stängning av räkenskapsår**:

-   Alternativet **Radera UB-transaktioner** används för att ange om den systemgenererade IB-transaktionen från föregående årsbokslut ska tas bort när årsbokslutet körs igen. Om det här alternativet ställs in på **Ja**, raderas föregående IB-transaktionen och en ny IB-transaktion skapas baserat på aktuella saldon. Om det här alternativet ställs in på **Nej**, stannar föregående IB-transaktion kvar och ytterligare en IB-transaktion skapas för att flytta fram saldon från justerade transaktioner som har bokförts efter föregående årsbokslut.
-   Alternativet **Skapa UB-transaktioner vid överföring** används för att skapa UB-transaktioner i räkenskapsåret som avslutas för att visa saldon på vinst-och förlustkonton till noll. Om det här alternativet ställs in på **Ja**, skapas både IB-transaktion och UB-transaktioner. Om det här alternativet ställs in på **nej**, skapas IB-transaktion i nästa räkenskapsår för att överföra saldona. Saldon på vinst- och förlustkonton ligger kvar i slutet av räkenskapsåret.
-   Alternativet **ange räkenskapsårets status till stängd permanent** används för att ställa in räkenskapsåret till permanent avslutad status. Inställningen används med försiktighet, eftersom perioder med statusen avslutad permanent inte kan öppnas igen, vilket förhindrar att justeringarna bokförs för räkenskapsåret. Det bästa är att ange detta som **Nej**.
-   Alternativet **verifikationsnumret måste fyllas i** används för att bestämma om ett verifikationsnummer är obligatoriskt när du kör årsbokslutsprocessen. Det är bäst att kräva ett verifikationsnummer för att enkelt identifiera IB-transaktion.

På sidan **räkenskapskalender**:

-   Nästa räkenskapsår måste finnas innan du kör årsbokslut. Nästa räkenskapsår krävs för att skapa ingående balanser i en ingående period.

På sidan **Redovisningskalender**:

-   Valfritt: Varje räkenskapsperiod för räkenskapsåret som stängs kan tilldelas **Väntar** för att förhindra att nya transaktioner förs in. När justeringar identifieras kan väntande perioder öppnas på nytt när du bokför justeringar, även om årsslutsprocessen redan har körts.

## <a name="define-year-end-close-templates"></a>Definiera årsbokslutsmallar
Årsbokslutsprocessen kan köras när systemet är konfigurerat. På sidan **årsbokslut** kan en mall kan definieras för gruppen med juridiska personer där årsbokslutsprocessen ska köras. Mallen kommer att återanvändas nära varje årsskifte, men kan ändras om din organisation ändras. 

Först definierar du **gruppnamn** för mallen och väljer räkenskapskalendern. Gruppnamnet ska identifiera gruppen av juridiska personer.  Exempelvis kan mallarna ställas in baserat på geografiska områden, med separata grupper för nordamerikanska juridiska personer och EMEA juridiska personer och APAC juridiska personer. 

Juridiska personer kan sedan läggas till i mallen. Juridiska personer kan läggas till genom att välja en organisationshierarki eller genom att välja de juridiska personerna. Om en organisationshierarki väljs, läggs endast juridiska personer i hierarkin till som använder den valda skattekalendern till mallen. Om du använder juridiska personer som vill lägga till mallen kan endast juridiska personer med samma räkenskapskalender läggas till. Samma räkenskapskalender krävs eftersom årsbokslutet körs genom att välja ett räkenskapsår som kan variera från en kalender till en kalender. 

När de juridiska enheterna har lagts till, definierar du de viktigaste boksluten för varje juridisk enhet. Fältet **Datum för senaste årsbokslut** uppdateras varje gång årsbokslutet körs för den juridiska personen. 

Fliken **ekonomiska dimensionen** används för att definiera vilka ekonomiska dimensioner som ska användas på IB-transaktionen. Observera att inställningarna du definierar endast gäller den valda juridiska personen i rutnätet **juridiska personer**. Inställningen upprepas för varje juridisk person i rutnätet. 

**Överför dimensioner i balansräkningen** används för att definiera om de ekonomiska dimensionerna i transaktioner som bokförts på balansräkningskonton ska hanteras på IB-transaktion. Det bästa är att ange detta som **Ja**. **Överför resultatdimensioner** används för att definiera vilka ekonomiska dimensionerna i transaktioner på bokförda vinst- och förlustkontot överförs till huvudkontot för balanserade vinstmedel. Först identifierar du de ekonomiska dimensionerna som är relevanta för den valda juridiska personen. Detta kan inkludera alla ekonomiska dimensioner bokförda under året, även om den ekonomiska dimensionen inte är en del av en aktiv kontostruktur. Härnäst definierar du varje dimension som **Stäng enstaka** eller **Stäng alla**.  Standardvärdet är **Stäng alla**, som har den ekonomiska dimensionens ursprungliga värden från bokförda transaktioner och använder dem för att skapa ingående saldon för balanserad vinst eller förlust. Separata ingående saldon för balanserad vinst eller förlust skapas för varje unik kombination av värden för ekonomiska dimensioner. Om **Stäng enstaka** är markerat kommer alla transaktioner som bokförs med den ekonomiska dimensionen sammanfattas i en balanserade vinstmedel ingående balans för det dimensionsvärde som angetts i fältet efter **Stäng enstaka**. Anta att alla transaktioner för räkenskapsåret har bokförts med kontostrukturen för huvudkontot - avdelning. I Avdelning ekonomiska dimensionen på mallen, **Stäng enstaka** är markerad och värdet 100. Om den totala intäkten för alla transaktioner som bokförts till avdelningar 200, 300 och 400 är 100,000 kr skapas en ingående balans för Balanserade vinstmedel - 100. Om du väljer **Stäng enstaka** och lämnar värdet för ekonomisk dimension tomt kommer alla transaktioner bokföras till balanserade vinstmedel med det dimensionsvärdet tomt. 

Årsbokslutsprocessen följer inte kontostrukturer. Detta beror på att kontostrukturer kan ändras under ett räkenskapsår och det är inte alltid möjligt att identifiera relevanta kontostrukturen på grund av dessa ändringar.  När IB-transaktioner skapas flyttas saldona framåt med ekonomiska dimensioner enligt årsbokslutsmallen. Posterna i ingående saldon kan inte längre inkludera ekonomiska dimensioner i aktuell kontostruktur och segmentkombinationerna är inte längre giltiga i den aktuella kontostrukturen. Om organisationen vill utesluta en ekonomisk dimension för balanserade vinstmedel ingående balans anger du ekonomiska dimensionen **Stäng enstaka** och lämnar dimensionsvärdet tomt.

## <a name="run-the-year-end-close-process"></a>Körning av årsbokslutprocess
När årsbokslutsmallar skapas initieras årsbokslutsprocessen genom att välja **Kör årsbokslut** i åtgärdsfönstret. Välj alla eller en underuppsättning juridiska personer från den mall för vilken du vill köra årsbokslutet. När du kör årsbokslut för första gången i ett räkenskapsår, kommer du troligen att välja de juridiska personerna för att skapa ingående balanser för de juridiska personerna. Om du kör årsbokslut igen måste du köra processen endast för de juridiska personerna som justerar transaktionerna bokfördes. 

Välj det räkenskapsår som du vill köra den nära årsslutsprocess mot. Om det finns fler än en UB-period för den första perioden på räkenskapsåret, blir **Periodnamn** tillgängligt så att du kan välja vilken UB-period som UB-transaktioner ska bokföras på om inställningarna har definierats för att skapa UB-transaktioner. 

Ange ett verifikationsnummer som kan krävas eller inte, beroende på inställningarna i redovisningsparametrar. Samma verifikationsnummer används för alla juridiska personer som har valts för årsbokslutsprocessen. Verifikationsnummer genereras inte för att använda nummersekvens. Det är bäst att ange ett verifikationsnummer, även om det inte är nödvändigt. Ange ett verifikationsnummer gör det enklare att hitta ingående transaktion i det nya räkenskapsåret. Om ett verifikationsnummer inte anges kommer verifikationen vara tom för IB-transaktion. 

Om du vill återföra ett föregående årsbokslut för valt räkenskapsår anger du **Ångra föregående slut** till **Ja**. Årsbokslutet återställs, men processen kan köras när som helst. Om du återför ett årsbokslut kommer **Datum för senaste årsbokslut** inte att vara tillgänglig. 

Årsbokslutprocessens standardvärden som ska köras i batchläge. Det är bäst att köra processen i batchläge för att ge användaren möjlighet att återgå till andra aktiviteter. Efter att årsbokslutsprocessen är slutförd **Datum för senaste årsbokslut** uppdateras med sessionsdatum.

Mer information finns i [Stäng redovisningen vid periodslut](close-general-ledger-at-period-end.md) och [Stäng räkenskapsåret](tasks/close-fiscal-year.md).



