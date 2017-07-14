---
title: "Nyheter och ändringar i Dynamics 365 for Operations-programvaruversion 1611 (november 2016)"
description: "Den här artikeln innehåller en beskrivning av nya eller ändrade funktioner i Dynamics 365 for Operations version 1611."
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.search.scope: Operations, UnifiedOperations
ms.custom: 221294
ms.assetid: 357931ed-f843-4bf5-bc85-0da3de0619ec
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 7fd8180bb3ae4ebf5a8dd4446ccd19e65cb6708d
ms.contentlocale: sv-se
ms.lasthandoff: 06/13/2017


---

# Nyheter och ändringar i Dynamics 365 for Operations-programvaruversion 1611 (november 2016)
<a id="whats-new-or-changed-in-dynamics-365-for-operations-version-1611-november-2016" class="xliff"></a>

[!include[banner](../includes/banner.md)]


Den här artikeln innehåller en beskrivning av nya eller ändrade funktioner i Dynamics 365 for Operations version 1611.

Kostnadsredovisning
<a id="cost-accounting" class="xliff"></a>
---------------

<table>




<thead>
<tr class="header">
<th>Vad du kan göra</th>
<th>Varför detta är viktigt</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Definiera dimensioner för kostnadselement och importera dimensionsmedlemmar för kostnadselement.</td>
<td>Kostnadelement används i kostnadsredovisning för att kategorisera kostnader och dokumentera flödet för kostnader. De primära kostnadselementen importeras antingen genom att använda en Microsoft Dynamics 365 for Operations-datakopplingen för att få huvudkonton direkt från Operations eller genom att använda en allmän datakoppling där du får huvudkonton via Microsoft Excel från någon annan typ av källsystem. När huvudkontona har importerats till kostnadsredovisning, används de som dimensionsmedlemmar för kostnadselement. De sekundära kostnadselementen är användardefinierade och används i allokeringar för att dokumentera flödet för kostnader.</td>
</tr>
<tr class="even">
<td>Mappa dimensioner för kostnadselement.</td>
<td>Om huvudkontona mellan dina juridiska personer inte kan delas upp på grund av lagstadgade redovisningsbestämmelser kan du mappa dem efter att du har importerat dem till kostnadsredovisning för att få en holistisk vy över organisationen.</td>
</tr>
<tr class="odd">
<td>Definiera dimensioner för kostnadsobjekt och importera dimensionsmedlemmar för kostnadsobjekt.</td>
<td>Kostnadobjekt är en typ av objekt som kostnader tilldelas till. Typiska kostnadsobjekt inkluderar produkter, projekt, resurser, avdelningar, kostnadsställen och geografiska regioner. Du kan använda antingen en Microsoft Dynamics 365 for Operations-datakoppling för att få ekonomiska dimensioner och värden från Operations eller använda en allmän datakoppling, där du kan få dimensioner och värden från Excel via någon annan typ av källsystem. Om du till exempel använder den ekonomiska dimensionen kostnadsställe är alla kostnadsställen som importeras dimensionsmedlemmarna för kostnadsobjektet.</td>
</tr>
<tr class="even">
<td>Definiera eller importerade statistikdimensioner.</td>
<td>Statistikdimensionsmedlemmar mäts i icke-monetära enheter, till exempel datortimmar, antalet medarbetare och kvadrat. De används i utdrag eller som grund för allokeringar och fördelningar.</td>
</tr>
<tr class="odd">
<td>Skapa providermallar för statistiska mätningar.</td>
<td>En providermall för statistiska mätningar används för att omvandla Dynamics 365 for Operations-data till statistiska mätningar. Mallen associeras sedan med en viss statistikdimensionsmedlem. Mallarna är förfiltrerade, så att de bara visar tabeller som är associerade med ekonomiska dimensioner.</td>
</tr>
<tr class="even">
<td>Skapa huvudböcker för kostnadsredovisning.</td>
<td>En kostnadsredovisning är en agnostisk redovisning som använder sin egen kalender och valuta. Den spelar en viktig roll när det gäller att bearbeta alla kostnadstransaktioner. Till exempel klassificerar en huvudbok för kostnadsredovisning kostnader som baseras på dess egna kostnadselement och tillsätter kostnader baserat på dess egna objektdimensioner. Du kan skapa så många huvudböcker för kostnadsredovisning som du vill för att göra hanteringsrapportering från olika perspektiv.</td>
</tr>
<tr class="odd">
<td>Skapa kostnadsstyrenheter.</td>
<td>Kostnadstyrenheter utgör kostnadsstrukturen och definierar kostnadsflödet i en huvudbok för kostnadsredovisning. De måste associeras med kostnadsobjektdimensioner för att motsvara kostnadsobjektdimensionerna i huvudboken.</td>
</tr>
<tr class="even">
<td>Bearbeta redovisningsposter.</td>
<td>Om du vill mäta faktisk prestanda måste du ha data. Data importeras genom att använda kopplingarna som du definierar för huvudboken för kostnadsredovisning. När du bearbetar redovisningsposterna, importeras data successivt.</td>
</tr>
<tr class="odd">
<td>Bearbeta budgetposter.</td>
<td>Om du vill mäta budgeterad prestanda måste du ha data. Data importeras genom att använda kopplingarna som du definierar för huvudboken för kostnadsredovisning. När du bearbetar budgetposterna, importeras data successivt.</td>
</tr>
<tr class="even">
<td>Skapa och tillämpa kostnadsbeteendepolicyer.</td>
<td>Du använder en kostnadsbeteendepolicy för att klassificera kostnad som fast, variabel eller halvvariabel. En policy är regelbaserad och har giltighetsdatum. Som standard markeras alla kostnader som oklassificerade, tills du använder en kostnadsbeteendepolicy och beräknar effekten av regeln. Efter beräkningen klassificeras kostnaderna.</td>
</tr>
<tr class="odd">
<td>Spårkostnader.</td>
<td>För att hjälpa dig att förstå inverkan av kostnadspolicyer låter kostnadsredovisning dig spåra kostnader till de källvärden och tillämpade regler där de har sitt ursprung. Den här funktionen ger fullständig spårbarhet om när kostnader uppstod, vilka typer av kostnader uppstod och vilka kostnadsbeteenderegler som användes.</td>
</tr>
<tr class="even">
<td>Definiera dimensionshierarkier.</td>
<td>Du kan skapa dimensionshierarkier för antingen kategorisering eller klassificering. Du kan till exempel definiera en kategoriseringshierarki som baseras på en dimension för kostnadselement och dess medlemmar. Alternativt kan du definiera en klassificeringshierarki som baseras på en dimension för kostnadsobjekt och dess medlemmar. Rapporteringstrukturerna används i följande situationer:
<ul>
<li>Du definierar allokeringar, kostnadstariffer och regler för samlade kostnader.</li>
<li>Du visar utdrag genom att använda arbetsytan.</li>
<li>Du definierar åtkomst för att visa aggregerade data.</li>
<li>Du visar data i Excel.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Skapa utdrag som kan visas på arbetsytan.</td>
<td>Använd arbetsytan för att få en snabb överblick över faktiska och budgeterade kostnader och även avvikelser. Du kan filtrera data efter period- eller kostnadnivå. Arbetsytan har utformats för chefer som ansvarar för kostnadskontroll. Den ansluter sig till de åtkomstregler som definierats för dimensionshierarkierna.</td>
</tr>
<tr class="even">
<td>Skapa rapporter genom att använda Excel. <strong>Obs!</strong> Du måste köra Microsoft Excel 2016.</td>
<td>Du kan exportera data för kostnadsredovisning direkt till Excel via datatabeller och använda Microsoft PivotTable om du vill skapa rapporter.</td>
</tr>
</tbody>
</table>

## Utläggshantering
<a id="expense-management" class="xliff"></a>
| Vad du kan göra                                                            | Varför detta är viktigt                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
|----------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Omtilldela uppsagda medarbetares kreditkortstransaktioner.                     | Ibland avaktiveras en uppsagd medarbetares Active Directory DS (AD DS)-konto vid import av aktiva kreditkortstransaktioner som måste kostnadsföras. Tidigare kunde du inte tilldela ett ombud för utgiftsposten eller koppla kreditkortstransaktionerna till en utgiftsrapport. Nu kan du använda sidan **Kreditkortstransaktioner** för att omtilldela medarbetaren för en kreditkortstransaktion där den associerade medarbetaren har sagts upp. När du har omtilldelat kreditkortstransaktionen, kan transaktionerna väljas för en utgiftsrapport och betalas via den vanliga processen för återbetalning av utgiftsrapport. |
| Ändra informationen för kreditkortet för utgifter för väntande och tidigare medarbetare. | Du kan ändra informationen för kreditkortet för utgiftshantering för väntande medarbetare och tidigare medarbetare. Tidigare kunder du bara ändra informationen för kreditkort för utgifter om medarbetaren var en aktiv medarbetare.                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| Kopiera en utgiftsrapport.                                                    | Du kan nu kopiera en befintlig utgift när du skapar en ny utgift på samma utgiftsrapport. Du kan kopiera en utgiftsrapport och alla associerad icke kreditkortsutgifter till en ny utgiftsrapport. Du måste fortfarande utföra alla nödvändiga specifikationer och bifoga obligatoriska inleveranser baserat på definierade utgiftsprinciper och kategorier. Du kan lägga till kreditkortstransaktioner i utgiftsrapporten, genom att välja att lägga till ej avstämda utgifter.                                                                                                                                                                                                                        |
| Bulkredigera utgifter.                                                        | Vissa kreditkortstransaktioner kan inte mappas till en utgiftskategori, eller så kan de mappas på fel sätt när de importeras. I detta fall måste medarbetare manuellt ändra den kopplade utgiftskategorin. När du hanterar de ej avstämda utgifterna kan du nu massredigera utgiftskategorin för de valda utgifterna. Dessutom, när du hanterar valda utgifter för en viss utgiftsrapport, kan du massredigera projektet och den ytterligare informationen.                                                                                                                                                                                    |
| Ändra valutakursen för kreditkortstransaktioner.                     | Den verkliga valutakursen som används för en kreditkortstransaktion, kan skilja sig från den som har ställts in i systemet. Tidigare medarbetare kan inte ändra valutakursen för en kreditkortstransaktion som importerats till utläggshanteringen. Du kan nu ange en parameter på sidan **Parametrar för utläggshantering** om du vill tillåta att valutakursen ändras för kreditkortstransaktioner.                                                                                                                                                                                                                                            |
| Ställ in antikorruptionsattestering för utgifter.                            | En del medarbetare i en organisation kan ha affärer med regeringstjänstemän och en del utgifter som uppstår som en del av den verksamheten kan upplevas som muta. I Utläggshantering kan du nu ställa in en antikorruptionsattestering som visas för valda utgiftskategorier, till exempel måltider och gåvor. Medarbetare måste välja om utgifter som har ställts in för antikorruptionsattestering uppfyller de kriterier som definieras av organisationens policyer.                                                                                                                                                                                     |
| Förhindra manuell registrering av utgifter för specifika utgiftskategorier.          | En kostnadskategori kan ställas in för att representera en kreditkortstransaktion som den kategorin inte kan ändras för. Ett exempel är en avgift för försenad betalning av kreditkortet. Nu kan du ställa in en utgiftskategori som tillåter att utgifter endast skapas via import. Den här funktionen hindrar medarbetare från att manuellt skapa en utgift för kategorin. Med den tillåter inte att kategorin ändras för transaktioner som har importerats och som använder denna kategori.                                                                                                                                                                                   |
| Koppla en inleverans till flera utgifter.                                     | En inleverans som överförs till Utläggshantering kan relateras till flera utgifter. Tidigare måste en inleverans som var relaterad till flera utgifter överföras en gång för varje utgift. Nu kan du koppla en inleverans till en utgift som redan har överförts och har kopplats till en annan utgift på samma utgiftsrapport. Om du överför en inleverans till utgiftsrapporthuvudet kan du välja en eller flera rader att koppla inleveransen till.                                                                                                                                                                                        |
| Skapa framtida utgifter.                                              | När du kopierar en utgiftsrapport, kan till exempel transaktionsdatumet för en utgift ha ett framtida datum. Tidigare versioner tillåter inte framtida utgifter. Du kan nu skapa och spara utgifter som har ett framtida datum. Du kan dock inte skicka in en framtida utgift.                                                                                                                                                                                                                                                                                                                                                                                 |
| Konfigurera utgiftsmoms för en region.                              | I vissa länder/regioner kan utgifter som uppstår i olika regioner bli föremål för olika momssatser. Nu kan du ställa in konfigurationerna för utgiftmoms på regionnivån, inte bara på land-/regionnivå. Om du lämnar fätet **Region** tomt på sidan **Momskonfiguration** gäller momsgruppen för alla regioner för det angivna landet/regionen.                                                                                                                                                                                                                                       |
| Ställ in kreditkortstyper för utgifter.                                          | Tidigare fanns det ingen sida där du kunde skapa nya kreditkortstyper, till exempel Visa, MasterCard eller AMEX som kunde användas med Utläggshantering. Du kan nu skapa kreditkortstyper som ska användas med Utläggshantering. Sidan finns i området **Inställningar** i avsnittet **Beräkningar och koder**.                                                                                                                                                                                                                                                                                                                                                 |
| Definiera ett arbetsflöde på flera nivåer för utgiftsrapporter.                 | Ett nytt arbetsflöde för utgiftsrapporter stöder en godkännandeprocess på flera nivåer. Medarbetare anger interima godkännare och slutliga godkännare när de skapar utgiftsrapporten. Arbetsflödet skickar sedan utgiftsrapporten till de interima godkännarna först. När utgiftsrapporten har godkänts på den nivån, skickar arbetsflödet det till den slutliga godkännaren för slutligt godkännande.                                                                                                                                                                                                                                                                                          |
| Skapa och underhåll utgifter som inte är kopplade till en utgiftsrapport.    | Användaren kan nu skapa och underhålla utgifter (exempelvis genom att koppla eller specificera inleveranser eller tilldela gäster) utan att först skapa en utgiftsrapport. En eller flera utgifter kan väljas och läggas till en ny utgiftsrapport, så att de kan skickas in för godkännande. En ny sida för underhåll av utgifter är tillgänglig på **Utläggshantering** &gt; **Mina utgifter** &gt; **Utgifter**.                                                                                                                                                                                                                                                       |

