---
title: Exempel på scenarier med rullande inventering
description: I denna artikel finns en samling scenarier där du kan undersöka funktionerna för rullande inventering i Microsoft Dynamics 365 Supply Chain Management.
author: GalynaFedorova
ms.date: 06/08/2021
ms.topic: article
ms.search.form: WHSCycleCountPlan, WHSCycleCountPlanListPage, WHSCycleCountThreshold, WHSWorkTableListPage, SalesShipmentDeviation, WHSRFMenuItemCycleCount, WHSWorkLineCycleCount
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2021-06-08
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 91a18b6deade6d67fce6b90308671910a4196104
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/23/2022
ms.locfileid: "9335748"
---
# <a name="cycle-counting-example-scenarios"></a>Exempel på scenarier med rullande inventering

[!include [banner](../includes/banner.md)]

I denna artikel finns en samling scenarier där du kan undersöka funktionerna för rullande inventering i Microsoft Dynamics 365 Supply Chain Management. Den beskriver först kraven för din befintliga Supply Chain Management-miljö. Det förklarar sedan hur du konfigurerar rullande inventering och beskriver alla faserna för rullande inventering. När du är klar bör du ha god förståelse för rullande inventering, inklusive guidad rullande inventering, rullande inventering av typen blind, rullande inventering av typen spot, tröskelvärden för rullande inventering och planer för rullande inventering.

## <a name="prerequisites"></a>Förutsättningar

### <a name="make-demo-data-available"></a>Gör demodata tillgängliga

Varje scenario i denna artikel refererar till värden och poster som ingår i den standarddemodata som finns för Supply Chain Management. Om du vill använda de värden som finns här när du går igenom scenarierna måste du arbeta i en miljö där demonstrationsdata har installerats samt konfigurera den juridiska personen (företag) på **USMF** innan du börjar.

### <a name="turn-on-support-for-the-warehouse-management-mobile-app"></a>Aktivera support för Warehouse Management-mobilappen

