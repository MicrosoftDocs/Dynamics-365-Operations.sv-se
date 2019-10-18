---
title: Projekthantering och redovisning – översikt
description: Funktionen för projekthantering och redovisning kan användas i flera branscher för att tillhandahålla en tjänst, för att tillverka en produkt eller för att uppnå ett resultat.
author: KimANelson
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjTable; ProjProjectManagementWorkspace
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0d461b85f89eff63c8747fb17b3ee34ebfeb2218
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2185645"
---
# <a name="project-management-and-accounting-overview"></a>Projekthantering och redovisning – översikt

[!include [banner](../includes/banner.md)]

Funktionen för projekthantering och redovisning kan användas i flera branscher för att tillhandahålla en tjänst, för att tillverka en produkt eller för att uppnå ett resultat.  

Ett projekt är en grupp aktiviteter som har utformats för att tillhandahålla en tjänst, tillverka en produkt eller för att uppnå ett resultat. Projekt förbrukar resurser och skapar ekonomiska resultat i form av intäkter eller tillgångar.

## <a name="projects-across-industries"></a>Projekt i flera branscher
Funktionen för projekthantering och redovisning kan användas i flera branscher, som illustreras nedan.

[![Projekt i flera branscher](./media/projects-accross-industries.jpg)](./media/projects-accross-industries.jpg) 

Hos en kundtjänst kan en biljett användas för att beskriva åtgärderna som krävs för att lösa ett ärende. Konsultföretag, till exempel management eller tekniska konsultorganisationer eller reklambyråer kallar sina aktiviteter för projekt. I marknadsföring representerar en kampanj en uppsättning med arbete som måste levereras. I projektbaserad tillverkning innehåller en produktionsorder de olika arbetsmomenten som måste göras för att tillverka en färdig produkt. Oavsett vilket namn som används, ingår det resurser, scheman och kostnader i projekten, och funktionen för projekthantering och redovisning kan hjälpa dig med planeringen, utförandet, och analysen av dessa projekt.

## <a name="project-phases"></a>Projektfaser
Även om projektflödet nedan gäller externa projekt eller projekt som slutförs för en eller flera kunder, gäller funktionerna även interna projekt med enbart kostnader. 

![Ett projekts tre faser](./media/3-stages-of-a-project.png) 

I föregående illustration visades att projektledning och redovisning kan delas in i tre faser:

1.  Initiera
2.  Kör
3.  Analysera

## <a name="initiate-the-project"></a>Initiera projektet
Under projektets inledning inträffar flera viktiga processer. Du kan använda en projektoffert för att kommunicera fälten uppskattat arbete, kostnader och material till kunden. Du kan registrera fakturavillkor, begränsningar och avtal i ett projektkontrakt. Du kan använda en uppdelad arbetsstruktur (WBS) för att planera och uppskatta arbete. Du kan ställa in prognoser och budgetar för att leda projektgenomförandet. I följande bild visas strukturen för ett projekt. [![-projektstruktur](./media/project-structure1.jpg)](./media/project-structure1.jpg)  

### <a name="create-project-quotations"></a>Skapa projektofferter

I den första fasen i ett projekt gör en projektoffert att du kan förse kunden med ett erbjudande som inte är bindande. En offert kan inkludera många punkter som exempelvis de artiklar och tjänster som offereras, grundläggande kontaktinformation, särskilda handelsavtal och rabatter samt eventuella skatter och tilläggsavgifter.

Du kan även utfärda en betalningsgaranti för en projektoffertstransaktion mellan din organisation och kunden. När projektofferten har skapats kan du skapa garantin för kunden och skicka den till banken. När banken har godkänt förfrågan utfärdas garantin till kunden. 

Mer information finns i [Projektofferter](project-quotations.md).

### <a name="create-project-contracts"></a>Skapa projektkontrakt

När du ingår ett avtal med en kund eller en annan finansieringskälla för att kunna slutföra ett projekt måste du först skapa ett projektavtal. När du sedan skapar projektet måste du koppla det till motsvarande avtal. Typen av projektet som du skapar för ett projektavtal bestämmer vilken metod som används för att faktura projektkunderna. Du kan ändra ett projektavtal och det relaterade projektet, men du kan inte ändra projekttypen. Mer information om projekttyper finns i avsnittet Skapa projekt.

Mer information om projektavtal finns i [Projektavtal](project-contracts.md).

### <a name="create-work-breakdown-structures"></a>Skapa uppdelade arbetsstrukturer

Graden av information i en WBS beror på noggrannhetsnivån som krävs i uppskattningarna och spårningsnivån som krävs för dessa uppskattningar. Projekt som har mycket låg tolerans för förseningar i tid eller kostnad kräver vanligtvis en mer detaljerad arbetsstruktur och även noggrann spårning av arbetsförloppet och kostnader mot strukturen. 

Mer information finns i [Uppdelade arbetsstrukturer](work-breakdown-structures.md).

### <a name="create-project-forecasts-and-budgets"></a>Skapa projektprognoser och projektbudgetar

Du kan använda prognostisering om organisationen har ett driftperspektiv och fokuserar på intäkter och kostnader som härleds från specifika transaktioner. Om din organisation fokuserar mer på ekonomiska belopp, kan du använda budgetering. Varje metod har sina fördelar. Mer information finns i [Projektprognoser och projektbudgetar](project-forecasts-budgets.md).

