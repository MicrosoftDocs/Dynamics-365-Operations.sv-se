---
title: Flexibel reservationspolicy för dimension på lagernivå
description: I det här avsnittet beskrivs den reservationspolicy för lager som gör det möjligt för företag att sälja batchspårade produkter och köra sin logistik som WMS-aktiverade operationer reservera specifika batchar för kundförsäljningsorder, även om den reservationssekvens som är kopplad till produkterna inte tillåter reservation av specifika batchar.
author: omulvad
manager: tfehr
ms.date: 02/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSReservationHierarchy
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2020-01-15
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: 0fe9ed9f2bebe8683f3b8bb37b33e8a63b9521f6
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3205677"
---
# <a name="flexible-warehouse-level-dimension-reservation-policy"></a>Flexibel reservationspolicy för dimension på lagernivå

[!include [banner](../includes/banner.md)]

När en hierarki för lagerreservationer av typen "batch-under\[plats\]" associeras med produkter kan företag som säljer spårade produkter och kör sin logistik när operationer som har aktiverats för Microsoft Dynamics 365 lagerställehanteringssystem (WMS) inte kan reservera specifika partier för dessa produkter för kundförsäljningsorder. I det här avsnittet beskrivs den reservationspolicy för lager som gör det möjligt för dessa företag att reservera specifika batchar, även om produkterna är kopplade till reservationshierarkin "Batch-under\[plats\]".

## <a name="inventory-reservation-hierarchy"></a>Lagerreservationshierarki

Det här avsnittet sammanfattar den befintliga lagerreservationshierarkin. Den fokuserar på hur batchspårade och seriespårade artiklar hanteras.

Lagerreservationshierarkin avgör att när det gäller lagringsdimensioner har efterfrågeordern de obligatoriska dimensionerna för plats, lager och lagerstatus, medan lagerställelogiken är ansvarig för att tilldela en plats till de begärda kvantiteterna och reservera platsen. Med andra ord förväntas en efterfrågeorder i interaktionen mellan efterfrågeorder ordern och lagerställeåtgärder för att ange var ordern måste levereras från (dvs. vilken plats och lagerställe). Lagerstället använder sig av sin logik för att hitta den begärda kvantiteten i dessa lagerlokaler.

Om du vill återspegla affärsverksamhetens driftsmodell, kan spårningsdimensioner (batch- och serienummer) bli mer flexibla. En hierarki för lagerreservationer kan innehålla scenarier där följande villkor gäller:

- Företaget använder sina lageroperationer för att hantera plockning av kvantiteter som har batch- eller serienummer efter det att kvantiteterna har hittats i lagringsutrymmet på lagringsplatsen. Den här modellen kallas ofta för en *Batch-under\[plats\]*. Den används vanligtvis när en produkts batch- eller serienummer-ID inte är viktig för de kunder som gör efterfrågan från det säljande företaget.
- Om batch- eller serienummer är en del av en kundsorderspecifikation och registreras på efterfrågeorder, begränsas lageroperationerna som hittar kvantiteterna i lagerstället till de specifika nummer som krävs och tillåts inte att ändra dem. Den här modellen kallas en *Batch-ovan\[plats\]*.

I dessa scenarier är utmaningen att bara en hierarki med lagerreservationer kan tilldelas varje frisläppt produkt. För att WMS ska hantera spårade objekt, efter att hierarkitilldelningen bestämmer när batch- eller serienumret ska reserveras (antingen när efterfrågan beställs eller under lagerplockningsarbetet), kan denna timing inte ändras på ad-hoc-basis.

## <a name="flexible-reservation-for-batch-tracked-items"></a>Flexibel reservation för batchspårade artiklar

### <a name="business-scenario"></a>Affärsscenario

I det här scenariot använder ett företag en lagerstrategi där färdiga varor spåras efter batchnummer. Det här företaget använder också WMS-arbetsbelastning. Eftersom den här arbetsbelastningen har en välutrustad logik för planering och transport av lagerplocknings- och leveransoperationer för batchaktiverade artiklar, associeras de flesta av de färdiga artiklarna med en batch-under\[plats\] lagerreservationshierarki. Fördelen med den här typen av driftsinställningar är att beslut (som är effektiva reservationsbeslut) om vilka batchar som ska plockas och var de ska skjutas upp tills lagerplockningsoperationer har startat. De görs inte när kundens order har placerats.

Även om reservationshierarkin "batch-under\[plats\]" "betjänar företagets affärsmål", kräver många av företagets etablerade kunder samma batch som de tidigare köpte när de beställer om produkter. Därför söker företaget efter flexibilitet på det sätt som reglerna för batchreservation hanteras, så att, beroende på kundernas efterfrågan för samma artikel, uppstår följande problem.

- Ett batchnummer kan registreras och reserveras när ordern görs av försäljningsbehandlaren och kan inte ändras under lageroperationer och/eller tas av andra behov. Det här beteendet garanterar att det batchnummer som beställs levereras till kunden.
- Om batchnumret inte är viktigt för kunden, kan lageroperationerna bestämma ett batchnummer under plockningsarbetet efter att registrering och reservation av försäljningsordern har utförts.

### <a name="allowing-reservation-of-a-specific-batch-on-the-sales-order"></a>Tillåta reservation av en specifik batch på försäljningsordern

För att tillgodose önskad flexibilitet i batchreservationens beteende för artiklar som är associerade med en "Batch-under\[plats\]" lagerreservationshierarki måste chefer markera kryssrutan **Tillåt reservation av efterfrågeorder** för nivån **Batch-nummer** på sidan **lagerreservationshierarkier**.

![Göra lagerreservationshierarkin flexibel](media/Flexible-inventory-reservation-hierarchy.png)

När nivån **Batch-nummer** i hierarkin väljs kommer alla dimensioner över den nivån och upp till nivån **plats** att väljas automatiskt. (Som standard är alla dimensioner ovanför nivån **plats** förvalda.) Det här beteendet återspeglar logiken där alla dimensioner i intervallet mellan batchnumret och lagerstället också reserveras automatiskt när du har reserverat ett specifikt batchnummer på orderraden.

