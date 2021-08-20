---
title: Produktidentifierare
description: Det här avsnittet innehåller information om de olika typerna av produktidentifierare och förklarar hur du infogar produktidentifierare i dina produktdata.
author: cvocph
ms.date: 03/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductEntityIdentifierCode, EcoResProductListPage, EcoResProductDetailsExtended, EcoResProductVariantsPerCompany
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: kamaybac
ms.dyn365.ops.version: 7.2999999999999998
ms.search.validFrom: 2017-12-31
ms.openlocfilehash: 1e706e184f0bdf3a44e69640a85a15d9cd3d0fb2ae097d6605a9a401d6da9051
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6746973"
---
# <a name="product-identifiers"></a>Produktidentifierare

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller information om de olika typerna av produktidentifierare och förklarar hur du infogar produktidentifierare i dina produktdata.

När du arbetar med produkter i fabriken eller på ett lagerställe i Microsoft Dynamics ERP eller Microsoft Dynamics CRM, måste du ha en bra strategi för att identifiera de produkterna och produktvarianterna.

## <a name="unique-product-numberproduct-id"></a>Unikt produktnummer/produkt-ID

I Dynamics 365 Supply Chain Management är den primära identifieraren för produktnumret (det vill säga unikt produkt-ID). Detta nummer kan genereras automatiskt av en nummerserie eller så kan det associeras manuellt med en produkt. Siffrorna kan definieras genom mallen för produktnomenklatur för produktvarianter.

I många fall skapades inte produktnumret ursprungligen i Dynamics 365 Supply Chain Management. I stället associeras det med en produkt i system för livscykelhantering för produkt (PLM) eller hantering av produktdata (PDM). I det här fallet kan du använda datatabeller för att importera produkterna och produktvarianterna. Supply Chain Management använder sedan numren i alla operationer.

När du implementerar Supply Chain Management bör du särskilt beakta din strategi för produktnummer. Ett bra numreringssystem förbättrar logistikflöden och förebygger fel. En bra produktidentifierare har högst 15 tecken. Idealiskt har den färre än 10 tecken och innehåller högst fem klassificeringstecken. Du kan också använda söknamn för att aktivera snabbsökning. Ett söknamn är ett ytterligare namn som representerar klassificeringen av en produkt.

När du använder Microsoft Dataverse är produktnumret i Supply Chain Management också produktnumret i Microsoft Dataverse. Produktvarianter synkroniseras till Dataverse som olika produkter.

## <a name="item-number-and-product-dimensions"></a>Artikelnummer och produktdimensioner

Artikelnumret är den produktidentifierare som används av en viss juridisk person. Vi rekommenderar att artikelnumret är identiskt med produktnumret. Om nomenklaturen skiljer sig per juridisk person, blir det svårt att följa en produkt genom leveranskedjan och betungande ommärkning och referensprocesser införs. För kompatibilitet med äldre versioner (det vill säga med Microsoft Dynamics AX 2009 och tidigare) har vi behållit den här modellen. Vi rekommenderar dock att du eliminerar identifierare som är specifika för juridiska personer när du kan och att du använder det unika produktnumret som den primära identifieraren i stället.

Dessutom kan en produktvariant inte identifieras unikt med ett artikelnummer. Det kräver alltid en kombination av ett artikelnummer och alla produktdimensioner som definieras på produktmallen. Detta krav kan bli svårhanterligt och kan sakta ner identifieringsprocesser. Därför rekommenderar vi att du använder det unika produktnumret i stället för artikelnumret så ofta du kan.

Många sidor har fortfarande artikelnummer och produktdimensioner som primära identifierare. Produktnummer kan dock användas för sökningar. Vid **Försäljning och marknadsföring**&gt;**Inställningar**&gt;**Sök**&gt;**Söka parametrar** kan du ändra sökuppslag så att den använder produktnummer i stället för artikelnummer som primär sökstrategi. Om du ställer in alternativet **Aktivera sökning för produktsökning** till **Ja**, kommer sökningen inte bara att visa produktmallar utan även produktvarianter. Mer information finns i [Sök efter produkter och produktvarianter under orderregistrering](search-products-product-variants.md)

