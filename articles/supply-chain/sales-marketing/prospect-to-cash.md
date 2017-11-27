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

# <a name="prospect-to-cash"></a><span data-ttu-id="8f13a-103">Potentiell kund till kontanter</span><span class="sxs-lookup"><span data-stu-id="8f13a-103">Prospect to cash</span></span>  

[!include[banner](../includes/banner.md)]

<span data-ttu-id="8f13a-104">Lösningen Potentiell kund till kontanter använder [Dataintegrering](/common-data-service/entity-reference/dynamics-365-integration) för att synkronisera data över både Microsoft Dynamics 365 for Finance and Operations, Enterprise edition- och Dynamics 365 for Sales-instanser via Common Data Service (CDS).</span><span class="sxs-lookup"><span data-stu-id="8f13a-104">The Prospect to cash solution uses [Data Integration](/common-data-service/entity-reference/dynamics-365-integration) to synchronize data across Microsoft Dynamics 365 for Finance and Operations, Enterprise edition and Dynamics 365 for Sales instances via the Common Data Service (CDS).</span></span> <span data-ttu-id="8f13a-105">Potentiell kund till kontanter-mallarna med funktionen för dataintegrering möjliggör ett flöde av konto-, produkt-, försäljningskvots-, försäljningsorder- samt försäljningsfakturadata mellan Finance and Operations och Sales.</span><span class="sxs-lookup"><span data-stu-id="8f13a-105">The Prospect to cash templates available with the Data Integration feature enable the flow of accounts, contacts, products, sales quotes, sales orders, and sales invoices data between Finance and Operations and Sales.</span></span> <span data-ttu-id="8f13a-106">Samtidigt som datan flödar mellan Finance and Operations och Sales kan du genomföra försäljnings- och marknadsföringsaktiviteter i Sales, samt hantera orderutförande och lagerhantering i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="8f13a-106">While the data is flowing between Finance and Operations and Sales, you can carry out sales and marketing activities in Sales and handle the order fulfillment with inventory management in Finance and Operations.</span></span> 

<span data-ttu-id="8f13a-107">Den här lösningen ger integration i följande områden:</span><span class="sxs-lookup"><span data-stu-id="8f13a-107">This solution provides integration in the following areas:</span></span> 

-   [<span data-ttu-id="8f13a-108">Underhåll konton i Sales och synkronisera dem med Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="8f13a-108">Maintain accounts in Sales and sync them to Finance and Operations</span></span>](accounts-template-mapping.md)
-   [<span data-ttu-id="8f13a-109">Underhåll kontakter i Sales och synkronisera dem med Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="8f13a-109">Maintain contacts in Sales and sync them to Finance and Operations</span></span>](contacts-template-mapping.md)
-   [<span data-ttu-id="8f13a-110">Underhåll produkter i Finance and Operations och synkronisera dem med Sales</span><span class="sxs-lookup"><span data-stu-id="8f13a-110">Maintain products in Finance and Operations and sync them to Sales</span></span>](products-template-mapping.md)
-   [<span data-ttu-id="8f13a-111">Skapa försäljningskvoter i Sales och synkronisera dem med Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="8f13a-111">Create sales quotes in Sales and sync them to Finance and Operations</span></span>](sales-quotation-template-mapping.md)
-   [<span data-ttu-id="8f13a-112">Skapa försäljningsorder i Finance and Operations och synkronisera dem med Sales</span><span class="sxs-lookup"><span data-stu-id="8f13a-112">Create sales orders in Finance and Operations and sync them to Sales</span></span>](sales-order-template-mapping.md)
-   [<span data-ttu-id="8f13a-113">Skapa försäljningsfakturor i Finance and Operations och synkronisera dem med Sales</span><span class="sxs-lookup"><span data-stu-id="8f13a-113">Create sales invoices in Finance and Operations and sync them to Sales</span></span>](sales-invoice-template-mapping.md)

<span data-ttu-id="8f13a-114">Den här lösningen ger direkt synkronisering i följande områden:</span><span class="sxs-lookup"><span data-stu-id="8f13a-114">This solution provides direct synchronization in the following areas:</span></span>