> [!NOTE]
> Kryssrutan **Tillåt reservation på efterfrågerorder** gäller bara för de nivåer för reservationshierarkier som ligger under dimensionen lagerställe.
>
> **Batchnummer** är den enda nivå i hierarkin som är öppen för den flexibla reservationsprincipen. Med andra ord kan du inte markera kryssrutan **Tillåt reservation på efterfrågeorder** för nivån **plats**, **ID-nummer** eller **serienummer**.
>
> Om din reservationshierarki innehåller dimensionen för serienummer (som alltid måste vara under nivån **Batch-nummer**), och om du har aktiverat batch-specifik reservation för batch-numret kommer systemet att fortsätta hantera reservations- och plockningsoperationer för serienummer baserat på de regler som gäller för reservationsprincipen "Serie-under\[plats\]".

Du kan när som helst tillåta batch-specifik reservation för en befintlig "batch-under\[plats\]" reservationshierarki i distributionen. Den här ändringen påverkar inte reservationer och öppna jobb i lagerställe som har skapats innan ändringen gjordes. Men kryssrutan **Tillåt reservation på efterfrågeorder** kan inte vara avmarkerad om lagertransaktioner för utleveranstyper **Reserverat beställt**, **Fysiskt reserverat** eller **Beställt** finns för en eller flera artiklar som är associerade med den reservationshierarkin.

> [!NOTE]
> Om en artikels befintliga reservationshierarki inte tillåter kommandospecifikation på ordern kan du tilldela om den till en reservationshierarki som tillåter batch-specifikation, förutsatt att hierarkinivåstrukturen är densamma i båda hierarkierna. Använd funktionen **ändra reservationshierarki för artiklar** för att utföra omtilldelningen. Den här ändringen kan vara relevant när du vill förhindra flexibel batch-reservation för en delmängd av batch-spårade artiklar, men tillåter den för resten av produktportföljen.

Oavsett om du har markerat kryssrutan **Tillåt reservation på efterfrågeorder** om du inte vill reservera ett specifikt batchnummer för artikeln på en orderrad, gäller standardoperationslogiken för lagerställe som är giltig för en "Batch-under\[location\]" reservationhierarkin.

### <a name="reserve-a-specific-batch-number-for-a-customer-order"></a>Reservera ett specifikt batchnummer för en kundorder

När en batch-spårad artikels "Batch-under\[plats\]" lagerreservationshierarki har ställts in för att tillåta reservation av specifika batchnummer på försäljningsorder, kan behandlare av försäljningsorder ta kundorder för samma artikel på något av följande sätt, beroende på kundens begäran:

- **Ange orderdetaljer utan att ange ett batchnummer** – det här tillvägagångssättet ska användas när produktens batch-specifikation inte är viktig för kunden. Alla befintliga processer som associeras med hantering av en order av den här typen i systemet förblir oförändradet. Det behövs ingen ytterligare hänsyn till användarna.
- **Ange orderdetaljer och reservera ett specifikt batchnummer** – den här metoden bör användas när kunden begär en specifik batch. Vanligtvis begär kunder en särskild batch när de ombeställer en produkt som de tidigare har köpt. Denna typ av batch-specifik reservation kallas för *orderallokerad reservation*.

Följande regler gäller när kvantiteter bearbetas och ett batchnummer allokeras till en specifik order:

- Om du vill tillåta reservation av ett specifikt batchnummer för en artikel under reservationsprincipen "Batch-under\[plats\]" måste systemet reservera alla dimensioner via platsen. I detta intervall ingår vanligtvis dimensionen registreringsskylt.
- Platsdirektiv används inte när plockningsarbete skapas för en försäljningsrad som använder orderallokerad batch-reservation.
- Under lagerbearbetning av arbete för orderallokerade batchar, tillåts varken användaren eller systemet att ändra batchnumret. (Bearbetningen omfattar undantagshantering.)

I följande exempel visas ett komplett flöde.

## <a name="example-scenario"></a>Exempelscenario

För det här exemplet måste demonstrationsdata vara installerade och du måste använda **USMF**-demodataföretaget.

### <a name="set-up-an-inventory-reservation-hierarchy-to-allow-batch-specific-reservation"></a>Ställ in en hierarki för lagerreservationer för att tillåta batch-specifika reservationer

1. Gå till **Lagerstyrning** \> **Inställningar** \> **Lager \> Reservationshierarki**.
2. Välj **Ny**.
3. I fältet **Namn** anger du ett namn (till exempel **BatchFlex**).
4. I fältet **Beskrivning** anger du en beskrivning (till exempel, **Batch under flexibel**).
5. I fältet **Valda** väljer du **Serienummer** och **Ägare** och väljer sedan vänsterpilen för att flytta dem till fältet **Tillgängliga**.
6. Välj **OK**.
7. I raden för dimensionsnivån **Batch-nummer** markera kryssrutan **Tillåt reservation på efterfrågeorder**. Nivåerna **Registreringsskylt** och **Plats** markeras automatiskt och du kan inte avmarkera kryssrutorna för dem.
8. Välj **Spara**.

### <a name="create-a-new-released-product"></a>Skapa en ny frisläppt produkt

1. Ställ in produktens tre huvuddataparametrar med hjälp av dessa värden:

    - I fältet **lagringsdimensionsgrupp** välj **Ware**.
    - I fältet **spårningsdimensionsgrupp** välj **Batch-Phy**.
    - I fältet **Reservationshierarki** välj **BatchFlex**.

2. Skapa två batchnummer, t.ex. **B11** och **B22**.
3. Lägg till artikelkvantiteter i lagerbehållning med hjälp av följande värden.

    | Distributionslager | Batchnummer | Plats | ID-nummer | Antal |
    |-----------|--------------|----------|---------------|----------|
    | 24        | B11          | BULK-001 | Ingen          | 10       |
    | 24        | B11          | FL-001   | LP11          | 10       |
    | 24        | B22          | FL-002   | LP22          | 10       |