## Ekonomisk styrning
<a id="financial-management" class="xliff"></a>
<table>




<thead>
<tr class="header">
<th>Vad du kan göra</th>
<th>Varför detta är viktigt</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Spåra värderingar för anläggningstillgångar med ett enstaka "bok"-koncept.</td>
<td>Tidigare där två separata typer av värdering användes för att spåra värden på anläggningstillgångar: värdemodeller och avskrivningsregler. I den aktuella versionen har de två olika koncepten slagits samman till ett enskilt värderingsbegrepp som kallas böcker. Böcker har alla funktioner av både värdemodeller och avskrivningsregler. Du kan till exempel stänga av bokföring i redovisningen. Räkenskapsböcker som inte bokför i redovisningen används normalt för ekonomisk företagsrapportering. Räkenskapsböcker som inte bokför i redovisningen kan användas för momsrapporteringssyften.</td>
</tr>
<tr class="even">
<td>Utför årsbokslutet för flera juridiska personer.</td>
<td>För att påskynda årsbokslutsprocessen kan du nu köra bokslut för flera juridiska personer från en sida för delat bokslut. Grupper av juridiska personer kan definieras tillsammans med inställningar som ska behållas från ett år till nästa. Andra förbättringar av användarbarhet har också gjorts i årsbokslutsprocessen.</td>
</tr>
<tr class="odd">
<td>Ta del av förbättringar av Redovisningomräkningen för utländsk valuta.</td>
<td>Följande förbättringar har gjorts i Redovisningomräkningen för utländsk valuta:
<ul>
<li>En valutakurstyp har lagts till huvudkontot. Den här valutakurstypen används för att bestämma valutakursen under valutaomvärdering. Om ingen valutakurstyp definieras, fortsätter processen att använda den valutakurstyp som definieras i redovisningen.</li>
<li>Det är nu enklare att välja ett intervall med huvudkonton och valutor för att köra omvärderingsprocessen för.</li>
<li>Omvärdering kan köras för flera juridiska personer.</li>
<li>Systemet underhåller nu en historik över varje omvärderingsprocess som utförs, som den gör för Kundreskontra (AR), Leverantörsreskontra (AP) och omvärderingsprocesser.</li>
<li>När du kör processen kan du nu förhandsgranska resultatet av omvärderingen. Förhandsgranskningen visar resultaten för alla juridiska personer som processen körs för. Du kan sedan bokföra alla juridiska personer eller en del av dem från förhandsgranskningen. Du kan också exportera resultaten i förhandsgranskningen till Excel.</li>
</ul></td>
</tr>
<tr class="even">
<td>Visa transaktioner för ytterligare bokföringsskikt.</td>
<td>På listsidan <strong>Råbalans</strong> och rapporten <strong>Dimensionsutdrag</strong> kan du nu välja de ytterligare bokföringsskikten som har lagts till i redovisningen. När du väljer de ytterligare bokföringsskikten, är justeringarna för dessa bokföringsskikt inkluderade i saldon på listsidan eller rapporten.</td>
</tr>
<tr class="odd">
<td>Koppla vägledningsdokumentationen till mallen för räkenskapsperiodens stängning.</td>
<td>Tidigare kan du koppla dokument efter att en uppgift avslutades. Du kan till exempel koppla en rapport som genererades. Nu kan du också bifoga ett vägledningsdokument till mallen. Detta vägledningsdokument kopieras sedan till varje uppgift i tidsplanen för räkenskapsperiod, så att uppgiftsägaren kan visa instruktioner om hur du slutför uppgiften.</td>
</tr>
<tr class="even">
<td>Definiera inställningar för koncernintern redovisning från en delad sida.</td>
<td>Sidan <strong>Inställningar för koncernintern redovisning</strong> delas nu, så att en organisation kan definiera alla par av juridiska personer som kan göra affärer med varandra. Dessutom kan du nu registrera en transaktion i den ursprungliga juridiska personen men inte från den juridiska personen på destinationen. Om någon juridisk person kan starta en koncernintern transaktion, måste det inbördes paret definieras. Därför ställs den juridiska personen på destinationen också in som en ursprunglig juridisk person.</td>
</tr>
<tr class="odd">
<td>Skicka motiveringsdokument för budgetplaner.</td>
<td>Du kan skapa en motiveringmall som kompletterande dokumentet för eventuella begärda budgetbelopp. Användarna kan fylla i obligatorisk information om mallen och koppla en mall på den här planen, så att den kan användas under godkännandeprocessen.</td>
</tr>
<tr class="even">
<td>Aktivera avancerade regler för budgetregisterposter.</td>
<td>Om avancerade regler är konfigurerade i redovisningen, kan dessa regler användas för nya poster och överföringar i budgetregistret.</td>
</tr>
<tr class="odd">
<td>Dra nytta av förbättrad synlighet av förskottsfaktureringsaktivitet.</td>
<td>En ny listsida med <strong>Öppna förskottsbetalningar</strong> ger en ögonblicksbild av statusen för förskottsfaktureringaktivitet. Sidan ger LR-avdelningen information om inköpsorder som har återstående värden för förskottsbetalning som måste faktureras, fakturerade värden som måste betalas och betalade fakturavärden som måste tillämpas på vanliga fakturor. Dessutom hjälper förbättringar av den automatiska tillämpningen av betalda förskottsfakturor till vanliga fakturor faktureringspersonalen att göra effektivare dataregistrering.</td>
</tr>
<tr class="even">
<td>Använd arbetsytan för <strong>leverantörssamarbetesfakturering</strong>.</td>
<td>En ny arbetsyta för <strong>Fakturering</strong> i området <strong>Leverantörsamarbete</strong> ger externa leverantörer säker åtkomst till sin egen fakturainformation. Till exempel kan leverantörer se om en faktura har betalats och skickats in sin egen faktura. Den här ändringen främjar mer effektiv och punktlig kommunikation med externa leverantörer. Därför har faktureringspersonalen mindre avbrott.</td>
</tr>
<tr class="odd">
<td>Växla juridiska personer under fakturaregistrering.</td>
<td>Förbättringar låter faktureringspersonalen som måste ange fakturor för flera juridiska personer snabbt ändra den juridiska personen från faktureringsidorna. Den här funktionen sparar faktureringspersonalens tid, eftersom de inte längre är tvungna att logga ut från den aktuella juridiska personen och logga in på en annan juridisk person. Både sidan <strong>Global fakturajournal</strong> och sidan <strong>Leverantörsfakturor</strong> låter användarna ändra den juridiska personen vid dataregistrering.</td>
</tr>
<tr class="even">
<td>Stöd för elektroniska filer för Internal Revenue Service (IRS) 1099 kombinerade federala/statliga arkiveringsprogram</td>
<td>När konfigurationsnyckeln <strong>USA</strong> aktiveras, ger elektronisk arkiveringsprocess 1099 ytterligare funktioner som överensstämmer med IRS regelverk för det kombinerade federala/statliga arkiveringsprogrammet. IRS har upprättat det här programmet så att det kan elektroniskt vidarebefordra informationsreturer till deltagande stater.</td>
</tr>
<tr class="odd">
<td>Kvittningsförbättringar</td>
<td>Förbättringar hjälper betalningspersonal att göra kvittningar mer effektiva eftersom de kan tillåta att flera ej bokförda betalningar kvittas mot samma faktura.</td>
</tr>
<tr class="even">
<td>Korsföretagsvy</td>
<td>Centraliserad betalningspersonal kan nu visa förfallna fakturor för alla företag. Arbetsytorna <strong>Leverantörsbetalningar</strong> och <strong>Kundbetalningar</strong> kan ge bättre insyn i och kontrollera förfallna fakturor, genom att ange ett sätt för att visa och filtrera mellan företag som ingår i en organisationshierarki med centraliserad betalning.</td>
</tr>
<tr class="odd">
<td>Använd arbetsytan <strong>Bankhantering</strong>.</td>
<td>En ny arbetsyta för <strong>Bankhantering</strong> hjälper till att spåra bankkonton och saldon för dina juridiska personer. Aktuella och väntande saldon är omedelbart tillgängliga för alla konton, och du kan bläddra tillbaka från saldona till de detaljerade transaktionsverifikationerna. Du kan också visa historiska saldodata för varje bankkonto eller en sammanfattning för alla bankkonton i företaget, i både kortfristiga samt långsiktiga vyer. Du kan få bättre inblick i bankkontoavstämning, eftersom datumet för den senaste avstämningen rapporteras för varje bankkonto och det finns även en indikator för avstämningar som pågår.</td>
</tr>
<tr class="even">
<td>Importera elektroniska bankutdrag för alla juridiska personer i ett enda steg.</td>
<td>Du kan nu importera elektroniska bankutdrag för alla juridiska personer i ett enda steg. Bankutdragfiler kan innehålla utdrag från flera bankkonton och juridiska personer och zipfiler kan innehålla flera bankutdragsfiler. Genom att använda en enda importeringsprocess, kan du starta avstämningen för alla rapporterade juridiska personer i alla bankkonton. Den här funktionen låter dig spara tid, eftersom du inte behöver växla mellan företag och flera utdragsimporter. Du kan också automatiskt köra matchande regler mot alla importerade utdrag i varje företag.</td>
</tr>
<tr class="odd">
<td>Värderingsspårning</td>
<td>En enskild anläggningstillgång kan ha flera värderingar för olika redovisningsstandarder och kan även eventuellt bokföra de associerade transaktionerna till redovisningen. Tidigare spårades dessa värderingar, genom att använda antingen värdemodeller eller avskrivningsregler. Nu kan du spåra dessa värderingar, som nu kallas böcker, med hjälp av en gemensam uppsättning journaler, frågor och rapporter. Den sammanslagna upplevelsen förenklar implementeringen och minskar antalet gränssnitt som de periodiska processerna kräver.</td>
</tr>
<tr class="even">
<td>Ta fördel av förbättringar av avskrivningkörningar mellan företag.</td>
<td>Du kan nu börja en avskrivningskörning för tillgångar mellan alla juridiska personer från en enda sida. Du kan också automatiskt bokföra journalerna efter att de har skapats. Du kan skicka skapande och bokföring av journalerna till batchbearbetning, så att avskrivningen körs i bakgrunden. Dessa förbättringar minskar ineffektivitet, eftersom du inte behöver starta enskilda avskrivningkörningar separat för varje företag. Förbättringen ger också bättre centraliserad hantering av dina anläggningstillgångar.</td>
</tr>
</tbody>
</table>

