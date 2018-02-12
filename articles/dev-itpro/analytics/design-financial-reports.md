---
title: Visa och utforma ekonomiska rapporter
description: "Denna artikel innehåller övningar som förklarar hur du visar och skapar ekonomiska rapporter för Microsoft Dynamics 365 for Finance and Operations."
author: jcart1106
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: FinancialReportingSetup
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 10814
ms.assetid: cd5f6483-c09b-4c2d-9336-d22eb6ab6e4f
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 86597a81b4dcfb14cbc88667fbb1db214133c6e5
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="view-and-design-financial-reports"></a>Visa och utforma ekonomiska rapporter

[!include[banner](../includes/banner.md)]


Denna artikel innehåller övningar som förklarar hur du visar och skapar ekonomiska rapporter för Microsoft Dynamics 365 for Finance and Operations. Ekonomisk rapportering består av en visningsupplevelse i Finance and Operations och en enklicks-rapportdesigner där du kan skapa och redigera ekonomiska rapporter.  

<a name="exercise-1-generate-and-explore-a-default-financial-report"></a>Övning 1: Generera och undersök en ekonomisk standardrapport
-----------------------------------------------------------

För den här övning ska du generera och undersöka en befintlig standardrapport. Den här rapporten innehåller alla konton och även kontoegenskaper (attribut) för kontona. Du ska gå nedåt till transaktionsdetaljer, tillämpa dimensionsfilter och ändra valutan i rapporten. Först ska du uppdatera visningsordningen för dimensioner för ekonomisk rapportering. På så sätt kan du välja hur dimensionerna visar inte bara när du designar och visar ekonomiska rapporter.

1.  Gå till **Konfiguration av ekonomisk dimension för integrering av applikationer** under **Dimensioner i kontoplanen** i redovisningen.
2.  Flytta dimensionerna till följande ordning:
    1.  Huvudkonto
    2.  Affärsenhet
    3.  Kostnadsställe
    4.  Avdelning

    Obs! De andra dimensionerna kan ligga kvar i den ordning som de för närvarande har.
3.  Spara dimensionskonfigurationen. Sedan ska du generera en rapport och utforska uppgifterna i rapporten.
4.  Gå till **Ekonomiska rapporter** under **Förfrågningar och rapporter** i redovisningen.
5.  Markera raden för rapporten som heter **Huvudbokdetalj – standardinställning**.
6.  Välj **Redigera**. Obs! Du uppmanas att hämta enklicks-rapportdesignern och att logga in. Använd dina autentiseringsuppgifter när du loggar in.
7.  Ändra basåret till 2012 och välj **Generera**. När en rapport genereras via rapportutformaren kommer den at öppnas i en ny webbläsarflik. Du kan antingen granska rapporten i den nya webbläsarfliken eller också gå till din ursprungliga webbläsarfliken och öppna rapporten därifrån genom att välja den i listan **Finansiella rappporter**.
8.  Välj ett av beloppen i den öppna rapporten för att gå nedåt till kontodetaljeran i rapporten.
9.  Välj ett konto med data i kontodetaljerna och **gå nedåt till rapporttransaktionsnivån**. På rapporttransaktionsnivån kan du se egenskaperna (attribut )som togs med i designen i den här rapporten. Beroende på transaktionen och kontot, visas några eller alla attribut.
10. Stäng rapporttransaktionsnivån.
11. Markera samma eller ett annat konto och **öppna verifikationstransaktioner**. Verifikationstransaktioner filtreras till period, år och konto + dimensionskombinationen för det valda kontot. Från verifikationstransaktioner kan du välja att undersöka annan information om transaktionen.
12. Stäng verifikationstransaktioner. I en ekonomisk rapport kan du välja att visa data antingen för ett annat period och ett annat år eller med olika attribut och dimensioner. Det gör du genom att använda **Rapportalternativ**.
13. Välj **Rapportalternativ**.
14. Markera **Lägg till ett dimensionsfilter** och sedan **Affärsenhet**.
15. Skriv 001 till fältet och välj **OK**. Rapporten visar nu bara data för affärsenheten 001. Detta är en anpassad vy av rapporten och den är inte tillgänglig för andra.
16. Stäng den filtrerade rapporten. Ekonomiska rapporter kan visas i vilken valuta som helst som har lagts till i Finance and Operations.
17. Välj **Valuta** och sedan **EUR**. Rapporten visas nu i euro. Valutakoder eller valutasymboler som ingår i rapportdesignen visas nu i den använda valutan. Om ingen valutasymbol har definierats för en valuta, visas ingen valutasymbol.
18. Stäng rapporten **Huvudbokdetalj**.
19. Stäng **rapportdesignern**.

