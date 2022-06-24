---
title: Hantering av försäljningspris (butik)
description: Denna artikel beskriver begreppen för att skapa och hantera försäljningspriser i Dynamics 365 Commerce.
author: ShalabhjainMSFT
ms.date: 07/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: retail
ms.author: shajain
ms.search.validFrom: 2018-03-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 16c948e6e14309f4e340bf622fac42b14e6ee591
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8887020"
---
# <a name="retail-sales-price-management"></a>Hantering av försäljningspris (butik)

[!include [banner](includes/banner.md)]

Denna artikel innehåller information om att skapa och hantera försäljningspriser i Dynamics 365 Commerce. Det fokuserar på begreppen som ingår i den här processen och på effekterna av olika konfigurationsalternativ för försäljningspriser.

## <a name="terminology"></a>Terminologi

Följande termer används i denna artikel:

| Villkor | Definition, användning och anteckningar |
|---|---|
| Pris | Det enkla enhetsbelopp som en produkt säljs för i en kassaklient eller på en försäljningsorder. I denna artikel avser termen *pris* alltid försäljningspriset, inte lagerpris eller självkostnad. |
| Grundpris | Det pris som anges i fältet **Pris** på en frisläppt produkt. |
| Handelsavtalspris | Priset som anges på en produkt eller variant genom att använda ett handelsavtal av typen **Pris (försäljn.)**. |
| Bästa pris | När flera priset eller rabatter kan användas för en produkt, ger det minsta prisbeloppet och/eller det största rabattbeloppet det lägsta möjliga nettobeloppet som kunden måste betala. I denna artikel avser alltid begreppet bästa pris ”bästa pris”. Det bästa priset skiljer sig från och bör inte förväxlas med uppräkningsvärde **Bästa pris** för en rabatts concurrency-läge. |

## <a name="price-groups"></a>Prisgrupper

Prisgrupper är den centrala delen av pris- och rabatthanteringen i Commerce. Prisgrupper används för att tilldela priser och rabatter till Commerce-enheter (dvs kanaler, kataloger, anknytningar och bonusprogram). Eftersom prisgrupper används för alla priser och rabatter, är det viktigt att du planerar hur du använder dem innan du börjar.

En prisgrupp är i sig bara ett namn, en beskrivning och eventuellt en prissättningsprioritet. Den viktigaste punkten att komma ihåg angående prisgrupper är att de används för att hantera många-till-många-relationer som rabatter och priser med Commerce-enheter.

Följande bild visar hur prisgrupper används. I den här illustrationen observera att ”prisgrupp” är bokstavligen i centrum för prissättning och rabatthantering. Commerce-enheterna som du kan använda för att hantera olika priser och rabatter finns till vänster, och de faktiska pris- och rabattposterna visas till höger.

![Prisgrupper.](./media/PriceGroups.png "Prisgrupper")

När du skapar prisgrupper bör du inte använda en enda prisgrupp för flera typer av Commerce-enheter. I annat fall kan det vara svårt att avgöra varför ett särskilt pris eller en rabatt används i en transaktion.

När en röd streckad linje i bilden visas ger Commerce inte stöd för huvudfunktionerna i Microsoft Dynamics 365 för en prisgrupp som anges direkt på en kund. I detta fall får du endast handelsavtal för försäljningspris. Om du vill använda kundspecifika priser rekommenderar vi att du inte anger prisgrupper direkt på kunden. Du bör i stället använda anknytningar. 

Observera att om prisgruppen har ställts in för kunden, kommer den här prisgruppen att associeras med försäljningsorderrubriken för de order som skapas för den här kunden. Om användaren ändrar prisgruppen i orderrubriken ersätts den gamla prisgruppen bara med den nya prisgruppen för den aktuella ordern. Den gamla prisgruppen kommer till exempel inte att påverka den aktuella ordern, men den kommer fortfarande att vara kopplad till kunden för framtida order.

Följande avsnitt innehåller mer information om de Commerce-enheter som du kan använda när du vill konfigurera olika priser när prisgrupperna används. Konfigurationen av priser och rabatter för dessa enheter är en tvåstegsprocess. Dessa steg kan göras i vilken ordning som helst. Den logiska ordningen är emellertid att först ange prisgrupperna för entiteterna eftersom det här steget är engångsinställningar som görs under genomförandet. Därefter när priser och rabatter skapas kan du ange prisgrupperna för dessa priser och rabatter separat.