## Administration av humankapital
<a id="human-capital-management" class="xliff"></a>
| Vad du kan göra                                                                                | Varför detta är viktigt                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
|------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Skapa en prestationsjournal.                                                                  | Innan du slutför granskningen samlar du som medarbetare ofta in information om aktiviteter eller händelser som bidragit till framgångarna under granskningsperioden. Du kan lägga till en post in din prestationsjournal för att dokumentera dessa aktiviteter och händelser. Du kan även koppla dessa aktiviteter och händelser till ett mål eller en prestationsgranskning för att tillhandahålla mer information till granskaren.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| Skapa mer detaljerade mål.                                                                    | Du har mer kontroll över innehållet av de mål du anger. Du kan skapa mätningar för målen, länka prestationsjournalposter till mätningarna och koppla och visa dokument. Du kan lagra mål som mallar och återanvända dem för snabba inställningar.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| Skapa mer detaljerade prestationsgranskningar.                                                      | Prestationsgranskning, som tidigare kallades diskussioner, är nu tillräckligt flexibel att stödja både kontinuerlig återrapportering och mer formella granskningar. Du kan dra in aktiva mål och bokföra kommentarer om dem och lägga till avsnitt för en granskning av dina kompetenser. Ytterligare avsnitt ges där du kan lägga till eller visa mått, prestationsjournalposter, bilagor och godkännande som är relaterade till granskningen.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| Associera ytterligare befattningshierarkier med arbetsflöden.                                      | Du kan associera ett arbetsflöde med en befattningshierarki. Du kan också ändra arbetsflödesstegen för att optimera godkännandeprocessen, så att den passar dina affärskrav. Därför kan du definiera en effektiv godkännandestruktur som passar de olika rapporteringsrelationerna som din organisation använder.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| Arbetsflödesupport för att ange PIN-koder i Självbetjäning för medarbetare. | Arbetsflödeskapacitet för Personal (HR) har expanderats och inkluderar nu stöd för PIN-koder. Medarbetare kan lägga till och redigera sin PIN-kod för att förbättra effektiviteten. Emellertid kan personalarbetare granska att den här informationen är korrekt och fullständig innan de lägger till den i medarbetarens post.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| Skapa målmallar och använd dem för att lägga till nya mål.                                          | Du kan skapa målmallar för mål som delas av flera medarbetare i företaget. Medarbetare kan lägga till sina egna mål från en mall, chefer kan lägga till mål för deras grupp från en mall, och personalgruppmedlemmar kan lägga till mål för medarbetare i hela företaget.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| Skapa målgrupper och använd dem för att lägga till nya mål.                                             | Du kan lägga till målmallar till en grupp och använda gruppen för att skapa en eller flera mål för en medarbetare, en grupp, en befattning, en avdelning eller företaget.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| Få mer kontroll över granskningsprocessen.                                                     | Du kan använda ett arbetsflöde för att kontrollera granskningsprocessen. Du kan skapa granskningmallar och använda dem för att skapa granskningar. Du kan också lägga till klassificeringar till en granskning.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| Använd granskningsperioder för att definiera tidsramen för granskningen.                                    | Du kan ange en tidsperiod för en resultatgranskning och start- och slutdatum för granskningen anges automatiskt. Du kan dock ändra de standarddata efter behov.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Öppna fem nya Power BI innehållspaket för personal                                     | Det nya innehållspaketet aktiverar personalorganisationer och personalchefer för att analysera följande: personalmätningar • demografisk uppdelning efter ålder, kön och civilstånd • jämför personalomsättning jämfört med föregående år och se en lista över orsaker som anställda har gett för att lämna organisationen • Visa en lista med öppna positioner, samt en jämförelse mellan öppen och stängd position Ersättningar och förmåner • Jämför timanställda och anställda med fast lön • Visa antalet anställda inskrivna i tillgängliga förmåner • Se anställda efter anställningstyp Rekrytering • Analysera sökande baseras på antalet sökande, var de kommer ifrån och vilka positioner de ansöker om Organisationsutbildning • Kursregistrering efter plats • Kursnärvaro efter status • Förteckning över de anställda som är registrerade på kurser Anställdas färdigheter och utveckling • Lista över färdigheter som innehas av anställda • Fördelning av färdighetstyper efter teammedlem |

## Lokaliseringar
<a id="localizations" class="xliff"></a>
<table>




