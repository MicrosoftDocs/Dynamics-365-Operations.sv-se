---
title: "Flöden och operationer"
description: "Det här avsnittet innehåller information om flöden och operationer. Ett flöde definierar processen för tillverkning av en produkt eller produktvariant. (Åtgärd) för varje steg beskrivs i produktionsprocessen, och dessa åtgärder måste utföras i angiven ordning. För varje steg definierar också flödet krävs operationsresurser krävs ställtid och körtid och hur kostnaden ska beräknas."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: BOMDesigner, BOMDesignerRouteVersion, Route, RouteInventProd, RouteOpr, RouteOprTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 268124
ms.assetid: f78d5836-3e71-42b7-a5d1-41f19228d9d2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: f707d45290682e79ee439ba0d504852429defa90
ms.openlocfilehash: 556b9859d0b162b11f0bcbfc6552f6fd9a900596
ms.lasthandoff: 03/31/2017


---

# <a name="routes-and-operations"></a>Flöden och operationer

Det här avsnittet innehåller information om flöden och operationer. Ett flöde definierar processen för tillverkning av en produkt eller produktvariant. (Åtgärd) för varje steg beskrivs i produktionsprocessen, och dessa åtgärder måste utföras i angiven ordning. För varje steg definierar också flödet krävs operationsresurser krävs ställtid och körtid och hur kostnaden ska beräknas.

<a name="overview"></a>Översikt
--------

Ett flöde beskrivs åtgärder som krävs för att producera en produkt eller produktvariant. Flödet definierar också operationsresurser som krävs, tid som krävs för att ställa in och utföra operationen och hur kostnaden ska beräknas för varje operation. Du kan använda samma flöde för att skapa flera produkter eller definiera en unik väg för varje produkt eller produktvariant. Du kan också innehålla flera vägar för samma produkt. I detta fall är beror det flöde som används på faktorer som den kvantitet som måste produceras. Definitionen av ett flöde i Microsoft Dynamics 365 för operationer består av fyra separata element som tillsammans beskriver produktionsprocessen:

-   **Väg** – ett flöde som definierar strukturen i produktionsprocessen. Den definierar alltså utförs.
-   **Åtgärden** – en operation som identifierar en namngiven steg i flödet, **sammansättningen**. Samma åtgärd kan ske på flera flöden och kan ha olika operationsnummer.
-   **Operationsrelation** – definierar en operationsrelation funktionella egenskaper för en åtgärd som ställtid och körtid, kostnadskategorier, förbrukning parametrar och krav på systemresurser. Operationsrelationen kan funktionella egenskaper för en operation kan variera beroende på som används för operationen i flödet, eller produkter som produceras.
-   **Flödesversion** – en flödesversion som definierar vägen som används för att tillverka en produkt eller produktvariant. Flödesversioner kan flöden ska återanvändas mellan produkter eller ändras med tiden. De ger också olika flöden som ska användas för att tillverka samma produkt. I detta fall är beror det flöde som används på faktorer som platsen eller den kvantitet som måste produceras.

## <a name="routes"></a>Flöden
Ett flöde beskrivs åtgärder som används för att tillverka en produkt eller produktvariant. Varje operation tilldelas ett operationsnummer och en efterföljande operation. Ordningen på åtgärderna utgör en flödesnätverket representeras av en riktad diagram med en eller flera startpunkter och en enda slutpunkt. I Dynamics 365 för operationer, skiljer flöden sig beroende på vilken typ av struktur. Två typer av flöden är enkla flöden och flödet nätverk. Du kan ange om endast enkla flöden kan användas eller om mer komplexa flödesnätverk kan användas i produktionsparametrarna kontroll.

### <a name="simple-routes"></a>Enkel flöden

Ett enkelt flöde är sekventiella och det finns bara en startpunkt för flödet.  

[![Enkel flöde](./media/routes-and-operations-1-simple-route.png)](./media/routes-and-operations-1-simple-route.png)  

Om du aktiverar endast enkla flöden i produktionsparametrarna kontrollen operationsnumren genererar automatiskt Dynamics 365 för operationerna (10, 20, 30 och så vidare) när du vill definiera vägen.

