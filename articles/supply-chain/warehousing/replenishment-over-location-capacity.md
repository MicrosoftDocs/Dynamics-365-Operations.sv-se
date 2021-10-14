---
title: Lagerpåfyllnad över platskapacitet
description: Det här avsnittet innehåller information om funktionen påfyllnad över lagerställekapacitet. Den här funktionen gör att allt påfyllningsarbete som krävs för dagen skapas och kan användas för att se till att plockplatsen varken hamnar utanför lagret eller går över kapacitet.
author: mirzaab
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSReplenishmentTemplates, WHSLocationLimit
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-16
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: 78bea4ee2429323a6e087c6433a8e496b08f4cea
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/29/2021
ms.locfileid: "7576122"
---
# <a name="replenishment-over-location-capacity"></a>Lagerpåfyllnad över platskapacitet

[!include [banner](../includes/banner.md)]

Vissa lagerställen med hög volym eller begränsat utrymme måste leverera mer kvantitet av en artikel på en dag än vad som får plats på plockplatsen. Funktionen *påfyllnad över lagerställekapacitey* gör att allt påfyllningsarbete som krävs för dagen skapas och kan användas för att se till att plockplatsen varken hamnar utanför lagret eller går över kapacitet.

Funktionen gör det möjligt att skapa mer återanskaffningsarbete än vad som får plats på en plats och det blockerar påfyllningsarbetet från att slutföras när platsen är full. När lagret på plockplatsen sjunker under ett konfigurerbart tröskelvärde görs mer återanskaffningsarbete tillgängligt.

## <a name="turn-on-the-replenishment-over-location-capacity-feature"></a>Aktivera funktionen påfyllnad över lagerställekapacitet

Om du vill göra den här funktionen tillgänglig aktiverar du följande funktioner i [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) i denna ordning:

1. Arbetsspärr för hela organisationen
1. Lagerpåfyllnad över platskapacitet

## <a name="set-up-the-feature-for-the-example-scenario"></a>Ställ in funktionen för det här exempelscenariot

Det här avsnittet innehåller riktlinjer och ett exempel som visar hur du ställer in den här funktionen och förbereder exempeldata för scenariot som ges senare i det här avsnittet.

### <a name="enable-sample-data"></a>Aktivera exempeldata