### <a name="enter-sales-order-details"></a>Ange försäljningsorderinformation

1. Gå till **Försäljning och marknadsföring** \> **Försäljningsorder** \> **Alla försäljningsorder**.
2. Välj **Ny**.
3. I försäljningsorderns rubrik, i fältet **Kundkonto** ange **US-003**.
4. Lägg till en rad för den nya artikeln och ange **10** som kvantitet. Se till att fältet **Lagerställe** anges till **24**.
5. På snabbfliken **försäljningsorderrader** välj **lager** och sedan i gruppen **underhåll** välj **Batch-reservation**. Sidan **Batch-reservation** visar en lista över batchar som är tillgängliga för reservation för orderraden. I det här exemplet visas ett antal på **20** för batchnummer **B11** och kvantiteten **10** för batchnummer **B22**. Observera att du inte kan komma åt sidan **Batch-reservation** från en rad om den raden är associerad med "Batch-under\[plats\]" reservationshierarki om den inte har ställts in för att tillåta batch-specifik reservation.

    > [!NOTE]
    > Om du vill reservera en specifik batch för en försäljningsorder måste du använda sidan **Batch-reservation**.
    >
    > Om du anger batchnumret direkt på försäljningsorderraden, kommer systemet att fungera som om du har angett ett specifikt batchvärde för ett objekt som omfattas av "Batch-under\[plats\]" reservationspolicy. När du sparar raden visas ett varningsmeddelande. Om du bekräftar att batchnumret ska anges direkt på orderraden hanteras inte raden av den normala lagerstyrningslogiken.
    >
    > Om du reserverar kvantiteten från sidan **Reservation** kommer ingen specifik batch att reserveras och körningen av lagerställeoperationer för raden följer reglerna som är tillämpliga under reservationspolicyn "Batch-under\[plats\]".

    Den här sidan fungerar vanligtvis på samma sätt och interagerar med artiklar som har en associerad reservationssekvens för typen "Batch-ovan\[plats\]". Följande undantag gäller emellertid:

    - Snabbfliken **batchnummer för källrad** visar de batchnummer som har reserverats för orderraden. Batchvärdet i rutnätet visas under hela orderradens uppfyllandecykel, inklusive faserna för lagerbearbetning. På snabbfliken **översikt** visas däremot en reservation på ordinarie orderrad (dvs. reservation som görs för dimensionerna över nivån **plats**) i rutnätet upp till punkten när lagerarbete skapas. Arbetsenheten tar över radreservationen och radreservationen visas inte längre på sidan. Snabbfliken **batchnummer för källrader** används för att garantera att försäljningsorderns handläggare kan visa de batchnummer som har utfästs till kundens order när som helst under livscykeln, upp till fakturering.
    - Förutom att reservera en viss batch kan han eller hon manuellt välja batchens specifika plats och licensskylt i stället för att låta systemet automatiskt välja dem. Denna kapacitet är relaterad till designen av mekanismen för orderallokerad batch-reservation. Som nämnts tidigare, när ett specifikt batchnummer reserveras för en artikel under reservationsprincipen "Batch-under\[plats\]" måste systemet reservera alla dimensioner via platsen. Därför kommer lagerstället att ha samma lagringsdimensioner som har reserverats av de användare som arbetade med ordern, och den kanske inte alltid representerar den placering av artikellagring som är praktiskt eller till och med möjlig för plockningsoperationer. Om orderhandläggarna känner till begränsningarna i lagerställena, kanske de vill välja de specifika platserna och licensskyltarna manuellt när de reserverar en batch. I det här fallet måste användaren använda funktionen för **visningsdimensioner** i sidhuvudet och måste lägga till platsen och licensskylten i rutnätet på snabbfliken **översikt**.

6. På sidan **Batch-reservation** välj raden för batch **B11** och välj sedan **reservera rad**. Det finns ingen särskild logik för att tilldela platser och licensskyltarna vid automatisk reservation. Du kan ange kvantiteten manuellt i fältet **reservation**. Observera att snabbfliken **batchnummer för källrad**, batch **B11** visas som **utfäst**.

    ![Utfästa ett specifikt batchnummer på en försäljningsorderrad på sidan batch-reservation](media/Batch-reservation-form-with-order-committed-reservation.png)

    > [!NOTE]
    > Det går att utföra reservationer av kvantiteten på en försäljningsorderrad i flera batchar. På samma sätt kan reservation av samma batch göras mot flera platser och licensskyltar (om licensskyltar är aktiverade för platserna).
    >
    > Reservation av en specifik batch för kvantiteten på en försäljningsorderrad kan också vara del. Den totala kvantiteten 100 enheter kan till exempel reserveras så att en specifik batch har allokerats till 20 enheter, medan 80 enheter reserveras på platsen och lagerställenivåer för någon tillgänglig batch. I det här fallet hanterar WMS plockningsoperationer med hjälp av två separata arbetsrader.

7. Gå till **Produktinformationshantering** \> **Produkter** \> **Frisläppta produkter**. Markera artikeln och välj sedan **hantera lager** \> **visa** \> **transaktioner**.

    ![Order-allokerad reservation som en lagertransaktionstyp](media/Inventory-transactions-for-order-committed-reservation.png)

8. Granska artikelns lagertransaktioner som hör till försäljningsorderradens reservation.

    - En transaktion där fältet **Referens** anges till **Försäljningsorder** och fältet **Ärende** anges till **Fysiskt reserverat** representerar orderradreservationen för lagerdimensionerna ovanför nivå **Plats**. Enligt artikelns hierarki för lagerreservationer är dessa dimensioner plats, lagerställe och lagerstatus.
    - En transaktion där fältet**Referens** anges till **Orderallokerad reservation** och fältet **Ärende** anges till **Fysiskt reserverat** representerar orderradreservationen för den specifika batchen och alla lagerdimensioner ovanför. Enligt artikelns hierarki för lagerreservationer är dessa dimensioner batch-nummer och plats. I det här exemplet är platsen **Bulk-001**.

