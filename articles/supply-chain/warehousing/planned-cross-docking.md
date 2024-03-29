---
title: Planerad direktleverans
description: I denna artikel beskrivs avancerad, planerad direktleverans, där lagerkvantiteten som krävs för en order dirigeras direkt från inleverans eller framställande till rätt utlastningsplats eller mellanlagringsområde. Allt återstående lager från den inkommande källan dirigeras till rätt lagringsplats genom den vanliga artikelinförselprocessen.
author: Mirzaab
ms.date: 08/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSCrossDockingTemplate, WHSLoadPostMethod, WHSWorkClass, WHSWorkTemplateTable, WHSLocDirTable, WHSPlannedCrossDocking
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: b530cc1403458775fd330e826a32417d3b03bf25
ms.sourcegitcommit: 203c8bc263f4ab238cc7534d4dd902fd996d2b0f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/23/2022
ms.locfileid: "9334578"
---
# <a name="planned-cross-docking"></a>Planerad direktleverans

[!include [banner](../includes/banner.md)]

I denna artikel beskrivs avancerad, planerad direktleverans. Direktleverans är en lagerställesprocess där lagerkvantiteten som krävs för en order dirigeras direkt från inleverans eller skapande till rätt utlastningsplats eller mellanlagringsområde. Allt återstående lager från den inkommande källan dirigeras till rätt lagringsplats genom den vanliga artikelinförselprocessen.

Direktleverans låter medarbetare hoppa över inkommande artikelinförsel och utgående plockning av lager som redan har markerats för en utgående order. Därför minimeras antalet gånger som lagret vidrörs, om det är möjligt. Eftersom det är mindre interaktion med systemet ökas dessutom tid och utrymmesbesparingar på lagret.

Innan du kan köra direktleverans måste du konfigurera en ny mall för direktleverans där leveranskällan och andra uppsättningar krav för direktleverans har angetts. När den utgående ordern skapas måste raden markeras mot en inkommande order som innehåller samma artikel. Du kan välja kodfältet för direktiv i direktutleveransmallen, på liknande sätt som du konfigurerar lagerpåfyllnads- och inköpsorder.

Vid tiden för inleverans av inkommande order identifierar inställningen för direktleverans automatiskt behovet av direktleverans och skapar flyttningsarbetet för den begärda kvantiteten, baserat på inställningen för platsdirektivet.

> [!NOTE]
> Lagertransaktioner avregistreras *inte* när jobbet för direktleverans avbryts, även om inställningen för denna funktion aktiveras i parametrar för lagerstyrning.

## <a name="turn-on-the-planned-cross-docking-features"></a>Aktivera funktionen planerad direktleverans

Om du kör version 10.0.28 eller tidigare i Supply Chain Management måste du eventuellt aktivera planerad direktutleverans innan du kan använda den. Gå till [utgiftshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) och aktivera följande funktioner i följande ordning:

1. *Planerad direktleverans*<br>(Från och med version 10.0.29 av Supply Chain Management är denna funktion obligatorisk och kan inte inaktiveras.)
1. *Mallar för direktleverans med platsdirektiv*<br>(Från och med version 10.0.29 av Supply Chain Management är denna funktion aktiverad som standard.)
    > [!NOTE]
    > Med hjälp av denna funktion kan fältet **Direktivkod** anges i direktleveransmallen, på liknande sätt som du konfigurerar påfyllnadsmallar. Genom att aktivera den här funktionen förhindrar du att du lägger till en kod för direktiv på direktleveransens arbetsmallrader för den slutgiltiga *Placera*-raden. På så sätt ser du till att den slutliga placeringsplatsen kan fastställas under skapandet av arbetet innan arbetsmallar övervägs.

## <a name="setup"></a>Ställ in

### <a name="regenerate-load-posting-methods"></a>Generera om lastbokföringsmetoder

Planerad direktleverans är implementerad som en lastbokföringsmetod. När du har aktiverat funktionen måste du generera om metoderna.