### <a name="create-projects"></a>Skapa projekt

Du kan skapa sex typer av projekt i Finance. Varje projekttyp konfigureras på olika sätt för kostnader och intäktsredovisning. Vilken projekttyp du väljer beror på syftet med projektet. I tabellen nedan beskrivs det vanliga användandet av varje projekttyp.
                                                                                                            
<table>
  <tr>
    <td>Projekttyp</th>
    <td>Beskrivning</th>
  </tr>
  <tr>
    <td>Tid och material</td>
    <td>I Tids- och materialprojekt faktureras kunden för alla kostnader som uppstår i ett projekt. Dessa kostnader inkluderar kostnader för timmar, utgifter, artiklar och avgifter.</td>
  </tr>
  <tr>
    <td>Fast pris</td>
    <td>Fakturorna i fastprisprojekt består av a conto-transaktioner. Fasprisprojekt faktureras enligt ett faktureringsschema baserat på ett projektkontrakt. Intäkt för ett fastprisprojekt kan beräknas och bokföras i hela projektet genom att använda metoden för slutförd procent. Alternativt kan intäkt beräknas och bokförs när projektet är avslutat genom att använda moden för slutfört kontrakt. Företag kan ofta använda värdet för produkter i arbete (WIP) för att beräkna graden av slutförandet för ett projekt eller en grupp av projekt.</td>
  </tr>
  <tr>
    <td>Investering</td>
    <td>Investeringsprojekt är projekt som inte ger omedelbara intäkter. De används vanligtvis för långa interna projekt vars kostnader måste kapitaliseras. Bara kostnader för artiklar, timmar och utgifter kan registreras för ett investeringsprojekt. Kostnader i ett investeringsprojekt spåras och kontrolleras med hjälp av uppskattningsfunktionen. Investeringsprojekt kan ställas in med maximal kapitalisering (valfritt). Under investeringsprojektets gång registrerar du dess kostnader i PIA-konton, där kostnaderna förvaras tills projektet är avslutat. När projektet har eliminerats överför du PIA-värdet till en anläggningstillgång, ett redovisningskonto eller ett nytt projekt. <br></br> <strong>OBS!</strong> Transaktioner för investeringsprojekt visas inte på sidorna <strong>Bokför kostnader<strong>, <strong>Periodisera intäkter</strong>, eller <strong>Skapa fakturaförslag</strong>.</td>
  </tr>
  <tr>
    <td>Kostnadsprojekt</td>
    <td>Likt investeringsprojekt används kostnadsprojekt vanligtvis för att spåra interna projekt, och bara timmar, utgifter och artiklar kan registreras i dem. Kostnadsprojekt är dock normalt kortare än investeringsprojekt. Dessutom kan inte kostnadsprojekt, till skillnad från investeringsprojekt, inte kapitaliseras mot balansräkningskonton. I stället bokförs deras projekttransaktioner bara på vinst- och förlustkonton. <br></br> <strong>OBS!</strong> Transaktioner för kostnadsprojekt visas inte på sidorna <strong>Bokför kostnader</strong>, <strong>Periodisera intäkter</strong>, eller <strong>Skapa fakturaförslag</strong>. Eftersom kostnadsprojekt vanligtvis används för att spåra interna projekt, är de vanligtvis inte associerade med ett kundkonto. Om din installation däremot kräver att artikelbehov skapas för inköpsorder måste du koppla kostnadsprojektet till en kund. Kopplingen är ett krav eftersom artikelbehoven hanteras som försäljningsorderrader och systemet kräver att en kund specificeras. Dessa inställningar kommer dock inte att resultera i att artikelbehov skapas automatiskt från en inköpsorder. I kostnadsprojekt ignoreras inställningen <strong>Skapa artikelbehov</strong>. Om du behöver ett artikelbehov i ett kostnadsprojekt, kan du skapa ett manuellt, under förutsättning att en kund är kopplad till projektet.</td>
  </tr>
  <tr>
    <td>Intern</td>
    <td>Interna projekt används för att spåra kostnader i ett projekt som är internt för din organisation. Interna projekt kan tillhandahålla ett planläggningsverktyg för hantering av resursförbrukning. <br></br><strong>OBS!<strong> Transaktioner för interna projekt visas inte på sidorna <strong>Periodisera intäkter</strong> eller <strong>Skapa fakturaförslag</strong>.</td>
  </tr>
  <tr>
    <td>Tid</td>
    <td>Tidsprojekt används för att spåra tid som är kopplad till icke-debiteringsbara och icke produktiva aktiviteter, till exempel ett projekt att spåra sjukfrånvaro för arbetare. Transaktioner i tidsprojekt bokförs inte i redovisningen. I stället är de inkluderade i rbetarutnyttjanderapporter. Endast timtransaktioner kan registreras för ett tidsprojekt. Du använder en timjournal eller tidrapport för att registrera dessa timmar till projektet. När timmarna har registrerats visas de som projekttransaktioner, men har inte motsvarande verifikationstransaktion. <br></br><strong>OBS!</strong> Transaktioner för tidsprojekt visas inte på sidorna<strong>Bokför kostnader</strong>, <strong>Periodisera intäkter</strong>, eller <strong>Skapa fakturaförslag</strong></td>
  </tr>
</table>


### <a name="assign-workers-categories-and-resources"></a>Tilldela anställda, kategorier och resurser

