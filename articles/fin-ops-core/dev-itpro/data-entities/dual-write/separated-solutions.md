---
title: Separat dubbelriktad skrivning programorkestrering-paket
description: Paketet för programorkestrering är inte längre ett enda paket utan har separerats i mindre paket. I den här artikeln beskrivs lösningar och kartor som varje paket innehåller, samt dess beroende av andra paket.
author: RamaKrishnamoorthy
ms.date: 04/25/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: separate-solution
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-11-29
ms.openlocfilehash: 504939f1f98c18005c092cabc1d040b420402c93
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8874824"
---
# <a name="separated-dual-write-application-orchestration-package"></a>Separat dubbelriktad skrivning programorkestrering-paket

[!include [banner](../../includes/banner.md)]



Tidigare var dubbelriktad skrivning programorkestrering-paketet ett enda paket som innehöll följande lösningar:

- Dynamics 365 Anteckningar
- Dynamics 365 Ekonomi och drift Gemensamt ankare
- Dynamics 365 Ekonomi och drift entitetsmappningar för dubbelriktade appar
- Dynamics 365 tillgångshanteringsapp
- Dynamics 365 tillgångshantering
- Gemensamt för HCM
- Dynamics 365 Supply Chain utökad
- Dynamics 365 Finance Extended
- Dynamics 365 Ekonomi och drift gemensamt
- Dynamics 365 företag
- Valutakurser
- Field Service Common

Eftersom det var ett enskilt paket skapade det här paketet en situation för kunder "allt eller inget". Microsoft har nu separerat den till mindre paket. Därför kan kunder bara välja paket för de lösningar de behöver. Om du till exempel är en Microsoft Dynamics 365 Supply Chain Management kund och du inte kräver integrering med Dynamics 365 Human Resources, anteckningar och tillgångshantering kan du utesluta dessa lösningar från lösningarna som är installerade. Eftersom de underliggande lösningsnamnen, och mappningsversionerna förblir desamma, bryts inte ändringen. Befintliga installationer kan uppgraderas.

![Separerat paket.](media/separated-package-1.png)

I den här artikeln beskrivs lösningar och kartor som varje paket innehåller, samt dess beroende av andra paket.

## <a name="dual-write-application-core"></a>Appkärna med dubbla skrivningar

Paketet med applikationskärna med dubbelriktad skrivning låter användare installera och konfigurera dubbelriktad skrivning utan någon app för kundengagemang. Den innehåller följande fem lösningar.

| Unikt namn                           | Visa namn                               |
|---------------------------------------|--------------------------------------------|
| Dynamics365Company                    | Dynamics 365 företag                       |
| Dynamics365FinanceAndOperationsCommon | Dynamics 365 Ekonomi och drift gemensamt |
| CurrencyExchangeRates                 | Valutakurser                    |
| msdyn_DualWriteAppCoreMaps            | Entitetsmappningar för dubbelriktade appar   |
| msdyn_DualWriteAppCoreAnchor          | Appkärna ankare med dubbla skrivningar        |

Följande kartor finns i detta paket.

| Ekonomi och drift-appar     | Kundengagemangsappar                    |
|---------------------------------|---------------------------------------------|
| Driftenhet                  | msdyn_internalorganizations                 |
| Organisationshierarki          | msdyn_internalorganizationhierarchies       |
| Juridiska personer                  | msdyn_internalorganizations                 |
| Juridiska personer                  | cdm_companies                               |
| Syften för organisationshierarki | msdyn_internalorganizationhierarchypurposes |
| Valutapar för valutakurs     | msdyn_currencyexchangeratepairs             |
| Namnaffix                    | msdyn_nameaffixes                           |
| Valutakurstyp              | msdyn_exchangeratetypes                     |
| Valutakurser för CDS              | msdyn_currencyexchangerates                 |
| Typ av organisationshierarki     | msdyn_internalorganizationhierarchytypes    |
| Valutor                      | transactioncurrencies                       |
| Enhet för mixad verklighet     | msmrw_guides                                |

**Beroendeinformation**

Paketet appkärna med dubbla skrivningar är inte beroende av andra paket.

## <a name="dual-write-human-resources"></a>Dubbel skrivning Human Resources

