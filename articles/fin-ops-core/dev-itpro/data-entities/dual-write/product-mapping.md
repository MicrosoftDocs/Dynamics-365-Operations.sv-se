---
title: Enhetlig produktupplevelse
description: I den här artikeln beskrivs integreringen av produktdata mellan appar för ekonomi och drift och Dataverse.
author: t-benebo
ms.date: 06/23/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 1546cdaf3c63a7ff9a330ae8609595aaf48fbc48
ms.sourcegitcommit: 6781fc47606b266873385b901c302819ab211b82
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/02/2022
ms.locfileid: "9111499"
---
# <a name="unified-product-experience"></a>Enhetlig produktupplevelse

[!include [banner](../../includes/banner.md)]



När ett affärsekosystem utgörs av Dynamics 365-program, t.ex. Finance, Supply Chain Management och Sales använder verksamheter ofta dessa program för att ange produktdata. Detta beror på att dessa appar ger en robust produktinfrastruktur som kompletteras med sofistikerade prissättningsbegrepp och korrekta lagerbehållningsdata. Verksamheter som använder ett externt PLM-system (Product Lifecycle Management) för anskaffning av produktdata kan kanalisera produkter från appar för ekonomi och drift till andra Dynamics 365-appar. Den enhetliga produktupplevelsen för den integrerade produktens datamodell till Dataverse så att alla programanvändare inklusive Power Platform-användare kan dra nytta av de omfattande produktdata som kommer från appar för ekonomi och drift.

Här är produktdatamodellen från Sales.

![Datamodell för produkter i CE.](media/dual-write-product-4.jpg)

Här visas produktdatamodellen från appar för ekonomi och drift.

![Datamodell för produkter i ekonomi och drift.](media/dual-write-products-5.jpg)

Dessa två produktdatamodeller har integrerats i Dataverse som visas nedan.

![Datamodell för produkter i Dynamics 365-appar.](media/dual-write-products-6.jpg)

Tabellmappningar med dubbelriktad skrivning för produkter har utformats så att data endast kan flöda i en riktning, i närapå realtid från appar för ekonomi och drift till Dataverse. Produktinfrastrukturen har dock gjorts öppen så att den är dubbelriktad vid behov. Även om du kan anpassa den på din egen risk eftersom Microsoft inte rekommenderar det här tillvägagångssättet.

## <a name="templates"></a>Mallar

Produktinformationen innehåller all information som är relaterad till produkten och dess definition, t.ex. produktdimensioner eller spårnings- och lagringsdimensioner. Som framgår av följande tabell skapas en samling med tabellmappningar för synkronisering av produkter och relaterad information.