### <a name="channels"></a>Kanaler

Inom handel är det mycket vanligt att det finns olika priser i olika kanaler. Två andra faktorer som påverkar kanalspecifika priser är kostnader och lokala marknadsvillkor.

- **Kostnader** – Ju längre bort en kanal är från produktkällan, desto mer kostar det att lagra en produkt. Färska produkter har exempelvis en begränsad hållbarhetstid och särskilda krav på produktionen (exempelvis växtsäsong). På vintern kostar färsk sallat sannolikt mer i norra klimat än i södra klimat. Om du anger priser för kanaler över ett stort geografiskt område vill du förmodligen ange olika priser i olika kanaler.
- **Lokala marknadsvillkor** – En butik som har en direkt konkurrent över gatan blir mycket mer priskänslig än en butik som inte har en direkt konkurrent i närheten.

### <a name="affiliations"></a>Anknytningar

En allmän definition av en anknytning är en länk eller koppling till en grupp. I Commerce är anknytningar grupper av kunder. Anknytningar är ett mycket flexibelt verktyg för kundens prissättning och rabatter än det grundläggande Microsoft Dynamics 365-begreppet för kundgrupper och rabattgrupper. Först kan en anknytning användas för både priser och rabatter, medan en icke-butiksprissättning för varje typ av rabatt och pris. Sedan kan en kund tillhöra flera anknytningar men kan endast tillhöra en icke-butiksprissättningsgrupp för varje typ. Slutligen kan även anknytningar ställas in så att de är kopplade till en kund, de behöver inte vara en. En ad hoc-anknytning kan användas för anonyma kunder i POS. Ett typiskt exempel på en anonym anknytningsrabatt är en pensionärs- eller studentrabatt där en kund kan erhålla en rabatt genom att bara visa ett gruppmedlemskort.

Även om anknytningar oftast är associerade med rabatter, kan du också använda dem för att ange olika priser. När t.ex. en återförsäljare säljer till en medarbetare, kan den vilja ändra försäljningspriset i stället för att tillämpa en rabatt på ordinarie pris. Ett annat exempel är att en återförsäljare som säljer till både konsumentkunder och affärskunder kan erbjuda bättre priser baserad på deras inköpsvolym. Anknytningar tillåter båda dessa situationer.

### <a name="loyalty-programs"></a>Bonusprogram

I relation till priser och rabatter är bonusprogram bara en anknytning som har ett särskilt namn. Både priser och rabatter kan ställas in för ett bonusprogram precis som de kan ställas in för en anknytning. Men sättet som kunder får förmånsprissättning vid transaktioner eller order skiljer sig från hur de får anknytningsprissättning. Kunder kan endast få förmånsprissättning om ett förmånskort läggs till en transaktion. När ett förmånskort läggs till i en transaktion, läggs även bonusprogrammet till. Bonusprogrammet kan sedan aktivera särskilda priser och rabatter.

Bonusprogram kan ha flera nivåer och rabatterna kan variera för olika nivåer. På så sätt kan återförsäljare ge kunder större belöningar utan att behöva sätta dessa kunder manuellt i en specialgrupp.

Bonusprogram har fler funktioner förutom priser och rabatter. Från perspektivet priser och rabatter äran de emellertid samma som anknytningar.

### <a name="catalogs"></a>Kataloger

Vissa återförsäljare använder fysiska eller virtuella kataloger för att marknadsföra produkter och prissätter dem för fokuserade grupper av kunder. Som en del av deras affärsmodell att marknadsföra via en katalog kan dessa återförsäljare ange olika priser på deras olika kataloger. Microsoft Dynamics 365 stöder denna funktion genom att låta dig ange katalogspecifika rabatter och priser, på samma sätt som du kan definiera kanalspecifika eller anknytningsspecifika rabatter. När du redigerar en katalog kan du koppla prisgrupper till katalogen på samma sätt som du kan koppla dem till en kanal, anknytning eller bonusprogram.

### <a name="best-practices-for-price-groups"></a>Metodtips för prisgrupper