1. Gå till **Lagerstyrning \> Inställningar \> Lastbokföringsmetoder**.
1. Klicka på **återskapa metoder** i åtgärdsfönstret.

    När återskapandet är slutfört visas en metod med ett värde för **metodnamn** på *planCrossDocking*.

1. Stäng sidan.

### <a name="create-a-cross-docking-template"></a>Skapa en direktleveransmall.

1. Gå till **Lagerstyrning \> Inställningar \> Arbete \> Mallar för direktleverans**.
1. I åtgärdsfönstret, välj **Ny** för att skapa en mall.
1. I rubriken anger du följande värden:

    - **Sekvens:** *1*

        I det här fältet definieras ordningen som mallarna utvärderas i.

    - **Mall-ID för direktleverans:** *51*
    - **Beskrivning:** *lagerställe 51*
    - **Frisläppning av efterfrågan:** *Före leverans av inleverans*
    - **Lagerställe:** *51*

1. Inställningen på snabbfliken **Planering** styr hur mallen fungerar. Ange följande värden.

    - **Krav på begäran:** *Inga*

        Det här fältet definierar kraven för efterfrågelager. Om behovet måste kopplas till leveransen före frisläppning väljer du markera *markering*. Om efter frågeställningen måste vara orderreserverad mot försörjningen före frisläppning väljer du *Orderreservation*.

    - **Söka efter typ:** *utleveransplatser*

        Det här fältet definierar om direktleveransen ska använda för produktions-/lastplatserna från leverans, eller om den ska använda platsdirektiv för att hitta sina egna mellanlagrings- eller lastplatser.

    - **Arbetsmall:** Lämna det här fältet tomt.

        Det här fältet definierar arbetsmallen som ska användas när direktleverans skapas.

    - **Validera på leveranskvitto igen:** *Nej*

        Det här alternativet anger om leveransen ska omvalideras under inleverans. Om det här alternativet har värdet *Ja* kontrolleras både det maximala tidsfönstret och intervallet för utgångsdagar.

    - **Direktivkod:** Lämna det här fältet tomt

        Det här alternativet aktiveras av funktionen *Mallar för direktleverans med platsdirektiv* (från och med Supply Chain Management version 10.0.29 aktiveras funktionen som standard). Systemet använder platsdirektiv för att avgöra vilken som är den bästa platsen att flytta lager för direktleverans till. Du kan konfigurera den genom att tilldela en direktivkod till varje relevant direktutleveransmall. Om en direktivkod ställs in kommer systemet att söka efter platsdirektiv med direktivkod när arbete genereras. På detta sätt kan du begränsa platsdirektiv som används för en viss direktleveransmall.

    - **Validera tidsfönster:** *Ja*

        Det här alternativet anger om det maximala tidsfönstret ska utvärderas när en leveranskälla väljs. Om det här alternativet är inställt på *Ja* blir fälten som är relaterade till den maximala och minsta tidsfönstret tillgängliga.

    - **Maximalt tidsfönster:** *5*

        Detta fält definierar den maximala perioden som är tillåten mellan leveransankomst och efterfrågeutförsel.

    - **Enheten maximalt tidsfönster:** *Dagar*
    - **Minsta tidsfönster:** *0*

        Detta fält definierar den minimala perioden som är tillåten mellan leveransankomst och efterfrågeutförsel.

    - **Enheten minimalt tidsfönster:** *Dagar*
    - **Intervall med förfallodagar:** *0*

        *FEFO-kriterier (först utgått, först ut):* Det här fältet definierar det maximala antalet dagar mellan utgångsdatumet för den första utgående batch som för närvarande finns i lagerstället och den batch som inlevereras.

1. På snabbfliken **Leveranskällor** anger du vilka typer av leveranser som är giltiga för den här mallen. Välj **ny** och ange sedan följande värden:

    - **Löpnummer:** *1*
    - **Leveranskälla:** *inköpsorder*

