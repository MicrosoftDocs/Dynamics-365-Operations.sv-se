---
title: Granska inkasseringsinformation
description: I den här avsnittet förklaras hur du granskar inkassoinformation samt olika inställningsalternativ och inkassotransaktioner.
author: ShivamPandey-msft
ms.date: 08/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustCollectionsPool, SysQueryForm, CustCollectionsAgent, OMTeamSelectMemberDialog, CustVendReportInterval, CustParameters, CustAgingSnapshot, CustVendAgingBucketLookUp, CustCollectionsPoolsListPage, CustCollectionsContactPart, CustCollections
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4d0cb09eb6ac455d72e9dd051065625475581416
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2022
ms.locfileid: "8725049"
---
# <a name="review-collections-information"></a>Granska inkasseringsinformation

[!include [banner](../../includes/banner.md)]

I den här avsnittet förklaras hur du granskar inkassoinformation samt olika inställningsalternativ och inkassotransaktioner. I den här proceduren används demonstrationsföretaget USMF.

## <a name="create-customer-pools"></a>Skapa kundpooler
1. I navigeringsfönstret, gå till **Moduler > Kredit och inkasso > Inställningar > Kundpooler**.
- Använd den här sidan för att ställa in kundpooler, som är frågor som definierar en grupp med kundkonton som kan visas och hanteras för samlingar eller åldersfördelningsprocesser. Använd kundpooler för att filtrera information på listsidan **Inkasso** och på relaterade listsidor. Du kan även använda kundpooler för att filtrera de kundkonton som är inkluderade när ögonblicksbilder av åldersfördelning skapas.  
- Du kan använda kundpooler för att filtrera de kundkonton som är inkluderade, när ögonblicksbilder av åldersfördelning skapas.  
2. Välj **Ny**.
3. I fältet **Pool-ID** skriver du ett värde.
4. I fältet **Poolbeskrivning** skriver du ett värde.
5. Klicka på **Välj kriterier för pool**.
6. I fältet **Kriterier** skriver du ett värde.
7. Välj **OK**.
8. Välj **Förhandsgranska kundpool**.

## <a name="create-collections-agents"></a>Skapa inkassohandläggare
1. I navigeringsfönstret, gå till **Moduler > Kredit och inkasso > Inställningar > Inkassohandläggare**.  
- Använd den här sidan för att ställa in arbetare som inkassohandläggare och tilldela kundpooler till dem. En *inkassohandläggare* är en person som arbetar med kunder för att säkerställa att betalningarna samlas in i tid.  
- Inkassohandläggare som ställs in på den här sidan läggs till automatiskt till i ett samlingsteam. Om ett team har valts i fältet **Team** på sidan **Parametrar för kundreskontra** läggs inkassohandläggare till för teamet. Om ett team inte har valts skapas en nytt team med namnet Inkasso automatiskt och inkassohandläggarna läggs till i teamet.  
2. Välj önskad agent och välj sedan **Lägg till** på sidan.
3. I fältet **Pool-ID** väljer du önskad post i listrutan.
4. Markera eller avmarkera kryssrutan **Standardpool**.
- Välj det här alternativet för att inkluderas alla kundpooler i filterlistor för den valda inkassohandläggaren. Om det här alternativet inte väljs är endast de kundpooler som har tilldelats inkassohandläggaren tillgängliga i filterlistor.  

