---
title: Bygg en produktkonfigurationsmodell
description: "De behöver konfigurera produkter för att uppfylla särskilda krav blir regel snarare än undantag, både i business-to-business och business-to-consumer relationer."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PCProductConfigurationModelDetails
audience: Application User
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 75083
ms.assetid: f08072b8-cb0b-43aa-9509-f5ec32caecd9
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 5bc19e95266e8f1bec8744da688387dca559373f
ms.contentlocale: sv-se
ms.lasthandoff: 06/13/2017


---

# Bygg en produktkonfigurationsmodell
<a id="build-a-product-configuration-model" class="xliff"></a>

[!include[banner](../includes/banner.md)]


De behöver konfigurera produkter för att uppfylla särskilda krav blir regel snarare än undantag, både i business-to-business och business-to-consumer relationer.

En tillverkare som stöder Konfigurera till order-scenarion har möjlighet att sköta mer noggrant efter kundens behov. Dessutom, genom att lagerföra halvfabrikat i form av generiska komponenter istället för färdiga produkter, tillverkaren kan minska det kapital som är bundet till lager.  

En lyckad övergång från en tillverkning mot lager inställning för att konfigurera för installation kräver noggrann analys av produktstrukturer, identifiering av produktfamiljer och componentization. Att minska antalet artiklar och minimera antalet varor som finns i processen är det viktigt att du förstår produkten gränssnitt, och att du utformar för återanvändning.  

Det finns flera produktkonfiguration modellering principer såsom regelbaserad, dimensionsbaserad och begränsningsbaserad modellering. Studier visar att den begränsningsbaserade metod kan minska antalet kodrader i modeller med cirka 50 procent jämfört med andra modellering principer. Därför är denna metod kan reducera den totala ägandekostnaden (TCO). Genom att flytta från en regelbaserad modell som bygger på koden X++ till en begränsningsbaserad modell, behöver du inte längre en utvecklarlicens för att upprätthålla produktmodeller.

## Produktkonfiguration
<a id="product-configuration" class="xliff"></a>
Industrialiseringen har lett till stora framgångar i att producera högkvalitativa och presentera-rika produkter till överkomliga priser. De stordriftsfördelar har gjort det möjligt för de flesta människor i den industrialiserade världen att köpa bilar, tv-apparater, hushållsapparater, och andra varor som de flesta av oss betraktar som en nödvändig del av vår vardag.  

Många produkter har blivit handelsvaror, ett behov av att särskilja dem har uppstått. Det omedelbara svaret från tillverkare till denna utmaning har varit att skapa varianter av varje produkt, så att kunderna kan få fler alternativ. Denna strategi har lett till ökade prognos utmaningar, och även en ökning av lagerkostnad och osålda produkter som blivit inaktuellt.  

Genom att anta en konfigurera för filosofi, tillverkar har en möjlighet att möta kundernas efterfrågan på unika produkter och samtidigt minska eller eliminera föråldrade inventarier. När en tillverkning mot lager filosofi skiftas till en konfiguration för filosofi, en utmaning som uppstår är att behovet av korta ledtider måste vägas mot låga lagernivåer.  

Nyckeln till framgång är att noggrant analysera produktportföljen och leta efter mönster i både produktens funktioner och processer. Målet är att identifiera generella komponenter som kan tillverkas med samma utrustning och används i alla varianter.  

Den nya produkten configuration innehåller ett användargränssnitt (UI) som ger en visuell översikt över produktens konfiguration modell struktur, och även en beskrivande tvång syntax som inte behöver sammanställas. Därför är företag som vill stödja en konfiguration kan komma igång lättare. Följande avsnitt förklarar, en konstruktör av en produkt kräver inte längre stöd av utvecklare för att bygga en produkt konfiguration modell, testa den och släpper den till säljorganisation.

## Bygga en produktkonfiguration modell
<a id="building-a-product-configuration-model" class="xliff"></a>
Det finns flera strategier som en användare kan vidta för att bygga upp en produktkonfiguration modell. Ett alternativ är att följa ett sekventiellt flöde genom att först skapa alla uppgifter, såsom produkten masters, skilda produkter och operativa resurser och sedan inkludera dem som komponenter, räkningen av material (BOM) linjer, rutt, och andra delar av produktens konfiguration modell. Alternativt kan du välja en mer iterativ metod genom att först skapa en modell och sedan lägga till uppgifter som behovet uppstår.

### Komponenter
<a id="components" class="xliff"></a>

En produktkonfiguration modellen består av en eller flera komponenter som är sammanbundna genom"relationer. Komponenterna definieras en gång och kan sedan användas många gånger i en eller flera produktkonfiguration modeller. Komponenterna är de viktigaste byggstenarna i en produkt konfigurationsmodell, och nästan all information om modellen är relaterade till dem.

