---
title: Enhetlig produktupplevelse
description: I det här avsnittet beskrivs integreringen av produktinformation mellan Finance and Operations-appar och Common Data Service.
author: t-benebo
manager: AnnBe
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 7de7af1084b62a7248eeda54df215e56f2541286
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/27/2020
ms.locfileid: "3173210"
---
# <a name="unified-product-experience"></a>Enhetlig produktupplevelse

[!include [banner](../../includes/banner.md)]



När ett affärsekosystem utgörs av Dynamics 365-program, t.ex. Finance, Supply Chain Management och Sales använder verksamheter ofta dessa program för att ange produktdata. Detta beror på att dessa appar ger en robust produktinfrastruktur som kompletteras med sofistikerade prissättningsbegrepp och korrekta lagerbehållningsdata. Verksamheter som använder ett externt PLM-system (Product Lifecycle Management) för inköp kan produktdata kanalisera produkter från Finance and Operations-appar till andra Dynamics 365-appar. Den enhetliga produktupplevelsen ger den integrerade produktens datamodell till Common Data Service, så att alla programanvändare inklusive Power Platform-användare kan dra nytta av de omfattande produktdata som kommer från Finance and Operations-appar.

Här är produktdatamodellen från Sales.

![Datamodell för produkter i CE](media/dual-write-product-4.jpg)

Här är produktdatamodellen från Finance and Operations-appar.

![Datamodell för produkter i Finance and Operations](media/dual-write-products-5.jpg)

Dessa två produktdatamodeller har integrerats i Common Data Service som visas nedan.

![Datamodell för produkter i Dynamics 365-appar](media/dual-write-products-6.jpg)

Dubbelriktade entitetsmappningar för produkter har utformats så att data endast kan flödas på ett sätt nästan i realtid från Finance and Operations-appar till Common Data Service. Produktinfrastrukturen har dock gjorts öppen så att den är dubbelriktad vid behov. Även om du kan anpassa den på din egen risk eftersom Microsoft inte rekommenderar det här tillvägagångssättet.

## <a name="templates"></a>Mallar

Produktinformationen innehåller all information som är relaterad till produkten och dess definition, t.ex. produktdimensioner eller spårnings- och lagringsdimensioner. Som framgår av följande tabell skapas en samling med enhetsmappningar för synkronisering av produkter och relaterad information.

Finance and Operations-appar | Andra Dynamics 365-appar | beskrivning
-----------------------|--------------------------------|---
Frisläppta produkter V2 | msdyn\_sharedproductdetails | Entiteten **msdyn\_sharedproductdetails** innehåller fälten från Finance and Operations-appar som definierar produkten och som innehåller produktens ekonomi- och hanteringsinformation. 
Common Data Service frisläppta specifika produkter | Produkt | Entiteten **Produkt** innehåller de fält som definierar produkten. Den omfattar enskilda produkter (produkter med undertypprodukt) och produktvarianter. Tabellen nedan visar mappningarna.
Produktnummer med identifierad streckkod | msdyn\_productbarcodes | Produktstreckkoder används för att identifiera produkter på ett unikt vis.
Standardorderinställningar | msdyn\_productdefaultordersettings
Produktspecifika standardorderinställningar | msdyn_productdefaultordersettings
Produktdimensionsgrupper | msdyn\_productdimensiongroups | Produktdimensionsgruppen som definierar vilka produktdimensioner som definierar produkten. 
Lagringsdimensionsgrupper | msdyn\_productstoragedimensiongroups | Lagringsdimensionsgrupp för produkter representerar den metod som används för att definiera placeringen av produkten i lagerstället.
Spårningsdimensionsgrupper | msdyn\_producttrackingdimensiongroups | Spårningsdimensionsgruppen för produkt representerar den metod som används för att spåra produkten i lagret.
Färger | msdyn\_productcolors
Storlekar | msdyn\_productsizes
Stilar | msdyn\_productsytles
Konfigurationer | msdyn\_productconfigurations
Produktmallfärger | msdyn_sharedproductcolors | Entiteten **Delad produktfärg** anger vilka färger en viss produktmall kan ha. Det här konceptet migreras till Common Data Service för att hålla data konsekventa.
Produktmallstorlekar | msdyn_sharedproductsizes | Entiteten **Delad produktstorlek** anger vilka storlekar en viss produktmall kan ha. Det här konceptet migreras till Common Data Service för att hålla data konsekventa.
Produktmallutföranden | msdyn_sharedproductstyles | Entiteten **Delad produktstil** anger vilka stilar en viss produktmall kan ha. Det här konceptet migreras till Common Data Service för att hålla data konsekventa.
Produktmallkonfigurationer | msdyn_sharedproductconfigurations | Entiteten **Delad produktkonfiguration** anger vilka konfigurationer en viss produktmall kan ha. Det här konceptet migreras till Common Data Service för att hålla data konsekventa.
Alla produkter | msdyn_globalproducts | Entiteten alla produkter innehåller alla produkter tillgängliga i Finance and Operations-appar, både frisläppta produkter och produkter som inte frisläppts.
Enhet | uoms
Enhetskonverteringar | msdyn_ unitofmeasureconversions
Produktspecifik måttenhetskonvertering | msdyn_productspecificunitofmeasureconversion
Produktkategorier | msdyn_productcategories | Var och en av produktkategorierna och informationen om dess struktur och egenskaper finns i entiteten produktkategori. 
Produktkategorihierarkier | msdyn_productcategoryhierarhies | Du kan använda produkthierarkier för att kategorisera eller gruppera produkter. Kategorihierarkier är tillgängliga i Common Data Service använda entiteten produktkategorihierarki. 
Produktkategorihierarkiroller | msdyn_productcategoryhierarchies | Produkthierarkier kan användas för olika roller i D365 Finance and Operations. De specificerar vilken kategori som används i varje roll som entiteten produktkategori används. 
Produktkategoritilldelningar | msdyn_productcategoryassignments | Så här tilldelar du en produkt till en kategori där entiteten produktkategoritilldelningar kan användas.

