---
title: Synkronisera produkter direkt från Supply Chain Management till produkter i Sales
description: Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera produkter från Dynamics 365 Supply Chain Management till Dynamics 365 Sales.
author: ChristianRytt
manager: tfehr
ms.date: 06/10/2019
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
ms.openlocfilehash: 85ea6d37079c965ac5ddfdc4cdd20f2f3d184e4f
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3216124"
---
# <a name="synchronize-products-directly-from-supply-chain-management-to-products-in-sales"></a>Synkronisera produkter direkt från Supply Chain Management till produkter i Sales

[!include [banner](../includes/banner.md)]

> [!NOTE]
> Innan du kan använda lösningen Potentiell kund till kontanter ska du bekanta dig med [integrera data i Common Data Service för appar](https://docs.microsoft.com/powerapps/administrator/data-integrator).

Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera produkter direkt från Dynamics 365 Supply Chain Management till Dynamics 365 Sales.

## <a name="data-flow-in-prospect-to-cash"></a>Dataflöden i Potentiell kund till kontanter

Lösningen Potentiell kund till kontanter använder funktionen Dataintegrering för att synkronisera data mellan instanser av Supply Chain Management och Sales. Potentiell kund till kontanter-mallarna med funktionen för dataintegrering möjliggör ett flöde av konto-, produkt-, försäljningskvots-, försäljningsorder- samt försäljningsfakturadata mellan Supply Chain Management och Sales. Följande bild visar hur data synkroniseras mellan Supply Chain Management och Sales.

[![Dataflöden i Potentiell kund till kontanter](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>Mallar och uppgifter

För att gå till tillgängliga mallar, öppna [Power Apps administratörscenter](https://admin.powerapps.com/dataintegration). Välj **projekt** och i det övre högra hörnet väljer du **nytt projekt** för att välja allmänna mallar.

Följande mall och underliggande uppgifter används för att synkronisera produkter från Supply Chain Management till Sales.

- **Namnet på mallen i dataintegrering:** produkter (Supply Chain Management till Sales) - Direkt
- **Namnen på uppgiften i dataintegreringsprojektet:** Produkter

Inga synkroniseringsuppgifter krävs innan synkroniseringen av produkt kan utföras.

## <a name="entity-set"></a>Ange entiteten

| Hantering av underleverantörer    | Försäljning    |
|----------------------------|----------|
| Säljbara frisläppta produkter | Produkter |

## <a name="entity-flow"></a>Flöde för entitet

Produkter hanteras i Supply Chain Management och synkroniseras med Sales. Dataentiteten **Säljbara frisläppta produkter** i Supply Chain Management exporterar endast produkter som är *Säljbara*. Säljbara produkter är produkter som har den information som de behöver för att kunna användas på en försäljningsorder. Samma regler gäller när en produkt kontrolleras med funktionen **Validera** på sidan **frisläppt produkt**.

Produktnumret används som nyckel. Därför när produktvarianter synkroniseras till Sales, har varje produktvarianten ett individuellt produkt-ID.

## <a name="prospect-to-cash-solution-for-sales"></a>Lösningen potentiell kund till kontanter för Sales

I Sales läggs ett nytt fält **hanteras externt** läggs till produkterna för att ange att en viss produkt hanteras externt. Det har värdet är som standrad inställt på **Ja** vid import till Sales. Följande värden finns:

- **Ja** – Produkten kommer från Supply Chain Management och kan inte redigeras i Sales.
- **Nej** – produkten angavs direkt i Sales.
- **(Tom)** – Produkten fanns i Sales innan lösningen Potentiell kund till kontanter aktiverades.

Fältet **Hanteras externt** hjälper till att säkerställa att endast offerter och försäljningsorder med externt hanterade produkter synkroniseras till Supply Chain Management.

Externt underhållna produkter läggs automatiskt till den första giltiga prislistan med samma valuta. Prislistor är sorterade i alfabetisk ordning efter namn. Produktens försäljningspris från Supply Chain Management används som pris i prislista. Därför måste det finnas en prislista i Sales för varje produktförsäljningsvaluta i Supply Chain Management. Valutan för frisläppta säljbara produkter har tilldelats redovisningsvalutan hos den juridiska personen som produkten exporteras från.

> [!NOTE]
> - Produktsynkronisering lyckas inte, såvida det inte finns en prislista som har en matchande valuta.
> - Du kan kontrollera den använda prislistan genom att mappa pricelevelid.name [standardprislista (namn)] i dataintegreringsprojektet. Inmatningen måste vara i gemener. Standardvärdet för en prislista i försäljning med namnet ”Standard” är till exempel: målfält: pricelevelid.name [standardprislista (namn)] och mapptyp: [ { "transformType": "Default", "defaultValue": "standard" } ].

## <a name="preconditions-and-mapping-setup"></a>Ställa in mappning och förutsättningar

- Innan du kör den första synkroniseringen måste du fylla i specifik produkttabell för befintliga produkter i Supply Chain Management. Befintliga produkter kommer inte att synkroniseras förrän jobbet är slutfört.

    1. I Supply Chain Management använder du Sök för att söka efter **Fyll i specifik produkttabell**.
    2. Välj **Fyll i specifik produkttabell** för att köra jobbet. Detta jobb kan endast köras en gång.

- Kontrollera att nödvändig värdemappning för den säljande enheten (UOM) mellan Supply Chain Management och Sales finns i mappningen **Säljenhetssymbol** till **Standardenhet (namn)**.
- Uppdatera värdemappen för **Enhetsgrupp** (**defaultuomscheduleid.name**) så att de matchar **Enhetsgrupper** i Sales.

    Standardmallvärdet är **standardenhet**.

- Se till att säljande UOM:er för alla produkter från Supply Chain Management finns i Sales.
- Se till att prislistor finns i Sales för varje produktförsäljningsvaluta i Supply Chain Management.
- När produkter skapas i Sales kan de ha ststusen **utkast** eller **aktiv**. Beteendet kontrolleras vid **inställningar** > **Administration** > **systeminställningar** > **försäljning** i Sales.

    Produkter som har statusen **utkast** när de skapas måste aktiveras innan de kan läggas till offerter eller försäljningsorder.

## <a name="template-mapping-in-data-integration"></a>Mallmappning i dataintegrering

I följande illustration visas ett exempel på en mallmappning i dataintegrering. 

> [!NOTE]
> Mappningen visar vilken fältinformation som kommer att synkroniseras från Sales till Supply Chain Management.

![Mallmappning i dataintegreraren](./media/products-direct-template-mapping-data-integrator-1.png)


## <a name="related-topics"></a>Relaterade ämnen

[Prospekt till kontanter](prospect-to-cash.md)

[Synkronisera konton direkt från Sales till kunder i Supply Chain Management](accounts-template-mapping-direct.md)

[Synkronisera kontakter direkt från Sales till kontakter i Supply Chain Management](contacts-template-mapping-direct.md)

[Synkronisering av försäljningsorder direkt mellan Sales och Supply Chain Management](sales-order-template-mapping-direct-two-ways.md)

[Synkronisera huvuden och rader i försäljningsfakturor direkt från Supply Chain Management till Sales](sales-invoice-template-mapping-direct.md)



