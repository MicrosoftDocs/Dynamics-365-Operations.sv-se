---
title: Potentiell kund till kontanter
description: Det här avsnittet innehåller en översikt över lösningen potentiell kund till pengar mellan Dynamics 365 Supply Chain Management och Dynamics 365 Sales.
author: ChristianRytt
manager: AnnBe
ms.date: 04/25/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustTable, SalesTable, EcoResProductListPage
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
ms.openlocfilehash: fb5abb983811ce736e3494bc85e8d9b23a2e373c
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/18/2019
ms.locfileid: "2814085"
---
# <a name="prospect-to-cash"></a>Prospekt till kontanter

[!include [banner](../includes/banner.md)]

Lösningen potentiell kund till pengar ger direkt synkronisering mellan Dynamics 365 Supply Chain Management och Dynamics 365 Sales. Potentiell kund till kontanter-mallarna med funktionen för dataintegrering möjliggör ett flöde av konto-, produkt-, försäljningskvots-, försäljningsorder- samt försäljningsfakturadata. Samtidigt som datan flödar kan du genomföra försäljnings- och marknadsföringsaktiviteter i Sales, samt hantera orderutförande genom att utnyttja lagerhantering i Supply Chain Management. 

För mer information om integration av funktionen potentiell kund till kontanter se en kort YouTube-video [Integrering av potentiell kund till pengar](https://www.youtube.com/watch?v=AVV9x5x-XCg).

I den aktuella versionen innehåller lösningen Potentiell kund till pengar följande typer av direktsynkronisering:

- [Synkronisera konton direkt från Sales till kunder i Supply Chain Management](accounts-template-mapping-direct.md)
- [Synkronisera produkter direkt från Supply Chain Management till produkter i Sales](products-template-mapping-direct.md)
- [Synkronisera kontakter direkt från Sales till kontakter i Supply Chain Management](contacts-template-mapping-direct.md)
- [Synkronisera försäljningsoffertrubriker och rader direkt från Sales till Supply Chain Management](sales-quotation-template-mapping-sales-fin.md)
- [Synkronisering av försäljningsorder direkt mellan Sales och Supply Chain Management](sales-order-template-mapping-direct-two-ways.md)
- [Synkronisera huvuden och rader i försäljningsfakturor direkt från Supply Chain Management till Sales](sales-invoice-template-mapping-direct.md)

## <a name="system-requirements-for-supply-chain-management"></a>System krav för hantering av Supply Chain Management
Potentiell kund till kontanter-integrering stöds på följande versioner:

### <a name="microsoft-dynamics-365-for-finance-and-operations-enterprise-edition-73-december-2017"></a>Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3 (december 2017)

- Dynamics 365 for Finance and Operations, Enterprise edition (december 2017) - programversion 7.3.11971.56116 med plattformsuppdatering 12 (7.0.4709.41129)

### <a name="dynamics-365-for-finance-and-operations-enterprise-edition-july-2017"></a>Dynamics 365 for Finance and Operations, Enterprise edition (juli 2017)

- Dynamics 365 for Finance and Operations, Enterprise edition (juli 2017) - med plattformsuppdatering 8 (programversion 7.2.11792.56024 med plattformsuppdatering 7.0.4565.16212).
- Följande snabbkorrigeringar är nödvändiga:

  - **[KB4045570](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4045570&bugId=3851320&qc=ac1145034fd04ab71ccc4d14aa012f245176712c9af7c36bb77a118726d46160)** – Denna snabbkorrigering möjliggör synkronisering av försäljningsorder med funktionen för dataintegrering mellan Sales och Supply Chain Management. Den innehåller även flera förbättringar.
  - **[KB4036524](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036524&bugId=3847504&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** – Denna snabbkorrigering möjliggör synkronisering av försäljningsorderrad med funktionen för dataintegrering mellan Supply Chain Management och Sales.
  - **[KB4036461](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036461&bugId=3847029&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** – Denna snabbkorrigering möjliggör synkronisering av försäljningsorder med funktionen för dataintegrering mellan Supply Chain Management och Sales.

    > [!NOTE]
    > Du måste bara installera KB4045570 eftersom installationen inkluderar ändringarna från andra snabbkorrigeringar. 

### <a name="dynamics-365-for-finance-and-operations-version-1611-november-2016"></a>Dynamics 365 for Finance and Operations version 1611 (november 2016)

- Dynamics 365 for Finance and Operations version 1611 (november 2016) med plattformsuppdatering 8 eller högre

- Följande snabbkorrigeringar är nödvändiga:

  - **[KB4051266](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4051266&bugId=3863566&qc=ee80faaa7bc6c77b368d5eaf456c9c08e0b9fba5903a7b6fd8c13756c3a4b757)** -Aktivera synkronisering av försäljningsorder med Data integrator mellan Supply Chain Management och Sales. 
  - **[KB4037542](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4037542&bugId=3848253&qc=8323b93c15280172c5ab4159e0256e37104ced1729462c91ab2f7d00cb8d419c)** -Aktivera synkronisering av försäljningsorderrubriken med Data integrator mellan Supply Chain Management och Sales.
  - **[KB4033093](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4033093&bugId=3824604&qc=bd7e15e1fb56066b3a82ce48b691cf1ffbc934a7473fa888545b2211a8d416c5)** - Stöd för Potentiell kund till pengar-integrering via datatabeller krävs.
    
    > [!NOTE]
    > Du måste initiera följande batchjobb från formuläret **SalesPopulateProspectToCash** när du har installerat snabbkorrigeringarna. Detta formulär är dolt eftersom du bara behöver det en gång. För att komma åt formuläret loggar du in och lägger till följande i din webbläsaradress: *&mi=action:SalesPopulateProspectToCash*, t.ex., `https://ax123456.cloud.test.dynamics.com/?cmp=USMF&mi=action:SalesPopulateProspectToCash`. När formuläret öppnas klickar du på OK. Då fylls ett nytt fält för **LineCreationSequnceNumber** i tabellerna **SalesLine**, **SalesQuotationLine** och **CustInvoiceTrans** med unika värden och produktraden uppdateras. Detta är nödvändigt för att integrationen Potentiell kund till kontanter ska fungera.


## <a name="system-requirements-for-sales"></a>Systemkrav för Sales

Om du vill använda lösningen Potentiell kund till kontanter måste du installera följande komponenter:

- Dynamics 365 Sales, version 1612 (8.2.1.207) (DB 8.2.1.207) online eller en senare version.
- Lösningen Potentiell kund till kontanter för Dynamics 365 Sales, version 1.15.0.0 eller senare. Lösningen finns att hämta från AppSource. [Hämta Dynamics 365, potentiell kund till kontanter](https://appsource.microsoft.com/product/dynamics-365/mscrm.c7a48b40-eed3-4d67-93ba-f2364281feb3).