## <a name="integration-of-products"></a>Integrering av produkter

I den här modellen representeras produkten av kombinationen av två entiteter i Common Data Service: **Produkt** och **msdyn\_sharedproductdetails**. Den första entiteten innehåller definitionen av en produkt (den unika identifieraren för produkten, produktens namn och beskrivningen), den andra entiteten innehåller fälten som lagras på produktnivå. Kombinationen av dessa två entiteter används för att definiera produkten enligt begreppet lagerhållningsenhet (SKU). Varje frisläppt produkt får sin information i nämnda enheter (information om produkt och delad produkt). Om du vill hålla reda på alla produkter (frisläppta och icke frisläppta) används entiteten **globala produkter**. 

Eftersom produkten representeras som SKU kan begreppen distinkta produkter, produktmallar och produktvarianter fångas in i Common Data Service på följande sätt:

- **Produkter med undertypsprodukter** är produkter som definieras av dem själva. Inga dimensioner behöver definieras. Ett exempel på detta är en specifik bok. För dessa produkter skapas en post i entiteten **produkt** och en post skapas i entiteten **msdyn\_sharedproductdetails**. Ingen produktfamiljepost skapas.
- **Produktmallar** används som allmänna produkter som innehåller definitionen och reglerna som bestämmer beteendet i affärsprocessern Baserat på dessa definitioner kan distinkta produkter som kallas produktvarianter genereras. T.ex. t-shirt är produktmall och kan ha färg och storlek som dimensioner. Varianter kan frisläppas med olika kombinationer av dessa dimensioner, t.ex. en liten blå t-shirt eller en medelstor grön t-shirt. I integrationen skapas en post per variant i produktregistret. Den här posten innehåller den variantspecifika informationen, t.ex. de olika dimensionerna. Den allmänna informationen för produkten lagras i entiteten **msdyn\_sharedproductdetails**. (Denna allmänna information finns i produktmallen). Dessutom skapas en produktfamiljpost per produktmall. Produktmallinformationen synkroniseras till Common Data Service så snart den frisläppta produktmallen skapas (men innan varianter släpps).
- **Distinkta produkter** refererar till alla produkters undertypprodukt och alla produktvarianter. 

![Datamodell för produkter](media/dual-write-product.png)

Om funktionen för dubbelriktad skrivning är aktiverad kommer apparna från Finance and Operations att synkroniseras i andra Dynamics 365-appar i tillståndet **utkast**. De läggs till den första prislista med samma valuta. Med andra ord läggs de till den första prislistan i en Dynamics 365-app som matchar valutan för den juridiska person där produkten släpps i en Finance and Operations-app. 