## <a name="create-aging-period-definition"></a>Skapa definition för åldersfördelningsperiod
1. I navigeringsfönstret, gå till **Moduler > Kredit och inkasso > Inställningar > Definitioner för åldersfördelningsperiod**.
- Med hjälp av åldersfördelningsperioddefinitioner kan du analysera förfallotiden för kundkonton och leverantörskonton, utifrån det datum som du anger. Varje åldersfördelningsperiod som du ställer in för åldersfördelningsperioddefinitionen, motsvarar en kolumn i listsidan eller i formuläret eller rapporten, när analysen utförs.  
2. Välj **Ny**.
3. Skriv ett värde i fältet **åldersfördelningsperiod**.
4. I fältet **Beskrivning** anger du ett värde.
- Ange periodnamnet, enheten och intervallet för varje åldersfördelningsperiod ska inkluderas i åldersfördelningsperioddefinitionen. Raden som innehåller 0 (noll) i fältet Enhet motsvarar datumet som analysen körs på. Rader före noll innehåller -1 och rader efter noll har 1 som standardvärde i fältet Enhet, men det kan ändras. Välj **upp** och **ned** för att ordna om raderna. Nollraden (0) kan inte flyttas.  
- Placera pekaren där du vill infoga en ny rad och klicka sedan på **Lägg till**.  
- Välj en indikator som motsvarar åldersfördelningsperioden i formuläret **Inkasso** och på listsidan. Du kan till exempel välja en grön indikator för en aktuell period, en gul indikator för en 30-dagar-förfallet-period och en röd indikator för en 90-dagar-förfallet-period.  
- Välj utskriftsriktning för definitionen av åldersfördelningsperioden. Valet bestämmer i vilken ordning kolumnerna ska visas i rapporten Åldersfördelning för kunder eller rapporten Åldersfördelning för leverantörer.  
  - Framåt – skriv ut kolumner i samma ordning som rubrikerna visas i registret, med början från den översta raden.  
  - Bakåt – skriv ut kolumner i bakvänd ordning som rubrikerna visas i registret, med början från den nedersta raden.    

## <a name="setup-collections-parameters"></a>Ställ in parametrar för inkasso
1. I navigeringsfönstret, gå till **Moduler > Kredit och inkasso > Inställningar > Parametrar för kundreskontra**.
2. Markera fliken **Inkasso**.
3. Utöka eller komprimera avsnittet **Inkassostandarder**.
- Välj en åldersfördelningsperiod för den ögonblicksbild av åldersfördelning som används som standard i formuläret **Inkasso**.  
- Välj ett team som inkassohandläggare tilldelas till i formuläret **Inkassohandläggare**. Endast team som har teamtypen Inkasso visas i listan.  
4. Expandera eller komprimera avsnittet **Avskrivning**.
- Välj det journalnamn som har ställts in för dagliga redovisningsjournaler som ska användas när en transaktion skrivs av genom att använda formuläret **Inkasso** eller relaterade listsidor.  
- Välj standardorsakskoden som ska användas när avskrivningstransaktioner skapas med hjälp av formuläret **Inkasso** eller relaterade listsidor.  
- Välj det här alternativet om du vill skapa en separat journalrad för momsbelopp när avskrivningstransaktioner skapas med hjälp av sidan **Inkasso** eller relaterade listsidor. Om du väljer det här alternativet kan du enkelt följa de momsbelopp som ingår i avskrivningstransaktioner. Du kan följa momsbeloppen separat för att enklare justera din momsskulder för den berörda perioden.  
5. Utöka eller komprimera avsnittet **E-postmall**.
- Välj e-postmallen som ska användas när du skickar ett e-postmeddelande via **E-post > åtgärden Transaktioner** till kontaktåtgärd i formuläret **Inkasso**.  
- Välj e-postmallen som ska användas när du skickar ett kundutdrag som en e-postbilaga via **E-post > åtgärden Utdrag** till kontaktåtgärd i formuläret **Inkasso**.  
- Välj e-postmallen som ska användas när du skickar ett e-postmeddelande via **E-post > åtgärden Transaktioner** till säljare i formuläret **Inkasso**.  

## <a name="age-customer-balance"></a>Åldersfördelat kundsaldo
1. I navigeringsfönstret, gå till **Moduler > Kredit och inkasso > Periodiska uppgifter > Åldersfördelade kundsaldon**.
- Välj en åldersfördelningsperiod Ögonblicksbilden av åldersfördelningsprocessen åldrar transaktioner enligt åldersfördelningsperioderna som definieras i den valda åldersfördelningsperioddefinitionen.  
- Välj en kundpool eller lämna det här fältet tomt om du vill skapa en ögonblicksbild av åldersfördelning för alla kunder. Om en kundpool väljs används ögonblicksbild av åldersfördelningsprocessen bara för kundkonton som ingår i kundpoolen. Den valda kundpoolen måste vara av typen Ögonblicksbild av åldersfördelning.  
- Välj den typ av datum som ögonblicksbilden av åldersfördelning ska baseras på.  
  - Transaktionsdatum – åldern för varje transaktion baserat på dess transaktionsdatum.    
  - Förfallodatum – åldern för varje transaktion baserat på dess förfallodatum.    
  - Dokumentdatum – åldern för varje transaktion baserat på dess dokumentdatum.  