Du kan tidsplanera arbetarresurser baserat på behoven och tidsplaneringen för ett projekt eller på de anställdas färdigheter och tillgänglighet. Med resurstidsplaneringsfunktionerna kan du fördela organisationens personal effektivt och rationellt. Du kan snabbt hitta de mest kvalificerade arbetarna som är tillgängliga för ditt projekt. Du kan också enkelt se hur de anställd kan användas effektivare under projektet. 

Nedan visas hur du kan använda resursplaneringsfunktionen på olika sätt:

-   Använd information om en arbetares attribut, som till exempel utbildning, färdigheter, certifieringar och projekterfarenhet, för att matchar arbetare med kraven för ett projekt.
-   Använd information om en arbetares kalender och tillgänglighet för att matcha arbetarens schema med projektkalendern.
-   Granska kapaciteten för varje arbetare och bestäm hur den kapaciteten används. Om till exempel en arbetstagare är underutnyttjad kan arbetstagaren tilldelas ett projekt som passar hans eller hennes tillgänglighet och attribut.
-   Granska en medarbetares tillgänglighet för att säkerställa att det inte finns några kalenderkonflikter med personens tilldelningar.
-   Granska information om användande av personal på ett övergripande sätt (t.ex. per avdelning eller per person) eller i en detaljerad vy (t.ex. per person på en avdelning eller veckovis för varje person).
-   Ändra resurstilldelningar för olika tidsenheter, till exempel dag, vecka eller månad, för att optimera hur personalen används.

## <a name="execute-the-project"></a>Köra projektet
Under projektutförandet registrerar gruppmedlemmarna eller projektledarna arbetet och utgifterna via tidrapporter, utgiftsrapporter och andra affärsdokument. Projektledare har verktyg som gör att de kan övervaka förbrukningen av budgeterade belopp i projektet. Projektledare kan också beställa, välja eller producera material för projekt med hjälp av inköpsorder och andra dokument. Fakturor förbereds och godkänns, så att kunder kan faktureras för pågående arbete. Slutligen identifieras intäkter som kan påverkar företagets ekonomi.

### <a name="manage-work-breakdown-structures"></a>Hantera uppdelade arbetsstrukturer

En uppdelad arbetsstruktur är en beskrivning av det arbete som ska utföras i ett projekt. Arbetsstrukturen är en hierarki av uppgifter. Den representerar inte bara arbetet i uppgiften, utan också uppgiftens omfattning, kostnad och tidslängd. 

Mer information finns i [Uppdelade arbetsstrukturer](work-breakdown-structures.md).

### <a name="manage-project-forecasts-and-budgets"></a>Hantera projektbudgetar och projektprognoser

Du kan hantera och kontrollera dina projekt på två sätt: projektprognoser och projektbudgetar. Du kan använda prognostisering om organisationen har ett driftperspektiv och fokuserar på intäkter och kostnader som härleds från specifika transaktioner. Om din organisation fokuserar mer på ekonomiska belopp, kan du använda budgetering.

Mer information finns i [Projektprognoser och projektbudgetar](project-forecasts-budgets.md).

### <a name="create-production-orders"></a>Skapa tillverkningsorder

En projektrelaterad tillverkningsorder kan kopplas till en försäljningsorder eller ett artikelbehov genom att använda antingen den färdiga artikelmetoden eller metoden för förbrukade artiklar. Dessutom, om tillverkningsordern skapades manuellt, finns det ingen koppling mellan tillverkningsordern och försäljningsordern eller artikelbehovet (ingen länk till beställning). Men om tillverkningsordern skapades automatiskt för att uppfylla en försäljningsorder eller ett artikelbehov, finns det en koppling mellan tillverkningsordern och försäljningsorder eller artikelbehovet (länk till beställning). 

Använd en av följande metoder, på grundval av kombinationen av dessa faktorer:

- **Slutförd artikel/länk till order** – Koppla projektet till en försäljningsorder eller ett artikelbehov. När du använder den här metoden bokförs de faktiska projektkostnaderna när försäljningsordern faktureras eller när följesedeln uppdateras för artikelbehovet. Kostnaden bokförs som en slutförd artikel.
- **Slutförd artikel/ingen länk till order** – faktiska kostnader kan inte har bokföras förrän produktionscykeln för en artikel har statusen **Avslutat**. Kostnaden för den slutförda artikeln bokförs som en enda transaktion.
- **Förbrukad artikel/länk till order** – koppla projektet till ett artikelbehov. Med den här metoden kan du visa de faktiska projektkostnaderna när produktionen har statusen **Startad** eller har rapporterats som avslutad. Kostnaderna bokförs som flera projektartikeltransaktioner för råmaterial och timmar som förbrukats för produktionen. När följesedeln uppdateras för artikelbehovet bokförs inte några projektkostnader. Du kan också definiera på vilken nivå i strukturlistehierarkin som projekten i produktionen ska spåras.
- *<strong><em>Förbrukad artikel/ingen länk till order</em></strong>* – koppla projektet till ett artikelbehov. Med den här metoden kan du visa de faktiska projektkostnaderna när produktionen har statusen <strong>Startad</strong> eller har rapporterats som avslutad. Kostnaderna bokförs som flera projektartikeltransaktioner för råmaterial och timmar som förbrukats för produktionen. Du kan också definiera på vilken nivå i strukturlistehierarkin som projekten i produktionen ska spåras.

### <a name="procure-products-and-services"></a>Anskaffa produkter och tjänster

