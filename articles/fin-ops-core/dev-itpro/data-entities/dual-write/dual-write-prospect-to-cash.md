---
title: Potentiell kund till kontanter vid dubbel skrivning
description: I det här avsnittet finns information om kunders kontantkassa vid dubbel skrivning.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-01-27
ms.openlocfilehash: 3b482a2754bb4bcaca5410da72c21897fd066a41
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4683657"
---
# <a name="prospect-to-cash-in-dual-write"></a>Potentiell kund till kontanter vid dubbel skrivning

[!include [banner](../../includes/banner.md)]



Ett viktigt mål för de flesta företag är att konvertera potentiell kund till kontanter och sedan underhålla en pågående affärsrelation med kunderna. I Microsoft Dynamics 365-appar processen potentiell kund till pengar via arbetsflöden för offerter eller orderbearbetning och ekonomierna stäms av och redovisas. Integrering av potentiell kund till pengar med dubbel skrivning skapar ett arbetsflöde som tar en offert och en order som har sitt ursprung i antingen Dynamics 365 Sales eller Dynamics 365 Supply Chain Management och gör offerten och ordern tillgängliga i båda apparna.

I programgränssnitten får du åtkomst till bearbetningsstatus och fakturainformation i realtid. Därför är det enklare att hantera funktioner som produktlager, lagerhantering och uppfyllelse i Supply Chain Management, utan att du behöver skapa offerter och order på nytt.

![Dataflöde med dubbel skrivning i potentiell kund till kontanter](../dual-write/media/dual-write-prospect-to-cash[1].png)

## <a name="prerequisites-and-mapping-setup"></a>Ställa in mappning och förutsättningar

Innan du kan synkronisera försäljningsofferter måste du uppdatera följande inställningar.

### <a name="setup-in-sales"></a>Inställningar i Sales

I Sales, gå till **Inställningar \> Administration \> Systeminställningar \> Sales** och säkerställ att följande inställningar används:

- Systemalternativet **Använd systemets prisberäkning** är **Ja**.
- Fältet **Metod för rabattberäkning** har tilldelats **radartikel**.

### <a name="sites-and-warehouses"></a>Webbplatser och lagerställen

I Supply Chain Management är fälten **Webbplats** och **Lagerställe** krävs för offertrader och orderrader. Om du ställer in webbplats och lagerstället i standard orderinställningarna kommer dessa fält automatiskt att ställas in när du lägger till en produkt på en offertrad eller en orderrad. 

### <a name="number-sequences-for-quotations-and-orders"></a>Nummerserier för offerter och order

Nummer serierna för Supply Chain Management och Sales inte är kopplade när offerter och order skapas och synkroniseras i Sales och Supply Chain Management. Om en försäljningsorder som skapas i Sales synkroniseras för Supply Chain Management, har den samma försäljningsorder nummer i Supply Chain Management. För att se till att försäljningsordernumret inte dupliceras måste du använda olika nummerseriesystem i de två programmen.

Nummerserien i hanteringen av Supply Chain Management är **1, 2, 3, 4, 5, ...** och nummerserien i Sales är **100, 99, 98, ...**. Om du skapar 100 försäljningsorder i Sales, ett ordernummer kommer slutligen genereras att den redan existerar i Supply Chain Management. Med andra ord överlappar de två nummerserierna när försäljningsorder skapas i Supply Chain Management och Sales. I stället kan du använda en nummerserie, t.ex. **F1, F2, F3, ...** i Supply Chain Management och nummerserien, t.ex. **C1, C2, C3, ...** i Sales. Dessa nummerserier resulterar aldrig i dubbla försäljningsordernummer.

## <a name="sales-quotations"></a>Försäljningsofferter

Försäljningsofferter kan skapas antingen i Sales eller Supply Chain Management. Om du skapar en offert i Sales synkroniseras den med Supply Chain Management i realtid. Om du skapar en offert i Supply Chain Management, synkroniseras den med Sales i realtid. Observera följande:

