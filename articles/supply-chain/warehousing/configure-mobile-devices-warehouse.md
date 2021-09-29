---
title: Ställ in mobila enheter för lagerarbete
description: Det här ämnet beskriver konfiguration av menyalternativ som lagerarbetare använder för att utföra arbete på en mobil enhet.
author: MarkusFogelberg
ms.date: 03/23/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSRFMenuItem, WHSRFSysDirSort, WHSWorkUserDisplaySettings
audience: Application User
ms.reviewer: kamaybac
ms.custom: 29941
ms.assetid: 6dff6313-dc6e-4f06-9c0c-dab24eefe4da
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dee8d0962626c42ab76e908072e686cc5c0a61d1
ms.sourcegitcommit: f332cabe9d5c6ece431fd5aa06759481be53f06a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/21/2021
ms.locfileid: "7506549"
---
# <a name="set-up-mobile-devices-for-warehouse-work"></a>Ställ in mobila enheter för lagerarbete

[!include [banner](../includes/banner.md)]

Det här ämnet beskriver konfiguration av menyalternativ som lagerarbetare använder för att utföra arbete på en mobil enhet.

> [!NOTE]
> Denna artikel gäller funktioner i lagerstyrningshanteringen. Den gäller inte funktioner i Lagerhantering. Menyalternativen som visas på menyerna på en mobil enhet för lagerställe konfigureras på sidan **Menyalternativ på mobil enhet**. Eftersom menyalternativen kan sättas på olika menyer, är det enklare att konfigurera menystrukturer så att endast specifika typer av arbete visas för specifika användare. Du kan konfigurera menykommando att utföra följande uppgifter:

- Bearbeta en förfrågan eller utföra en aktivitet, som till exempel skriva ut en etikett, generera ID-nummer, starta en produktionsorder eller snabbt samla in information artiklar på en plats.
- Skapa arbete som ska utföras genom en annan process. Mottagning av en artikel för en inköpsorder kan till exempel skapa inlagrat arbete för en annan arbetstagare.
- Utför arbete som har skapats av en annan process (befintligt arbete), som till exempel inlagrat arbete som har skapats när en artikel inlevererades för en inköpsorder.

För att skapa ett menyalternativ för en aktivitet eller en förfrågan, ange fältet **Läge** som **Indirekt**. En lista alternativen för **Aktivitetskod** blir sedan tillgänglig, så att du kan välja typ av fråga eller aktivitet som menyalternativet avser. För att skapa ett menyalternativ för att generera lagerarbete, ange fältet **Läge** som **Arbete**. En lista över alternativen för **Skapandeprocess för arbete** blir sedan tillgänglig. För att skapa ett menyalternativ för att bearbeta befintliga lagerarbete konfigurerar du fältet **Metod** till **Arbete** och sedan anger du alternativet **Använd befintligt arbete** som **Ja**. 

> [!NOTE]
> Beroende på det läge som du väljer för menyalternativet och om menyalternativet används för att utföra befintligt arbete, kan det finnas ytterligare fält tillgängliga för menyalternativet. Se avsnittet ”Ytterligare menyalternativ" senare i det här avsnittet för information om ytterligare fältval.

## <a name="configure-menu-items-for-activities-and-inquiries"></a>Konfigurera menyalternativ för aktiviteter och förfrågningar

Om fältet **Metod** för ett menyalternativ anges som **Indirekt**, kan du skapa ett menyalternativ för att utföra en allmän aktivitet eller förfrågning som inte skapar arbete. Till exempel nyutskrift av registreringsskyltar och en förfrågan om artiklar på en plats. I följande tabell finns de alternativ som är tillgängliga.

