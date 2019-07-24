---
title: Synkronisera produkter direkt från Finance and Operations till produkter i Sales
description: Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera produkter från Microsoft Dynamics 365 for Finance and Operations till Microsoft Dynamics 365 for Sales.
author: ChristianRytt
manager: AnnBe
ms.date: 06/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: ff284585a2eb4c5cf55d2e3a3e0f317d1fb218bb
ms.sourcegitcommit: 51dc11919fcb2324482b48cc4ce4484945ade803
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/10/2019
ms.locfileid: "1624345"
---
# <a name="synchronize-products-directly-from-finance-and-operations-to-products-in-sales"></a>Synkronisera produkter direkt från Finance and Operations till produkter i Sales

[!include [banner](../includes/banner.md)]

> [!NOTE]
> Innan du kan använda lösningen Potentiell kund till kontanter ska du bekanta dig med [integrera data i Common Data Service för appar](https://docs.microsoft.com/en-us/powerapps/administrator/data-integrator).

Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera produkter direkt från Microsoft Dynamics 365 for Finance and Operations till Microsoft Dynamics 365 for Sales.

## <a name="data-flow-in-prospect-to-cash"></a>Dataflöden i Potentiell kund till kontanter

Lösningen Potentiell kund till kontanter använder funktionen Dataintegrering för att synkronisera data mellan instanser av Finance and Operations och Sales. Potentiell kund till kontanter-mallarna med funktionen för dataintegrering möjliggör ett flöde av konto-, produkt-, försäljningskvots-, försäljningsorder- samt försäljningsfakturadata mellan Finance and Operations och Sales. Följande bild visar hur data synkroniseras mellan Finance and Operations och Sales.

[![Dataflöden i Potentiell kund till kontanter](./media/prospect-to-cash-data-flow.png)](./media/prospect-to-cash-data-flow.png)

## <a name="templates-and-tasks"></a>Mallar och uppgifter

För att gå till tillgängliga mallar, öppna [PowerApps administratörscenter](https://admin.powerapps.com/dataintegration). Välj **projekt** och i det övre högra hörnet väljer du **nytt projekt** för att välja allmänna mallar.

Följande mall och underliggande uppgifter används för att synkronisera produkter från Finance and Operations till Sales.

- **Namnet på mallen i dataintegrering:** produkter (Fin and Ops to Sales) - Direkt
- **Namnen på uppgiften i dataintegreringsprojektet:** Produkter

Inga synkroniseringsuppgifter krävs innan synkroniseringen av produkt kan utföras.

## <a name="entity-set"></a>Ange entiteten

| Finance and Operations     | Försäljning    |
|----------------------------|----------|
| Säljbara frisläppta produkter | Produkter |

## <a name="entity-flow"></a>Flöde för entitet

Produkter hanteras i Finance and Operations och synkroniseras i Sales. Dataentiteten **Säljbara frisläppta produkter** i Finance and Operations exporterar endast produkter som är *Säljbara*. Säljbara produkter är produkter som har den information som de behöver för att kunna användas på en försäljningsorder. Samma regler gäller när en produkt kontrolleras med funktionen **Validera** på sidan **frisläppt produkt**.

Produktnumret används som nyckel. Därför när produktvarianter synkroniseras till Sales, har varje produktvarianten ett individuellt produkt-ID.

## <a name="prospect-to-cash-solution-for-sales"></a>Lösningen potentiell kund till kontanter för Sales

I Sales läggs ett nytt fält **hanteras externt** läggs till produkterna för att ange att en viss produkt hanteras externt. Det har värdet är som standrad inställt på **Ja** vid import till Sales. Följande värden finns:

- **Ja** – produkten kommer från Finance and Operations och kan inte redigeras i Sales.
- **Nej** – produkten angavs direkt i Sales.
- **(Tom)** – Produkten fanns i Sales innan lösningen Potentiell kund till kontanter aktiverades.

Fältet **Hanteras externt** hjälper till att säkerställa att endast offerter och försäljningsorder med externt hanterade produkter synkroniseras till Finance and Operations.

Externt underhållna produkter läggs automatiskt till den första giltiga prislistan med samma valuta. Prislistor är sorterade i alfabetisk ordning efter namn. Produktens försäljningspris från Finance and Operations används som pris i prislista. Därför måste det finnas en prislista i Sales för varje produktförsäljningsvaluta i Finance and Operations. Valutan för frisläppta säljbara produkter har tilldelats redovisningsvalutan hos den juridiska personen som produkten exporteras från.

> [!NOTE]
> - Produktsynkronisering lyckas inte, såvida det inte finns en prislista som har en matchande valuta.
> - Du kan kontrollera den använda prislistan genom att mappa pricelevelid.name [standardprislista (namn)] i dataintegreringsprojektet. Inmatningen måste vara i gemener. Standardvärdet för en prislista i försäljning med namnet ”Standard” är till exempel: målfält: pricelevelid.name [standardprislista (namn)] och mapptyp: [ { "transformType": "Default", "defaultValue": "standard" } ].

## <a name="preconditions-and-mapping-setup"></a>Ställa in mappning och förutsättningar

- Innan du kör den första synkroniseringen måste du fylla i specifik produkttabell för befintliga produkter i Finance and Operations. Befintliga produkter kommer inte att synkroniseras förrän jobbet är slutfört.

    1. I Finance and Operations använder du Sök för att söka efter **Fyll i specifik produkttabell**.
    2. Välj **Fyll i specifik produkttabell** för att köra jobbet. Detta jobb kan endast köras en gång.

- Kontrollera att nödvändig värdemappning för den säljande enheten (UOM) mellan Finance and Operations och Sales finns i mappningen **Säljenhetssymbol** till **Standardenhet (namn)**.
- Uppdatera värdemappen för **Enhetsgrupp** (**defaultuomscheduleid.name**) så att de matchar **Enhetsgrupper** i Sales.

    Standardmallvärdet är **standardenhet**.

- Se till att säljande UOM:er för alla produkter från Finance and Operations finns i Sales.
- Se till att prislistor finns i Sales för varje produktförsäljningsvaluta i Finance and Operations.
- När produkter skapas i Sales kan de ha ststusen **utkast** eller **aktiv**. Beteendet kontrolleras vid **inställningar** > **Administration** > **systeminställningar** > **försäljning** i Sales.

    Produkter som har statusen **utkast** när de skapas måste aktiveras innan de kan läggas till offerter eller försäljningsorder.

## <a name="template-mapping-in-data-integration"></a>Mallmappning i dataintegrering

I följande illustration visas ett exempel på en mallmappning i dataintegrering. 

> [!NOTE]
> Mappningen visar vilken fältinformation som kommer att synkroniseras från Sales till Finance and Operations.

![Mallmappning i dataintegreraren](./media/products-direct-template-mapping-data-integrator-1.png)


## <a name="related-topics"></a>Relaterade ämnen

[Potentiell kund till kontanter](prospect-to-cash.md)

[Synkronisera konton direkt från Sales till kunder i Finance and Operations](accounts-template-mapping-direct.md)

[Synkronisera kontakter direkt från Sales till kontakter i Finance and Operations](contacts-template-mapping-direct.md)

[Synkronisera huvuden och rader i försäljningsorder direkt från Finance and Operations till Sales](sales-order-template-mapping-direct-two-ways.md)

[Synkronisera huvuden och rader i försäljningsfakturor direkt från Finance and Operations till Sales](sales-invoice-template-mapping-direct.md)



