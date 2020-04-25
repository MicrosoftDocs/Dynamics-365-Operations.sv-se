---
title: Entitetsberoende kedja (synkroniseringsordning)
description: Det här avsnittet anger ordningen för synkroniseringen som du måste följa för att skapa de ursprungliga data.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/25/2019
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
ms.openlocfilehash: 4adb2c8d57ad8f67346b8d34212b7a4b0bd052ab
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/27/2020
ms.locfileid: "3173141"
---
# <a name="entity-dependency-chain-synchronization-order"></a>Entitetsberoende kedja (synkroniseringsordning)

[!include [banner](../../includes/banner.md)]



I följande tabeller listas entiteter i den ordning som du bör aktivera dem i. När du aktiverar en mappning för inledande synkronisering identifieras dubbelriktad skrivning automatiskt andra mappningar som måste aktiveras. Du kan använda sidan **dubbelriktad skrivning** i Finance and Operations-appar för att välja eller annullera urvalet av entiteter under den ursprungliga synkroniseringen.

I den senaste versionen av dubbelriktad skrivning kan du bara aktivera vissa entiteter och beroenden hanteras åt dig.

## <a name="dynamics-365-supply-chain-management-entities"></a>Dynamics 365 Supply Chain Management-entiteter

Följande entiteter för Supply Chain Management listas i den ordning som du bör aktivera dem i.