Inköp och försäljning av artiklar är viktiga aktiviteter i många projektfokuserade företag.

#### <a name="purchase-orders-for-projects"></a>Inköpsorder för projekt

Syftet med inköpsordern avgör när inköpsordern förbrukas och därmed när artiklar debiteras i ett projekt.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Metod</th>
<th>Syfte</th>
<th>Förbrukning av artiklar</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Skapa en inköpsorder direkt.</td>
<td>Inköpsartiklar från en extern leverantör för förbrukning i ett projekt. Du kan skapa inköpsorder på följande sätt:
<ul>
<li>Från själva projektet. I det här fallet har projektet redan definierats för inköpsordern.</li>
<li>Genom att navigera till projektinköpsordern. Du måste välja både leverantören och projektet som inköpsordern ska skapas för.</li>
</ul></td>
<td>Artiklar förbrukas när leverantörsfakturan uppdateras.</td>
</tr>
<tr class="even">
<td>Skapa en inköpsorder från en försäljningsorder.</td>
<td>Köp in artiklar när du skapar en försäljningsorder av ett projekt.</td>
<td>Artiklar förbrukas när försäljningsordern faktureras till kunden.</td>
</tr>
<tr class="odd">
<td>Skapa en inköpsorder från ett artikelbehov.</td>
<td>Köp in artiklar när du skapar ett artikelbehov av ett projekt.</td>
<td>Artiklar förbrukas när följesedeln för artikelbehov uppdateras.</td>
</tr>
</tbody>
</table>

#### <a name="sales-orders-for-projects"></a>Försäljningsorder för projekt

I Projekthantering och redovisning kan du registrera förbrukningen av artiklar på flera olika sätt. Du kan sälja eller köpa artiklar från ett projekt eller reservera artiklar för ett projekt. 

Du kan beställa artiklar från företagets lager för förbrukning i ett projekt. Alternativt kan du köpa från en extern leverantör. Artiklar kan förbrukas i alla projekt utom projekt av typen Tid. 

Hur du beställer artiklar beror på varifrån du beställer dem:

-   Om du vill beställa artiklar från företagets lager måste du registrera ordern som ett artikelbehov. Om du använder sidan **Artikelbehov** kan du ange kraven så att artiklarna ska inlevereras som delleveranser. Därför kan du skjuta upp förbrukningen av en kvantitet av artiklarna tills ett behov av artiklarna uppstår.
-   Om du beställer artiklar från en extern leverantör måste du skapa ordern som en inköpsorder på sidan **Inköpsorder**.

> [!NOTE] 
> Följesedeln för en projektrelaterad försäljningsorder kan inte annulleras om artiklarna redan har märkts för att packas. 

Följande tabell listar metoder för att beställa artiklar och beskriver hur artiklarna förbrukas.

| Metod            | Syfte                                                                                                                                                        | Förbrukning av artikeltransaktioner                                                                                                                  |
|-------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------|
| Försäljningsorder       | Ange en transaktion direkt på ett projekt av typen Tid och material.                                                                                                   | Artikeltransaktioner förbrukas när kundfakturan bokförs.                                                                               |
| Lagerjournal | Ange och underhåll artikelposter snabbt. Om du till exempel vill ange ett artikelbehov baserat på en utskriven lista, kan du använda lagerjournalen. | Artikeltransaktioner förbrukas när journalen bokförs.                                                                                        |
| Artikelbehov  | Ange artiklar som inte ska förbrukas direkt. Denna metod gör att du kan hålla ordning på hur många artiklar som har förbrukats inom en artikelbehovspost.    | Artikeltransaktioner förbrukas när följesedeln uppdateras. Artikelbehovet skapas alltså när följesedeln bokförs. |
| Inköpsorder   | Registrera transaktioner på en av tre olika platser, beroende på inköpsmetod.                                                                              | Artikeltransaktioner förbrukas när följesedeln uppdateras eller när kunden och/eller leverantören faktureras.                                      |

### <a name="process-project-invoices"></a>Bearbeta projektfakturor

Projekttypen bestämmer vilken faktureringsprocedur som ska användas. Endast de två externa projekttyperna (Tid och material och Fastpris) går att fakturera. Tids- och materialprojekt och fastprisprojekt är alltid kopplade till ett projektkontrakt. 

Innan du skapar en kundfaktura för ett projekt kan du skapa en preliminär faktura eller ett fakturaförslag. I ett fakturaförslag kan du välja projekttransaktioner som ska inkluderas i en projektfaktura. Du kan sedan granska fakturadetaljerna innan du bokför projektfakturan och skickar den till kunden eller annan finansieringskälla. 


Mer information om hur du bearbetar projektfakturor finns i [Projektfakturering](../accounts-payable/project-invoicing.md).


### <a name="calculate-the-cost-to-complete-a-project"></a>Beräkna kostnaden för slutförande av ett projekt

När du skapar en uppskattning, kan du välja den metod som används för att beräkna kostnaden för projektet. Du väljer en metod i fältet **Kostnad för slutförande-metod** på sidan **Skapa uppskattning**. Metoden du väljer gäller för varje kostnadsrad separat i kostnadsuppskattningen. När en rad har statusen **Skapat**, kan du ändra den metod som används till raden på sidan **Kostnadsuppskattning**. 

