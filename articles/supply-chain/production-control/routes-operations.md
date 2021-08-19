---
title: Flöden och operationer
description: Det här avsnittet innehåller information om Flöden och operationer.
author: sorenva
ms.date: 03/18/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BOMDesigner, BOMDesignerRouteVersion, Route, RouteInventProd, RouteOpr, RouteOprTable, ProdRouteJob, ProdRouteTrans, ProdRouteOverview, ProdRouteJobOverview, ProdRouteJobListPagePreviewPane, RouteTable, RouteVersionFeasibility, ProdRouteJobCurrent, RouteGroup, RouteProductionOrder, EngChgCaseRouteTablePart, EcoResProductProdTypeFormulaNoActiveRouteFormPart,
ms.author: sorenand
audience: Application User
ms.reviewer: kamaybac
ms.custom: 268124
ms.assetid: f78d5836-3e71-42b7-a5d1-41f19228d9d2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2478d86a24bc6e41dd43b41c9e7062108c3122e8b5a3d699db2fc8243e8be5c1
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6721305"
---
# <a name="routes-and-operations"></a>Flöden och operationer

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller information om Flöden och operationer. Ett flöde definierar processen för tillverkning av en produkt eller produktvariant. Det beskriver varje steg (operation) i produktionsprocessen och den ordning som dessa steg måste utföras i. För varje steg definierar också flödet de operationsresurser krävs, ställtid och körtid som krävs och hur kostnaden ska beräknas.

## <a name="overview"></a>Översikt

Ett flöde beskriver ordningen av operationer som krävs för att producera en produkt eller produktvariant. Flödet definierar också operationsresurser som krävs, tid som krävs för att ställa in och utföra operationen och hur kostnaden ska beräknas för varje operation. Du kan använda samma flöde för att skapa flera produkter eller definiera ett unikt flöde för varje produkt eller produktvariant. Du kan också ha flera flöden för samma produkt. I detta fall varierar det flöde som används beroende på faktorer som t.ex. den kvantitet som måste produceras. Definitionen av ett flöde i Supply Chain Management består av fyra separata element som tillsammans beskriver produktionsprocessen:

- **Flöde** – ett flöde som definierar strukturen i produktionsprocessen. Den definierar alltså operationernas ordning.
- **Operation** – en operation som identifierar ett namngivet steg i flödet, som t.ex. **sammansättning**. Samma operation kan ske på flera flöden och kan ha olika operationsnummer.
- **Operationsrelation** – En operationsrelation definierar de funktionella egenskaper för en operation som ställtid och körtid, kostnadskategorier, förbrukningsparametrar och krav på systemresurser. Operationsrelationen möjliggör att operativa egenskaper hos en operation varierar beroende på vilket föde som operationen används i eller produkterna som produceras.
- **Flödesversion** – en flödesversion som definierar flödet som används för att tillverka en produkt eller produktvariant. Flödesversioner tillåter att flöden ska återanvändas mellan produkter eller ändras med tiden. De tillåter också att olika flöden används för att tillverka samma produkt. I detta fall varierar det flöde som används beroende på faktorer som t.ex. plats eller den kvantitet som måste produceras.

## <a name="routes"></a>Flöden
Ett flöde beskriver ordningen av operationer som används för att producera en produkt eller produktvariant. Varje operation tilldelas ett operationsnummer och en efterföljande operation. Operationernas ordning utgör en flödesnätverk som kan representeras av ett riktat diagram med en eller flera startpunkter och en enda slutpunkt. I Supply Chain Management skiljer sig flöden baserat på vilken typ av struktur. Två typer av flöden är enkla flöden och flödesnätverk. I produktionsstyrningsparametrarna kan du ange om endast enkla flöden kan användas, eller om mer komplexa flödesnätverk kan användas

### <a name="simple-routes"></a>Enkla flöden

Ett enkelt flöde är sekventiellt och det finns bara en startpunkt för flödet.  