| Mappningsnamn på sidan dubbelriktad skrivning | Entitetens metadatanamn i Supply Chain Management | Entitetens metadatanamn i Common Data Service | Anteckningar |
|---|---|---|---|
| Enheter ... uoms                                                                      | UnitOfMeasureEntity                                    | enhet                                          | |
| Enhetskonverteringar ... msdyn_unitofmeasureconversions                                 | UnitOfMeasureConversionEntity                          | msdyn_unitofmeasureconversion                | |
| Alla produkter ... msdyn_globalproducts                                               | EcoResEveryProductEntity                               | msdyn_globalproduct                          | |
| Produktdimensionsgrupper ... msdyn_productdimensiongroups                           | EcoResProductDimensionGroupEntity                      | msdyn_productdimensiongroup                  | |
| Lagringsdimensionsgrupper ... msdyn_productstoragedimensiongroups                    | EcoResStorageDimensionGroupEntity                      | msdyn_productstoragedimensiongroup           | |
| Spårningsdimensionsgrupper ... msdyn_producttrackingdimensiongroups                  | EcoResTrackingDimensionGroupEntity                     | msdyn_producttrackingdimensiongroup          | |
| Färger ... msdyn_productcolors                                                      | EcoResProductColorEntity                               | msdyn_productcolor                           | |
| Storlekar ... msdyn_productsizes                                                        | EcoResProductSizeEntity                                | msdyn_productsize                            | |
| Formatmallar ... msdyn_productstyles                                                      | EcoResProductStyleEntity                               | msdyn_productstyle                           | |
| Konfigurationer ... msdyn_productconfigurations                                      | EcoResProductConfigurationEntity                       | msdyn_productconfiguration                   | |
| Frisläppta produkter V2 ... msdyn_sharedproductdetails                                 | EcoResReleasedProductV2Entity                          | msdyn_sharedproductdetail                    | |
| Common Data Service-frisläppta specifika produkter ... produkter                         | EcoResReleasedDistinctProductCommon Data Service-enhet | produkt                                      | |
| Produktnummeridentifierad streckkod ... msdyn_productbarcodes                         | EcoResProductNumberIdentifiedBarcodeEntity             | msdyn_productbarcode                         | |
| Standardorderinställningar ... msdyn_productspecificdefaultordersettings                        | InventProductDefaultOrderSettingsEntity                | msdyn_productdefaultordersetting             | |
| Standardorderinställningar för produkt v2 ... msdyn_productspecificdefaultordersettings     | InventProductSpecificOrderSettingsV2Entity             | msdyn_productspecificdefaultordersetting     | |
| Produktspecifika enhetskonverteringar ... msdyn_productspecificunitofmeasureconversions | EcoResProductSpecificUnitConversionEntity              | msdyn_productspecificunitofmeasureconversion | |
| Webbplatser ... msdyn_operationalsites                                                    | InventOperationalSiteEntity                            | msdyn_operationalsite                        | |
| Lagerställen ... msdyn_warehouses                                                     | InventWarehouseEntity                                  | msdyn_warehouse                              | Se [notering 1](#scm-notes). |
| Färg på produktmall ... msdyn_sharedproductcolors                                 | EcoResProductMasterColorEntity                         | msdyn_sharedproductcolor                     | |
| Storlekar på produktmall ... msdyn_sharedproductsizes                                   | EcoResProductMasterSizeEntity                          | msdyn_sharedproductsize                      | |
| Formatmallar för produktmall ... msdyn_sharedproductstyles                                 | EcoResProductMasterStyleEntity                         | msdyn_sharedproductstyle                     | |
| Konfiguration av produktmall ... msdyn_sharedproductconfigurations                 | EcoResProductMasterConfigurationEntity                 | msdyn_sharedproductconfiguration             | |
| Produktkategorier ... msdyn_productcategories                                      | EcoResProductCategoryEntity                            | msdyn_productcategory                        | Se [notering 2](#scm-notes). |
| Produktkategoritilldelningar ... msdyn_productcategoryassignments                   | EcoResProductCategoryAssignmentEntity                  | msdyn_productcategoryassignment              | |
| Produktkategorihierarkier ... msdyn_productcategoryhierarchies                   | EcoResProductCategoryHierarchyEntity                   | msdyn_productcategoryhierarchy               | |
| Roller för produktkategorihierarki ... msdyn_productcategoryhierarchyroles            | EcoResProductCategoryHierarchyRoleEntity               | msdyn_productcategoryhierarchyrole           | |
| Lagergång ... msdyn_warehouseaisles                                           | WMSWarehouseAisleEntity                                | msdyn_warehouseaisle                         | |
| Lagerzoner ... msdyn_warehousezones                                            | WHSWarehouseZoneEntity                                 | msdyn_warehousezone                          | |
| Lagerzongrupper ... msdyn_warehousezonegroups                                 | WHSWarehouseZoneGroupEntity                            | msdyn_warehousezonegroup                     | |
| Lagerställen ... msdyn_inventorylocations                                    | WMSWarehouseLocationEntity                             | msdyn_inventorylocation                      | Se [notering 3](#scm-notes). |
| Rubriker för lagerarbete ... msdyn_warehouseworkheaders                               | WHSWarehouseWorkHeaderEntity                           | msdyn_warehouseworkheader                    | |
| Racer för lagerarbete ... msdyn_warehouseworklines                                    | WHSWarehouseWorkLineEntity                             | msdyn_warehouseworklines                     | Se [notering 4](#scm-notes). |
| Leveranssätt ... msdyn_shipvias                                                | DlvDeliveryModeEntity                                  | msdyn_shipvias                               | |
| Leveransvillkor ... msdyn_termsofdeliveries                                       | DeliveryTermsEntity                                    | msdyn_termsofdelivery                        | |
| Koder för försäljningsorderursprung ... msdyn_salesorderorigins                                | SalesOrderOriginEntity                                 | msdyn_salesorderorigin                       | |
| Common Data Service försäljningsorderrubriker ... salesorders                             | SalesOrderHeaderCommon Data Service-enhet              | salesorder                                   | |
| Common Data Service försäljningsorderrader ... salesorderdetails                         | SalesOrderLineCommon Data Service-enhet                | salesorderdetails                            | |
| Common Data Service försäljningsofferrubrik ... offerter                               | SalesQuotationHeaderCommon Data Service-enhet          | offert                                        | |
| Common Data Service försäljningsoffertrader ... quotedetails                          | SalesQuotationLineCommon Data Service-enhet            | QuoteDetails                                 | |
| Försäljningsfakturahuvuden V2 ... invoices                                               | SalesInvoiceHeaderV2Entity                             | faktura                                      | |
| Försäljningsfakturarader V2 ... invoicedetails                                           | SalesInvoiceLineV2Entity                               | invoicedetail                                | |

### <a name="mapping-specific-notes"></a><a id='scm-notes'></a>Mappning – specifika anteckningar

1. På grund av ett självberoende måste du kanske köra den ursprungliga synkroniseringen två gånger.
2. Som standard är den inledande synkroniseringen inaktiverad eftersom relationen mellan över- och underordnade relationer ("smart"-relationen inte hanteras av plattformen). Därför måste de befintliga produktkategorierna synkroniseras manuellt (t.ex. genom att uppdatera beskrivningen av kategorin) i rätt ordning (rotkategori först, sedan underordnade och sedan underordnade underordnade). Gå till **Produktinformationshantering \> Inställningar \> Kategorier och attribut \> Kategorihierarkier**. På sidan **kategorihierarkier** kan du välja varje hierarki och visa produktkategorierna i den.
3. Mappningen av tomma **ItemNumberInLocation** uppslagsfält och de första, andra och tredje lagerzonerna gör att den ursprungliga synkroniseringen misslyckas. Dessa mappningar tas därför bort för tillfället.
4. Mappningen av det tomma **CaptureWeight**-fältet leder till att den ursprungliga synkroniseringen misslyckas. Dessa mappningar tas därför bort för tillfället.

### <a name="setup-related-information"></a>Inställningsrelaterad information

+ När poster skapas för första gången i entiteten **produkter** i modellstyrda appar i Dynamics 365, har de status **utkast**. Om du vill ändra status till **aktiv**, gå till **Inställningar \> Administration \> Systeminställningar \> Försäljning** i den modellstyrda appen och ange alternativet **skapa produkter i aktivt läge** till **ja**.
+ Om du skapar poster i enheten **produkter** i modellstyrda appar i Dynamics 365 eller i Common Data Service innan du aktiverar dubbelriktad skrivning kommer dessa poster endast att uppdateras om hela nyckeln, inklusive **företag**, matchar data i Finance and Operations-appen.
+ Synkronisering av enheten **produkter** är enkelriktat från Finance and Operations-appar till Common Data Service. Om ett mappat fält i enheten **produkter** i modellstyrda appar i Dynamics 365 uppdateras, kommer uppdateringen att skrivas över vid nästa synkronisering från Finance and Operations-appen.

### <a name="known-issues"></a>Kända problem

- Ett fel uppstår när en enhet tas bort i en Finance and Operations-app. När måttenheter synkroniseras från Finance and Operations-appen till Common Data Service kommer den första enheten i en viss klass att skapas som den primära enheten och den kommer inte att tas bort.

    **Minskning:** ta först bort enheten i Common Data Service. Den kan sedan tas bort i Finance and Operations-appen.

- Ett fel uppstår när en driftsplats tas bort i Common Data Service. Felmeddelandets tillstånd, "Informationslogg: Varning: den primära adressen kan inte tas bort. Varning: det gick inte att ta bort entitetsposten eftersom valideringen misslyckades för följande datakälla: InventSiteLogisticsLocation (InventSiteLogisticsLocation)." Det här felet orsakas av ett problem i datatabellen i Finance and Operations-appen.

    **Minskning:** du kan ta bort webbplatsen i Finance and Operations-appen. Webbplatsen kommer sedan att tas bort i Common Data Service om motsvarande karta för dubbelriktad skrivning körs.

## <a name="dynamics-365-finance-entities"></a>Dynamics 365 Finance-entiteter

Följande entiteter för Dynamics 365 Finance listas i den ordning som du bör aktivera dem i.

| Mappningsnamn på sidan dubbelriktad skrivning | Entitetens metadatanamn i Finance | Entitetens metadatanamn i Common Data Service | Anteckningar |
|---|---|---|---|
| Valutor ... transactioncurrencies                                            | CurrencyEntity                              | Valuta                                   | |
| Valutakurstyp ... msdyn_exchangeratetypes                                  | ExchangeRateTypeEntity                      | msdyn_exchangeratetype                     | |
| Valutapar för valutakurs ... msdyn_currencyexchangeratepairs                 | ExchangeRateCurrencyPairEntity              | msdyn_currencyexchangeratepair             | |
| Common Data Service valutakurser ... msdyn_currencyexchangerates              | ExchangeRateCommon Data Service-enhet       | msdyn_currencyexchangerate                 | Se [notering 1](#fin-notes). |
| Integreringsenhet för räkenskapskalender ... msdyn_fiscalcalendaryears                    | FiscalCalendarEntity                        | msdyn_fiscalcalendar                       | |
| Räkenskapskalenders årsintegreringsenhet ... msdyn_fiscalcalendaryears           | FiscalCalendarYearEntity                    | msdyn_fiscalcalendaryear                   | |
| Räkenskapskalenderperiod ... msdyn_fiscalcalendarperiods                          | FiscalPeriodEntity                          | msdyn_fiscalcalendarperiod                 | |
| Organisationshierarkityp ... msdyn_internalorganizationhierarchytypes        | OMOrganizationHierarchyTypeEntity           | msdyn_internalorganizationhierarchytype    | Se [notering 1](#fin-notes). |
| Organisationshierarkisyften ... msdyn_internalorganizationhierarchypurposes | OMOrganizationHierarchyPurposeEntity        | msdyn_internalorganizationhierarchypurpose | Se [notering 1](#fin-notes). |
| Juridiska personer ... msdyn_internalorganizations                                  | OMLegalEntity                               | msdyn_internalorganization                 | Se [notering 1](#fin-notes). |
| Juridiska personer ... cdm_companies                                                | OMLegalEntity                               | cdm_company                                | |
| Driftenhet ... msdyn_internalorganizations                                  | OMOperatingUnitEntity                       | msdyn_internalorganization                 | Se [notering 1](#fin-notes). |
| Organisationshierarki – publicerad ... msdyn_internalorganizationhierarchies    | OMOrganizationHierarchyPublishedEntity      | msdyn_internalorganizationhierarchy        | Se [notering 1](#fin-notes). |
| Namnaffix ... msdyn_nameaffixes                                              | DirNameAffixEntity                          | msdyn_nameaffix                            | |
| Betalningsdagar Common Data Service ... msdyn_paymentdays                          | PaymentDayCommon Data Service-enhet         | msdyn_paymentday                           | |
| Betalningsdagsrader Common Data Service V2 ... msdyn_paymentdaylines              | PaymentDayLineCommon Data ServiceV2Entity   | msdyn_paymentdayline                       | |
| Betalningsplan ... msdyn_paymentschedules                                     | PaymentScheduleEntity                       | msdyn_paymentschedule                      | |
| Betalningsplanrader ... msdyn_paymentschedulelines                           | PaymentScheduleLineEntity                   | msdyn_paymentscheduleline                  | |
| Betalningsvillkor ... msdyn_paymentterms                                         | PaymentTermEntity                           | msdyn_paymentterm                          | |
| Kundbetalningsmetod ... msdyn_customerpaymentmethods                        | CustomerPaymentMethodEntity                 | msdyn_customerpaymentmethod                | |
| Leverantörsbetalningsmetod ... msdyn_vendorpaymentmethods                            | VendorPaymentMethodEntity                   | msdyn_vendorpaymentmethod                  | |
| Kundgrupper ... msdyn_customergroups                                        | CustCustomerGroupEntity                     | msdyn_customergroup                        | |
| Leverantörsgrupper ... msdyn_vendorgroups                                            | VendVendorGroupEntity                       | msdyn_vendorgroup                          | |
| Momsgrupper ... msdyn_taxgroups                                            | TaxGroupEntity                              | msdyn_taxgroup                             | |
| Artikelmomsgrupper ... msdyn_taxitemgroups                                   | TaxItemGroupEntity                          | msdyn_taxitemgroup                         | |
| Bokföringsgrupper för momsredovisning V2 ... msdyn_taxpostinggroups                   | TaxPostingGroupEntityV2                     | msdyn_taxpostinggroup                      | |
| Momsbefrielsekods enhets-Common Data Service ... msdyn_taxexemptcodes       | TaxExemptCodeCommon Data Service-enhet      | msdyn_taxexemptcode                        | |
| Skattemyndigheter ... msdyn_taxauthorities                                  | TaxAuthorityEntity                          | msdyn_taxauthority                         | |
| Momskod ... msdyn_taxcodes                                               | TaxCodeEntity                               | msdyn_taxcode                              | Se [notering 1](#fin-notes). |
| Format på ekonomiska dimensioner ... msdyn_financialdimensionformats                  | DimensionIntegrationFormatEntity            | msdyn_financialdimensionformat             | |
| Ekonomiska dimensioner ... msdyn_dimensionattributes                              | DimensionAttributeEntity                    | msdyn_dimensionattribute                   | |
| Källskattegrupper ... msdyn_withholdingtaxgroups                           | TaxWithholdingGroupEntity                   | msdyn_withholdingtaxgroup                  | |
| Källskattekoder ... msdyn_withholdingtaxcodes                             | TaxWithholdingTaxCodes                      | msdyn_withholdingtaxcode                   | |
| Kontoplaner ... msdyn_chartofaccountses                                   | LedgerChartOfAccountsEntity                 | msdyn_chartofaccounts                      | |
| Redovisning ... msdyn_ledgers                                                        | LedgerEntity                                | msdyn_ledger                               | Se [notering 1](#fin-notes). |
| Huvudkontokategorier ... msdyn_mainaccountcategories                         | MainAccountCategoryEntity                   | msdyn_mainaccountcategory                  | |
| Huvudkonto ... msdyn_mainaccounts                                             | MainAccountEntity                           | msdyn_mainaccount                          | |
| Kunder V3 ... konton                                                       | CustCustomerV3Entity                        | konto                                    | Se [notering 2](#fin-notes). |
| Kunder V3 ... kontakter                                                       | CustCustomerV3Entity                        | kontakta                                    | Se [notering 3](#fin-notes). |
| Leverantörer V2 ... msdyn_vendors                                                    | VendVendorV2Entity                          | msdyn_vendor                               | Se [notering 2](#fin-notes). |
| Common Data Service-kontakter V2 ... kontakter                                    | smmContactPersonCommon Data ServiceV2Entity | kontakta                                    | Se [notering 4](#fin-notes). |
| Common Data Service-kontakter V2 ... kontakter                                    | smmContactPersonCommon Data ServiceV2Entity | kontakta                                    | Se [notering 5](#fin-notes). |

### <a name="mapping-specific-notes"></a><a id='fin-notes'></a>Mappning – specifika anteckningar

1. Enkelriktad synkronisering sker från Finance and Operations-appar till Common Data Service.
2. På grund av ett självberoende måste du kanske köra den ursprungliga synkroniseringen mer än en gång. Se till att välja **kund** som relations typ när du skapar ett konto med hjälp av sidan **konton** i Common Data Service. Om det uppstår problem med fältet **primär kontakt** under den första synkroniseringen tar du bort fältet från mappningen och kör sedan den ursprungliga synkroniseringen igen. När den första synkroniseringen har slutförts stoppar du mappningen och lägger till fältet **primär kontakt** igen. Därefter startar du mappningen, men hoppar över den första synkroniseringen. Värdet i fältet **primär kontakt** tas inte med i den ursprungliga synkroniseringen, och du måste flytta värdena manuellt.
3. Se till att ställa in alternativet **säljbar** till **ja** på sidan **kontakter** i Common Data Service när du försöker skapa en kund av typen **person**.
4. Denna mappning har ett filter på båda sidorna för att koppla kundkontakter. Öppna mappningsinformationen, välj filterknappen (trattsymbol) bredvid entitetsnamnet **Sales.Contact** och se till att filkriterierna innehåller **msdyn_contactforvendor eq true och msdyn_sellable eq false**.
5. Denna mappning har ett filter på båda sidorna för att koppla leverantörskontakter. Öppna mappningsinformationen, välj filterknappen (trattsymbol) bredvid entitetsnamnet **Sales.Contact** och se till att filterkriterierna innehåller **msdyn_contactforvendor eq true och msdyn_sellable eq false**. 

## <a name="dynamics-365-human-resources-entities"></a>Dynamics 365 Human Resources-entiteter

Följande entiteter för Dynamics 365 Human Resources listas i den ordning som du bör aktivera dem i.

| Mappningsnamn på sidan dubbelriktad skrivning | Entitetens metadatanamn i personal | Entitetens metadatanamn i Common Data Service | Anteckningar |
|---|---|---|---|
| cdm_jobfunction - Jobbfunktion                                |                                   | cdm_jobfunction                  | |
| cdm_jobtypes - Jobbtyper                                      |                                   | cdm_jobtypes                     | |
| cdm_jobs - Jobb                                               |                                   | cdm_jobs                         | |
| cdm_jobs - Jobbinformation                                        |                                   | cdm_jobs                         | |
| cdm_positiontype - PositionType                               | HcmPositionTypeEntity             | cdm_positiontype                 | |
| cdm_jobpositions - grundläggande befattning                              | HcmPositionBaseEntity             | cdm_jobposition                  | Se [notering 1](#hr-notes). |
| cdm_jobposition - befattningsdetaljer                            | HcmPositionDetailEntity           | cdm_jobposition                  | Se [notering 1](#hr-notes). |
| cdm_jobposition - befattningens varaktighet                           | HcmPositionDurationEntity         | cdm_jobposition                  | Se [notering 1](#hr-notes). |
| cdm_jobposition - befattningshierarkier                        | HcmPositionHierarchyEntity        | cdm_jobposition                  | Se [notering 1](#hr-notes). |
| cdm_veteranstatus - Veteranstatus                            |                                   | cdm_veteranstatus                | |
| cdm_ethnicorigin - etniskt ursprung                              |                                   | cdm_ethnicorigin                 | |
| cdm_languagecode - språkkod                              |                                   | cdm_languagecode                 | |
| cdm_worker - arbetare                                           | HcmWorkerEntity                   | cdm_worker                       | |
| cdm_employments - anställningar                                 |                                   | cdm_employments                  | |
| cdm_employments - anställningsdetalj                           |                                   | cdm_employments                  | |
| cdm_positionworkerassignmentmaps - Befattningstilldelningar för arbetare | HcmPositionWorkerAssignmentEntity | cdm_positionworkerassignmentmaps | Se [notering 2](#hr-notes).|

### <a name="mapping-specific-notes"></a><a id='hr-notes'></a>Mappning – specifika anteckningar

1. En Common Data Service-enhet mappas till flera Finance and Operations-appentiteter.
2. Den här mappningen har en självreferens.

## <a name="asset-management-entities"></a>Entiteter för tillgångshantering

Följande entiteter för tillgångshantering för Dynamics 365 Supply Chain Management listas i den ordning som du bör aktivera dem i.

| Mappningsnamn på sidan dubbelriktad skrivning | Entitetens metadatanamn i tillgångshantering | Entitetens metadatanamn i Common Data Service | Anteckningar |
|---|---|---|---|
| FO.AssetManagementAssetLifecycleStates--Common Data Service.msdyn_assetlifecyclestates                           | Tillgångshantering för livscykeltillstånd av tillgångar               | msdyn_assetlifecyclestates               | |
| FO.AssetManagementAssetLifecycleModels--Common Data Service.msdyn_assetlifecyclemodels                           | Tillgångshantering för livscykelmodeller av tillgångar               | msdyn_assetlifecyclemodels               | |
| FO.AssetManagementFunctionalLocationLifecycleModels--Common Data Service.msdyn_functionallocationlifecyclemodels | Livscykelmodeller för funktionsplatsens tillgångshantering | msdyn_functionallocationlifecyclemodels  | |
| FO.AssetManagementFunctionalLocationLifecycleStates--Common Data Service.msdyn_functionallocationlifecyclestates | Livscykeltillstånd för funktionsplatsens tillgångshantering | msdyn_functionallocationlifecyclestates  | |
| FO.AssetManagementAssetTypes--Common Data Service.msdyn_customerassetcategories                                  | Tillgångstyper för hantering av tillgångar                          | msdyn_customerassetcategories            | |
| FO.AssetManagementFunctionalLocationTypes--Common Data Service.msdyn_functionallocationtypes                     | Funktionsplatstyper för tillgångshantering            | msdyn_functionallocationtypes            | |
| FO.AssetManagementFunctionalLocations--Common Data Service.msdyn_functionallocations                             | Funktionsplatser för tillgångshantering                 | msdyn_functionallocations                | Se [noteringen](#am-notes). |
| FO.AssetManagementAssets--Common Data Service.msdyn_customerassets                                               | Tillgångar för hantering av tillgångar                               | msdyn_customerassets                     | Se [noteringen](#am-notes). |
| FO.AssetManagementManufacturers--Common Data Service.msdyn_manufacturers                                         | Tillverkare för tillgångshantering                        | msdyn_manufacturers                      | |
| FO.AssetManagementModels--Common Data Service.msdyn_models                                                       | Tillgångshanteringsmodeller                               | msdyn_models                             | |
| FO.AssetManagementWarranty--Common Data Service.msdyn_warranties                                                 | Garanti över tillgångshantering                             | msdyn_warranties                         | |

### <a name="mapping-specific-notes"></a><a id='am-notes'></a>Mappning – specifika anteckningar

- På grund av ett självberoende måste du kanske köra den ursprungliga synkroniseringen mer än en gång.