I tabellen nedan beskrivs metoderna för beräkning av kostnaden för att slutföra ett projekt.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Metod</th>
<th>Beskrivning</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Total kostnad – utfall</td>
<td>Uppskattade kostnader måste anges manuellt. När kolumnen <strong>Total kostnad</strong> eller <strong>Total kvantitet</strong> på sidan <strong>Kostnadsuppskattning </strong> har fyllts i, dras de faktiska kostnaderna från den användarspecificerade summan. Resultatet är kostnaden för att slutföra projektet. Vanligtvis spåras inte kostnaderna baserat på exempelvis antal hotellnätter och måltider som registreras för varje period. I stället baseras spårningen på en jämförelse med det totala antalet beräknade timmar. Den här metoden kräver inte en prognosmodell och den totala kostnaden eller totala kvantiteten går att ändra manuellt. När ett värde har angetts i kolumnen <strong>Total kostnad</strong> eller <strong>Total kvantitet</strong> jämför Finance detta värde med de verkliga transaktionerna som bokförs i perioden. Sedan minskas värdet i kolumnen <strong>Kvantitet som ska slutföras</strong> eller <strong>Kostnad för slutförande</strong>.</td>
</tr>
<tr class="even">
<td>Total budget – utfall</td>
<td>Faktiska kostnader jämförs med prognosmodellen du har valt för att bestämma kostnaden. Den här metoden använder den totala budgetmodellen som innefattar prognostransaktioner. Om du vill ha en mer exakt vy av projektet kan du ändra budgetmodell när projektet pågår. Om du behöver justera prognosen gör du så här:
<ol>
<li>Kopiera prognostransaktionerna till en annan prognosmodell.</li>
<li>Jämför prognostransaktioner med verkligt transaktioner.</li>
<li>Underhåll, minska eller öka uppskattningarna för nästa period.</li>
</ol>
Finance minskar inte automatiskt prognosuppskattningarna. Därför är det en bra idé att upprätthålla en originalprognosmodell i fastprisprojektet för att ha en något att jämföra med när projektet är avslutat. 
<br></br> <strong>OBS!</strong> När du väljer den här metoden ska du använda minst två prognosmodeller. En modell ska innehålla originalprognosen. Till den andra modellen ska du kopiera prognostransaktionerna från en annan modell. Den här metoden gäller bara för fastprisprojekt och investeringsprojekt.</td>
</tr>
<tr class="odd">
<td>Resterande budget</td>
<td>Den här metoden använder en modell för återstående budget för att beräkna kostnaden för projektet. När du använder den här metoden adderas de faktiska kostnaderna och prognosbeloppen i den återstående budgeten. Resultatet är en totalkostnad. Innan du använder den här metoden, måste en modell för resterande budget läggas upp där transaktioner dras av baserat på faktiska transaktioner som har registrerats i systemet. På sidan <strong>Prognosmodeller</strong> ser du till att fälten är markerade i gruppen <strong>Automatisk prognosreducering</strong> . Vanligtvis kopieras en en resterande budget från en ursprunglig budget. När transaktioner registreras minskas transaktionerna i den resterande budgeten. När projektet framskrider och om du bestämmer att den återstående budgeten ska justeras debiterar du prognostransaktioner på den resterande budgeten. <br></br> <strong>OBS!</strong> Metoden kan endast användas om en prognosmodell är kopplad till uppskattningen.</td>
</tr>
<tr class="even">
<td>Som föregående uppskattning</td>
<td>Samma uppskattningsmetod som användes i den föregående perioden tillämpas. Den här metoden kräver en prognosmodell om den föregående perioden kräver en prognosmodell.</td>
</tr>
<tr class="odd">
<td>Ställ in den kostnad du vill slutföra till noll</td>
<td>Vanligtvis används den här metoden innan uppskattningsprojektet elimineras. Den här metoden matchar de totala uppskattningarna med de verkliga transaktionerna som bokfördes och rensar kolumnen <strong>Kostnad för slutförande</strong>. Den resulterande slutförandeprocenten är alltid 100 procent. Fältet <strong>Prognostisering</strong> är inte markerat för varje kostnadsrad du skapar, och den totala uppskattningen kopieras från den föregående kostnadsuppskattningen. Den faktiska förbrukningen för uppskattningsperioden dras från kostnaden som ska slutföra projektet. Denna metod kräver inte någon prognosmodell.</td>
</tr>
<tr class="even">
<td>Från kostnadsmall</td>
<td>Kostnad för slutförande-metoden som ställdes in i kostnadsmallen som är kopplad till det valda uppskattningsprojektet tillämpas.</td>
</tr>
</tbody>
</table>

## <a name="analyze-the-project"></a>Analysera projektet
I sin enklaste form används ett projekt till att gruppera transaktioner som registrerar kostnader och sedan bokföra dessa kostnader i redovisningen. 

Allmänt är dessa transaktioner resultatet av affärsdokument, t.ex.tidrapporter, utgiftsrapporter, leverantörsfakturor och lagertransaktioner. Livscykeln för ett projekt börjar vanligen med uppskattningar, prognoser och budgetar som hjälper till att planera arbetet och ekonomin i projektet. När du analyserar ett projekt, kan du inte bara utvärdera transaktionerna som inträffar under projektet, men också riktigheten i dina uppskattningar och prognoser, utnyttjandegraderna av projektmedlemmarna och den övergripande framgången för projektet.

### <a name="analyze-cash-flow"></a>Analysera kassaflöde