Använd inte en prisgrupp för flera typer av enheter. I stället använder du en uppsättning prisgrupper för kanaler, en annan uppsättning prisgrupper för anknytningar eller bonusprogram, osv. Du kan använda ett prefix eller suffix i namnet på prisgruppen för att gruppera de olika typerna av prisgrupper som du använder.

Undvik att ange prisgrupper direkt på en kund. Använd i stället en anknytning. På så sätt kan du tilldela alla typer av priser och rabatter till kunder, inte bara handelsavtal med försäljningspriser.

## <a name="pricing-priority"></a>Prisprioritet

En prissättningsprioritet är i sig bara ett nummer och en beskrivning. Prissättningsprioriteter kan användas i olika prisgrupper eller de kan tillämpas direkt på rabatter När prisprioriteter används kan en återförsäljare åsidosätta principen om bästa pris genom att styra ordningen som priser och rabatter tillämpas på produkter. Ett större prissättningsprioritetnummer utvärderas före ett lägre prisprioritetsnummer. Även om ett pris eller en rabatt finns på något prioritetsnummer ignoreras alla priser och rabatter som har lägre prioritetsnummer.

Pris och rabatt kan komma från två olika prissättningsprioriteter eftersom prissättningprioriteringar gäller priser och rabatter separat.

Om du vill använda prissättningsprioritet för priser måste du tilldela en prioritera en prissättningsprioritet och sedan skapa ett handelsavtal för försäljningspris för den prisgruppen.

Funktionen prissättningsprioritet infördes så att den stöder ett scenario där en återförsäljare vill tillämpa högre priser i en viss uppsättning butiker. En återförsäljare har t.ex. definierat nationella priser för ostkusten, men vill ha högre priser för vissa produkter i New York-butiker eftersom det kostar mer sälja vissa produkter på orten och/eller eftersom den lokala marknaden kommer att utgöra ett högre pris.

Som beskrivs i avsnittet ”Bästa pris” i denna artikel väljer prissättningsmotorn vanligtvis det lägre av två priser. Därför förhindras återförsäljaren vanligen från att använda det högre av två priser i en butik som har både ostkust och New York-prisgrupper. För att lösa problemet innan funktionen prissättningsprioritet infördes, behövde återförsäljaren definiera priser för varje produkt två gånger och inte tilldela båda prisgrupper. Alternativt kan återförsäljaren var tvungen att skapa extra prisgrupper för att isolera de produkter som har högre priser från produkter som har normala, lägre priser.

Funktionen prissättningsprioritet kan dock skapa prisprioritet för butikspriser som är högre än prisprioritet för nationella priser. Återförsäljaren kan även skapa prisprioritet för butikspriser och lämna nationella priser vid prissättningsprioritet 0 (noll) som standard. Båda inställningar garanterar att butikspriser alltid används innan nationella priser.

### <a name="pricing-priority-example"></a>Exempel på prisprioritet

Låt oss titta på ett exempel där butikspriser åsidosätter andra priser.

En nationell återförsäljare anger de flesta priser per region och har fyra områden: Nordöst, Sydöst, Mellanvästern och Väst. Den har identifierat flera höga kostnadsmarknader som stöder högre priser. Dessa marknader är i New York City, Chicago och San Francisco.

I det här exemplet ska vi gå till regionen Nordöst. Butik 1 finns i Boston och butik 2 i Manhattan. För Boston-butiken är två prisgrupper kopplade till kanalen: nordöst och Butik 1. För Manhattan-butiken är tre prisgrupper kopplade till kanalen: nordöst, NYC och Butik 2.

Återförsäljaren anger två prissättningsprioriteter: hög kostnad har prioritetsnummer 5 och i butikspriser har prioritetsnummer 10. (Kom ihåg att som standard är prissättningsprioritet 0 \[noll\], och ett pris eller en rabatt med högre prioritet används innan ett pris eller en rabatt med ett lägre prioritetsnummer.) Prisgruppen nordöst har prissättningsprioritet standardvärdet på **0** (noll). Prisgrupp NYC prissättningsprioritet anges till **5**, eftersom New York City är en hög kostnadsmarknad. För prisgrupperna för butik 1 och 2 har prissättningsprioriteten värdet **10**.

Två produkter som återförsäljaren säljer är produkt 1, en T-shirt och produkt 2, branschspecifika modejeans.