## <a name="exercise-2-add-additional-account-properties-to-a-report-design"></a>Övning 2: Lägg till ytterligare kontoegenskaper i en rapportdesign
I den här övningen ska du ändra en befintlig standardrapport. Du kommer att uppdatera både raddefinitionen för att ta med alla konton och kolumndefinitionen så att den innehåller kontoattribut. När uppdateringarna är slutförd, ska du generera den nyligen skapade rapporten och undersöka rapporten. Vi börjar med listan över ekonomiska rapporter.

1.  Gå till **Ekonomiska rapporter** under Förfrågningar och rapporter i redovisningen.
2.  Markera raden för rapporten som heter **Råbalanssammanfattning - standardinställning**.
3.  Välj **Redigera**. **Råbalanssammanfattning - standardinställning** öppnas i rapportdesignern.
4.  Välj **Arkiv**, sedan **Spara som** och namnge rapporten Detaljerad råbalans med attribut. Obs! När en ny rapport har skapats i rapportdesignern uppdateras listan med ekonomisk rapporter i Finance and Operations.
5.  Välj rapportdefinitionen, markera raddefinitionsikonen för att öppna i **Råbalans – detaljerad raddefinition**.
6.  Spara raddefinitionen som **Detaljerad råbalans med attribut**
7.  Med markören på rad 50, markera **Redigera** och sedan **Infoga rader från dimensioner**. Infoga rader från dimensioner gör att du kan välja vilka dimensioner du vill ha i din raddefinition. I den här övning ska du skapa raddefinitionen med hjälp av huvudkontot.
8.  Se till att **Huvudkonto** innehåller et-tecken och välj **OK**. Raddefinitionen innehåller nu alla huvudkonton för den juridiska personen USMF.
9.  Rulla ned till rad 11110 och ta bort rad 11110.
10. På rad 11080, markera **--- (understreckbelopp)**.
11. På rad 11140, skriv **Summan av alla konton** i kolumn B.
12. I kolumn C, markera **TOT** i listrutan.
13. Skriv **50:11080** i kolumn D.
14. **Spara** raddefinitionen. Raddefinitionen innehåller nu alla konton plus en summarad där du kan addera alla konton. Härnäst uppdaterar vi kolumndefinitionen så att den inkluderar ytterligare kontoattribut.
15. I rapportdefinitionen **Detaljerad råbalans med attribut**, välj kolumndefinitionsikonen för att öppna kolumndefinitionen **Råbalanssammanfattning - standardinställning**.
16. Spara kolumndefinitionen som **Detaljerad råbalans med attribut**. Kolumndefinitionen innehåller kolumner med ekonomiska uppgifter, en beskrivningskolumn och beräkningskolumner. Vi ska lägga till attributkolumner i kolumndefinitionen för att ge den ytterligare information om konton.
17. Följande attribut ska läggas till i kolumndefinitionen:
    -   Journalnummer
    -   Journalbeskrivning
    -   Transaktionsdatum
    -   Skapad av
    -   Senast ändrad av

18. I kolumn I, välj **ATTR** som kolumntyp. Välj sedan **Journalnummer** som attributkategori.
19. Fortsätt lägga till kolumner för de återstående attributen.
20. På raden **Rubrik 2**, lägg till beskrivningar för alla nya kolumner som har lagts till.
21. Spara kolumndefinitionen. När nu raddefinitionen och kolumndefinitionen har uppdaterats, måste vi lägga till dem i rapportdefinitionen.
22. Gå till rapportdefinitionen **Detaljerad råbalans med attribut** och välj Detaljerad råbalans med attribut både till raddefinitionen och kolumndefinitionen.
23. Ändra basåret till **2012**.
24. **Spara** rapportdefinitionen och **skapa**. När rapporten är klar och har öppnats kan du utforska rapporten som du har gjort i den första övningen. Sök nedåt i andra konton för att se hur de ytterligare attributen visas.
25. Stäng rapporten **Detaljerad råbalans med attribut**.
26. Stäng **rapportdesignern**.