Med kassaflödesövervakning kan du övervaka både det prognostiserade och faktiska kassaflödet i ett projekt. Du kan granska kassaflödet både i ett pågående projekt och i ett avslutat. 

Genom att övervaka kassaflödet kan du utvärdera ett enstaka projekt, visa flera projekt med hjälp av rapporter och överföra projektkassaflöden till kassaflödesprognoser i redovisningen.

#### <a name="cash-inflow-forecasting"></a>Kassainflödesprognoser

Baserat på dina inställningar, kan du prognostisera kassainflödena för ett valt projekt. Om projektdatumet till exempel är 5 mars 2012 och du fakturerar den 31 mars 2012 kan du prognostisera förfallodatumet och det förväntade betalningsdatumet:

-   **Projektdatum:** 5 mars 2012.
-   **Fakturadatum:** 31 mars 2012. Det här datumet bestäms utifrån fakturafrekvens. För det här exemplet ställer du in fakturafrekvensen på den aktuella månaden. Därför faktureras alla transaktioner som bokförs under månaden mars den sista dagen i månaden.
-   **Förfallodatum:** 14 april 2012. Det här datumet bestäms utifrån betalningsvillkoren som har angetts för projektet. I det är exemplet är betalningsvillkoren 14 dagar. Därför läggs 14 dagar till fakturadatumet så att datumet blir 14 april 2012.
-   **Förväntat försäljningsbetalningsdatum:** 27 april 2012. Det här datumet beräknas genom att addera antal dagar i fältet **Allmänna buffertdagar** på sidan **Parametrar för projekthantering och redovisning** till antalet dagar i fältet **Individuella buffertdagar** på sidan **Projektkontrakt** och sedan lägga till totalt antal dagar i fältet **Förfallodatum**. För det här exemplet har du angett **3** i fältet **Allmänna buffertdagar** och **10** i fältet **Individuella buffertdagar**. Därför adderas 13 dagar till förfallodatumet så att resultatet blir det förväntade försäljningsbetalningsdatumet 27 april 2012.

De allmänna buffertdagarna kan antingen ersätta de enskilda buffertdagarna eller läggas till de enskilda buffertdagarna:

-   Om du vill använda de allmänna buffertdagarna som ersättning för de enskilda buffertdagarna anger du det genomsnittliga antalet dagar mellan förfallodatumet och det riktiga betalningsdatum för kunder.
-   Om du vill addera de allmänna buffertdagarna till de enskilda buffertdagarna, anger du din uppskattning av antalet dagar mellan dagen när kunden skickar betalningen och dagen då ditt företag får betalningen i fältet, **Allmänna buffertdagar**.

Ställ in enskilda buffertdagar i projektets kontrakt. Dagarna beräknas utifrån både fakturans förfallodag och företagets erfarenhet av kundens betalningsmönster.

#### <a name="actual-cash-inflow"></a>Faktiskt kassainflöde

Faktiskt kassainflöde påminner om prognoser, men du kan inleda beräkningarna från första fakturadatumet. Här är ett exempel:

-   **Fakturadatum:** 2 mars 2012.
-   **Förfallodatum:** 16 mars 2012. Betalningsvillkoren har angetts till 14 dagar.
-   **Förväntat försäljningsbetalningsdatum:** 29 mars 2012. Beräkningen innefattar tre allmänna buffertdagar och 10 individuella buffertdagar.

#### <a name="cost-forecasting"></a>Kostnadsprognos

Baserat på dagarna som har definierats, kan betalningsdatumet skilja sig från projektdatumet. I det här fallet beräknas betalningsdatumet genom att addera antal dagar från projektdatumet till antal dagar i betalningsvillkoret. 

Exempelvis är projektdatumet för transaktionen 5 mars 2012, och betalningsvillkoren är följande:

-   **Timmar:** Aktuell månad (**M**)
-   **Utgifter:** 14 dagar (**D14**)
-   **Artiklar:** 30 dagar (**D30**)

Här är betalningsdatumet för varje transaktionstyp, baserat på de här inställningarna:

-   **Timmar:** 31 mars 2012, vilket är den sista dagen i den valda månaden.
-   **Utgifter:** 19 mars 2012, vilket är 14 dagar efter datumet för transaktionen.
-   **Artiklar:** 4 april 2012, vilket är 30 dagar efter datumet för transaktionen.

> [!NOTE] 
> Inköpsorderns förfallodatum baseras på leverantörstransaktionen när projektinköpsordern skapas. Förfallodatumet bestäms inte av några standardinställningar. 

betalningsdatumet beräknas inte på buffertdagar. När ett projekt är klart och alla kostnader och faktureringen är slutförda, bokförs både kostnader och försäljning i resultaträkningen. 

När all försäljning och alla leverantörsfakturor har slutförts kan du visa relationen mellan fälten på sidan **Kassaflöde** och fälten på sidan **Projektutdrag**.

:::row:::
    :::column:::
        #### <a name="cash-flow-page"></a>Sidan Kassaflöde
        - Kassainflöden 
        - Kassautflöden
        - Nettokassaflöden
    :::column-end:::
    :::column:::
        #### <a name="project-statements-page"></a>Sidan Projektutdrag
        - Intäkt
        - Totalkostnad
        - Bruttomarginal
    :::column-end:::
:::row-end:::

### <a name="review-costs"></a>Granska kostnader