### Attribut
<a id="attributes" class="xliff"></a>

Varje komponent har ett eller flera attribut som identifierar dess egenskaper. Attributen är vad användarna välja under konfigurationsprocessen. Attribut styra både inter-komponenten och intra-komponent kundrelationer genom införande i begränsningar eller beräkningar. Genom villkor som tillämpas på BOM linjer, attributen kan användas för att avgöra vilka fysiska artiklar konfigurerad produkt kommer att bestå av. Dessutom kan ett attribut kan styra egenskaperna för en bom med en kartläggning. Liknande funktioner finns för rutten verksamhet både vad gäller integration och egenskapsinställningar.

### Uttrycksbegränsningar
<a id="expression-constraints" class="xliff"></a>

Användning av en begränsningsbaserad produktkonfiguration modell innebär att vissa begränsningar när användaren väljer värden för olika attribut. Sådana begränsningar kan genomföras som uttryck begränsningar med hjälp av optimering Modeling Language (9,0 ml). Alternativt kan en begränsning kan genomföras i form av en tabell.

### Registerbegränsningar
<a id="table-constraints" class="xliff"></a>

Registerbegränsningar kan vara antingen användardefinierade eller systemdefinierade.  

En användardefinierad tabell begränsning är byggd av användaren. Användaren väljer en kombination av attribut som representerar tabellens kolumner och sedan in värdena från domäner på valt attribut typer att bilda rader i tabellen.  

En systemdefinierad tabellbegränsning definieras genom att välja den Microsoft Dynamics 365 for Finance and Operations-tabell som ska användas som referens, och sedan välja fält från denna tabellen för att bilda kolumnerna i begränsningen. Raderna i tabellbegränsning är rader av inance and Operations-tabellen som finns vid konfigurering.  

En tabellbegränsning ingår i en produktkonfiguration modell genom att referera till tabellbegränsningsdefinitionen och mappa relevanta attribut i modellen till kolumnerna i tabellen.

### Beräkningar
<a id="calculations" class="xliff"></a>

Beräkningar utgör en mekanism för att utföra aritmetiska operationer i en konfiguration modell. Till exempel, en beräkning kan bestämma längden på en specifik bit av råmaterial eller bearbetningstiden för en polering. Beräkningarna är tvingande och ställa in värdet för attributet target efter alla attributvärden som inkluderas i beräkningen uttryck blir tillgängliga.

### Delkomponenter
<a id="subcomponents" class="xliff"></a>

Underkomponenter utgör noder i produktens konfiguration modell struktur. För varje"relation, en hänvisning måste anges för en produkt master som har variant konfigurering teknik till begränsningsbaserad konfiguration.

### Användarbehov
<a id="user-requirements" class="xliff"></a>

En användare har kravet på alla beståndsdelar i en". Den enda skillnaden är att en användare är inte bunden till en produkt master. Den praktiska effekten av denna skillnad är att någon BOM rader eller rutter som definieras inom ramen för en användare krav är minimerad till överordnad komponent produktstruktur eller rutten. Detta beteende liknar beteendet hos en fiktiv BOM.

### Strukturlisterader
<a id="bom-lines" class="xliff"></a>

BOM rader ingår att identifiera tillverkning BOM för varje komponent. En BOM måste hänvisning ett objekt och alla objekt egenskaper kan ställas in på ett fast värde eller mappas till ett attribut.

### Flödesoperationer
<a id="route-operations" class="xliff"></a>

Rutten verksamhet ingår att identifiera tillverkning rutt. En rutt måste hänvisning en definierad funktion och alla egenskaper kan ställas in till ett fast värde. Alla fastigheter utom resursbehov kan mappas till ett attribut i stället för ett värde.

## Validera och testa en produkt konfigurationsmodell
<a id="validating-and-testing-a-product-configuration-model" class="xliff"></a>
Validering av en produktkonfiguration modell kan inträffa på flera nivåer i modellen och kan således omfatta olika omfattningar. Den lägsta nivån är för en enda uttryck tvång. I det här fallet, validering utförs normalt av produkten designer för att kontrollera att syntaxen för ett uttryck är korrekt.  

På samma sätt en förutsättning för en bom eller en rutt kan valideras i isolering.  

Validering kan även göras för en användardefinierad tabellbegränsning definition. I detta fall måste användaren kan kontrollera att de värden som registreras för varje fält finns inuti domänen av motsvarande attribut.  