| Alternativ | Beskrivning |
|---|---|
| Ingen | Detta standardvärde aktiverar inte en aktivitet eller en förfrågan. |
| Om | Visa information om systemet, som till exempel versionsnumret, lagerställe-ID:t och arbetaren som för närvarande är inloggad. |
| Byt lagerställe | Ändra det lagerställe som en arbetare är inloggad på. |
| Platsförfrågan | Visa information om alla artiklar och kvantiteter för en plats. |
| Registreringsskyltsförfrågan | Visa kvantiteten av artiklar på en registreringsskylt och platsen för registreringsskylten. |
| Starta produktionsorder | Starta en produktionsorder. |
| Produktionskassation | Ange kvantiteten av kassation som har skapats under produktionen för varje strukturlisterad. |
| Sista produktionspall | Ange att den sista lastpallen har producerats för en tillverkningsorder, och att statusen för produktionsordern måste uppdateras till **Rapporterat som färdigt**-klienten. Status för råmaterial som inte förbrukats under produktionen ändras tillbaka från **Plockat** till **Har beställts** och artiklarna kan returneras till lagret. |
| Artikelfråga | Skanna en artikel för att avgöra var den finns i lagerstället. Frågan returnerar alla platser och kvantiteter för den skannade artikeln. |
| Skriv ut etikett på nytt | Skriva ut en ID-nummeretikett igen. |
| Skapa registreringsskylt | Skapa en överordnad registreringsskylt genom att kombinera flera registreringsskyltar på samma plats. Detta alternativ är användbart om du flyttar flera registreringsskyltar samtidigt. När den överordnade registreringsskylten har tagits bort måste du utföra ett registreringsskyltsavbrott innan du kan plocka artiklar från varje registreringsskylt. <p></p>**Tips:** Om du vill flytta en överordnad registreringsskylt måste du använda en mobil enhet som har konfigurerats för att skapa arbete för förflyttningar. |
| Avbrott för registreringsskylt | Bryt upp en registreringsskyltversion, så att du kan plocka artiklar från registreringsskyltarna i den versionen. |
| Förarens incheckning | Om du använder Transporthantering ska du registrera att en förare har anlänt genom att skanna utgående last-ID, mötes-ID eller försändelse-ID. För detta alternativ krävs att en last tilldelas mötet, och att lastens status är **Lastad**. |
| Förarens utcheckning | Registrera att en förare har slutfört deras möte. |
| Rensa nummerseriecache | Ta bort nummer i nummerserie från nummerserieminnet. Denna aktivitet utförs vanligtvis av en systemadministratör för att lösa cachelagringsproblem från mobila enheter. |
| Ändra batchdisposition | Tillåt att en anställd anger en batchdispositionskod för en artikel och en batch. Detta val uppdaterar den dispositionskod som anges för batchen. |
| Visa lista över öppet arbete | Visa en lista över tillgängligt arbete till en viss användare. Användaren kan sedan välja arbetet som ska utföras och styrs mot det. Den här listan är avsedd att visas på pekplattor med skärmstorlekar på 7 tum eller mer. När du väljer det här alternativet kommer menyalternativen **Redigera fråga** och **Fältlista** blir tillgängliga. Sidan **Redigera fråga** låter dig ställa in kriterier för det arbete som visas i listan. Sidan **Fältlista** låter dig välja vilka fält som visas i arbetslistan. Du kan till exempel minska antalet fält som visas så att användaren snabbare kan välja den lämpligaste arbetsuppgiften. På snabbfliken **Allmän** i fältet **Poster per sida** kan du också välja hur många arbetsposter per sida som ska visas. Om alternativet **Tillåt användare att filtrera arbete efter transaktionstyp** är markerat, kommer arbetslistan att inkludera en **Filtrera arbete**-kontroll i arbetsuppgiftslistan, som låter användaren filtrera per transaktionstyp. I arbetslistan kommer användaren endast att se arbete som de har behörighet till. Du måste kontrollera att användarna har behörighet för en eller flera användarriktade menykommandon som stöder de specifika arbetsklasstyperna som de ska ha åtkomst till. Behörigheter kontrolleras när en användare försöker utföra arbete i listan.|
| Skapa överföringsorder från ID-nummer | Tillåter lagerarbetare att skapa och bearbeta överföringsorder direkt från mobilappen för distributionslagerhantering. Lagerarbetarna börjar med att välja destinationslager stället och kan sedan skanna en eller flera licensskyltar med hjälp av appen. När lagerarbetaren väljer **slutför order**, kommer ett batch-jobb att skapa de överföringsorder och orderrader som krävs baserat på den lagerbehållning som har registrerats för dessa registreringsskyltar. Mer information finns i [skapa överföringsorder från lagerställeapp](create-transfer-order-from-warehouse-app.md)

## <a name="configure-menu-items-to-create-work-for-another-worker-or-process"></a>Ställ in menyalternativ för att skapa arbete för en annan arbetare eller process

Du kan ställa in en menykommando som skapar arbete för en annan anställd, efter en ursprunglig åtgärden har utförts på mobila enheten. När till exempel en arbetstagare använder en mobil enhet för att ta emotå en artikel, skapas inlagrat arbete för en annan arbetstagare. Om du vill ställa in ett menyalternativ som skapar arbete, välj sidan **Menyalternativ på mobil enhet** i fältet **Metod** och sedan **Arbete**. I följande register arrangeras alternativen i fältet **Process för att skapa arbete** efter arbetsordertyp.