> [!NOTE]
> Du kan konfigurera en frågeställning för att kontrollera när en specifik direktleveransmall används. Frågan för direktleveransmallar har bara *inventTable*-registret (artiklar) och den inre sammanfogade tabellen *WHSInventTable* (WMS-artiklar). Om du vill lägga till andra register i frågan kan du sammanfoga dem genom att bara använda *finns sammankopplingar* eller *finns inte sammankopplingar*. När du filtrerar på de sammanfogade registren hämtas en post från huvudregistret för varje matchande post i det sammanfogade registret. Om sammanslagningstypen är *finns sammanslagning* avslutas sökningen efter att den första matchningen har hittats. Om du till exempel sammanfogar registret för försäljningsorderraden till registret för artiklar validerar och returnerar systemet artiklar för vilka minst en försäljningsorderrad har det definierade villkoret. Data hämtas i praktiken från det överordnade (artikel) registret och inte från det underordnade registret (försäljningsorderraden). Därför går det inte att från början filtrera efter källdokument som försäljningsorderrader eller kunder.

### <a name="create-a-work-class"></a>Skapa en arbetsklass

1. Gå till **Warehouse management \> Inställningar \> Arbete \> Arbetsklasser**.
1. I åtgärdsfönstret, välj **Ny** för att skapa en arbetsklass.
1. Ange följande värden.

    - **Arbetsklass-ID:** *CrossDock*
    - **Beskrivning:** *Direktleverans*
    - **Typ av arbetsorder:** *direktleverans*

### <a name="create-a-work-template"></a>Skapa en arbetsuppgiftsmall

1. Gå till **Lagerstyrning \> Inställningar \> Arbete \> Arbetsmallar**.
1. Ange fältet **Inköpsordertyp** till *Direktleverans*.
1. I åtgärdsfönstret, välj **Ny** om du vill lägga till en rad i fliken **Översikt**.
1. Ställ in följande värden på denna nya rad:

    - **Löpnummer:** *1*
    - **Arbetsmall:** *51 direktleverans*
    - **Beskrivning av arbetsmall:** *51 direktleverans*

1. Välj **Spara** om du vill göra snabbfliken **Arbetsmallinformation** tillgänglig.
1. På snabbfliken **Arbetsmallinformation** välj **Ny** för att lägga till en rad i rutnätet.
1. Ställ in följande värden på denna nya rad:

    - **Arbetstyp:** *plockning*
    - **Arbetsklass-ID:** *CrossDock*

1. Välj **Ny** för att lägga till en till rad och konfigurera följande värden på den:

    - **Arbetstyp:** *Placera*
    - **Arbetsklass-ID:** *CrossDock*

1. Välj **Spara** och bekräfta att kryssrutan **Giltig** är markerad för mallen *51 direktleverans*.
1. Valfritt: Välj **Redigera fråga** för att konfigurera kriterier som ska styra när och var arbetsmallen används.

    Du kan konfigurera en frågeställning för att kontrollera när en specifik arbetsuppgiftsmall används. Du kan till exempel ange att en mall bara kan användas för arbete på en viss plats. Om du vill att arbetsuppgiftsmallen för direktleveransen ska användas på en viss plats måste du filtrera fältet **Startplats**, inte fältet **Plats**, eftersom skapa arbetsuppgift för inkommande processerna (inköp, direktleverans och lagerpåfyllnad) börjar från placeringsraden. När arbetsuppgift skapas anger platsdirektivet i fältet **Plats** placeringsplats. Plockplatsen lagras dock i fältet **Startplats**.

> [!NOTE]
> Arbetsklass-ID för arbetstyperna *Plocka* och *Placera* måste vara samma.

### <a name="create-location-directives"></a>Skapa platsdirektiv

1. Gå till **Lagerstyrning \> Inställningar \> Platsdirektiv**.
1. I vänster ruta ange fältet **Arbetsordertyp** till *Direktleverans*.
1. I åtgärdsfönstret, välj **ny** och ange sedan följande värden:

    - **Löpnummer:** *1*
    - **Namn:** *51 direktleverans*
    - **Arbetstyp:** *Placera*
    - **Plats:** *5*
    - **Lagerställe:** *51*

1. Välj **Spara** om du vill göra snabbfliken **Rader** tillgänglig.
1. På snabbfliken **Rader** välj **Ny** för att lägga till en rad i rutnätet.
1. Ställ in följande värden på denna nya rad:

    - **Från kvantitet:** *1*
    - **Till kvantitet:** *1000000*