<thead>
<tr class="header">
<th>Vad du kan göra</th>
<th>Varför detta är viktigt</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Lokaliseringar är tillgängliga för ytterligare 18 länder:
<ul>
<li>Österrike</li>
<li>Belgien</li>
<li>Brasilien</li>
<li>Kina</li>
<li>Tjeckien</li>
<li>Estland</li>
<li>Finland</li>
<li>Ungern</li>
<li>Italien</li>
<li>Lettland</li>
<li>Litauen</li>
<li>Norge</li>
<li>Polen</li>
<li>Saudiarabien</li>
<li>Spanien</li>
<li>Sverige</li>
<li>Schweiz</li>
<li>Thailand</li>
</ul>
Följande länder kräver också Butikslokalisering. Butikslokaliseringen för dessa länder inte har slutförts och planeras endast för H1 CY2017:
<ul>
<li>Brasilien</li>
<li>Tjeckien</li>
<li>Estland</li>
<li>Ungern</li>
<li>Lettland</li>
<li>Litauen</li>
<li>Malaysia</li>
<li>Polen</li>
<li>Sverige</li>
</ul></td>
<td>Dynamik 365 for Operations är tillgänglig i ytterligare 18 länder. Som en del av vårt försök att skapa lokalisering och mer konfigurerbar, har lagstadgade elektroniska rapporteringsfunktioner konverterats till Elektronisk rapportering (ER)-konfigureringar och en del lagstadgade Microsoft SQL Server Reporting Services (SSRS)-rapporter har konverterats till ER-konfigurationer som använder Excel-mallar. Dessa konverterade funktioner nämns specifikt senare i den här tabellen.</td>
</tr>
<tr class="even">
<td>Japan – gruppera anläggningstillgångar när du skriver ut formulär 26 och dess bifogade register.</td>
<td>Formuläret 26 måste skickas in till varje till ort där företaget verkar. För att spara ansträngning när du skriver ut formulär 26 kan anläggningstillgångar automatiskt grupperas och sorteras efter plats.</td>
</tr>
<tr class="odd">
<td>Japan – visa beloppen för accelererad och ytterligare avskrivning i profilen.</td>
<td>Profilen kan ge en exakt uppskattning av beloppen för accelererad och ytterligare avskrivning.</td>
</tr>
<tr class="even">
<td>Japan – Beräkna progressiv källskatt.</td>
<td>Den japanska myndigheter kräver att du beräknar källskatt progressiv, baserat på fakturabeloppet.</td>
</tr>
<tr class="odd">
<td>Japan – Importera postnummerfilen för specifika stora företagsbyggnader.</td>
<td>Postnummerfilen som myndigheten tillhandahåller för specifika stora företagsbyggnader, kan importeras till system. Adressen kan sedan härledas från postnumren.</td>
</tr>
<tr class="even">
<td>Japan – Konfigurera vilande period för anläggningstillgångar.</td>
<td>Vilande perioder tillåter användaren att pausa avskrivning av anläggningstillgången under en viss period. Denna funktion krävs enligt förordningen.</td>
</tr>
<tr class="odd">
<td>Europa – Konfigurera ett momsregistreringsnummer (VAT) för en parts adress, med hjälp av ramverket registrerings-ID.</td>
<td>Du kan konfigurera ett momsregistreringsnummer för en parts adress med ramverket för registrerings-ID samt en ny registreringskategorin för <strong>Moms-ID</strong>.</td>
</tr>
<tr class="even">
<td>Finland – Konfigurera ett tullkundsnummer för en parts adress, med hjälp av ramverket registrerings-ID.</td>
<td>Du kan konfigurera ett tullkundsnummer för en parts adress med hjälp av ramverket för registrerings-ID samt en ny registreringskategori för <strong>tullkunds-ID</strong>.</td>
</tr>
<tr class="odd">
<td>Frankrike – skriva ut kundfakturor i en layout som är specifik för Frankrike.</td>
<td>Kundfakturautskriften justeras för att uppfylla Frankrike-specifika krav.</td>
</tr>
<tr class="even">
<td>Frankrike - Framtvninga kronologiskt numrering av dokument efter räkenskapsperiod.</td>
<td>För att uppfylla Frankrike-specifika krav för numrering av kundfakturor kan du ställa in nummerserier för kundfakturor per räkenskapsperiod.</td>
</tr>
<tr class="odd">
<td>Österrike-lokalisering - ER-konfigurationer</td>
<td><ul>
<li>Filformat för export av lista över försäljning inom EU för Österrike.</li>
<li>Intrastat-format för Österrike</li>
<li>ISO20022 betalningsformat för kreditöverföring för Österrike</li>
<li>ISO20022 betalningsformat för autogiro för Österrike.</li>
<li>Österrikiskt EDIFACT-PAYMUL-format</li>
<li>Momsdeklaration för Österrike</li>
</ul></td>
</tr>
<tr class="even">
<td>Belgien-lokalisering - ER-konfigurationer</td>
<td><ul>
<li>BLWI-format för Belgien</li>
<li>Filformat för export av lista över försäljning inom EU för Belgien</li>
<li>Rapport om anläggningstillgångar för Belgien</li>
<li>Intervat-format för Belgien</li>
<li>Intrastat-format för Belgien</li>
<li>Fakturaomsättningsrapport för Belgien</li>
<li>Exportformat för redovisningstransaktioner för Belgien</li>
<li>SWIFT-leverantörsbetalningsformat för Belgien</li>
<li>CODA-importformat för bankutdrag för Belgien</li>
<li>ISO20022 betalningsformat för kreditöverföring för Belgien</li>
<li>ISO20022 betalningsformat för autogiro för Belgien.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Brasilien-lokalisering - ER-konfigurationer</td>
<td><ul>
<li>GIA-SP för Brasilien</li>
<li>GIA-ST för Brasilien</li>
</ul></td>
</tr>
<tr class="even">
<td>Tjeckien-lokalisering – ER-konfigurationer</td>
<td><ul>
<li>Filformat för export av lista över försäljning inom EU för Tjeckien.</li>
<li>Intrastat-format för Tjeckien</li>
<li>Momsdeklaration för Tjeckien</li>
</ul></td>
</tr>
<tr class="odd">
<td>Kina-lokalisering - ER-konfigurationer</td>
<td><ul>
<li>Format för åldersfördelningsrapport för kunder för Kina</li>
<li>Format för analysrapport av förfallet belopp för kund för Kina</li>
<li>Format för åldersfördelningsrapport för Kina</li>
<li>Format för analysrapport av förfallet belopp för leverantör för Kina</li>
<li>Format för åldersfördelningsanalys av ingående betalning för Kina</li>
<li>Format för saldorapport för kunder för Kina</li>
<li>Format för saldo för huvudbokskontorapport för Kina</li>
<li>Format för saldorapport för Kina</li>
<li>GBT-fil för Kina</li>
<li>Format för Golden Tax-exportfil</li>
<li>Format för produktionsförbrukningavvikelserapport för Kina</li>
</ul></td>
</tr>
<tr class="even">
<td>Estland-lokalisering - ER-konfigurationer</td>
<td><ul>
<li>Filformat för export av lista över försäljning inom EU för Estland.</li>
<li>Intrastat-format för Estland</li>
<li>Lageromklassificeringutdrag för Estland</li>
<li>ISO20022 betalningsformat för kreditöverföring för Estland</li>
<li>Kundsaldomeddelanderapport för Estland</li>
<li>Momsdeklaration för Estland</li>
</ul></td>
</tr>
<tr class="odd">
<td>Finland-lokalisering - ER-konfigurationer</td>
<td><ul>
<li>EU-försäljningslista i TXT-format för Finland</li>
<li>Intrastat-format för Finland</li>
<li>ISO20022 betalningsformat för kreditöverföring för Finland</li>
</ul></td>
</tr>
<tr class="even">
<td>Ungern-lokalisering - ER-konfigurationer</td>
<td><ul>
<li>Filformat för export av lista över försäljning inom EU för Ungern.</li>
<li>Intrastat-format för Ungern</li>
<li>Intrastat förenklat formatet för Ungern</li>
<li>Exportformat för fakturalista för Ungern</li>
<li>Momsdeklaration för Ungern</li>
<li>Specificerad momsdeklaration för Ungern</li>
<li>Lagerutdrag för Ungern</li>
<li>MultiCash-betalningsformat för Ungern</li>
</ul></td>
</tr>
<tr class="odd">
<td>Italien-lokalisering - ER-konfigurationer</td>
<td><ul>
<li>Intrastat-format för Italien</li>
<li>Projektfakturaformat för Italien</li>
<li>Försäljningsfakturaformat för Italien</li>
<li>ISO20022 betalningsformat för kreditöverföring för Italien</li>
<li>ISO20022 betalningsformat för autogiro för Italien.</li>
<li>RIBA-inkassoremissformat för Italien</li>
<li>Rapport för lokala skattetransaktioner för Italien</li>
<li>Rapport för svarta listan för Italien</li>
<li>Modello770-rapport för Italien</li>
<li>Årlig momsredovisningsrapport för Italien</li>
</ul></td>
</tr>
<tr class="even">
<td>Lettland-lokalisering - ER-konfigurationer</td>
<td><ul>
<li>Användningsrapport för kassakvitton (LV)</li>
<li>Filformat för export av lista över försäljning inom EU för Lettland.</li>
<li>Filformat för export av lista över korrigeringar inom EU för Lettland.</li>
<li>Intrastat (A)-format för Lettland</li>
<li>Intrastat (B)-format för Lettland</li>
<li>Lagerräkningslista för Lettland</li>
<li>Lagerräkningsutdrag för Lettland</li>
<li>Lagerrörelse för Lettland</li>
<li>Intern överföringsföljesedel för Lettland</li>
<li>Omklassificeringsdokument för Lettland</li>
<li>ISO20022 betalningsformat för kreditöverföring för Lettland</li>
<li>Momsdeklaration för Lettland</li>
</ul></td>
</tr>
<tr class="odd">
<td>Litauen-lokalisering - ER-konfigurationer</td>
<td><ul>
<li>Filformat för export av lista över försäljning inom EU för Litauen.</li>
<li>Intrastat-format för Litauen</li>
<li>Lagerutdrag för Litauen</li>
<li>ISO20022 betalningsformat för kreditöverföring för Litauen</li>
<li>Rapport för avstämning mellan kund och leverantör för Litauen</li>
<li>Momsdeklaration för Litauen</li>
</ul></td>
</tr>
<tr class="even">
<td>Norge-lokalisering - ER-konfigurationer</td>
<td><ul>
<li>Kravbrevformat för Norge</li>
<li>Autogirobetalningsformat för Norge</li>
<li>Format för AvtaleGiro-kundbetalning för Norge</li>
<li>Format för eFaktura-kundbetalning för Norge</li>
<li>ISO20022 betalningsformat för kreditöverföring för Norge</li>
<li>NETS-betalningsformat för Norge</li>
</ul></td>
</tr>
<tr class="odd">
<td>Polen-lokalisering - ER-konfigurationer</td>
<td><ul>
<li>Intrastat-format för Polen</li>
<li>Lagerställedokument för Polen</li>
<li>Omklassificeringsdokument för Polen</li>
<li>MultiCash-betalningsformat för Polen</li>
<li>MultiCash utländskt betalningsformat för Polen</li>
<li>Kundsaldobekräftelserapport för Polen</li>
</ul></td>
</tr>
<tr class="even">
<td>Saudiarabien-lokalisering - ER-konfigurationer</td>
<td>Rembursavgifter Allokeringsformat för Saudiarabien</td>
</tr>
<tr class="odd">
<td>Spanien-lokalisering - ER-konfigurationer</td>
<td><ul>
<li>EU-försäljningslista i TXT-format för Spanien</li>
<li>Intrastat-format för Spanien</li>
<li>Projektfakturaformat för Spanien</li>
<li>Försäljningsfakturaformat för Spanien</li>
<li>ISO20022 betalningsformat för kreditöverföring för Spanien</li>
<li>ISO20022 betalningsformat för autogiro för Spanien</li>
<li>Format för spansk momsregistreringsbok</li>
<li>Format för summering av spansk momsregistreringsbok</li>
<li>Export av deklaration 347 till ASCII för Spanien</li>
<li>Deklaration 347-rapport för Spanien</li>
</ul></td>
</tr>
<tr class="even">
<td>Sverige-lokalisering - ER-konfigurationer</td>
<td><ul>
<li>Intrastat-format för Sverige</li>
<li>Format för Bankgirot Autogiro-kundbetalning för Sverige</li>
<li>Bankgirot leverantörsbetalningformat för Sverige</li>
<li>SWIFT-leverantörsbetalningsformat för Sverige</li>
<li>SIE-exportformat för Sverige</li>
<li>ISO20022 betalningsformat för kreditöverföring för Sverige</li>
</ul></td>
</tr>
<tr class="odd">
<td>Schweiz-lokalisering - ER-konfigurationer</td>
<td><ul>
<li>Autogiro-betalningsformat för Schweiz</li>
<li>LSV-autogiro-betalningsformat för Schweiz</li>
<li>ISO20022 betalningsformat för kreditöverföring för Schweiz.</li>
<li>ISO20022 autogiro-betalningsformat för Schweiz</li>
<li>ESR-importformat för bankutdrag för Schweiz</li>
</ul></td>
</tr>
<tr class="even">
<td>Tyskland - Exportera leverantörsbetalningar DTAZV-format</td>
<td>Tyskland kräver DTAZV med utländsk formatspecifikation som representerar ett meddelande om kreditöverföring (leverantörsbetalning) enligt specifikationen för gränsöverskridande betalningar från Tyskland till ett konto i utländsk bank eller till en lokal bank i en utländsk valuta. 
</td>
</tr>
</tbody>
</table>

### Elektronisk rapportering
<a id="electronic-reporting" class="xliff"></a>

