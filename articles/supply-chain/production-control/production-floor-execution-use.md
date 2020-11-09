---
title: Hur arbetare använder körningsgränssnittet för produktionsgolvet
description: I det här avsnittet beskrivs hur du använder körningsgränssnittet för produktionsgolvet från en arbetares synvinkel.
author: johanhoffmann
manager: tfehr
ms.date: 10/05/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2020-10-05
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 40c6794fdf25da44a75aba4a502a89966c0ec4d0
ms.sourcegitcommit: 9dd2d38e76d4d93171315ec319e6ce7d51d4e6c7
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/15/2020
ms.locfileid: "4012509"
---
# <a name="how-workers-use-the-production-floor-execution-interface"></a>Hur arbetare använder körningsgränssnittet för produktionsgolvet

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Körningsgränssnittet för produktionsgolvet är optimerat för beröringsinteraktion. Dess design ger visuell kontrast som uppfyller tillgänglighetskraven för verkstadsmiljöer. Den erbjuder alla funktioner som jobbkortsenhet. Det gör dock också att flera jobb startas parallellt från en jobblista. (Den här funktionen kallas även för *buntning av jobb*.) Från en jobblista kan arbetare dessutom öppna en guide som har skapats i Microsoft Dynamics 365-guiden. På så sätt kan de visa visuella instruktioner för en HoloLens.

## <a name="sign-in-to-the-production-floor-execution-interface-as-a-worker"></a>Logga in på körningsgränssnittet för produktionsgolvet som en arbetare

Innan arbetarna kan börja använda enheten måste han eller hon förbereda den och öppna rätt sida i Dynamics 365 Supply Chain Management. Mer information om hur du ställer in en enhet finns i [Konfigurera en enhet att köra körningsgränssnittet för produktionsgolvet](production-floor-execution-setup.md).

När enheten har förberett visas inloggningssidan på den. På den här sidan visas information om status för jobb för den lokala arbetsgruppen. Denna information uppdateras regelbundet. På sidan använder arbetarna sin ID-bricka för att logga in. Även om arbetarna inte behöver ha ett användarkonto för Supply Chain Management, måste de ha ett konto för *tidsregistrerad arbetare* som de kan använda när de loggar in.

![Inloggningssida för körningsgränssnittet för produktionsgolvet](media/pfei-sign-in-page.png "Inloggningssida för körningsgränssnittet för produktionsgolvet")

I de återstående avsnitten i det här ämnet beskrivs hur arbetare interagerar med gränssnittet.

## <a name="all-jobs-tab"></a>Fliken alla jobb

Fliken **Alla jobb** tillhandahåller en jobblista som visar alla produktionsjobb som har statusen *inte startad* , *stoppad* eller *startad*.

![Fliken alla jobb](media/pfei-all-jobs-tab.png "Fliken alla jobb")

Det finns följande kolumner i jobblistan. (Siffrorna motsvarar siffrorna i föregående illustration.)

1. **Urvalskolumn** – kolumnen längst till vänster använder en bockmarkering för att visa jobb som har valts av arbetaren. Arbetare kan välja flera jobb i listan samtidigt. Om du vill markera alla jobb i listan markerar du kryssrutan i kolumnrubriken. När ett enstaka jobb väljs visas information om jobbet i den nedre delen av sidan.
1. **Kolumn för jobbstatus** – i den här kolumnen används symboler för att visa status för varje jobb. Jobb som saknar symbol i den här kolumnen har statusen *inte startad*. En grön triangel anger jobb som har statusen *startat*. Två gula lodräta linjer indikerar jobb som har statusen *stoppad*.
1. **Kolumnen hög prioritet** – i den här kolumnen används utropstecken för att ange jobb med hög prioritet.
1. **Order** – i den här kolumnen visas produktionsordernumret för ett jobb.
1. **Beskrivning** – i den här kolumnen visas en beskrivning av den operation som ett jobb ingår i.
1. **Begärd** – den här kolumnen visar den kvantitet som ett jobb har planerats att producera.
1. **Startad** – i den här kolumnen visas den kvantitet som redan har startats för ett jobb.
1. **Slutförd** – i den här kolumnen visas den kvantitet som redan har slutförts för ett jobb.
1. **Kasserad** – i den här kolumnen visas den kvantitet som redan har kasserats för ett jobb.
1. **Resterande** – i den här kolumnen visas den kvantitet som återstår att färdigställa för ett jobb.

## <a name="active-jobs-tab"></a>Fliken aktiva jobb

![Fliken aktiva jobb](media/pfei-active-jobs-tab.png "Fliken aktiva jobb")

Jobblistan på fliken **Aktiva jobb** har följande kolumner:

- **Urvalskolumn** – kolumnen längst till vänster använder en bockmarkering för att visa jobb som har valts av arbetaren. Arbetare kan välja flera jobb i listan samtidigt. Om du vill markera alla jobb i listan markerar du kryssrutan i kolumnrubriken. När ett enstaka jobb väljs visas information om jobbet i den nedre delen av sidan.
- **Order** – i den här kolumnen visas produktionsordernumret för ett jobb.
- **Beskrivning** – i den här kolumnen visas en beskrivning av den operation som ett jobb ingår i.
- **Begärd** – den här kolumnen visar den kvantitet som ett jobb har planerats att producera.
- **Startad** – i den här kolumnen visas den kvantitet som redan har startats för ett jobb.
- **Slutförd** – i den här kolumnen visas den kvantitet som redan har slutförts för ett jobb.
- **Kasserad** – i den här kolumnen visas den kvantitet som redan har kasserats för ett jobb.
- **Resterande** – i den här kolumnen visas den kvantitet som återstår att färdigställa för ett jobb.

## <a name="starting-and-completing-production-jobs"></a>Starta och slutföra produktionsjobb

Arbetare startar ett produktionsjobb genom att välja ett jobb på fliken **Alla jobb** och sedan välja **Starta jobb** för att öppna dialogrutan **Starta jobb**.

![Dialogrutan Startjobb](media/pfei-start-job-dialog.png "Dialogrutan Startjobb")

Arbetare använder dialogrutan **Startjobb** för att bekräfta produktionskvantiteten och sedan starta jobbet. Arbetare kan justera kvantiteten genom att markera fältet **Kvantitet** och sedan använda det numeriska tangentbordet som visas. Arbetstagarna väljer sedan **Start** för att börja arbeta med jobbet. Dialogrutan **Starta jobb** stängs och jobbet läggs till på fliken **Aktiva jobb**.

Arbetare kan starta ett jobb som har status. När en arbetare startar ett jobb med statusen *Inte startad* visar **Kvantitet** i dialogrutan **Starta jobb** inledningsvis hela kvantiteten. När en arbetare startar ett jobb med statusen *Startad* eller *Stoppad* visar fältet **Kvantitet** inledningsvis kvarstående kvantitet.

## <a name="reporting-good-quantities"></a>Rapportera godkända kvantiteter

När en arbetare slutför eller delvis slutför ett jobb kan de rapportera bra kvantiteter som producerats genom att välja ett jobb på fliken **Aktiva jobb** och flik **Rapportera progress**. Sedan i dialogrutan **Rapportera framsteg** anger arbetaren den goda kvantiteten med hjälp av det numeriska tangentbordet. Kvantiteten är tom som standard. När en kvantitet har angivits kan han eller hon uppdatera status för jobbet till *pågår* , *stoppad* eller *slutfört*.

![Dialogrutan rapportera framsteg](media/pfei-report-progress-dialog.png "Dialogrutan rapportera framsteg")

## <a name="reporting-scrap"></a>Rapportera kassation

När en arbetare slutför eller delvis slutför ett jobb kan de rapportera kassation genom att välja ett jobb på **Aktiva jobb** och flik **Rapportera kassation**. Sedan i dialogrutan **Rapportera kassation** anger arbetaren kassationskvantiteten med hjälp av det numeriska tangentbordet. Arbetaren väljer också en orsak ( *ingen* , *maskin* , *operatör* eller *material* ).

![Dialogrutan rapportera kassation](media/pfei-report-scrap-dialog.png "Dialogrutan rapportera kassation")

## <a name="completing-a-job-and-starting-a-new-job"></a>Slutföra ett jobb och starta ett nytt jobb

Vanligtvis slutför arbetarna ett jobb genom att välja ett eller flera aktuella jobb på fliken **Aktiva jobb** och sedan välja **Rapportera framsteg**. Därefter anger de kvantiteten som producerades (den godkända kvantiteten) och ställer in statusen för att *slutföra*. Om fler än ett jobb har valts använder en arbetare sedan knapparna **Föregående** och **Nästa** för att förflytta sig mellan dem. Om du vill starta ett nytt jobb väljer arbetaren det på fliken **Alla jobb** och väljer sedan **Starta jobb**.

En arbetare kan också starta ett nytt jobb medan deras tidigare jobb fortfarande är öppet. Återigen väljer arbetaren det nya jobbet på fliken **Alla jobb** och väljer sedan **Starta jobb**. I det här fallet informerar dialogrutan **Starta jobb** arbetaren att de för närvarande arbetar med ett jobb och att de därför måste antingen sluta eller slutföra det jobbet innan de börjar det nya jobbet.

## <a name="working-on-multiple-jobs-in-parallel"></a>Arbeta med flera jobb parallellt

En arbetare kan arbeta med flera jobb samtidigt (det vill säga parallellt). I det här fallet kallas samlingen av jobb som arbetaren arbetar på en *jobbunt*. Arbetaren kan lägga till nya jobb i bunten eller fylla i ett eller flera jobb i bunten. I följande två scenarier visas hur en arbetare kan arbeta med jobb parallellt.

### <a name="scenario-1-a-worker-who-has-no-active-jobs-wants-to-start-two-jobs-and-work-on-them-in-parallel"></a>Scenario 1: en arbetare som inte har aktiva jobb vill starta två jobb och arbeta med dem parallellt