Dessutom kommer du att kunna söka och filtrera på produktnummer, produktnamn och beskrivning och produktdimensionens ID för produktvarianten. När du väljer en variant kommer tillhörande artikelnummer och alla produktdimensioner att väljas. Därför kan du lättare hitta och välja rätt variant. Den här inställningen rekommenderas starkt om du använder produktvarianter och unika produktnummer som primära identifierare för produkter. Det enda undantaget kan vara modebranschen där affärsprocesserna kräver att du väljer originalet innan du väljer en variant. Du bör noggrant utvärdera det här alternativet innan du implementerar numreringssystemet.

> [!NOTE]
> Det går inte att ändra artikelnumret för en produkt när det finns en eller flera transaktioner för produkten.

## <a name="product-name-and-description"></a>Produktnamn och beskrivning

Produktnamn och beskrivning är läsbara identifierare för en produkt och kan hållas på flera språk. Supply Chain Management-klienten visar som standard all produktinformation på företagets standardspråk, inte på användarens språk. Översatta produktnamn och beskrivningar används emellertid i all kommunikation med kunder och leverantörer. Översättningarna baseras på språkkoden för kund- och leverantörskonton.

Produktnamnet kan genereras genom en mall för produktnomenklatur för produktvarianter. Eftersom det inte krävs att produktnamn är unika, kan du hitta flera produkter som har samma namn.

## <a name="product-and-item-search-names"></a>Produkt- och artikelsökningsnamn

Supply Chain Management erbjuder ett sekundärt söknamn för produkter och även för artiklar (frisläppta produkter). Dessa söknamn behöver inte vara unika och de kan ändras efter att en produkt eller produktvariant skapas. Vi rekommenderar att du använder söknamnet för att söka efter produkter efter kategorier. Söknamnen aktiverar snabbsökning, särskilt i försäljnings- och inköpsorderprocesser.

Söknamnet kan också innehålla en kund eller produkt-ID för leverantör eller några andra externa produkt-ID, om detta externa ID är det primära sökvillkoret för en produkt.

## <a name="external-product-identifiers-customer-and-vendor-identifiers"></a>Externa produktidentifierare (kund- och leverantörsidentifierare)

För frisläppta produkter kan du behålla de artikelnummer, artikelnamn och artikelbeskrivningar som kunden eller leverantören använder. Referenserna visas på externa dokument, till exempel försäljningsorder, inköpsorder, följesedlar och fakturor. I den aktuella versionen av Supply Chain Management visas externa referenser inte på sidor för kärnoperationer. Det enda undantaget är leverantörens artikelnummer. Det här numret visas i dialogrutan **Produktinformation** om en standardleverantör har definierats för frisläppt produkt.

Du kan underhålla externa produktidentifierare av frisläppt produkt, frisläppt produktvariant, kund eller kundgrupp, leverantör eller leverantörsgrupp.

På sidan **frisläppta produkter**, gör du något av följande.

- För kunder på fliken **Sälja** i gruppen **Relaterad information**, välj **Extern artikelbeskrivning**.
- För leverantörer på fliken **Köpa** i gruppen **Relaterad information**, välj **Extern artikelbeskrivning**.

På sidan **Externa artikelbeskrivningar** kan du koppla kundens eller leverantörens artikelnummer med en frisläppt produkt. Den här kopplingen måste göras för varje juridisk person. Du kan hämta följande information. Tyvärr är etiketterna lite missvisande i den aktuella versionen av Supply Chain Management. Etiketterna kan dock ändras i framtida versioner.

| Fält | Motsvarande kundinformation | Motsvarande leverantörsinformation |
|-------|------------------------------------|----------------------------------|
| Externt artikelnummer | Kundens artikelnummer. | Leverantörens artikelnummer. |
| beskrivning | Det namn som kunden har kopplat med artikeln | Det namn som leverantören har kopplat med artikeln |
| Extern artikeltext | Kundens artikelbeskrivning | Leverantörens artikelbeskrivning |

Du kan skapa grupper med kunder eller leverantörer som förenklar underhållet av extern produktinformation om många kunder eller leverantörer använder samma artikelnummer (som t.ex. gäller för en inköpsförening eller handelsgrupp).

