---
title: Avancerad belastningsuppbyggnad under påfyllnad
description: I det här avsnittet finns information om avancerad belastningsuppbyggnad under påfyllnad, som automatiskt tilldelar försändelser till befintliga påfyllnader under påfyllnadskörning. Därför kan du skapa meningsfulla laster som representerar truckar utan att behöva använda workbench för lastplanering.
author: mirzaab
manager: AnnBe
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: a4d331e08af75347ed2dbc3dd777c79961de48a4
ms.sourcegitcommit: a7a7303004620d2e9cef0642b16d89163911dbb4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/01/2020
ms.locfileid: "3530522"
---
# <a name="advanced-load-building-during-wave"></a>Avancerad belastningsuppbyggnad under påfyllnad

[!include [banner](../includes/banner.md)]

Avancerad belastningsuppbyggnad under påfyllnad, som automatiskt tilldelar försändelser till befintliga påfyllnader under påfyllnadskörning. Därför kan du skapa meningsfulla laster som representerar truckar utan att behöva använda workbench för lastplanering. Den här funktionen är användbar för företag som vill använda begreppet last för att spåra och planera godstransporter på en lastbil/släpfordon, men som inte vill skapa dessa laster varje dag manuellt.

Under en påfyllnadsbearbetning skapar systemet vanligtvis en ny beläggning för varje försändelse som ingen last tilldelas till. När avancerad avancerad belastningsuppbyggnad under påfyllnad är aktiverad tilldelar dock systemet varje otilldelad leverans till en befintlig last (om en lämplig last finns) och nya laster skapas endast när de behövs. Avancerad belastningsuppbyggnad under påfyllnad skapar automatiskt nya laster, baserat på de kriterier du definierar.

Om du vill använda funktionen måste du ställa in systemet på följande sätt:

- Skapa *påfyllnadsmallar* som innehåller den nya **buildLoads**-metoden. Den här metoden gör avancerad belastningsuppbyggnad under påfyllnad tillgänglig för påfyllnader som använder dessa mallar.
- Konfigurera *mallar för belastningsuppbyggnad*, som var och en är kopplad till en viss påfyllnadsmall och -metod. Mallar för belastningsuppbyggnad styr vilken belastning (befintlig eller ny) som används för att lägga till de lastrader som används för påfyllnad. Du kan ha kombinerade eller separata försändelser, baserat på kriterier som t.ex. lastmall, utrustning och andra fältvärden på lastraden.
- Definiera *grupper med blandad last* för att kontrollera vilka artiklar som ska och inte ska kombineras i en enda last. Du anger också om begränsningen ska generera en varning eller ett fel, och om begränsningen för lastmallens volym ska utvärderas.

## <a name="turn-on-advanced-wave-load-building-in-your-system"></a>Aktivera avancerad på belastningsuppbyggnad i systemet

