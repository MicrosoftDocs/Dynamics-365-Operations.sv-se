---
title: Synkronisera försäljningsoffertrubriker och rader direkt från Sales till Supply Chain Management
description: I det här ämnet diskuteras mallarna och de underliggande uppgifterna som används för att synkronisera försäljningsoffertrubriker och rader direkt från Dynamics 365 Sales till Dynamics 365 Supply Chain Management.
author: ChristianRytt
manager: tfehr
ms.date: 10/25/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: c7d4cacbf56243830633f4d0fd3c57071b08ab56
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/17/2020
ms.locfileid: "4527348"
---
# <a name="synchronize-sales-quotation-headers-and-lines-directly-from-sales-to-supply-chain-management"></a>Synkronisera försäljningsoffertrubriker och rader direkt från Sales till Supply Chain Management

[!include [banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

I det här ämnet diskuteras mallarna och de underliggande uppgifterna som används för att synkronisera försäljningsoffertrubriker och rader direkt från Dynamics 365 Sales till Dynamics 365 Supply Chain Management.

> [!NOTE]
> Innan du kan använda lösningen Potentiell kund till kontanter ska du bekanta dig med [integrera data i Common Data Service för appar](https://docs.microsoft.com/powerapps/administrator/data-integrator).

## <a name="data-flow-in-prospect-to-cash"></a>Dataflöden i Potentiell kund till kontanter

Lösningen Potentiell kund till kontanter använder funktionen Dataintegrering för att synkronisera data mellan instanser av Supply Chain Management och Sales. Potentiell kund till kontanter-mallarna med funktionen för dataintegrering möjliggör ett flöde av konto-, produkt-, försäljningskvots-, försäljningsorder- samt försäljningsfakturadata mellan Supply Chain Management och Sales. Följande bild visar hur data synkroniseras mellan Supply Chain Management och Sales.

[![Dataflöden i Potentiell kund till kontanter](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="template-and-tasks"></a>Mall och uppgifter

Följande mallar och underliggande uppgifter används för att synkronisera huvuden och rader direkt i försäljningsofferter från Supply Chain Management:

- **Namnet på mallen i dataintegrering:** försäljningsofferter (Sales till Supply Chain Management) - Direkt
- **Namnen på uppgifterna i dataintegreringsprojektet:**

    - QuoteHeader
    - QuoteLine

Följande synkroniseringsuppgifter krävs före synkronisering av huvuden och rader i försäljningsofferter kan uppstå:

- Produkter (Supply Chain Management till Sales) - direkt
- Konton (Sales till Supply Chain Management)-direkt (om den används)
- Kontakter till kunder (Sales till Supply Chain Management) - direkt (om den används)

## <a name="entity-set"></a>Ange entiteten

| Försäljning        | Hantering av underleverantörer     |
|--------------|----------------------------|
| Citat       | CDS-försäljningsofferrubrik |
| QuoteDetails | Försäljningsoffertrader för CDS  |

## <a name="entity-flow"></a>Flöde för entitet

Försäljningsofferter skapas i Sales och synkroniseras med Supply Chain Management.

Försäljningsofferter från Sales synkroniseras endast om följande villkor är uppfyllda:

- Alla offertprodukter på försäljningsofferna hanteras externt.
- När du har klickat på **aktivera offert**, är försäljningsofferten aktiv.

## <a name="prospect-to-cash-solution-for-sales"></a>Lösningen potentiell kund till kontanter för Sales

Fältet **Har endast externt hanterade produkter** har lagts till entiteten **Offert** för att konstant spåra om försäljningsofferten helt består av externt underhållna produkter. Om en försäljningsoffert endast har externt underhållna produkter, underhålls produkter i Supply Chain Management. Detta beteende hjälper till att garantera att du inte försöker synkronisera försäljningsoffertraderna med produkter som är okända för Supply Chain Management.

Alla offertprodukter på försäljningsofferten uppdateras med informationen **Har endast externt hanterade produkter** från försäljningsofferthuvudet. Den här informationen finns i fältet **Offerten har endast externt hanterade produkter** på entiteten **Offertdetaljer**.

En rabatt kan läggas till i offertprodukten och synkroniseras med Supply Chain Management. Fälten **rabatt**, **tillägg**, och **moms** på rubriken styrs av en inställning i Supply Chain Management. För närvarande stöder inte den här inställningen integreringsmappning. I den aktuella designen underhålls fälten **pris**, **rabatt**, **tillägg**, och **moms** i Supply Chain Management.

I Sales gör lösningen följande fält skrivskyddade, eftersom värdena inte ska synkroniseras till Supply Chain Management.

- Skrivskyddade fält på försäljningsoffertens huvud: **Rabatt %**, **Rabatt** och **Fraktbelopp**
- Skrivskyddade fält på offertprodukter: **moms**

## <a name="preconditions-and-mapping-setup"></a>Ställa in mappning och förutsättningar

Innan försäljningsofferter synkroniseras är det viktigt att du uppdaterar följande inställningar.

### <a name="setup-in-sales"></a>Inställningar i Sales

- Se till att behörigheterna ställs in för teamet som användaren från din anslutning som anges i Sales har tilldelats. Om du använder demodata har användaren vanligtvis administratörsåtkomst, men inte administratöråtkomst. Om gruppen inte har administratörsåtkomst även när du kör projektet från dataintegration, visas ett felmeddelande att primärt team saknas.

    Om du vill ställa in behörigheter för gruppen gå till **inställningar**&gt;**säkerhet**&gt;**team**, och välj relevant team. Välj **hantera roller**, och välj sedan en roll med behörigheter, t.ex. **systemadministratör**.

- Gå till **inställningar** &gt; **Administration** &gt; **systeminställningar** &gt; **Sales** och säkerställ att följande inställningar används:

    - Alternativet **Använd systemets prisberäkningssystem** är **Ja**.
    - Fältet **Metod för rabattberäkning** har tilldelats **radartikel**.

### <a name="setup-in-the-data-integration-project"></a>Inställningar i dataintegreringsprojektet

#### <a name="quoteheader"></a>QuoteHeader

- Kontrollera att nödvändig mappning finns i **Shipto\_land** till **DeliveryAddressCountryRegionISOCode**. Du kan definiera ett standardvärde som används om värdet är tomt i värdemappningen. Lämna bara värdet på vänster sida tomt och ange höger sida till önskat land eller region. På så sätt kan du inte ange land eller region för nationella order.

    Mallvärdet är en värdemappning där flera länder eller regioner som mappas och där ett tomt värde är lika med **US**.

#### <a name="quoteline"></a>QuoteLine

- Kontrollera att nödvändig värdemappning finns för **Säljenhetssymbol** i Supply Chain Management.
- Kontrollera att nödvändiga enheter definieras i Sales.

    En värdemall som har en värdemappning definieras för **oumid.name** till **Säljenhetssymbol**.

- Valfritt: Du kan lägga till följande mappningar för att garantera att försäljningsoffertraderna importeras till Supply Chain Management om det inte finns någon standardinformation från varken kunden eller produkten:

    - **SiteId** – en plats måste anges för att skapa offerter och försäljningsorderrader i Supply Chain Management. Det finns inget standrdmallvärde för **SiteId**.
    - **WarehouseId** – ett lagerställe måste anges för att skapa offerter och försäljningsorderrader i Supply Chain Management. Det finns inget standrdmallvärde för **WarehouseId**.

## <a name="template-mapping-in-data-integrator"></a>Mallmappning i dataintegratör

> [!NOTE]
> - Fälten **rabatt**, **tillägg**, och **moms** styrs av en komplex inställning i Supply Chain Management. För närvarande stöder inte den här inställningen integreringsmappning. I den aktuella designen hanteras fälten **pris**, **rabatt**, **tillägg**, och **moms** av Supply Chain Management.
> - Fälten **betalningsvillkor**, **fraktvillkor**, **leveransvillkor**, **leveranssätt** och **leveransläge** tillhör inte standardmappningarna. Om du vill mappa dessa fält måste du konfigurera en värdemappning som är specifik för data i organisationer som enheten synkroniseras mellan.

I följande illustrationer visas ett exempel på en mallmappning i dataintegratör.

### <a name="quoteheader"></a>QuoteHeader

![Mallmappning i dataintegratör](./media/sales-quotation-direct-template-mapping-data-integrator-1.png)

### <a name="quoteline"></a>QuoteLine

![Mallmappning i dataintegratör](./media/sales-quotation-direct-template-mapping-data-integrator-2.png)

## <a name="related-topics"></a>Relaterade ämnen

[Potentiell kund till kontanter](prospect-to-cash.md)