I paketet med dubbelriktad skrivning Human Resources finns de lösningar och kartor som krävs för att personaldata ska synkroniseras. Den innehåller följande tre lösningar.

| Unikt namn                | Visa namn                             |
|----------------------------|------------------------------------------|
| HCMCommon                  | Gemensamt för HCM                               |
| msdyn_Dynamics365HCMMaps   | Dynamics 365 Human Resources enhetsmappningar |
| msdyn_Dynamics365HCMAnchor | Dynamics 365 Human Resources fästpunkt      |

Följande kartor finns i detta paket.

| Ekonomi och drift-appar | Kundengagemangsappar         |
|-----------------------------|----------------------------------|
| Etniska ursprung              | cdm_ethnicorigins                |
| Jobbfunktion för kompensation   | cdm_jobfunctions                 |
| Befattningar v2                | cdm_jobpositions                 |
| Jobb                        | cdm_jobs                         |
| Jobbtyp för kompensation       | cdm_jobtypes                     |
| Språkkoder              | cdm_languages                    |
| Befattningstyp               | cdm_positiontypes                |
| Befattningstilldelningar för arbetare | cdm_positionworkerassignmentmaps |
| Veteranstatus              | cdm_veteranstatuses              |
| Arbetare                      | cdm_workers                      |
| Anställning per företag      | cdm_employments                  |

**Beroendeinformation**

Dubbelriktad Human Resources-paketet beror på dubbelriktad appkärnpaketet. Därför bör du installera applikationskärna med dubbla skrivningar-paketet innan du installerar paketet Human Resources med dubbla skrivningar.

## <a name="dual-write-supply-chain"></a>Försörjningskedja med dubbel skrivning

I paketet Försörjningskedja finns de lösningar och kartor som krävs för att Supply Chain Management-data ska synkroniseras. Den innehåller följande tre lösningar.

| Unikt namn                                | Visa namn                                              |
|--------------------------------------------|-----------------------------------------------------------|
| Dynamics365SupplyChainExtended             | Dynamics 365 Supply Chain utökad                        |
| msdyn_Dynamics365SupplyChainExtendedMaps   | Dynamics 365 Supply Chain Management Extended enhetsmappningar |
| msdyn_Dynamics365SupplyChainExtendedAnchor | Dynamics 365 Supply Chain Management Extended ankare      |

Följande kartor finns i detta paket.