9. Välj i försäljningsorderhuvudet **Lagerställe** \> **Åtgärder** \> **Släpp till lagerställe**. Orderraden är nu vågad och en last och ett arbete skapas.

### <a name="review-and-process-warehouse-work-that-has-order-committed-batch-numbers"></a>Granska och bearbeta lageställearbete som har orderallokerade batchnummer

1. På snabbfliken **Försäljningsorderrader** välj **Lagerställe** \> **Arbetsdetaljer**.

    Det arbete som hanterar plockoperationen för batchkvantiteter som har bekräftats till försäljningsorderraden har följande egenskaper:

    - Om du vill skapa arbete använder systemet arbetsmallar men inte platsdirektiv. Alla standardinställningar som definieras för arbetsmallar, t.ex. ett maximalt antal plockningsrader eller en specifik måttenhet, används för att bestämma när nytt arbete ska skapas. Reglerna som är kopplade till platsdirektiv för identifiering av plockningsplatser beaktas dock inte eftersom den order som genomförts redan anger alla lagerdimensioner. Dessa lagerdimensioner inkluderar dimensionerna på lagerställets lagernivå. Därför ärver arbetet dessa dimensioner utan att behöva konsultera platsdirektiv.
    - Batchnumret visas inte på plockningsraden (som är fallet för den arbetsrad som skapas för en artikel som har en motsvarande "batch-ovan\[plats\]" reservationshierarki.) I stället visas batchnummer från och alla andra lagringsdimensioner på arbetsradens jobblagertransaktion som refereras från de associerade lagertransaktionerna.

        ![Lagerställets lagertransaktion för arbete som härrör från en reservation som har genomförts av order](media/Work-inventory-transactions-for-order-committed-reservation.png)

    - När arbetet har skapats är artikelns lagertransaktion där fältet **Referens** är inställt på **Order-allokerad reservation** borttagen. Lagertransaktionen där fältet **Referens** anges till **Arbete** innehåller nu den fysiska reservationen på alla lagerdimensionerna för kvantiteten.

        Lageroperationer kan fortsätta för att hantera utförande av arbetet på vanligt sätt. Men instruktionerna på den mobila enheten instruerar arbetaren att välja ett specifikt batchnummer. I lagermiljöer där platser är registreringsskylt – styrs efter att en arbetare har nått en plats som lagrar samma batch på registreringsskyltar, kan han eller hon välja från alla registreringsskyltar som inte redan har reserverats (t.ex. av en annan order-allokerad reservation eller arbete som härrör från en reservation av den typen.)

        Om det blir opraktiskt att plocka från den plats som anges på arbetsraden, kan lagerställets operatörer använda någon av följande åtgärder för att dirigera om plockning av en viss batch:

        - Standard är åtgärden **åsidosätta plats** på en mobil enhet (förutsatt att inställningen för lagerarbetare **Tillåt åsidosättning av plockplats** är aktiverad)
        - Åtgärden **ändra plats** på sidan **information om arbetslista**. 

2. Slutför plockningen på den mobila enheten och sätt in arbetet.

    Kvantiteten **10** för batchnummer **B11** har nu plockats för försäljningsorderraden och placerats på platsen **Baydoor**. I detta skede är den klar att lastas på lastbilen och skickas till kundens adress.

## <a name="exception-handling-of-warehouse-work-thas-has-order-committed-batch-numbers"></a>Hantering av undantag av lageställearbete som har orderallokerade batchnummer

Orderallokerade batchnummer för lagerarbete för plockning är underställt samma standardundantagshantering och åtgärder för lagerställe som normalt arbete. I allmänhet kan öppna arbete eller arbetsrad avbrytas, den kan avbrytas eftersom en användarplats är full, det kan tas bort och kan uppdateras på grund av en rörelse. På samma sätt kan plockad kvantitet av arbete som redan har slutförts minskas, eller så kan arbetet återföras.

Följande nyckelregel används för alla dessa undantagsåtgärder: det batchnummer som har reserverats för kunden kan aldrig ersättas med ett annat batchnummer, men dess lagringsdimensioner (plats och registreringsskylt) kan ändras genom antingen manuell uppdatering av användaren eller automatiska uppdateringar i systemet. Den automatiska uppdateringen baseras på samma slumpmässiga tilldelning av lagringsdimensioner som används när en specifik batch automatiskt reserverades men inga lagringsdimensioner har angetts.

### <a name="example-scenario"></a>Exempelscenario

Ett exempel på det här scenariot är en situation där arbetet med tidigare slutfört arbete avbryts med funktionen **minska plockad kvantitet**. I det här exemplet fortsätter det föregående exemplet i det här avsnittet.

1. Gå till **Lagerstyrning** \> **Laster** \> **Aktiva laster**.
2. Välj den last som skapades i samband med leveransen av din försäljningsorder.
3. På snabbfliken **Läs in orderrader** väljer du **minska plockad kvantitet**.
4. På sidan **minska plockad kvantitet** i fältet **Flytta till plats** väljer du **FL-001**.
5. I fältet **Flytta till registreringsskylt** väljer du **LP33**.
6. I rutnätet skriver du **Lagerkvantitet där plockning ska hävas** anger du **10**.
7. Välj **OK**.

Här är resultaten av åtgärden för ej plockning:

- Status för det tidigare avslutade arbetet är inställd på **annullerat**.
- Nytt arbete för typen **lagerrörelse** skapas för det ej plockade antalet **10** för batchnummer **B11**. Det här arbetet motsvarar flyttningen från platsen **Baydoor** till registreringsskylten **LP33** på plats **FL-001**. Status är inställt på **Stängd**.
- Systemet omreserverar batchnumret som ursprungligen beställdes och tilldelar plats- och registreingsskylt-ID. (Den här processen motsvarar att köra funktionen **reservera rad** för orderraden för ett givet batchnummer). Som ett resultat visas batch **B11** som genomförd på snabbfliken **batchnummer för källrad** på sidan **Batch-reservation** och fältet **Reservation** innehåller antalet **10** för batchnummer **B11**. Dessutom är fältet **plats** inställt **FL-001** och fältet **registreringsskylt** är inställt på **LP11**. (Du kan lägga till dessa fält i rutnätet om de inte visas.)