| Vad du kan göra                                                                                                                                                                                                                                                                                     | Varför detta är viktigt                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Konfigurera ER-rapporter om du vill infoga data i flera format, från dokumenthanteringslagring till elektroniska meddelanden som genereras.                                                                                                                                                              | ER-rapporter kan infoga data i elektroniska meddelanden som skapas från dokumenthanteringslagring. Därför kan bilagorna till ett affärsdokument läggas till i elektroniska meddelanden, som genereras för det dokumentet i enlighet med lagkraven. För närvarande kan dessa bilagor läggas till i MIME-format till ett XML-meddelande som genereras. Alternativt kan bilagorna läggas till i Base64-format till ett binärt meddelande som genereras.                                                                      |
| Konfigurera ER-rapporter för att generera elektroniska handlingar i Excel, Microsoft Word eller PDF-format.                                                                                                                                                                                                      | En konfiguration aktiverar ER-rapporter för att generera elektroniska handlingar i tre olika format: OpenXML kalkylblad (Excel), Word och XML-formulärdataformat (XFDF) (PDF). Användarna kan välja ett format genom att lägga till en formatmall till en ER-rapport som Excel, Word eller PDF-dokument.                                                                                                                                                                                                                                                                       |
| Konfigurera ER-rapporter om du vill infoga data i sidhuvud och sidfötter av elektroniska handlingar, som skapas i OpenXML kalkylbladformat och för att kontrollera sidbrytningar.                                                                                                                               | ER-rapporter kan ange affärsdata i sidhuvud och sidfötter och styr även var sidbrytningar inträffar. Därför kan rapporterna stödja statiska övre och undre avsnitt för sidor i de elektroniska handlingar som genereras. Det går också att stödja viss växling av dessa dokument, så att de överensstämmer med juridiska krav.                                                                                                                                                                                                             |
| Konfigurera målet för ER-rapporter, så att utleveransens skickas som e-postmeddelanden och så att affärsdata och ER-logik (uttryck) kan användas för att ange e-postadressen som ska användas under körning.                                                                                                    | Tidigare när du konfigurerade en ER-destination, kan e-postadress för utleveransens mottagare definieras vid designtillfället. Du kan nu konfigurera ett uttryck i ER-formatet. Detta uttryck kan sedan markeras i en destination som källa för e-postadressen för varje formatkonfiguration och varje utleveranskomponent (mapp eller fil) separat. Därför, när en ER-rapport körs, kan varje fil som skapas, e-postas till en annan mottagare och e-postadressen kan definieras baserat på ER-logik och affärsdata. |
| Konfigurera destinationen för ER-rapporter, så att problemet skickas till Microsoft SharePoint-mappen som antingen en ny namngiven fil eller en ny version av den befintliga filen och så att affärsdata kan användas i ramverket för Microsoft Power BI som antingen en datauppsättning eller en rapport.                 | När du konfigurerar ER-rapporter kan du nu enkelt (utan kodning) förbereda de begärda affärsdata så att den kan användas av Power BI-ramverket. När du kör dessa ER-rapporter kan du erhålla Power BI-ramverket med passande affärsdata och/eller Excel-rapporter som redan är tillgängliga. Om du schemalägger rapportkörningarna i regelbundet återkommande läge, kan du upprätta den schemalagda distributionen av affärsdata från Dynamics 365 for Operations till Power BI för att stödja uppdateringsschemat för Power BI-baserade rapporter.                             |
| Konfigurera ER-rapporter till att använda en del av de elektroniska handlingar som redan har skapats som en datakälla för att generera resten av dokumentet.                                                                                                                                             | Du kan konfigurera ER-rapporter som skapar utleveransen i textformat för att göra dokumentets räkning av rader. Den här informationen kan sedan användas i andra delar av dokumentet för att skapa rader som innehåller sammanfattningsuppgifter. Sammanfattningsuppgifter (summor och nummer) kan beräknas och skrivas ut till de elektroniska handlingarna som skapas, utan att kräva ytterligare transformeringar av data. Därför förbättrar den här funktionen resultatet av rapportkörning och gör framtida underhållet av det konfigurerade ER-formatet enklare.    |
| Konfigurera ER-rapporter för att ange filnamnstillägget för elektroniska handlingar som genereras i textformat.                                                                                                                                                                                 | Du kan konfigurera ER-rapporter om du vill skapa utleveransen i textformat, så att den kan sparas som en fil som har ett specifikt tillägg. Förutom standardtillägget .txt kan du konfigurera tillägg som till exempel .csv och .prn, i enlighet med formatspecifikationen.                                                                                                                                                                                                                                                                             |
| Skapa nya ER-rapporter som baseras på en specifik version av en ER-modell.                                                                                                                                                                                                                          | Tidigare när du skapade ett nytt ER-format, kunde endast den allra senaste versionen av den valda ER-modellen användas som formatets datakällplats. Du kan du välja någon tillgänglig version av den valda ER-modellen. Den här funktionen låter dig underhålla ER-rapporter för innevarande år och utforma en ny version av ER-modellen för nästa år parallellt.                                                                                                                                                                                          |
| Sök datakällor och format/modeller efter text eller den valda artefakten i ett klick. Lös eventuella ombaseringskonflikter och konflikter mellan konfigurationer proaktivt. Konfigurera ER-rapporter om du vill skapa flera valideringsmeddelanden för fel som upptäcks, tills rapportkörningen stoppas. | Flera förbättringar av användarupplevelse (UX) i ER-ramverket hjälper användare att arbeta effektivare och enklare med ER.                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| Visa **ER**-arbetsytan på Power BI-rapporter.                                                                                                                                                                                                                                                      | Användarna kan konfigurera sidan **ER-arbetsyta** så att den innehåller nya menykommandon och levande paneler som kör de Power BI-baserade transaktioner.                                                                                                                                                                                                                                                                                                                                                                                                                       |

## Lön
<a id="payroll" class="xliff"></a>
<table>




<thead>
<tr class="header">
<th>Vad du kan göra</th>
<th>Varför detta är viktigt</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Konfigurera löneposter och bearbeta lönekonton genom att använda funktionen som motsvarar kontoplanens funktion för modulen <strong>Lön</strong> i Microsoft Dynamics AX 2012 R3.</td>
<td>Du kan nu konfigurera och bearbeta amerikansk lönelista, med hjälp av en viss funktion som motsvarar kontoplanens funktion som anges i AX 2012 R3.
<ul>
<li>Du kan konfigurera lönecykler och löneperioder, arbetscykler och arbetsperioder, ersättningskoder och ersättningskodgrupper, tidsplaner, tjänstledighetstyper och förmånsperiodiseringsplaner.</li>
<li>Du kan också ställa in obligatoriska avdrag för både förmåner och moms och registrera löneinformation för befattningar och anställda i rapporterings- och analyssyfte.</li>
<li>Du kan också ställa in och hantera avdrag för löne- och skatteutmätningar och för alla associerade administrativa avgifter.</li>
</ul></td>
</tr>
<tr class="even">
<td>Övervaka och bearbeta din löneperiod genom att använda den nya arbetsytan <strong>Lönehantering </strong>.</td>
<td>Nu kan du enkelt övervaka din lönehantering. På ett ögonblick kan löneadministratörer se inkomst- och löneutdrag som kräver deras uppmärksamhet, så att lönekörningen kan slutföras korrekt. Arbetsytan<strong>Lönehantering </strong>låter användare övervaka och köra slutpunktsprocesser från en enda arbetsyta.</td>
</tr>
<tr class="odd">
<td>Skapa betalningskontrollfiler för lönecheckar.</td>
<td>Det finns ett nytt tillägg för funktionen betalningskontroll i Kassa- och bankhantering för lönebetalningar. Olika menykommandon har lagts till genom hela kärnprocessen för att tillåta isolerade konfiguration som är specifik för lön. Funktionen är identisk med den huvudsakliga betalningskontroll som släpptes i Microsoft Dynamics AX programversion 7.0.1 (maj 2016). Tack vare detta tillägg isoleras lönedata helt från resten av dina transaktioner för betalningskontroll. Den här isoleringen hjälper till garantera att endast löneanvändare kan komma åt och visa data som är relaterade till lönesystemet.</td>
</tr>
<tr class="even">
<td>Importera utdragsrader för inkomster från en extern källa, genom att använda den nya datatabellen inkomstutdragsrader.</td>
<td>En viktig ny datatabell tillåter integration med externa tids- och inkomstberäkningssystem. Datatabellen importerar utdragsrader för inkomster och utför all samma standardlogik som användaren anger direkt på inkomstutdraget. Efter importen associeras raderna automatiskt med lämpligt inkomstutdragsdokument. Om ett lämpligt inkomstutdragsdokument inte existerar, skapas ett dokument automatiskt.</td>
</tr>
</tbody>
</table>

## Planering och schemaläggning
<a id="planning-and-scheduling" class="xliff"></a>
| Vad du kan göra                                                                                                                                                                                                      | Varför detta är viktigt                                                                                                                                                                                                                                                                                                                                                                                                                 |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Ställa in standardorderinställningar för försäljning och inköp baserat på aktiva produktdimensioner på produktmallen. Därför kan du definiera standardorderinställningar för lagerhållningsenhet (SKU) eller en delvis lagerhållningsenhet. | Du kan ange standardorderinställningar som gäller för alla produktdimensioner eller en kombination av produktdimensioner. **Exempel** Du säljer en produkt med namnet Polo T-shirt. Denna produkt är tillgängliga i två färger: grönt och blått. Den är också tillgänglig i två storlekar: small och medium. Färg och storlek är aktiva produktdimensioner för Polo T-shirt. Du kan spärra inköp av alla gröna Polo T-shirt oavsett deras storlek. |

## Produktmalldata
<a id="product-master-data" class="xliff"></a>
<table>




<thead>
<tr class="header">
<th>Vad du kan göra</th>
<th>Varför detta är viktigt</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Ställ in alla standardorderinställningar och sitespecifika orderinställningar samtidigt, från en sida.</td>
<td>Den här funktionen ger en bättre översikt över artikelinställningarna.</td>
</tr>
<tr class="even">
<td>Skapa en nomenklatur för produktvariantnummer</td>
<td>Du kan inkludera element som produktdimensioner, attribut och tecken i dina produktvariantnummer. När du skapar en försäljningsorder eller inköpsorder kan du snabbt hitta en specifik produktvariant.</td>
</tr>
<tr class="odd">
<td>Sök efter produkter och produktvarianter i försäljnings- och inköpssituationer.</td>
<td>När du skapar försäljningsrader eller inköpsrader, kan du söka efter produkter genom att använda produktdimensioner och eventuella produktnummer förutom EAN-artikelnummer (GTIN) och streckkoder. Dena sökning är fulltextsökning som ersätter den befintliga "Börjar med"-sökning som används i söklistan för försäljning och inköp. Den här funktionen låter dig hitta grupper med produkter som har liknande egenskaper eller en enskild produkt, som har unika egenskaper. För att aktivera den här funktionen väljer du parametern <strong>Aktivera uppslag för produktsökning</strong> på sidan <strong>Sökparametrar</strong> .</td>
</tr>
<tr class="even">
<td>Ange produktvarianten direkt när du skapar en försäljnings- eller inköpstransaktion. Alternativt kan du välja i en lista med giltiga dimensionskombinationer.</td>
<td>Den här funktionen är en produktivitetsförbättring. <strong>Exempel</strong> Du säljer en produkt med namnet Polo T-shirt. Denna produkt är tillgängliga i två färger: grönt och blått. Den är också tillgänglig i två storlekar: small och medium. Färg och storlek är aktiva produktdimensioner för Polo T-shirt. När du anger en försäljningsrad för Polo T-shirt som är av grön färg och med storlek small, måste du inte ange data i fälten <strong>Artikelnummer</strong>, <strong>Färg</strong> och <strong>Storlek</strong> Du kan skapa raden genom att följa ett av följande steg:
<ul>
<li>I fältet <strong>Artikelnummer</strong> anger du produktvariantnumret, värdet för en färg eller storleken. Hitta den specifika varianten som du vill sälja, och skapa försäljningraden i uppslaget.</li>
<li>I fältet <strong>Artikelnumret</strong> anger du artikelnumret. Gå till något fält för produktdimension. I uppslaget <strong>Produktdimension</strong> kan du se alla frisläppta dimensionskombinationer som gäller för Polo T-shirt. I ett steg kan du välja produktvarianten som du vill sälja.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Ange om produktnummer visas på transaktionssidorna.</td>
<td>Transaktionssidorna som till exempel försäljningsorder och inköpsorder, visar bara fälten <strong>Artikelnummer</strong> och <strong>Produktnamn</strong>. För att se fältet <strong>Produktnummer</strong> väljer du parametern <strong>Visa produktnummer i formulär</strong> under <strong>Parametrar för produktinformationshantering</strong>.</td>
</tr>
</tbody>
</table>

## Projekthantering och redovisning
<a id="project-management-and-accounting" class="xliff"></a>
| Vad du kan göra                                                                                                           | Varför detta är viktigt                                                                                                                                                                                                                                                                                                             |
|---------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Använd sent val när du bokför fakturaförslag i en batch.                                                            | Projektrevisorer kan ställa in ett batchjobb automatiskt till att plocka upp fakturaförslag för bokföring, om dessa förslag uppfyller de villkor som anges i batchjobbet. Den här funktionen förbättrar automationen för fakturabokföring, eftersom batchjobbet kan köras kontinuerlig och automatiskt plocka in förslag för bokföring. |
| Skapa analyser i Power BI-skrivbordet.                                                                                     | Business intelligence (BI)-innehåll för projektrelaterade och resursrelaterade data kan enkelt skapas i Power BI-skrivbordet.                                                                                                                                                                                                       |
| Använd förskottsbetalningar för inköpsorder och inkludera dem korrekt i projektets uppskattningsbearbetning.                               | För projektinköpsordrar, måste förskottsbetalningar behandlas innan någon betalning kan frisläppas till leverantörer. Dessa förskottsfakturor visas projektuppskattning-/erkännandeprocessen av typen **Fast pris**.                                                                                           |
| Ta fram och hantera kostnads- och intäktuppskattningar och artikelbehov, direkt från en uppdelad arbetsstruktur (WBS)-uppgift. | Du kan hantera kostnadsuppskattningar, intäktsuppskattningar och artikelbehov för en viss uppgift som WBS-uppgift i detaljdialogrutan för den uppgiften i WBS-planeringsvyn.                                                                                                                                                                 |
| Plocka en finansieringskälla på avgiftsjournaler.                                                                                    | Om avtalet för ett projekt innehåller flera finansieringskällor, kan du välja en specifik finansieringskälla när avgifter bokförs. Om du inte väljer en specifik finansieringskälla, kommer finansieringsreglerna som anges i avtalet att användas för att fördela avgiften.                                                                   |
| Öppna projektutdrag i Excel.                                                                                         | Nya datatabeller för redovisningsuppdateringar och budgetuppdateringar låter dig öppna projektutdragsdata i Excel och skapa analyser med Excel-funktionen.                                                                                                                                                                           |
| Använd bara en konfigurationsnyckel för att aktivera funktionen för projekthantering och redovisning (PMA).                       | De projektrelaterade konfigurationsnycklarna har ersatts med en projektkonfigurationsnyckel som aktiverar PMA-funktionen.                                                                                                                                                                                                       |