För att använda Warehouse Management Mobile-appen måste funktionen *Användarinställningar, ikoner och stegrubriker för den nya distributionslagerappen* måste vara aktiverade för systemet. Från och med version 10.0.25 av Supply Chain Management är denna funktion obligatorisk och kan inte inaktiveras. Om du kör en version äldre än 10.0.25 kan administratörer aktivera eller inaktivera denna funktion genom att söka efter funktionen *Användarinställningar, ikoner och stegrubriker för den nya distributionslagerappen* i arbetsytan [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

### <a name="prepare-demo-data-for-the-scenarios"></a><a name= "prepare-demo-data"></a>Förbered demodata för scenarierna

Följ dessa steg för att bekräfta att alla de demodata som krävs för scenarierna är tillgängliga i USMF-företaget i ditt system. Skapa poster eller värden som saknas.

1. Gå till **Warehouse management \> Inställningar \> Arbetare**.
1. Välj i listfönstret **Julia Funderburk**.
1. På snabbflikarna **Användare** välj raden som har följande värden. Om det inte finns någon befintlig rad med de här värdena skapar du den.

    - **Användar-ID:** *61*
    - **Användarnamn:** *WH61*
    - **Standardlagerställe:** *61*
    - **Menynamn:** *huvud*

1. På snabbflikarna **Arbete**, ange följande värde för användare *61* ställts in:

    - **Är ansvarig för rullande inventering:** *Nej*
    - **Gräns för högsta procentandel:** *0*
    - **Gräns för högsta kvantitet:** *0*
    - **Gräns för högsta värde:** *0*

1. Gå till **Warehouse management \> Inställningar \> Arbete \> Arbetspooler**.
1. Arbetspooler används för att skilja lagerställearbetet baserat på typ av arbete (i det här fallet arbete med rullande inventering). Kontrollera att det finns en post med följande inställningar:

    - **Arbetspools-ID:** *CycleCount*
    - **Beskrivning:** *rullande inventering*

1. Gå till **Warehouse management \> Inställningar \> Mobil enhet \> Menyalternativ på mobil enhet**.
1. Markera posten som får namnet *rullande inventering* i listfönstret. Om det inte finns någon befintlig post med det här namnet skapar du den. Bekräfta eller ställ in följande värden för posten:

    - **Menyartikelnamn:** *rullande inventering*
    - **Titel:** *Guidad rullande inventering*
    - **Läge:** *arbete*
    - **Använd befintligt arbete:** *Ja*
    - **Styrt av:** *Systemstyrd* (Det här värdet visar att Supply Chain Management kommer att tilldela en arbets-ID för rullande inventering till arbetaren.)
    - **Visa lagerstatus:** *Ja*

1. Välj **rullande inventering** i åtgärdsfönstret.
1. I dialogrutan **rullande inventering för mobil enhet**, bekräfta eller ställ in följande värden:

    - **Visa artikelnummer:** *Ja*
    - **Visa ID-nummer:** *Ja*
    - **Antal försök:** *1*

1. Välj **OK** för att stänga dialogrutan.
1. Markera posten som får namnet *rullande inventering av typen* i listfönstret. Om det inte finns någon befintlig post med det här namnet skapar du den. Bekräfta eller ställ in följande värden för posten:

    - **Menyartikelnamn:** *rullande inventering av typen blind*
    - **Titel:** *rullande inventering av typen blind*
    - **Läge:** *arbete*
    - **Använd befintligt arbete:** *Ja*
    - **Dirigerad av:** *Gruppering av rullande inventering* (Detta värde indikerar att arbetaren kan gruppera ID:n för pågående rullande inventeringar som är specifika för en plats, zon eller arbetspool.)

1. Välj **rullande inventering** i åtgärdsfönstret.
1. I dialogrutan **rullande inventering för mobil enhet**, bekräfta eller ställ in följande värden:

    - **Visa artikelnummer:** *Nej*
    - **Visa ID-nummer:** *Nej*
    - **Antal försök:** *0*

1. Välj **OK** för att stänga dialogrutan.
1. Markera posten som får namnet *Punktinventering* i listfönstret. Om det inte finns någon befintlig post med det här namnet skapar du den. Bekräfta eller ställ in följande värden för posten:

    - **Menyartikelnamn:** *Punktinventering*
    - **Rubrik:** *Punktinventering*
    - **Läge:** *arbete*
    - **Använd befintligt arbete:** *Nej*
    - **Arbetsskapandeprocess:** *Rullande inventering av typen Spot* (Detta värde indikerar att arbetaren kan räkna artiklar på ett lagerställe när som helst utan att skapa en arbetsuppgift för rullande inventering. Om arbetaren vill utföra rullande inventering av typen spot för en plats, anger hen plats-ID.)

1. Gå till **Warehouse management \> Inställningar \> Mobil enhet \> Meny på mobil enhet**.
1. Markera posten som får namnet *Lager* i listfönstret. Om det inte finns någon befintlig post med det här namnet skapar du den. Bekräfta att följande menyalternativ för rullande inventering visas i kolumnen **Menystruktur**:

    - Rullande inventering
    - Rullande inventering av typen blind
    - Punktinventering

1. Gå till **Warehouse management \> Inställningar \> Parametrar för Warehouse management**.
1. Ange följande värden på fliken **rullande inventering**:

    - **Standardjusteringstyp för rullande inventering:** *rullande inventering* (Det här fältet anger den loggtyp som bokförs när rullande inventering är klar.)
    - **Standardklass-ID för rullande inventering** *CCount* (I det här fältet anges den arbetsklass som används för rullande inventering.)
    - **Standard för arbetsprioritet rullande inventering:** *50* (Det här fältet anger den prioritet som rullande inventering har i förhållande till andra typer av arbete i lagret. Genom att ange ett lägre nummer än numret som anges för andra typer av arbete, ger du arbetet med rullande inventering en högre prioritet.

1. Gå till **Warehouse management \> Inställningar \> Lager \> Justeringstyper**.
1. På sidan **Justeringstyper** kan du skapa koder för olika in- och utjusteringar som kan inträffa. Bekräfta att det finns en post med följande inställningar:

    - **Lagerjusteringstyp:** *Rullande inventering*
    - **Beskrivning:** *Rullande inventering*
    - **Namn:** *ICnt*

1. Gå till **Warehouse management \> Inställningar \> Inställningar för distributionslager \> Lagerställen**.
1. I listrutan välj lagerställe *61*. Om det inte finns någon befintlig post med det här namnet skapar du den.
1. PÅ snabbfliken **Lagerställe**, ange följande värden:

    - **Använda lagerstyrningsprocessen:** *Ja* (Detta värde aktiverar lagerstället för lagerstyrningsprocesser (WMS).)
    - **Tillåt flytt av ID-nummer under rullande inventering:** *Ja* (Detta värde gör det möjligt för arbetstagare att flytta ID-nummer under rullande inventering.)

## <a name="scenario-1-guided-cycle-counting"></a>Scenario 1: Guidad rullande inventering

Innan guidad rullande inventering kan göras måste du skapa arbete. Det här arbetet vägleder den tilldelade personen genom lagerstället, från plats till plats, för att slutföra de inventeringar som har ställts in i arbetet.

### <a name="create-cycle-counting-work-for-scenario-1"></a>Skapa rullande inventeringsarbete för scenario 1

Följ dessa steg för att skapa arbete för rullande inventering för artikelplats *01A02R2S2B* (BULK-06) i lagerställe *61*.

1. Gå till **Warehouse management \> Rullande inventering \> Rullande inventeringsarbete efter plats**.
1. I dialogrutan **Skapa rullande inventeringsarbete efter plats** ange fältet **Arbetspool-ID** till *CycleCount*.
1. På snabbfliken **Poster att inkludera**, välj **Filter**.
1. I frågeredigerarens dialogruta på fliken **Intervall** följ dessa steg:

    - För raden där fältet **Fält** ange till *Lagerställe*, ange **Kriterium** till *61*.
    - För raden där fältet **Fält** ange till *Plats*, ange **Kriterium** till *01A02R2S2B*.

1. Stäng dialogrutan för frågeredigeraren genom att välja **OK**.
1. Välj **OK** om du vill stänga dialogrutan **Skapa rullande inventeringsarbete efter plats**.

    När arbetet med att skapa processen är klar visas ett meddelande i Åtgärdscentret.

1. Gå till **Warehouse management \> Arbete \> Arbetsdetaljer**.
1. Hitta det nya arbetet genom att ange ett filter i kolumnen **Arbetspool-ID** för att hitta poster som har värdet *CycleCount*.

### <a name="do-cycle-counting-work-for-scenario-1"></a>Gör rullande inventeringsarbete för scenario 1

När du har skapat cykelräkningsarbetet gör du jobbet genom att räkna artiklar på en lagerplats och sedan ange resultatet i Supply Chain Management med hjälp av en mobil enhet. Följ dessa steg när du vill göra arbete för rullande inventering i mobilappen Warehouse Management.

1. Logga in på mobilappen Warehouse Management som arbetsanvändaren som du konfigurerat i [Förbereda demodata för scenarierna](#prepare-demo-data) som beskrivs tidigare i denna artikel. För exemplet i denna artikel heter användaren *Julia Funderburk* och har konfigurerats för lagerställe *61*. (USMF-demodata bör låta dig logga in som den här arbetsanvändaren genom att ange *61* som användar-ID och *1* som lösenord.)
1. I huvudmenyn, välj **lager**.
1. I menyn **lager**, välj **Guidad rullande inventering**.
1. Markera fältet **Kvt** ange *9* med hjälp av det numeriska tangentbordet och sedan **OK** (bockmarkeringsknappen).
1. Systemet förväntade sig att du skulle ange en räkning på 10 enheter för artikeln, platsen och licensinnehavaren. Du uppmanas därför att stämma av. Markera fältet **Kvt** ange *9* med hjälp av det numeriska tangentbordet och sedan **OK** (bockmarkeringsknappen). Vid det andra försöket godkänns din räkning.

    > [!NOTE]
    > När systemet upptäckte en skillnad mellan den förväntade kvantiteten och den kvantitet som du angav, bad det dig att räkna en andra gång eftersom fältet **Antal försök** anger *1* för **Guidad rullande inventering** menyalternativ för mobila enheter. Du guidades till ett specifikt artikelnummer och registreringsnummer eftersom båda alternativet **Visa artikelnummer** och **Visa ID-nummer** är *Ja* menyalternativ för mobila enheter.

1. Välj **OK** (bockmarkeringsknappen).

### <a name="review-the-cycle-counting-differences-for-scenario-1"></a>Granska skillnader för rullande inventering för scenario 1

Följ de här stegen när du vill granska differenserna för rullande inventering.

1. Gå tillbaka till Supply Chain Management.
1. Gå till **Warehouse management \> Arbete \> Arbetsdetaljer**.
1. Sök efter och välj det rullande inventeringsarbete som du tittat på tidigare. (Du kan t.ex. ange ett filter för kolumnen **Arbetspool-ID** för att hitta poster som har värdet *CycleCount*.) Observera att fältet **Arbetsstatus** för det här arbetet nu är inställt på *Pågående granskning*.

    > [!NOTE]
    > För arbetsanvändarkontot som du använde för att göra inventeringsarbetet sätts alternativet **ansvarig för rullande inventering** anges till *Nej* och fälten **Gräns för högsta procentandel**, **Gräns för högsta kvantitet** och **Gräns för högsta värde** anges till *0* (noll). Därför måste alla inventeringsdifferenser som den här användaren rapporterar godkännas manuellt och fältet **Arbetsstatus** för det relaterade arbetet ställs in *Väntande granskning*. Om det räknade värdet var inom avvikelsegränserna (som anges i fälten **Gräns för högsta procentandel** eller **Gräns för högsta kvantitet** på sidan **Arbetsanvändare**) eller om alternativet **ansvarig för rullande inventering** anges till *Ja* för användaren skulle arbetet automatiskt ha stängts.

1. I åtgärdsfönstret på fliken **Arbete** välj **Rullande inventering**.
1. Välj **Godkänn inventering** i åtgärdsfönstret.

    Skillnaden bokförs med hjälp av standardräkningsjournalen och en ny arbetsorder skapas.

1. På sidan **Transaktioner för rullande inventering** i åtgärdsfönstret, välj **Härlett arbete** för att hitta arbetet som har skapats för den godkända differensen.

## <a name="scenario-2-blind-cycle-counting"></a>Scenario 2: Rullande inventering av typen blind

För det här scenariot måste scenario 1 redan ha slutförts i systemet.

### <a name="create-cycle-counting-work-for-scenario-2"></a>Skapa rullande inventeringsarbete för scenario 2

Innan rullande inventering av typen blind kan göras måste du skapa arbete. Följ dessa steg för att skapa arbete för rullande inventering för artikelplats *01A02R2S2B* (BULK-06) i lagerställe *61*.

1. Gå till **Warehouse management \> Rullande inventering \> Rullande inventeringsarbete efter artikel**.
1. I dialogrutan **Skapa rullande inventeringsarbete efter artikel** ange fältet **Arbetspool-ID** till *CycleCount*.
1. På snabbfliken **Poster att inkludera**, välj **Filter**.
1. I frågeredigerarens dialogruta, på fliken **Intervall** lägg till tre rader med följande värden:

    - Rad 1:

        - **Register:** *Artiklar*
        - **Fält:** *Artikelnummer*
        - **Kriterier:** *L0101*

    - Rad 2:

        - **Tabell:** *Lagerdimensioner*
        - **Fält:** *lagerställe*
        - **Kriterier:** *61*

    - Rad 3:

        - **Tabell:** *Lagerdimensioner*
        - **Fält:** *Plats*
        - **Kriterier:** *01A02R2S2B*

1. Stäng dialogrutan för frågeredigeraren genom att välja **OK**.
1. Välj **OK** om du vill stänga dialogrutan **Skapa rullande inventeringsarbete efter artikel**.

    När arbetet med att skapa processen är klar får du ett informationsmeddelande.

### <a name="do-cycle-counting-work-for-scenario-2"></a>Gör rullande inventeringsarbete för scenario 2

Följ dessa steg när du har skapat arbete för rullande inventering i mobilappen Warehouse Management.

1. Logga in på mobilappen Warehouse Management som arbetsanvändaren som du konfigurerat i [Förbereda demodata för scenarierna](#prepare-demo-data) som beskrivs tidigare i denna artikel. För exemplet i denna artikel heter användaren *Julia Funderburk* och har konfigurerats för lagerställe *61*. (USMF-demodata bör låta dig logga in som den här arbetsanvändaren genom att ange *61* som användar-ID och *1* som lösenord.)
1. I huvudmenyn, välj **lager**.
1. I menyn **lager**, välj **Rullande inventering av typen blind**.
1. Välj fältet **Zon-ID** ange *BULK06* och markera **OK** (bockmarkeringsknappen).
1. Välj fältet **Artikel** ange *L0101* och markera **OK** (bockmarkeringsknappen).
1. Välj fältet **ID-nummer** ange *LP\_BULK\_06\_01* och markera **OK** (bockmarkeringsknappen).
1. Välj fältet **Kvt** ange *10* och markera **OK** (bockmarkeringsknappen).

    > [!NOTE]
    > När systemet upptäckte en skillnad mellan den förväntade kvantiteten och den kvantitet som du angav, bad det dig att räkna en andra gång eftersom fältet **Antal försök** anger *0* för **Rullande inventering av typen blind** menyalternativ för mobila enheter. Du ombads skanna artikelnummer och registreringsnummer eftersom båda alternativet **Visa artikelnummer** och **Visa ID-nummer** är *Nej* menyalternativ för mobila enheter.

1. Välj **OK** (bockmarkeringsknappen).

### <a name="review-the-cycle-counting-differences-for-scenario-2"></a>Granska skillnader för rullande inventering för scenario 2

Följ de här stegen när du vill granska differenserna för rullande inventering.

1. Gå tillbaka till Supply Chain Management.
1. Gå till **Warehouse management \> vanlig \> arbete \> granskning av väntande rullande inventeringsarbete**.
1. I åtgärdsfönstret på fliken **Arbete** välj **Rullande inventering**.
1. Välj **Avvisa inventering** i åtgärdsfönstret.

    Eftersom inventeringsdifferensen avvisades, stängs arbetet.

## <a name="scenario-3-spot-cycle-counting"></a>Scenario 3: Rullande inventering av typen spot

Lagerhållningsposten visar att det finns en lagerkvantitet av artikel *L0101* på plats *01A02R2S2B*. Lagerarbetaren är på plats *01A02R2S1B*. Den här platsen ska vara tom men är full. Därför gör lagerarbetaren omedelbart en platsräkning av den här platsen.

### <a name="do-cycle-counting-work-for-scenario-3"></a>Gör rullande inventeringsarbete för scenario 3

Följ dessa steg när du vill göra arbete för rullande inventering i mobilappen Warehouse Management.

1. Logga in på mobilappen Warehouse Management som arbetsanvändaren som du konfigurerat i [Förbereda demodata för scenarierna](#prepare-demo-data) som beskrivs tidigare i denna artikel. För exemplet i denna artikel heter användaren *Julia Funderburk* och har konfigurerats för lagerställe *61*. (USMF-demodata bör låta dig logga in som den här arbetsanvändaren genom att ange *61* som användar-ID och *1* som lösenord.)
1. I huvudmenyn, välj **lager**.
1. I menyn **lager**, välj **Punktinventering**.
1. Välj fältet **plats** ange *01A02R2S1B* och markera **OK** (bockmarkeringsknappen).

    Systemet identifierar att platsen är tom i Supply Chain Management.

1. Välj **Lägg till LP eller artikel**.
1. Välj fältet **Artikel** ange *L0101* och markera **OK** (bockmarkeringsknappen).
1. Välj fältet **ID-nummer** ange *LP\_BULK\_06\_01* och markera **OK** (bockmarkeringsknappen).
1. Välj fältet **Kvt** ange *9* och markera **OK** (bockmarkeringsknappen).

    Eftersom systemet upptäcker att den angivna licensinnehavaren redan finns tillgänglig på en annan plats i Supply Chain Management, flyttas den licensinnehavaren till den aktuella platsen. Därför ber systemet dig bekräfta förflyttningen.

1. Välj **OK** (bockmarkeringsknappen).

### <a name="review-the-cycle-counting-differences-for-scenario-3"></a>Granska skillnader för rullande inventering för scenario 3

Följ de här stegen när du vill granska resultaten för inventering.

1. Gå tillbaka till Supply Chain Management.
1. Gå till **Warehouse management \> Vanlig \> Arbetsdetaljer**.
1. Markera kryssrutan **Visa stängd** längst upp i rutnätet.
1. Ange filtret för kolumnen **Arbetsordertyp** till *Lagerrörelse*.

    Den här inventeringen identifieras automatiskt som en lagerrörelse. Den här flytten tillåts eftersom alternativet **Tillåt flytt av ID-nummer under rullande inventering** har ställts in på *Ja* för lagerställe *61* på sidan **Lagerställen**.

## <a name="scenario-4-define-cycle-count-thresholds"></a>Scenario 4: Definiera tröskelvärden för rullande inventering

Ett sätt att skapa arbete för rullande inventering är att använda tröskelvärden. En tröskel för rullande inventering anger kvantitets- eller procentgränsen för lagerartiklar. En arbetsuppgift för rullande inventering skapas automatiskt när tröskelgränsen nås.

Det finns till exempel 60 artiklar på en plats som har en tröskel för rullande inventering på 40. Under en försäljningsordertransaktion plockas 25 artiklar från platsen och placeras på en mellanlagringsplats. Eftersom det nya artikelantalet är 35, d.v.s. mindre än tröskelkvantiteten, skapas arbete för rullande inventering automatiskt för platsen.

Följ dessa steg när du vill konfigurera tröskelvärden för rullande inventering.

1. Gå till **Warehouse management \> Inställningar \> Rullande inventering \> Trösklar för rullande inventering**.
1. I åtgärdsfönstret väljer du **Ny** för att skapa en tröskel och anger följande värden:

    - **Tröskel-ID för rullande inventering:** *L0101*
    - **Beskrivning:** *tröskel L0101*
    - **Tröskelmängd:** *2*
    - **Enhet:** *ea*
    - **Kapacitetströskel baserat på procent:** *0,00*
    - **Typ av rullande inventeringströskel:** *Kvantitet*
    - **Bearbeta rullande inventering direkt:** *Ja*
    - **Dagar mellan rullande inventering:** *1*
    - **Arbetspools-ID:** *CycleCount*

1. Klicka på **Välj artiklar** i åtgärdsfönstret.
1. I dialogrutan för frågeredigerare på fliken **Område** hittar du på den rad där fältet **Fält** anges till *Artikelnummer*. Ställ in fältet **villkor** för den här raden till *L0101*.
1. Stäng dialogrutan för frågeredigeraren genom att välja **OK**.

    Nu har du definierat en tröskel för rullande inventering för artikel *L0101*.

Rullande inventering skapas nu för artikel *L0101* på valfri plats om lagerhållningskvantiteten är mindre än 2 och om datumet för den senaste rullande inventering för platsen inte är idag.

## <a name="scenario-5-define-cycle-count-plans"></a>Scenario 5: Definiera planer för rullande inventering

Med hjälp av planer för rullande inventering kan du automatisera skapandet av rullande inventeringsarbete. Du kan konfigurera varje plan för för rullande inventering med specifika artikel- och platsfrågor. När batchjobbet körs skapas rullande inventeringsarbete för alla platser som matchar artikel- och platskriterierna (upp till det maximala antalet inventeringar som har angetts för planen). När rullande inventeringsarbete skapas innehåller raden för rullande inventering information om vilken plats som ska räknas. Den lagerbehållning som är kopplad till den platsen är inte spärrad. Det är därför tillgängligt för reservationer och utgående bearbetningar, även om det finns öppna inventeringsarbete.

Följ dessa steg när du vill konfigurera plan för rullande inventering.

1. Gå till **Warehouse management \> Inställningar \> Rullande inventering \> Planer för rullande inventering**.
1. I åtgärdsfönstret, välj **Ny** om du vill lägga till en rad i rutnätet och ange följande värden:

    - **Plan-ID för rullande inventering:** *BULK06*
    - **Beskrivning:** *Inventering av plats för BULK06*
    - **Arbetspools-ID:** *CycleCount*
    - **Högsta antal rullande inventeringar:** *10*
    - **Dagar mellan rullande inventering:** *10*
    - **Tomma platser:** *Undanta tomma*
    - **Arbetsmall:** Lämna det här fältet tomt.

1. Klicka på **Välj platser** i åtgärdsfönstret.
1. En dialogruta för standard frågeredigeraren visas. På fliken **intervall**, lägg till en rad med följande värden:

    - **Register:** *platser*
    - **Fält:** *zon-ID*
    - **Kriterier:** *BULK06*

1. Stäng dialogrutan för frågeredigeraren genom att välja **OK**.
1. Välj **Bearbetning av plan för rullande inventering** i åtgärdsfönstret.
1. I dialogrutan **Planer för rullande inventering** på snabbfliken **Kör i bakgrunden** ange **Batch-bearbetning** till *Ja*.
1. Ange **upprepning**.
1. I dialogrutan **Definiera upprepning** ställer du in batchjobbet så att det startar omedelbart och körs en gång varje minut och så att det inte finns något slutdatum.
1. Välj **OK** för att stänga dialogrutan **Definiera upprepning**.
1. Välj **OK** för att stänga dialogrutan **Planer för rullande inventering**.

    Ett meddelande informerar om att jobbet har lagts till i batchkön.

1. Klicka på **Warehouse management \> Allmänt \> Tidsplanera cykelinventering**. Planen börjar omedelbart och skapar inventeringsarbete. Eftersom inventeringsarbetet inte har slutförts ställs **status** fältet in på *Pågår*. Efter en minut ändras värdet i kolumnen **Totalt antal cykler** till *1*.

    > [!NOTE]
    > Rullande inventeringsarbete skapas inte om antalet dagar sedan den senaste inventeringen är lägre än värdet som du har angett för fältet **Dagar mellan rullande inventering** för plan för rullande inventering. Om till exempel fältet **Dagar mellan rullande inventering** anges till *5* kommer ett arbete för rullande inventering att skapas var femte dag. Men om arbete för rullande inventering bearbetas på dag tre kommer nästa arbete för rullande inventering skapas fem dagar efter att den sista rullande inventeringen bearbetades på dag åtta.

1. Välj **Arbeta** i åtgärdsfönstret om du vill visa inventeringsarbetet som har skapats.