Följande register ger en översikt som visar hur systemet hanterar den beställda batchreservationen för specifika lageråtgärder. Om du vill tolka innehållet i tabellerna antar du att varje lageråtgärd körs i samband med befintligt lagerarbete som har sitt ursprung i en batchorder som har genomförts med order, eller att körningen av varje lageråtgärd påverkar arbete av den typen.

> [!NOTE]
> I dessa register visar kolumnen "Batchkvantitet är tillgänglig" om en batchkvantitet är tillgänglig utöver kvantiteten som antingen redan har reserverats för den aktuella orderallokerade reservationen eller redan har reserverats för det lagerställearbete som härstammar från reservationer av den typen.

#### <a name="override-the-pick-location-on-the-open-work"></a>Åsidosätt plockplatsen på det öppna arbetet

<table>
<thead>
<tr>
<th>Viktig inställningsparameter</th>
<th>Batchkvantitet är tillgänglig</th>
<th>Viktiga användarsteg</th>
<th>Lagerarbete</th>
<th>Orderallokerad batchreservation</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'>Alternativet <strong>Tillåt åsidosättning av plockplats</strong> är aktiverat för arbetaren.</td>
<td>Ja</td>
<td>
<ol>
<li>Välj menyalternativ <strong>Åsidosätt plats</strong> på lagerapp för mobil (WMA) när du startar plockningsarbete.</li>
<li>Välj <strong>föreslå</strong>.</li>
<li>Bekräfta den nya platsen som föreslås baserat på tillgängligheten för batchkvantitet.</li>
</ol>
</td>
<td>I det aktuella arbetet inträffar följande åtgärder:
<ul>
<li>Platsen på plockraden uppdateras till den nya platsen. (Om platsen är registreringsskyltkontrollerad, tilldelas en slumpmässig registreringsskylt till arbetslagertransaktionen och arbetaren kan välja från registreringsskylt som har den tillgängliga kvantiteten.)</li>
<li>Om kvantiteten finns på fler än en registreringsskylt på den nya platsen, delas den ursprungliga plockningsraden på flera rader för att matcha varje registreringsskylt.</li>
</ul>
</td>
<td>Inte aktuellt</td>
</tr>
<tr>
<td>Nej</td>
<td>
<ol>
<li>Välj menyalternativ <strong>Åsidosätt plats</strong> på WMA när du startar plockningsarbete.</li>
<li>Ange en plats manuellt.</li>
</ol>
</td>
<td>Åtgärden <strong>åsidosätta plats</strong> är inte möjlig. Den misslyckas och ett fel genereras.</td>
<td>Inte aktuellt</td>
</tr>
</tbody>
</table>

#### <a name="full-button--split-a-work-line-because-of-overflow-on-the-user-location"></a>Full knapp – dela en arbetsrad på grund av spill på användarplatsen

<table>
<thead>
<tr>
<th>Viktig inställningsparameter</th>
<th>Batchkvantitet är tillgänglig</th>
<th>Viktiga användarsteg</th>
<th>Lagerarbete</th>
<th>Orderallokerad batchreservation</th>
</tr>
</thead>
<tbody>
<tr>
<td>Alternativet <strong>Tillåt delning av arbete</strong> är aktiverat på menyalternativet för mobil enhet.</td>
<td>Inte aktuellt</td>
<td>
<ol>
<li>Välj menyalternativ <strong>Full</strong> på WMA när du bearbetar plockningsarbete.</li>
<li>I fältet <strong>Plockkvantitet</strong> ange den delkvantitet för att ange den fullständiga kapaciteten.</li>
</ol>
</td>
<td>
<ul>
<li>I det aktuella arbetet uppdateras kvantiteten till den resterande kvantiteten som måste plockas.</li>
<li>Nytt arbete för plockad kvantitet skapas och stängs.</li>
</ul></td>
<td>Inte aktuellt</td>
</tr>
</tbody>
</table>

#### <a name="reduce-the-picked-quantity-of-completed-work-from-a-load"></a>Minska den plockade kvantiteten färdigt arbete (från en last)

<table>
<thead>
<tr>
<th>Viktig inställningsparameter</th>
<th>Batchkvantitet är tillgänglig</th>
<th>Viktiga användarsteg</th>
<th>Lagerarbete</th>
<th>Orderallokerad batchreservation</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'>Inte aktuellt</td>
<td>Ja</td>
<td>
<ol>
<li>Öppna sidan <strong>minska plockad kvantitet</strong> kvantitet från lastraden.</li>
<li>Ange den fulla kvantitet att häva plockning.</li>
<li>Välj en "flytta till" plats/registreringsskylt.</li>
</ol>
</td>
<td>
<ul> 
<li>Arbete som är kopplat till lastraden avbryts.</li>
<li>Nytt arbete för lagerrrörelse skapas och stängs.</li>
</ul>
</td>
<td>Kvantiteten har reserverats för samma batch. Systemet tilldelar slumpmässigt en plats och registreringsskylt (om platsen är registreringsskyltkontrollerad) där kvantiteten är tillgänglig.</td>
</tr>
<tr>
<td>Nej</td>
<td>Se föregående rad.</td>
<td>Se föregående rad.</td>
<td>Kvantiteten reserveras för samma batch och för samma plats och registreringsskylt (om platsen är registreringsskyltkontrollerad) som angavs under hävning av plockningen.</td>
</tr>
</tbody>
</table>

#### <a name="move-an-item-within-a-warehouse"></a>Flytta en artikel inom ett lagerställe

> [!NOTE]
> Den här lageråtgärden kan bara användas i rörelse av typen **Process för att skapa arbete**, inte för rörelse per mall.