Arbetaren väljer de två jobben på fliken **Alla jobb** och väljer sedan **Starta jobb**. Dialogrutan **Starta jobb** visar båda valda jobb och arbetaren kan justera kvantiteten så att den startar på varje jobb. Arbetaren bekräftar sedan dialogrutan och kan starta båda jobben.

### <a name="scenario-2-a-worker-who-has-two-active-jobs-that-are-in-progress-wants-to-start-a-third-job-and-work-on-it-in-parallel-with-the-other-two"></a>Scenario 2: en arbetare som har två aktiva jobb som pågår vill starta ett tredje jobb parallellt med de andra två

Arbetaren väljer det tredje jobbet på fliken **Alla jobb** och väljer sedan **Bunt**. I dialogrutan **Bunt** kan arbetaren justera kvantiteten så att den startar. Arbetaren bekräftar sedan dialogrutan genom att välja **bunt**.

## <a name="working-on-indirect-activities"></a>Arbeta på indirekta aktiviteter

Indirekta aktiviteter är aktiviteter som inte är direkt relaterade till en produktionsorder. Indirekta aktiviteter kan anges på ett flexibelt sätt, enligt beskrivningen i [ställa in indirekta aktiviteter för tid och närvaro](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-indirect-activities-for-time-and-attendance).

Till exempel Shannon, en butiksarbetare i Contoso, vill delta i ett företagsmöte och möten betraktas som en indirekt aktivitet. Ett av följande två scenarier gäller:

- **Shannon arbetar med ett eller flera aktiva jobb.** Shannon väljer **aktivitet** , identifierar aktiviteten (mötet) och bekräftar valet. Ett meddelande som visas med information om att hon har jobb som pågår. Med hjälp av meddelandet kan Shannon välja att slutföra eller stoppa jobb som hon arbetar med innan hon går till mötet.
- **Shannon har inga aktiva jobb.** Shannon väljer **aktivitet** , identifierar aktiviteten (mötet) och bekräftar valet. Hon är nu registrerad som på mötet.

När Shannon bekräftar sina val i båda scenarierna, går hon antingen till inloggningssidan eller en sida som väntar på att hon ska bekräfta att hon har returnerat från sin indirekta aktivitet. Vilken sida som visas beror på konfigurationen av körningsgränssnittet för produktionsgolvet. (Mer information finns i [Konfigurera gränssnittet för körning av produktionsstyrning](production-floor-execution-configure.md).)

## <a name="working-on-breaks"></a>Arbeta med raster

Arbetare kan registrera raster. Raster kan definieras flexibelt, vilket beskrivs i [lön baserat på registreringar](pay-based-on-registrations.md).

En arbetare registrerar en rast genom att välja **rast** och sedan välja det kort som representerar rasttypen (t.ex. lunch). När personen har bekräftat urvalet visar enheten antingen inloggningssidan eller en sida som väntar på att personen ska bekräfta att de har returnerats från rasten. Vilken sida som visas beror på konfigurationen av körningsgränssnittet för produktionsgolvet. (Mer information finns i [Konfigurera gränssnittet för körning av produktionsstyrning](production-floor-execution-configure.md).)

## <a name="opening-instructions"></a>Öppnar instruktioner

Arbetare kan öppna ett dokument som är kopplat till ett jobb genom att välja **instruktioner**. Knappen **instruktioner** är endast tillgänglig om ett dokument är kopplat till jobbet i huvuddata. Till exempel kan ett dokument som är kopplat till en produkt på sidan **frisläppta produkter** i Supply Chain Management kommer att vara tillgängligt för arbetare som ska öppnas i gränssnittet för arbetsstyrningskörning.

## <a name="opening-mixed-reality-guides-for-hololens"></a>Öppnade guider för mixad verklighet för HoloLens

[Dynamics 365 Guides](https://dynamics.microsoft.com/mixed-reality/guides/) kan hjälpa arbetarna att erbjuda praktisk utbildning med hjälp av mixad verklighet. Du kan definiera standardiserade processer med steg-för-steg-instruktioner som vägleder medarbetare till de verktyg och delar de behöver och visa hur de kan använda verktygen i verkliga arbetssituationer. Här finns en översikt av processen.

1. Varje gång en arbetare öppnar en jobblista i gränssnittet för arbetsstyrningskörningen, hittar gränssnittet alla relevanta guider för de jobb som visas.
1. Arbetaren väljer själv **guider** som visar listan över guider.
1. Arbetaren väljer en relevant guide i listan.
1. I gränssnittet för arbetsstyrningskörning visas en QR-kod för den valda guiden.
1. Arbetaren ger en HoloLens och en överblick över QR-koden för att starta guiden.
1. Arbetaren går igenom guiden för att lära sig uppgiften.

Mer information om hur du skapar, tilldelar och använder guider för HoloLens finns i [Ange guider för mixad verklighet för arbetare i produktion](instruction-guides-in-production-overview.md).