Slutligen, validering kan göras för en komplett produktkonfiguration modellen för att verifiera att den kompletta syntaxen är korrekt, och att alla namn och modellering konventioner har respekterats.

### Testning
<a id="testing" class="xliff"></a>

Att testa en modell påminner om att köra en faktisk konfigurationssession. Användaren kan gå igenom konfigurationssidorna och kontrollera att modellstrukturen stöder konfigurationen. Användaren kan kontrollera att attributvärden är korrekta och att attributet beskrivningar guidar användaren att välja rätt värden. Slutligen, efter en test session har avslutats, försöker systemet att skapa struktur och den rutt som motsvarar det valda attributet värden och presenterar ett felmeddelande om något går fel.

### Konfigurationssidan
<a id="the-configuration-page" class="xliff"></a>

För att navigera mellan komponenter, klicka på **Nästa** eller klicka på en komponent i produkten konfigurationsmodell träd satt fokus på det.

## Färdigställa en modell för konfiguration
<a id="finalizing-a-model-for-configuration" class="xliff"></a>
När en produkt konfigurationsmodell är redo att användas i Konfigurera till order scenarier, en version måste skapas. Men det finns flera alternativ som kan förbättra modelleringen erfarenhet.

### Användargränssnitt
<a id="user-interface" class="xliff"></a>

Konfigurationen UI kan ändras genom införande av attributet grupper i en eller flera delkomponenter. En sådan gruppering kan belysa sambanden mellan specifika attribut och hjälpa konfiguration användaren identifiera området för den produkt som för tillfället är i fokus.

### Mallar
<a id="templates" class="xliff"></a>

En eller flera konfigurationer mallar kan skapas för att påskynda processen för konfiguration. Alternativt, mallar kan skapas för att främja särskilda attribut kombinationer, t.ex. när en försäljning kampanjen fokuserar på en specifik uppsättning funktioner.

### Översättningar
<a id="translations" class="xliff"></a>

Om produkten kommer att säljas i olika länder/regioner, översättningar kan skapas för all text som visas i konfigurationsanvändargränssnitt. Denna text innehåller inte bara namn och beskrivning, men också attribut värden.

### Versioner
<a id="versions" class="xliff"></a>

Den sista och viktigaste steget i slutförandet är att skapa en version för produktkonfiguration modell. Version representerar förhållandet mellan produkt master, som kan väljas för konfiguration på en order- eller offertrad och produktens konfiguration modell. En version måste vara godkänt och aktiverat innan den kan användas i en konfigurationssession.

## Utöka en produktkonfiguration modell via API
<a id="extending-a-product-configuration-model-through-the-api" class="xliff"></a>
En dedikerad application programming interface (API) har genomförts, så att partner och andra som har en utvecklarlicens kan utöka kapaciteten hos en produktkonfiguration modell. Huvudmålet har varit att upprätta en mekanism som låter kunder och partners som använder den befintliga produktbyggaren att migrera den kod som är inbäddad i produktbyggarmodeller till API. På detta sätt kan de migrera sina modeller från Produktbyggare till produktens konfiguration. Men nya partners och kunder kan också dra nytta av att använda API för att utvidga ny produktkonfiguration modeller.

### PCAdaptor klass
<a id="pcadaptor-class" class="xliff"></a>

API finnas genomfört genom att använda en uppsättning **PCAdaptor** klasser att utsätta datastrukturen i produktens konfiguration modeller. En instans av klassen **PCAdaptor** måste skapas för varje modell som ska utökas. När en konfigurationssession slutförts, kontrollerar systemet om det finns en instans av den här klassen och kör den om sådan finns.  

Följande flödesschema beskriver processen.  

[![Flödesdiagram](./media/product_configuration_2.png)](./media/product_configuration_2.png)  

Flödesschema över produktkonfigurations-API

## Produktkonfiguration
<a id="product-configuration" class="xliff"></a>
Produktkonfigurationen kan utföras från följande ställen:

-   Försäljningsorderrad
-   Försäljningsoffertrad
-   Inköpsorderrad
-   Produktion orderrad
-   Punkt krav (projekt)

Syftet med den är att skapa ett distinkt variant av produkt som uppfyller kundens krav. En unik konfigurations-ID skapas för varje ny konfiguration. Detta ID möjliggör spårning via lager.

### Flera orter och företagsinterna
<a id="multiple-sites-and-intercompany" class="xliff"></a>

Om konfigurationen kommer att ske på en ort, eller ens ett företag, som skiljer sig från den ort eller det företag där produktionen sker, BOM och rutten skapas för och sätta på leverantörens ort i det levererande företaget. Produkten variant kommer att släppas i alla företag som deltar i distributionskedjan.




