---
title: Redovisa uppskjuten intäkt
description: I det här avsnittet finns information om hur du redovisar intäkter med hjälp av intäktsredovisningsfunktionen.
author: kweekley
manager: aolson
ms.date: 08/24/2018
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: ace1d00ec25a57b26b1858369c32d9134a380977
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4459959"
---
# <a name="recognize-deferred-revenue"></a>Redovisa uppskjuten intäkt

[!include [banner](../includes/banner.md)]

> [!NOTE]
> Intäktsredovisningsfunktionen kan inte slås på via funktionshantering. För närvarande måste du använda konfigurationsnycklar för att slå på den.

I det här avsnittet beskrivs hur intäkter redovisas i intäktsplanen. När en faktura har bokförts för en försäljningsorder skapas en intäktsredovisningsplan för varje försäljningsorderrad som har en intäktsplan. Intäktsplaner på en rad används för att bestämma om radens intäkt ska skjutas upp eller inte.

## <a name="view-revenue-recognition-schedule-details"></a>Visa detaljer i intäktsredovisningsplanen

Det finns två sätt att visa detaljer i intäktsredovisningsplanen.

- Du kan öppna intäktsredovisningsplanen direkt från en fakturerad försäljningsorder. I det här fallet filtreras informationen i intäktsplanen så att bara information om den valda försäljningsordern visas. Den här metoden är användbar när du validerar detaljer i planen för en försäljningsorder.
- Du kan öppna intäktsredovisningsplanen från sidan **Intäktsredovisning \> Periodiska uppgifter**. Den här metoden används ofta när intäkten redovisas i slutet av en period. När sidan öppnas för första gången visas ingen information. Du använder filtren ovanför rutnätet för att definiera kriterier för den planinformation som ska visas. Du kan filtrera efter fakturadatum genom att ange ett datumintervall eller efter försäljningsorder, kund, projekt-ID eller tillstånd.

[![Sidan Intäktsplaner](./media/revenue-recognition-rev-revenue-schedules.png)](./media/revenue-recognition-rev-revenue-schedules.png)

På snabbfliken **Ekonomisk dimension** under rutnätet visas försäljningsorderradens ekonomiska dimensioner. Dessa dimensioner övervägdes under bokföringen av uppskjuten intäkt. De beaktas också när intäkten redovisas. Vilka dimensionsvärden som används beror på den kontostruktur som tilldelats huvudkontona för intäkt och uppskjuten intäkt.

## <a name="recognize-revenue"></a>Redovisa intäkt

Du kan redovisa intäkter genom att köra processen **Skapa journal** från sidan **Redovisa intäkt**. Du kan öppna den här sidan antingen från försäljningsordern eller **Periodiska uppgifter**. Om processen körs från försäljningsordern redovisas bara intäkter för den valda försäljningsordern. Vanligtvis körs processen från **Periodiska uppgifter**, vilket innebär att intäkterna för alla bokförda fakturor för försäljningsorder redovisas.

Du definierar kriterier för hur intäkter väljs och bokförs genom att välja **Skapa journal**. Då öppnas dialogrutan **Skapa journal**.

[![Parameteralternativ för Skapa journal](./media/revenue-recognition-create-journal.png)](./media/revenue-recognition-create-journal.png)

I dialog rutan använder du alternativen i fältgruppen **Bearbetningsdatum** för att definiera vilket bokföringsdatum som ska användas när intäkten bokförs. Om du väljer **Valt datum** kan du ange ett bokföringsdatum i fältet **Transaktionsdatum**. Om du väljer **Datum för intäktsplan** används inte transaktionsdatumet. I stället används värdet i fältet **Redovisningsdatum** på respektive rad i planen som bokföringsdatum.

Därefter anger du från-datumet för intäktsredovisningen i fältet **Från och med (datum)**. Alla rader i planen där redovisningsdatumet infaller på eller före från-datumet redovisas, förutsatt att de inte är spärrade.

När du har definierat datumen väljer du **OK** i dialogrutan så att journalen skapas. Du får ett informationsmeddelande som anger antalet transaktioner som har skapats och den journal där de skapades. Journalen bokförs inte automatiskt. Därför har den som ansvarar för intäktsredovisningen tid att validera vilka rader i planen som ska redovisas.