+ Du kan lägga till en rabatt för produkten på offerten. I det här fallet kommer rabatten att synkroniseras med Supply Chain Management. Fälten **rabatt**, **tillägg**, och **moms** på rubriken styrs av en inställning i Supply Chain Management. Den här inställningen stöder inte integreringsmappning. I stället underhålls och underhålls fälten **pris**, **rabatt**, **tillägg**, och **moms** i Supply Chain Management.
+ Fälten **Rabatt %**, **Rabatt** och **Fraktbelopp** fält på försäljningsoffertens rubrik är skrivskyddade fält.
+ Fälten **betalningsvillkor**, **fraktvillkor**, **leveransvillkor**, **leveranssätt** och leveransläge tillhör inte standardmappningarna. Om du vill mappa dessa fält måste du konfigurera en värdemappning som är specifik för data i organisationer som enheten synkroniseras mellan.

Om du även använder Field Service-lösningen måste du aktivera parametern **Snabbskapa anbudsförfrågan**. Om du aktiverar parametern igen kan du fortsätta att skapa offertrader med hjälp av funktionen snabbgenerering.
1. Navigera till ditt Dynamics 365 Sales-program.
2. Välj ikonen Inställningar i det övre navigeringsfältet.
3. Välj **avancerade inställningar**.
4. Välj alternativet **anpassa systemet**.
5. Välj menyalternativet **offertrad**.
6. Gå till avsnittet **datatjänster** och markera kryssrutan **Tillåt snabbskapande**.

## <a name="sales-orders"></a>Försäljningsorder

Försäljningsorder kan skapas antingen i Sales eller Supply Chain Management. Om du skapar en försäljningsorder i Sales synkroniseras den med Supply Chain Management i realtid. Om du skapar en försäljningsorder i Supply Chain Management synkroniseras den med Sales i realtid. Observera följande:

+ Produkter som körs på Dynamics 365 Sales visas som produkt kategorier i Dynamics 365 Supply Chain Management.
+ Rabattberäkning och avrundning:

    - Rabattberäkningsmodellen i Sales avviker från rabattberäkningsmodell i Supply Chain Management. I Supply Chain Management kan det slutgiltiga rabattbeloppet på en försäljningsrad vara resultatet av en kombination av rabattbelopp och rabattsatser. Om detta slutliga rabattbelopp divideras med antalet på raden, kan avrundning uppstå. Den här typen av avrundning inkluderas inte om ett avrundat rabattbelopp per enhet synkroniseras till Sales. För att garantera att det fullständiga rabattbeloppet från en försäljningsrad i Supply Chain Management synkroniseras korrekt till Sales, måste hela beloppet synkroniseras utan att divideras med radkvantiteten. Därför måste du definiera rabattberäkningsmetod som **radartikel** i Sales.
    - När en försäljningsorderrad synkroniseras från Sales till Supply Chain Management används fullständig radrabatt. Eftersom Supply Chain Management inte har några fält som kan innehålla fullständiga rabattbeloppet för en rad, divideras beloppet med kvantiteten och lagras i fältet **radrabatt**. All avrundning som uppstår i denna division lagras i fältet **försäljningstillägg** på försäljningsraden.

### <a name="example-synchronization-from-sales-to-supply-chain-management"></a>Exempel: Synkronisering från Sales till Supply Chain Management

Du har följande försäljningsorder:

+ **Sales:** kvantitet = 3 per radrabatt = $10,00
+ **Supply Chain Management** : kvantitet = 3, radrabattbelopp = 3,33 $, försäljningsavgift = – 0,01 $

Om du synkroniserar från Supply Chain Management till Sales får du följande resultat:

+ **Supply Chain Management** : kvantitet = 3, radrabattbelopp = 3,33 $, försäljningsavgift = – 0,01 $
+ **Sales:** kvantitet = 3 per radrabatt = (3 × $3,33) + $0,01 = $10,00

## <a name="dual-write-solution-for-sales"></a>Lösningar för dubbelriktad skrivning för Sales