<table>
<tbody>
<tr>
<th>Typ av arbetsorder</th>
<th>Alternativ</th>
<th>Beskrivning</th>
</tr>
<tr>
<td rowspan="8">Inköpsorder</td>
<td>Inleverans av inköpsorderrad</td>
<td>Registrera inleverans av en kvantitet av en artikel genom att använda inköpsordernummer och inköpsorderradnumret och skapa inlagrat arbete för en annan arbetstagare.</td>
</tr>
<tr>
<td>Inköpsorderrad har inlevererats och inlagrats</td>
<td>Registrera inleverans av en kvantitet av en artikel genom att använda inköpsordernummer och inköpsorderradnumret och inlagra artiklarna. Samma arbetare utför båda åtgärder.</td>
</tr>
<tr>
<td>Inleverans av inköpsorderartikel</td>
<td>Registrera inleverans av en kvantitet av en artikel för en inköpsorder genom att registrera inköpsordernumret och artikelnumret och skapa inlagrat arbete för en annan arbetstagare.</td>
</tr>
<tr>
<td>Inleverans och inlagring av inköpsorderartikel</td>
<td>Registrera inleverans av en kvantitet av en artikel för en inköpsorder genom att registrera inköpsorderradnumret och inlagra artikeln. Samma arbetare utför båda åtgärder.</td>
</tr>
<tr>
<td>Inleverans av registreringsskylt</td>
<td>Ta emot en ingående leveransavisering (ASN) genom att använda ID-numret.</td>
</tr>
<tr>
<td>Plats och mottagning av registreringsskylt</td>
<td>Ta emot och inlagra en ingående leveransavisering (ASN) genom att använda ID-numret.</td>
</tr>
<tr>
<td>Mottagande av lastartikel</td>
<td>Registrera inleverans av en kvantitet för en last genom att använda last-ID och skapa inlagrat arbete för en annan arbetare. Artikelnumret och produktdimensionerna matchar inleveransen till inköpsorderraderna.</td>
</tr>
<tr>
<td>Mottagande och inleverans av lastartikel</td>
<td>Registrera inleverans av en last med hjälp av last-ID och inlagra artiklarna. Artikelnumret och produktdimensionerna matchar inleveransen till inköpsorderraderna. Samma arbetare utför båda åtgärder.</td>
</tr>
<tr>
<td rowspan="2">Returorder</td>
<td>Mottagande av returorder</td>
<td>Registrera inleverans av en kvantitet för en artikel genom att registrera RMA-numret och skapa inlagrat arbete för en annan arbetare.</td>
</tr>
<tr>
<td>Returorder mottagning och inleverans</td>
<td>Registrera inleverans av en kvantitet för en artikel genom att registrera RMA-numret och inlagra artiklarna. Samma arbetare utför båda åtgärder.</td>
</tr>
<tr>
<td rowspan="6">Överföringsorder</td>
<td>Mottagning överföringsorderartikel</td>
<td>Registrera inleverans av en kvantitet av en artikel genom att skapa inlagrat arbete för en annan arbetare.

<strong>Obs!</strong> Använd endast det här alternativet, om artiklarna levererats från ett lagerställe som inte har aktiverats för lagerhanteringsprocesser.</td>
</tr>
<tr>
<td>Inleverans och inlagring av överföringsorderartikel</td>
<td>Registrera inleverans av en kvantitet av en artikel och inlagra artiklarna. Samma arbetare utför båda åtgärder.

<strong>Obs!</strong> Använd endast det här alternativet, om artiklarna levererats från ett lagerställe som inte har aktiverats för lagerhanteringsprocesser.</td>
</tr>
<tr>
<td>Mottagning överföringsorderrad</td>
<td>Registrera inleverans av en kvantitet av en artikel genom att skapa inlagrat arbete för en annan arbetare.</td>
</tr>
<tr>
<td>Överför orderrad inleverans och inlagring</td>
<td>Registrera inleverans av en kvantitet av en artikel och inlagra artiklarna. Samma arbetare utför båda åtgärder.</td>
</tr>
<tr>
<td>Inleverans av registreringsskylt</td>
<td>Ta emot en ingående leveransavisering (ASN) genom att använda ID-numret.</td>
</tr>
<tr>
<td>Plats och mottagning av registreringsskylt</td>
<td>Ta emot och inlagra en ingående leveransavisering (ASN) genom att använda ID-numret.</td>
</tr>
<tr>
<td rowspan="4">Produktion</td>
<td>Rapportera som färdig</td>
<td>Registrera en kvantitet för en färdig artikel som har avslutats för en produktion och skapa inlagrat arbete för en annan arbetare. Kvantiteten kan vara en del av eller hela den kvantitet som planerades för produktion.</td>
</tr>
<tr>
<td>Rapportera som färdig och inlagrad</td>
<td>Registrera en kvantitet för en färdig artikel som har avslutats för en produktion och lagra in artiklarna. Kvantiteten kan vara en del av eller hela den kvantitet som planerades för produktion. Samma arbetare utför båda åtgärder.</td>
</tr>
<tr>
<td>Kanban</td>
<td>Ange att en kanban ska utföras och skapa inlagrat arbete för en annan arbetare.</td>
</tr>
<tr>
<td>Kanban-plats</td>
<td>Ange att en kanban ska utföras och inlagra artiklarna. Samma arbetare utför båda åtgärder.</td>
</tr>
<tr>
<td rowspan="5">Lager</td>
<td>Rörelse</td>
<td>Registrera att artiklar har tagits bort från en plats till en annan. Arbetaren anger den plats de flyttas från och vilken plats de flyttas till.</td>
</tr>
<tr>
<td>Karantän</td>
<td>Ändra status för lagerbehållningen för en registreringsskylt eller en plats så att skadade eller saknade lagerartiklar inte längre är tillgängliga.</td>
</tr>
<tr>
<td>Förflyttning efter registreringsskylt</td>
<td>Flytta artiklar från en plats till en annan på ett halvautomatiskt sätt. Arbetaren väljer den plats artiklarna ska flyttas från, systemet använder platsdirektivet för att avgöra vilken plats som artiklarna ska flyttas till.</td>
</tr>
<tr>
<td>Överföring lagerställe</td>
<td>Registrera att artiklar har överförts från en plats till en annan. Detta alternativ kräver att arbetare tillåts att utföra arbete på båda lagerställena.

