---
title: Potentiell kund till kontanter vid dubbel skrivning
description: I den här artikeln finns information om kunders kontantkassa vid dubbel skrivning.
author: RamaKrishnamoorthy
ms.date: 01/07/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-27
ms.openlocfilehash: 4321d980f56e321a653ca4f4c5738ebd1bb0153d
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9289621"
---
# <a name="prospect-to-cash-in-dual-write"></a>Potentiell kund till kontanter vid dubbel skrivning

[!include [banner](../../includes/banner.md)]

Ett viktigt mål för de flesta företag är att konvertera potentiell kund till kontanter och sedan underhålla en pågående affärsrelation med kunderna. I Microsoft Dynamics 365-appar processen potentiell kund till pengar via arbetsflöden för offerter eller orderbearbetning och ekonomierna stäms av och redovisas. Integrering av potentiell kund till pengar med dubbel skrivning skapar ett arbetsflöde som tar en offert och en order som har sitt ursprung i antingen Dynamics 365 Sales eller Dynamics 365 Supply Chain Management och gör offerten och ordern tillgängliga i båda apparna.

I programgränssnitten får du åtkomst till bearbetningsstatus och fakturainformation i realtid. Därför är det enklare att hantera funktioner som produktlager, lagerhantering och uppfyllelse i Supply Chain Management, utan att du behöver skapa offerter och order på nytt.

![Dataflöde med dubbel skrivning i potentiell kund-till-pengar.](../dual-write/media/dual-write-prospect-to-cash[1].png)

Mer information om kund- och kontaktintegrering finns i [Integrerad kundmall](customer-mapping.md). Information om produktintegration finns i [Enhetlig produkterfarenhet](product-mapping.md).

> [!NOTE]
> I Dynamics 365 Sales, refererar både potentiell kund och kund till en post i tabellen **Konto** där kolumnen **RelationshipType** är antingen **Potentiell kund** eller **Kund**. Om din affärslogik innehåller en kvalifikationsprocess för **Konto** där posten **Konto** skapas och kvalificeras som potentiell kund först och sedan som en kund, kommer den kunden att synkroniseras till appen för ekonomi och drift först när den är en kund (`RelationshipType=Customer`). Om du vill att raden **Konto** ska synkroniseras som en potentiell kund, behöver du en anpassad mappning för att integrera data för potentiell kund.

## <a name="prerequisites-and-mapping-setup"></a>Ställa in mappning och förutsättningar

Innan du kan synkronisera försäljningsofferter måste du uppdatera följande inställningar.

### <a name="setup-in-sales"></a>Inställningar i Sales

I Sales, gå till **Inställningar \> Administration \> Systeminställningar \> Sales** och säkerställ att följande inställningar används:

- Systemalternativet **Använd systemets beräkningssystem för prissättning** anges som **Ja**.
- Kolumnen **Metod för rabattberäkning** har tilldelats **radartikel**.

### <a name="sites-and-warehouses"></a>Webbplatser och lagerställen

I Supply Chain Management är kolumnerna **Webbplats** och **Lagerställe** krävs för offertrader och orderrader. Om du ställer in webbplats och lagerstället i standard orderinställningarna kommer dessa kolumner automatiskt att ställas in när du lägger till en produkt på en offertrad eller en orderrad. 

### <a name="number-sequences-for-quotations-and-orders"></a>Nummerserier för offerter och order

Nummer serierna för Supply Chain Management och Sales inte är kopplade när offerter och order skapas och synkroniseras i Sales och Supply Chain Management. Om en försäljningsorder som skapas i Sales synkroniseras för Supply Chain Management, har den samma försäljningsorder nummer i Supply Chain Management. För att se till att försäljningsordernumret inte dupliceras måste du använda olika nummerseriesystem i de två programmen.

Nummerserien i hanteringen av Supply Chain Management är **1, 2, 3, 4, 5, ...** och nummerserien i Sales är **100, 99, 98, ...**. Om du skapar 100 försäljningsorder i Sales, ett ordernummer kommer slutligen genereras att den redan existerar i Supply Chain Management. Med andra ord överlappar de två nummerserierna när försäljningsorder skapas i Supply Chain Management och Sales. I stället kan du använda en nummerserie, t.ex. **F1, F2, F3, ...** i Supply Chain Management och nummerserien, t.ex. **C1, C2, C3, ...** i Sales. Dessa nummerserier resulterar aldrig i dubbla försäljningsordernummer.

## <a name="sales-quotations"></a>Försäljningsofferter

Försäljningsofferter kan skapas antingen i Sales eller Supply Chain Management. Om du skapar en offert i Sales synkroniseras den med Supply Chain Management i realtid. Om du skapar en offert i Supply Chain Management, synkroniseras den med Sales i realtid. Observera följande:

+ Du kan lägga till en rabatt för produkten på offerten. I det här fallet kommer rabatten att synkroniseras med Supply Chain Management. Kolumnerna **rabatt**, **tillägg**, och **moms** på rubriken styrs av en inställning i Supply Chain Management. Den här inställningen stöder inte integreringsmappning. I stället underhålls kolumnerna **pris**, **rabatt**, **tillägg**, och **moms** i Supply Chain Management.
+ Kolumnerna **Rabattprocent**, **Rabatt** och **Fraktbelopp** på försäljningsoffertens rubrik är skrivskyddade kolumner.
+ Kolumnerna **betalningsvillkor**, **fraktvillkor**, **leveransvillkor**, **leveranssätt** och leveransläge tillhör inte standardmappningarna. Om du vill mappa dessa kolumner måste du konfigurera en värdemappning som är specifik för data i organisationer som tabellen synkroniseras mellan.