### <a name="route-networks"></a>Flödesnätverk

Om du aktiverar mer komplexa Flödesnätverk i produktionsparametrarna kontrollen kan definiera du flöden som har flera inledande punkter och operationer som kan köras parallellt.  

[![Route network](./media/routes-and-operations-2-route-network.png)](./media/routes-and-operations-2-route-network.png)  

**Anteckningar:**

-   Varje operation kan ha endast en efterföljande operation och hela vägen måste sluta på en gång.
-   Det finns ingen garanti för att flera operationer med samma efterföljande operation (exempelvis operationer 30 och 40 i bilden ovan) kommer att köras parallellt. Tillgängligheten och kapaciteten hos resurserna kan sätta begränsningar på väg att åtgärder schemaläggs.
-   Du kan inte använda 0 (noll) som operationsnummer. Detta nummer används för att ange att den sista operationen i flödet har inga efterföljande aktivitet är reserverade.

### <a name="parallel-operations"></a>Parallella operationer

Ibland krävs en kombination av flera operationsresurser som har olika egenskaper för att utföra en åtgärd. En montering kanske till exempel kräver en maskin och ett verktyg för en arbetare för varje två maskiner kan övervaka hur. I det här exemplet kan utformas med parallella operationer där en operation anges som den primära operationen och andra sekundär.  

[![Väg med primära och sekundära operationer](./media/routes-and-operations-3-parallel-operations.png)](./media/routes-and-operations-3-parallel-operations.png)  

Den primära operationen representerar flaskhalsresurs normalt och avgör bearbetningstiden för sekundära operationer. Emellertid som berör ändlig kapacitet under planeringen, resurser som har schemalagts för både den primära operationen och sekundära operationer måste finnas och ha fri kapacitet samtidigt.  

Både den primära operationen och sekundära operationer måste ha samma operationsnummer (30 i bilden ovan).  