<strong>Obs!</strong> Detta menyalternativ kräver en standardiserad lageröverföringsjournal där fältet <strong>Verifikationsdragning</strong> anges som <strong>Bokför</strong>.</td>
</tr>
<tr>
<td>Läs in registreringsskylt</td>
<td>Använd det här alternativet när du ställer in ditt lagerställe för första gången. Skanna platser för alla ID-nummer på alla platser i lagerstället. Platserna måste vara registreringsskyltstyrda. Du kan inte använda det här alternativet, om <strong>Serienummer</strong> eller <strong>Batchnummer</strong> anges över <strong>Plats</strong> i lagerreservationshierarkin.</td>
</tr>
<tr>
<td rowspan="3">Rullande inventering</td>
<td>Justering in</td>
<td>Öka kvantiteten av artiklar i lagret. Ange plats, registreringsskylt, artikel, kvantitet, måttenhet och status.</td>
</tr>
<tr>
<td>Justering ut</td>
<td>Reducera kvantiteten av artiklar i lagret. Ange plats, registreringsskylt, artikel, kvantitet, måttenhet och status för lagret.</td>
</tr>
<tr>
<td>Rullande inventering av typen Spot</td>
<td>Starta en räkning för en plats. Arbetaren måste räkna alla artiklar på platsen. När resultatet av en strukturlista är mindre än den förväntade kvantiteten, betraktas den saknade kvantiteten som en förlust.</td>
</tr>
</tbody>
</table>

## <a name="configure-menu-items-to-process-existing-work"></a>Ställa in menyalternativ för att bearbeta befintligt arbete
Förutom inställningar av menyalternativ som skapar lagerställearbete, kan du ställa in menyalternativ till processarbete som redan har skapats. Ställ in fältet **Metod** till **Arbete** och välj alternativet **Använd befintligt arbete**. Alla ytterligare alternativ blir sedan tillgängliga på fliken **Allmänt**. Du kan styra åtkomsten till menyalternativet genom att tilldela en eller flera arbetsklasser på snabbfliken **Arbetsklass** . Arbetsklasserna definierar det arbete som menyalternativet kan bearbeta. Arbetsklassen kan också användas för att bevilja åtkomst till specifika användarroller eller för separat bearbetning för andra typer av operationer. I följande tabell beskriver de alternativ som är tillgängliga. Alternativet kan väljas under fältet **Dirigerad av** på sidan **Menyalternativ på mobil enhet**. 

<table>