| Produkt | Nordöst pris | NYC pris | Butikspris |
|---|---|---|---|
| T-shirt | $15 | Inte inställd | Inte inställd |
| Modejeans | $50 | $70 | Inte inställd |

T-shirten säljs för samma pris (dvs. $15) i både Boston- och Manhattan-butiker, eftersom endast ett pris har angetts i nordöstra prisgruppen som är kopplad till båda kanalerna. Modejeans säljer för $50 i Boston-butiken eftersom detta pris är det enda pris som finns i den här butiken. Men i Manhattan-butiken finns två priser: $50 och $70. Eftersom prissättningsprioritet 5 för prisgruppen NYC är högre än prissättningsprioritet 0 (noll) för prisgruppen nordöst ska priset vara $70 i kassasystemet.

> [!NOTE]
> För varje prissättningsprioritet krävs fullständig passsering genom logiken för butiksprissättningsmotorn. För att upprätthålla prestanda för pris- och rabattberäkningen, bör du därför använda prissättningsprioriteringar sparsamt.

## <a name="types-of-prices"></a>Typer av priser

Du kan ange priset på en produkt i Microsoft Dynamics 365 på tre platser:

- Direkt på produkten (grundpris)
- I ett handelsavtal för försäljningspris
- I en prisjustering

Grundpris och handelsavtalspriset ingår i kärninstallationen av Dynamics 365 och är tillgängliga även om du inte använder Commerce. Funktionen prisjustering är endast tillgänglig i Commerce. Nästa avsnitt innehåller mer information om dessa alternativ för att ange priser och förklarar hur alternativen fungerar tillsammans.

## <a name="setting-prices"></a>Prissättning

### <a name="base-price"></a>Grundpris

Den enklaste platsen att ange priset för en produkt är direkt på produkten. Det värde du angav direkt på en produkt kallas ofta grundpriset för produkten. Du anger grundpris i fältet **pris** på fliken **sälj** på sidan **Information om frisläppt produkt**. Värdet du anger är i företagets valuta. Som standard är priset för en kvantitet på 1 i måttenheten (UoM) som har angetts i fältet **enhet** på fliken **sälj**. Det faktiska priset per enhet av en produkt baseras på måttenheten, priskvantitet och valuta.

Om en produkt har ett pris för alla ger grundpriset det mest effektiva sättet att hantera priset på produkten. Även om du använder handelsavtal för att ange priser kan du också ange grundpriset på en produkt. Om du inte använder en handelsavtal **alla** har du ett reservpriset som används när inga handelsavtal gäller.

Om en kanals valuta skiljer sig från företagsvalutan, bestäms grundpriset i denna kanal med hjälp av valutakonvertering på priset som har angetts för produkten.

Även om prisenheten inte är vanligt scenario ger prissättningsmotorn stöd för den. Om prisenheten har tilldelats ett värde annat än **0** (noll), är pris per enhet lika med pris/prisenhet. Om priset på en produkt är $10,00 och prisenheten är 50, är priset för kvantiteten 1 $0,20 (= $10,00/50).

### <a name="sales-price-trade-agreement"></a>Handelsavtal för försäljningspris

Du kan skapa handelsavtal för varje produkt genom att använda handelsavtalsjournalen. I Microsoft Dynamics 365 finns tre kundomfattningar för handelsavtal för försäljningspris: **tabell**, **grupp** och **alla**. Kundens omfattning bestämmer kunder som ges ett visst handelsavtal för försäljningspris.

Ett handelsavtal för försäljningspris **Tabell** är för en kund som anges direkt i handelsavtalet. Detta scenario är inte ett vanligt B2C-scenario. Om detta uppstår kommer prissättningsmotorn att använda handelsavtal **tabell** för att fastställa priset.

Ett handelsavtal för prissättningen **grupp** är den typ som används oftast. Utanför handel är handelsavtal för prissättningen **grupp** för en enkel kundgrupp. Men i Commerce har begreppet kundgrupp utökats så att det är en mer allmän prisgrupp. En prisgrupp kan länkas till en kanal, anknytning, bonusprogram eller katalog. Detaljerad information om prisgrupper finns i avsnittet ”Prisgrupper” tidigare i denna artikel.

> [!NOTE]
> Ett pris för handelsavtalet används alltid före grundpris.