I exemplet ovan är Resursbehov för den primära operationen (30) datorn resursbehov för sekundära operationer (30' och 30'') är verktyget och arbetaren. En 50 - procentig beläggning kan garantera schemalagda arbetare kan övervaka två datorer samtidigt.

### <a name="approval-of-routes"></a>Godkännande av flöden

Ett flöde måste godkännas innan den kan användas i produktion och huvudplanering. Godkännande anger att designen flödet har slutförts. Samma frisläppt produkt eller variant frisläppt produkt kan ha flera godkända vägar. Normalt uppstår när den första relevanta flödesversionen godkänns godkännandet av ett flöde. I vissa företag är scenarier, godkännande av flödet och flödesversionen dock separata aktiviteter som kan omfatta olika processägare.  

Varje flöde kan vara godkända eller ej godkända separat. Tänk på att, när ett flöde är ej godkända alla relaterade flödesversioner är inte har godkänts. Du kan ange om flöden kan bli icke-godkända och om godkända flöden kan ändras i produktionsparametrarna kontroll.  

Om du vill hålla en logg som poster som godkänner varje flöde kan du kräva elektroniska signaturer för Flödesgodkännande. Användare måste sedan bekräfta sin identitet med hjälp av en [elektronisk signatur](/dynamics365/operations/organization-administration/electronic-signature-overview).

## <a name="operations"></a>Operationer
En åtgärd är ett steg i produktionsprocessen, t.ex. I Dynamics 365 för operationer har varje operation ett ID och en kort beskrivning. I följande tabell visas vanliga exempel på åtgärder från en affär för datorer.

| Åtgärd  | beskrivning        |
|------------|--------------------|
| PipeCut    | Pipe styckning       |
| TIGweld    | TIG svetsning        |
| JigAssy    | Montering av jig       |
| Inspektion | Kvalitetskontroll |

Operation, t ex den ställtid och körtid resursbehov, kostnadsinformation och förbrukningsberäkning, operativa egenskaper anges i operationsrelationen. (Mer information om operationsrelationer finns i nästa avsnitt.)

## <a name="operation-relations"></a>Operationsrelation
Följande funktionella egenskaper för en åtgärd hanteras på operationsrelationen:

-   Kostnadskategorier
-   Förbrukning-parametrar
-   Bearbetningstider
-   Kvantiteterna för behandling
-   Resurskrav
-   Anteckningar och instruktioner

Du kan definiera flera operationsrelationer för samma operation. Men varje operationsrelationen gäller samtidigt och lagrar egenskaper som är specifika för ett flöde, frisläppt produkt eller en uppsättning frisläppta produkter som hör till en artikelgrupp. Samma åtgärd kan därför användas i flera flöden som har olika funktionella egenskaper. Dessutom kan du lättare underhålla standarduppgifterna om du använder standardåtgärder som har samma funktionella egenskaper, oavsett flödet som används och produkt som produceras. Tillämpningsområde operationsrelationen definieras via den **Artikelkod**, **Artikelrelation**, **flöde kod** och **flöde relationen** egenskaper, vilket visas i följande tabell.

| Artikelkod | Artikelrelation         | Flödeskod | Flödesrelation   | Operationsrelationen tillämpningsområde                                                                                                                                                                                                                                                                              |
|-----------|-----------------------|------------|------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Tabell     | &lt;Artikel-ID&gt;       | Flöde      | &lt;Rutt-ID&gt; | Funktionella egenskaper för en åtgärd vid användning i flödet där **Flödesnummer**=&lt;flödes-ID&gt; att producera slutprodukten där **artikelnummer**=&lt;artikel-ID&gt;.                                                                                                                        |
| Tabell     | &lt;Artikel-ID&gt;       | Allt        |                  | Öppet standardegenskaperna för en åtgärd när det används för att producera slutprodukten där **artikelnummer**=&lt;artikel-ID&gt;. Dessa funktionella egenskaper gäller alltså när det inte finns någon specifik väg operationsrelationen för frisläppt produkt.                                     |
| Grupp     | &lt;Grupp-ID för artikeln&gt; | Flöde      | &lt;Rutt-ID&gt; | Funktionella egenskaper för en åtgärd vid användning i flödet där **Flödesnummer**=&lt;flödes-ID&gt; att producera frisläppta produkter som är kopplade till artikelgrupp &lt;artikel grupp-ID&gt;, såvida det inte finns en specifik väg operationsrelationen för frisläppt produkt.                         |
| Grupp     | &lt;Grupp-ID för artikeln&gt; | Allt        |                  | Öppet standardegenskaperna för en åtgärd när det används för att producera frisläppta produkter som är kopplade till artikelgrupp &lt;artikel grupp-ID&gt;, om det inte finns en mer specifik operationsrelation.                                                                                                  |
| Allt       |                       | Flöde      | &lt;Rutt-ID&gt; | Öppet standardegenskaperna för operationen när det används i flödet där **Flödesnummer**=&lt;flödes-ID&gt;. Dessa funktionella egenskaper gäller alltså när det inte finns någon Operationsrelation för vägen som gäller antingen frisläppt produkt eller det associeras artikelgrupp. |
| Allt       |                       | Allt        |                  | Öppet standardegenskaperna för en operation. Dessa funktionella egenskaper gäller när en mer specifik Operationsrelation inte finns.                                                                                                                                                                |

Du kan ange att en operationsrelation är specifika för en webbplats. På så sätt kan funktionella egenskaper för en åtgärd variera beroende på plats (site) där åtgärden utförs. Du kan ange olika funktionella egenskaper för varje produktkonfigurationen för konfigurerade produkter.  

Operationsrelationer ger stor flexibilitet när du definierar ditt flöden. Dessutom kan du definiera standardegenskaperna bidrar till att minska mängden huvuddata som du måste underhålla. Den här flexibiliteten innebär dock även att du måste känna till det sammanhang som du kan ändra en operationsrelation i.  

**Anmärkning:** eftersom funktionella egenskaper lagras i operationsrelationer per operation, per väg, alla förekomster av samma operation (exempelvis sammansättningen) har samma ställtid, körtid, krav på systemresurser och så vidare. Om två förekomster av en operation måste finnas i samma flöde men har olika körtider, därför måste du skapa två olika operationer, t ex Assembly1 och Assembly2.

### <a name="modifying-product-specific-routes"></a>Ändra produktspecifika flöden

När du öppnar den **väg** sidan från den **ut produktinformation** sidan flödesversioner som är kopplade till den valda frisläppt produkten visas. I detta sammanhang för varje operation, visar Dynamics 365 för operationer från operationsrelationen funktionella egenskaper som bäst motsvarar flödesversionen. Ser du att listan åtgärder innehåller den **Artikelkod** och **flöde kod** egenskaper från operationsrelationen. Därför kan du bestämma vilka operationsrelationen ska visas.  

I den **flöde** sidan Ändra funktionella egenskaper för operationen, till exempel bearbetningstiden eller kostnadskategorier. Ändringarna sparas i operationsrelationen gäller flödet och frisläppt produkt som hänvisas till i den aktuella flödesversionen. Om operationsrelationen som visas inte är begränsade till flödet och frisläppt produkt innan ändringarna sparas, skapas en kopia av operationsrelationen. Den här kopian *är* avser flödet och frisläppt produkt. Ändringarna påverkar inte andra flöden därför eller frisläppta produkter. Kontrollera vilka operationsrelationen ändras på den **flöde** kan du titta på de **Artikelkod** och **flöde kod** fält.  

Kan du också manuellt skapa en åtgärd som gäller ett flöde och en frisläppt produkt med hjälp av den **kopiera och redigera relation** funktion.  

**Anmärkning:** om du lägger till en ny åtgärd till ett flöde på de **flöde** sida, skapas en operationsrelation endast för den aktuella frisläppt produkten. Därför flödet används också för att tillverka andra frisläppta produkter, finns ingen operationsrelationen gäller för de frisläppta produkterna och flödet kan inte längre användas för de frisläppta produkterna.

### <a name="maintaining-operation-relations-per-route"></a>Underhåll operationsrelationer per flöde

När du öppnar den **flödesdetaljer** sidan från den **flöden** listsidan visas en lista över alla operationsrelationer som gäller för det valda flödet. Du kan därför enkelt kontrollera vilken funktionella egenskaper används för vilka produkter. Du kan ändra både standardvärden för egenskaper och egenskapsvärden för olika produkter.  

Om du lägger till en ny åtgärd skapas på den **vidarebefordra information** sidan det **flöde kod** ställs automatiskt in på **flöde**, och **flöde relationen** är inställt på flödesnumret för det aktuella flödet.

### <a name="maintaining-operation-relations-per-operation"></a>Underhåll operationsrelationer per åtgärd

Från den **Operations**, men du kan öppna den **operationsrelationer** sida. Du kan ändra alla operationsrelationer för en specifik operation på denna sida. Du kan även ändra operationsrelationer med standardvärden.  

Om ditt företag använder standardåtgärder och driftsparametrar är desamma för alla produkter och processer i **operationsrelationer** sida är ett enkelt sätt att underhålla fungerar standardegenskaperna för dessa åtgärder.

### <a name="applying-operation-relations"></a>Kopplade operationsrelationer

I vissa fall finns Dynamics 365 för operationer funktionella egenskaper för en operation. Exempelvis när en inköpsorder skapas måste för varje operation funktionella egenskaper kopieras från operationsrelationer i produktionsflödet. I sådana fall måste sökningen från den mest specifika kombinationen affärsrelationer till den minst specifika kombinationen Dynamics 365 för operationer.  

När Dynamics 365 för operationer sökningar efter mest relevanta operationsrelationen för frisläppt produkt, en operationsrelation som överensstämmer med artikel-ID: T för frisläppt produkt föredras över en operationsrelation som matchar artikelgruppen-ID. I sin tur är en operationsrelation som överensstämmer med artikel grupp-ID att föredra över standard operationsrelationen. Sökningen utförs i följande ordning:

1.  **Artikelkod**=**i tabellen** och **Artikelrelation**=&lt;artikel-ID&gt;
2.  **Artikelkod**=**grupp** och **Artikelrelation**=&lt;artikel grupp-ID&gt;
3.  **Artikelkod**=**alla**
4.  **Dirigera kod**=**väg** och **flöde relationen**=&lt;flödes-ID&gt;
5.  **Dirigera kod**=**alla**
6.  **Konfigurationen**=&lt;konfigurations-ID&gt;
7.  **Configuration**=
8.  **Webbplatsen**=&lt;site-ID&gt;
9.  **Site**=

En åtgärd bör därför användas endast en gång för varje väg. Alla förekomster av operationen ska ha samma operationsrelationen om operationen förekommer flera gånger i samma flöde, och du inte har olika egenskaper (till exempel körtid) för varje förekomst.

## <a name="route-versions"></a>Flödesversioner
Flödesversioner används för att ge plats åt variationer i produktionen av produkter eller ge större kontroll över produktionsprocessen. De definierar vilken väg som ska användas när en specifik frisläppt produkt eller variant frisläppt produkt tillverkas. Du kan använda följande villkor för att definiera vilka flödesversioner används för frisläppt produkt:

-   Produktdimensioner (storlek, färg, stil eller konfiguration)
-   Produktionskvantitet
-   Produktionssite
-   Produktionsdatum

När du skapar på en viss plats i ett visst antal produkten eller under en angiven period, du kan ange en specifik flödesversion som standard flödesversionen. Observera dock att det enda aktiva flödet som tillåts för en viss frisläppt produkt och en given uppsättning villkor.  

Du kan kräva att giltighetsperioden för en flödesversion alltid anges i produktionsparametrarna kontroll.

### <a name="approval-of-route-versions"></a>Godkännande av flödesversion

Innan en flödesversion kan användas i planering eller tillverkningsprocessen måste godkännas. När du godkänner en flödesversion kan även godkänna flödet relaterade. Tänk på att en flödesversion godkänns endast om flödet Närliggande även är godkänd.

### <a name="activating-the-default-route-version"></a>Aktivera flödesversionen standard

När du aktiverar en flödesversion måste ange du den som standard flödesversionen som huvudplanering, eller det som används för att skapa produktionsorder. Du kan ha endast en aktiv flödesversion för en given uppsättning villkor (till exempel period, webbplats eller antal). Om den version som du försöker aktivera står i konflikt med en version som redan är aktivt, visas ett felmeddelande. För att undvika en tvetydig aktivering kan du sedan inaktivera den andra versionen eller ändra begränsningar (normalt tid) för flödesversionen.

### <a name="electronic-signatures"></a>Elektroniska signaturer

Om du vill hålla en logg som poster som godkänner och aktiverar varje flödesversion kan du kräva elektroniska signaturer för aktiviteterna. Användare som kan godkänna och aktivera flödesversioner måste sedan bekräfta sin identitet med hjälp av en [elektronisk signatur](/dynamics365/operations/organization-administration/electronic-signature-overview).

### <a name="product-change-that-uses-case-management"></a>Ändra produkt som använder ärendehantering

Produkten ändra skiftläge för godkännande och aktivering av nya eller ändrade flöden och flödesversioner ger dig ett enkelt sätt att visa en översikt över flödet version begränsningar. Du kan också godkänna och aktivera alla flöden som är kopplade till en viss händelse i en operation och resultaten i fallet ändra produkten dokumentera.

## <a name="maintaining-routes"></a>Underhåll flöden
Beroende på ditt företags behov kanske du vill minska det arbete som krävs för att underhålla dina definitioner.

### <a name="making-routes-independent-of-resources"></a>Göra flöden oberoende av resurser

I många system anges operationer resursen eller resursgruppen som ska utföra operationen i flödet. I Dynamics 365 för operationer kan definiera du också en uppsättning krav på att en resurs operationer ska kunna tillämpas för operationen. Därför är specifika operationer resurs eller resursgrupp som ska användas inte kan bestämmas förrän åtgärden schemaläggs. Denna funktion är speciellt användbar när du har många arbetstagare eller maskiner som kan utföra samma åtgärd.  

Till exempel ange att en operation kräver en resurs operationer av den **maskin** typ med en **Stamping** kapacitet 20 ton. Planeringsmotorn matchar sedan dessa krav med en specifika operationer resurs eller resursgrupp när operationen planeras. Eftersom du kan bara ange dessa krav i stället för bindningsåtgärden till en viss dator, har du mycket större flexibilitet. Underhåll är dessutom lättare när resurser flyttas eller läggs nya resurser.  

Mer information om de olika typerna av resursbehovet och hur de används finns i Operations resurskrav och [resurskunskaper](resource-capabilities.md).

### <a name="sharing-routes-across-sites"></a>Dela flöden mellan platser

Om du skapar samma produkt på mer än en produktionssite och stegen för att framställa produkten är samma på alla platser skapar du ofta en delad väg som används i alla produktionsanläggningar. Om du vill skapa en delad väg inte specifiera en site på själva flödet. Du måste fortfarande skapa en flödesversion som kopplar produkten på varje delad flödet.  

Du måste också kontrollera att resursbehov för varje operation i flödet inte kräva specifika operationer, resurser eller resursgrupper, men i stället uttrycks i egenskaperna för resurserna som krävs. Planeringsmotorn kommer sedan att kunna tilldela lämpliga operationsresurser från produktionen planeras på webbplatsen. Om det finns små skillnader i bearbetningstiden eller ställtiden för en bestämd operation är sitespecifika ange du denna information genom att lägga till en ytterligare Operationsrelation för platsen.  

Du bör också använda resursförbrukning på motsvarande strukturlistan (BOM) om du vill dra nytta av fördelarna med delade flöden. När du anger flaggan för resursförbrukning för strukturlisteraden härleddes lagerställe och plats som råvaror som ska förbrukas från från resursen operationen planeras för operationer. Därför lagerstället och platsen inte kan bestämmas förrän produktionen planeras. På så sätt kan du både Strukturlistan och flödet oberoende av den fysiska platsen där produkten tillverkas.

### <a name="standard-operation-relations"></a>Standardåtgärd operationsrelationer

Om företaget använder standardiserad driften inom hela produktionen om det finns en liten eller ingen variation i ställtiden, körtid förbrukningsberäkning, kostnadsberäkning, och osv, kan du tjäna på hur du skapar operationsrelationer för alla operationer. Då slipper operationsrelationer som avser ett flöde eller frisläppt produkt.  

Om även express resursbehov i fråga om kunskaper och funktioner och göra dina flöden oberoende av plats, kan du skydda det löpande underhållet av affärsprocesserna så lite som möjligt.  

När du använder den här metoden skapar det **operationsrelationer** sidan blir primära målet för underhåll körtid och andra egenskaper.

### <a name="resource-specific-process-times"></a>Resursspecifik processtider

Om du inte anger en operations resursen eller resursgruppen som en del av resurskraven för en åtgärd, kan resurser arbeta med olika hastigheter. Den tid som behövs för att bearbeta en åtgärd varierar. Du kan använda för att lösa problemet i **formeln** på operationsrelationen anger hur processtiden beräknas. Följande alternativ är tillgängliga:

-   **Standard** – (standardalternativet) beräkningen används fälten från operationsrelationen och angiven Körtid multipliceras med orderantalet.
-   **Kapacitet** – beräkningen innefattar den **kapacitet** från resursen operationer. Därför är tiden resursen beroende. Värdet som anges för resursen operationer är kapacitet per timme. Det här värdet multipliceras med orderantalet och **faktor** värdet från operationsrelationen.
-   **Batch** – Batchkapacitet beräknas utifrån informationen operationsrelationen. Antal batchar och därmed bearbetningstiden kan beräknas baserat på orderkvantiteten.
-   **Resursbatch** – det här alternativet är ungefär densamma som den **Batch** alternativ. Beräkningen innefattar dock den **kapacitet Batch** från resursen operationer. Därför är tiden resursen beroende.


<a name="see-also"></a>Se även
--------

[Bills of materials and formulas](bill-of-material-bom.md)

[Cost categories used in production routing](../cost-management/cost-categories-used-production-routings.md)

[Resource capabilities](resource-capabilities.md)

[Electronic signature overview](/dynamics365/operations/organization-administration/electronic-signature-overview)