<thead>
<tr class="header">
<th>Alternativ</th>
<th>beskrivning</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Ingen</td>
<td>Detta standardvärde processar inte arbete.</td>
</tr>
<tr class="even">
<td>Systemstyrd</td>
<td>Supply Chain Management kontrollerar den typ av arbete som har tilldelats en arbetare och i vilken ordning som personen utför arbetet. När du väljer det här alternativet kan du klicka på <strong>Systemstyrt arbete</strong> i åtgärdsfönstret för att öppna sidan <strong>Systemstyrd sorteringsordning</strong>, där du kan ställa in sorteringskriterier för resursen. Sorteringskriteriet kontrollerar den följd i vilken arbetaren utför arbetet. Du kan lägga till så många kriterier som du behöver.</td>
</tr>
<tr class="odd">
<td>Användarstyrd</td>
<td>Arbetaren väljer det arbete som ska utföras och ordningen det ska utföras i.</td>
</tr>
<tr class="even">
<td>Användargruppering</td>
<td>Arbetaren grupperar arbetet manuellt. Detta alternativ är praktiskt när t.ex. en arbetare kan plocka flera objekt samtidigt på en plats. När arbetaren har plockat alla nödvändiga artiklar kan de inlagra artiklarna.</td>
</tr>
<tr class="odd">
<td>Systemgruppering</td>
<td>Supply Chain Management grupperar arbete för arbetaren baserat på ett angivet fält. Till exempel plockningsarbete som grupperas när en arbetstagare skannar ett leverans-ID, last-ID eller något värde som kan kopplas till varje arbetsenhet. Om du väljer det här alternativet krävs följande fält:
<ul>
<li><strong>Fält för systemgruppering</strong> – Välj det fält som arbetaren ska skanna för att gruppera arbetet.</li>
<li><strong>Etikett för systemgruppering</strong> – Ange text för att instruera arbetaren om vad du ska skanna för att gruppera arbetet.</li>
</ul></td>
</tr>
<tr class="even">
<td>Styrs av validerad användare</td>
<td>Arbetaren väljer det arbete som ska utföras när jobbet är kopplat till en större enhet, till exempel en last eller en försändelse. Arbetaren bestämmer den ordningsföljd som artiklarna plockas i. Om du väljer det här alternativet krävs följande fält:
<ul>
<li><strong>Fält för validerad användarstyrning</strong> – Välj det fält som arbetaren ska skanna för att gruppera arbetet.</li>
<li><strong>Etikett för validerad användarstyrning</strong> – Ange text som instruerar arbetaren om vad som skannas när plockarbetet grupperas av systemet.</li>
</ul>
Det här alternativet är praktiskt när t.ex. flera lastpallar mellanlagras för en last. Om du väljer <strong>LoadId</strong> i fältet <strong>Validerad användarstyrning</strong> kan arbetaren plocka valfri lastpall som associeras med beläggningen. Arbetaren får ett felmeddelande visas om de skannar en artikel som inte är associerad med lasten.</td>
</tr>
<tr class="odd">
<td>Klusterplockning</td>
<td>Arbetsgruppens arbete till kluster. Kluster gör att arbetare kan plocka artiklar från ett ställe för flera arbetsorder samtidigt.</td>
</tr>
<tr class="even">
<td>Rullande inventeringsgruppering</td>
<td>Arbetaren väljer en zon, en arbetspool eller en plats, och Supply Chain Management tilldelar arbete som bygger på dessa val. Om du markerar det här alternativet kan du även klicka på <strong>Rullande inventering</strong> i åtgärdsfönstret för att ange ytterligare information, och du kan också ange hur många gånger som en arbetare måste upprepa inventeringen om en skillnad upptäcks.</td>
</tr>
 <tr class="odd">
<td>Transportlastning</td>
<td>Den här funktionen låter flera lagerarbetare lasta lager från samma eller olika laster till samma lastbil med laster som är helt eller delvis levererade.</td>
</tr>
</tbody>
</table>

## <a name="additional-menu-item-options"></a>Ytterligare menyalternativ
Det finns ytterligare menyalternativ tillgängliga på sidan **Menyalternativ på mobil enhet** . Alternativen varierar beroende på processen som du konfigurerar menyalternativen för. 

I följande register beskrivs dessa alternativ.

<table>