### <a name="price-adjustment"></a>Prisjustering

Som namnet antyder används en prisjustering för att ändra det pris som antingen anges direkt på produkten eller som anges med ett handelsavtal. Du kan bara använda en prisjustering till att sänka priset inte höja det. En prisjustering är det rekommenderade sättet för återförsäljare att skapa, spåra och hantera prissänkning för sina produkter på längre sikt.

Det finns tre typer av prisjusteringar: procent av, belopp av och pris. En prisjustering av hur många procent av eller ett belopp av typen används alltid en försäljningstransaktion. En prisjustering av pristypen tillämpas endast om det ändrade priset är mindre än det pris som skapats med hjälp av grundpriset eller handelsavtalspris. Därför om det pris som anges i en prisjustering överstiger det ej justerade priset, används prisjusteringen inte.

## <a name="determining-price-for-a-product-in-a-transaction"></a>Att fastställa priset för en produkt i en transaktion

Beräkningen av pris- och rabattinformation för en transaktion använder principen att hitta det bästa priset för kunden. Om det finns fler än ett pris, enligt den här principen används det lägsta priset. Dessutom används en kombination av rabatter som ger det största rabattbeloppet för hela transaktionen. I vissa fall kan en mindre rabatt användas på en och samma produkt så att rabatt kan tillämpas på andra produkter i transaktionen.

Det enda undantaget från principen att hitta det bästa priset för kunden är ett alternativ för minst kostsamma mixa och matcha-rabatter. Detta alternativ tillåter minst kostsamma rabatter att ge företräde åt återförsäljarens när produkter har valts och grupperats. När en transaktion innehåller fler produkter än vad som behövs för erhållande av minst kostsamma rabatten, väljer prissättningsmotorn därför produkter som ger minsta möjliga rabattbeloppet angivet för kunden.

Prissättningsmotorn returnerar tre priser för varje produkt: grundpris, handelsavtalspris och aktivt pris.

Grundpriset är bara egenskapen för produkten och samma för alla överallt.

I handelsavtalet för försäljningspris om alternativet **Sök nästa** är **Ja**, används det lägsta priset för tillämpligt handelsavtalet för försäljningspris som handelsavtalspriset. Handelsavtal kan hittas med hjälp av prisgrupper eller kontokoden **ALLA**. Handelsavtal kan alternativt tilldelas direkt till en kund. Om alternativet **Sök nästa** är **Nej**, används det första handelsavtalspriset som hittas. Om det inte finns några handelsavtal är handelsavtalspriset lika med grundpriset.

Det aktiva priset beräknas genom att använda handelsavtalspriset och tillämpa största prisjusteringen som gäller för produkten. Om det inte finns några prisjusteringar eller om beräknat aktivt pris är större än handelsavtalspriset anges det aktiva priset till handelsavtalspriset. Kom ihåg att du inte kan höja priset på en produkt med hjälp av en prisjustering. Du hittar tillämpliga prisjusteringar genom att använda prisgrupper för artiklar som har tilldelats en kanal, katalog, anknytning eller förmånsprogram.

## <a name="category-price-rules"></a>Kategoriprisregler

Kategoriprisregelfunktionen i Commerce ger ett enkelt sätt att skapa nya handelsavtal för alla produkter i en kategori. Den här funktionen låter dig automatiskt söka efter befintliga handelsavtal för produkter i kategorin och upphöra dem.

När du väljer alternativet att upphöra befintliga handelsavtal skapar systemet en ny handelsavtalsjournalen för produkter i kategorin som har ett aktivt handelsavtal. Men journalen bokföras manuellt. Dessutom hittar nu kategoriprisregler befintliga handelsavtal endast om du använder samma prisregel (d.v.s. om du skapar en ny prisregel som använder samma kategori som tidigare). Om du inte använder samma prisregel kommer inte befintliga handelsavtal upphöra att gälla.

Priserna kan ökas eller minskas med fälten **prisregel** och **prisbas** för kategoriprisregler.

