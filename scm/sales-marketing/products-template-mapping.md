---
title: "Synkronisera produkter från Finance and Operations till produkter i Sales"
description: "Det här avsnittet beskriver vilka mallar och underliggande uppgifter som används för att synkronisera från Microsoft Dynamics 365 for Finance and Operations, Enterprise edition till Microsoft Dynamics 365 for Sales."
author: ChristianRytt
manager: AnnBe
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: ChristianRytt
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 2f14b06b57930256f9211f2085512aa589df083e
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---

# <a name="synchronize-products-from-finance-and-operations-to-products-in-sales"></a>Synkronisera produkter från Finance and Operations till produkter i Sales

[!include[banner](../includes/banner.md)]

> [!NOTE]
> Innan du kan använda lösningen potentiell kund till kontanter ska du bekanta dig med [Dynamics 365 dataintegrering](https://docs.microsoft.com/en-us/common-data-service/entity-reference/dynamics-365-integration). 

Det här avsnittet beskriver vilka mallar och underliggande uppgifter som används för att synkronisera från Microsoft Dynamics 365 for Finance and Operations, Enterprise edition till Microsoft Dynamics 365 for Sales.

## <a name="template-and-task"></a>Mall och uppgift

Följande mallar och underliggande uppgifter som används för att synkronisera från Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (Finance and Operations) till Microsoft Dynamics 365 for Sales (Sales).

-   Mallens namn: produkter (Fin and Ops till Sales)

-   Namn på uppgiften projekt: produkter

Synkronisering av uppgifter krävs innan synkronisering av produkt: ingen

## <a name="entity-set"></a>Ange entiteten

| **Finance and Operations** | **CDS** | **Försäljning**  |
|----------------------------|---------|------------|
| Säljbara frisläppta produkter | Produkt | Produkter   |

## <a name="entity-flow"></a>Flöde för entitet

Produkter hanteras i Finance and Operations och synkroniseras i Sales. Dataentiteten **Säljbara frisläppta produkter** i Finance and Operations exporterar endast produkter som är säljbara, vilket innebär att produkterna har nödvändig information för att användas på en försäljningsorder. Samma regler gäller när en produkt kontrolleras med funktionen **Validera** på sidan **frisläppt produkt**.

**Produktnummer** används som nyckel, vilket innebär att produktvarianter synkroniseras till CDS och Sales med enskilda **produkt-ID-nummer** per **produktvariant**.

## <a name="prospect-to-cash-solution-for-sales"></a>Lösningen potentiell kund till kontanter för Sales

I Sales läggs ett nytt fält **hanteras externt** läggs till produkterna för att ange att en viss produkt hanteras externt. Det har värdet **Ja** som standard vid import till Sales.

-   **Hanteras externt = Ja**: produkten härrör från Finance and Operations och kan inte redigeras i Sales.

-   **Hanteras externt = Nej**: produkten anges direkt i Sales.

-   **Hanteras externt = tom**: produkten finns i Sales innan du aktiverar den potentiella kunden till kontantlösning.

Informationen **hanteras externt** används för att säkerställa att endast **offerter** och **försäljningsorder** med **externt hanterade produkter** synkroniseras till Finance and Operations.

**Externt underhållna produkter** läggs automatiskt till den första giltiga **prislistan** med samma valuta. Observera att listan är i alfabetisk ordning efter **namn**. Produktens försäljningspris från Finance and Operations används som pris i **prislista**. Detta innebär att den måste ha en **prislista** i Sales för varje **produktförsäljningsvaluta** i Finance and Operations. Valuta för frisläppta säljbara produkter har tilldelats redovisningsvalutan hos den juridiska personen som produkten exporteras från.

> [!NOTE]
> Produktsynkronisering kommer inte att fungera utan en **prislista** med matchande valuta.

## <a name="preconditions-and-mapping-setup"></a>Ställa in mappning och förutsättningar

-   Innan du kör den första synkroniseringen måste du fylla i **specifik produkttabell** för befintliga produkter i Finance and Operations. Befintliga produkter kommer inte att synkroniseras förrän jobbet är slutfört.

    -   I Finance and Operations använder du Sök för att söka efter **Fyll i specifik produkttabell**.

    -   Klicka på **Fyll i specifik produkttabell** för att köra jobbet. Det här jobbet behöver bara köras en gång.

-   Försäkra sig om att den nödvändiga **ValueMap** för försäljningens **måttenhet** (UOM) i Finance and Operations finns i **källa -\> CDS-mappning SalesUnitSymbol / DefaultSellingUnitOfMeasure**.

-   Se till att **decimaler som stöds** för UOM matchar dina krav i **CDS -\> Destination**. Om du vill ha olika värden per UOM kan detta göras med **ValueMap** från enhet, till exempel [varje: 0] & [pund: 2].

    -   Mallvärdet är som standard 0.

-   Uppdatera **CDS organisations-ID Organization_OrganizationId** i **källa -\> CDS**.

    -   Mallvärdet är som standard ORG001.

-   Uppdatera **ValueMap** för **enhetsgrupp** (**defaultuomscheduleid.name**) i **CDS -\> Destination** så att de matchar **enhetsgrupper** i Sales.

    -   Mallvärdet är som standard **standardenhet**.

-   Se till att alla produkter som säljer UOM:er från Finance and Operations finns i Sales med värdet **CDS-plocklistor**.

-   Se till att **prislistor** finns i Sales för varje produktförsäljningsvaluta i Finance and Operations.

-   Produkter kan skapas i Sales med status **utkast** eller **aktiv**. Detta styrs i **systeminställningar** under **försäljning** i Sales.

    -   Produkter som skapats med utkaststatus måste aktiveras innan de kan läggas till i **offert** eller **försäljningsorder**.

## <a name="template-mapping-in-data-integrator"></a>Mallmappning i dataintegratör

I följande illustrationer visas ett exempel på en mallmappning i dataintegratör.

![mallmappning i dataintegratör](./media/products-template-mapping-data-integrator-1.png)

![mallmappning för produkter i dataintegratör](./media/products-template-mapping-data-integrator-2.png)

## <a name="related-topics"></a>Relaterade ämnen

[Synkronisera konton från Sales till kunder i Finance and Operations](accounts-template-mapping.md)

[Synkronisera kontakter från Sales till kontakter i Finance and Operations](contacts-template-mapping.md)

[Synkronisera huvuden och rader i försäljningsofferter från Sales till Finance and Operations](sales-quotation-template-mapping.md)