- För kundgrupper, gå till **Försäljning**&gt;**Inställningar**&gt;**Artiklar**&gt;**Extern artikelbeskrivning** för att skapa och hantera grupper och tillhörande artikelnummer. Koppla kunder till en grupp genom att gå till **Kundreskontra**&gt;**Kunder**&gt;**Alla kunder** och sedan till på snabbfliken **Standardvärden för försäljningsorder** anger du ett värde i fältet **Artikel - kundgrupp**.
- För leverantörsgrupper, gå till **Anskaffning och källa** &gt; **Inställningar** &gt; **Extern artikelbeskrivningsgrupp** för att skapa och hantera grupper och tillhörande artikelnummer. Koppla leverantörer till en grupp genom att gå till **Leverantörsreskontra**&gt;**Leverantörer**&gt;**Alla leverantörer** och sedan till på snabbfliken **Standardvärden för inköpsorder** anger du ett värde i fältet **Artikel - leverantörsgrupp**.
 
## <a name="bar-codes"></a>Streckkoder

Om du vill använda en streckkodsskanner för att identifiera produkter måste produktidentifieraren uppfylla kraven för den streckkodsstandard som används. Därför innehåller streckkoder inte vanligtvis det råa produktnumret utan ett nummer som har genererats för vald streckkodsteknik. Du kan underhålla flera streckkoder efter streckkodstyp. Du kan även koppla samma streckkod till flera produkter och sedan välja den faktiska aktiva kopplingen när du skannar en streckkod.

Innan du definierar streckkoder kan du definiera en eller flera streckkodsinställningar. Streckkodsinställningar kan hjälpa dig att kontrollera att streckkoder följer nödvändiga riktlinjer och de kan därför effektivt skrivas ut och skannas. Du kan också upprätthålla särskilda streckkoder för specifika produktkvantiteter.

Vi rekommenderar att du använder streckkodsinställningar för att underhålla Global Trade Item Number (GTIN) eller internationella artikelnummer (EAN).

För att underhålla streckkoder, på sidan **Frisläppta produkter** på fliken **Hantera lager** i gruppen **Lagerställe** markerar du **Streckkoder**.

## <a name="gtin-codes"></a>GTIN-koder

