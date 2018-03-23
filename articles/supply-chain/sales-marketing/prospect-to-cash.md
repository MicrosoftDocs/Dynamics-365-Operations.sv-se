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
ms.sourcegitcommit: e342c67f53828c77f77d99a2c3f909a23ced8989
ms.openlocfilehash: 5d9bc41c92258f9856088b04ec5af123c8e915e5
ms.contentlocale: sv-se
ms.lasthandoff: 03/13/2018

---

# <a name="prospect-to-cash"></a><span data-ttu-id="e3cde-103">Potentiell kund till kontanter</span><span class="sxs-lookup"><span data-stu-id="e3cde-103">Prospect to cash</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="e3cde-104">Denna Potentiell kund till pengar-lösning erbjuder direktsynkronisering mellan Dynamics 365 for Finance and Operations, Enterprise Edition och Dynamics 365 for Sales.</span><span class="sxs-lookup"><span data-stu-id="e3cde-104">The Prospect to cash solution provides direct synchronization across Dynamics 365 for Finance and Operations, Enterprise edition, and Dynamics 365 for Sales.</span></span> <span data-ttu-id="e3cde-105">Potentiell kund till pengar-mallarna med funktion för dataintegrering möjliggör ett dataflöde för konton, produkter, kontakter, produkter, försäljningskvoter, försäljningsorder samt försäljningsfakturor Finance and Operations och Sales.</span><span class="sxs-lookup"><span data-stu-id="e3cde-105">The Prospect to cash templates that are available with the Data Integration feature enable the flow of data for accounts, contacts, products, sales quotations, sales orders, and sales invoices between Finance and Operations and Sales.</span></span> <span data-ttu-id="e3cde-106">Samtidigt som datan flödar mellan Finance and Operations och Sales kan du genomföra försäljnings- och marknadsföringsaktiviteter i Sales, samt hantera orderutförande genom att utnyttja lagerhantering i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e3cde-106">While data is flowing between Finance and Operations and Sales, you can perform sales and marketing activities in Sales, and you can handle order fulfillment by using inventory management in Finance and Operations.</span></span> 

<span data-ttu-id="e3cde-107">Mer information om integration av funktionen potentiell kund till kontanter se en kort YouTube-video:</span><span class="sxs-lookup"><span data-stu-id="e3cde-107">For more information about the Prospect to cash integration, watch the short YouTube video:</span></span>