[![Enkelt flöde.](./media/routes-and-operations-1-simple-route.png)](./media/routes-and-operations-1-simple-route.png)  

Om du bara aktiverar enkla flöden i produktionsstyrningsparametrarna genererar Supply Chain Management automatiskt operationsnumren (10, 20, 30 osv.) när du definierar flödet.

### <a name="route-networks"></a>Flödesnätverk

Om du aktiverar mer komplexa flödesnätverk i produktionsstyrningsparametrarna kan du definiera flöden som har flera startpunkter och operationer som kan köras parallellt.  

[![Flödesnätverk.](./media/routes-and-operations-2-route-network.png)](./media/routes-and-operations-2-route-network.png)  

> [!NOTE]
> - Varje operation kan ha endast ha en efterföljande operation och hela flödet måste sluta i en enkel operation.
> - Det finns ingen garanti för att flera operationer med samma efterföljande operation (exempelvis operationer 30 och 40 i bilden ovan) kommer att köras parallellt. Tillgängligheten och kapaciteten hos resurserna kan sätta begränsningar på sättet som operationerna schemaläggs.
> - Du kan inte använda 0 (noll) som operationsnummer. Det numret är reserverat och används för att ange att den sista operationen i flödet inte har någon efterföljande operation.

### <a name="parallel-operations"></a>Parallella operationer

Ibland krävs en kombination av flera operationsresurser som har olika egenskaper för att utföra en operation. En monteringsoperation kanske till exempel kräver en maskin och ett verktyg och en arbetare för varje två maskiner för att övervaka operationen. Det här exemplet kan utformas med parallella operationer där en operation anges som den primära operationen och de andra sekundära.  

[![Flöde som har primära och sekundära åtgärder.](./media/routes-and-operations-3-parallel-operations.png)](./media/routes-and-operations-3-parallel-operations.png)  

Den primära operationen representerar vanligen flaskhalsresurs och avgör bearbetningstiden för sekundära operationer. Under schemaläggningen som innefattar begränsad kapacitet, måste emellertid resurserna som är schemalagda för både primära operationer och sekundära operationer vara tillgängliga och samtidigt ha fri kapacitet.  

Både den primära operationen och sekundära operationer måste ha samma operationsnummer (30 i bilden ovan).  