Inom e-handel är det viktigt att alla parter talar ett gemensamt språk och hänvisar till produkter med en gemensam uppsättning identifierare. Därför kan vissa branscher vara beroende av [GTIN](https://www.gs1.org/id-keys/gtin), som är ett globalt artikelnummersystem som möjliggörs med hjälp av GS1.

Vi rekommenderar att du underhåller GTIN som en streckkod. Men du kan också hantera den på sidan **Artikel - GTIN**. För att öppna denna sida, på **Frisläppta produkter** på fliken **Hantera lager** i gruppen **Lagerställe** markerar du **GTIN-koder**. GTIN hanteras inte som ett globalt nummer. I stället hanteras det av juridisk person.

I Supply Chain Management definierar du förpackningsvarianter i lageroperationer genom att definiera specifika måttenheter. Till exempel kan en artikel lagras i delar, buntar med sex, i fack med 18 eller i fulla lastpallar. En specifik måttenhet ska fastställas för var och en av dessa förpackningsvarianterna. Eftersom GTIN normalt är relaterad till en produkts förpackningsenheten låter sidan **Artikel - GTIN** dig hantera flera GTIN-koder per produkt och måttenheten. Du kan inte använda samma GTIN-kod mer än en gång för olika artiklar eller produktvarianter i en juridisk person.

För att hantera **GTIN-koder**, på sidan **Frisläppta produkter**, på fliken **Hantera lager** i gruppen **Lagerställe** väljer du **GTIN**.

## <a name="external-codes"></a>Externa koder

Du kan definiera externa koder för många entiteter. Du kan till exempel definiera externa koder för att identifiera och frisläppta produkter. Dessa externa koder kan användas för att koppla statistiska koder eller momskoder med frisläppta produkter och frisläppta produktvarianter. Du definierar externa koder med juridisk person och kodtyp. De måste vara unika genom juridisk person, kodtyp och tabellreferens.

Det finns tyvärr ingen standardfunktion där du kan söka efter produkter efter externa koder.

## <a name="data-entities-that-are-used-to-import-and-export-product-identifiers"></a>Dataentiteter som används för att importera och exportera produktidentifierare

| Enhetsnamn | Importera identifierare | Exportera identifierare | Kommentarer |
|-------------|--------------------|--------------------|----------|
| Produker V2 | Produktnummer, produktsökningsnamn, produktnamn, produktbeskrivning | Produktnummer, produktsökningsnamn, produktnamn, produktbeskrivning | Beroende på inställningarna för enheten och nummerserien för produktnumret kan produktnummer skapas automatiskt vid tidpunkten för importen. |
| Produktvarianter | Produktnummer, produktsökningsnamn, produktnamn, produktbeskrivning | Produktnummer, produktsökningsnamn, produktnamn, produktbeskrivning | Beroende på vilken mall för produktnomenklatur kan produktnummer skapas automatiskt vid tidpunkten för importen. Men du kan importera alla unika produktnummer och det produktnumret behöver inte ha strukturen som mallen för produktnomenklatur. |
| Produktöversättningar | Produktnamn, produktbeskrivning | Produktnamn, produktbeskrivning | Den här entiteten skriver över alla språk. När det primära språket för namnet eller beskrivningen av en juridisk person skrivs över, ändras namn och beskrivning för produkten. |
| Frisläppt produktgenerering version2 | Artikelnummer, produktnummer, namn på artikelsökning| Artikelnummer, produktnummer, namn på artikelsökning, namn på produktsökning, produktnamn | Den här entiteten kan vara svår när nummerserier används när du skapar nya frisläppta produkter. Både nummerserien **Artikelnummer** och nummerserien **Produktnummer** påverkar. Men nummerserien **Artikelnummer** är per juridisk person, medan nummerserien **Produktnummer** är global. Därför rekommenderar vi inte att du använder nummerserien **Artikelnummer** när du distribuerar nya frisläppta produkter. Det är självklart att när enheten används för att frisläppa en befintlig produkt måste produktnumret anges i enheten. Mer information finns i avsnittet ”Produkt- och artikelnummerserier” i det här avsnittet. |
| Frisläppta produktvarianter | Artikelnummer, produktdimensioner, produktnummer | Produktnummer, produktsökningsnamn, produktnamn, produktbeskrivning, produktdimensioner | Liksom entiteten **Produktvarianter** kan den här entiteten kan användas för att skapa nya produkter som antingen följa mallen för produktnomenklatur eller egna produktnummer för varianten. |
| Extern artikelbeskrivning för kunder | Kundens artikelnummer, kundens artikelnamn, kundbeskrivning, kundkonto | Kundens artikelnummer, kundens artikelnamn, kundbeskrivning, kundkonto | En grupp med kunder (exempelvis en köparförening) kan samlas i en grupp med hjälp av entiteten **Kundgrupper för extern artikelbeskrivning**. |
| Extern artikelbeskrivning för säljare | Leverantörens artikelnummer, leverantörens artikelnamn, leverantörsbeskrivning, leverantörskonto | Leverantörens artikelnummer, leverantörens artikelnamn, leverantörsbeskrivning, leverantörskonto | En grupp med leverantörer (exempelvis en säljarförening eller branschorganisation) kan samlas i en grupp med hjälp av entiteten **Leverantörsgrupper för extern artikelbeskrivning**. |
| Artikelstreckkod | Streckkod | Streckkod | Vid tidpunkten för importen måste du hänvisa till en streckkodsinställning som definieras i målsystemet. De importerade streckkodreferenserna verifieras mot streckkodsinställningen och avvisas om streckkoderna inte motsvarar kraven som har definierats i dessa inställningar. |
| Externa koder för frisläppta produkter | Extern kod | Extern kod, externa kodklasser, artikelnummer | Externa koder är efter juridisk person. Vid import måste du hänvisa till en angiven kodklass. Importera kodklasser genom att använda entiteten **Externa kodklasser för frisläppta produkter**. |
| Externa koder för frisläppta produktvarianter | Extern kod | Extern kod, externa kodklasser, artikelnummer, produktdimensioner | Externa koder är efter juridisk person. Vid import måste du hänvisa till en angiven kodklass. Importera kodklasser genom att använda entiteten **Externa kodklasser för frisläppta produkter**. Den här entiteten avser produktvarianter efter artikelnummer och produktdimensioner. |
| Externa koder för frisläppta produktvarianter per produktnummeridentifierare | Extern kod | Extern kod, externa kodklasser, produktnummer | Externa koder är efter juridisk person. Vid import måste du hänvisa till en angiven kodklass. Importera kodklasser genom att använda entiteten **Externa kodklasser för frisläppta produkter**. Den här entiteten avser produktvarianter efter produktnummer av varianten. (Från nästa stora utgåva) |
| GTIN | Inte tillämpligt | Inte tillämpligt | För närvarande finns ingen specifik entitet som används för att importera och exportera GTIN-koder. Vi rekommenderar att du använder entiteten **Artikelstreckkod** i stället. |
| Entiteten identifierare av common data service | Inte tillämpligt | Artikelnummer, namn på artikelsökning, produktsökningsnamn, leverantörens artikelnummer, kundens artikelnummer, externa koder, GTIN-koder, streckkoder | Entiteten konsoliderar alla identifierare till en datamodell, så att ett gränssnitt kan användas för att enkelt exportera alla identifierare och deras relaterade typer. Använd entiteten **ID-koder för produktenhet** för att exportera identifieringskoder och beskrivningar. Använd entiteten **ID-omfattning för produktenhet** för att exportera ytterligare områdesinformation till en identifierare, till exempel part, juridisk person, kvantitet eller enhet. |

### <a name="product-and-item-number-sequences"></a>Produkt- och artikelnummerserier

Du kan definiera två olika nummerserier:

- Nummerserien för **Produktnummer** för det globala produktnumret
- Nummerserien för **Artikelnummer** för artikelnumret per juridisk person

> [!NOTE]
> Du bör använda artikelnumret som en separat identifierare bara när du migrerar andra juridiska enheter från olika källor som hade olika nummersystem. Du bör alltid försöka använda ett produkt-ID som är unikt inom alla juridiska personer. Därför bör du ange alternativet **Manuell** till **Ja** för nummerserien **Artikelnummer**. På detta sätt följer artikelnumret produktnumret när det skapas. Om Supply Chain Management inte är ledande system för nya produktnummer kan du ange alternativet **Manuell** till **Ja** för både nummerserier **Artikelnummer** och **Produktnummer**.

När du använder entiteten **Frisläppt produktgenerering V2** för att skapa produkter kan flera inställningar påverka hur nummerserierna används för att skapa artikelnumret och produktnumret:

- Inställningarna av nummerserien **Produktnummer**
- Inställningarna av nummerserien **Artikelnummer**
- Mappning av artikelnumret. 
- Mappning av produktnumret.

Följande tabell ger en översikt över resultaten av import och manuellt skapande vid specifika kombinationer av nummersekvens och fältmappningsinställningar.

| Nummerserien Produktnummer | Nummerserien Artikelnummer | Mappning av artikelnummer. | Mappning av produktnumret. | Resultat av entitetsimport | Resultat av manuellt skapande | Slutsats |
|--------------------------------|-----------------------------|----------------------------|-------------------------------|-------------------------|----------------------------|-----------|
| Manuell = Nej | Manuell = Nej | Ingen mappning | Ingen mappning | Produktnummer använder nummerserien **Produktnummer**. Artikelnummer använder nummerserien **Artikelnummer**. | Produktnummer använder nummerserien **Produktnummer**. Artikelnummer använder nummerserien **Artikelnummer**. | Med den här konfigurationen följer produktnumren följer produktnummerserien och artikelnumren följer artikelnummerserien. Den här konfigurationen fungerar dock inte om det finns fler än en artikel (rad) att importera. |
| Manuell = Nej | Manuell = Ja | Autogenerera | Ingen mappning | Både produktnummer och artikelnummer använder nummer serien **Artikelnummer**. | Både produktnummer och artikelnummer använder nummer serien **Produktnummer**. | Både produktnummer och artikelnummer följer produktnummersekvensen. Detta är den rekommenderade metoden för att importera bulkprodukter till dataentiteten Frisläppt produktgenerering V2.<br><br>Du kan bara använda det här arbetssättet vid bulkimport av artiklar (flera rader) och när du inte skapar artiklar via användargränssnittet. Om du behöver både importera bulk och skapa produkter via användargränssnittet, använder du istället proceduren på nästa rad i registret. För att övergå från att använda en bulkimportmetod till att använda användargränssnittet för att manuellt importera och skapa produkter måste du manuellt justera **Nästa nummer** i artikelnummerserien för att matcha **Nästa nummer** i produktnummersekvensen. Du kan sedan växla till nästa rad i det här registret. |
| Manuell = Nej | Manuell = Ja | Ingen mappning | Ingen mappning | Både produktnummer och artikelnummer använder nummer serien **Produktnummer**. | Både produktnummer och artikelnummer använder nummer serien **Produktnummer**. | Både produktnummer och artikelnummer använder produktnummersekvensen. Den här konfigurationen fungerar dock inte om det finns fler än en artikel (rad) att importera.<br><br>Du måste använda det här arbetssättet om du både behöver importera produkter med hjälp av enheterna (endast en rad kan importeras åt gången) och för att skapa produkter via användargränssnittet. |
| Manuell = Ja | Inte aktuellt | Inte aktuellt | Autogenerera | Du får följande felmeddelande: ”Nummerserien kan inte identifieras”. | Enligt nummerserien **Artikelnummer** | Den här inställningen stöds inte för import. |

## <a name="product-entity-identifier-export-all-product-identifiers"></a>Identifierare för produktenhet (exportera alla produktidentifierare)

Produktenhetens ID-modell skapades för att möjliggöra att version 1.0 av Dataverse tillhandahålls med alla identifierare som används för att referera till en produkt. För att förenkla uppgiften samlas alla identifierare i en global identifierartabell så att de kan exporteras som en modell. Observera att den här versionen av Dataverse inte använder produktidentifierarens modell. Därför har entiteten **Produktentiteten identifierare av common data service** och denna process begränsad praktisk användning och kommer sannolikt att ändras i framtiden.

Tabellen för produktidentifierare är en globalt tabell som är ifylld från alla referenstabeller från den huvudsakliga juridiska personen genom ett återkommande batchjobb. Du måste välja en juridisk person och en produktkategorihierarki som definition av den globala produktmallomfattningen. Generering av den globala tabellen för produktidentifierare begränsas till produkter som övergår till den valda juridiska personen och produkter som ingår i produkthierarkin som har valts för rollen **Common data service** i produktkategorihierarkin.

Den här processen förutsätter att huvuddata för produkt huvudsakligen hålls i en central juridisk person. (Den här juridiska personen kan dock vara en virtuell juridisk person som endast används för att upprätthålla globala huvuddata.)

Gör på följande sätt när du vill konfigurera miljön.

1. Välj kategorihierarki för Dataverse. På sidan **Rollassociationer för kategorihierarkier** om ingen hierarki är associerad med rollen **Common data service** måste du skapa en ny association. Välj rollen **Common Data Service** och associera sedan den kategorihierarki som representerar produktportföljen som ska synkroniseras till Dataverse.
2. Välj juridisk person för globala huvuddata för produkt. På sidan **Parametrar för produktinformationshantering** på fliken **Produktattribut** väljer du det huvudföretag där produkt- och artikelidentifierarna huvudsakligen hålls.
3. Definiera ID-kodtyper och koder som ska exporteras. Gå till **Produktinformationshantering**&gt;**Inställningar**&gt;**ID-koder för produkt**. Om du vill generera ID-kodtyperna, välj **Generera koder**. En kodtyppost genereras för varje typ för identifierare som finns i den valda juridiska personen.

    För streckkoder genereras en kodtyp för varje streckkodsinställningar. För externa koder genereras en kodtyp för varje extern kodklass.

    Nu kan du underhålla listan över kodtyper. Du kan ändra kod, namn och beskrivning. Du kan också radera kodtyper. Kodtyper som du tar bort används inte för att fylla i de globala produktenhetens ID-tabeller

4. När du har definierat kodtyper för produktidentifierare kan du skapa identifierare i den globala tabellen genom att starta jobbet **Skapa identifierare för produktenhet** på sidan **ID-koder för produktenhet**. Du bör köra det här jobbet i en batch. Det här jobbet bör ställas in som ett återkommande batchjobb så att tabellen fylls i enligt nya poster.

Nu kan du använda dataentiteterna **Entiteten identifierare av common data service**, **ID-kod för produktenhet** och **ID-omfattning för produktenhet** för att exportera identifierarna för ett målsystem.

## <a name="related-topic"></a>Relaterat ämne

[Sök efter produkter och produktvarianter under orderregistrering](search-products-product-variants.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