> [!Video https://www.youtube.com/embed/AVV9x5x-XCg]

<span data-ttu-id="e3cde-108">I den aktuella versionen innehåller lösningen Potentiell kund till pengar följande typer av direktsynkronisering:</span><span class="sxs-lookup"><span data-stu-id="e3cde-108">In the current version, the Prospect to cash solution provides the following types of direct synchronization:</span></span>

- [<span data-ttu-id="e3cde-109">Underhåll konton i Sales och synkronisera dem direkt från Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="e3cde-109">Maintain accounts in Sales and sync them directly from Sales to Finance and Operations</span></span>](accounts-template-mapping-direct.md)
- [<span data-ttu-id="e3cde-110">Underhåll produkter i Finance and Operations och synkronisera dem direkt med Sales</span><span class="sxs-lookup"><span data-stu-id="e3cde-110">Maintain products in Finance and Operations and sync them directly to Sales</span></span>](products-template-mapping-direct.md)
- [<span data-ttu-id="e3cde-111">Behåll kontakter i Sales och synkronisera dem direkt till kontakter i Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="e3cde-111">Maintain contacts in Sales and sync them directly to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping-direct.md)
- [<span data-ttu-id="e3cde-112">Synkronisera försäljningsofferter direkt från Sales till Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="e3cde-112">Synchronize sales quotation directly from Sales to Finance and Operations</span></span>](sales-quotation-template-mapping-sales-fin.md)
- [<span data-ttu-id="e3cde-113">Synkronisera försäljningsorder direkt mellan Sales och Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="e3cde-113">Synchronize sales orders directly between Sales and Finance and Operations</span></span>](sales-order-template-mapping-direct-two-ways.md)
- [<span data-ttu-id="e3cde-114">Synkronisera försäljningsfakturor direkt från Finance and Operations till Sales</span><span class="sxs-lookup"><span data-stu-id="e3cde-114">Synchronize sales invoice directly from Finance and Operations to Sales</span></span>](sales-invoice-template-mapping-direct.md)

## <a name="system-requirements-for-finance-and-operations"></a><span data-ttu-id="e3cde-115">Systemkrav för Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="e3cde-115">System requirements for Finance and Operations</span></span>

<span data-ttu-id="e3cde-116">Potentiell kund till kontanter-integrering stöds på följande versioner:</span><span class="sxs-lookup"><span data-stu-id="e3cde-116">Prospect to cash integration is supported on the following versions:</span></span>

### <a name="microsoft-dynamics-365-for-finance-and-operations-enterprise-edition-73-december-2017"></a><span data-ttu-id="e3cde-117">Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition 7.3 (December 2017)</span><span class="sxs-lookup"><span data-stu-id="e3cde-117">Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3 (December 2017)</span></span>

- <span data-ttu-id="e3cde-118">Dynamics 365 for Finance and Operations, Enterprise Edition (December 2017) - Application build 7.3.11971.56116 med med plattformsuppdatering 12 (7.0.4709.41129)</span><span class="sxs-lookup"><span data-stu-id="e3cde-118">Dynamics 365 for Finance and Operations, Enterprise edition (December 2017) - Application build 7.3.11971.56116 with Platform Update 12 (7.0.4709.41129)</span></span>

### <a name="dynamics-365-for-finance-and-operations-enterprise-edition-july-2017"></a><span data-ttu-id="e3cde-119">Dynamics 365 for Finance and Operations, Enterprise Edition (juli 2017)</span><span class="sxs-lookup"><span data-stu-id="e3cde-119">Dynamics 365 for Finance and Operations, Enterprise edition (July 2017)</span></span>

- <span data-ttu-id="e3cde-120">Dynamics 365 for Finance and Operations, Enterprise Edition (July 2017) - med plattformsuppdatering 8 (programversion 7.2.11792.56024 med plattform 7.0.4565.16212).</span><span class="sxs-lookup"><span data-stu-id="e3cde-120">Dynamics 365 for Finance and Operations, Enterprise edition (July 2017) - with platform update 8 (application build 7.2.11792.56024 with platform build 7.0.4565.16212).</span></span>
- <span data-ttu-id="e3cde-121">Följande snabbkorrigeringar är nödvändiga:</span><span class="sxs-lookup"><span data-stu-id="e3cde-121">The following hotfixes are required:</span></span>

    - <span data-ttu-id="e3cde-122">**[KB4045570](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4045570&bugId=3851320&qc=ac1145034fd04ab71ccc4d14aa012f245176712c9af7c36bb77a118726d46160)** – Denna snabbkorrigering möjliggör synkronisering av försäljningsorder med funktionen för dataintegrering mellan Finance and Operations och Sales.</span><span class="sxs-lookup"><span data-stu-id="e3cde-122">**[KB4045570](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4045570&bugId=3851320&qc=ac1145034fd04ab71ccc4d14aa012f245176712c9af7c36bb77a118726d46160)** – This hotfix enables sales order synchronization from Sales to Finance and Operations via the Data Integration feature.</span></span> <span data-ttu-id="e3cde-123">Den innehåller även flera förbättringar.</span><span class="sxs-lookup"><span data-stu-id="e3cde-123">It also provides several other enhancements.</span></span>
    - <span data-ttu-id="e3cde-124">**[KB4036524](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036524&bugId=3847504&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** – Denna snabbkorrigering möjliggör synkronisering av försäljningsorderrader med funktionen för dataintegrering mellan Finance and Operations och Sales.</span><span class="sxs-lookup"><span data-stu-id="e3cde-124">**[KB4036524](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036524&bugId=3847504&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** – This hotfix enables sales order line synchronization from Finance and Operations to Sales via the Data Integration feature.</span></span>
    - <span data-ttu-id="e3cde-125">**[KB4036461](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036461&bugId=3847029&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** – Denna snabbkorrigering möjliggör synkronisering av försäljningsorder med funktionen för dataintegrering mellan Finance and Operations och Sales.</span><span class="sxs-lookup"><span data-stu-id="e3cde-125">**[KB4036461](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036461&bugId=3847029&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** – This hotfix enables sales order synchronization from Finance and Operations to Sales via the Data Integration feature.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e3cde-126">Du måste bara installera KB4045570 eftersom installationen inkluderar ändringarna från andra snabbkorrigeringar.</span><span class="sxs-lookup"><span data-stu-id="e3cde-126">You only have to install KB4045570 because the installation includes the changes from other hotfixes.</span></span> 

### <a name="dynamics-365-for-finance-and-operations-version-1611-november-2016"></a><span data-ttu-id="e3cde-127">Dynamics 365 for Finance and Operations version 1611 (november 2016)</span><span class="sxs-lookup"><span data-stu-id="e3cde-127">Dynamics 365 for Finance and Operations version 1611 (November 2016)</span></span>

- <span data-ttu-id="e3cde-128">Dynamics 365 for Finance and Operations version 1611 (november 2016) med plattformsuppdatering 8 eller senare</span><span class="sxs-lookup"><span data-stu-id="e3cde-128">Dynamics 365 for Finance and Operations version 1611 (November 2016)  with platform update 8 or higher</span></span>

- <span data-ttu-id="e3cde-129">Följande snabbkorrigeringar är nödvändiga:</span><span class="sxs-lookup"><span data-stu-id="e3cde-129">The following hotfixes are required:</span></span>

    - <span data-ttu-id="e3cde-130">**[KB4051266](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4051266&bugId=3863566&qc=ee80faaa7bc6c77b368d5eaf456c9c08e0b9fba5903a7b6fd8c13756c3a4b757)** -Aktivera synkronisering av försäljningsorder med Data integrator från Finance and Operations och Sales.</span><span class="sxs-lookup"><span data-stu-id="e3cde-130">**[KB4051266](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4051266&bugId=3863566&qc=ee80faaa7bc6c77b368d5eaf456c9c08e0b9fba5903a7b6fd8c13756c3a4b757)** - Enable sales order synchronization with Data integrator from Finance and Operations to Sales.</span></span> 
    - <span data-ttu-id="e3cde-131">**[KB4037542](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4037542&bugId=3848253&qc=8323b93c15280172c5ab4159e0256e37104ced1729462c91ab2f7d00cb8d419c)** - Aktivera synkronisering av försäljningsorderrubriken och raden med Data integrator från Finance and Operations och Sales.</span><span class="sxs-lookup"><span data-stu-id="e3cde-131">**[KB4037542](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4037542&bugId=3848253&qc=8323b93c15280172c5ab4159e0256e37104ced1729462c91ab2f7d00cb8d419c)** - Enable sales order header and line synchronization with Data integrator from Finance and Operations to Sales.</span></span>
    - <span data-ttu-id="e3cde-132">**[KB4033093](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4033093&bugId=3824604&qc=bd7e15e1fb56066b3a82ce48b691cf1ffbc934a7473fa888545b2211a8d416c5)** - Stöd för Potentiell kund till pengar-integrering via datatabeller krävs.</span><span class="sxs-lookup"><span data-stu-id="e3cde-132">**[KB4033093](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4033093&bugId=3824604&qc=bd7e15e1fb56066b3a82ce48b691cf1ffbc934a7473fa888545b2211a8d416c5)** - Support for prospect to cash integration through data entities is required.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e3cde-133">Du måste initiera följande batchjobb från formuläret **SalesPopulateProspectToCash** när du har installerat snabbkorrigeringarna.</span><span class="sxs-lookup"><span data-stu-id="e3cde-133">After you install the hotfixes, you must trigger the following batch job from the **SalesPopulateProspectToCash** form.</span></span> <span data-ttu-id="e3cde-134">Detta formulär är dolt eftersom du bara behöver det en gång.</span><span class="sxs-lookup"><span data-stu-id="e3cde-134">This form is hidden because you only need it once.</span></span> <span data-ttu-id="e3cde-135">För att komma åt formuläret loggar du in och lägger till följande i din webbläsaradress : & mi = åtgärd: SalesPopulateProspectToCash, t.ex `https://ax123456.cloud.test.dynamics.com/?cmp=USMF&mi=action:SalesPopulateProspectToCash`.</span><span class="sxs-lookup"><span data-stu-id="e3cde-135">To access the form, log in to the environment and add the following to the URL in your browser address: &mi=action:SalesPopulateProspectToCash, for example, `https://ax123456.cloud.test.dynamics.com/?cmp=USMF&mi=action:SalesPopulateProspectToCash`.</span></span> <span data-ttu-id="e3cde-136">När formuläret öppnas klickar du på OK.</span><span class="sxs-lookup"><span data-stu-id="e3cde-136">When the form opens, click OK.</span></span> <span data-ttu-id="e3cde-137">Då fylls ett nytt fält för **LineCreationSequnceNumber** i tabellerna **SalesLine**, **SalesQuotationLine** och **CustInvoiceTrans** med unika värden och produktraden uppdateras.</span><span class="sxs-lookup"><span data-stu-id="e3cde-137">This will populate a new **LineCreationSequnceNumber** field in the **SalesLine**, **SalesQuotationLine**, and **CustInvoiceTrans** tables with unique values, and the product list will be refreshed.</span></span> <span data-ttu-id="e3cde-138">Detta är nödvändigt för att integrationen Potentiell kund till kontanter ska fungera.</span><span class="sxs-lookup"><span data-stu-id="e3cde-138">This is required for the Prospect to cash integration to work.</span></span>


## <a name="system-requirements-for-sales"></a><span data-ttu-id="e3cde-139">Systemkrav för Sales</span><span class="sxs-lookup"><span data-stu-id="e3cde-139">System requirements for Sales</span></span>

<span data-ttu-id="e3cde-140">Om du vill använda lösningen Potentiell kund till kontanter måste du installera följande komponenter:</span><span class="sxs-lookup"><span data-stu-id="e3cde-140">To use the Prospect to cash solution, you must install the following components:</span></span>

- <span data-ttu-id="e3cde-141">Dynamics 365 for Sales, version 1612 (8.2.1.207) (DB 8.2.1.207) online eller en senare version.</span><span class="sxs-lookup"><span data-stu-id="e3cde-141">Dynamics 365 for Sales version 1612 (8.2.1.207) (DB 8.2.1.207) online or a later version</span></span>
- <span data-ttu-id="e3cde-142">Lösningen Potentiell kund till pengar för Dynamics 365 for Sales, version 1.15.0.0 (v15)</span><span class="sxs-lookup"><span data-stu-id="e3cde-142">Prospect to cash solution for Dynamics 365 for Sales, version 1.15.0.0 (v15)</span></span> 

### <a name="install-the-prospect-to-cash-solution-for-sales"></a><span data-ttu-id="e3cde-143">Installera Potentiell kund till kontanter-lösningen för Sales</span><span class="sxs-lookup"><span data-stu-id="e3cde-143">Install the Prospect to cash solution for Sales</span></span>

1. <span data-ttu-id="e3cde-144">Hämta [Lösningspaketet Potentiell kund till kontanter för Dynamics 365 for Sales (zip-fil)](https://mbs.microsoft.com/customersource/Global/365Enterprise/downloads/product-releases/MD365FNOPENTProspectToCash) från CustomerSource.</span><span class="sxs-lookup"><span data-stu-id="e3cde-144">Download the [Prospect to cash for Dynamics 365 for Sales solution package zip file](https://mbs.microsoft.com/customersource/Global/365Enterprise/downloads/product-releases/MD365FNOPENTProspectToCash) from CustomerSource.</span></span>
2. <span data-ttu-id="e3cde-145">Se till att zip-filen inte blockeras.</span><span class="sxs-lookup"><span data-stu-id="e3cde-145">Make sure that the zip file is unblocked.</span></span> <span data-ttu-id="e3cde-146">I annat fall kommer du att få följande felmeddelande när du försöker installera lösningspaketet: ”Inget importpaket hittades”.</span><span class="sxs-lookup"><span data-stu-id="e3cde-146">Otherwise, when you try to install the solution package, you may receive the following error message, "No import packages were found."</span></span> <span data-ttu-id="e3cde-147">För att avblockera zip-filen, högerklicka på filen och välj **Egenskaper**.</span><span class="sxs-lookup"><span data-stu-id="e3cde-147">To unblock the zip file, right-click it, and select **Properties**.</span></span> <span data-ttu-id="e3cde-148">Välj **Avblockera**.</span><span class="sxs-lookup"><span data-stu-id="e3cde-148">Select **Unblock**.</span></span>
3. <span data-ttu-id="e3cde-149">Packa upp och kör **PackageDeployer.exe**.</span><span class="sxs-lookup"><span data-stu-id="e3cde-149">Unzip and run **PackageDeployer.exe**.</span></span>
4. <span data-ttu-id="e3cde-150">Installera lösningen Potentiell kund till pengar i din Sales-instans:</span><span class="sxs-lookup"><span data-stu-id="e3cde-150">Install the Prospect to cash solution on your Sales instance:</span></span>

    1. <span data-ttu-id="e3cde-151">Välj **Office 365** som implementeringstyp.</span><span class="sxs-lookup"><span data-stu-id="e3cde-151">Select **Office 365** as the deployment type.</span></span>
    2. <span data-ttu-id="e3cde-152">Välj **Visa avancerade**.</span><span class="sxs-lookup"><span data-stu-id="e3cde-152">Select **Show advanced**.</span></span>
    3. <span data-ttu-id="e3cde-153">Välj en region för att köra en snabbinstallation.</span><span class="sxs-lookup"><span data-stu-id="e3cde-153">For a quick installation, select a region.</span></span> <span data-ttu-id="e3cde-154">Om du väljer **Vet inte** kommer systemet att söka efter samtliga regioner, och installationen kommer att ta längre tid.</span><span class="sxs-lookup"><span data-stu-id="e3cde-154">If you select **Don't know**, the system searches for all regions, and the installation will take more time.</span></span>
    4. <span data-ttu-id="e3cde-155">Ange användarnamn och lösenord för en administratörsanvändare med installationsbehörighet.</span><span class="sxs-lookup"><span data-stu-id="e3cde-155">Enter the user name and password of an admin user who has installation rights.</span></span>