<table>
<thead>
<tr>
<th>Viktig inställningsparameter</th>
<th>Batchkvantitet är tillgänglig</th>
<th>Viktiga användarsteg</th>
<th>Lagerarbete</th>
<th>Orderallokerad batchreservation</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'>Alternativet <strong>Tillåt flyttning av lager med associerat arbete</strong> är aktiverat för arbetaren.</td>
<td>Ja</td>
<td>
<ol>
<li>Starta en rörelse på WMA.</li>
<li>Ange "från-" och "till"-platser.</li>
</ol></td>
<td>
<ul>
<li>För allt befintligt arbete som påverkas av flyttningen uppdateras plockplatsen till den nya "till"-platsen.</li>
<li>Nytt arbete för lagerrrörelse skapas och stängs.</li>
</ul>
</td>
<td>Alla befintliga reservationer som påverkas av flyttningen av kvantiteten från den angivna platsen reserveras för samma batch. Systemet tilldelar slumpmässigt en plats och registreringsskylt (om platsen är registreringsskyltkontrollerad) där kvantiteten är tillgänglig.</td>
</tr>
<tr>
<td>Nej</td>
<td>Se föregående rad.</td>
<td>Se föregående rad.</td>
<td>Alla befintliga reservationer som påverkas av antalet transporter från den angivna platsen reserveras för samma batch och för den nya "till"-platsen och registreringsskylten (om platsen är registreringsskyltkontrollerad).</td>
</tr>
</tbody>
</table>

#### <a name="reverse-the-picked-quantity-of-completed-work-from-a-load-or-a-wave"></a>Återför den plockade kvantiteten färdigt arbete (från en last eller en påfyllnad)

<table>
<thead>
<tr>
<th>Viktig inställningsparameter</th>
<th>Batchkvantitet är tillgänglig</th>
<th>Viktiga användarsteg</th>
<th>Lagerarbete</th>
<th>Orderallokerad batchreservation</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='6'>Inte aktuellt</td>
<td>Ja</td>
<td>
<ol>
<li>Öppna sidan <strong>Återför arbete</strong>.</li>
<li>Välj alternativet <strong>Lämna artiklar på aktuell plats</strong> på sidan begäran.</li>
</ol>
</td>
<td>Allt arbete som är kopplat till lasten avbryts.</td>
<td>Kvantiteten har reserverats för samma batch. Systemet tilldelar slumpmässigt en plats och registreringsskylt (om platsen är registreringsskyltkontrollerad) där kvantiteten är tillgänglig.</td>
</tr>
<tr>
<td>Nej</td>
<td>Se föregående rad.</td>
<td>Se föregående rad.</td>
<td>Kvantiteten omreserveras för samma batch och för plats- och registreringsskylten där kvantiteten lämnades vid återföring.</td>
</tr>
<tr>
<td>Ja</td>
<td>
<ol>
<li>Öppna sidan <strong>Återför arbete</strong>.</li>
<li>Välj alternativet <strong>Tilldela artiklar till denna plats</strong> på sidan begäran.</li>
</ol>
</td>
<td>
<ul>
<li>Aktuellt arbete är annullerat.</li>
<li>Nytt arbete för lagerrrörelse skapas och stängs.</li>
</ul>
</td>
<td>Kvantiteten har reserverats för samma batch. Systemet tilldelar slumpmässigt en plats och registreringsskylt (om platsen är registreringsskyltkontrollerad) där kvantiteten är tillgänglig.</td>
</tr>
<tr>
<td>Nej</td>
<td>Se föregående rad.</td>
<td>Se föregående rad.</td>
<td>Kvantiteten omreserveras för samma batch och för plats- och registreringsskylten där kvantiteten tilldelades till vid återföring.</td>
</tr>
<tr>
<td>Ja/Nej</td>
<td>
<ol>
<li>Öppna sidan <strong>Återför arbete</strong>.</li>
<li>Välj alternativet <strong>Flytta artiklar till denna plats</strong> på sidan begäran.</li>
</ol>
</td>
<td>Återföring stöds inte.</td>
<td>Inte aktuellt</td>
</tr>
<tr>
<td>Ja/Nej</td>
<td>
<ol>
<li>Öppna sidan <strong>Återför arbete</strong>.</li>
<li>Välj alternativet <strong>Flytta artiklar baserat på platsdirektiv</strong> på sidan begäran.</li>
</ol>
</td>
<td>Återföring stöds inte. </td>
<td>Inte aktuellt</td>
</tr>
</tbody>
</table>

#### <a name="short-pick-a-quantity--register-the-quantity-as-physically-not-found-at-the-locationlicense-plate-while-you-perform-picking-work"></a>Kort plockning av en kvantitet – registrera kvantiteten som fysiskt inte finns på plats/registreringsskylt medan du utför plockningsarbete