<thead>
<tr class="header">
<th>Fält</th>
<th>Beskrivning</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Tillåt delning av arbete</td>
<td>Välj det här alternativet om du vill tillåta användarna att placera artiklar för en arbetsorder i fler än en målregistreringsskylt. Detta alternativ är användbart när en målregistreringsskylt är full och arbetaren måste lägga till de kvarvarande artiklarna till en annan registreringsskylt. Arbetaren kan klicka på <strong>Fullständig</strong> för att ange att registreringsskylten är full och stoppa plockningsarbete för den. Läggplatsen för de plockade artiklarna visas sedan, och det plockningsarbete som redan har slutförts flyttas till en ny arbetsorder. Återstående plockningarbete för målregistreringsskylten blir kvar på den ursprungliga arbetsordern.</td>
</tr>
<tr class="even">
<td>Förankring</td>
<td>Markera det här alternativet om du låta arbetare ange en plats som åsidosätter den föreslagna platsen för mellanlagring eller lastning. Allt resterande inlagrat arbete dirigeras till den nya platsen. Detta alternativ är praktiskt när t.ex. en arbetstagare som måste inlagra artiklar för order 1 på en mellanlagringsplats efter docka 1, inte kan göra detta eftersom en tidigare last inte har rensats från platsen. I stället för att vänta på att mellanlagringplatsen Dock 1 blir tillgänglig, kan arbetaren välja att använda mellanlagringsplatsen för Dock 2. I det här fallet åsidosätter arbetaren den föreslagna mellanlagringsplatsen. Läggplatsen för alla återstående artiklar för arbetsordern uppdateras då till mellanlagringsplatsen Docka 2. Om du väljer det här alternativet måste du ställa in fältet <strong>Förankra efter</strong>.</td>
</tr>
<tr class="odd">
<td>Förankra efter</td>
<td>Om du använder förankring måste du ange om du vill förankra efter leverans eller efter beläggning.</td>
</tr>
<tr class="even">
<td>ID för granskningsmall</td>
<td>Välj den arbetsgranskningsmall som ska avbryta arbetsprocessen för det här menyalternativet så att en annan operation kan utföras. Om till exempel det här menykommandot är för inkommande arbete kan granskningsmallen kräva att arbetstagaren kontrollerar temperaturen i leveransbehållaren. Den punkt där processen avbryts anges på revisionsmallen. Denna punkt kan till exempel vara när arbetet har påbörjats eller avslutats, eller när dess status ändras.</td>
</tr>
<tr class="odd">
<td>ID för klusterprofil</td>
<td>Välj den klusterprofil som ska användas för klusterplockning. Klusterprofilen omfattar inställningar som om du vill skapa kluster automatiskt, namnen på positioner och antalet arbetsenheter de kan tilldelas, när du vill bryta kluster till individuella enheter och om verifiering krävs. Det här fältet är endast tillgängligt om <strong>Klusterplockning</strong> har valts i fältet <strong>Dirigerad av</strong>.</td>
</tr>
<tr class="even">
<td>Räkna total artikelkvantitet först</td>
<td>Välj det här alternativet om du vill tillåta att en arbetare ska inventera den totala kvantiteten först under en inventering. Om en skillnad hittas måste arbetaren ange ytterligare information, till exempel registreringsskyltnumret, batchnummer, serienummer osv.</td>
</tr>
<tr class="odd">
<td>Skapa förflyttning</td>
<td>Markera det här alternativet för att aktivera en arbetare om du vill skapa arbete för förflyttningar utan att kräva arbetaren utför arbetet på en gång. Detta alternativ är praktiskt om t.ex. en kvalitetsinspektion har utförts och inspektören vill att artikeln ska flyttas från kvalitetinspektionsområdet.</td>
</tr>
<tr class="even">
<td>Direktivkod</td>
<td>Markera den direktivkod som associeras platsdirektivet för att använda ett visst platsdirektiv. Detta fält är tillgängligt när du skapar arbete och processen för att skapa arbete är <strong>Förflyttning efter registreringsskylt</strong>.</td>
</tr>
<tr class="odd">
<td>Inaktivera trösklar för rullande inventering</td>
<td>Markera det här alternativet om du vill ignorera trösklarna för rullande inventering. Om du markerar det här alternativet, skapas inte rullande inventeringsarbete när tröskelvärden överskrids.</td>
</tr>
<tr class="even">
<td>Visa batchdispositionskod</td>
<td>Välj det här alternativet om du vill visa batchdispositionskoder. Du kan till exempel visa batchdispositionskoder, när du får en returnerad batch. Arbetare kan sedan utvärdera status eller kvalitet på en batch och välja lämplig kod. Reglerna på batchdispositionskoden bestämmer om den ska vara tillgängliga för andra lagerprocesser. Om du inte markerar det här alternativet, används en av följande batchdispositionskoder:
<ul>
<li>Om du får ett nytt batchnummer, används standardinställning batchdispositionskoden som anges på artikelmodellgruppen.</li>
<li>Den batchdispositionskod som redan tilldelats batchen används.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Visa dispositionskod</td>
<td>Välj det här alternativet om du vill visa dispositionskoder. Du kan till exempel visa batchdispositionskoder, när du får en returnerade artiklar. Arbetare kan sedan utvärdera status eller kvalitet på artiklarna och välja lämplig kod. Reglerna på dispositionskoden bestämmer om artiklarna ska vara tillgängliga för andra lagerprocesser.</td>
</tr>
<tr class="even">
<td>Visa lagerstatus</td>
<td>Markera det här alternativet om du vill visa status för artiklar i lager. Det här alternativet är tillgängligt för alla menyalternativ som använder befintligt arbete, förutom rullande inventering.</td>
</tr>
<tr class="odd">
<td>Visa sammanfattning av plockskärm</td>
<td>Markera det här alternativet om du vill visa en sammanfattning av plockningsarbetet för den valda arbetsordern. Sammanfattningen visas tills den första arbetsraden för arbetsordern bearbetats.</td>
</tr>
<tr class="even">
<td>Generera registreringsskylt</td>
<td>Markera det här alternativet om du vill generera ett unikt ID-nummer baserat på nummersekvensvalet. Du kan till exempel skapa ett registreringsskyltnummer för artiklar som tagits emot för inköpsorder.</td>
</tr>
<tr class="odd">
<td>Grupplats</td>
<td>Markera det här alternativet om du vill gruppera inlagrat arbete. Det här alternativet är tillgängligt när arbetet grupperats av antingen arbetaren eller Supply Chain Management. När arbetaren har slutfört allt plockningsarbete i gruppen skapas inlagrat arbete för samma grupp.</td>
</tr>
<tr class="even">
<td>Lagerjusteringstyper</td>
<td>Välj den lagerjusteringstyp som bestämmer vilken lagerinventeringsjournal som används för att bokföra justeringen och om du vill ta bort reservationer. Det här fältet är bara tillgänglig för processerna för att skapa arbete <strong>Justering in</strong> eller <strong>Justering ut</strong>.</td>
</tr>
<tr class="odd">
<td>Åsidosätt batchnummer</td>
<td>Markera det här alternativet om du vill tillåta arbetare som rapporterar en kvantitet som färdig för en produktionsorder att ange ett batchnummer som skiljer sig från det batchnummer som har tilldelats till produktionsordern.</td>
</tr>
<tr class="even">
<td>Åsidosätt målregistreringsskylt</td>
<td>Välj det här alternativet om du vill tillåta arbetare att ange ett mål-ID-nummer som skiljer sig från det föreslagna mål-ID-numret. Använd det här alternativet när den första plockningen för en arbetsorder utförs för hela kvantiteten för en artikel på en registreringsskylt. Det här alternativet är praktiskt t.ex. när du återanvänder en lastpall.</td>
</tr>
<tr class="odd">
<td>Plocka och packa</td>
<td>Välj det här alternativet om du vill tillåta att arbetare kombinerar arbete för en försäljningsorder eller läser in i en enskild arbetsenhet. Arbetaren kan utföra arbete endast för försäljningsordern eller beläggning. Detta alternativ är praktiskt när du t.ex. måste öka kvantiteten för en försäljningsorder efter lastningen och leverans, och arbete har skapats för försäljningsordern. Det här alternativet är tillgängligt när menyalternativet använder befintligt arbete och arbetet styrs av användaren eller systemet.</td>
</tr>
<tr class="even">
<td>Välj äldsta batch</td>
<td>Ange om arbetaren måste välja den äldsta batchen på en plats först. Följande alternativ är tillgängliga:
<ul>
<li><strong>Ingen</strong> – Arbetaren kan välja valfri batch på platsen. Arbetaren får inget meddelande.</li>
<li><strong>Varna</strong> – Arbetaren kan plocka alla batchar på platsen, men han eller hon får ett varningsmeddelande en batch inte är den äldsta batchen.</li>
<li><strong>Framtvinga</strong> – Arbetaren måste välja den äldsta batchen på platsen. Arbetaren får ett felmeddelande om en batch inte är den äldsta batchen. <strong>Obs!</strong> Detta alternativ är endast relevant om <strong>Batchnumret</strong> är lägre än <strong>Plats</strong> i den reservationhierarki som tilldelats artikeln.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Skriv ut etikett</td>
<td>Markera det här alternativet om du vill tillåta att anställda skriver ut registreringsskyltar.</td>
</tr>
<tr class="even">
<td>Fält för systemgruppering</td>
<td>Välj det fält som bestämmer hur Supply Chain Management ska gruppera plockningsarbete för arbetare. Om du till exempel väljer fältet <strong>ShipmentId</strong> kommer arbetstagare att skanna leverans-ID:t för att gruppera plockningsarbetet. Allt arbete för leveransen tilldelas sedan till arbetaren. Detta fält kräver att du skapar ett menyalternativ som ska använda befintligt arbete som grupperas av systemet. Du måste också ange text i fältet <strong>Systemgrupperingsetikett</strong> för att instruera arbetaren om vad den ska skanna..</td>
</tr>
<tr class="odd">
<td>Etikett för systemgruppering</td>
<td>Ange text för att instruera arbetaren om vad som skannas när plockarbetet grupperas av Supply Chain Management. Om du till exempel använder fältet <strong>ShipmentId</strong> för att gruppera plockningarbete efter leveransen kan du ange <strong>Leverans-ID</strong> i fältet. Detta fält kräver att du skapar ett menyalternativ som ska använda befintligt arbete som grupperas av systemet. Du måste också välja fältet som du vill gruppera efter i fältet <strong>Systemgruppering</strong>.</td>
</tr>
<tr class="even">
<td>Använd standarddata</td>
<td>Välj det här alternativet om du vill aktivera knappen <strong>Standarddata</strong> på åtgärdsfönstret där du kan välja fält om du vill visa data som en arbetare vanligtvis behöver i sitt dagliga arbete. Detta alternativ är praktiskt om t.ex. en arbetare ofta plockar artiklar från samma plats. Du kan välja fältet <strong>Från plats</strong> om du vill visa enheten som standard.</td>
</tr>
<tr class="odd">
<td>Fält för validerad användarstyrning</td>
<td>Välj det fält som arbetaren ska skanna för att gruppera arbetet. Om du till exempel väljer <strong>LoadId</strong>, kan en arbetstagare plocka ett arbete som är associerat till den valda lasten. Du måste också ange text i fältet <strong>Etikett för validerad användarstyrning</strong> för att instruera arbetaren om vad den ska skanna..</td>
</tr>
<tr class="even">
<td>Etikett för validerad användarstyrning</td>
<td>Ange text för att instruera arbetaren om vad som skannas när plockarbetet grupperas av ett fält med validerad användarstyrning. Om du till exempel använder fältet <strong>LoadId</strong> för att gruppera plockningarbete för en last kan du ange <strong>Last-ID</strong> i fältet.</td>
</tr>
<tr class="odd">
<td>Kod för arbetsmall</td>
<td>Välj den arbetsmall som ska användas för att skapa arbetet för en process. Om du till exempel tar emot en artikel för en inköpsorder, genereras det inlagrade arbetet baserat på arbetsmallen. Om du inte väljer någon arbetsmall tilldelar Supply Chain Management en mall baserat på frågevillkor. Mer information om arbetsmallar finns i <a href="control-warehouse-location-directives.md">Kontrollera lagerarbete med arbetsmallar och platsdirektiv</a>.</td>
<tr class="even">
<td>Visa lista med arbetsrad</td>
<td>Välj ett alternativ för hur arbetare ska kunna visa och interagera med raderna för det valda plockningsarbetet. Mer information om det här alternativet finns i <a href="pick-line-overview.md">Konfigurera en menyartikel för mobila enheter för att visa en översikt över en plockningsrad</a>.</td>
</tr>
</tbody>
</table>