## Butik och handel
<a id="retail-and-commerce" class="xliff"></a>
### Avancerad lagerstyrning i en butik
<a id="advanced-warehouse-management-in-a-retail-store" class="xliff"></a>

Återförsäljare kan använda den avancerade lagerstyrningslösningen för (WHS) i sina butiker och göra nödvändiga uppdateringar för de aktuella kassafunktionerna (POS) för att kunna använda den. Följande processer för den handhållna lösningen bör fungera i en butik, som de gör på alla lagerställen. Alla aktuella butiklagerprocesser och eventuella kassaprocesser som skapar eller uppdaterar lagertransaktioner, uppdateras så att de använder företagskontots specifika krav för WHS-aktiverade lagerställen.

| Vad du kan göra                                                                       | Varför detta är viktigt                                                                                                                                                                                                                          |
|---------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Använd kassan för att gör uppslag i tillgängligt lager i WHS-aktiverade butiker.                     | När du gör uppslag i lager bör processen fungera på samma sätt som tidigare. Uppslaget bör visa de tillgängliga kvantiteterna på lagernivå och bör inte beakta plats, lagerstatus eller registreringsskyltdimensioner. |
| Använd kassan när du vill bearbeta en produktinleverans för en överföringsorder i en WHS-aktiverad butik. | Du kan ta emot överföringsorder i kassan för en WHS-aktiverad butik och artiklar. Användaren ska kunna välja platserna för mottagning och ska kunna ange registreringsskylt-ID för att automatiskt fylla i mottagningsrader.    |
| Använd kassan när du vill bearbeta en produktinleverans för en inköpsorder i en WHS-aktiverad butik. | Du kan ta emot inköpsorder i kassan för en WHS-aktiverad butik och artiklar. Användaren ska kunna välja platserna för mottagning och ska kunna ange registreringsskylt-ID för att automatiskt fylla i mottagningsrader.    |
| Använd kassan när du vill bearbeta en produktförsändelse från en WHS-aktiverad butik               | Du kan registrera överföringar från kassan för en WHS-aktiverad butik och artiklar. Användaren ska kunna välja platserna som försändelsen ska skickas från, lagerstatus ska genereras automatiskt och registreringsskyltar ska ignoreras.         |

### Aktivera sömlös omni-kanalkommers
<a id="enable-seamless-omni-channel-commerce" class="xliff"></a>

Sömlös omni-kanalkommers refererar till hantering och orderbearbetning mellan fysiska butiker, online-butiker, callcenter och mobila kommerserfarenheter. För den här versionen har följande investeringar gjorts inom detta område:

-   Förbättringar att publicera för nätbutiker
-   En ny konsumentinriktad mobilapp som aktiverar produktupptäckt, kontohantering och näthandel

| Vad du kan göra                                                                                                                                                                                                                                                                   | Varför detta är viktigt                                                                                                                                                            |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Konsument: Den aktuella versionen av konsumentinriktade appen aktiverar följande funktioner: produktsökning, kategoribläddring, lägg till i kundvagn och gästutcheckning. Återförsäljare kan även använda företagets varumärkesprofilering till appen och sedan förpacka den till Android och iOS-appbutikerna. | Återförsäljare kan enkelt skapa en konsumentinriktad app som låter deras kunder söka, söka produkter och leverera produkter som en gäst från deras mobila enheter.                      |
| Kunders önskelistor för anslutna online-butiker                                                                                                                                                                                                                             | Oberoende programförsäljare (ISV) kan använda önskelistkontrollen för att låta användarna skapa och hantera flera listor i deras online-butiker och visa/använda dessa listor i kassan. |
| Asynkron kundskapelse via anslutna e-handelsbutiker                                                                                                                                                                                                                  | ISV kan nu skapa kundkonton, även om Commerce Data Exchange: Realtidtjänst inte är tillgänglig.                                                                        |
| Publicera kanalprodukter från Retail Server till tredje partsbutiker.                                                                                                                                                                                                           | Retail Server stödjer nu tjänst-till-tjänst-autentisering. ISV kan använda kanalproduktpublicering från Retail Server till tredje partsbutiker.               |

### Utbyggbarhet
<a id="extensibility" class="xliff"></a>

-   Commerce runtime-projekt är nu stängda från Retail SDK.
-   Enklare distribution och service via Microsoft komponentpaket och ISV-paket för kassa, Retail Server, databaser, betalnings- och maskinvarustationer.

| Vad du kan göra                                                                                                                 | Varför detta är viktigt                                                                                                                                                                                          |
|---------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| CRT/Retail Server: Återförsäljare eller ISV kan utöka CRT via tillägg. Ändringar av infogad kod stöds inte mer. | Om du vill aktivera integration kontinuerlig distribution ska ändringar av infogad kod helt undvikas. Dessutom, för att stödja enkelt upptag av snabbkorrigering utan någon kodsammanslagning och distribution för CRT-komponenter. |

### Anpassade produktrekommendationer
<a id="personalized-product-recommendations" class="xliff"></a>

| Vad du kan göra                                                                                                                                                                                                                                                                        | Varför detta är viktigt                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Visa anpassade produktrekommendationer vid flera beröringspunkter i kassan (POS) för att avgöra vad kunden kan vara intresserad av baserat på deras tidigare inköp, artiklar i deras önskelista och artiklar som andra kunder har köpt online och i fysiska butiker | För återförsäljare med stora kataloger hjälper anpassade rekommendationer kunden att hitta produkter och stärka butikens associerade med intelligent kundbas. Genom att visa upp riktade till en kunds intresse och inköpsvanor kan produktrekommendationer hjälpa återförsäljare med medförsäljning och förbättrad kundvård. I Microsoft Dynamics 365 for Retail är produktrekommendationer utrustade med kognitiva tjänster och Microsoft Azure-maskininlärning. |

### Uppgiftsregistrering i kassan
<a id="pos-task-recorder" class="xliff"></a>

| Vad du kan göra                                                                                                                                                                                                  | Varför detta är viktigt                                                                                                                                                                                    |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Återförsäljare kan använda Uppgiftsregistrering i kassan för att producera utbildningsmaterial, Business process modeler (BPM) och skapa hjälpinformation för att förbättra produktiviteten och göra bättre analys och design av appar. | Om du vill aktivera integration och kontinuerlig distribution ska infogade ändringar helt undvikas. Dessutom, för att stödja enkelt upptag av snabbkorrigering utan någon kodsammanslagning och distribution för CRT-komponenter. |
| Realtidshjälp i kassa.                                                                                                                                                                                           | Kassören/chefen kan få realtidshjälp från kassan för affärsprocess utan att växla kontext.                                                                                                           |

### Butikssystem: Ger sömlös lokal butikserfarenhet
<a id="store-system-providing-a-seamless-on-premises-store-experience" class="xliff"></a>

Butiksystem är ett distributionsval för återförsäljare som hjälper till att driva en uppsättning butiksåtgärder, oavsett om det är i en lokal butik, Microsofts offentliga moln eller kundens eget privata moln. Den här versionen omfattas endast av butik. För att bättre stödja miljöer som har långsam och otillförlitlig nätverksanslutning, måste vi ge ett alternativ för återförsäljare att distribuera kanaldatabas och Retail Server i butiken. Därefter kan de fortsätta köra scenarier för deras huvudsakliga arbete, även om det inte finns någon möjlighet att ansluta till huvudkontor (HQ). Baserat på de olika datapoäng, som inkluderade, teknikteamdiskussioner kundundersökningsresultat och konkurrentanalys, har vi identifierat följande lösningsomfång som den ideala passformen för våra målkunder:

-   Ett självbetjäningspaket är endast tillgängligt för butikssystem.
-   Standardinstallationen är distribution i en box, men anpassad distribution tillåts.
-   Aktivera enkelt distribution/självbetjäning.
-   Retail Server och butiksdatabasen är i butiken, tillsammans med Async-klienttjänsten.
-   Retail Server i butiken kommunicerar direkt med Application Object Server (AOS) i huvudkontor för butikssystem.
-   Stödja korsterminalscenarier där det inte finns någon anslutning till huvudkontor.
-   Retail Modern POS och Cloud POS kommunicerar alltid med Retail Server i butiken.
-   Stödja Retail Modern POS och Cloud POS där det inte finns anslutning till huvudkontor.
-   Stödja en Retail Modern POS-specifik offlinedatabas (som isoleras till varje Retail Modern POS-instans) där det inte finns någon anslutning till huvudkontor.
-   Autentisering baseras på tjänst-till-tjänst endast för butikssystem.
-   Realtidstjänstsamtal stöds inte om det inte finns någon internet-anslutning.
-   Direkt databasanslutning av Retail Modern POS till kanaldatabasen stöds inte.
-   Aktivera telemetri/övervakning.

| Vad du kan göra                                                                                                                                       | Varför detta är viktigt                                                                                   |
|-------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| En återförsäljare hämtar installationsprogrammet för självbetjäning från kanaldatabassidan i Dynamics AX HQ och hämtar konfigurationsfilen.   | Återförsäljaren kan sömlöst kan hämta självbetjäningpaketet.                                          |
| En återförsäljare installerar butikssystemet, genom att använda installationsprogrammet för självbetjäning.                                                                                 | Återförsäljaren kan installera butikssystemet genom att använda självbetjäningspaketet.                                |
| It-chefen konfigurerar butikssystemet i Dynamics 365 for Operations (kanaldatabas, kanalprofil, butik och driftfärdigt paket).             | It-chefen kan enkelt och effektivt konfigurera butikssystemet.                                       |
| En återförsäljare använder Retail Modern POS i den lokala butiken och kan göra realtidsoperationer, till exempel utfärda presentkort om det finns en möjlighet att ansluta. | Återförsäljaren kan utföra realtidsåtgärder från butikssystem, om det finns en möjlighet att ansluta.                |
| En återförsäljare kan synkronisera data från lokala butikssystem till huvudkontor, när det finns möjlighet att ansluta.                                                      | Återförsäljaren kan synkronisera till och från butikssystem, om det finns en möjlighet att ansluta.                              |
| En återförsäljare kan ha säker kommunikation mellan lokala butikssystemet och huvudkontor.                                                                 | Återförsäljaren kan kommunicera säkert från butikssystem, om det finns en möjlighet att ansluta.                     |
| IT-chefen och Microsoft Operations kan övervaka och rapportera i lokala butikssystem (diagnostik- och rapporteringsändringar).                   | IT-chefen och Microsoft Operations kan övervaka butikssystemet på säkert sätt och felsöka effektivt. |

