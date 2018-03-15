---
title: Potentiell kund till kontanter
description: "Detta avsnitt ger en översikt över lösningen Potentiell kund till pengar mellan Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition och Microsoft Dynamics 365 for Sales."
author: ChristianRytt
manager: AnnBe
ms.date: 02/08/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustTable, SalesTable, EcoResProductListPage
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 95d5bf26c22238753586cf4a7aaf5c26f061a705
ms.openlocfilehash: 62f328c5a6bf5343c97de0b7d907bbcfe2fcde4d
ms.contentlocale: sv-se
ms.lasthandoff: 02/23/2018

---

# <a name="prospect-to-cash"></a>Potentiell kund till kontanter

[!include[banner](../includes/banner.md)]

Denna Potentiell kund till pengar-lösning erbjuder direktsynkronisering mellan Dynamics 365 for Finance and Operations, Enterprise Edition och Dynamics 365 for Sales. Potentiell kund till pengar-mallarna med funktion för dataintegrering möjliggör ett dataflöde för konton, produkter, kontakter, produkter, försäljningskvoter, försäljningsorder samt försäljningsfakturor Finance and Operations och Sales. Samtidigt som datan flödar mellan Finance and Operations och Sales kan du genomföra försäljnings- och marknadsföringsaktiviteter i Sales, samt hantera orderutförande genom att utnyttja lagerhantering i Finance and Operations. 

Mer information om integration av funktionen potentiell kund till kontanter se en kort YouTube-video:

> [!Video https://www.youtube.com/embed/AVV9x5x-XCg]

I den aktuella versionen innehåller lösningen Potentiell kund till pengar följande typer av direktsynkronisering:

- [Underhåll konton i Sales och synkronisera dem direkt från Finance and Operations](accounts-template-mapping-direct.md)
- [Underhåll produkter i Finance and Operations och synkronisera dem direkt med Sales](products-template-mapping-direct.md)
- [Behåll kontakter i Sales och synkronisera dem direkt till kontakter i Finance and Operations](contacts-template-mapping-direct.md)
- [Synkronisera försäljningsofferter direkt från Sales till Finance and Operations (mall väntar på release)](sales-quotation-template-mapping-sales-fin.md)
- [Synkronisera försäljningsorder direkt från Finance and Operations till Sales](sales-order-template-mapping-direct.md)
- [Synkronisera försäljningsorder direkt mellan Sales och Finance and Operations (mall väntar på release)](sales-order-template-mapping-direct-two-ways.md)
- [Synkronisera försäljningsfakturor direkt från Finance and Operations till Sales](sales-invoice-template-mapping-direct.md)

## <a name="system-requirements-for-finance-and-operations"></a>Systemkrav för Finance and Operations

Potentiell kund till kontanter-integrering stöds på följande versioner:

### <a name="microsoft-dynamics-365-for-finance-and-operations-enterprise-edition-73-december-2017"></a>Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition 7.3 (December 2017)

- Dynamics 365 for Finance and Operations, Enterprise Edition (December 2017) - Application build 7.3.11971.56116 med med plattformsuppdatering 12 (7.0.4709.41129)

### <a name="dynamics-365-for-finance-and-operations-enterprise-edition-july-2017"></a>Dynamics 365 for Finance and Operations, Enterprise Edition (juli 2017)

- Dynamics 365 for Finance and Operations, Enterprise Edition (July 2017) - med plattformsuppdatering 8 (programversion 7.2.11792.56024 med plattform 7.0.4565.16212).
- Följande snabbkorrigeringar är nödvändiga:

    - **[KB4045570](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4045570&bugId=3851320&qc=ac1145034fd04ab71ccc4d14aa012f245176712c9af7c36bb77a118726d46160)** – Denna snabbkorrigering möjliggör synkronisering av försäljningsorder med funktionen för dataintegrering mellan Finance and Operations och Sales. Den innehåller även flera förbättringar.
    - **[KB4036524](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036524&bugId=3847504&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** – Denna snabbkorrigering möjliggör synkronisering av försäljningsorderrader med funktionen för dataintegrering mellan Finance and Operations och Sales.
    - **[KB4036461](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036461&bugId=3847029&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** – Denna snabbkorrigering möjliggör synkronisering av försäljningsorder med funktionen för dataintegrering mellan Finance and Operations och Sales.

    > [!NOTE]
    > Du måste bara installera KB4045570 eftersom installationen inkluderar ändringarna från andra snabbkorrigeringar. 

### <a name="dynamics-365-for-finance-and-operations-version-1611-november-2016"></a>Dynamics 365 for Finance and Operations version 1611 (november 2016)

- Dynamics 365 for Finance and Operations version 1611 (november 2016) med plattformsuppdatering 8 eller senare

- Följande snabbkorrigeringar är nödvändiga:

    - **[KB4051266](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4051266&bugId=3863566&qc=ee80faaa7bc6c77b368d5eaf456c9c08e0b9fba5903a7b6fd8c13756c3a4b757)** -Aktivera synkronisering av försäljningsorder med Data integrator från Finance and Operations och Sales. 
    - **[KB4037542](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4037542&bugId=3848253&qc=8323b93c15280172c5ab4159e0256e37104ced1729462c91ab2f7d00cb8d419c)** - Aktivera synkronisering av försäljningsorderrubriken och raden med Data integrator från Finance and Operations och Sales.
    - **[KB4033093](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4033093&bugId=3824604&qc=bd7e15e1fb56066b3a82ce48b691cf1ffbc934a7473fa888545b2211a8d416c5)** - Stöd för Potentiell kund till pengar-integrering via datatabeller krävs.
    
    > [!NOTE]
    > Du måste initiera följande batchjobb från formuläret **SalesPopulateProspectToCash** när du har installerat snabbkorrigeringarna. Detta formulär är dolt eftersom du bara behöver det en gång. För att komma åt formuläret loggar du in och lägger till följande i din webbläsaradress : & mi = åtgärd: SalesPopulateProspectToCash, t.ex `https://ax123456.cloud.test.dynamics.com/?cmp=USMF&mi=action:SalesPopulateProspectToCash`. När formuläret öppnas klickar du på OK. Då fylls ett nytt fält för **LineCreationSequnceNumber** i tabellerna **SalesLine**, **SalesQuotationLine** och **CustInvoiceTrans** med unika värden och produktraden uppdateras. Detta är nödvändigt för att integrationen Potentiell kund till kontanter ska fungera.


## <a name="system-requirements-for-sales"></a>Systemkrav för Sales

Om du vill använda lösningen Potentiell kund till kontanter måste du installera följande komponenter:

- Dynamics 365 for Sales, version 1612 (8.2.1.207) (DB 8.2.1.207) online
- Lösningen Potentiell kund till pengar för Dynamics 365 for Sales, version 1.15.0.0 (v15) 

### <a name="install-the-prospect-to-cash-solution-for-sales"></a>Installera Potentiell kund till kontanter-lösningen för Sales

1. Hämta [Lösningspaketet Potentiell kund till kontanter för Dynamics 365 for Sales (zip-fil)](https://mbs.microsoft.com/customersource/Global/365Enterprise/downloads/product-releases/MD365FNOPENTProspectToCash) från CustomerSource.
2. Se till att zip-filen inte blockeras. I annat fall kommer du att få följande felmeddelande när du försöker installera lösningspaketet: ”Inget importpaket hittades”. För att avblockera zip-filen, högerklicka på filen och välj **Egenskaper**. Välj **Avblockera**.
3. Packa upp och kör **PackageDeployer.exe**.
4. Installera lösningen Potentiell kund till pengar i din Sales-instans:

    1. Välj **Office 365** som implementeringstyp.
    2. Välj **Visa avancerade**.
    3. Välj en region för att köra en snabbinstallation. Om du väljer **Vet inte** kommer systemet att söka efter samtliga regioner, och installationen kommer att ta längre tid.
    4. Ange användarnamn och lösenord för en administratörsanvändare med installationsbehörighet.