## <a name="exercise-3-create-a-multidimensional-report-using-a-reporting-tree"></a>Övning 3: Skapa en flerdimensionell rapport med ett rapportträd
I den här övningen ska du ändra en befintlig standardrapport. Du ska skapa ett rapportträd och lägga till en rapportdefinition för att producera en resultaträkning för kostnadsställe/avdelning. När uppdateringen är klar, skapar du resultaträkningen för kostnadsstället/avdelningen och utforskar rapporten med hjälp av rapportträdet. Vi börjar med listan över ekonomiska rapporter.

1.  Gå till **Ekonomiska rapporter** under Förfrågningar och rapporter i redovisningen.
2.  Markera raden för rapporten som heter **Resultaträkning – standardinställning**.
3.  Välj **Redigera**. **Resultaträkning – standardinställning** öppnas i rapportdesignern.
4.  Gå till menyn **Arkiv**, peka på **Nytt** och klicka på **Rapportträddefinition**
5.  Klicka på menyn **Redigera** och på **Infoga rapportenheter från dimensioner**.
6.  Avmarkera kryssrutorna för alla dimensioner, utom **Kostnadsställe**.
7.  Klicka i fältet **Från dimension** för kostnadsställedimensionen och skriv **007**. Tryck sedan på tabbtangenten. I fältet **Till dimension**, skriv **018**.
8.  **Spara** det resulterande trädet med namnet **Kostnadsställen per avdelning**. Nu när rapportträdet har skapats, kan du ändra rapportträdet så att det innehåller tre nya värdeenheter: marknadsföring, åtgärder och butik.
9.  På menyn **Fönster**, klicka på **Kostnadsställen per avdelning**. (Om rapportträdet har stängts, markerade det i rapportträddefinitionerna i navigeringsfönstret).
10. Klicka på enheten nummer två, **Mässor** och klicka på ikonen **Infoga rapportenhet**.
11. Dubbelklicka på enhetskolumnen på den tomma raden och välj **USMF**.
12. Skriv **Marknadsföring** in kolumnerna B och C.
13. Klicka på enhet nummer fem, **Serviceåtgärder**, och högerklicka. **Välj infoga rapportenhet**.
14. Upprepa steg 11.
15. Skriv **Åtgärder** in kolumnerna B och C.
16. Klicka på enhet nummer tolv, **Outlet**, och högerklicka. Välj **Infoga rapportenhet**.
17. Upprepa steg 11.
18. Skriv **Butik** in kolumnerna B och C. Observera att marknadsföringsenheten, åtgärdsenheten och butiksenheten visas på samma nivå som de aktuella värdeenheterna. Härnäst ordnas de nya enheterna. Rapportenheter ordnas via högerklick, höjning eller sänkning eller dra och släpp.
19. Kontrollera att enhet tre, **Mässor**, aktiv och högerklicka.
20. Välj **Sänk rapportenhet**. Nu visas enheten som underordnad **Marknadsföring**.
21. Klicka på enhet fyra, **Marknadsförings****kampanj**, och högerklicka.
22. Välj **Sänk rapportenhet**.
23. Klicka på **Serviceåtgärder** i den grafiska presentationen. Peka och hålla ned vänster musknapp medan du dra enheten upp till **Åtgärder**. Släpp vänster musknapp när du vill släppa enheten i Åtgärder. Upprepa detta för **Produktion, kvalitetskontroll, logistik, anskaffning samt administration**.
24. Gör **Outlet**, **Super**, **Galleria** och **Online** underordnade till **Butik** genom att sänka dem eller dra och släppa.
25. Spara omorganisationen. Nu när vi har skapat och organiserat rapportträdet kan det läggas till i rapportdefinitionen.
26. På menyn **Fönster**, välj **Resultaträkning – standardinställning** för att öppna definitionen.
27. Klicka på listrutan **Trädtyp** och välj **Rapporträd**.
28. Klicka på trädpilen och välj **Kostnadsställen per avdelning**.
29. Ändra basåret till **2012**, **spara** ändringarna och **generera** rapporten. När rapporten har genererats och öppnats kan du granska den.
30. Välj listrutan **Rapportträd** för att visa rapportenheterna. Alternativt kan du gå ner till en rad i rapporten om du vill visa alla saldon för alla enheter i rapportträdet.
31. Stäng **Resultaträkning – standardinställning**.
32. Stäng **rapportdesignern**.

## <a name="exercise-4-create-a-consolidated-report-using-an-organization-hierarchy"></a>Övning 4: Skapa en konsoliderad rapport med hjälp av en organisationshierarki
I den här övningen ska du ändra en befintlig standardrapport. Du kan lägga till en organisationshierarki i rapportdefinitionen för att producera en konsoliderad resultaträkning och balansräkning. När uppdateringarna är klara, skapar du den konsoliderade rapporten och utforskar rapporten med hjälp av rapportträdet. Vi börjar med listan över ekonomiska rapporter.