## <a name="require-workers-to-confirm-the-product-location-or-quantity-when-they-pick-items"></a>Begär att arbetare ska bekräfta produkten, platsen eller kvantiteten när de plockar artiklar

Du kan ställa in arbetsbekräftelser som kräver en arbetare att använda en mobil enhet för att registrera platsen eller kvantitet, när han eller hon utför arbete på lagerstället. Arbetsbekräftelser hjälper till att garantera att arbetaren är på rätt plats eller hanterar rätt kvantitet av artiklar. Du kan också aktivera Supply Chain Management du automatiskt vill bekräfta arbetarens registrering. Om du aktiverar automatisk bekräftelse, kan du inte också kräva bekräftelser för plats och kvantitet. Arbetsbekräftelser innehåller också produkter och produktvarianter. Du kan registrera bekräftelser genom att skanna en streckkod. Om du bekräfta produkter och produktvarianter måste du ange ett ID för produkten eller produktvarianten. Detta ID kan vara ett produkt-ID, ett produktsöknings-ID, ett externt ID, en GTIN eller en streckkod. När du har angett ID eller skannat streckkoden visas dimensionerna för produktvarianten i den mobila enheten. 

I tabellen nedan beskrivs de olika arbetstyperna som du kan använda arbetsbekräftelser med.