1. Välj **Spara** om du vill göra snabbfliken **Platsdirektivåtgärd** tillgänglig.
1. På snabbfliken **Platsdirektivåtgärder** välj **Ny** för att lägga till en rad i rutnätet.
1. Ställ in följande värden på denna nya rad:

    - **Namn:** *Baydoor*
    - **Användning av fast lagerplats:** *Fasta och ej fasta platser*

1. Välj **Spara** så att knappen **Redigera fråga** i verktygsfältet **Platsdirektivåtgärder** är tillgänglig.
1. Välj **Redigera fråga** för att öppna frågeredigeraren.
1. På fliken **Intervall** ser du till att följande två rader har konfigurerats:

    - Rad 1:

        - **Register:** *platser*
        - **Härlett register:** *platser*
        - **Fält:** *lagerställe*
        - **Kriterier:** *51*

    - Rad 2:

        - **Register:** *platser*
        - **Härlett register:** *platser*
        - **Fält:** *Plats*
        - **Kriterier:** *Baydoor*

1. Stäng frågeredigeraren genom att välja **OK**.

### <a name="create-a-mobile-device-menu-item"></a>Skapa ett menykommando för mobila enheter

1. Gå till **Lagerstyrning \> Inställningar \> Mobil enhet \> Menyalternativ på mobil enhet**.
1. I listan över menyalternativ i det vänstra fönstret väljer du **inköpsartikelinförsel**.
1. Välj **Redigera**.
1. På snabbfliken **Arbetsklasser** välj **Ny** för att lägga till en rad i rutnätet.
1. Ställ in följande värden på denna nya rad:

    - **Arbetsklass-ID:** *CrossDock*
    - **Typ av arbetsorder:** *direktleverans*

1. Välj **Spara**.

## <a name="scenario"></a>Scenario

### <a name="create-a-purchase-order"></a>Skapa en inköpsorder

Följ stegen nedan när du vill skapa en inköpsorder som leveranskälla.

1. Gå till **Anskaffning och källa \> Inköpsorder \> Alla inköpsorder**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. I dialogrutan **Skapa inköpsorder** ställ in följande värden:

    - **Leverantörskonto:** *104*
    - **Lagerställe:** *51*

1. Välj **OK** och anteckna ordernumret.
1. En ny rad läggs till i rutnätet på snabbfliken **Inköpsorderrader**. Ställ in följande värden på denna rad:

    - **Artikelnummer:** *A0001*
    - **Kvantitet:** *5*

### <a name="create-a-sales-order"></a>Skapa en försäljningsorder

Följ stegen nedan när du vill skapa en försäljningsorder som behovskälla.

1. Gå till **Försäljning och marknadsföring \> Försäljningsorder \> Alla försäljningsorder**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. I dialogrutan **Skapa försäljningsorder** ställ in följande värden:

    - **Kundkonto:** *US-002*
    - **Lagerställe:** *51*

1. Välj **OK**.
1. En ny rad läggs till i rutnätet på snabbfliken **Försäljningsorderrader**. Ställ in följande värden på denna rad:

    - **Artikelnummer:** *A0001*
    - **Kvantitet:** *3*

### <a name="create-planned-cross-docking"></a>Skapa planerad direktleverans

Följ dessa steg för att skapa den planerade direktleveransen från försäljningsordern.

1. På sidan **försäljningsorderinformation** för försäljningsordern som du just skapat, i åtgärdsfönstret på fliken **Lagerställe** i gruppen **Åtgärder** väljer du **Frisläpp till lager**.

    Åtgärden frisläpp till lager skapar en leverans- och lastrad för försäljningsorderraden och försöker allokera lager.
    
    Du får ett informativt meddelande. Följande varningsmeddelande visas också: "inget arbete har skapats för påfyllnad XXXX. Mer information finns i loggen över arbetsskapande." Det här beteendet förväntas eftersom det inte finns något lager i lagerstället.