<table>
<thead>
<tr>
<th>Viktig inställningsparameter</th>
<th>Batchkvantitet är tillgänglig</th>
<th>Viktiga användarsteg</th>
<th>Lagerarbete</th>
<th>Orderallokerad batchreservation</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'>Ett arbetsundantag från typen <strong>Kort plockning</strong> konfigureras där <strong>Omallokering av artikel</strong> = <strong>Ingen</strong>, <strong>Justera lager</strong> = <strong>Ja</strong> och <strong>Ta bort reservationer</strong> = <strong>Nej</strong>.</td>
<td>Ja</td>
<td>
<ol>
<li>Välj menyalternativ <strong>Kort plockning</strong> på WMA när du kör plockningsarbete.</li>
<li>I fältet <strong>Plockkvantitet</strong>, ange <strong>0</strong> (noll).</li>
<li>I fältet <strong>Orsak</strong> anger du <strong>Ingen omallokering</strong>.</li>
</ol>
</td>
<td>
<ul>
<li>Det aktuella arbetet är stängt och plockad kvantitet är 0 (noll).</li>
<li>En lagertransaktion av typen <strong>Inventering</strong> och utleveranstypen <strong>Såld</strong> skapas som representerar justeringen.</li>
</ul>
</td>
<td>Kvantiteten har reserverats för samma batch. Systemet tilldelar slumpmässigt en plats och registreringsskylt (om platsen är registreringsskyltkontrollerad) där kvantiteten är tillgänglig.</td>
</tr>
<tr>
<td>Nej</td>
<td>Se föregående rad.</td>
<td>
<ul>
<li>Den korta plock åtgärden misslyckas och ett fel genereras.</li>
<li>Det aktuella arbetet förblir öppet.</li>
</ul>
</td>
<td>Inte aktuellt</td>
</tr>
<tr>
<td rowspan='2'>Ett arbetsundantag från typen <strong>Kort plockning</strong> konfigureras där <strong>Omallokering av artikel</strong> = <strong>Ingen</strong>, <strong>Justera lager</strong> = <strong>Ja</strong> och <strong>Ta bort reservationer</strong> = <strong>Ja</strong>.</td>
<td>Ja</td>
<td>
<ol>
<li>Välj menyalternativ <strong>Kort plockning</strong> på WMA när du kör plockningsarbete.</li>
<li>I fältet <strong>Plockkvantitet</strong>, ange <strong>0</strong> (noll).</li>
<li>I fältet <strong>Orsak</strong> anger du <strong>Ingen omallokering</strong>.</li>
</ol>
</td>
<td>
<ul>
<li>Det aktuella arbetet är stängt och plockad kvantitet är 0 (noll).</li>
<li>En lagertransaktion av typen <strong>Inventering</strong> och utleveranstypen <strong>Såld</strong> skapas som representerar justeringen.</li>
</ul>
</td>
<td>Alla befintliga reservationer som påverkas av justering av kvantiteten från den kort plockade platsen reserveras för samma batch. Systemet tilldelar slumpmässigt en plats och registreringsskylt (om platsen är registreringsskyltkontrollerad) där kvantiteten är tillgänglig.</td>
</tr>
<tr>
<td>Nej</td>
<td>Se föregående rad.</td>
<td>Se föregående rad.</td>
<td>Alla befintliga reservationer som påverkas av justering av kvantiteten från den kort plockade platsen tas bort.</td>
</tr>
<tr>
<td>Ett arbetsundantag från typen <strong>Kort plockning</strong> konfigureras där <strong>Omallokering av artikel</strong> = <strong>Manuell</strong>, <strong>Justera lager</strong> = <strong>Ja</strong> och <strong>Ta bort reservationer</strong> = <strong>Nej/Ja</strong>. Dessutom är alternativet <strong>Tillåt omfördelning av artikel</strong> aktiverat för arbetaren.</td>
<td>Ja</td>
<td>
<ol>
<li>Välj menyalternativ <strong>Kort plockning</strong> på WMA när du kör plockningsarbete.</li>
<li>I fältet <strong>Kort plockkvantitet</strong>, ange <strong>0</strong> (noll).</li>
<li>I fältet <strong>orsak</strong> väljer du <strong>Kort plockning med manuell omallokering</strong>.</li>
<li>Välj plats/registreringsskylt i listan.</li>
</ol>
</td>
<td>
<ul>
<li>I det aktuella arbetet inträffar följande åtgärder:
<ul>
<li>Plockraden är stängd och plockad kvantitet är 0 (noll).</li>
<li>Placeringsraden har annullerats.</li>
<li>En ny plockrad har skapats. Den använder den plats/registreringsskylt som användaren har valt.</li>
<li>En ny placeringsrad har skapats.</li>
</ul>
</li>
<li>En lagertransaktion av typen <strong>Inventering</strong> och utleveranstypen <strong>Såld</strong> skapas som representerar justeringen.</li>
</ul>
</td>
<td>Inte aktuellt</td>
</tr>
<tr>
<td>Ett arbetsundantag från typen <strong>Kort plockning</strong> konfigureras där <strong>Omallokering av artikel</strong> = <strong>Manuell</strong>, <strong>Justera lager</strong> = <strong>Ja</strong> och <strong>Ta bort reservationer</strong> = <strong>Nej</strong>. Dessutom är alternativet <strong>Tillåt omfördelning av artikel</strong> aktiverat för arbetaren.</td>
<td>Nej</td>
<td>
<ol>
<li>Välj menyalternativ <strong>Kort plockning</strong> på WMA när du kör plockningsarbete.</li>
<li>I fältet <strong>Kort plockkvantitet</strong>, ange <strong>0</strong> (noll).</li>
<li>I fältet <strong>orsak</strong> väljer du <strong>Kort plockning med manuell omallokering</strong>.</li>
</ol>
</td>
<td>Den korta plock åtgärden misslyckas och ett fel genereras.</td>
<td>Inte aktuellt</td>
</tr>
<tr>
<td>Ett arbetsundantag från typen <strong>Kort plockning</strong> konfigureras där <strong>Omallokering av artikel</strong> = <strong>Manuell</strong>, <strong>Justera lager</strong> = <strong>Ja</strong> och <strong>Ta bort reservationer</strong> = <strong>Ja</strong>. Dessutom är alternativet <strong>Tillåt omfördelning av artikel</strong> aktiverat för arbetaren.</td>
<td>Nej</td>
<td>
<ol>
<li>Välj menyalternativ <strong>Kort plockning</strong> på WMA när du kör plockningsarbete.</li>
<li>I fältet <strong>Kort plockkvantitet</strong>, ange <strong>0</strong> (noll).</li>
<li>I fältet <strong>orsak</strong> väljer du <strong>Kort plockning med manuell omallokering</strong>.</li>
<li>Välj plats/registreringsskylt i listan.</li>
</ol>
</td>
<td>
<ul>
<li>I det aktuella arbetet inträffar följande åtgärder:
<ul>
<li>Plockraden är stängd och plockad kvantitet är 0 (noll).</li>
<li>Placeringsraden har annullerats.</li>
</ul>
</li>
<li>En lagertransaktion av typen <strong>Inventering</strong> och utleveranstypen <strong>Såld</strong> skapas som representerar justeringen.</li>
</ul>
</td>
<td>Alla befintliga reservationer som påverkas av justering av kvantiteten från den kort plockade platsen/registreringsskylten tas bort.</td>
</tr>
<tr>
<td>Ett arbetsundantag från typen <strong>Kort plockning</strong> konfigureras där <strong>Omallokering av artikel</strong> = <strong>Automatisk</strong>, <strong>Justera lager</strong> = <strong>Ja/Nej</strong> och <strong>Ta bort reservationer</strong> = <strong>Ja/Nej</strong>.</td>
<td>Inte aktuellt</td>
<td>
<ol>
<li>Välj menyalternativ <strong>Kort plockning</strong> på WMA när du kör plockningsarbete.</li>
<li>I fältet <strong>Kort plockkvantitet</strong>, ange <strong>0</strong> (noll).</li>
<li>I fältet <strong>orsak</strong> väljer du <strong>Kort plockning med automatisk omallokering</strong>.</li>
</ol>
</td>
<td>Korta plockningar som inbegriper automatisk omfördelning stöds inte.</td>
<td>Korta plockningar som inbegriper automatisk omfördelning stöds inte.</td>
</tr>
</tbody>
</table>