-   [<span data-ttu-id="8f13a-115">Underhåll konton i Sales och synkronisera dem direkt från Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="8f13a-115">Maintain accounts in Sales and sync them directly from Sales to Finance and Operations</span></span>](accounts-template-mapping-direct.md)
-   [<span data-ttu-id="8f13a-116">Underhåll produkter i Finance and Operations och synkronisera dem direkt med Sales</span><span class="sxs-lookup"><span data-stu-id="8f13a-116">Maintain products in Finance and Operations and sync them directly to Sales</span></span>](products-template-mapping-direct.md)
-   [<span data-ttu-id="8f13a-117">Behåll kontakter i Sales och synkronisera dem direkt till kontakter i Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="8f13a-117">Maintain contacts in Sales and sync them directly to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping-direct.md)
-   [<span data-ttu-id="8f13a-118">Synkronisera huvuden och rader i försäljningsofferter direkt från Sales till Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="8f13a-118">Synchronize sales quotation headers and lines directly from Sales to Finance and Operations</span></span>](sales-quotation-template-mapping-sales-fin.md)
-   [<span data-ttu-id="8f13a-119">Skapa försäljningsorder i Finance and Operations och synkronisera dem direkt med Sales</span><span class="sxs-lookup"><span data-stu-id="8f13a-119">Create sales orders in Finance and Operations and sync them directly to Sales</span></span>](sales-order-template-mapping-direct.md)
-  [<span data-ttu-id="8f13a-120">Synkronisera huvuden och rader i försäljningsorder direkt mellan Sales och Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="8f13a-120">Synchronize sales order headers and lines directly between Sales and Finance and Operations</span></span>](sales-order-template-mapping-between-sales-fin.md)
-   [<span data-ttu-id="8f13a-121">Synkronisera försäljningsorder direkt mellan Sales och Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="8f13a-121">Synchronize sales orders directly between Sales and Finance and Operations</span></span>](sales-order-template-mapping-direct-two-ways.md)
-   [<span data-ttu-id="8f13a-122">Skapa försäljningsfakturor i Finance and Operations och synkronisera dem direkt med Sales</span><span class="sxs-lookup"><span data-stu-id="8f13a-122">Create sales invoices in Finance and Operations and sync them directly to Sales</span></span>](sales-invoice-template-mapping-direct.md)


## <a name="system-requirements-for-dynamics-365-for-finance-and-operations-enterprise-edition"></a><span data-ttu-id="8f13a-123">Systemkrav för Dynamics 365 for Finance and Operations, Enterprise edition</span><span class="sxs-lookup"><span data-stu-id="8f13a-123">System requirements for Dynamics 365 for Finance and Operations, Enterprise edition</span></span>

<span data-ttu-id="8f13a-124">Om du vill använda lösningen Potentiell kund till kontanter måste du installera följande:</span><span class="sxs-lookup"><span data-stu-id="8f13a-124">To use the Prospect to cash solution, you must install the following:</span></span>

- <span data-ttu-id="8f13a-125">Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (juli 2017) med plattformsuppdatering 8 (app 7.2.11792.56024 med plattform 7.0.4565.16212)</span><span class="sxs-lookup"><span data-stu-id="8f13a-125">Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (July 2017) with Platform update 8 (App 7.2.11792.56024 w/ Platform 7.0.4565.16212)</span></span>

- <span data-ttu-id="8f13a-126">Snabbkorrigeringar för Dynamics 365 for Finance and Operations, Enterprise edition (juli 2017).</span><span class="sxs-lookup"><span data-stu-id="8f13a-126">Hotfixes for Dynamics 365 for Finance and Operations, Enterprise edition (July 2017).</span></span>
        
    -  <span data-ttu-id="8f13a-127">[KB4045570](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4045570&bugId=3851320&qc=ac1145034fd04ab71ccc4d14aa012f245176712c9af7c36bb77a118726d46160) - denna snabbkorrigering ger stöd för synkronisering av försäljningsorder med dataintegrering från Sales till Finance and Operations tillsammans med många andra förbättringar.</span><span class="sxs-lookup"><span data-stu-id="8f13a-127">[KB4045570](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4045570&bugId=3851320&qc=ac1145034fd04ab71ccc4d14aa012f245176712c9af7c36bb77a118726d46160) - This hotfix enabels support for sales order synchronization with the Data Integration feature from Sales to Finance and Operations, along with a number of other enhancements.</span></span>

    -  <span data-ttu-id="8f13a-128">[KB4036524](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036524&bugId=3847504&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2) - Denna snabbkorrigering möjliggör radsynkronisering av försäljningsorder med funktionen för dataintegrering mellan Finance and Operations och Sales.</span><span class="sxs-lookup"><span data-stu-id="8f13a-128">[KB4036524](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036524&bugId=3847504&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2) - This hotfix enables sales order line synchronization with the Data Integration feature from Finance and Operations to Sales.</span></span>
        
    -  <span data-ttu-id="8f13a-129">[KB4036461](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036461&bugId=3847029&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2) - Denna snabbkorrigering möjliggör radsynkronisering av försäljningsorder med funktionen för dataintegrering mellan Finance and Operations och Sales.</span><span class="sxs-lookup"><span data-stu-id="8f13a-129">[KB4036461](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036461&bugId=3847029&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2) - This hotfix enables sales order synchronization with the Data Integration feature from Finance and Operations to Sales.</span></span>

<span data-ttu-id="8f13a-130">**Obs**: Eftersom installationen inkluderar ändringarna från andra KB behöver du bara installera KB4045570 .</span><span class="sxs-lookup"><span data-stu-id="8f13a-130">**Note**: You only need to install KB4045570 because the installation includes the changes from the other KB's.</span></span>
 