Som standard synkroniseras produkter från Finance and Operations-appar till andra Dynamics 365-appar i tillståndet **utkast**. Om du vill synkronisera produkten med tillståndet **Aktiv** så att du kan använda den direkt på försäljningsorderofferter, till exempel, måste du välja följande inställning: under **System> Adminstration > Systemadministration > Systeminställningar > Försäljning**, välj **skapa produkter i aktivt tillstånd = ja**. 

Observera att synkroniseringen av produkter sker från Finance and Operations-appar till Common Data Service. Det innebär att värdena i fälten för produktentitet kan ändras i Common Data Service, men när synkroniseringen utlöses (när ett produktfält ändras i en Finance and Operations-appar) skrivs värdena över i Common Data Service. 

[!include [symbols](../../includes/dual-write-symbols.md)]

[!include [products](includes/EcoResReleasedDistinctProductCDSEntity-products.md)]

[!include [product details](includes/EcoResReleasedProductV2-msdyn-sharedproductdetails.md)]

[!include [global products](includes/EcoResEveryProductEntity-msdyn-globalproducts.md)]

## <a name="product-dimensions"></a>Produktdimensioner 

Produktdimensioner är egenskaper som identifierar en produktvariant. De fyra produktdimensionerna (färg, storlek, stil och konfiguration) mappas också till Common Data Service för att definiera produktvarianter. Följande bild visar datamodellen för produktdimensionsfärgen. Samma modell används i storlekar, stilar och konfigurationer. 

![Datamodell för produkter](media/dual-write-product-two.png)

[!include [product colors](includes/EcoResProductColorEntity-msdyn-productcolor.md)]

[!include [product sizes](includes/EcoResProductSizeEntity-msdyn-productsizes.md)]

[!include [product sizes](includes/EcoResProductStyleEntity-msdyn-productstyles.md)]

[!include [product sizes](includes/EcoResProductConfigurationsEntity-msdyn-productconfigurations.md)]

När en produkt har olika produktdimensioner (t.ex. en produktmall har storlek och färg som produktdimensioner) definieras varje enskild produkt (dvs. varje produktvarianten) som en kombination av dessa produktdimensioner. Produktnummer B0001 är t.ex. en extra liten svart T-shirt och produktnummer B0002 är en liten svart T-shirt. I det här fallet definieras de befintliga kombinationerna av produktdimensioner. T.ex. kan t-shirten från föregående exempel vara extra small och svart, small och svart, medium och svart eller large och svart, men inte vara extra large och svarta. Med andra ord anges de produktdimensioner som en produktmall kan utföra och varianter kan frisläppas baserat på dessa värden.

Om du vill hålla reda på vilka produktdimensioner en produktmall kan utföra, skapas följande entiteter och mappas i Common Data Service för varje produktdimension. Mer information finns i [Översikt över produktinformation](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/pim/product-information).

[!include [product colors](includes/EcoResProductMasterColorEntity-msdyn-sharedproductcolors.md)]

[!include [product sizes](includes/EcoResProductMasterSize-msdyn-sharedproductsizes.md)]

[!include [product styles](includes/EcoResProductMasterStyleEntity-msdyn-sharedproductstyles.md)]

[!include [product configurations](includes/EcoResProductMasterConfigurationEntity-msdyn-sharedproductconfigurations.md)]

[!include [product bar codes](includes/EcoResProductNumberIdentifiedBarcode-msdyn-productbarcodes.md)]

## <a name="default-order-settings-and-product-specific-default-order-settings"></a>Standardorderinställningar och produktspecifika standardorderinställningar

Standardorderinställningar definierar site och lagerställe som artiklar kommer att anskaffas från eller lagras, och de minimum-, maximum-, multipla- och standardkvantiteter som ska användas för handel eller lagerhantering, ledtider, stoppflagga och orderlöftesmetod. Informationen kommer att vara tillgänglig i Common Data Service med hjälp av standardorderinställningarna för orderinställningar och produktspecifika entiteter för standardorderinställningar. Mer information om funktionen finns i avsnittet [standardorderinställningar](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/production-control/default-order-settings).

[!include [product sizes](includes/InventProductDefaultOrderSettingsEntity-msdyn-productdefaultordersetting.md)]

[!include [product sizes](includes/InventProductSpecificOrderSettingsV2Entity-msdyn-productspecificdefaultordersetting.md)]

## <a name="unit-of-measure-and-unit-of-measure-conversions"></a>Måttenheter och konverteringar av måttenheter