1.  Gå till **Ekonomiska rapporter** under Förfrågningar och rapporter i redovisningen.
2.  Markera raden för rapporten **Balansräkning och resultaträkning sida vid sida – standardinställning**
3.  Välj **Redigera**. **Balansräkning och resultaträkning sida vid sida – standardinställning** öppnas i rapportdesignern.
4.  Välj **Fil** &gt; **Spara som** och namnge rapporten **Konsoliderad balansräkning och resultaträkning sida vid sida**.
5.  Ändra basåret till 2012.
6.  Klicka på trädlistrutan och välj **Organisationshierarkier**.
7.  Klicka på trädlistpilen och välj **Contoso Holdings**.
8.  Spara ändringarna och generera rapporten. Markera alla rapportenheter, om du uppmanas till det. När rapporten har genererats och öppnats kan du granska den.
9.  Välj **Rapportalternativ**.
10. Markera **Lägg till ett dimensionsfilter** och välj **Avdelning**.
11. Skriv **022** till fältet och välj **OK**.
12. Stäng den filtrerade rapporten.
13. Välj listrutan **Rapportträd** för att visa rapportenheterna. Alternativt kan du gå ner till en rad i rapporten om du vill visa alla saldon för alla enheter i rapportträdet.
14. Stäng **Konsoliderad balansräkning och resultaträkning sida vid sida**.
15. Stäng **rapportdesignern**.

## <a name="exercise-5-create-a-sidebyside-departmental-report"></a>Övning 5: Skapa en rapport för parallella avdelningar
I den här övning ska du skapa en ny rapport. Rapporten är en resultaträkning för parallella avdelningar. Du använder en befintlig raddefinition, men skapar en ny rapportdefinition och en ny kolumndefinition som använder dimensionsfilter. Vi börjar med listan över ekonomiska rapporter.

1.  Gå till **Ekonomiska rapporter** under Förfrågningar och rapporter i redovisningen.
2.  Markera **Nytt**. Rapportdesignern öppnas med en tom rapportdefinition. Din första uppgift blir att skapa kolumndefinitionen.
3.  Skapa en ny kolumndefinition genom att klicka på **Arkiv**, sedan på **Nytt** och därefter på **Kolumndefinition**.
4.  I **Kolumn A**, välj **DESC** som kolumntyp.
5.  I **Kolumn B**, välj **FD** som kolumntyp.
6.  Dubbelklicka i fältet **Dimensionsfilter**.
7.  I fönstret **Dimension**, dubbelklicka på kolumnen **Avdelning**.
8.  I avsnittet för enstaka eller intervall klickar du på **ellipsen** för fältet **Från** för att visa en lista med avdelningar.
9.  Välj avdelning **022**, **Försäljning och marknadsföring** och klicka sedan på **OK**.
10. Upprepa steg 5 till 8 för avdelningarna 23–25.
11. På raden **Huvud 2** för varje FD-kolumn, skriv följande avdelningsbeskrivningar:
    -   Kolumn B – Försäljning och marknadsföring
    -   Kolumn C – Åtgärder
    -   Kolumn D – Ekonomi
    -   Kolumn E – IT

12. Spara kolumndefinitionen som Parallella avdelningar. Eftersom du använder en befintlig raddefinition, kan rapportdefinitionen nu ändras för att kunna använda den nyligen skapade kolumndefinitionen och den befintlig raddefinitionen.
13. På menyn **Fönster**, välj **Ny rapportdefinition** för att öppna definitionen.
14. Välj **Resultaträkning – standardinställning** som raddefinitionen och **Parallella avdelningar** som kolumndefinition.
15. Spara rapportdefinitionen som **Resultaträkning för parallella avdelningar**.
16. Ändra basåret till **2012**.
17. Ändra detaljnivån till **Ekonomisk, Konto och Transaktion**
18. **Spara** ändringarna och **generera**. När rapporten har genererats och öppnats kan du granska den.

## <a name="additional-resources"></a>Ytterligare resurser
[Ekonomisk rapportering](../../financials/general-ledger/financial-reporting-getting-started.md) 
[Visa ekonomiska rapporter](../../financials/general-ledger/view-financial-reports.md) 
[Dynamics blogg för ekonomisk rapportering](http://blogs.msdn.com/b/dynamics_financial_reporting/)