Innan du kan använda avancerad belastningsuppbyggnad måste du aktivera två funktioner i systemet. Administratörer kan använda inställningarna [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera status för dessa funktioner och aktivera dem om de behövs. I arbetsytan **utgiftshantering** anges den här funktionen på följande sätt:

- Funktion för belastningsuppbyggnad under påfyllnad:

    - **Modul:** *Lagerstyrning*
    - **Funktionsnamn:** *Funktion för belastningsuppbyggnad under påfyllnad*

- Påfyllnadsstegkod för hela organisationen:

    - **Modul:** *Lagerstyrning*
    - **Funktionsnamn:** *Påfyllnadsstegkod för hela organisationen*

### <a name="make-sample-data-available"></a>Gör exempeldata tillgängliga

Om du vill arbeta genom denna demo med hjälp av de exempelposter och värden som anges här måste du använda ett system där standard [demodata](../../fin-ops-core/dev-itpro/deployment/deploy-demo-environment.md) har installerats. Dessutom måste du välja den **USMF** juridiska personen innan du börjar.

Du kan också använda denna demo som vägledning för funktionen när du arbetar med ett produktionssystem. I så fall måste du emellertid ersätta dina egna värden och du kanske saknar vissa typer av obligatoriska poster som används i standard demodata.

### <a name="make-sure-that-the-scenario-setup-includes-enough-available-inventory"></a>Kontrollera att scenarioinställningen innehåller tillräckligt med tillgängligt lager

Om du arbetar med **USMF** demodata, bör du först se till att ditt system är konfigurerat så att tillräckligt med lager finns tillgängliga på varje relevant plats. I den här demon är det förväntat att du har följande lager tillgängligt på lagerställe *62*:

- **Artikel A0001:** 10 stycken
- **Artikel A0002:** 10 stycken
- **Artikel M9200:** 10 ea

Artikel **M9200** måste läggas till i lagerstället. Lägg till artikellagret genom att följa procedurerna i följande underavsnitt.

#### <a name="create-a-new-license-plate-id"></a>Skapa ett nytt ID-nummer

1. Gå till **Lagerstyrning** \> **Inställningar** \> **Lagerställe** \> **ID-nummer**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. På den nya raden i **Licensplatta** ange *LP6203*.
1. Välj **Spara**.

#### <a name="create-a-standard-cost-for-item-m9200-in-site-6"></a>Skapa en standardkostnad för artikel M9200 på plats 6

1. Gå till **Produktinformationshantering** \> **Produkter** \> **Frisläppta produkter**.
1. Sök på **M9200**.
1. Välj raden för artikeln och sedan, på fliken **Hantera kostnader** i **Ställ in** välj **Artikelpris**.
1. På sida **Artikelpris** välj fliken **Väntande priserna**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. Ställ in följande värden på denna nya rad:

    - **Kostnadstyp:** *Planerad kostnad*
    - **Pristyp:** *Kostnad*
    - **Version:** *10*
    - **Plats:** *6*
    - **Pris:** *1,60*

1. Klicka på **Spara** i åtgärdsfönstret.
1. I åtgärdsfönstret, välj **Aktivera väntande priser**.
1. Välj fliken **Aktiva priser** om du vill verifiera att den nya självkostnaden för webbplatsen *6* har lagts till.

#### <a name="create-inventory-in-warehouse-62"></a>Skapa inventering i ett lagerställe 62

1. Gå till **Lagerhantering** \> **Journalposter** \> **Artiklar** \> **Lagerjustering**.
1. Klicka på **Ny** i åtgärdsfönstret.
1. I dialogrutan **Skapa lagerjournal** på snabbfliken **Översikt** i fältet **Lagerställe** ange *62*. Acceptera standardvärden i alla andra fält.
1. Välj **OK** för att stänga dialogrutan.
1. Sidan **Jagerjustering** har öppnats. På snabbfliken **Journalrader**, klicka på **Ny** för att lägga till en rad.
1. Ställ in följande värden på denna nya rad. Acceptera standardvärden i alla andra fält.

    - **Artikelnummer:** *M9200*
    - **Plats:** *bulk-003*
    - **Kvantitet:** Ändra värdet till *10*.

1. Klicka på **Spara** i åtgärdsfönstret.
1. I åtgärdsfönstret väljer du **Validera** om du vill söka efter fel.
1. I dialogrutan **Kontrollera journal** väljer du **OK** för att starta kontrollen. Ett meddelande visas när checken är slutförd.
1. I åtgärdsfönstret, välj **Bokför** för att genomföra lagerjusteringen.
1. I dialogrutan **Bokför journal** väljer du **OK** för att starta bokföringen. Ett meddelande visas när bokföringen är slutförd.

## <a name="set-up-advanced-wave-load-building"></a>Ställ upp avancerad belastningsuppbyggnad under påfyllnad

### <a name="regenerate-wave-process-methods"></a>Återskapa metoder för påfyllnadsprocesser

Du måste kanske återskapa dina metoder för påfyllnadsprocess för att göra belastningsuppbyggnadsmetoden (**buildLoads**) tillgänglig.

1. Gå till **Lagerstyrning** \> **Inställningar** \> **Påfyllnader** \> **Metoder för påfyllnadsprocess**.
2. Kontrollera att **buildLoads** finns i listan. Om den inte finns med väljer du **återskapa metoder** i åtgärdsfönstret för att lägga till den.

### <a name="set-up-wave-templates"></a>Ställa in påfyllnadsmallar

Om du vill utnyttja avancerad belastningsuppbyggnad under påfyllnad måste du inkludera **buildLoads**-metoden i varje relevant [påfyllnadsmall](tasks/configure-wave-processing.md).

1. Gå till **Lagerstyrning** \> **Inställningar** \> **Påfyllnader** \> **Påfyllnadsmallar**.
1. Välja en påfyllnadsmall.

    Om du arbetar med **USMF** demodata väljer du mallen **Standardleverans för 62**.

1. I åtgärdsfönstret, välj **Redigera** för att placera sidan i redigeringsläge.
1. På snabbfliken **Metoder** i rutnätet **återstående metoder**, välj metoden **buildLoads**.
1. Välj höger knapp för att flytta metoden **buildLoads** på rutnätet **Valda metoder**.
1. Om du vill tilldela ett värde **Kod för påfyllnadssteg** för metoden **buildLoads** måste du först skapa en kod på sidan **Koder för påfyllnadssteg**. Du kan använda vilket värde du vill, men glöm inte att anteckna det eftersom du kommer att behöva det senare. Följ dessa steg för att skapa koden **WSC2112**:

    1. I raden för metoden **buildLoads**, högerklicka på nedpilen i fältet **Kod för påfyllnadssteg** och välj sedan **Visa information**.
    1. På sidan **Koder för påfyllnadssteg** i åtgärdssfönstret väljer du **Ny**.
    1. I fältet **Kod för påfyllnadssteg**, ange *WSC2112*.
    1. I fältet **Beskrivning för påfyllnadssteg**, ange *WSC2112*.
    1. I fältet **Typ av påfyllnadssteg** väljer du *Lastuppbyggnad*.

1. Markera **Spara** och stäng sedan sidan.
1. På raden för metoden **buildLoads** i fältet **Kod för påfyllnadssteg** den kod som du just har skapat (**WSC2112**).
1. Klicka på **Spara** i åtgärdsfönstret.

> [!NOTE]
> Koder för påfyllnadssteg är koder som användarna kan ställa in och använda för att länka specifika förekomster av påfyllnadsmetoder till en motsvarande mallar. Mallarna innehåller mallar för påfyllning, skapande av behållare, etikettutskrift, lastuppbyggnad och sortering.
>
> När koder för påfyllnadssteg inte används måste användarna ange fritext för att referera till en specifik mall från förekomst av påfyllnadsmetod. Fritext är benägen att bli fel, eftersom användare måste se till att påfyllnadsstegets text de lägger till för en specifik påfyllnadsstegmetoden i en vågmall exakt matchar påfyllnadsstegtexten i målmallen.
>
> Påfyllnadskoderna för en viss typ av påfyllnadsstegtyp ställs in på en separat sida. För varje instans av påfyllnadsstegmetod i en påfyllnadsmall som kräver en kod för påfyllnadssteg, måste koden för påfyllnadssteg väljas i en nedrullningsbar lista. Markeringen i en nedrullningsbar lista ersätter text som är fritext och minskar risken och konsekvenserna av det mänskliga felet. Inställningskoder används för att koppla en påfyllnadsstegmetod i en påfyllnadsmall till en målmall för metoden.

### <a name="set-up-load-mix-groups"></a>Ställ in grupper med blandad last

grupper med blandad last skapar regler för de typer av artiklar som kan kombineras i en enda last. Du kan ställa in så många grupper med blandad last, som du behöver. Om du vill använda avancerad belastningsuppbyggnad måste du dock ha minst en. Följ dessa steg om du vill skapa grupp med blandad last.

1. Gå till **Lagerstyrning** \> **Inställningar** \> **Last** \> **Grupper med blandad last**.
1. I åtgärdsfönstret, välj **Ny** för att skapa en lastgrupp.
1. I fältet **ID för grupp med blandad last** ange ett namn för den nya gruppen.

    Om du arbetar med **USMF** demodata ange följande värden:

    - **ID för grupp med blandad last:** *TV*
    - **Beskrivning:** *TV*

1. I åtgärdsfönstret, välj **Spara** för att göra snabbfliken **Kriterium för grupp med blandad last** tillgänglig.
1. På snabbfliken **Kriterium för grupp med blandad last** väljer du **Ny** för att lägga till en rad i rutnätet.
1. Ange önskade värden i varje fält i den nya raden. Dessa värden bestämmer vilka artikelgrupper som tas med i lastblandningen.

    Om du arbetar med **USMF** demodata väljer du *TV&Video* i fältet **artikelgrupp**.

1. I åtgärdsfönstret, välj **Spara** för att göra snabbfliken **Begränsningar för grupp med blandad last** tillgänglig.
1. På snabbfliken **Begränsningar för grupp med blandad last** väljer du **Ny** för att lägga till en rad i rutnätet.
1. Ange önskade värden i varje fält i den nya raden.

    Om du arbetar med **USMF** demodata ange följande värden:

    - **Artikelgrupp:** *CarAudio*
    - **Lastuppbyggnadsåtgärd:** *Begränsa* (Detta värde förhindrar objekt som tillhör artikelgrupp **CarAudio** från att vara på samma last som artiklar som hör till artikelgruppen **TV&Video**.)

1. Fortsätt att arbeta med reglerna tills du har lagt till alla kriterier och begränsningar som krävs för den grupp med blandad last.

Om du arbetar med **USMF** demodata har du nu avslutat den här inställningen.

### <a name="set-up-load-build-templates"></a>Konfigurera mallar för belastningsuppbyggnad

Du kan ställa in så många mallar för belastningsuppbyggnad, som du behöver. Om du vill använda avancerad belastningsuppbyggnad måste du dock ha minst en. Följ dessa steg om du vill skapa en mall för belastningsuppbyggnad.

1. Gå till **Lagerstyrning** \> **Inställningar** \> **Last** \> **Belastningsuppbyggnad under påfyllnad**.
1. I åtgärdsfönstret, välj **Ny** du vill lägga till en rad i rutnätet.
1. I den nya raden anger du följande värden.

    | Fält | beskrivning | Värde i USMF-demodata |
    |---|---|---|
    | Sekvensnummer | Den ordning som mallen ska utvärderas i. | *1* |
    | Lastuppbyggnadens mallnamn | Ange den unika identifieraren av lastuppbyggnadsmallen. Ange namnet på mallen som du skapade eller uppdaterade tidigare i den här inställningen. | *Standardleverans 62* |
    | Kod för påfyllnadssteg | Ange påfyllnadsstegkod som ska användas för att länka mallen till en vågmetod. Du bör ange koden som du har valt för metoden **buildLoads** när du ställer in påfyllnadsmallen tidigare i den här inställningen. | *WSC2112* |
    | Lastmall-ID | Välj den lastmall som används när du skapar nya laster och att matcha mot när du tilldelar befintliga laster. I lastmallen definieras den maximala vikt och volym som tillåts för hela lasten. | *Standardlastmall* |
    | Utrustning | Utrustningen att matcha mot när du tilldelar befintliga laster och att ange nya laster som skapas. | Lämna det här fältet tomt. |
    | ID för grupp med blandad last | Välj den grupp med blandad last som används om artikeln är tillåtet på lasten. Blandade gruppen skapar regler för de typer av artiklar som kan kombineras i en enda last. Markera en av de blandade grupper som du skapade tidigare i den här inställningen. | *TV* |
    | Använd öppna laster | Välj om befintliga öppna laster också läggas till. Följande alternativ är tillgängliga:<ul><li>**Ingen** – Lägg inte till öppna laster till befintliga laster.</li><li>**Alla** – Lägg till öppna laster till alla befintliga laster som gäller för raden.</li><li>**Tilldelad** – Lägg till öppna laster till den last som är tilldelad till påfyllnad.</li></ul> | *Valfritt* |
    | Skapa laster | Ange om nya laster ska skapas om ingen befintlig last matchar kriterierna. | Markerad (= *Ja*) |
    | Tillåt delning av leveransrad | Ange om en enda lastrad kan delas mellan flera laster, om den fullständiga raden överstiger maximumkapaciteten för lastmallen. | Reglerat (= *Nej*) |
    | Validera volymmetriker | Ange om lastuppbyggnaden bör kontrollerar vikten och volymen när varje lastrad läggs till för att säkerställa att lastmallens volymetriska gränser respekteras. | Reglerat (= *Nej*) |

1. I åtgärdsfönstret väljer du **Spara** om du vill göra alternativet **Redigera fråga** tillgängligt.
1. I åtgärdsfönstret, välj **Redigera fråga** för att öppna en dialogruta för att redigera frågan.
1. I dialogrutan på fliken **Sortering** väljer du **Lägg till** om du vill lägga till en rad i rutnätet.
1. Definiera de sorteringsregler som du vill använda på den nya raden. Ange till exempel följande värden för att sortera sökresultaten i stigande ordning efter ordernummer:

    - **Register:** *Lastinformation*
    - **Härlett register:** *Lastinformation*
    - **Fält:** *Ordernummer*
    - **Sökriktning:** *Stigande*

1. Välj **OK** om du vill spara dina ändringar fråga och stänga dialogrutan.
1. På snabbfliken **Dela efter** anger du regler som styr hur dina laster delas upp. Vanligtvis kan du dela på anpassade fält som har förlängts på lastraden, t.ex. **flöde**, **visning** eller **körning**. Om du till exempel vill skapa en last per ordernummer markerar du kryssrutan **Dela efter** för den rad som har följande värden:

    - **Referensregisternamn:** *Lastinformation*
    - **Namn på referensfält:** *Ordernummer*

## <a name="scenario"></a>Scenario

Det här scenariot visar hur inställningarna som beskrevs tidigare i det här avsnittet påverkar lageroperationer medan en försäljningsorder bearbetas. I det här scenariot används **USMF** demodata tillsammans med andra demovärden som finns i dessa installationsanvisningar.

### <a name="create-sales-orders"></a>Skapa försäljningsorder

1. Gå till **Försäljning och marknadsföring** \> **Försäljningsorder** \> **Alla försäljningsorder**.
1. I åtgärdsfönstret välj **Ny** om du vill öppna dialogrutan **Skapa försäljningsorder**.
1. Ange följande värden i dialogrutan:

    - På snabbfliken **Kund** ställer du in fältet **Kundkonto** på *US-007*.
    - På snabbfliken **Allmänt** anger du fältet **Lagerställe** till *62*.

1. Välj **OK** för att skapa den försäljningsordern och stänga dialogrutan.
1. Den nya försäljningsordern öppnas. Detta bör innehålla en ny tom rad i rutnätet på snabbfliken **försäljningsorderrader**. På den nya raden anger du fältet **Artikelnummer** till *A0001* och fältet **Kvantitet** till *1*.
1. I menyn **Lager** ovanför rutnätet, välj **Reservation**.
1. På sidan **Reservation** i åtgärdssfönstret väljer du **Reservera parti**.
1. Välj knappen **Stäng** (**X**) överst till höger på sidan för att återgå till försäljningsordern.
1. I åtgärdsfönstret **Lagerställe**, flik **åtgärder**, välj **Släpp till lagerställe**. Systemet skapar en försändelse och lägger till den i en ny last, eftersom ingen befintlig last innehåller lastrader som har det här ordernumret.

    Du får informationsmeddelanden som anger vilket arbete, vilken påfyllnad och vilket leverans som skapas för den här ordern.

1. Bekräfta informationen om last, leverans och arbete på försäljningsraden genom att markera raden och sedan välja menyn **Lagerställe** ovanför rutnätet, välj **Lastinformation**, **Leveransinformation** eller **Arbetsinformation**.
1. I försäljningsordern som du just skapat på snabbfliken **Försäljningsorderrader** väljer du **Lägg till rad** om du vill lägga till ytterligare en rad.
1. På den nya raden anger du fältet **Artikelnummer** till *A0002* och fältet **Kvantitet** till *1*.
1. Upprepa raderna 6 till 9 om du vill reservera raden och släppa den på lagerstället. En **ny** leverans skapas för raden som du har lagt till i systemet. Eftersom du använder avancerad belastningsuppbyggnad under påfyllnad lägger systemet dock till leverans- och lastraden för den befintliga påfyllnaden. Om du inte använder avancerad belastningsuppbyggnad under påfyllnad skulle systemet skapa en ny last för leveransen.
1. I försäljningsordern som du just skapat på snabbfliken **Försäljningsorderrader** väljer du **Lägg till rad** om du vill lägga till ytterligare en rad.
1. På den nya raden anger du fältet **Artikelnummer** till *M9200* och fältet **Kvantitet** till *1*.
1. Upprepa raderna 6 till 9 om du vill reservera raden och släppa den på lagerstället. Som tidigare skapar systemet en **ny** leverans för raden som du har lagt till. Eftersom artikeln kommer från artikelgruppen **CarAudio** kommer den att **misslyckas med att klara de begränsningar som du ställer in för grupp med blandad last**. Därför **läggs det till i en ny last**. Om du inte hade angett en grupp med blandad last i lastuppbyggnadsmallen skulle denna leverans ha lagts till i den första lasten.