- Välj vilket datum som ska användas som det aktuella datumet för ögonblicksbilden av åldersfördelning. Åldersfördelningsperioder beräknas utifrån detta datum.    
  - Dagens datum – använd systemdatumet. Använd det här alternativet om bearbetning har ställts in för att inträffa i en återkommande batch. Om du använder detta datum, kan den återkommande batchen köras regelbundet och systemdatumet vid den tidpunkten används.    
  - Markerat datum – använd ett datum som du anger. Om du väljer det här alternativet anger du ett åldersfördelningsdatum.  
2. Välj **OK**.

## <a name="view-aged-customer-balances"></a>Visa åldersfördelade kundsaldon
1. I navigeringsfönstret, gå till **Moduler > Kredit och inkasso > Inkasso > Åldersfördelade saldon**.
- Använd den här listsidan för att visa kundsaldon och föråldrade belopp per åldersfördelningsperiod. Den här informationen lagras i en ögonblicksbild över åldersfördelningen. Åldersfördelningsperioderna bestäms av åldersfördelningsperioddefinitionen som används. Åldersfördelningsperioddefinitionen hämtas från kundpoolen, om en sådan har angetts för poolfrågan. Om kundpoolen inte har någon åldersfördelningsperioddefinition används standardåldersfördelningsperioddefinitionen som angetts i formuläret Parametrar för kundreskontra.  
2. Expandera faktaboxen **Kontakt**. Här kan du visa kontaktinformation:
- Inkassokontakten för kunden.  
- Standardsäljaren för kunden.  
3. Expandera faktaboxen **Kreditgräns**.
- Använd faktaboxen **Kreditinformation** för att visa information om kreditgränsen och om aktuell balans för kunden.  

## <a name="view-customer-collections-details"></a>Visa information om kundkrav
1. Kontrollera att önskad post är markerad.
2. Expandera faktaboxarna **Adress**, **Kontact**, **Åldersfördelning** och **Kreditgräns** för att visa den angivna informationen.
3. Välj **Inkasso** i åtgärdsfönstret.
- Uppdatera ögonblicksbilden av åldersfördelning för kunden med hjälp av det aktuella datumet som det åldersfördelningsdatum som transaktionsdatumen jämförs med. Om ögonblicksbilden av åldersfördelning innehåller information om flera juridiska personer, innehåller den uppdaterade ögonblicksbilden av åldersfördelning information för samma uppsättning juridiska personer. Beloppen lagras i redovisningsvalutan för den juridiska person du är inloggad på när du uppdaterar ögonblicksbilden av åldersfördelning.  
- Välj en åldersfördelningsperiod Som standard visas åldersfördelningsperioddefinitionen, som är kopplad till ögonblicksbilden av åldersfördelning för kunden. Åldersfördelningsperioddefinitionen kontrollerar åldersfördelningsperioderna och beloppen som visas i faktarutorna **Åldersfördelade saldon** och **Kreditinformation**.  
- Öppna en meny som innehåller följande objekt:    
  - Företag – visa belopp i faktaboxarna Åldersfördelade saldon och Kreditinformation i den juridiska personens redovisningsvaluta.  
  - Kund – visa belopp i faktaboxarna Åldersfördelade saldon och Kreditinformation i kundens valuta.  