I det föregående exemplet är resursbehovet för den primära operationen (30) maskinen, medan resursbehoven för de sekundära operationerna (30' och 30'') är verktyget och arbetaren. En 50 procentig beläggning hjälper till att garantera att den schemalagda arbetaren kan övervaka två datorer samtidigt.

### <a name="approval-of-routes"></a>Godkännande av flöden

Ett flöde måste godkännas innen det kan användas i planeringen eller tillverkningsprocessen. Godkännande anger att flödesdesignen har slutförts. Samma frisläppta produkt eller frisläppta produktvariant kan ha flera godkända flöden. Vanligtvis sker godkännande av ett flöde när den första relevanta flödesversionen är godkänd. I vissa affärsscenarier är dock godkännandet av flödet och flödesvisionen separata aktiviteter som kan involvera olika processägare.  

Varje flöde och formel går att godkänna och upphäva separat. Observera att om ett flöde inte är godkänd är alla relaterade flödesversioner heller inte godkända. I produktionsstyrningsparametrarna kan du ange om flöden kan godkännas och om godkända flöden kan ändras.  

Om du måste hålla en logg som registrerar vem som godkänner varje flöde, kan du kräva elektroniska signaturer för flödeskännande. Användare måste sedan bekräfta sin identitet med hjälp av en [elektronisk signatur](../../fin-ops-core/fin-ops/organization-administration/electronic-signature-overview.md).

## <a name="operations"></a>Operations
En operation är ett steg i produktionsprocessen, t.ex. Varje operation har ett ID och en kort beskrivning. I följande tabell visas vanliga exempel på operationer från en maskinaffär.

| Åtgärd  | beskrivning        |
|------------|--------------------|
| PipeCut    | Rörskärning       |
| TIGweld    | TIG-svetsning        |
| JigAssy    | Jiggmontering       |
| Inspektion | Kvalitetsinspektion |

De funktionella egenskaper för en operation som ställtid och körtid, kostnadskategorier, resursbehov, kostnadsinformation och konsumtionsberäkning specificeras i operationsrelationen. (Mer information om operationsrelationer finns i nästa avsnitt.)

## <a name="operation-relations"></a>Operationsrelation
Följande funktionella egenskaper för en operation hanteras i operationsrelationen:

- Kostnadskategorier
- Förbrukningsparametrar
- Bearbetningstider
- Bearbetningskvantiteter
- Resurskrav
- Anteckningar och instruktioner

Du kan definiera flera operationsrelationer för samma operation. Men varje operationsrelationen gäller samtidigt och lagrar egenskaper som är specifika för ett flöde, frisläppt produkt eller en uppsättning frisläppta produkter som hör till en artikelgrupp. Samma operation kan därför användas i flera flöden som har olika funktionella egenskaper. Dessutom kan du lättare underhålla huvuddata om du använder standardoperationer som har samma funktionella egenskaper, oavsett flödet som används och produkten som produceras. Omfattningen av operationsrelationen definieras via egenskaperna **Artikelkod**, **Artikelrelation**, **flödeskod** och **flödesrelationen**, vilket visas i följande tabell.

| Artikelkod | Artikelrelation         | Flödeskod | Flödesrelation   | Omfattningen av operationsrelationen                                                                                                                                                                                                                                                                              |
|-----------|-----------------------|------------|------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Tabell     | &lt;Artikel-ID&gt;       | Flöde      | &lt;Rutt-ID&gt; | De funktionella egenskaperna för en operation när den används i flödet där **Flödesnummer**=&lt;flödes-ID&gt; för att producera slutprodukten där **artikelnummer**=&lt;artikel-ID&gt;.                                                                                                                        |
| Tabell     | &lt;Artikel-ID&gt;       | Allt        |                  | De funktionella standardegenskaperna för en operation när den används för att producera den frisläppta produkten där **Artikelnummer**=&lt;artikel-ID&gt;. Dessa funktionella egenskaper gäller alltså när det inte finns någon flödesspecifik operationsrelation för frisläppt produkt.                                     |
| Grupp     | &lt;Artikelgrupp-ID&gt; | Flöde      | &lt;Rutt-ID&gt; | Funktionella egenskaper för en operation vid användning i flödet där **Flödesnummer**=&lt;flödes-ID&gt; producerar frisläppta produkter som är kopplade till artikelgrupp &lt;artikelgrupp-ID&gt;, såvida det inte finns en flödesspecifik operationsrelation för frisläppt produkt.                         |
| Grupp     | &lt;Artikelgrupp-ID&gt; | Allt        |                  | Standardegenskaperna för en operation när det används för att producera frisläppta produkter som är kopplade till artikelgrupp &lt;artikelgrupp-ID&gt;, om det inte finns en mer specifik operationsrelation.                                                                                                  |
| Allt       |                       | Flöde      | &lt;Rutt-ID&gt; | Standardegenskaperna för operationen när den används i flödet där **Flödesnummer**=&lt;flödes-ID&gt;. Dessa funktionella egenskaper gäller alltså när det inte finns någon operationsrelation för detta flöde som är specifik för antingen frisläppt produkt eller des associerade artikelgrupp. |
| Allt       |                       | Allt        |                  | Standardegenskaperna för en operation. Dessa funktionella egenskaper gäller när en mer specifik operationsrelation inte finns.                                                                                                                                                                |

Du kan ange att en operationsrelation är specifik för en plats. På så sätt kan funktionella egenskaper för en operation variera beroende på plats (site) där operation utförs. Du kan ange olika funktionella egenskaper för konfigurerade produktkonfiguration för varje produktkonfiguration.  

Operationsrelationer ger stor flexibilitet när du definierar dina flöden. Dessutom kan du definiera standardegenskaperna för att minska mängden huvuddata som du måste underhålla. Den här flexibiliteten innebär dock även att du måste känna till det sammanhang som du kan ändra en operationsrelation i.  

> [!NOTE]
> Eftersom funktionella egenskaper lagras i operationsrelationer per operation för varje flöde, per flöde, har alla förekomster av samma operation (exempelvis sammansättningen) samma ställtid, körtid, resurskrav. Om två förekomster av en operation måste finnas i samma flöde men har olika körtider, måste du därför skapa två olika operationer, t.ex. Sammansättning1 och Sammansättning2.

### <a name="modifying-product-specific-routes"></a>Ändra produktspecifika flöden

När du öppnar sidan **Flöde** från **Frisläppt produktinformation** kommer de flödesversioner som är kopplade till den valda frisläppt produkten att visas. I detta sammanhang visar Supply Chain Management de operationsrelationers funktionella egenskaper som bäst motsvarar flödesversionen för varje operation. Du ser att listan över operationer innehåller egenskaperna **Artikelkod** och **flöde śkod** från operationsrelationen. Därför kan du bestämma vilken operationsrelation som ska visas.  

På sidan **flöde** kan du ändra funktionella egenskaperna för operationen, till exempel körtiden eller kostnadskategorier. Ändringarna sparas i operationsrelationen som är specifika för flödet och frisläppt produkt som hänvisas till i den aktuella flödesversionen. Om operationsrelationen som visas inte är specifik till flödet och frisläppt produkt innan ändringarna sparas, skapas en kopia av operationsrelationen. Den här kopian *är* specifik för flödet och frisläppt produkt. Ändringarna påverkar inte andra flöden eller frisläppta produkter. Kontrollera vilka operationsrelationen ändras på den **flöde** kan du titta på fälten **Artikelkod** och **flödeskod**.  

Kan du också manuellt skapa en operation som gäller ett flöde och en frisläppt produkt med hjälp av funktionen **kopiera och redigera relation**.  

> [!NOTE]
> Om du lägger till en ny operation till ett flöde på sidan **flöde**, skapas en operationsrelation endast för den aktuella frisläppta produkten. Därför används också flödet för att tillverka andra frisläppta produkter, gäller inte operationsrelationen för de frisläppta produkterna och flödet kan inte längre användas för de frisläppta produkterna.

### <a name="maintaining-operation-relations-per-route"></a>Underhåll operationsrelationer för flöden

När du öppnar sidan **Flödesdetaljer** från listsidan **flöden** visas en lista över alla operationsrelationer som gäller för det valda flödet. Du kan därför enkelt kontrollera vilka funktionella egenskaper används för vilka produkter. Du kan ändra både standardvärden för egenskaper och produktspecifika egenskapsvärden.  

Om du lägger till en ny operationsrelation på sidan **flödesinformation** anges fältet **flödeskod** automatiskt till **flöde**, och **flödesrelationen** är inställt på flödesnumret för det aktuella flödet.

### <a name="maintaining-operation-relations-per-operation"></a>Underhåll av operationsrelationer per operation

Från sidan **Operationer** kan du öppna sidan **operationsrelationer**. Du kan ändra alla operationsrelationer för en specifik operation på denna sida. Du kan även ändra operationsrelationer med standardvärden.  

Om ditt företag använder standardåtgärder och om driftsparametrar är desamma för alla produkter och processer ger sidan **operationsrelationer** ett enkelt sätt att underhålla standardegenskaperna för dessa operationer.

### <a name="applying-operation-relations"></a>Tillämpa operationsrelationer

I vissa fall måste for Supply Chain Management hitta operationens funktionella egenskaper. Exempelvis när en inköpsorder skapas måste de funktionella egenskaperna för varje operation kopieras från operationsrelationer i produktionsflödet. I sådana fall söker Supply Chain Management efter de relevanta operationsrelationerna från den mest specifika kombinationen till den minst specifika.  

När Supply Chain Management söker efter den mest relevanta operationsrelationen för en frisläppt produkt, föredras en operationsrelation som överensstämmer med artikel-ID för frisläppt produkt över en operationsrelation som matchar artikelgrupp-ID. I sin tur är en operationsrelation som överensstämmer med artikel grupp-ID att föredra över standardoperationsrelationen. Tabellen görs i följande ordning.

1.  **Artikelkod**=**Tabell** och **Artikelrelation**=&lt;artikel-ID&gt;
2.  **Artikelkod**=**Grupp** och **Artikelrelation**=&lt;artikelgrupp-ID&gt;
3.  **Artikelkod**=**Alla**
4.  **Flödeskod**=**Flöde** och **flödesrelation**=&lt;flödes-ID&gt;
5.  **Flödeskod**=**Alla**
6.  **Konfigurationen**=&lt;konfigurations-ID&gt;
7.  **Konfiguration**=
8.  **Plats**=&lt;plats-ID&gt;
9.  **Plats**=

En operation bör därför användas endast en gång för varje flöde. Om en operation händer flera gånger i samma flöde kommer alla händelser av den operationen kommer ha samma operationsrelation och du inte har olika egenskaper (till exempel körtid) för varje händelse.

## <a name="route-versions"></a>Flödesversioner

Flödesversioner används för att ge plats åt varianter i produktionen av produkter, eller för att ge dig större kontroll över produktionsprocessen. De definierar vilket flöde som ska användas när en specifik frisläppt produkt eller frisläppt produktvariant tillverkas. Du kan använda följande villkor för att definiera vilka flödesversioner används för frisläppt produkt:

- Produktdimensioner (storlek, färg, format eller konfiguration)
- Produktionskvantitet
- Produktionsplats
- Produktionsdatum

När du skapar produkten på en viss plats, i en viss kvantitet eller under en viss period kan du ange en specifik flödesversion som standardflödesversionen. Observera dock att det enda aktiva flödet som tillåts för en viss frisläppt produkt och en viss uppsättning villkor.  

I produktionsstyrningsparametrarna kan du kräva att giltighetsperioden för en flödesversion alltid anges.

### <a name="approval-of-route-versions"></a>Godkännande av flödesversioner

Innan en flödesversion kan användas i planeringen eller tillverkningsprocessen måste den godkännas. När du godkänner en flödesversion kan du också godkänna det relaterade flödet. Observera dock att en färdvägsversion endast kan godkännas om det relaterade flödet också är godkänt.

### <a name="activating-the-default-route-version"></a>Aktivera standardflödesversionen

När du aktiverar en flödesversion måste ange du den som standardflödesversionen som huvudplaneringen använder eller den som används för att skapa produktionsorder. Du kan ha endast en aktiv flödesversion för en given uppsättning villkor (till exempel period, plats eller antal). Du får ett felmeddelande om versionen som du försöker aktivera står i konflikt med en version som redan är aktiv. Du måste sedan antingen inaktivera den motstridiga versionen eller ändra versionsbegränsningarna (vanligtvis perioden) för att förhindra en oklar aktivering.

### <a name="electronic-signatures"></a>Elektronisk signatur

Om du måste hålla en logg som registrerar vem som godkänner och aktiverar varje flödesversion, kan du kräva elektroniska signaturer för flödeskännande. Användare som kan godkänna och aktivera flödesversioner måste sedan bekräfta sin identitet med hjälp av en [elektronisk signatur](../../fin-ops-core/fin-ops/organization-administration/electronic-signature-overview.md).

### <a name="product-change-that-uses-case-management"></a>Produktändring med ärendehantering

Produktändringsärendet för godkännande och aktivering av nya eller ändrade flöden och flödesversioner ger dig ett enkelt sätt att visa en översikt över begränsningarna för flödesversioner. Du kan också godkänna och aktivera alla flöden som är kopplade till en viss händelse i en operation och resultaten i produktändringsfallet.

## <a name="maintaining-routes"></a>Underhålla flöden

Beroende på ditt företags behov kanske du vill minska det arbete som krävs för att underhålla dina processdefinitioner.

### <a name="making-routes-independent-of-resources"></a>Göra flöden oberoende av resurser

I många system måste operationresursen eller resursgruppen som ska utföra operationen anges i flödet. I Supply Chain Management kan du dock definiera en uppsättning krav som en verksamhetsresurs måste uppfylla för att kunna tillämpas på operationen. Därför kan inte specifika operationsresurser eller resursgrupper som ska användas bestämmas förrän operationen schemaläggs. Denna funktion är speciellt användbar när du har många arbetare eller maskiner som kan utföra samma operation.  

Till exempel anger du att en operation kräver en operationsresurs av typen **maskin** med en **stämplings** kapacitet på 20 ton. Planeringsmotorn matchar sedan dessa krav med en specifik operationsresurs eller resursgrupp när operationen planeras. Eftersom du bara kan ange dessa krav i stället för bindning av operationen till en viss maskin, har du mycket större flexibilitet. Underhåll är dessutom lättare när resurser flyttas eller när nya resurser läggs till.  

Mer information om de olika typerna av resursbehov och hur de används finns i Operationsresurskrav och [resurskunskaper](resource-capabilities.md).

### <a name="sharing-routes-across-sites"></a>Dela flöden mellan platser

Om du skapar samma produkt på mer än en produktionsplats och stegen för att framställa produkten är samma på alla platser skapar du ofta ett delat flöde som används i alla produktionsanläggningar. Om du vill skapa ett delat flöde ska du inte specifiera en plats på själva flödet. Du måste fortfarande skapa en flödesversion som kopplar produkten på varje delad flödet.  

Du måste också kontrollera att resursbehov för varje operation i flödet inte kräver specifika operationer, resurser eller resursgrupper, men i stället uttrycks i egenskaperna för resurserna som krävs. Planeringsmotorn kommer sedan att kunna tilldela lämpliga operationsresurser från platsen som produktionen planeras på. Om det finns små skillnader i bearbetningstiden eller ställtiden för en bestämd operation är platsspecifik anger du denna information genom att lägga till en ytterligare operationsrelation för platsen.  

Du bör också använda resursförbrukning på motsvarande strukturlista(BOM) om du vill dra nytta av fördelarna med delade flöden. När du anger flaggan för resursförbrukning för strukturlisteraden härleds lageret och den plats som råvaror ska konsumeras av från den operationresurs som operationen är planerad till. Därför måste inte lagerstället och platsen bestämmas förrän produktionen planeras. På så sätt kan du göra både strukturlistan och flödet oberoende av den fysiska platsen där produkten tillverkas.

### <a name="standard-operation-relations"></a>Standardoperationsrelationer

Om företaget använder standardiserad operationer genom hela produktionen och om det finns en liten eller ingen variation i ställtid, körtid, förbrukningsberäkning, kostnadsberäkning osv, kan du dra nytta av att skapa standardoperationsrelationer för alla operationer. Då slipper du operationsrelationer som avser ett flöde eller frisläppt produkt.  

Om även uttrycker resursbehov i fråga om kunskaper och funktioner och gör dina flöden oberoende av plats, kan du hålla det löpande underhållet av affärsprocesserna till ett minimum.  

När du använder den här metoden blir sidan **operationsrelationer** det primära målet för underhållskörtid och andra egenskaper.

### <a name="resource-specific-process-times"></a>Resursspecifika processtider

Om du inte anger en operationsresurs eller resursgrupp som en del av resurskraven för en operation, kan resurser arbeta med olika hastigheter. Den tid som behövs för att bearbeta en operation varierar. För att lösa problemet kan du använda fältet **formel** på operationsrelationenför att ange hur processtiden beräknas. Följande alternativ är tillgängliga:

- **Standard** – (standardalternativet) beräkningen använder endast fälten från operationsrelationen och angiven körtid multipliceras med orderantalet.
- **Kapacitet** – beräkningen innefattar fältet **kapacitet** från operationsresursen. Därför är tiden resursenberoende. Värdet som anges för operationsresursen är kapacitet per timme. **Processtiden** beräknas som **Orderkvantitet** delad av **Kapacitet**.
- **Batch** – Batchkapacitet beräknas utifrån informationen från operationsrelationen. Antal batchar och därmed bearbetningstiden kan beräknas baserat på orderkvantiteten.
- **Resursbatch** – det här alternativet är ungefär densamma som alternativet **Batch**. Men innefattar fältet **Batchkapacitet** från operationsresursen. Därför är tiden resursberoende.

### <a name="set-up-route-groups"></a>Ställ in flödesgrupper

Du kan definiera flödesgrupperna och inställningarna för dess flödes- eller jobbtyper under **Produktionskontroll > Inställningar > Flöden > Flödesgrupper**. För varje flödes-/jobbtyp i flödesgruppen kan du markera eller avmarkera följande alternativ:

- **Aktivering** - Välj det här alternativet om du vill aktivera beräkningar och tidsplanering för den valda jobbtypen och få återrapportering för ett jobb när du kör finplanering. Du måste markera det här alternativet för att aktivera jobbtyp och sedan välja resten av alternativ för denna jobbtyp. Om aktiveringen inte markeraskommer denna jobbtyp inte att aktiveras, oavsett vad som valts av de andra alternativen. 
- **Jobbhantering** - Välj det här alternativet för att inkludera jobbtypen i jobbhantering när du kör finplanering. 
- **Arbetstid** Välj det här alternativet om du vill tidsplanera jobbtypen enligt arbetstidskalendern som har definierats för operationsresursen. Annars används den gregorianska kalendern. Arbetstid kan antingen tidsplaneras enligt den gregorianska kalendern eller enligt den definierade arbetskalendern. Om du väljer det här alternativet kommer tidsplaneringen att baseras på den definierade arbetstidskalendern. Dessutom tidsplaneras jobbtypens jobb från midnatt det datum som har angetts som jobbets startdatum.
- **Kapacitet** - Välj det här alternativet om du vill reservera kapacitet för jobbtypen när du kör finplanering. Om du väljer det här alternativet reserveras kapacitet när tidsplanering körs för den valda jobbtypen. Detta ger en översikt över vilka jobbtyper i varje flödesgruppbruk som använder operationsresurserna. Om du till exempel i en situation där uttorkningsresurser är flaskhalsar måste dessa resurser anges som flaskhalsar. Uttorkningoperationer som är tilldelade kötidjobbtyper kommer att reservera uttorkningresurser. 

För var och en av jobbtyperna måste du först aktivera eller inaktivera den. När du inaktiverar beaktas ingen av de övriga inställningarna (jobbhantering, arbetstid och kapacitet) eftersom jobbtypen inte kommer att vara aktiverad. 

Bland jobbtyper hittar du överlappning. Överlappning tillåter att olika jobb utförs samtidigt. När jobben överlappas kan resurserna användas men kan inte reserveras inte för specifika jobb.
Därför när aktivering väljs för överlappning kommer resten av inställningarna (jobbhantering, arbetstid och kapacitet) inte ha någon inverkan på flödesgruppen. 

> [!NOTE]
> När du uppgraderar versioner kan följande fel uppstå: **”CRL-fel uppstod när planeringsmotorn anropades”**. Om du får detta felmeddelande går du till sidan **flödesgrupper** och för alla flöden där du har aktiverat **överlappa** avmarkerar du alternativen **jobbhantering**, **arbetstid** och **kapacitet**. 

## <a name="additional-resources"></a>Ytterligare resurser

- [Strukturlistor och formler](bill-of-material-bom.md)

- [Kostnadskategorier som används i produktionsflöde](../cost-management/cost-categories-used-production-routings.md)

- [Resurskunskaper](resource-capabilities.md)

- [Översikt över elektroniska underskrifter](../../fin-ops-core/fin-ops/organization-administration/electronic-signature-overview.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]