Du kan övervaka kostnaderna som din organisation kan ådra sig under ett projekt på sidan **Kostnadskontroll**. Genom att jämföra de ursprungligen budgeterade kostnaderna för projektet med de aktuella faktiska kostnaderna och de utfästade kostnaderna, kan du bestämma om projektet följer budget eller ligger över eller under. 

> [!NOTE] 
> När du använder sidan **Kostnadskontroll** för att visa aktuell status på projektkostnaderna, ska du använda prognosmodellerna som valdes till den ursprungliga och resterande budgeten. Om du väljer andra modeller när du uppskattar kostnader, blir beräkningsresultatet inte korrekt.

#### <a name="viewing-the-remaining-budgeted-amounts"></a>Visa de resterande budgeterade beloppen

Om **Resterande budget** är markerad som kostnadskontrollmetod på sidan **Parametrar för projekthantering och redovisning**, beräknar sidan **Kostnadskontroll** kostnader som inte har blivit bokförda som faktiska eller markerade som utfästa. Beloppen på fliken **Allmänt** i det nedre fönstret på sidan **Kostnadskontroll** beräknas på följande sätt:

-   **Faktisk kostnad** – det totala beloppet som har lagts på projektet för den valda kostnadsraden. Det faktiska kostnadsbeloppet beräknas på sidan **Redovisningsuppdateringar**.
-   **Utfästa kostnader** – det ytterligare beloppet för utgifter som den juridiska personen har lovat att betala. De specifika utfästa kostnadsbeloppen beräknas på sidan **Utfästa kostnader**.
-   **Resterande budget** – originalbudgetbeloppet som fortfarande är tillgängligt för den valda kostnadsraden. Det resterande budgetbeloppet beräknas på sidan **Förhandsgranskning av huvudbok**.
-   **Totalkostnad** – summan av den faktiska kostnaden, den utfästa kostnaden och det resterande budgetbeloppet.

På fliken **Avvikelse** på sidan **Kostnadskontroll** kan du visa en jämförelse mellan den totala förväntande kostnaden och den ursprungliga budgeten. Denna jämförelse visar eventuella skillnader mellan dessa belopp. Därför kan du se var uppgifterna inte stämmer. Avvikelsebeloppen beräknas på följande sätt:

-   **Ursprunglig budget** – det belopp som ursprungligen budgeterades för den valda kostnadsraden. Det ursprungliga budgetbeloppet beräknas på sidan **Förhandsgranskning av huvudbok**.
-   **Totalkostnad** – summan av den faktiska kostnaden, den utfästa kostnaden och resterande budget enligt fliken **Allmänt**.
-   **Avvikelse** – skillnaden mellan totalkostnaden och den ursprungliga budgeten.
-   **Avvikelse baserad på kvantitet** – den totala skillnaden i belopp mellan den ursprungliga prognosen och den totala prognosen. Den här skillnaden kan uttryckas matematiskt som (Total prognoskvantitet) × (Ursprungligt genomsnittligt pris - Totalt genomsnittligt pris). Beräkningen gäller bara projekttimmar.
-   **Avvikelse baserad på pris** – den totala skillnaden i belopp mellan den ursprungliga prognosen och den totala prognosen. Den här skillnaden kan uttryckas matematiskt som (Ursprungligt prognospris) × (Ursprunglig prognoskvantitet - Total prognoskvantitet). Beräkningen gäller bara projekttimmar.

#### <a name="viewing-the-total-budgeted-amounts"></a>Visa de totala budgeterade beloppen

Om **Total budget** är markerad som kostnadskontrollmetod på sidan **Parametrar för projekthantering och redovisning**, beräknar sidan **Kostnadskontroll** de faktiska kostnaderna och totala kostnaderna för projektet för att du ska kunna hitta eventuella skillnader mellan dem. Beloppen i kolumnerna i det nedre fönstret på fliken **Allmänt** på sidan **Kostnadskontroll** beräknas på följande sätt:

-   **Total budgeterad kostnad** – det totala budgeterade beloppet för den valda kostnadsraden.
-   **Faktisk kostnad** – det totala kostnadsbeloppet som har uppkommit i projektet fram till nu för de valda kostnadsraderna.
-   **Utfästa kostnader** – det totala beloppet som har lovats för den valda kostnadsraden.
-   **Avvikelse** – skillnaden mellan summan av de faktiska och utfästa kostnaderna och den totala kostnaden. Avvikelsen anger om ytterligare kostnader måste anges i den totala budgeten.

På sidan **Kostnadskontroll** på fliken **Avvikelse** kan du se skillnaden mellan den totala budgeten och den ursprungliga budgeten i följande fält:

-   **Ursprunglig budget** – det belopp som ursprungligen budgeterades för kostnadsraden. Den ursprungliga budgeten beräknas på sidan **Förhandsgranskning av huvudbok**.
-   **Total budgeterad kostnad** – den totala kostnaden som ursprungligen budgeterades för kostnadsraden. Den totala budgeterade kostnaden beräknas på sidan **Förhandsgranskning av huvudbok**.
-   **Avvikelse** – avvikelsen för kostnadsraden. Beloppet beräknas genom att dra den totala kostnaden från den ursprungliga budgeten.
-   **Avvikelse baserad på kvantitet** – den totala skillnaden i belopp mellan den ursprungliga budgeten och den totala budgeten. Detta belopp beräknas genom att de totala budgeterade timmarna subtraheras från de ursprungliga budgeterade timmarna och sedan multipliceras skillnaden med den ursprungliga budgeterade självkostnaden. Skillnad kan uttryckas matematiskt som (Ursprunglig budgeterad självkostnad) × (Ursprungliga budgeterade timmar - Totala budgeterade timmar). Beräkningen gäller bara projekttimmar.
-   **Avvikelse baserad på pris** – detta belopp beräknas genom att de totala budgeterade timmarna subtraheras från de ursprungliga budgeterade timmarna och sedan multipliceras skillnaden med det totala antalet förbrukade timmar. Skillnad kan uttryckas matematiskt som (Totalt förbrukade timmar) × (Ursprungliga budgeterade timmar - Totala budgeterade timmar). Beräkningen gäller bara projekttimmar.

