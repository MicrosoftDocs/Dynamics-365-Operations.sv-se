---
title: Potentiell kund till kontanter
description: Det här avsnittet innehåller en översikt över lösningen potentiell kund till pengar mellan Dynamics 365 Supply Chain Management och Dynamics 365 Sales.
author: ChristianRytt
manager: tfehr
ms.date: 04/25/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustTable, SalesTable, EcoResProductListPage
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
ms.openlocfilehash: 55c39fac40498488519fcb539b3c3f7560a46b30
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437596"
---
# <a name="prospect-to-cash"></a><span data-ttu-id="65dde-103">Prospekt till kontanter</span><span class="sxs-lookup"><span data-stu-id="65dde-103">Prospect to cash</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="65dde-104">Lösningen potentiell kund till pengar ger direkt synkronisering mellan Dynamics 365 Supply Chain Management och Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="65dde-104">The Prospect to cash solution provides direct synchronization across Dynamics 365 Supply Chain Management and Dynamics 365 Sales.</span></span> <span data-ttu-id="65dde-105">Potentiell kund till kontanter-mallarna med funktionen för dataintegrering möjliggör ett flöde av konto-, produkt-, försäljningskvots-, försäljningsorder- samt försäljningsfakturadata.</span><span class="sxs-lookup"><span data-stu-id="65dde-105">The Prospect to cash templates that are available with the Data Integration feature enable the flow of data for accounts, contacts, products, sales quotations, sales orders, and sales invoices.</span></span> <span data-ttu-id="65dde-106">Samtidigt som datan flödar kan du genomföra försäljnings- och marknadsföringsaktiviteter i Sales, samt hantera orderutförande genom att utnyttja lagerhantering i Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="65dde-106">While data is flowing, you can perform sales and marketing activities in Sales, and you can handle order fulfillment by using inventory management in Supply Chain Management.</span></span> 