Appar för ekonomi och drift | Andra Dynamics 365-appar | Beskrivning
-----------------------|--------------------------------|---
[Alla produkter](mapping-reference.md#138) | msdyn_globalproducts | Tabellen för alla produkter innehåller alla produkter som är tillgängliga i appar för ekonomi och drift, både frisläppta produkter och produkter som inte frisläppts.
[CDS‑frisläppta specifika produkter](mapping-reference.md#213) | Produkt | Tabellen **Produkt** innehåller de kolumner som definierar produkten. Den omfattar enskilda produkter (produkter med undertypprodukt) och produktvarianter. Tabellen nedan visar mappningarna.
[Färger](mapping-reference.md#170) | msdyn\_productcolors
[Konfigurationer](mapping-reference.md#171) | msdyn\_productconfigurations
[Standardorderinställningar](mapping-reference.md#172) | msdyn_productdefaultordersettings |
[Produktkategorier](mapping-reference.md#166) | msdyn_productcategories | Var och en av produktkategorierna och informationen om dess struktur och egenskaper finns i tabellen produktkategori.
[Produktkategoritilldelningar](mapping-reference.md#167) | msdyn_productcategoryassignments | Så här tilldelar du en produkt till en kategori där tabellen produktkategoritilldelningar kan användas.
[Produktkategorihierarkier](mapping-reference.md#168) | msdyn_productcategoryhierarchies | Du kan använda produkthierarkier för att kategorisera eller gruppera produkter. Kategorihierarkier är tillgängliga i Dataverse använda tabellen produktkategorihierarki.
[Produktkategorihierarkiroller](mapping-reference.md#169) | msdyn_productcategoryhierarchyroles | Produkthierarkier kan användas för olika roller i D365 Ekonomi och drift. De specificerar vilken kategori som används i varje roll som tabellen produktkategori används.
[Standardorderinställningar för produkt V2](mapping-reference.md#175) | msdyn_productspecificdefaultordersettings |
[Produktdimensionsgrupper](mapping-reference.md#173) | msdyn\_productdimensiongroups | Produktdimensionsgruppen som definierar vilka produktdimensioner som definierar produkten.
[Produktmallfärger](mapping-reference.md#187) | msdyn_sharedproductcolors | Tabellen **Delad produktfärg** anger vilka färger en viss produktmall kan ha. Det här konceptet migreras till Dataverse för att hålla data konsekventa.
[Produktmallkonfigurationer](mapping-reference.md#188) | msdyn_sharedproductconfigurations | Tabellen **Delad produktkonfiguration** anger vilka konfigurationer en viss produktmall kan ha. Det här konceptet migreras till Dataverse för att hålla data konsekventa.
[Produktmallstorlekar](mapping-reference.md#190) | msdyn_sharedproductsizes | Tabellen **Delad produktstorlek** anger vilka storlekar en viss produktmall kan ha. Det här konceptet migreras till Dataverse för att hålla data konsekventa.
[Produktmallutföranden](mapping-reference.md#191) | msdyn_sharedproductstyles | Tabellen **Delad produktstil** anger vilka stilar en viss produktmall kan ha. Det här konceptet migreras till Dataverse för att hålla data konsekventa.
[Produktnummer med identifierad streckkod](mapping-reference.md#164) | msdyn\_productbarcodes | Produktstreckkoder används för att identifiera produkter på ett unikt vis.
[Produktspecifika enhetskonverteringar](mapping-reference.md#176) | msdyn_productspecificunitofmeasureconversions |
[Frisläppta produkter V2](mapping-reference.md#189) | msdyn\_sharedproductdetails | Tabellen **msdyn\_sharedproductdetails** innehåller kolumnerna från appar för ekonomi och drift som definierar produkten och som innehåller produktens ekonomi- och hanteringsinformation.
[Storlekar](mapping-reference.md#174) | msdyn\_productsizes
[Lagringsdimensionsgrupper](mapping-reference.md#177) | msdyn_productstoragedimensiongroups | Lagringsdimensionsgrupp för produkter representerar den metod som används för att definiera placeringen av produkten i lagerstället.
[Utföranden](mapping-reference.md#178) | msdyn\_productstyles
[Spårningsdimensionsgrupper](mapping-reference.md#179) | msdyn_producttrackingdimensiongroups | Spårningsdimensionsgruppen för produkt representerar den metod som används för att spåra produkten i lagret.
[Enheter](mapping-reference.md#219) | uoms
[Enhetskonverteringar](mapping-reference.md#199) | msdyn_ unitofmeasureconversions

## <a name="integration-of-products"></a>Integrering av produkter

I den här modellen representeras produkten av kombinationen av två tabeller i Dataverse: **Produkt** och **msdyn\_sharedproductdetails**. Den första tabellen innehåller definitionen av en produkt (den unika identifieraren för produkten, produktens namn och beskrivningen), den andra tabellen innehåller kolumnen som lagras på produktnivå. Kombinationen av dessa två tabeller används för att definiera produkten enligt begreppet lagerhållningsenhet (SKU). Varje frisläppt produkt får sin information i nämnda tabeller (information om produkt och delad produkt). Om du vill hålla reda på alla produkter (frisläppta och icke frisläppta) används tabellen **globala produkter**.

Eftersom produkten representeras som SKU kan begreppen distinkta produkter, produktmallar och produktvarianter fångas in i Dataverse på följande sätt:

- **Produkter med undertypsprodukter** är produkter som definieras av dem själva. Inga dimensioner behöver definieras. Ett exempel på detta är en specifik bok. För dessa produkter skapas en rad i tabellen **produkt** och en rad skapas i tabellen **msdyn\_sharedproductdetails**. Ingen produktfamiljerad skapas.
- **Produktmallar** används som allmänna produkter som innehåller definitionen och reglerna som bestämmer beteendet i affärsprocessern Baserat på dessa definitioner kan distinkta produkter som kallas produktvarianter genereras. T.ex. t-shirt är produktmall och kan ha färg och storlek som dimensioner. Varianter kan frisläppas med olika kombinationer av dessa dimensioner, t.ex. en liten blå t-shirt eller en medelstor grön t-shirt. I integreringen skapas en rad per variant i produktregistret. Den här raden innehåller den variantspecifika informationen, t.ex. de olika dimensionerna. Den allmänna informationen för produkten lagras i raden **msdyn\_sharedproductdetails**. (Denna allmänna information finns i produktmallen). Produktmallinformationen synkroniseras till Dataverse så snart den frisläppta produktmallen skapas (men innan varianter släpps).
- **Distinkta produkter** refererar till alla produkters undertypprodukt och alla produktvarianter.

![Datamodell för produkter.](media/dual-write-product.png)

Om funktionen för dubbelriktad skrivning är aktiverad kommer produkterna från Ekonomi och drift att synkroniseras i andra Dynamics 365-produkter i tillståndet **Utkast**. De läggs till i den första prislistan med samma valuta som används i kundinteraktionsappen och använder alfabetisk sortering på prislistans namn. Med andra ord läggs de till i den första prislistan i en Dynamics 365-app som matchar valutan för den juridiska tabell där produkten frisläpps i en app för ekonomi och drift. Om det inte finns någon prislista för den angivna valutan skapas en prislista automatiskt och produkten tilldelas den.

Den aktuella implementeringen av de plugin-program för dubbelriktad skrivning som kopplar standardprislistan till enheten söker efter den valuta som är kopplad till appen för ekonomi och drift, och som hittar den första prislistan i kundengagemangsappen med hjälp av alfabetisk sortering av prislistans namn. Om du vill ställa in en standardprislista för en specifik valuta när du har flera prislistor för valutan måste du uppdatera prislistans namn till ett namn som är tidigare i alfabetisk ordning än någon annan prislista för samma valuta. Om den inte har någon prislista för den angivna valutan skapas en ny.

Som standard synkroniseras produkter från appar för ekonomi och drift till andra Dynamics 365-appar i tillståndet **Utkast**. Om du vill synkronisera produkten med tillståndet **Aktiv** så att du kan använda den direkt på försäljningsorderofferter, till exempel, måste du välja följande inställning: under **System> Adminstration > Systemadministration > Systeminställningar > Försäljning**, välj **skapa produkter i aktivt tillstånd = ja**.

När produkter synkroniseras måste du ange ett värde för fältet **Försäljningsenhet** i appen för ekonomi och drift, detta det är ett obligatoriskt fält i Sales.

Skapandet av produktfamiljer från Dynamics 365 Sales stöds inte med synkronisering av dubbelriktad skrivning av produkter.

Synkroniseringen av produkter sker från appen för ekonomi och drift till Dataverse. Det innebär att värdena i tabellkolumnen för produkten kan ändras i Dataverse, men när synkroniseringen utlöses (när en produktkolumn ändras i en app för ekonomi och drift) skrivs värdena över i Dataverse.

Appar för ekonomi och drift | Kundengagemangsappar |
---|---
[CDS‑frisläppta specifika produkter](mapping-reference.md#213) | Produkt |
[Frisläppta produkter V2](mapping-reference.md#189) | msdyn_sharedproductdetails |
[Alla produkter](mapping-reference.md#138) | msdyn_globalproducts |

## <a name="product-dimensions"></a>Produktdimensioner

Produktdimensioner är egenskaper som identifierar en produktvariant. De fyra produktdimensionerna (färg, storlek, stil och konfiguration) mappas också till Dataverse för att definiera produktvarianter. Följande bild visar datamodellen för produktdimensionsfärgen. Samma modell används i storlekar, stilar och konfigurationer.

![Datamodell för produktdimensioner.](media/dual-write-product-two.png)

Appar för ekonomi och drift | Kundengagemangsappar |
---|---
[Färger](mapping-reference.md#170) | msdyn\_productcolors
[Storlekar](mapping-reference.md#174) | msdyn\_productsizes
[Utföranden](mapping-reference.md#178) | msdyn\_productstyles
[Konfigurationer](mapping-reference.md#171) | msdyn\_productconfigurations

När en produkt har olika produktdimensioner (t.ex. en produktmall har storlek och färg som produktdimensioner) definieras varje enskild produkt (dvs. varje produktvarianten) som en kombination av dessa produktdimensioner. Produktnummer B0001 är t.ex. en extra liten svart T-shirt och produktnummer B0002 är en liten svart T-shirt. I det här fallet definieras de befintliga kombinationerna av produktdimensioner. T.ex. kan t-shirten från föregående exempel vara extra small och svart, small och svart, medium och svart eller large och svart, men inte vara extra large och svarta. Med andra ord anges de produktdimensioner som en produktmall kan utföra och varianter kan frisläppas baserat på dessa värden.

Om du vill hålla reda på vilka produktdimensioner en produktmall kan utföra, skapas följande tabeller och mappas i Dataverse för varje produktdimension. Mer information finns i [Översikt över produktinformation](../../../../supply-chain/pim/product-information.md).

Appar för ekonomi och drift | Kundengagemangsappar |
---|---
[Produktmallfärger](mapping-reference.md#187) | msdyn_sharedproductcolors |
[Produktmallkonfigurationer](mapping-reference.md#188) | msdyn_sharedproductconfigurations |
[Produktmallstorlekar](mapping-reference.md#190) | msdyn_sharedproductsizes |
[Produktmallutföranden](mapping-reference.md#191) | msdyn_sharedproductstyles |
[Produktnummer med identifierad streckkod](mapping-reference.md#164) | msdyn\_productbarcodes |

## <a name="default-order-settings-and-product-specific-default-order-settings"></a>Standardorderinställningar och produktspecifika standardorderinställningar

Standardorderinställningar definierar site och lagerställe som artiklar kommer att anskaffas från eller lagras, och de minimum-, maximum-, multipla- och standardkvantiteter som ska användas för handel eller lagerhantering, ledtider, stoppflagga och orderlöftesmetod. Informationen kommer att vara tillgänglig i Dataverse med hjälp av standardorderinställningarna för orderinställningar och produktspecifika entiteter för standardorderinställningar. Mer information om funktionen finns i avsnittet [standardorderinställningar](../../../../supply-chain/production-control/default-order-settings.md).

Appar för ekonomi och drift | Kundengagemangsappar |
---|---
[Standardorderinställningar](mapping-reference.md#172) | msdyn_productdefaultordersettings |
[Standardorderinställningar för produkt V2](mapping-reference.md#175) | msdyn_productspecificdefaultordersettings |

## <a name="unit-of-measure-and-unit-of-measure-conversions"></a>Måttenheter och konverteringar av måttenheter

Måttenheterna och deras respektive konverteringar är tillgängliga i Dataverse enligt datamodellen som visas i diagrammet.

![Datamodell för måttenhet.](media/dual-write-product-three.png)

Måttenhetens koncept integreras mellan appar för ekonomi och drift och andra Dynamics 365-appar. För varje enhetsklass i en app för ekonomi och drift skapas en enhetsgrupp i en Dynamics 365-app som innehåller de enheter som tillhör enhetsklassen. En standardbasenhet skapas också för varje enhetsgrupp.

Appar för ekonomi och drift | Kundengagemangsappar |
---|---
[Produktspecifika enhetskonverteringar](mapping-reference.md#176) | msdyn_productspecificunitofmeasureconversions |
[Enheter](mapping-reference.md#219) | uoms
[Enhetskonverteringar](mapping-reference.md#199) | msdyn_ unitofmeasureconversions

## <a name="initial-synchronization-of-units-data-matching-between-finance-and-operations-and-dataverse"></a>Initial synkronisering av enhetsdata matchar mellan ekonomi och drift och Dataverse

### <a name="initial-synchronization-of-units"></a>Initial synkronisering av enheter

När dubbelriktad skrivning är aktiverad synkroniseras enheter från appar för ekonomi och drift till andra Dynamics 365-appar. Enhetsgrupperna som synkroniseras från appar för ekonomi och drift i Dataverse har en flagguppsättning som anger att de "underhålls externt".

### <a name="matching-units-and-unit-classesgroups-data-from-finance-and-operations-and-other-dynamics-365-apps"></a>Matchande enheter och enhetsklasser/gruppers data från appar för ekonomi och drift och andra Dynamics 365-appar

För det första är det viktigt att notera att integreringsnyckeln för enheten är msdyn_symbol. Därför måste värdet vara unikt i Dataverse eller andra Dynamics 365-appar. Eftersom det i andra Dynamics 365-appar är paret "Enhetsgrupp-ID" och "Namn" som definierar unikheten hos en enhet måste du ta hänsyn till olika scenarier för matchande enhetsdata mellan appar för ekonomi och drift och Dataverse.

För enhetsmatchning/överlappning i appar för ekonomi och drift och andra Dynamics 365-appar:

+ **Enheten tillhör en enhetsgrupp i andra Dynamics 365-appar som motsvarar den associerade enhetsklassen i appar för ekonomi och drift**. I det här fallet måste kolumnen msdyn_symbol i andra Dynamics 365-appar fyllas i med enhetssymbolen från appar för ekonomi och drift. Därför kommer data att matchas och enhetsgruppen ställs in som "externt underhåll" i andra Dynamics 365-appar.
+ **Enheten tillhör en enhetsgrupp i andra Dynamics 365-appar som inte motsvarar den associerade enhetsklassen i appar för ekonomi och drift (ingen befintlig enhetsklass i appar för ekonomi och drift för enhetsklassen i andra Dynamics 365-appar).** I det här fallet måste msdyn_symbol fyllas i med en slumpmässig sträng. Observera att detta värde måste vara unikt i andra Dynamics 365-appar.

För enheter och enhetsklasser i Ekonomi och drift som inte finns i andra Dynamics 365-appar:

Som en del av dubbelriktad skrivning skapas och synkroniseras enhetsgrupperna från appar för ekonomi och drift och tillhörande enheter i andra Dynamics 365-appar och Dataverse, och enhetsgruppen anges som "underhålles externt". Ingen extra initiering krävs.

För enheter i andra Dynamics 365-appar som inte existerar i appar för ekonomi och drift:

Kolumnen msdyn_symbol måste fyllas i för alla enheter. Enheterna kan alltid skapas i appar för ekonomi och drift i motsvarande enhetsklass (om sådan finns). Om enhetsklassen inte finns måste du först skapa en enhetsklass (observera att du inte kan skapa en enhetsklass i appar för ekonomi och drift utom via tillägg om du utökar uppräkningen) som matchar den andra Dynamics 365-programenhetsgruppen. Sedan kan du skapa enheten. Observera att enhetssymbolen i appar för ekonomi och drift måste vara msdyn_symbol såsom tidigare angetts i andra Dynamics 365-program för enheten.

## <a name="product-policies-dimension-tracking-and-storage-groups"></a>Produktpolicyer: dimension, spårning och lagringsgrupper

Produktpolicyer är uppsättningar med policyer som används för att definiera produkter och dess egenskaper i lagret. Produktdimensionsgrupp, dimensionsgrupp för produktspårning och lagringsdimensionsgrupp kan hittas som produktpolicyer.

Appar för ekonomi och drift | Kundengagemangsappar |
---|---
[Produktdimensionsgrupper](mapping-reference.md#173) | msdyn\_productdimensiongroups |
[Lagringsdimensionsgrupper](mapping-reference.md#177) | msdyn_productstoragedimensiongroups |
[Spårningsdimensionsgrupper](mapping-reference.md#179) | msdyn_producttrackingdimensiongroups |

## <a name="product-hierarchies"></a>Produkthierarkier

Appar för ekonomi och drift | Kundengagemangsappar |
---|---
[Produktkategoritilldelningar](mapping-reference.md#167) | msdyn_productcategoryassignments |
[Produktkategorihierarkier](mapping-reference.md#168) | msdyn_productcategoryhierarchies |
[Produktkategorihierarkiroller](mapping-reference.md#169) | msdyn_productcategoryhierarchyroles |

## <a name="integration-key-for-products"></a>Integreringsnyckel för produkter

För att unikt identifiera produkter mellan Dynamics 365 Finance och produkter i Dataverse används integreringsnycklarna.
För produkter är **(productnumber)** den unika nyckel som identifierar en produkt i Dataverse. Den består av sammanslagningen av: **(företag, msdyn_productnumber)**. **Företaget** anger den juridiska personen i Ekonomi och drift, medan **msdyn_productnumber** anger produktnumret för den specifika produkten i Ekonomi och drift.

För användare av andra Dynamics 365-appar identifieras produkten i användargränssnittet med **msdyn_productnumber** (observera att kolumnens etikett är **produktnummer**). I produktformuläret visas både företaget och msydn_productnumber. Den unika nyckeln för en kolumn visas dock inte i fältet (productNumber).

Om du skapar appar i Dataverse ska du vara uppmärksam på att använda **productnumber** (det unika produkt-ID) som integreringsnyckel. Använd inte **msdyn_productnumber**, eftersom det inte är unikt.

## <a name="initial-synchronization-of-products-and-migration-of-data-from-dataverse-to-finance-and-operations"></a>Initial synkronisering av produkter och migrering av data från Dataverse till Ekonomi och drift

### <a name="initial-synchronization-of-products"></a>Initial synkronisering av produkter

När dubbelriktad skrivning har aktiverats synkroniseras produkter från appar för ekonomi och drift till Dataverse och kundengagemangsappar. Produkter som skapats i Dataverse och andra Dynamics 365-program innan dubbelriktad skrivning fanns kommer inte att uppdateras eller matchas med produktdata från appar för ekonomi och drift.

### <a name="matching-product-data-from-finance-and-operations-and-other-dynamics-365-apps"></a>Matchande produktdata från Ekonomi och drift samt andra Dynamics 365-appar

Om samma produkter bibehålls (överlappande/matchande) i Ekonomi och drift och i Dataverse och i andra Dynamics 365-appar kommer, när du aktiverar dubbelriktad skrivning, synkroniseringen av produkter att ske från Ekonomi och drift, och dubbla rader visas i Dataverse för samma produkt.
För att undvika den tidigare situationen: Om andra Dynamics 365-appar har produkter som överlappar/matchar Ekonomi och drift, måste administratören som aktiverar dubbelriktad skrivning initiera kolumnerna **Företag** (exempel: "USMF") och **msdyn_productnumber** (exempel: "1234:Black:S") innan synkroniseringen av produkterna äger rum. Med andra ord måste dessa två kolumner i produkten i Dataverse fyllas i med respektive företag i Ekonomi och drift som produkten måste matchas mot, samt med dess produktnummer.

När synkroniseringen aktiveras och genomförs synkroniseras produkter från Ekonomi och drift med de matchade produkterna i Dataverse och andra Dynamics 365-appar. Detta gäller för både separata produkter och produktvarianter.

### <a name="migration-of-product-data-from-other-dynamics-365-apps-to-finance-and-operations"></a>Migrering av produktdata från och andra Dynamics 365-appar till Ekonomi och drift

Om andra Dynamics 365-program har produkter som inte finns i Ekonomi och drift kan administratören först använda **EcoResReleasedProductCreationV2Entity** för att importera produkterna i Ekonomi och drift. För det andra, matcha produktdata från Ekonomi och drift och andra Dynamics 365-program enligt beskrivningen ovan.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