#### <a name="change-the-inventory-status"></a>Ändra lagerstatus

> [!NOTE]
> Den här lageråtgärden kan utföras från flera startpunkter. I exemplet som visas här används åtgärden **Ändring av lagerstatus** på sidan **Behållning efter plats**.

<table>
<thead>
<tr>
<th>Viktig inställningsparameter</th>
<th>Batchkvantitet är tillgänglig</th>
<th>Viktiga användarsteg</th>
<th>Lagerarbete</th>
<th>Orderallokerad batchreservation</th>
</tr>
</thead>
<tbody>
<tr>
<td rowspan='2'>På fliken <strong>Lagerställe</strong> i posten <strong>Lagerställe</strong> är fältet <strong>ta bort reservationer och markeringar</strong> inställt på <strong>Reservationer</strong> eller <strong>Markeringar och reservationer</strong>.</td>
<td>Ja</td>
<td>
<ol>
<li>Välj en specifik plats.</li>
<li>Välj en rad som har en viss artikel, plats och registreringsskylt (om platsen är registreringsskyltkontrollerad).</li>
<li>Välj <strong>Ändring av lagerstatus</strong>.</li>
<li>Ange fältet <strong>lagerstatus</strong> till <strong>blockering</strong>.</li>
</ol>
</td>
<td>Ändringar av lagerstatus är inte tillåtna för kvantiteter som är reserverade för arbete.</td>
<td>
<ul>
<li>Kvantiteten har reserverats för samma batch. Systemet tilldelar slumpmässigt en plats och registreringsskylt (om platsen är registreringsskyltkontrollerad) där kvantiteten är tillgänglig.</li>
<li>Två lagertransaktioner av typen <strong>ändring av lagerstatus</strong> skapas för att representera ändringen i dimensionen lagerstatus.</li>
<li>En lagertransaktion av typen <strong>Lagerblockering</strong> och utleveranstypen <strong>Fysiskt reserverat</strong> skapas för att representera reservationen av den spärrade kvantiteten.</li>
</ul>
</td>
</tr>
<tr>
<td>Nej</td>
<td>Se föregående rad.</td>
<td>Ändringar av lagerstatus är inte tillåtna för kvantiteter som är reserverade för arbete.</td>
<td>
<ul>
<li>Reservationen tas bort.</li>
<li>Två lagertransaktioner av typen <strong>ändring av lagerstatus</strong> skapas för att representera ändringen i dimensionen lagerstatus.</li>
<li>En lagertransaktion av typen <strong>Lagerblockering</strong> och utleveranstypen <strong>Fysiskt reserverat</strong> skapas för att representera reservationen av den spärrade kvantiteten.</li>
</ul>
</td>
</tr>
<tr>
<td rowspan='2'>På fliken <strong>Lagerställe</strong> i posten <strong>Lagerställe</strong> anges fältet <strong>Ta bort reservationer och markeringar</strong> till <strong>Ingen</strong>.</td>
<td>Ja</td>
<td>
<ol>
<li>Välj en specifik plats.</li>
<li>Välj en rad som har en viss artikel, plats och registreringsskylt (om platsen är registreringsskyltkontrollerad).</li>
<li>Välj <strong>Ändring av lagerstatus</strong>.</li>
<li>Ange fältet <strong>lagerstatus</strong> till <strong>blockering</strong>.</li>
</ol>
</td>
<td>Ändringar av lagerstatus är inte tillåtna för kvantiteter som är reserverade för arbete.</td>
<td>Kvantiteten har reserverats för samma batch. Systemet tilldelar slumpmässigt en plats och registreringsskylt (om platsen är registreringsskyltkontrollerad) där kvantiteten är tillgänglig.</td>
</tr>
<tr>
<td>Nej</td>
<td>Se föregående rad.</td>
<td>Ändringar av lagerstatus är inte tillåtna för kvantiteter som är reserverade för arbete.</td>
<td>Ändringar i lagerstatus är inte tillåtna.</td>
</tr>
</tbody>
</table>

## <a name="limitations"></a>Begränsningar

- Den flexibla funktionen för dimensionsreservation på lagernivå stöder inte följande funktioner:

    - Hantering av fångstvikt
    - Fysiskt negativt lager
    - Reservation mot beställda leveranser
    - Överföringsorder och plockning av råmaterial

- Behållarens konsolideringsregel för paketering av direktivenhet har begränsningar. För orderallokerade reservationer rekommenderar vi att du inte använder uppbyggnadsmallar för behållare där fältet **Packa efter enhet för direktiv** är aktiverad. I den aktuella designen används inte platsdirektiv när lagerarbete skapas. Det innebär att endast den minsta enheten i enhetssekvensgruppen (lagerenheten) används under påfyllnadssteget skapande av behållare.