| Ekonomi och drift-appar                 | Kundengagemangsappar                      |
|---------------------------------------------|-----------------------------------------------|
| Enheter                                       | uoms                                          |
| CDS-försäljningsorderrubrik                     | salesorders                                   |
| CDS-försäljningsorderrader                       | salesorderdetails                             |
| CDS-försäljningsofferrubrik                  | anbudsförfrågningar                                        |
| Försäljningsoffertrader för CDS                   | quotedetails                                  |
| CDS‑frisläppta specifika produkter              | produkter                                      |
| Lagerställezoner                             | msdyn_warehousezones                          |
| Grupper - lagerställezoner                       | msdyn_warehousezonegroups                     |
| Lagerarbetesrader                        | msdyn_warehouseworklines                      |
| Huvuden för lagerarbete                      | msdyn_warehouseworkheaders                    |
| Lagerställen                                  | msdyn_warehouses                              |
| Lagergång                             | msdyn_warehouseaisles                         |
| Enhetskonverteringar                            | msdyn_unitofmeasureconversions                |
| Leveransvillkor                           | msdyn_termsofdeliveries                       |
| Leveranssätt                           | msdyn_shipvias                                |
| Produktmallutföranden                       | msdyn_sharedproductstyles                     |
| Försäljningsfakturarader V2                      | fakturainformation                                |
| Försäljningsfakturahuvuden V2                    | fakturor                                      |
| Produktmallstorlekar                        | msdyn_sharedproductsizes                      |
| Frisläppta produkter V2                        | msdyn_sharedproductdetails                    |
| Produktmallkonfigurationer               | msdyn_sharedproductconfigurations             |
| Produktmallfärger                       | msdyn_sharedproductcolors                     |
| Koder för försäljningsorderursprung                    | msdyn_salesorderorigins                       |
| Produktinleveranshuvud                      | msdyn_purchaseorderreceipts                   |
| Produktinleveransrad                        | msdyn_purchaseorderreceiptproducts            |
| Inköpsorderhuvuden V2                   | msdyn_purchaseorders                          |
| CDS-inköpsorderrad mjukt borttagen enhet | msdyn_purchaseorderproducts                   |
| Enhet för CDS-inköpsorderrad              | msdyn_purchaseorderproducts                   |
| Spårningsdimensionsgrupper                   | msdyn_producttrackingdimensiongroups          |
| Utföranden                                      | msdyn_productstyles                           |
| Lagringsdimensionsgrupper                    | msdyn_productstoragedimensiongroups           |
| Produktspecifika enhetskonverteringar           | msdyn_productspecificunitofmeasureconversions |
| Standardorderinställningar för produkt V2           | msdyn_productspecificdefaultordersettings     |
| Storlekar                                       | msdyn_productsizes                            |
| Produktdimensionsgrupper                    | msdyn_productdimensiongroups                  |
| Standardorderinställningar                      | msdyn_productdefaultordersettings             |
| Konfigurationer                              | msdyn_productconfigurations                   |
| Alla produkter                                | msdyn_globalproducts                          |
| Färger                                      | msdyn_productcolors                           |
| Produktkategorihierarkiroller            | msdyn_productcategoryhierarchyroles           |
| Produktkategorihierarkier                | msdyn_productcategoryhierarchies              |
| Produktkategoritilldelningar                | msdyn_productcategoryassignments              |
| Produktkategorier                          | msdyn_productcategories                       |
| Lagerplatser                         | msdyn_inventorylocations                      |
| CDS-inventering på                            | msdyn_inventoryonhandentries                  |
| Produktkategorier                          | msdyn_productcategories                       |
| CDS-inventering på                            | msdyn_inventoryonhandrequests                 |
| Produktnummer med identifierad streckkod           | msdyn_productbarcodes                         |
| Förmånskort                                | msdyn_loyaltycards                            |
| Förmånsbelöningspoäng                       | msdyn_loyaltyrewardpoints                     |
| Kundgrupper med pris                       | msdyn_pricecustomergroups                     |
| Sites                                       | msdyn_operationalsites                        |
| Försäljningsoffertrader för CDS                   | quotedetails                                  |
| CDS-försäljningsorderrader                       | salesorderdetails                             |

**Beroendeinformation**

Leveranskedjepaketet är beroende av följande tre paket. Därför bör du installera dessa paket innan du installerar leveranskedjepaketet för dubbelriktad skrivning.

- Paket för appkärna med dubbla skrivningar
- Dubbel riktad skrivning för Finance-paketet
- Dubbel skrivning Human Resources-paketet

## <a name="dual-write-finance"></a>Dubbel riktad skrivning för Finance

I paketet dubbelriktad skrivning för Finance finns de lösningar och kartor som krävs för att Dynamics 365 Finance-data ska synkroniseras. Den innehåller följande fyra lösningar.

| Unikt namn                            | Visa namn                               |
|----------------------------------------|-------------------------------------------|
| Dynamics365FinanceExtended             | Dynamics 365 Finance Extended             |
| msdyn_Dynamics365FinanceExtendedMaps   | Dynamics 365 Finance Extended entitetskartor |
| FieldServiceCommon                     | Field Service Common                      |
| msdyn_Dynamics365FinanceExtendedAnchor | Dynamics 365 Finance Extended-ankare      |

Följande kartor finns i detta paket.