- I fältet **Prisregel** väljer du vilken typ av prisändring du vill använda:

    - **Pålägg** – En procentandel av prisbasen används för att beräkna försäljningspriset. Till exempel en produkt som kostar 10,00 och säljs för 15,00 har ett pålägg på 50 procent.
    - **Marginal** – En procentandel av försäljningspriset som används för att beräkna vinstbeloppet. Exempel: En produkt som kostar 10,00 och säljs för 15,00 har en marginal på 33,3 procent.
    - **Fast belopp** – Ett belopp som läggs till i prisbasen som används för att beräkna försäljningspriset. Exempel: En produkt som kostar 10,00 och säljs för 15,00 har ett fast belopp på 5,00.

- I fältet **Prisbas** ange pristypen du vill ändra:

    - **Baskostnad** – Det belopp som återförsäljaren har betalat till leverantören.
    - **Baspriset** – Försäljningspriset innan handelsavtal och prisjusteringar tillämpats.
    - **Aktuellt pris** – Försäljningspriset efter handelsavtal och prisjusteringar tillämpats.

För att enkelt uppdatera priserna på olika produkter från olika produktkategorier kan du använda de kompletterande produktkategorierna tillsammans med kategoriprisreglerna.

## <a name="best-practices"></a>Regelverk

Microsoft SQL Server Express används ofta för kanaldatabaser på grund av kostnaden (kostnadsfri). Tänk på att SQL Server Express har maskinvarubegränsningar och begränsningar på datastorlek. Om du inte planerar korrekt kan du snabbt nå datastorleksbegränsningar av SQL Server Express. Detta gäller varor och också andra delar av produkten. Här följer några tips som kan hjälpa dig att minska mängden data:

- Om du använder handelsavtal och ändrar dina priser, ska du upphöra att gälla de gamla handelsavtalen genom att ange ett slutdatum. Med tiden minskar du antalet handelsavtal som hålls i kanaldatabaser. Det hjälper dig också att minska mängden data som prisberäkningsalgoritmen måste samarbeta med.
- Om priserna varierar efter produktvariant kan du använda produktbaspris som pris för den vanligaste varianten. Använd sedan handelsavtal för variantpriserna som undantag. Den här metoden kan minska antalet handelsavtalsposter. Eftersom det är så enkelt att importera data till Microsoft Dynamics 365 kan du kanske frestas att importera ett handelsavtal för varje variant av varje enskild produkt. Detta tillvägagångssätt kan emellertid producera många handelsavtal som har samma värde. Det kan därför öka mängden data i onödan.
- Commerce behandlar variantspecifika priser i ordning från mest specifika till minst specifika. Om en produktdimension inte påverkar priset ska du inte definiera handelsavtal för den. Till exempel en produkt är tillgänglig i tre färger och fyra storlekar och priset varierar endast efter storlek. Om du definierar ett handelsavtal för varje variant kan skapa du 12 poster. Istället kan du definiera handelsavtal för varje storlek och lämna färgdimensionen tom. I det här fallet kan du skapa fyra poster.

    Om inte alla värden för en dimensionshierarki leder till ett annat pris, kan du också definiera ett handelsavtal för produktmallen och lämna alla produktdimensioner tomma. Definiera sedan ett separat handelsavtal för varje dimensionsvärde som leder till ett annat pris. Exempelvis om storleken XXL har ett högre pris, men alla storlekar har samma pris, kräver du två handelsavtal: en för produktmallen och en XXL storleken.

## <a name="prices-that-include-tax-vs-prices-that-exclude-tax"></a>Priser som omfattar skatt jämfört med priser exklusive skatt

När du anger försäljningspriser i Dynamics 365, anger du inte om prisvärdet du anger inkluderar eller exkluderar skatt. Värdet är bara priset. Men inställningen **Pris inkluderar moms** på kanaler låter dig konfigurera kanaler så att de inkluderar eller exkluderar skatt från priser. Inställningen är inställd på kanalen och ändra även i ett enskilt företag.

Om du arbetar med både inkluderad och exkluderad skatt är det viktigt att du har korrekt inställda priser, eftersom totalbeloppet som kunden betalar ändras om inställningen **Pris inkluderar moms** ändras för kanalen.

## <a name="differences-between-commerce-pricing-and-non-commerce-pricing"></a>Skillnader mellan Commerce-prissättning och icke-Commerce-prissättning

En enda prissättningsmotor används för att beräkna priserna i alla kanaler: kundtjänst, butiker och onlinebutiker. Detta bidrar till att möjliggöra de enhetliga Commerce-scenarierna.