Om du även använder Field Service-lösningen måste du aktivera parametern **Snabbskapa anbudsförfrågan**. Om du aktiverar parametern igen kan du fortsätta skapa offertrader med hjälp av funktionen snabbgenerering.

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
    - När en försäljningsorderrad synkroniseras från Sales till Supply Chain Management används fullständig radrabatt. Eftersom Supply Chain Management inte har några kolumner som kan innehålla fullständiga rabattbeloppet för en rad, divideras beloppet med kvantiteten och lagras i kolumnen **radrabatt**. All avrundning som uppstår i denna division lagras i kolumnen **försäljningstillägg** på försäljningsraden.

### <a name="example-synchronization-from-sales-to-supply-chain-management"></a>Exempel: Synkronisering från Sales till Supply Chain Management

Du har följande försäljningsorder:

+ **Sales:** kvantitet = 3 per radrabatt = $10,00
+ **Supply Chain Management** : kvantitet = 3, radrabattbelopp = 3,33 $, försäljningsavgift = – 0,01 $

Om du synkroniserar från Supply Chain Management till Sales får du följande resultat:

+ **Supply Chain Management** : kvantitet = 3, radrabattbelopp = 3,33 $, försäljningsavgift = – 0,01 $
+ **Sales:** kvantitet = 3 per radrabatt = (3 × $3,33) + $0,01 = $10,00

## <a name="dual-write-solution-for-sales"></a>Lösningar för dubbelriktad skrivning för Sales

Nya kolumner har lagts till i tabellen **Order** och visas på sidan. De flesta av dessa kolumner visas på fliken **integration** i Sales. För att veta mer om hur statuskolumner mappas ska du gå till [Ställa in mappningen för kolumner för försäljningsorderstatus](sales-status-map.md).

+ Knapparna **skapa faktura** och **annullera order** på sidan **försäljningsorder** är dolda i Sales.
+ Värdet **Status för försäljningsorder** förblir **aktiv** för att se till att ändringar från Supply Chain Management når Försäljningsordern i Sales. För att styra detta beteende, ange standardvärdet till **Statuskod \[Status\]** till **Aktiv**.

## <a name="invoices"></a>Fakturor

Försäljningsfakturor skapas i Supply Chain Management och synkroniseras med Sales. Observera följande:

+ En kolumn för **fakturanummer** har lagts till i tabellen **Faktura** och visas på sidan.
+ Knappen **Skapa faktura** på sidan **Försäljningsorder** är dold eftersom fakturorna skapas i Supply Chain Management och synkroniseras med Sales. Sidan **Faktura** kan inte redigeras eftersom fakturorna synkroniseras från Supply Chain Management.
+ Värdet **Status för försäljningsorder** ändras automatiskt till **Fakturerad** när tillhörande faktura från Supply Chain Management har synkroniserats med Sales. Dessutom kan ägaren till den försäljningsorder som fakturan skapades från tilldelas fakturaägaren. Därför kan ägaren till försäljningsordern kan visa fakturan.
+ Kolumner **betalningsvillkor**, **fraktvillkor** och **leveranssätt** och leveransläge tillhör inte standardmappningarna. Om du vill mappa dessa kolumner måste du konfigurera en värdemappning som är specifik för data i organisationer som tabellen synkroniseras mellan.

## <a name="templates"></a>Mallar

Potentiell kund till kontanter inkluderar en samling tabellmappningar som fungerar tillsammans under kunddatainteraktion, enligt följande tabell.

| Appar för ekonomi och drift | Kundengagemangsappar | Beskrivning |
|-----------------------------|-----------------------------------|-------------|
[Alla produkter](mapping-reference.md#138) | msdyn_globalproducts | |
[Kunder V3](mapping-reference.md#101) | konton | |
[Kunder V3](mapping-reference.md#116) | kontakter | |
[Kontakter V2](mapping-reference.md#221) | msdyn_contactforparties | |
[CDS-försäljningsorderrubrik](mapping-reference.md#217) | salesorders | |
[CDS-försäljningsorderrader](mapping-reference.md#216) | salesorderdetails | |
[CDS-försäljningsofferrubrik](mapping-reference.md#215) | anbudsförfrågningar | |
[Försäljningsoffertrader för CDS](mapping-reference.md#214) | quotedetails | |
[Frisläppta produkter V2](mapping-reference.md#189) | msdyn_sharedproductdetails | |
[Försäljningsfakturahuvuden V2](mapping-reference.md#118) | fakturor | Tabellen Försäljningsfakturahuvuden V2 i appen för ekonomi och drift innehåller fakturor för försäljningsorder och fritextfakturor. Ett filter används för Dataverse för att filtrera bort eventuella fritextfakturadokument. |
[Försäljningsfakturarader V2](mapping-reference.md#117) | fakturainformation | |
[Koder för försäljningsorderursprung](mapping-reference.md#186) | msdyn_salesorderorigins | |

Information om prislistor finns i [Enhetlig produkterfarenhet](product-mapping.md).

## <a name="limitations"></a>Begränsningar

- Returorder stöds inte.
- Kreditfakturor stöds inte.
- Ekonomiska dimensioner måste anges för huvuddata, till exempel kund och leverantör. När en kund läggs till en offert eller försäljningsorder, flödar kundposten automatiskt till ordern. För närvarande innehåller inte dessa ekonomiska dimensioner några data för huvuddata.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