<span data-ttu-id="65dde-107">För mer information om integration av funktionen potentiell kund till kontanter se en kort YouTube-video [Integrering av potentiell kund till pengar](https://www.youtube.com/watch?v=AVV9x5x-XCg).</span><span class="sxs-lookup"><span data-stu-id="65dde-107">For more information about the Prospect to cash integration, watch the short YouTube video [Prospect to cash integration](https://www.youtube.com/watch?v=AVV9x5x-XCg).</span></span>

<span data-ttu-id="65dde-108">I den aktuella versionen innehåller lösningen Potentiell kund till pengar följande typer av direktsynkronisering:</span><span class="sxs-lookup"><span data-stu-id="65dde-108">In the current version, the Prospect to cash solution provides the following types of direct synchronization:</span></span>

- [<span data-ttu-id="65dde-109">Synkronisera konton direkt från Sales till kunder i Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="65dde-109">Synchronize accounts directly from Sales to customers in Supply Chain Management</span></span>](accounts-template-mapping-direct.md)
- [<span data-ttu-id="65dde-110">Synkronisera produkter direkt från Supply Chain Management till produkter i Sales</span><span class="sxs-lookup"><span data-stu-id="65dde-110">Synchronize products directly from Supply Chain Management to products in Sales</span></span>](products-template-mapping-direct.md)
- [<span data-ttu-id="65dde-111">Synkronisera kontakter direkt från Sales till kontakter i Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="65dde-111">Synchronize contacts directly from Sales to contacts or customers in Supply Chain Management</span></span>](contacts-template-mapping-direct.md)
- [<span data-ttu-id="65dde-112">Synkronisera försäljningsoffertrubriker och rader direkt från Sales till Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="65dde-112">Synchronize sales quotation headers and lines directly from Sales to Supply Chain Management</span></span>](sales-quotation-template-mapping-sales-fin.md)
- [<span data-ttu-id="65dde-113">Synkronisering av försäljningsorder direkt mellan Sales och Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="65dde-113">Synchronization of sales orders directly between Sales and Supply Chain Management</span></span>](sales-order-template-mapping-direct-two-ways.md)
- [<span data-ttu-id="65dde-114">Synkronisera huvuden och rader i försäljningsfakturor direkt från Supply Chain Management till Sales</span><span class="sxs-lookup"><span data-stu-id="65dde-114">Synchronize sales invoice headers and lines directly from Supply Chain Management to Sales</span></span>](sales-invoice-template-mapping-direct.md)

## <a name="system-requirements-for-supply-chain-management"></a><span data-ttu-id="65dde-115">System krav för hantering av Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="65dde-115">System requirements for Supply Chain Management</span></span>
<span data-ttu-id="65dde-116">Potentiell kund till kontanter-integrering stöds på följande versioner:</span><span class="sxs-lookup"><span data-stu-id="65dde-116">Prospect to cash integration is supported on the following versions:</span></span>

### <a name="microsoft-dynamics-365-for-finance-and-operations-enterprise-edition-73-december-2017"></a><span data-ttu-id="65dde-117">Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3 (december 2017)</span><span class="sxs-lookup"><span data-stu-id="65dde-117">Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3 (December 2017)</span></span>

- <span data-ttu-id="65dde-118">Dynamics 365 for Finance and Operations, Enterprise edition (december 2017) - programversion 7.3.11971.56116 med plattformsuppdatering 12 (7.0.4709.41129)</span><span class="sxs-lookup"><span data-stu-id="65dde-118">Dynamics 365 for Finance and Operations, Enterprise edition (December 2017) - Application build 7.3.11971.56116 with Platform Update 12 (7.0.4709.41129)</span></span>

### <a name="dynamics-365-for-finance-and-operations-enterprise-edition-july-2017"></a><span data-ttu-id="65dde-119">Dynamics 365 for Finance and Operations, Enterprise edition (juli 2017)</span><span class="sxs-lookup"><span data-stu-id="65dde-119">Dynamics 365 for Finance and Operations, Enterprise edition (July 2017)</span></span>

- <span data-ttu-id="65dde-120">Dynamics 365 for Finance and Operations, Enterprise edition (juli 2017) - med plattformsuppdatering 8 (programversion 7.2.11792.56024 med plattformsuppdatering 7.0.4565.16212).</span><span class="sxs-lookup"><span data-stu-id="65dde-120">Dynamics 365 for Finance and Operations, Enterprise edition (July 2017) - with platform update 8 (application build 7.2.11792.56024 with platform build 7.0.4565.16212).</span></span>
- <span data-ttu-id="65dde-121">Följande snabbkorrigeringar är nödvändiga:</span><span class="sxs-lookup"><span data-stu-id="65dde-121">The following hotfixes are required:</span></span>

  - <span data-ttu-id="65dde-122">**[KB4045570](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4045570&bugId=3851320&qc=ac1145034fd04ab71ccc4d14aa012f245176712c9af7c36bb77a118726d46160)** – Denna snabbkorrigering möjliggör synkronisering av försäljningsorder med funktionen för dataintegrering mellan Sales och Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="65dde-122">**[KB4045570](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4045570&bugId=3851320&qc=ac1145034fd04ab71ccc4d14aa012f245176712c9af7c36bb77a118726d46160)** – This hotfix enables sales order synchronization from Sales to Supply Chain Management via the Data Integration feature.</span></span> <span data-ttu-id="65dde-123">Den innehåller även flera förbättringar.</span><span class="sxs-lookup"><span data-stu-id="65dde-123">It also provides several other enhancements.</span></span>
  - <span data-ttu-id="65dde-124">**[KB4036524](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036524&bugId=3847504&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** – Denna snabbkorrigering möjliggör synkronisering av försäljningsorderrad med funktionen för dataintegrering mellan Supply Chain Management och Sales.</span><span class="sxs-lookup"><span data-stu-id="65dde-124">**[KB4036524](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036524&bugId=3847504&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** – This hotfix enables sales order line synchronization from Supply Chain Management to Sales via the Data Integration feature.</span></span>
  - <span data-ttu-id="65dde-125">**[KB4036461](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036461&bugId=3847029&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** – Denna snabbkorrigering möjliggör synkronisering av försäljningsorder med funktionen för dataintegrering mellan Supply Chain Management och Sales.</span><span class="sxs-lookup"><span data-stu-id="65dde-125">**[KB4036461](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036461&bugId=3847029&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** – This hotfix enables sales order synchronization from Supply Chain Management to Sales via the Data Integration feature.</span></span>

    > [!NOTE]
    > <span data-ttu-id="65dde-126">Du måste bara installera KB4045570 eftersom installationen inkluderar ändringarna från andra snabbkorrigeringar.</span><span class="sxs-lookup"><span data-stu-id="65dde-126">You only have to install KB4045570 because the installation includes the changes from other hotfixes.</span></span> 

### <a name="dynamics-365-for-finance-and-operations-version-1611-november-2016"></a><span data-ttu-id="65dde-127">Dynamics 365 for Finance and Operations version 1611 (november 2016)</span><span class="sxs-lookup"><span data-stu-id="65dde-127">Dynamics 365 for Finance and Operations version 1611 (November 2016)</span></span>

- <span data-ttu-id="65dde-128">Dynamics 365 for Finance and Operations version 1611 (november 2016) med plattformsuppdatering 8 eller högre</span><span class="sxs-lookup"><span data-stu-id="65dde-128">Dynamics 365 for Finance and Operations version 1611 (November 2016)  with platform update 8 or higher</span></span>

- <span data-ttu-id="65dde-129">Följande snabbkorrigeringar är nödvändiga:</span><span class="sxs-lookup"><span data-stu-id="65dde-129">The following hotfixes are required:</span></span>

  - <span data-ttu-id="65dde-130">**[KB4051266](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4051266&bugId=3863566&qc=ee80faaa7bc6c77b368d5eaf456c9c08e0b9fba5903a7b6fd8c13756c3a4b757)** -Aktivera synkronisering av försäljningsorder med Data integrator mellan Supply Chain Management och Sales.</span><span class="sxs-lookup"><span data-stu-id="65dde-130">**[KB4051266](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4051266&bugId=3863566&qc=ee80faaa7bc6c77b368d5eaf456c9c08e0b9fba5903a7b6fd8c13756c3a4b757)** - Enable sales order synchronization with Data integrator from Supply Chain Management to Sales.</span></span> 
  - <span data-ttu-id="65dde-131">**[KB4037542](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4037542&bugId=3848253&qc=8323b93c15280172c5ab4159e0256e37104ced1729462c91ab2f7d00cb8d419c)** -Aktivera synkronisering av försäljningsorderrubriken med Data integrator mellan Supply Chain Management och Sales.</span><span class="sxs-lookup"><span data-stu-id="65dde-131">**[KB4037542](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4037542&bugId=3848253&qc=8323b93c15280172c5ab4159e0256e37104ced1729462c91ab2f7d00cb8d419c)** - Enable sales order header and line synchronization with Data integrator from Supply Chain Management to Sales.</span></span>
  - <span data-ttu-id="65dde-132">**[KB4033093](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4033093&bugId=3824604&qc=bd7e15e1fb56066b3a82ce48b691cf1ffbc934a7473fa888545b2211a8d416c5)** - Stöd för Potentiell kund till pengar-integrering via datatabeller krävs.</span><span class="sxs-lookup"><span data-stu-id="65dde-132">**[KB4033093](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4033093&bugId=3824604&qc=bd7e15e1fb56066b3a82ce48b691cf1ffbc934a7473fa888545b2211a8d416c5)** - Support for prospect to cash integration through data entities is required.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="65dde-133">Du måste initiera följande batchjobb från formuläret **SalesPopulateProspectToCash** när du har installerat snabbkorrigeringarna.</span><span class="sxs-lookup"><span data-stu-id="65dde-133">After you install the hotfixes, you must trigger the following batch job from the **SalesPopulateProspectToCash** form.</span></span> <span data-ttu-id="65dde-134">Detta formulär är dolt eftersom du bara behöver det en gång.</span><span class="sxs-lookup"><span data-stu-id="65dde-134">This form is hidden because you only need it once.</span></span> <span data-ttu-id="65dde-135">För att komma åt formuläret loggar du in och lägger till följande i din webbläsaradress: *&mi=action:SalesPopulateProspectToCash*, t.ex., `https://ax123456.cloud.test.dynamics.com/?cmp=USMF&mi=action:SalesPopulateProspectToCash`.</span><span class="sxs-lookup"><span data-stu-id="65dde-135">To access the form, log in to the environment and add the following to the URL in your browser address: *&mi=action:SalesPopulateProspectToCash*, for example, `https://ax123456.cloud.test.dynamics.com/?cmp=USMF&mi=action:SalesPopulateProspectToCash`.</span></span> <span data-ttu-id="65dde-136">När formuläret öppnas klickar du på OK.</span><span class="sxs-lookup"><span data-stu-id="65dde-136">When the form opens, click OK.</span></span> <span data-ttu-id="65dde-137">Då fylls ett nytt fält för **LineCreationSequnceNumber** i tabellerna **SalesLine**, **SalesQuotationLine** och **CustInvoiceTrans** med unika värden och produktraden uppdateras.</span><span class="sxs-lookup"><span data-stu-id="65dde-137">This will populate a new **LineCreationSequnceNumber** field in the **SalesLine**, **SalesQuotationLine**, and **CustInvoiceTrans** tables with unique values, and the product list will be refreshed.</span></span> <span data-ttu-id="65dde-138">Detta är nödvändigt för att integrationen Potentiell kund till kontanter ska fungera.</span><span class="sxs-lookup"><span data-stu-id="65dde-138">This is required for the Prospect to cash integration to work.</span></span>


## <a name="system-requirements-for-sales"></a><span data-ttu-id="65dde-139">Systemkrav för Sales</span><span class="sxs-lookup"><span data-stu-id="65dde-139">System requirements for Sales</span></span>

<span data-ttu-id="65dde-140">Om du vill använda lösningen Potentiell kund till kontanter måste du installera följande komponenter:</span><span class="sxs-lookup"><span data-stu-id="65dde-140">To use the Prospect to cash solution, you must install the following components:</span></span>

- <span data-ttu-id="65dde-141">Dynamics 365 Sales, version 1612 (8.2.1.207) (DB 8.2.1.207) online eller en senare version.</span><span class="sxs-lookup"><span data-stu-id="65dde-141">Dynamics 365 Sales version 1612 (8.2.1.207) (DB 8.2.1.207) online or a later version</span></span>
- <span data-ttu-id="65dde-142">Lösningen Potentiell kund till kontanter för Dynamics 365 Sales, version 1.15.0.0 eller senare.</span><span class="sxs-lookup"><span data-stu-id="65dde-142">Prospect to cash solution for Dynamics 365 Sales, version 1.15.0.0 or a later version.</span></span> <span data-ttu-id="65dde-143">Lösningen finns att hämta från AppSource.</span><span class="sxs-lookup"><span data-stu-id="65dde-143">The solution is available for download from AppSource.</span></span> <span data-ttu-id="65dde-144">[Hämta Dynamics 365, potentiell kund till kontanter](https://appsource.microsoft.com/product/dynamics-365/mscrm.c7a48b40-eed3-4d67-93ba-f2364281feb3).</span><span class="sxs-lookup"><span data-stu-id="65dde-144">[Download Dynamics 365, Prospect to Cash](https://appsource.microsoft.com/product/dynamics-365/mscrm.c7a48b40-eed3-4d67-93ba-f2364281feb3).</span></span>