När processen har körts markeras de rader i planen som överförts till journalen som **Bearbetade**. Flaggan **Bearbetade** anger att raderna har överförts till journalen, men du kan välja att bokföra dem eller inte bokföra dem. När journalen för intäktsredovisning har bokförts finns flaggan **Bearbetade** fortfarande kvar. Om intäktsredovisningsjournalen tas bort, eller om en rad tas bort, tas flaggan **Bearbetade** bort. På så sätt kan raden redovisas när processen **Skapa journal** körs igen.

[![Sidan Intäktsredovisningsplan](./media/revenue-recognition-rev-recog-schedule-02.png)](./media/revenue-recognition-rev-recog-schedule-02.png)

Gå till sidan **Intäktsredovisningsjournal** (**Intäktsredovisning \> Journalposter \> Intäktsredovisningsjournal**) och öppna **Rader** om du vill visa mer information om vad som redovisas. En separat transaktion skapas alltid för varje rad i planen som redovisas, även om alla rader bokförs på samma datum på samma huvudbokskonton.

[![Sidan Bokföringsorder](./media/revenue-recognition-journal-voucher.png)](./media/revenue-recognition-journal-voucher.png)

I kolumnen **Konto** visas huvudbokskontot för uppskjutna intäkter. Det här huvudbokskontot kan inte redigeras. Denna begränsning garanterar att avdraget görs från rätt huvudbokskonto för uppskjutna intäkter. Det här huvudbokskontot valideras inte mot kontostrukturen eftersom det kan ha ändrats sedan den senaste bokföringen utfördes på huvudbokskontot för uppskjutna intäkter.

I kolumnen **Motkonto** visas huvudbokskontot för intäkter. Som standard hämtas huvudbokskontot för intäkter från lagerbokföringsprofilerna, och de ekonomiska dimensionerna hämtas från försäljningsorderraden. Det här huvudbokskontot valideras mot den aktuella kontostrukturen. Det kan dock redigeras om kontostrukturen har ändrats och ytterligare ekonomiska dimensioner behövs.

Standardbeloppet hämtas från motsvarande rad i planen och kan inte ändras.

Om försäljningsordern är en försäljningsorder med flera valutor, får valutakursen som standard samma värde som valutakursen på fakturan. Detta garanterar att beloppen i redovisningsvalutan och rapporteringsvalutan dras av helt och hållet. Om beloppen avrundas kan valutakursen för den sista raden i planen skilja sig något från kursen på fakturan.

När intäktsredovisningsjournalen har bokförts registreras verifikationen i planen. Om det finns fler än en verifikation för samma rad i planen visas en asterisk (\*) på raden. Välj **Verifikationstransaktioner** om du vill visa verifikationer som har bokförts för raden.

## <a name="modify-the-revenue-recognition-schedule-details"></a>Ändra detaljerna i intäktsredovisningsplanen

De flesta data i intäktsplanen kan inte redigeras. Det går inte att lägga till nya rader i planen och det går inte att ta bort befintliga rader. Du måste underhålla intäktsplansuppgifterna för varje försäljningsorderrad, så att organisationen över tid redovisar samma uppskjutna belopp.

### <a name="edit-schedule-lines"></a>Redigera rader i intäktsplanen

Det går att utföra vissa ändringar på raderna i planen. Följande fält på raderna kan ändras:

- **Spärrad** – Den här flaggan kan ställas in eller rensas innan raden bearbetas. Du tar bort flaggan genom att markera raden och välja **Ta bort spärr**. Det går inte att redovisa intäkter på rader som är spärrade. Rader kan spärras automatiskt om intäktsplanen har ställts in för automatiska spärrar.

    [![Intäktsplaner – Redigera rader i intäktsplanen](./media/revenue-recognition-rev-revenue-schedules.png)](./media/revenue-recognition-rev-revenue-schedules.png)