Måttenheterna och deras respektive konverteringar är tillgängliga i Common Data Service enligt datamodellen som visas i diagrammet.

![Datamodell för produkter](media/dual-write-product-three.png)

Måttenhetens koncept integreras mellan Finance and Operations-appar och andra Dynamics 365-appar. För varje enhetsklass i en Finance and Operations-app skapas en enhetsgrupp i en Dynamics 365-app som innehåller de enheter som tillhör enhetsklassen. En standardbasenhet skapas också för varje enhetsgrupp. 

[!include [unit of measure](includes/UnitOfMeasureEntity-uom.md)]

[!include [unit of measure conversions](includes/UnitOfMeasureConversionEntity-msdyn-unitofmeasureconversions.md)]

[!include [product-specific unit of measure conversions](includes/EcoResProductSpecificUnitConversionEntity-msdyn-productspecificunitofmeasureconversions.md)]

## <a name="initial-synchronization-of-units-data-matching-between-finance-and-operations-and-common-data-service"></a>Initial synkronisering av enhetsdata matchar mellan Finance and Operations och Common Data Service

### <a name="initial-synchronization-of-units"></a>Initial synkronisering av enheter

När dubbelriktat är aktiverat synkroniseras enheter från Finance and Operations-appar till andra Dynamics 365-appar. Enhetsgrupperna som synkroniseras från Finance and Operations-appar i Common Data Service har en flagguppsättning som anger att de är "externt underhåll".

### <a name="matching-units-and-unit-classesgroups-data-from-finance-and-operations-and-other-dynamics-365-apps"></a>Matchande enheter och enhetsklasser/gruppers data från Finance and Operations och andra Dynamics 365-appar

För det första är det viktigt att notera att integrationsnyckeln för enheten är msdyn_symbol. Därför måste värdet vara unikt i Common Data Service eller andra Dynamics 365-appar. Eftersom i andra Dynamics 365-appar är det paret "enhetsgrupp-ID" och "namn" som definierar unikheten av en enhet, men du måste ta hänsyn till olika scenarier för matchande enhetsdata mellan Finance and Operations-appar och Common Data Service.

För enhetsmatchning/överlappning i Finance and Operations-appar och andra Dynamics 365-appar:

+ **Enheten tillhör en enhetsgrupp i andra Dynamics 365-appar som motsvarar den associerade enhetsklassen i Finance and Operations-appar**. I det här fallet måste fältet msdyn_symbol i andra Dynamics 365-appar fyllas i med enhetssymbolen från Finance and Operations-appar. Därför kommer data att matchas och enhetsgruppen ställs in som "externt underhåll" i andra Dynamics 365-appar.
+ **Enheten tillhör en enhetsgrupp i andra Dynamics 365-appar som inte motsvarar den associerade enhetsklassen i Finance and Operations-appar (ingen befintlig enhetsklass i Finance and Operations-appar för enhetsklassen i andra Dynamics 365-appar).** I det här fallet måste msdyn_symbol fyllas i med en slumpmässig sträng. Observera att detta värde måste vara unikt i andra Dynamics 365-appar.

För enheter och enhetsklasser i Finance and Operations-appar som inte finns i andra Dynamics 365-appar:

Som en del av dubbelriktad skapas och synkroniseras enhetsgrupperna från Finance and Operations-appar och de tillhörande enheterna i andra Dynamics 365-appar och Common Data Service och enhetsgruppen anges som "externt underhåll". Ingen extra initiering krävs.

För enheter i andra Dynamics 365-appar som inte existerar i Finance and Operations-appar:

Fältet msdyn_symbol måste fyllas i för alla enheter. Enheterna kan alltid skapas i Finance and Operations-appar i motsvarande enhetsklass (om det finns). Om enhetsklassen inte finns måste du först skapa en enhetsklass (observera att du inte kan skapa en enhetsklass i Finance and Operations-appar utom via tillägg om du utökar uppräkningen) som matchar den andra Dynamics 365-appenhetsgruppen. Sedan kan du skapa enheten. Observera att enhetssymbolen i Finance and Operations-appar måste vara msdyn_symbol som tidigare anges i andra Dynamics 365-appar för enheten.

## <a name="product-policies-dimension-tracking-and-storage-groups"></a>Produktpolicyer: dimension, spårning och lagringsgrupper

Produktpolicyer är uppsättningar med policyer som används för att definiera produkter och dess egenskaper i lagret. Produktdimensionsgrupp, dimensionsgrupp för produktspårning och lagringsdimensionsgrupp kan hittas som produktpolicyer. 