## <a name="system-requirements-for-dynamics-365-for-sales"></a><span data-ttu-id="8f13a-131">Systemkrav för Dynamics 365 for Sales</span><span class="sxs-lookup"><span data-stu-id="8f13a-131">System requirements for Dynamics 365 for Sales</span></span>

<span data-ttu-id="8f13a-132">Om du vill använda lösningen Potentiell kund till kontanter måste du installera följande:</span><span class="sxs-lookup"><span data-stu-id="8f13a-132">To use the Prospect to cash solution, you must install the following:</span></span>

- <span data-ttu-id="8f13a-133">Dynamics 365 for Sales, version 1612 (8.2.1.207) (DB 8.2.1.207) online.</span><span class="sxs-lookup"><span data-stu-id="8f13a-133">Dynamics 365 for Sales version 1612 (8.2.1.207) (DB 8.2.1.207) online.</span></span>
- <span data-ttu-id="8f13a-134">Lösningen Potentiell kund till kontanter för Dynamics 365 for Sales, version 1.14.0.0 (v14) eller senare.</span><span class="sxs-lookup"><span data-stu-id="8f13a-134">Prospect to cash solution for Dynamics 365 for Sales, version 1.14.0.0 (v14) or later.</span></span>

### <a name="install-the-prospect-to-cash-solution-for-sales"></a><span data-ttu-id="8f13a-135">Installera Potentiell kund till kontanter-lösningen för Sales</span><span class="sxs-lookup"><span data-stu-id="8f13a-135">Install the Prospect to cash solution for Sales</span></span>

- <span data-ttu-id="8f13a-136">Hämta [Lösningspaketet Potentiell kund till kontanter för Dynamics 365 for Sales (zip-fil)](https://mbs.microsoft.com/customersource/Global/365Enterprise/downloads/product-releases/MD365FNOPENTProspectToCash) på CustomerSource.</span><span class="sxs-lookup"><span data-stu-id="8f13a-136">Download the [Prospect to cash for Dynamics 365 for Sales solution package zip file](https://mbs.microsoft.com/customersource/Global/365Enterprise/downloads/product-releases/MD365FNOPENTProspectToCash) on CustomerSource.</span></span>

- <span data-ttu-id="8f13a-137">Se till att zip-filen inte blockeras och då genererar felmeddelandet "Inga importpaket hittades" när du installerar lösningspaketet.</span><span class="sxs-lookup"><span data-stu-id="8f13a-137">Make sure that the zip file is unblocked so that you do not get the error message "No import packages were found" when you install the solution package.</span></span> <span data-ttu-id="8f13a-138">Gör följande för att avblockera filen:</span><span class="sxs-lookup"><span data-stu-id="8f13a-138">To unblock the file, do the following:</span></span>

    -  <span data-ttu-id="8f13a-139">Högerklicka zip-filen.</span><span class="sxs-lookup"><span data-stu-id="8f13a-139">Right-click the zip file.</span></span>
    -  <span data-ttu-id="8f13a-140">Välj **Egenskaper** och sedan **Avblockera**.</span><span class="sxs-lookup"><span data-stu-id="8f13a-140">Select **Properties** and then select **Unblock**.</span></span> 

- <span data-ttu-id="8f13a-141">Packa upp och kör PackageDeployer.exe.</span><span class="sxs-lookup"><span data-stu-id="8f13a-141">Unzip and run PackageDeployer.exe.</span></span>

- <span data-ttu-id="8f13a-142">Installera lösningen Potentiell kund till kontanter i din Sales-instans.</span><span class="sxs-lookup"><span data-stu-id="8f13a-142">Install the Prospect to Cash solution in your Sales instance.</span></span>

    - <span data-ttu-id="8f13a-143">Välj distributionstypen **Office 365**.</span><span class="sxs-lookup"><span data-stu-id="8f13a-143">Select the **Office 365** Deployment type.</span></span>
    - <span data-ttu-id="8f13a-144">Välj **Visa avancerade**.</span><span class="sxs-lookup"><span data-stu-id="8f13a-144">Select **Show advanced**.</span></span>
    - <span data-ttu-id="8f13a-145">Välj en **Region** för att köra en snabbinstallation.</span><span class="sxs-lookup"><span data-stu-id="8f13a-145">For a quick installation, select a **Region**.</span></span> <span data-ttu-id="8f13a-146">Om du väljer **Vet inte** kommer systemet att söka efter samtliga regioner, och installationen kommer att ta längre tid.</span><span class="sxs-lookup"><span data-stu-id="8f13a-146">If you select **Don’t know**, the system searches for all regions and it will take longer to install.</span></span>
    - <span data-ttu-id="8f13a-147">Ange **Användarnamn** och **Lösenord** för en administratörsanvändare som innehar användarbehörighet att installera.</span><span class="sxs-lookup"><span data-stu-id="8f13a-147">Enter **User name** and **Password** for an admin user who has the user rights to install.</span></span>