### Universal Windows Platform-app för Retail Modern POS
<a id="universal-windows-platform-app-for-retail-modern-pos" class="xliff"></a>

För närvarande är Retail Modern POS endast tillgänglig som Windows 8.1-program för stationära maskiner och surfplattor och som Cloud POS för webbläsare för stationära datorer surfplattor. I denna version konverteras Retail Moderns POS till Universal Windows Platform (UWP)-app. Den här ändringen kommer att aktivera Retail Modern POS till att köras på alla Windows 10-enheter (dator, surfplatta eller telefon) och till om med växla mellan vyerna för Continuum-aktiverade enheter.

| Vad du kan göra                                                   | Varför detta är viktigt                                                                                     |
|-------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------|
| Aktivera viktig kassafunktion för enheter med liten form. | Retail POS-funktioner är tillgängliga för telefoner och andra små enheter som kör Windows 10. |

## Hantering av underleverantörer
<a id="supply-chain-management" class="xliff"></a>
### Försändelselager
<a id="consignment-inventory" class="xliff"></a>

| Vad du kan göra                                                                                                                                                                | Varför detta är viktigt                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Som leverantör kan du spara råmaterial på kundens lagerställe. Som kund kan du skjuta upp det faktiska inköpet tills råmaterial krävs för produktionen. | Att hålla ett lager med råmaterial kan omfatta stora kostnader. Genom att använda försändelselager kan en leverantör lagra råmaterial på kundens lagerställe. Som kund kan du skjuta upp det faktiska inköpet tills råmaterial krävs för produktionen. Råmaterial beställts och tas emot med hjälp av en order för försändelseåteranskaffning. Denna order för återanskaffning bokför fysiska transaktioner med inte redovisningen. Om du vill skilja mellan kundägda lagerartiklar och leverantörsägde lagerartiklar kan du använda lagerägarskapsdimensionen. Ändring av ägarskapet för lager utförs av en journalprocess som hanterar överföringen av ägarskapet för råmaterial från det leverantörsägda lagret till kundägda lagret. Den här processen utlöser genereringen av en inköpsorder och en produktinleverans. **Obs!** Den här funktionen begränsas till den inkommande leveransen av råmaterial för produktion. Den integreras inte med Lagerstyrning (WHS) och Transporthantering (TMS). |
| Som leverantör får du information om beloppet för det avsända lagret som överförs till kunden.                                                                      | Om du vill fakturera en kund, kräver leverantören information om det råmaterial som köpts från försändelselagret och datum för inköpet. Leverantören kan också övervaka det lokala lagret hos en kund med hjälp av leverantörsamarbetesgränssnittet.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| Flytta det leverantörsägda lagret, med hjälp av en överföringsjournal.                                                                                                                       | För att spåra den fysiska positionen av de leverantörsägda lagret måste du kunna registrera positionen i systemet. Genom att använda en överföringsjournal kan du registrera den fysiska flyttningen av lager, som till exempel flytt från en plats på ett lagerställe till en annan plats på det lagerstället.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| Justera det leverantörsägda lagret, med hjälp av en inventeringsjournal.                                                                                                                     | Det är viktigt att du synkroniserar systemlagerbehållningen med det faktiska fysiska lagret. Det leverantörsägda lagret kan justeras in och ut, med hjälp av redovisningsprocesser som t.ex. kvantitetsjustering och inventeringsjournal.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| Få mer information om försändelsesupport i Dynamics 365 for Operations                                                                                                         | För mer information om support för försändelseprocesses, se [Försändelse](/dynamics365/unified-operations/supply-chain/inventory/consignment), [Ställa in försändelse](/dynamics365/unified-operations/supply-chain/inventory/set-up-consignment), [Skapa en order för försändelseåteranskaffning (uppgiftsgudie)](http://ax.help.dynamics.com/en/wiki/create-a-consignment-replenishment-order/) och [Ändra ägarskapet för försändelselagret baserat på produktionsbegäran (uppgiftsgudie)](http://ax.help.dynamics.com/en/wiki/change-the-ownership-of-consignment-inventory-based-on-production-demand/).                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |

### Leverantörssamarbete (tidigare känt som leverantörsportalen)
<a id="vendor-collaboration-previously-known-as-the-vendor-portal" class="xliff"></a>

| Vad du kan göra                                                                      | Varför detta är viktigt                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |
|--------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Låt leverantörer svara på varje inköpsorderrad och föreslå ändringar.           | I vissa fall vill leverantörer acceptera en del inköpsorderrader men avvisar andra. Leverantörer kan nu individuellt hantera inköpsorderrader. Varje rad kan avvisas, accepteras eller accepterats med ändringar. T.ex. kan leverantörer ändra leveransdatumet, dela leverans och kvantitet eller föreslå en alternativ artikel.                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| Aktivera leverantörer om du vill hantera information om kontaktperson.                                 | Leverantörer kan behålla kontaktpersoninformation för det deras företag. Denna information omfattar namn och telefonnummer, e-postadress. Åtkomst till den här funktionen beviljas genom en dedikerad säkerhetsroll.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| Dela dokument relaterade till inköpsorder med leverantörer.                    | När du måste dela ett dokument med en leverantör, till exempel ett dokument om behov, är det lämpligt att koppla dokumentet till den relevanta inköpsordern. Leverantören kan sedan dela anteckningar och bilagor med kunden, genom att koppla dokumentet till hans eller hennes svar på inköpsordern. Dokumenthantering är det underliggande stödjande ramverket och bara anteckningar och bilagor som klassificeras som ”externa” kan delas med leverantörer.                                                                                                                                                                                                                                                                                                                              |
| Reservera nya leverantörsanvändare.                                                          | Om dina leverantörer använder leverantörsamarbetesgränssnittet har ett sömlöst sätt att begära nya användarkonton, när nya kontakter behöver åtkomst till leverantörssamarbete. Anskaffningsproffs kan skicka in begäran om ett användarkonto för en kontaktperson på leverantörsorganisationen. En leverantörskontaktperson som redan är en leverantörssamarbetesanvändare kan också skicka in den här typen av begäran. Denna begäran skapar slutligen en ny användare i Dynamics 365 for Operations som har leverantörspecifika säkerhetsroller. Den underlättar också begäran till Microsoft Azure B2B-portalen att ge användaren ett nytt Azure Active Directory (Azure AD)-användarkonto). Leverantörer kan också begära att specifika leverantörsanvändarkonton inaktiveras, eller att säkerhetsroller ändras. |
| Få mer information om support för leverantörssamarbete i Dynamics 365 for Operations. | Mer information om leverantörssamarbete finns i [Leverantörssamarbete med externa leverantörer](/dynamics365/unified-operations/supply-chain/procurement/vendor-collaboration-work-external-vendors), [Leverantörssamarbete med kunder](/dynamics365/unified-operations/supply-chain/procurement/vendor-collaboration-work-customers-dynamics-365-operations), [Hantera användare av leverantörssamarbete](/dynamics365/unified-operations/supply-chain/procurement/manage-vendor-collaboration-users), [Skapa och underhåll leverantörssamarbeten](/dynamics365/unified-operations/supply-chain/procurement/set-up-maintain-vendor-collaboration) och [Faktureringsarbetsyta för leverantörssamarbeten](/dynamics365/unified-operations/financials/accounts-payable/vendor-portal-invoicing-workspace).                                                         |

### Koncerninterna orderbearbetning
<a id="intercompany-order-processing" class="xliff"></a>

<table>




<thead>
<tr class="header">
<th>Vad du kan göra</th>
<th>Varför detta är viktigt</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Definiera direkt på försäljningsorderrader, där efterfrågan ska anskaffas från och hur den ska anskaffas. <strong>Exempel</strong> Skapa en försäljningsorderrad och ange en direktleverans som leveranstyp. Den primära leverantören läggs till i försäljningsorderraden som anskaffningspunkt.</td>
<td>Flödet för ordertagning har förbättrats märkbart. Du kan nusefiniera direkt på försäljningsorderrader, där efterfrågan ska anskaffas från och hur den ska anskaffas. Du behöver inte längre vänta tills alla rader har lagts till i försäljningsordern. Nya alternativ på försäljningsorderrader låter dig ange leveranstypen, när du anger en leverantör. När du kopplar en leverantör med försäljningsorderrader, skapas orderkedjor för leverans från leverantören.
<ul>
<li>Leverantören kan vara en koncernintern leverantör som använder en intern inköpsorder och försäljningsorder, eller kan vara en extern leverantör som använder en extern inköpsorder.</li>
<li>Leveranstypen kan vara <strong>Direktleverans</strong> eller <strong>Lager</strong>. Leveranstypen <strong>Lager</strong> anger att leverantören ska leverera till det lokala lagret innan det skickar till kunden.</li>
</ul></td>
</tr>
<tr class="even">
<td>Skapa ett orderlöfte direkt från försäljningsorderrader. <strong>Exempel</strong> Skapa en försäljningsorderrad som är anskaffade från en koncernintern leverantör. Lämna raden. Leveransdatum beräknas enligt tillgänglighet i anskaffningsföretaget.</td>
<td>När du skapar försäljningsorderrader som använder den nya anskaffningsinformationen, beräknas leveransdatum enligt kontrollen <strong>Leveransdatum</strong> . Om till exempel en koncernintern leverantör markeras beräknas tillgängligheten i anskaffningsföretaget. På så sätt skapas automatiskt orderkedjor tillsammans med försäljningsorderrader. Den här funktionen hjälper till att garantera att leveransdatum blir synliga i anskaffningsföretaget, så att disponibelt att lova-profilerna (ATP) kan hantera den planerade efterfrågan direkt när försäljningsordern skapas.</td>
</tr>
<tr class="odd">
<td>Granska produkttillgänglighet för alla anskaffningsplatser och välj det översta anskaffningsalternativet.</td>
<td>Sidan <strong>Leveransalternativ</strong> har omformats och ger nu värdefull information om alla godkända interna och externa leverantörer. Denna information omfattar anskaffningsalternativ för leverantörsanskaffning. När du väljer ett leveranssätt, beräknar systemet möjliga leveransdatum. Du kan sömlöst välja det bästa alternativet för kunden och använda det här alternativet för varje försäljningsorderrad.</td>
</tr>
</tbody>
</table>

### Lagerställeförbättringar för distributionscenter med hög volym
<a id="warehouse-enhancements-for-high-volume-distribution-centers" class="xliff"></a>