1. På snabbfliken **Försäljningsorderrader** i menyn **Lagerställe** välj **Leveransinformation**.

    Sidan **Leveransinformation** visas och visar den leverans som har skapats för försäljningsordern.

1. På snabbfliken **Lastrader** ser du att fältet **Kvantitet i planerad direktleverans** har värdet *3*. Eftersom det inte fanns något lager tillgängligt i lagerstället, men en giltig leveranskälla kommer in inom tidsfönstret som definieras i mallen för direktleverans, skapades kvantiteten för direktleverans.
1. På snabbfliken **Lastrader** välj **Planerad direktleverans** om du vill visa information om direktleverans som har skapats.

## <a name="process-the-cross-docking"></a>Bearbeta direktleverans.

### <a name="purchase-order-receiving-on-the-warehousing-mobile-app"></a>Inleverans av inköpsorder med mobilappen för lagerhantering

Kvantiteten för 5 tas emot från inköpsordern till mottagningsplatsen och två arbetsuppgifter skapas.

Det första arbets-ID som skapas har värdet **Arbetsordertyp** för *Direktleverans* och är kopplat till försäljningsordern. Den har kvantiteten 3 och dirigeras till den slutgiltiga leveransplatsen så att den kan skickas direkt.

Det andra arbets-ID som skapas har värdet **Arbetsordertyp** för *Inköpsorder* och är kopplat till inköpsordern. Den innehåller den återstående kvantiteten 2 som inte har direktlevereras och dirigeras till artikelinförseln till lagret.

1. Logga in på den mobila enheten för en användare i lager ställe *51*.
1. Gå till **inkommande \> inleverans av inköp**.
1. I fältet **PONum** anger du inköpsordernummer.
1. I fältet **Kvt**, ange *5*.
1. Välj **OK**.
1. På nästa sida anger du fältet **artikel** till *A0001*.
1. Välj **OK**.
1. På nästa sida bekräfta värdena **PONum**, **Artikel** och **Kvt** genom att klicka på **OK**.

    Du får ett meddelande arbetet är slutfört.

1. Välj **avbryt** för att avsluta.

### <a name="put-away-to-cross-docking-and-bulk"></a>Artikelinförsel till direktleverans och bulk

För närvarande har båda arbets-ID:n samma ID-nummer. För att slutföra de kommande stegen måste du ha arbets-ID:t och målnummer-ID. Den här informationen kan du få från arbetsuppgifterna för inköpsorderraden och försäljningsorderraden. Du kan också gå till information om **Lagerstyrning \> Arbete \> Arbetsinformation** och filtrera fram det arbete där värde **Lagerstället** är *51*.

1. Gå till den mobila enheten **Inkommande \> Inköpsartikelinförsel** och ange målnummer-ID från arbetet.
1. I fältet **ID** ange målnummer-ID från arbetsinformationen.

    Plocksidan för direktleverans visar plockplatsen (*RECV*), målnummer-ID (*ID-nummer*), artikel (*A0001*) och kvantitet (*3*).

1. Välj **OK**.
1. I fältet **Mål LP** anger du en målnummer-ID för det licensserver-ID som ska placeras (direktlevereras) på leveransplatsen. Du kan välja valfritt ID-nummer.
1. Välj **OK**.
1. På nästa sida i fältet **ID** ange målnummer-ID.
1. Välj **OK**.
1. Bekräfta arbetet för plockning av resterande kvantitet av 2 och klicka sedan på **OK**.
1. På nästa sida väljer **Klar** för att avsluta plockningsprocessen och påbörjar artikelinförselprocessen.

    I mobilappen får du en plats och ett ID-nummer platta att inlagra artikeln i.

1. Bekräfta masslagringen **Placera** genom att välja **OK**.
1. På nästa sida bekräfta direktleverans **Placera** och välj **OK**.

    Du får ett meddelande arbetet är slutfört.

1. Välj **avbryt** för att avsluta.

Följande illustration visar hur det slutförda direktleveransen kan visas i Microsoft Dynamics 365 Supply Chain Management.

![Direktleveransarbete har slutförts.](media/PlannedCrossDockingWork.png "Direktleveransarbete har slutförts")


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