Om du vill arbeta genom detta [exempelscenario](#example-scenario) med hjälp av de exempelposter och värden som anges här måste du använda ett system där standard [demodata](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) har installerats. Dessutom måste du välja den **USMF** juridiska personen innan du börjar.

### <a name="location-profile"></a>Platsprofiler

Aktivera funktionen för påfyllning över kapacitet på platsprofilen.

1. Gå till **Lagerstyrning \> Inställningar \> Lagerställe \> Platsprofiler**.
1. Markera **PICK-06** i det vänstra fönstret.
1. I åtgärdsfönstret väljer du **Redigera**.
1. Ange följande värden på snabbfliken **lagerpåfyllnad**:

    - **Överskriden kapacitet för plats:** *ja*

        När den aktiveras blir platsens maxkapacitet tillåten att överskridas med påfyllnadsarbete. Detta aktiverar även andra fält på snabbfliken **lagerpåfyllnad**.

    - **Tröskeltyp för arbetstillgänglighet:** *kvantitet*

        I det här fältet anges den metod som används för att bestämma när mer arbete ska frisläppas. Du kan släppa antingen kvantitet eller procent:

        - *Procent* – Välj det här alternativet om du vill använda procentkapacitet som baseras på lagergränser eller volymmetriker. Om du väljer det här alternativet aktiveras fältet **Överfyllnadsprocent** och inaktiverar de två kvantitetsrelaterade fälten,  **Överfyllnadskvantitet** och **Överfyllnadsenhet**.

            Du kan använda det här alternativet om plockplatserna använder volymmetriker.

            Om det här alternativet är markerat ställer du in **Överfyllnadsprocent** för den procentsats som ytterligare påfyllningsarbete kommer att göras tillgängligt för.

        - *Kvantitet* – Välj det här alternativet om du vill använda ett specifikt värde för kvantitet. Om du väljer det här alternativet inaktiveras fältet **Överfyllnadsprocent** och aktiverar fälten **Överfyllnadskvantitet** och **Överfyllnadsenhet**.

            Använd det här alternativet om du inte använder volymmetriker för de platser som ska fyllas på, eller när du har enhetliga kvantiteter som du vill att mer lager ska skickas till.

           Om det här alternativet är markerat ställer du in fälten **Överfyllnadskvantitet** och **Överfyllnadsenhet** till kvantitet och enhet där mer påfyllningsarbete kommer att göras tillgängligt.

    - **Överfyllnadskvantitet:** *0.65*

        Det här fältet anger den kvantitet där vilken platsen överfylls.

        Arbetet kommer att finnas tillgängligt när summan av den tillgängliga kvantiteten på platsen och arbetskvantiteten ligger under detta värde. Eventuell kvantitet för påfyllningsarbete som är över detta värde spärras och måste avblockeras manuellt.

        Platslagergränser beaktas när arbetskvantiteten beräknas.

    - **Överfyllnadsenhet:** *PL*

        Det här fältet definierar den enhet som är kopplad till överfyllnadskvantiteten.

        I det här fallet görs mer lagerpåfyllnadsarbete när platsen kommer ner till 0,65 lastpall (PL).

    - **Överfyllnad i procent**

        Det här fältet anger den procentsats där platsen överfylls.

        Arbetet kommer att finnas tillgängligt när summan av den tillgängliga kvantiteten på platsen och arbetskvantiteten ligger under denna procentsats. Eventuell kvantitet för påfyllningsarbete som är procentsats över detta värde spärras och måste avblockeras manuellt.

        Platslagergränser beaktas när arbetskvantitetens procentsats beräknas. Om inga platslagringsgränser anges beräknas den procentuella kvantiteten av volym om volymbegränsningar definieras i platsprofilen.

> [!IMPORTANT]
> Om du använder demodata för juridiska personen **USMF** och tidigare aktiverat funktionen för positionering av funktionen *Placering för plats-ID-nummer* måste du stänga inställningen **Aktivera plats för positionering av ID-nummer** för platsprofilen **BULK-06** för att slutföra de mobila stegen i exempelscenariot.

### <a name="wave-step-code"></a>Kod för påfyllnadssteg

> [!NOTE]
> Om du vill ställa in en påfyllnadskod som beskrivs här, kanske du först måste använda [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att aktivera funktionen med namnet *Påfyllnadsstegkod för hela organisationen*.

1. Gå till **Lagerstyrning \> Inställningar \> Påfyllnader \> Koder för påfyllnadssteg**.
1. Välj **ny** och ange sedan följande värden:

    - **Kod för påfyllnadssteg:** *lagerp*
    - **Beskrivning för påfyllnadssteg:** *lagerpåfyllnad*
    - **Typ av påfyllnadssteg:** *lagerpåfyllnad*

1. Välj **Spara**.

### <a name="replenishment-template"></a>Mall för lagerpåfyllnad

Mallar för lagerpåfyllnad är en uppsättning regler som kontrollerar hur en plats fylls på.

1. Gå till **Lagerstyrning \> Inställningar \> Lagerpåfyllnad \> Mall för lagerpåfyllnad**.
1. I åtgärdsfönstret väljer du **Redigera**.
1. I avsnittet **Översikt** väljer du den rad där fältet **Lagerpåfyllnadsmall** anges till *Efterfrågan av lagerpåfyllnad*.
1. Ange följande värden.

    - **Kod för påfyllnadssteg:** *lagerp*
    - **Tillåt påfyllnad av efterfrågan att använda icke-reserverade kvantiteter:** *Ja*

1. Välj **Spara**.

### <a name="wave-template"></a>Påfyllnadsmall

1. Gå till **Lagerstyrning \> Inställningar \> Påfyllnader \> Påfyllnadsmallar**.
1. I vänster ruta ange fältet **Malltyp för påfyllnad** till *Leverans*.
1. Välj mallen **61 leverans** i listan.
1. I åtgärdsfönstret väljer du **Redigera**.
1. På snabbfliken **Allmänt** ställer du in alternativet **Automatisera frisläppning av lagerpåfyllnadsarbete** till *Ja*.

    Ange det här alternativet till *Ja* om du vill skapa efterfrågebaserat återanskaffningsarbete och frisläppa det automatiskt. Du måste lägga till påfyllnadsmetoden i påfyllnadsmallen och skapa en återanskaffningsmall av typen **Påfyllnadsefterfrågan**. Ställ in en påfyllnadsmall på sidan för **Återanskaffningmallar**. Om du vill skapa en påfyllningsmall måste du lägga till metoden för påfyllnadsmall.

1. På snabbfliken **Metoder** i kolumnen **Valda metoder** hittar du följande rad:

    - **Metodnamn:** *fylla på*
    - **Namn:** *lagerpåfyllnad*

1. Ställ in fältet **Kod för påfyllnadssteg** för den här raden till *lagerp*.
1. Välj **Spara**.

## <a name="example-scenario"></a>Exempelscenario

När du har gjort alla exempel data som du redan har beskrivit och ställt in dem kan du arbeta i det här scenariot för att testa funktionen *Påfyllnad över lagerställekapacitet*. De värden som visas i det här scenariot förutsätter att du arbetar med standard demodata, att du har valt den juridiska personen **USMF** och att du har förberett exempelposterna som beskrivs tidigare i det här avsnittet. Det här scenariot fungerar även som ett exempel som visar hur funktionen kan användas i en produktionsinställning.

### <a name="create-replenishment-work"></a>Skapa lagerpåfyllnadsarbete

#### <a name="create-sales-order-1"></a>Skapa försäljningsorder 1

1. Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.
1. I åtgärdsfönstret välj **Ny** om du vill öppna dialogrutan för att skapa en ny försäljningsorder.
1. Ange följande värden i dialogrutan:

    - **Kundkonto:** *US-007*
    - **Lagerställe:** *61*

1. Välj **OK** för att skapa den försäljningsordern och stänga dialogrutan.
1. Den nya försäljningsordern öppnas. Den innehåller en ny tom rad i snabbfliken **Försäljningsorderrader**. Ställ in följande värden på denna rad:

    - **Artikelnummer:** *T0100*
    - **Kvantitet:** *40*

1. På snabbfliken **Försäljningsorderrader** välj **Lager \> Reservation**.
1. På sidan **Reservation** väljer du **Reservera parti**.
1. Stäng sidan.
1. I åtgärdsfönstret på fliken **Lagerställe** välj **Frisläpp till regel för lagerställe**.

    Du får ett informationsmeddelande som visar påfyllnad-ID och leverans-ID som skapades. En lagerpåfyllnad skapas också.

    Du får också ett varningsmeddelande med status "arbets-ID XXXX kan inte avblockeras eftersom det har oavslutat lagerpåfyllnadsarbete".

#### <a name="create-sales-order-2"></a>Skapa försäljningsorder 2

1. På sidan **Alla försäljningsorder** i åtgärdsfönstret, välj **Ny** om du vill öppna dialogrutan för att skapa en ny försäljningsorder.
1. Ange följande värde i dialogrutan:

    - **Kundkonto:** *US-001*
    - **Lagerställe:** *61*

1. Välj **OK** för att skapa den försäljningsordern och stänga dialogrutan.
1. Den nya försäljningsordern öppnas. Den innehåller en ny tom rad i snabbfliken **Försäljningsorderrader**. Ställ in följande värden på denna rad:

    - **Artikelnummer:** *T0100*
    - **Kvantitet:** *60*

1. På snabbfliken **Försäljningsorderrader** välj **Lager \> Reservation**.
1. På sidan **Reservation** väljer du **Reservera parti**.
1. Stäng sidan.
1. I åtgärdsfönstret på fliken **Lagerställe** välj **Frisläpp till regel för lagerställe**.

    Du får ett informationsmeddelande som visar påfyllnad-ID och leverans-ID som skapades. En lagerpåfyllnad skapas också.

    Du får också ett varningsmeddelande med status "arbets-ID XXXX kan inte avblockeras eftersom det har oavslutat lagerpåfyllnadsarbete".

#### <a name="create-sales-order-3"></a>Skapa försäljningsorder 3

1. På sidan **Alla försäljningsorder** i åtgärdsfönstret, välj **Ny** om du vill öppna dialogrutan för att skapa en ny försäljningsorder.
1. Ange följande värden i dialogrutan:

    - **Kundkonto:** *US-004*
    - **Lagerställe:** *61*

1. Välj **OK** för att skapa den försäljningsordern och stänga dialogrutan.
1. Den nya försäljningsordern öppnas. Den innehåller en ny tom rad i snabbfliken **Försäljningsorderrader**. Ställ in följande värden på denna rad:

    - **Artikelnummer:** *T0100*
    - **Kvantitet:** *30*

1. På snabbfliken **Försäljningsorderrader** välj **Lager \> Reservation**.
1. På sidan **Reservation** väljer du **Reservera parti**.
1. Stäng sidan.
1. I åtgärdsfönstret på fliken **Lagerställe** välj **Frisläpp till regel för lagerställe**.

    Du får ett informationsmeddelande som visar påfyllnad-ID och leverans-ID som skapades. En lagerpåfyllnad skapas också.

    Du får också ett varningsmeddelande med status "arbets-ID XXXX kan inte avblockeras eftersom det har oavslutat lagerpåfyllnadsarbete".

#### <a name="view-work-details"></a>Visa information om arbete

1. Gå till **Lagerstyrning \> Arbete \> Arbetsdetaljer**.
1. I avsnittet **Översikt** filtrerar du kolumnen **Lagerställe** för lagerställe *61*.
1. Du bör se att sju arbets-ID:n har skapats för de tre försäljningsorder som krävs.

    - Tre av de sju arbets-ID:na har värdet **Arbetsordertyp** av *Lagerpåfyllnad* och fyra har ett värde **Arbetsordertyp** av *Försäljningsorder*.
    - Alla tre arbets-ID:n som har en **Arbetsordertyp** värdet för *Påfyllning* har samma *plockning* och *placering* i avsnittet **Rader**:

        - **Plocka:** *02A01R5S1B*
        - **Placera:** *06A01R2S1B*

    - Två arbets-ID:n skapades för försäljningsorder 1.

1. Anteckna arbets-ID:t för försäljningsorder.

Beroende på behållningskvantitet kan de skapade arbetskvantiteterna skilja sig något. Men generellt bör de arbetsrubriker som skapas överensstämma med det här scenarioexemplet.

#### <a name="on-hand-inventory-license-plate-id"></a>ID-nummer för lagerbehållning

Senare i det här scenariot använder du mobilappen för distributionslagerhantering (eller en emulator), där du måste identifiera ID-numret för att slutföra scenarier med plockning och lagerpåfyllnad.

Följ instruktionerna nedan för att hitta de ID-nummer som du kommer att behöva senare.

1. Gå till **Lagerhantering \> Förfrågningar och rapporter \> Behållningslista**.
1. Välj knappen **Visa filter** om du vill öppna filterrutan.
1. Ange följande filtreringskriterier för att hämta ID-nummer för scenariot. Använd filtret *börjar med*.

    - **Artikelnummer:** *T0100*
    - **Lagerställe:** *61*

1. Välj **Tillämpa**.
1. I åtgärdsfönstret, välj **Dimensioner**.
1. I dialogrutan **Dimensionsvisning** i avsnittet **Lagerdimensioner** väljer du alla värden.
1. I avsnittet **Transaktioner** väljer du **Artikelnummer** och **Kvantitet \<\> 0**.
1. När du är klar klickar du på **OK** för att stänga dialogrutan.
1. Rutnätet **Behållning** visar ID-nummer för artikel *T0100* på varje plats. Anteckna vilket ID-nummer som finns på varje plats, eftersom du kommer att behöva dessa uppgifter vid ett senare tillfälle.
1. Stäng sidan.

### <a name="process-steps"></a>Processteg

Du kommer att utföra återanskaffningen av distributionslagret för de första två arbets-ID:n. Arbetet med det tredje påfyllnadsarbetet spärras tills lagernivån på plockplatsen sjunker under tröskelvärdet.

#### <a name="replenishment"></a>Lagerpåfyllnad

1. Logga in på mobilappen för distributionslagerhantering en användare i lager ställe *61*. (Ange *61* som användar-ID och *1* som lösenord.)
1. Gå till **Lager \> Lagerpåfyllnad**.

    Du uppmanas att slutföra det första påfyllningsarbetet. Artikelnummer, kvantitet och plats att plocka från visas.

1. I fältet **LP** ange ID-nummer för den artikel på platsen som visas.
1. Välj **OK**-knappen (bockmarkeringssymbol).

    Systemet genererar ett mål-ID-nummer för det nya ID-numret för den plockade artikeln.

1. Bekräfta värdet genom att välja **OK**.

    Infört arbete visas och instruerar användaren att placera mål-ID-numret på påfyllningsplatsen. *Placeringsplatsen* bör vara **06A01R2S1B**.

1. Bekräfta placeringsinformationen och välj **OK**.

    Meddelandet "arbete slutförd" visas och information om nästa uppgift med påfyllnadsplockning visas: artikelnummer, kvantitet och lagerställe att plocka från. Plockningsplatsen kommer att vara densamma som den första lagerpåfyllnadsplatsen. Därför får ID-numret samma ID-nummer som användes för den första lagerpåfyllnadsuppgiften.

1. Upprepa föregående steg för att slutföra lagerpåfyllnadsarbetet för den andra arbetsuppgiften. Kvantiteten och ID-numret kommer att skilja sig från kvantiteten och mål-ID-numret för den första arbetsuppgiften.

När det andra lagerpåfyllnadsarbetet har slutförts visas meddelandet "färdigt arbete". Den mobila enheten informerar också om att inget arbete är tillgängligt, även om en del av lagerpåfyllnadsarbetet kvarstår. Det här problemet beror på att en tillgänglighetsstatus har angetts för lagerpåfyllnadsarbetet *Hållen* och därför markeras det som **Spärrat**.

Statusen *Hållen* utlöstes eftersom platsprofilen för plockningsplatsen som arbetet tilldelas till har ett värdet för **Överfyllnadskvantitet** på *0,65 PL*. De två föregående påfyllningsarbetena fyller platsen i stort sett mot dess överfyllnadsgräns för artikel *T0100*. (Enhetskonverteringen för artikeln är *1 PL = 100 ea*.) Därför kommer det återstående påfyllningsarbetet att överskrida sin överfyllnadsgräns.

Tills tillräckligt med lager plockas från platsen för att få plats under tröskelvärdet för arbetsfrisläppning på menyalternativet mobil enhet förblir detta påfyllningsarbete spärrat.

#### <a name="sales-order-pick"></a>Plockning av försäljningsorder

Innan lagerpåfyllnadsarbetet kan slutföras måste plockningsplatsen vara tom för lagret till en nivå där det återstående påfyllningsarbetet kan avbrytas. Med andra ord kan summan av lagerbehållningen på platsen och den påfyllningskvantitet som anges inte överskrida värdet för **Överfyllnadskvantitet**. När den här summan är mindre än överfyllnadskvantitet, kommer det återstående lagerpåfyllnadsarbetet att spärras.

1. Logga in på mobilappen för distributionslagerhantering en användare i lager ställe *61*. (Ange *61* som användar-ID och *1* som lösenord.)
1. Gå till **Utgående \> Försäljningsplockning**.
1. Ange det första arbets-ID:t för försäljningsorder 1.

    Se arbets-ID:n för försäljningsorder som du har gjort en anteckning för tidigare på sidan **arbetsuppgifter**. Det arbets-ID som du anger här kommer att generera ett plockningsarbete för en kvantitet på 10 ea från två separata platser.

1. Välj **OK**.

    Uppgiftssidan **Försäljningsorder: plockning** visar artikelnummer, kvantitet och plats som du vill plocka från för den första platsen.

1. I fältet **LP** ange ID-nummer för den artikel på platsen som visas.
1. Välj **OK**-knappen (bockmarkeringssymbol).

    Uppgiftssidan **Försäljningsorder: plockning** visar artikelnummer, kvantitet och plats som du vill plocka från för nästa plats.

1. I fältet **LP** ange ID-nummer för den artikel på platsen som visas.
1. Välj **OK**-knappen (bockmarkeringssymbol).

    Sidan **Försäljningsorder: placera** ger instruktioner om att både slutförda plockningar ska föras in på den utgående mellanlagringsplatsen.

1. Välj **OK**.

    Du får ett meddelande arbetet är slutfört.

1. Ange det andra arbets-ID:t för försäljningsorder 1.

    Det finns bara en plockningsuppgift för detta arbets-ID.

1. Välj **OK**.

    Uppgiftssidan **Försäljningsorder: plockning** visar artikelnummer, kvantitet och plats som du vill plocka från.

1. I fältet **LP** ange ID-nummer för den artikel på platsen som visas.

    Det ID-numret som du anger kommer att vara en av de systemgenererade ID-numren från uppgifterna för påfyllningsarbetet. Kontrollera att du har hämtat rätt ID-nummer genom att kontrollera lager på sidan **Behållningslista** för artikeln, platsen och kvantiteten.

1. Välj **OK**-knappen (bockmarkeringssymbol).
1. Bekräfta instruktionerna för placeringsuppgiften på den utgående mellanlagringsplatsen.
1. Välj **OK**.

    Du får ett meddelande arbetet är slutfört.

Försäljningsorder 2 spärras från plockning eftersom den lagerpåfyllnadsuppgift som den är kopplad till inte är slutförd. För närvarande finns det fortfarande en kvantitet på 30 ea på plockningsplatsen och lagerpåfyllnadskvantitet för försäljningsorder 2 är 60 ea. Summan av lagerbehållningen och det påfyllnings lagret (90 ea) överskrider överflödningskvantiteten på 0,65 PL (eller 65 ea). Innan påfyllningsarbetet kan slutföras måste försäljningsorder 3 plockas.

1. Ange arbets-ID:t för försäljningsorder 3.

    Det finns bara en plockningsuppgift för detta arbets-ID.

1. Välj **OK**.

    Uppgiftssidan **Försäljningsorder: plockning** visar artikelnummer, kvantitet och plats som du vill plocka från.

1. I fältet **LP** ange ID-nummer för den artikel på platsen som visas.

    Det ID-numret som du anger kommer att vara en av de systemgenererade ID-numren från uppgifterna för påfyllningsarbetet. Kontrollera att du har hämtat rätt ID-nummer genom att kontrollera lager på sidan **Behållningslista** för artikeln, platsen och kvantiteten.

1. Välj **OK**-knappen (bockmarkeringssymbol).
1. Bekräfta instruktionerna för placeringsuppgiften på den utgående mellanlagringsplatsen.
1. Välj **OK**.

    Du får ett meddelande arbetet är slutfört.

Så snart summan av lagerbehållningen på plockningsplatsen och lagerpåfyllnadskvantitet ligger under tröskeln kan du bearbeta det återstående påfyllningsarbetet.

Gå tillbaka till sidan **Arbetsinformation** och observera att lagerpåfyllnadsarbetet för sista lagerpåfyllnadsdelen (för försäljningsorder 2) är *Öppen*, eftersom det nu finns tillräckligt med utrymme på platsen för att acceptera påfyllnaden.

Du kan nu bearbeta påfyllningsarbetet via den mobila enheten.

1. Gå till **Lager \> Lagerpåfyllnad**.

    Du uppmanas att slutföra det återstående påfyllningsarbetet. Artikelnummer, kvantitet och plats att plocka från visas.

1. I fältet **LP** ange ID-nummer för den artikel på platsen som visas.
1. Välj **OK**-knappen (bockmarkeringssymbol).

    Systemet genererar ett mål-ID-nummer för det nya ID-numret för den plockade artikeln.

1. Bekräfta värdet genom att välja **OK**.

    Infört arbete visas och instruerar användaren att placera mål-ID-numret på påfyllningsplatsen. *Placeringsplatsen* bör vara **06A01R2S1B**.

1. Bekräfta placeringsinformationen och välj **OK**.

    Meddelanden med "arbete slutfört" och "inget arbete tillgängligt" visas.

Du kan nu välja försäljningsorder 2. Den blev spärrad när det påfyllningsarbete som har kopplats till försäljningsordern slutfördes.

1. Ange arbets-ID:t för försäljningsorder 2.

    Det finns bara en plockningsuppgift för detta arbets-ID.

1. Välj **OK**.

    Uppgiftssidan **Försäljningsorder: plockning** visar artikelnummer, kvantitet och plats som du vill plocka från.

1. I fältet **LP** ange ID-nummer för den artikel på platsen som visas.

    Det ID-numret som du anger kommer att vara det systemgenererade ID-numret från uppgiften för påfyllningsarbetet. Kontrollera att du har hämtat rätt ID-nummer genom att kontrollera lager på sidan **Behållningslista** för artikeln, platsen och kvantiteten.

1. Välj **OK**-knappen (bockmarkeringssymbol).
1. Bekräfta instruktionerna för placeringsuppgiften på den utgående mellanlagringsplatsen.
1. Välj **OK**.

    Du får ett meddelande arbetet är slutfört.

## <a name="notes-and-tips"></a>Anteckningar och tips

- Den här funktionen fungerar med alla typer av påfyllnad: påfyllnad av efterfrågan, min/max, lastefterfrågan och artikelplacering.
- Du kan manuellt åsidosätta lagerpåfyllnadsarbetets tillgänglighet för varje arbetsrubrik från sidan **Arbetsinformation** om du vill.
- När systemet ställer in tillgänglighet av lagerpåfyllnadsarbete beaktas alla lager som redan finns på platsen innan något arbete har slutförts
- Varje exemplar av försäljningsorderarbete är kopplat till ett visst påfyllningsarbete. Det finns ingen motsvarande funktion för tillgänglighet av försäljningsresurser.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]