- **Redovisningsdatum** – Du kan ändra redovisningsdatumet innan raden bearbetas. När processen som skapar journalen för redovisning av intäkt körs, registreras ett datum i fältet **Redovisa intäkter från och med (datum)**. Detta datum jämförs med datumet i fältet **Redovisningsdatum** för att avgöra vilka rader som ska redovisas.
- **Belopp att frisläppa** – Det belopp som kommer att frisläppas kan ändras innan raden bearbetas. Du kan minska intäktsbeloppet som ska redovisas, men inte öka det. I det här fältet kan en organisation redovisa en del av intäkterna på redovisningsdatumet. Om beloppet ändras anger beloppet i fältet **Resterande belopp** hur mycket intäkt som finns kvar att redovisa.
- **Kvantitet att frisläppa** – Om intäktsplaner har ställts in för en förekomst eller en månad anger fältet **Kvantitet att frisläppa** kvantiteten på försäljningsorderraden. Det här fältet kan också redigeras, och innebär ett annat sätt att redovisa en del av intäkten. Om kvantiteten på raden till exempel är 5, kan du åsidosätta kvantiteten så att den är mindre än 5. Beloppet i fältet **Belopp att frisläppa** uppdateras proportionellt.

### <a name="update-contract-terms"></a>Uppdatera kontraktsvillkor

Intäktsplansdetaljerna skapas utifrån den intäktsplan som tilldelas försäljningsorderraden när fakturan bokförs. Om intäktsplanen på försäljningsorderraden är felaktig, kan den inte ändras på försäljningsordern när försäljningsordern väl har fakturerats. I stället måste du använda knappen **Uppdatera kontraktsvillkor** om du vill ändra intäktsplanen. Intäktsplaner kan ändras antingen före eller efter att intäkten redovisas.

Om du vill ändra planen markerar du en rad i planen för den artikel du ändrar. I bilden nedan markeras raden för artikel S0008 som bokförts med hjälp av en intäktsplan på 12 månader. När du väljer **Uppdatera kontraktsvillkor** visas start- och slutdatumet för kontraktet i en dialogruta samt intäktsplanen.

[![Start- och slutdatum för kontrakt](./media/revenue-recognition-rev-revenue-schedule-update-cntrct-dates-schedule.png)](./media/revenue-recognition-rev-revenue-schedule-update-cntrct-dates-schedule.png)

Ändra kontraktets start- och slutdatum så att de återspeglar rätt datumintervall. När du ändrar datumintervallet måste värdet i fältet **Antal förekomster** matcha en intäktsplan som har definierats i systemet. Eftersom kontraktet i det här exemplet har ändrats till ett 24-månaders kontrakt, måste du skapa en intäktsplan på 24 månader. Eftersom det finns en intäktsplan på 24 månader anges den som standard och kontraktet kan ändras. Om det inte finns någon intäktsplan som har motsvarande antal förekomster, kan kontraktet inte ändras. När du har uppdaterat kontraktsvillkoren och intäktsplanen väljer du **OK** i dialogrutan så att ändringarna sparas.

[![Uppdaterat datumintervall för kontrakt](./media/revenue-recognition-rev-revenue-schedule-update-cntrct-dates-schedule-02.png)](./media/revenue-recognition-rev-revenue-schedule-update-cntrct-dates-schedule-02.png)

Ändringarna i kontraktet påverkar intäktsplansdetaljerna på följande sätt:

- Om ingen intäkt har redovisats för produkten, tas alla tidigare plandetaljer bort och ersätts med de nya intäktsplansdetaljerna. Artikel S0008 hade till exempel ursprungligen 12 rader i plandetaljerna. Dessa 12 rader tas bort och ersätts med 24 rader, vilket baseras på den nya intäktsplanen.
- Om intäkt har redovisats för produkten, redovisades en del intäkter felaktigt eftersom redovisningen baseras på fel intäktsplan. Dessa rader måste återföras och redovisas på nytt, baserat på den nya planen. I det här scenariot skapas nya intäktsplansrader med negativa belopp på det ursprungliga redovisningsdatumet. Sedan skapas nya rader som redovisar belopp baserat på den nya intäktsplanen. Exempel: Den 8 augusti 2019 redovisade du intäkter på 10,53 USD. Den 8 september 2019 redovisade du intäkter på 13,16 USD. Därför skapas två nya rader på samma datum. En rad på -10,53 USD och en annan på -13,16 USD. 24 nya rader skapas sedan och den totala uppskjutna intäkten på 160,61 USD fördelas mellan dem. Du kan bokföra återföringsraderna genom att köra processen **Skapa journal**.

[![Intäktsredovisningsplan](./media/revenue-recognition-rev-recog-schedule-03.png)](./media/revenue-recognition-rev-recog-schedule-03.png)
