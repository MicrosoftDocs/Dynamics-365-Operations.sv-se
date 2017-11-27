---
title: Potentiell kund till kontanter
description: "Detta avsnitt ger en översikt över lösningen Potentiell kund till kontanter mellan Dynamics 365 for Finance and Operations, Enterprise edition och Dynamics 365 for Sales."
author: ChristianRytt
manager: AnnBe
ms.date: 10/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 674d2e1f2c5cdbccf43618a9083ca01abed0735a
ms.openlocfilehash: 2accf77c5241adff7ad1648737dde451153fde46
ms.contentlocale: sv-se
ms.lasthandoff: 11/14/2017

---

# <a name="prospect-to-cash"></a>Potentiell kund till kontanter  

[!include[banner](../includes/banner.md)]

Lösningen Potentiell kund till kontanter använder [Dataintegrering](/common-data-service/entity-reference/dynamics-365-integration) för att synkronisera data över både Microsoft Dynamics 365 for Finance and Operations, Enterprise edition- och Dynamics 365 for Sales-instanser via Common Data Service (CDS). Potentiell kund till kontanter-mallarna med funktionen för dataintegrering möjliggör ett flöde av konto-, produkt-, försäljningskvots-, försäljningsorder- samt försäljningsfakturadata mellan Finance and Operations och Sales. Samtidigt som datan flödar mellan Finance and Operations och Sales kan du genomföra försäljnings- och marknadsföringsaktiviteter i Sales, samt hantera orderutförande och lagerhantering i Finance and Operations. 

Den här lösningen ger integration i följande områden: 

-   [Underhåll konton i Sales och synkronisera dem med Finance and Operations](accounts-template-mapping.md)
-   [Underhåll kontakter i Sales och synkronisera dem med Finance and Operations](contacts-template-mapping.md)
-   [Underhåll produkter i Finance and Operations och synkronisera dem med Sales](products-template-mapping.md)
-   [Skapa försäljningskvoter i Sales och synkronisera dem med Finance and Operations](sales-quotation-template-mapping.md)
-   [Skapa försäljningsorder i Finance and Operations och synkronisera dem med Sales](sales-order-template-mapping.md)
-   [Skapa försäljningsfakturor i Finance and Operations och synkronisera dem med Sales](sales-invoice-template-mapping.md)

Den här lösningen ger direkt synkronisering i följande områden:

-   [Underhåll konton i Sales och synkronisera dem direkt från Finance and Operations](accounts-template-mapping-direct.md)
-   [Underhåll produkter i Finance and Operations och synkronisera dem direkt med Sales](products-template-mapping-direct.md)
-   [Behåll kontakter i Sales och synkronisera dem direkt till kontakter i Finance and Operations](contacts-template-mapping-direct.md)
-   [Synkronisera huvuden och rader i försäljningsofferter direkt från Sales till Finance and Operations](sales-quotation-template-mapping-sales-fin.md)
-   [Skapa försäljningsorder i Finance and Operations och synkronisera dem direkt med Sales](sales-order-template-mapping-direct.md)
-  [Synkronisera huvuden och rader i försäljningsorder direkt mellan Sales och Finance and Operations](sales-order-template-mapping-between-sales-fin.md)
-   [Synkronisera försäljningsorder direkt mellan Sales och Finance and Operations](sales-order-template-mapping-direct-two-ways.md)
-   [Skapa försäljningsfakturor i Finance and Operations och synkronisera dem direkt med Sales](sales-invoice-template-mapping-direct.md)


## <a name="system-requirements-for-dynamics-365-for-finance-and-operations-enterprise-edition"></a>Systemkrav för Dynamics 365 for Finance and Operations, Enterprise edition

Om du vill använda lösningen Potentiell kund till kontanter måste du installera följande:

- Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (juli 2017) med plattformsuppdatering 8 (app 7.2.11792.56024 med plattform 7.0.4565.16212)

- Snabbkorrigeringar för Dynamics 365 for Finance and Operations, Enterprise edition (juli 2017).
        
    -  [KB4045570](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4045570&bugId=3851320&qc=ac1145034fd04ab71ccc4d14aa012f245176712c9af7c36bb77a118726d46160) - denna snabbkorrigering ger stöd för synkronisering av försäljningsorder med dataintegrering från Sales till Finance and Operations tillsammans med många andra förbättringar.

    -  [KB4036524](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036524&bugId=3847504&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2) - Denna snabbkorrigering möjliggör radsynkronisering av försäljningsorder med funktionen för dataintegrering mellan Finance and Operations och Sales.
        
    -  [KB4036461](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036461&bugId=3847029&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2) - Denna snabbkorrigering möjliggör radsynkronisering av försäljningsorder med funktionen för dataintegrering mellan Finance and Operations och Sales.

**Obs**: Eftersom installationen inkluderar ändringarna från andra KB behöver du bara installera KB4045570 .
 
## <a name="system-requirements-for-dynamics-365-for-sales"></a>Systemkrav för Dynamics 365 for Sales

Om du vill använda lösningen Potentiell kund till kontanter måste du installera följande:

- Dynamics 365 for Sales, version 1612 (8.2.1.207) (DB 8.2.1.207) online.
- Lösningen Potentiell kund till kontanter för Dynamics 365 for Sales, version 1.14.0.0 (v14) eller senare.

### <a name="install-the-prospect-to-cash-solution-for-sales"></a>Installera Potentiell kund till kontanter-lösningen för Sales

- Hämta [Lösningspaketet Potentiell kund till kontanter för Dynamics 365 for Sales (zip-fil)](https://mbs.microsoft.com/customersource/Global/365Enterprise/downloads/product-releases/MD365FNOPENTProspectToCash) på CustomerSource.

- Se till att zip-filen inte blockeras och då genererar felmeddelandet "Inga importpaket hittades" när du installerar lösningspaketet. Gör följande för att avblockera filen:

    -  Högerklicka zip-filen.
    -  Välj **Egenskaper** och sedan **Avblockera**. 

- Packa upp och kör PackageDeployer.exe.

- Installera lösningen Potentiell kund till kontanter i din Sales-instans.

    - Välj distributionstypen **Office 365**.
    - Välj **Visa avancerade**.
    - Välj en **Region** för att köra en snabbinstallation. Om du väljer **Vet inte** kommer systemet att söka efter samtliga regioner, och installationen kommer att ta längre tid.
    - Ange **Användarnamn** och **Lösenord** för en administratörsanvändare som innehar användarbehörighet att installera.