Nya fält har lagts till i enheten **Order** och visas på sidan. De flesta av dessa fält visas på fliken **integration** i Sales. För att veta mer om hur statusfälten mappas ska du gå till [Ställa in mappningen för fält för försäljningsorderstatus](sales-status-map.md).

+ Knapparna **skapa faktura** och **annullera order** på sidan **försäljningsorder** är dolda i Sales.
+ Värdet **Status för försäljningsorder** förblir **aktiv** för att se till att ändringar från Supply Chain Management når Försäljningsordern i Sales. För att styra detta beteende, ange standardvärdet till **Statuskod \[Status\]** till **Aktiv**.

## <a name="invoices"></a>Fakturor

Försäljningsfakturor skapas i Supply Chain Management och synkroniseras med Sales. Observera följande:

+ Ett fält för **fakturanummer** har lagts till i entiteten **Faktura** och visas på sidan.
+ Knappen **Skapa faktura** på sidan **Försäljningsorder** är dold eftersom fakturorna skapas i Supply Chain Management och synkroniseras med Sales. Sidan **Faktura** kan inte redigeras eftersom fakturorna synkroniseras från Supply Chain Management.
+ Värdet **Status för försäljningsorder** ändras automatiskt till **Fakturerad** när tillhörande faktura från Supply Chain Management har synkroniserats med Sales. Dessutom kan ägaren till den försäljningsorder som fakturan skapades från tilldelas till fakturaägaren. Därför kan ägaren till försäljningsordern kan visa fakturan.
+ Fälten **betalningsvillkor**, **fraktvillkor** och **leveranssätt** och leveransläge tillhör inte standardmappningarna. Om du vill mappa dessa fält måste du konfigurera en värdemappning som är specifik för data i organisationer som enheten synkroniseras mellan.

## <a name="templates"></a>Mallar

Potentiell kund till kontanter inkluderar en samling tabellmappningar som fungerar tillsammans under kunddatainteraktion, enligt följande tabell.

| Finance and Operations-appar | Modellstyrda appar i Dynamics 365 | beskrivning |
|-----------------------------|-----------------------------------|-------------|
| Försäljningsfakturahuvuden V2    | fakturor                          |             |
| Försäljningsfakturarader V2      | fakturainformation                    |             |
| CDS-försäljningsorderrubrik     | salesorders                       |             |
| CDS-försäljningsorderrader       | salesorderdetails                 |             |
| Koder för försäljningsorderursprung    | msdyn\_salesorderorigins          |             |
| CDS-försäljningsofferrubrik  | anbudsförfrågningar                            |             |
| Försäljningsoffertrader för CDS   | quotedetails                      |             |

Här är de relaterade huvudsakliga tabellmappningarna för potentiella kunder till kontanter:

+ [Kunder V3 till konton](customer-mapping.md#customers-v3-to-accounts)
+ [CDS-kontakter V2 till kontakter](customer-mapping.md#cds-contacts-v2-to-contacts)
+ [Kunder V3 till kontakter](customer-mapping.md#customers-v3-to-contacts)
+ [Frisläppta produkter V2 till msdyn_sharedproductdetails](product-mapping.md#released-products-v2-to-msdyn_sharedproductdetails)
+ [Alla produkter till msdyn_globalproducts](product-mapping.md#all-products-to-msdyn_globalproducts)
+ [Prislista](product-mapping.md)

[!include [symbols](../../includes/dual-write-symbols.md)]

[!include [sales invoice](includes/SalesInvoiceHeaderV2Entity-invoice.md)]

[!include [sales invoice line](includes/SalesInvoiceLineV2Entity-invoicedetail.md)]

[!include [sales order header](includes/SalesOrderHeaderCDSEntity-salesorder.md)]

[!include [sales order line](includes/SalesOrderLineCDSEntity-salesorderdetails.md)]

[!include [sales order origin](includes/SalesOrderOriginEntity-msdyn-salesorderorigin.md)]

[!include [sales quotation header](includes/SalesQuotationHeaderCDSEntity-quote.md)]

[!include [sales quotation line](includes/SalesQuotationLineCDSEntity-QuoteDetails.md)]


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]