| Alternativ | Beskrivning |
|------------------------|----------------------------------------------------------------------------|
| Välj | Begär bekräftelse när du plockar artiklar. |
| Placera | Begär bekräftelse när du placerar artiklar på en plats. |
| Inventering | Begär bekräftelsen under rullande inventering. |
| Justeringar | Begär bekräftelse när du justerar lagerkvantiteter. |
| Anpassad | Begär bekräftelse för anpassat arbete. |
| Karantän | Begär bekräftelsen när du flyttar artiklar till karantän. |
| Skapa registreringsskylt | Begär bekräftelse när du konsoliderar artiklarna för att skapa ett ID-nummer. |
| Skriv ut | Begär bekräftelse när du skriver ut ID-nummeretiketter. |
| Statusändring | Begär bekräftelse när du ändrar statusen för lagret. |

> [!NOTE]
> Det går bara att begäran produktbekräftelse för plock- och placeringsarbetstyper.

## <a name="additional-resources"></a>Ytterligare resurser

- [Ställ in ett menyalternativ för mobila enheter för att utföra arbete av typen Inköpsorder](tasks/set-up-mobile-device-menu.md)
- [Ställ in ett menyalternativ för mobila enheter för att registrera mottagna artiklar](tasks/set-up-mobile-device-menu-item-register-received-items.md)
- [Lagerstatus](../inventory/inventory-statuses.md)




[!INCLUDE[footer-include](../../includes/footer-banner.md)]