[!include [product dimension group](includes/EcoResProductDimensionGroup-msdyn-productdimensiongroups.md)]

[!include [product tracking dimension group](includes/EcoResTrackingDimensionGroup-msdyn-producttrackingdimensiongroups.md)]

[!include [product storage dimension group](includes/EcoResStorageDimensionGroup-msdyn-productstoragedimensiongroups.md)]

## <a name="product-hierarchies"></a>Produkthierarkier

[!include [product category hierarchy](includes/EcoResProductCategoryHierarchyEntity-msdyn-productcategoryhierarchy.md)]

[!include [product category](includes/EcoResProductCategoryEntity-msdyn-productcategory.md)]

[!include [product category assignments](includes/EcoResProductCategoryAssignmentEntity-msdyn-productcategoryassignment.md)]

[!include [product category role](includes/EcoResProductCategoryHierarchyRoleEntity-msdyn-productcategoryhierarchyrole.md)]


## <a name="integration-key-for-products"></a>Integrationsnyckel för produkter 

För att unikt identifiera produkter mellan Dynamics 365 for Finance and Operations och produkter i Common Data Service används integrationsnycklarna. För produkter är **(productnumber)** den unika nyckel som identifierar en produkt i Common Data Service. Den består av sammanfogningen av: **(företag, msdyn_productnumber)**. **Företaget** anger den juridiska personen i Finance and Operations och **msdyn_productnumber** anger produktnumret för den specifika produkten i Finance and Operations. 

För användare av andra Dynamics 365-appar identifieras produkten i användargränssnittet med **msdyn_productnumber** (observera att fältets etikett är **produktnummer**). I produktformuläret visas både företaget och msydn_productnumber. Den unika nyckeln för en produkt visas dock inte i fältet (productNumber). 

Om du skapar appar i Common Data Service ska du vara uppmärksam på att använda **productnumber** (det unika produkt-ID) som integrationsnyckel. Använd inte **msdyn_productnumber**, eftersom det inte är unikt. 

## <a name="initial-synchronization-of-products-and-migration-of-data-from-common-data-service-to-finance-and-operations"></a>Initial synkronisering av produkter och migrering av data från Common Data Service till Finance and Operations

### <a name="initial-synchronization-of-products"></a>Initial synkronisering av produkter 

När dubbelriktat är aktiverat synkroniseras produkter från Finance and Operations-appar till Common Data Service och andra modellstyrda appar i Dynamics 365. Produkter som skapats i Common Data Service och andra Dynamics 365-appar före dubbelriktning frisläpptes kommer inte att uppdateras eller matchas med produktdata från Finance and Operations.

### <a name="matching-product-data-from-finance-and-operations-and-other-dynamics-365-apps"></a>Matchande produktdata från Finance and Operations och andra Dynamics 365-appar

Om samma produkter hålls (överlappande/matchande) i Finance and Operations och i Common Data Service och i andra Dynamics 365-appar, när du aktiverar dubbelriktning sker synkroniseringen av produkter från Finance and Operations och dubbla poster visas i Common Data Service för samma produkt.
För att undvika den tidigare situationen, om andra Dynamics 365-appar har produkter som överlappar/matchar med Finance and Operations, måste administratören som aktiverar dubbelriktning initiera fälten **företag** (exempel: "USMF") och **msdyn_productnumber** (exempel: "1234:Black:S") innan synkroniseringen av produkterna äger rum. Med andra ord måste dessa två fält i produkten i Common Data Service fyllas i med respektive företag Finance and Operations som produkten måste matchas mot och med dess produktnummer. 

När synkroniseringen aktiveras och genomförs synkroniseras produkter från Finance and Operations med de matchade produkterna i Common Data Service och andra Dynamics 365-appar. Detta gäller för både separata produkter och produktvarianter. 


### <a name="migration-of-product-data-from-other-dynamics-365-apps-to-finance-and-operations"></a>Migrering av produktdata från och andra Dynamics 365-appar till Finance and Operations

Om andra Dynamics 365-appar har produkter som inte finns i Finance and Operations Operations, kan administratören först använda **EcoResReleasedProductCreationV2Entity** för att importera produkterna i Finance and Operations. För det andra, matcha produktdata från Finance and Operations och andra Dynamics 365-appar enligt beskrivningen ovan. 