| Ekonomi och drift-appar             | Kundengagemangsappar        |
|-----------------------------------------|---------------------------------|
| Källskattegrupper                  | msdyn_withholdingtaxgroups      |
| CDS kontakter V2 (kund)              | kontakter                        |
| CDS kontakter V2 (leverantör)                | kontakter                        |
| Kunder V3                            | kontakter                        |
| Källskattekoder                   | msdyn_withholdingtaxcodes       |
| Leverantörer V2                              | msdyn_vendors                   |
| Betalningsmetod för leverantör                   | msdyn_vendorpaymentmethods      |
| Leverantörsgrupper                           | msdyn_vendorgroups              |
| Kontoplan                       | msdyn_chartofaccountses         |
| Bokföringsgrupper V2 för momsredovisning      | msdyn_taxpostinggroups          |
| Artikelmomsgrupp                    | msdyn_taxitemgroups             |
| Momsgrupper                        | msdyn_taxgroups                 |
| Momsbefrielsekod CDS        | msdyn_taxexemptcodes            |
| Kundgrupper                         | msdyn_customergroups            |
| Kundbetalningsmetod                 | msdyn_customerpaymentmethods    |
| Ekonomiska dimensioner                    | msdyn_dimensionattributes       |
| Skattemyndigheter                   | msdyn_taxauthorities            |
| Format för ekonomisk dimension              | msdyn_financialdimensionformats |
| Period i räkenskapskalender                  | msdyn_fiscalcalendarperiods     |
| Integrationsenhet för räkenskapskalender      | msdyn_fiscalcalendars           |
| Integrationsenhet för räkenskapskalenderår | msdyn_fiscalcalendaryears       |
| Betalningsvillkor                        | msdyn_paymentterms              |
| Betalningsplan                        | msdyn_paymentschedules          |
| Betalningsplanrader                  | msdyn_paymentschedulelines      |
| Betalningsdagar – CDS                        | msdyn_paymentdays               |
| Betalningsdagsrader – CDS V2                | msdyn_paymentdaylines           |
| Huvudkonto                            | msdyn_mainaccounts              |
| Huvudkontokategorier                 | msdyn_mainaccountcategories     |
| Ledger                                  | msdyn_ledgers                   |
| Kunder V3                            | konton                        |

**Beroendeinformation**

Dubbelriktad Finance-paketet beror på dubbelriktad appkärnpaketet. Därför bör du installera applikationskärna med dubbla skrivningar-paketet innan du installerar paketet Finance med dubbla skrivningar.

## <a name="dual-write-notes"></a>Anteckning av dubbelriktad skrivning

I anteckningar paketet för dubbelriktad skrivning finns de lösningar och kartor som krävs för att anteckningar ska synkroniseras. Den innehåller följande fyra lösningar.

| Unikt namn                  | Visa namn                   |
|------------------------------|--------------------------------|
| Dynamics365Notes             | Dynamics 365 Anteckningar             |
| Dynamics365NotesExtended     | Dynamics 365 anteckningar utökad    |
| msdyn_Dynamics365NotesMaps   | Mappningar för Dynamics 365-noteringar |
| msdyn_Dynamics365NotesAnchor | Dynamics 365 anteckningar ankare      |

Följande kartor finns i detta paket.

| Ekonomi och drift                     | Customer Engagement |
|--------------------------------------------|---------------------|
| Försäljningsorderrubrikens dokumentbilagor    | anteckningar         |
| Kundbilagor                       | anteckningar         |
| Bilagor till leverantörsdokument                | anteckningar         |
| Inköpsorderhuvudets dokumentbilagor | anteckningar         |

**Beroendeinformation**

Anteckningar paketet är beroende av följande två paket. Därför bör du installera dessa paket innan du installerar anteckningar paketet för dubbelriktad skrivning.

- Paket för appkärna med dubbla skrivningar
- Dubbel riktad skrivning för Finance-paketet

## <a name="dual-write-asset-management"></a>Dubbelriktad skrivning för tillgångshantering

I paketet dubbelriktad skrivning för tillgångshantering innehåller de lösningar och kartor som krävs för att synkronisera tillgångsdata från Supply Chain Management eller Dynamics 365 Field Service. Den innehåller följande fyra lösningar.

| Unikt namn                          | Visa namn                              |
|--------------------------------------|-------------------------------------------|
| Dynamics365AssetManagement           | Dynamics 365 tillgångshantering             |
| Dynamics365AssetManagementApp        | Dynamics365 tillgångshanteringsapp          |
| msdyn_DualWriteAssetManagementMaps   | Mappningar för Dynamics 365 tillgångshantering |
| msdyn_DualWriteAssetManagementAnchor | Dynamics 365 tillgångshantering fästpunkt      |

Följande kartor finns i detta paket.