- Markera en eller flera juridiska personer i kundens ögonblicksbild av åldersfördelning för vilken du vill visa information. De juridiska personerna som visas i listan valdes när ögonblicksbilden av åldersfördelning skapades.  
- Visa kundens utdrag i Microsoft Excel-format. Du kan välja ett startdatum för intervallet för de transaktioner som ska inkluderas på utdraget och för att avgöra om du endast vill inkludera öppna transaktioner eller båda öppna och kvittade transaktioner. Om ögonblicksbilden av åldersfördelning innehåller information om flera juridiska personer, informationen för alla juridiska personer inkluderas.  
- Öppna formuläret **Dokument**, där du kan skapa eller redigera dokument eller anteckningar.  
4. Klicka på **Kommunicera** i åtgärdsfönstret.  
- Öppna Outlook där du kan skicka ett e-postmeddelande till kontakten som anges i fältet Kontakt. Om en inkassokontakt inte har angetts används den primära adressen för kunden. Om en primär kontakt inte anges, e-postmeddelanden skickas till den första adressen som är angiven i formuläret **Kontakter**. De transaktioner som väljs inkluderas som en bilaga. Bilagan är i Excel-format och innehåller tre kalkylblad. En mall för e-postmeddelanden till kundkontakter kan anges i formuläret **Parametrar för kundreskontra**.  
- Den här knappen är inte tillgänglig om den kontakt som väljs i det här formuläret inte har en e-postadressinställning.  
- Förbered ett utdrag och öppna Outlook, där du kan skicka ett e-postmeddelande som har ett utdrag anslutet till den registrerade adressen i fältet **Kontakt**. Om en inkassokontakt inte har angetts används den primära adressen för kunden. Om en primär kontakt inte anges, e-postmeddelanden skickas till den första adressen som är angiven i formuläret **Kontakter**.  
- Den här knappen är inte tillgänglig om den kontakt som väljs i det här formuläret inte har en e-postadressinställning.  
- Öppna Outlook, där du kan skicka ett e-postmeddelande till den medarbetare som anges för säljaren för försäljningsgruppen som har tilldelats kunden. Om transaktioner väljs inkluderas den som en bilaga. Bilagan är i Excel-format och innehåller två kalkylblad. En mall för e-postmeddelanden till säljaren kan anges i formuläret **Parametrar för kundreskontra**.  
- Den här knappen är inte tillgänglig om den säljare som visas i det här formuläret inte har en e-postadressinställning.  
- Visa och utför transaktionsåtgärder för kunden. Om du använder centraliserade betalningar, inkluderas informationen om alla juridiska personer som är inkluderade i kundens ögonblicksbild av åldersfördelning. Du kan begränsa informationen för en juridisk person genom att välja **Företag** i gruppen **Välj** i åtgärdsfönstret.  
- Välj inkasseringsstatusen för de valda transaktionerna.    
  - Inte omtvistat – ingen inkasseringsåtgärd har inträffat för transaktionen.    
  - Omtvistat – kunden har meddelat dig att det finns ett problem med transaktionen.    
  - Lovat att betala – kunden har lovat att betala transaktionsbeloppet.    
  - Löst – alla problem med transaktionen har lösts och ingen ytterligare inkasseringsåtgärd behövs.  
- Öppna en meny och välj något av följande objekt för att ange vilka transaktioner som ska visas i det här formuläret:    
  - Öppna – visa enbart redovisningstransaktioner som inte har kvittats.    
  - Öppna och stängda – visa alla transaktioner, både de som kvittats och de som inte har kvittats.  
- Bearbeta den valda betalningen som en betalning med otillräckliga medel.    
  - Den här knappen är endast tillgänglig om den valda transaktionen är en betalning (ett kreditsaldo utan en faktura) som anges i en betalningsjournal, ett bankkonto är fördelat till transaktionen, och betalningen inte tidigare har annullerats.  
- Skriv av de valda transaktionerna.  
- Välj de valda transaktionerna för kvittning mot varandra.  
- Öppna formuläret **Ursprungsdokument**, där du kan visa och skriva ut dokumentet för den valda transaktionen.  
- Öppna en **meny** som innehåller följande objekt:    
  - Inkasso – visa enbart aktiviteter som har skapats i formuläret Inkasso.    
  - Alla – visa alla aktiviteter för kunden, oavsett var aktiviteterna skapades.  
- Öppna en **meny** som innehåller följande objekt:    
  - Öppna – visa enbart aktiviteter som inte har stängts.    
  - Öppna och stängda – visa alla aktiviteter, oavsett status.  
- Välj ett inkasseringsärende som tilldelats kunden eller lämna det här fältet tomt. Om ett ärende är markerat, visas endast transaktioner och aktiviteter som är kopplade till ärendet i det här formuläret.  
5. Välj **Visa lista**.
- Markera ett kundkonto eller acceptera standardvärdet. Som standard är det här det valda kundkontot på listsidan eller i formuläret från vilket du öppnade det här formuläret. Om du öppnade formuläret från en listsida, kunderna i listan är de kunder som ingår i inkassopoolen som används på listsidan.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