Prissättning fungerar med Commerce-enheter istället för icke-Commerce-enheter. Särskilt utformad för att konfigurera priser per butik, inte per lagerställe.

Commerce-prissättningsmotorn **stöder inte** följande prissättningsfunktioner:

- Det går inte att ange priser efter plats eller plats och lagringsdimensioner för lagerställe. Om du bara anger platsdimensionen på handelsavtalen ignoreras webbplatsen av prissättningsmotorn och handelsavtalet tillämpas på alla webbplatser. Om du anger både webbplats och lagerställe är beteendet odefinierat/oprövat eftersom det förväntas att återförsäljare använder butikspris grupperna för att kontrollera priserna för varje butik/lagerställe.
- Attributbaserad prissättning stöds inte.
- Leverantörsrabattens genomströmning stöds inte.
- Den generiska valutafunktionen stöds inte, det vill säga även om ett handelsavtal har växeln **Inkludera generisk valuta** kommer detta handelsavtal fortfarande endast att anses giltigt för den valuta som definieras i handelsavtalet.
- Standard prissättningsmotorn för Supply Chain Management stöder prisberäkningen baserat på "begärt transportdatum" och "begärt inleveransdatum" tillsammans med aktuellt datum. Butikspriset stöder dock för närvarande inte dessa värden. Orsaken till detta är att kunder för B2C-scenario inte förväntar sig begärt leveransdatum för att påverka artikelpriset. I vissa fall har återförsäljare både B2B- och B2C-åtgärder. För B2B-åtgärder är det vanligt att ändra priser baserat på leveransdatum. Dessa återförsäljare kan använda Supply Chain Management prissättning för B2B-företag och återförsäljningspris för deras B2C-företag. Självkostnaden aktiveras bara om programanvändaren läggs till som en kundtjänstanvändare, så återförsäljarna kan tilldela vissa användare som kommer att arbeta med Supply Chain Management prissättning och tilldela ett par som fungerar med butikspriset, dvs. dessa användare bör läggas till som en kundtjänstanvändare. Dessutom måste egenskapen **Använd dagens datum för att beräkna priser** i avsnittet **Handelsparametrar > Prissättning och rabatter > Diverse** vara aktiverade. På så sätt kan de behålla det använda kundreskontra parametervärden för begärt transportdatum eller begärt inleveransdatum för Supply Chain Management prissättning, men återförsäljarpriset fortsätter att använda dagens datum för prisberäkning.

Dessutom, **endast** Commerce-prissättningsmotorn stöder följande prissättningsfunktioner:

- Priset baseras på produktdimensioner i ordning från de mest specifika variantpriset till det minst specifika variantpriset till produktmallpriset. Ett pris som anges med två produktdimensioner (till exempel färg och storlek) används innan ett pris som anges med hjälp av en enda produktdimensionen (exempelvis storlek).
- Samma prisgrupp kan användas för att kontrollera priser och rabatter.

## <a name="pricing-api-enhancements"></a>Förbättringar av prissättnings-API

Pris är en av de viktigaste faktorerna som kontrollerar köpbesluten för många kunder och många kunder jämför priserna på olika webbplatser innan de gör ett inköp. För att garantera att de erbjuder konkurrenskraftiga priser håller återförsäljare ett öga på sina konkurrenter och kör ofta erbjudanden. För att hjälpa dessa återförsäljare att locka till sig kunderna är det mycket viktigt att produktsökningen, bläddringsfunktionen, listorna och produktinformation visar de mest exakta priserna.

API:n **GetActivePrices** (Application Programming Interface) i Commerce returnerar priser som innehåller enkla rabatter (t.ex. rabatter på en rad som inte är beroende av andra artiklar i varukorgen). På så sätt ligger priserna som visas nära det faktiska beloppet som kunderna ska betala för artiklar. Denna API kommer att innehålla alla typer av enkla rabatter: anknytningsbaserade, lojalitetsbaserade, katalogbaserade och kanalbaserade rabatter. Dessutom returnerar API:er namn och giltighetsinformation för de rabatter som används, så att detaljhandlare kan ge en mer detaljerad beskrivning av priset och skapa en uppfattning om hur rabatten kommer att förfalla snart.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