| Vad du kan göra                                                              | Varför detta är viktigt                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
|------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Skapa arbete, när varorna har packats på en emballagestation.               | Den här funktionen är användbar, om det finns ytterligare processer efter manuellt emballagearbete (till exempel palletering, kvalitetskontroll, konsolidering av leveranser eller ändringar av lastplatser). Den nya arbetstypen **Plockning för packad behållare** låter dig utforma dessa uppgifter, genom att använda separata arbetsrader. Du kan nu utforma emballagestationer för att generera arbete efter att du har packat. Detta arbete kan användas för att organisera flyttning av packat lager.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Gruppera behållare på förpackningsstationen.                                     | Den här funktionen aktiverar flera förpackningar som ska grupperas i en behållare eller registreringsskylt på emballagestationen. Till exempel kan en e-handlare/grossist gruppera 100 individuellt packade paket till en gemensam behållare (till exempel en lastpall eller en lagerhållare). Denna behållare kan sedan flyttas, mellanlagras eller lastas genom en enskild arbetsinstruktion som en arbetare genererar genom att skanna en enskild streckkod (registreringsskylt) för den grupperade behållaren. Den här funktionen minimerar arbetstransaktionerna för att flytta många mindre packade behållare. Mer information finns på [Skapa ett nytt menyalternativ för mobila enheter för avstämning av registreringsskylt](http://ax.help.dynamics.com/en/wiki/create-a-mobile-device-menu-item-for-license-plate-consolidation/).                                                                                                                                                                                                                                                                                                                                                                                            |
| Skapa en leveranspolicy för packade behållare.                               | Arbete som utlöses av frisläppning av behållare kan skapas automatiskt eller manuellt. När den är automatisk, genereras arbete vid stängning av behållare med hjälp av ramverket för platsdirektiv och arbetsmallen. När frisläppningen är manuell, kan packaren bestämma om arbetet ska skapas för en enda behållare eller för en grupp med behållare. Den här funktionen minskar risken att stängda behållare ska plockas och flyttas, innan de är klara att flyttas från förpackningsstationen. Med den tillåter även icke-systemstyrd grupperad frisläppning.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| Omfördelning av kortplockning                                                   | Support har lagts till för kortplockningsprocesser, för att hjälpa en associerad som inte kan plocka varorna och vill uppfylla ordern, när artikeln som krävs, är tillgänglig på en annan plats. Det går att använda en automatisk omallokeringsprocess som använder platsdirektiv för att hämta varorna, om dessa är tillgängliga på en annan plats. Alternativt, när manuell omfördelning används visar den mobila enheten en lista över platser tillsammans med den tillgängliga kvantiteten. Lagerställearbetaren kan sedan välja vilken plats att använda lager från. Dessa två metoder kan kombineras individuellt eller kombineras som ett enda kommando på lagerställearbetarens meny. När den manuella omfördelningen används, kan lagerställearbetaren plocka den kortplockade artikelkvantiteten från flera platser. Mer information finns på [Skapa omallokering av artiklar för kort plockning (uppgiftsguide)](http://ax.help.dynamics.com/en/wiki/set-up-short-picking-item-reallocation/).                                                                                                                                                                                          |
| Flytta lager som har arbete associerat.                             | Du kan nu flytta lager som har arbete associerad till den. Den här funktionen kan vara användbar om till exempel en arbetare vill rensa lite inlastningsplatsutrymme och flyttar registrerade lastpallar som väntar på att ställas undan till en annan inlastningsplats. Inlastningsplatsen rensas kan ta emot ytterligare en last med varor och lagret som har flyttats är uppdaterat med ny platsinformation. Den här funktionen kan också användas för frigöra utrymme på plockplatser, genom att flytta lagret som har arbete associerat och skapa utrymme för lagerpåfyllnad. Du kan också använda den för att flytta laster från en fas till en annan plats, utan att förlora lastarbetet som har skapats. På så sätt kan funktionen optimera den tid som krävs för att lasta lastbilar när de ankommer. Du kan flytta lagret som har reserverats för försäljningsorder, överföringsorderutleveranser, överföringsorderinleveranser och inköpsorder. Rörelse förhindras om det kommer att orsaka att rader delas. Om du till exempel har en arbetsrad för 100 enheter av en artikel, kan du inte flytta endast 30 enheter av den artikeln till en annan plats. |
| Slå samman registreringsskyltar som har arbete associerat.                    | Du kan slå samman registreringsskyltar som har utgående arbete associerat. När till exempel en plockning har delats upp i flera delar av arbete, kan det vara praktiskt att tillåta att registreringsskyltarna slås samman, när de har levererats på mellanlagringsplatsen. Registreringsskyltar kan endast konsolideras om de är på samma plats, är medlemmar i samma last och har samma information om försändelsen.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| Frysa plockningsarbete som associeras med Mellanlagringsplatsen på radnivå. | Du kan nu frysa arbete på radnivå i stället för på rubriknivå, så att arbetare kan slutföra plockrader som inte är låsta av lagerpåfyllnad för efterfrågan. Därför kan en grossist som har stora försäljningsorder eller en återförsäljare, som har stora försäljningsorder eller återanskaffningöverföringsordrar, tillåta att plockningarbetet startar på alla rader som inte är föremål för lagerpåfyllnadsarbete. Plockningen och lagerpåfyllnadsarbete kan sedan avslutas parallellt. Den här funktionen kan konfigureras, så att du kan välja om du vill frysa på rubriknivå eller radnivå. Du kan också använda båda metoderna och skapa en arbetsmall för varje metod. Rubrik-/radkonfigurationen anges på arbetsmallar, men du kan ändra den direkt på det genererade arbetet.                                                                                                                                                                                                                                                                                                                                                                      |
| Avbryt arbete genom att använda mobila enheten.                                      | Du kan nu avbryta arbete, genom att använda mobila enheten med eller utan lagerpåfyllnad för efterfrågan. Tidigare måste du använda den rika klienten. För att tillåta den här funktionen skapar du ett Menyobjekt för mobil enhet som har läget inställt på **Indirekt** på aktivitetskoden inställd på. **Avbryt arbete**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |

### Förbättring av lagerställeoperationer
<a id="warehouse-operation-enhancements" class="xliff"></a>

| Vad du kan göra                    | Varför detta är viktigt                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
|------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Forma olika behållaretyper.   | Du kan använda olika behållartyper i lagerstället för att optimera lagring och för andra orsaker. Den nya behållartypenheten har de fysiska egenskaperna för behållartyperna. Du kan nu associera registreringsskyltar med en viss behållartyp och använda lagringsbegränsningsplats. Du kan till exempel använda den här funktionen om du vill kontrollera hur många lastpallar (eller andra behållartyper) som du tillåter på en viss plats. Behållartyper också har lagts till enhetsekvensgrupper för att lägga till standardbehållartyper för inleveransen. Behållartyper kan användas med inkommande och utgående platsdirektiv. De kan även användas i lagerbehållningsvyn för att bestämma hur många behållartyper som för närvarande finns i lager. Mer information finns i blogginlägget [Använda registreringsskyltar som är kopplade till en typ av behållare för att påskynda lagerhanteringsprocesser](https://blogs.msdn.microsoft.com/dynamicsaxscm/2016/06/20/use-of-license-plates-associated-with-a-container-type-to-drive-warehouse-management-processes/). Även om det här blogginlägget beskriver en uppdatering till Microsoft Dynamics AX 2012, har samma support nu lagts till Dynamics 365 for Operations.                                                                                                                                                                                                                                                                                                                         |
| Återför leveranser.                 | I ett lagerställe måste du vara en stånd att hantera sena ändringar. Några varor kan till exempel skadas så att du inte kan skicka dem. Alternativt kan en kund göra en sen begäran om att annullera eller ändra en order. Dynamics 365 for Operations låter dig nu återföra en försändelse. Därför kan du avbryta en följesedel, så att du kan uppdatera den senare med de korrekta kvantiteterna. På samma sätt på det inkommande flödet, kan du avbryta produktinleveranser, så att en uppdaterad version kan skapas.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| Använd lastpallar som har blandat artiklar. | Du kan nu ta emot och registrera ”blandad” lastpall. En blandad lastpall består av olika artiklar, som samlas i en lastpall för en eller flera inköpsorder, eller rader. Alla registreringar kan sammanfattas på en målregistreringsskylt. Den här processen har aktiverats genom mobil enhet för lagerställe. När till exempel lastpallen av blandade artiklar ankommer till lagerstället, identifierar inleveransansvarige artiklarna och kvantiteterna på lastpallen innan lastpallen flyttas till dedikerade platser. Platserna anges med arbetsmallar och platsdirektiv. Om platserna fördelas över flera artiklar, som har fasta platser, skapar den här funktionen så många satta inlagringsarbetsrader som det finns olika artiklar på den blandade lastpallen. Den här funktionen gör registreringar och placeringen av mottagna blandade artikellastpallar snabbare och mer flexibel. Mer information finns i blogginlägget [Ta emot och registrera en lastpall med blandade källdokumentrader med hjälp av 1 registreringsskylt – inköpsordermatchning](https://blogs.msdn.microsoft.com/dynamicsaxscm/2016/05/13/receive-and-register-a-pallet-with-mixed-source-document-lines-using-1-license-plate-purchase-order-matching/) och information om support för blandad pallet support i [ finns i tillkännagivandet av vår senaste kumulativa uppdateringen](https://blogs.msdn.microsoft.com/dynamicsaxscm/2016/06/30/whats-new-in-cu11-for-wms-and-tms/). Även om det här blogginlägget beskriver en uppdatering AX 2012, har samma support nu lagts till Dynamics 365 for Operations. |

### Mindre funktionsförbättringar i Hantering av underleverantörer
<a id="minor-feature-enhancements-in-supply-chain-management" class="xliff"></a>

<table>




<thead>
<tr class="header">
<th>Vad du kan göra</th>
<th>Varför detta är viktigt</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Använd nya datatabeller för att importera och exportera data.</td>
<td>Du kan importera och exportera data, genom att använda dessa datatabeller:
<ul>
<li>Fraktfaktura</li>
<li>Sätt samman lagerbehållning enligt lagerställe och lagerstatus</li>
<li>Lagertillägg</li>
<li>Offert</li>
</ul></td>
</tr>
<tr class="even">
<td>Använd den avancerade Gantt-kontrollen om du vill sammanställa interaktiva planeringsscenarier.</td>
<td>Den avancerade Gantt-kontrollen låter dig sammanställa nya interaktiva planeringsscenarier, och leverera förbättrade API, som kan användas till att anpassa utseendet på aktiviteter. Nedan följer några av de nya API:
<ul>
<li>Vertikal dra och släpp av aktiviteter</li>
<li>Lägg till/ta bort aktiviteter</li>
<li>Förhandsgranska bokade perioder i sammanfattningsfält</li>
<li>Ändra färg och typ av aktivitetsgränser</li>
<li>Ändra färg, stil och bakgrund av texten i rutnätet</li>
</ul></td>
</tr>
<tr class="odd">
<td>Bättre hanteringsmaterial och resursplanering.</td>
<td>Vissa förbättringar har gjorts i material- och resursplanläggningen:
<ul>
<li>Utleveransmarginalen hanteras nu, när en artikel är tillgänglig.</li>
<li>Skriv över leveransdatumet när du bekräftar planerade order.</li>
<li>Prioritera uppfyllelse av order över säkerhetslager.</li>
<li>Förhindra tidsplanering av planerade order tidigare.</li>
</ul></td>
</tr>
<tr class="even">
<td>Rapportera verklig förbrukning för produktion och visa lagerstatus.</td>
<td>Du kan visa verklig förbrukning för produktion. Dessutom kan en ny kryssruta för <strong>Visa lagerstatus</strong> som har lagts till i <strong>Rörelse</strong> på menyn <strong>Skapa arbete</strong> låter dig visa lagerstatus.</td>
</tr>
<tr class="odd">
<td>Beräkna volymetrisk vikt, om tarifferna för transportföretaget baseras på volymetrisk vikt.</td>
<td>En ny TMS-tariffmotor, baserad på volymetrisk vikt, har lagts till så att du kan beräkna volymetrisk vikt.</td>
</tr>
</tbody>
</table>



Se även
<a id="see-also" class="xliff"></a>
--------

[Nytt eller ändrat](whats-new-changed.md)