| Ekonomi och drift-appar                           | Kundengagemangsappar                |
|-------------------------------------------------------|-----------------------------------------|
| Garanti över tillgångshantering                             | msdyn_warranties                        |
| Tillgångshanteringsmodeller                               | msdyn_models                            |
| Tillverkare för tillgångshantering                        | msdyn_manufacturers                     |
| Funktionsplatstyper för tillgångshantering            | msdyn_functionallocationtypes           |
| Funktionsplatser för tillgångshantering                 | msdyn_functionallocations               |
| Livscykeltillstånd för funktionsplatsens tillgångshantering | msdyn_functionallocationlifecyclestates |
| Livscykelmodeller för funktionsplatsens tillgångshantering | msdyn_functionallocationlifecyclemodels |
| Tillgångar för hantering av tillgångar                               | msdyn_customerassets                    |
| Tillgångstyper för hantering av tillgångar                          | msdyn_customerassetcategories           |
| Tillgångshantering för livscykeltillstånd av tillgångar               | msdyn_assetlifecyclestates              |
| Tillgångshantering för livscykelmodeller av tillgångar               | msdyn_assetlifecyclemodels              |

**Beroendeinformation**

Dubbelriktad Tillgångshantering-paketet beror på dubbelriktad appkärnpaketet. Därför bör du installera applikationskärna med dubbla skrivningar-paketet innan du installerar paketet Tillgångshantering med dubbla skrivningar.

## <a name="packages-required-for-project-operations"></a>Paket som krävs för Project Operations
Project Operations är beroende av följande paket. Därför bör du installera dessa paket innan du installerar Project Operations.

- Paket för appkärna med dubbla skrivningar
- Dubbel riktad skrivning för Finance-paketet
- Försörjningskedja paket med dubbel skrivning
- Dubbelriktad skrivning för tillgångshantering paket
- Dubbel skrivning Human Resources-paketet

## <a name="dual-write-party-and-global-address-book-solutions"></a>Lösningar för dubbelskrivningspart och global adressbok

Det paketet med dubbelskrivningspart och global adressbok innehåller följande lösningar och kartor som krävs för att synkronisera part- och globala adressboksdata. 

| Unikt namn                       | Visningsnamn                            |
|-----------------------------------|-----------------------------------------|
| Part                             | Part                                   |
| Dynamics365GABExtended            | Dynamics 365 GAB Extended               |
| Dynamics365GABDualWriteEntityMaps | Dynamics 365 GAB entitetskartor för dubbelriktad skrivning |
| Dynamics365GABParty_Anchor        | Dynamics 365 GAB och part              |

Följande kartor finns i detta paket.

| appar för ekonomi och drift | Kundengagemangsappar | 
|-----------------------------|--------------------------|
| CDS-parter | msdyn_parties | 
| Platser för postadressen för CDS | msdyn_postaladdresscollections | 
| Historik över postadressen för CDS V2 | msdyn_postaladdresses | 
| Platser för CDS-partens postadress | msdyn_partypostaladdresses | 
| Partkontakter V3 | msdyn_partyelectronicaddresses | 
| Kunder V3 | konton | 
| Kunder V3 | kontakter | 
| Leverantörer V2 | msdyn_vendors | 
| Kontaktpersonens titlar | msdyn_salescontactpersontitles | 
| Avslutningsfraser | msdyn_complimentaryclosings | 
| Tilltal | msdyn_salutations | 
| Roller för beslutsfattare | msdyn_decisionmakingroles | 
| Anställningsfunktioner | msdyn_employmentjobfunctions | 
| Lojalitetsnivåer | msdyn_loyaltylevels | 
| Typer av personliga egenskaper | msdyn_personalcharactertypes | 
| Kontakter V2 | msdyn_contactforparties | 
| CDS-försäljningsofferrubrik | anbudsförfrågningar | 
| CDS-försäljningsorderrubrik | salesorders | 
| Försäljningsfakturahuvuden V2 | fakturor | 
| CDS-adressroller | msdyn_addressroles |

**Beroendeinformation**

Lösningarna för dubbelriktad skrivning och global adressbok beror på följande tre paket. Därför bör du installera dessa paket innan du installerar paketet med lösningar för dubbelriktad skrivning och global adressbok.

- Paket för appkärna med dubbla skrivningar
- Dubbel riktad skrivning för Finance-paketet
- Försörjningskedja paket med dubbel skrivning