### <a name="analyze-utilization"></a>Analysera utnyttjande

Utnyttjandegraden är den procent av tiden en anställd utför fakturerbart arbete eller produktivt arbete under en viss period. Fakturerbara timmar är den anställdas timmar som går att debitera på en viss kund. 

En anställds utnyttjandegrad beräknas genom att dela antalet fakturerbara timmar med arbetstiden under en viss period. Om en anställd t.ex. har 30 fakturerbara timmar i en period och arbetstiden i samma period är 40, är utnyttjandegraden 75 procent. 

När du beräknar utnyttjandegraden för en anställd kan du beräkna antingen faktureringsgraden eller effektivitetsgraden:

-   **Andel fakturerbar tid** – differensen mellan fakturerbara timmar och ej fakturerbara timmar eller normtimmar.
-   **Effektivitetsgrad** – differensen mellan produktiva timmar och ej produktiva timmar eller normtimmar. Produktiva timmar är de timmar som den anställda lägger på ett visst projekt. Produktiva timmar faktureras vanligtvis på kunder, förutom i interna projekt. Ej produktiva timmar faktureras aldrig på en kund.

Du beräknar utnyttjandegraderna på sidan **Timutnyttjande**. Beräkningarna baseras på standardinställningarna. Dessa inställningar anger också hur timmar beräknas genom att koppla **Utnyttjande** eller **Ej fakturerbart** till respektive projekttyp. Detta gäller beräkningar av fakturerbar tid och effektivitetsgrad.

-   **Utnyttjande** – timmar som har rapporterats för den valda projekttypen betraktas alltid som fakturerbara eller effektivitetsutnyttjande.
-   **Ej fakturerbart** – timmar som har rapporterats för den valda projekttypen betraktas alltid som ej fakturerbara eller ej effektivitetsutnyttjande.
-   **Enligt radegenskap** – radegenskaperna i en viss timtransaktion bestämmer om timmarna är fakturerbara eller effektivitetsutnyttjade.
-   **Inkluderas inte** – timmar ingår inte i beräkningarna av fakturerbar tid eller effektivitetsutnyttjande.

Förutom den övergripande utnyttjandegraden för en anställd eller ett projekt , kan du på sidan **Timutnyttjande** visa antalet timmar som användes för beräkningar av utnyttjandegraden för var och en av följande timmetyper:

-   **Ej inkluderade timmar** – dessa timmar inkluderas inte i timutnyttjandegraden.
-   **Inkluderade timmar** – timmarna beräknas genom att addera utnyttjandetimmar och ej fakturerbara timmar. Dessa timmar ingår i utnyttjandegraden.
-   **Ej fakturerbara timmar** – om du beräknar en fakturerbar tid, blir dessa timmar samma som ej debiteringsbara timmar. Om du beräknar en effektivitetsgrad, blir dessa timmar samma som ej produktiva timmar.
-   **Timutnyttjande** – om du beräknar en fakturerbar tid, blir dessa timmar samma som debiteringsbara timmar. Om du beräknar en effektivitetsgrad, blir dessa timmar samma som produktiva timmar.

När du beräknar utnyttjandegraden för en anställd, kan du använda normtimmar eller inkluderade timmar. Om du använder inkluderade timmar, måste du se till att den anställda registrerar sina all arbetstid för tidrapportperioderna, eftersom beräkningen uttrycks som en procentandel av timmar som anges. När du beräknar timutnyttjandegraden för ett projekt, ett projektkontrakt, en kundpost eller en kategori, måste du använda inkluderade timmar i beräkningen.

### <a name="review-project-statements"></a>Granska projektutdrag

Du kan skapa ett projektutdrag för att visa en snabb ögonblicksbild av förloppet i ett projekt. När du kör ett projektutdrag, kan du ange villkoren som används för att beräkna utdraget genom att göra val på fliken **Allmänt** på sidan **Projektutdrag**. Du kan inkludera eller utesluta följande information:

-   Projekttyper
-   Transaktionstyper
-   Projektdatum/redovisningsdatum
-   Data

När utdraget har beräknats, kan du visa följande information på de olika flikarna på sidan **Projektutdrag**:

-   **Allmänt** – allmän information om den grundläggande vinst - och förluststrukturen i projektet.
-   **Vinst och förlust** – information om upplupen intäkt.
-   **PIA** – information om PIA-kontosaldon.
-   **Förbrukning** – information om förbrukning av timmar, artiklar, utgifter och lönetransaktioner.
-   **Faktura** – information om fakturor och a conto-fakturering.
-   **Timtariff** – timpriset på timmarna som bokförs på vinst- och förlustkonton.
