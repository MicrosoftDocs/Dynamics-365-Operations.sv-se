---
title: Potentiell kund till kontanter
description: "Detta avsnitt ger en översikt över lösningen Potentiell kund till kontanter mellan Dynamics 365 for Finance and Operations, Enterprise edition och Dynamics 365 for Sales."
author: ChristianRytt
manager: AnnBe
ms.date: 08/28/2017
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
ms.author: crytt
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 47e70cb1291e390b42b7feff844b2aca141f09b7
ms.openlocfilehash: a5f1ecd5f8b46287839439a963e571531ae161a7
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="prospect-to-cash"></a><span data-ttu-id="e5da3-103">Potentiell kund till kontanter</span><span class="sxs-lookup"><span data-stu-id="e5da3-103">Prospect to cash</span></span>  

[!include[banner](../includes/banner.md)]

<span data-ttu-id="e5da3-104">Lösningen Potentiell kund till kontanter använder [Dataintegrering](/common-data-service/entity-reference/dynamics-365-integration) för att synkronisera data över både Microsoft Dynamics 365 for Finance and Operations, Enterprise edition- och Dynamics 365 for Sales-instanser via Common Data Service (CDS).</span><span class="sxs-lookup"><span data-stu-id="e5da3-104">The Prospect to cash solution uses [Data Integration](/common-data-service/entity-reference/dynamics-365-integration) to synchronize data across Microsoft Dynamics 365 for Finance and Operations, Enterprise edition and Dynamics 365 for Sales instances via the Common Data Service (CDS).</span></span> <span data-ttu-id="e5da3-105">Potentiell kund till kontanter-mallarna med funktionen för dataintegrering möjliggör ett flöde av konto-, produkt-, försäljningskvots-, försäljningsorder- samt försäljningsfakturadata mellan Finance and Operations och Sales.</span><span class="sxs-lookup"><span data-stu-id="e5da3-105">The Prospect to cash templates available with the Data Integration feature enable the flow of accounts, contacts, products, sales quotes, sales orders, and sales invoices data between Finance and Operations and Sales.</span></span> <span data-ttu-id="e5da3-106">Samtidigt som datan flödar mellan Finance and Operations och Sales kan du genomföra försäljnings- och marknadsföringsaktiviteter i Sales, samt hantera orderutförande och lagerhantering i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="e5da3-106">While the data is flowing between Finance and Operations and Sales, you can carry out sales and marketing activities in Sales and handle the order fulfillment with inventory management in Finance and Operations.</span></span> 

<span data-ttu-id="e5da3-107">Den här lösningen ger integration i följande områden:</span><span class="sxs-lookup"><span data-stu-id="e5da3-107">This solution provides integration in the following areas:</span></span> 

-   [<span data-ttu-id="e5da3-108">Underhåll konton i Sales och synkronisera dem med Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="e5da3-108">Maintain accounts in Sales and sync them to Finance and Operations</span></span>](accounts-template-mapping.md)
-   [<span data-ttu-id="e5da3-109">Underhåll kontakter i Sales och synkronisera dem med Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="e5da3-109">Maintain contacts in Sales and sync them to Finance and Operations</span></span>](contacts-template-mapping.md)
-   [<span data-ttu-id="e5da3-110">Underhåll produkter i Finance and Operations och synkronisera dem med Sales</span><span class="sxs-lookup"><span data-stu-id="e5da3-110">Maintain products in Finance and Operations and sync them to Sales</span></span>](products-template-mapping.md)
-   [<span data-ttu-id="e5da3-111">Skapa försäljningskvoter i Sales och synkronisera dem med Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="e5da3-111">Create sales quotes in Sales and sync them to Finance and Operations</span></span>](sales-quotation-template-mapping.md)
-   [<span data-ttu-id="e5da3-112">Skapa försäljningsorder i Finance and Operations och synkronisera dem med Sales</span><span class="sxs-lookup"><span data-stu-id="e5da3-112">Create sales orders in Finance and Operations and sync them to Sales</span></span>](sales-order-template-mapping.md)
-   [<span data-ttu-id="e5da3-113">Skapa försäljningsfakturor i Finance and Operations och synkronisera dem med Sales</span><span class="sxs-lookup"><span data-stu-id="e5da3-113">Create sales invoices in Finance and Operations and sync them to Sales</span></span>](sales-invoice-template-mapping.md)

## <a name="system-requirements-for-dynamics-365-for-finance-and-operations-enterprise-edition"></a><span data-ttu-id="e5da3-114">Systemkrav för Dynamics 365 for Finance and Operations, Enterprise edition</span><span class="sxs-lookup"><span data-stu-id="e5da3-114">System requirements for Dynamics 365 for Finance and Operations, Enterprise edition</span></span>

<span data-ttu-id="e5da3-115">Om du vill använda lösningen Potentiell kund till kontanter måste du installera följande:</span><span class="sxs-lookup"><span data-stu-id="e5da3-115">To use the Prospect to cash solution, you must install the following:</span></span>

- <span data-ttu-id="e5da3-116">Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (juli 2017) med plattformsuppdatering 8 (app 7.2.11792.56024 med plattform 7.0.4565.16212)</span><span class="sxs-lookup"><span data-stu-id="e5da3-116">Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (July 2017) with Platform update 8 (App 7.2.11792.56024 w/ Platform 7.0.4565.16212)</span></span>

- <span data-ttu-id="e5da3-117">Två snabbkorrigeringar för Dynamics 365 for Finance and Operations, Enterprise edition (juli 2017).</span><span class="sxs-lookup"><span data-stu-id="e5da3-117">Two hotfixes for Dynamics 365 for Finance and Operations, Enterprise edition (July 2017).</span></span>

    -  <span data-ttu-id="e5da3-118">[KB4036524](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036524&bugId=3847504&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2) - Denna snabbkorrigering möjliggör radsynkronisering av försäljningsorder med funktionen för dataintegrering mellan Finance and Operations och Sales.</span><span class="sxs-lookup"><span data-stu-id="e5da3-118">[KB4036524](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036524&bugId=3847504&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2) - This hotfix enables sales order line synchronization with the Data Integration feature from Finance and Operations to Sales.</span></span>
        
    -  <span data-ttu-id="e5da3-119">[KB4036461](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036461&bugId=3847029&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2) - Denna snabbkorrigering möjliggör radsynkronisering av försäljningsorder med funktionen för dataintegrering mellan Finance and Operations och Sales.</span><span class="sxs-lookup"><span data-stu-id="e5da3-119">[KB4036461](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036461&bugId=3847029&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2) - This hotfix enables sales order synchronization with the Data Integration feature from Finance and Operations to Sales.</span></span>
    
<span data-ttu-id="e5da3-120">**Obs**: Eftersom installationen inkluderar ändringarna från KB4036461 behöver du bara installera KB4036524.</span><span class="sxs-lookup"><span data-stu-id="e5da3-120">**Note**: You only need to install KB4036524 because the installation includes the changes from KB4036461.</span></span>
 
## <a name="system-requirements-for-dynamics-365-for-sales"></a><span data-ttu-id="e5da3-121">Systemkrav för Dynamics 365 for Sales</span><span class="sxs-lookup"><span data-stu-id="e5da3-121">System requirements for Dynamics 365 for Sales</span></span>

<span data-ttu-id="e5da3-122">Om du vill använda lösningen Potentiell kund till kontanter måste du installera följande:</span><span class="sxs-lookup"><span data-stu-id="e5da3-122">To use the Prospect to cash solution, you must install the following:</span></span>

- <span data-ttu-id="e5da3-123">Dynamics 365 for Sales, version 1612 (8.2.1.207) (DB 8.2.1.207) online eller senare.</span><span class="sxs-lookup"><span data-stu-id="e5da3-123">Dynamics 365 for Sales version 1612 (8.2.1.207) (DB 8.2.1.207) online or later.</span></span>
- <span data-ttu-id="e5da3-124">Lösningen Potentiell kund till kontanter för Dynamics 365 for Sales, version 1.14.0.0 (v14) eller senare.</span><span class="sxs-lookup"><span data-stu-id="e5da3-124">Prospect to cash solution for Dynamics 365 for Sales, version 1.14.0.0 (v14) or later.</span></span>

### <a name="install-the-prospect-to-cash-solution-for-sales"></a><span data-ttu-id="e5da3-125">Installera Potentiell kund till kontanter-lösningen för Sales</span><span class="sxs-lookup"><span data-stu-id="e5da3-125">Install the Prospect to cash solution for Sales</span></span>

- <span data-ttu-id="e5da3-126">Hämta [Lösningspaketet Potentiell kund till kontanter för Dynamics 365 for Sales (zip-fil)](https://mbs.microsoft.com/customersource/Global/365Enterprise/downloads/product-releases/MD365FNOPENTProspectToCash) på CustomerSource.</span><span class="sxs-lookup"><span data-stu-id="e5da3-126">Download the [Prospect to cash for Dynamics 365 for Sales solution package zip file](https://mbs.microsoft.com/customersource/Global/365Enterprise/downloads/product-releases/MD365FNOPENTProspectToCash) on CustomerSource.</span></span>

- <span data-ttu-id="e5da3-127">Se till att zip-filen inte blockeras och då genererar felmeddelandet "Inga importpaket hittades" när du installerar lösningspaketet.</span><span class="sxs-lookup"><span data-stu-id="e5da3-127">Make sure that the zip file is unblocked so that you do not get the error message "No import packages were found" when you install the solution package.</span></span> <span data-ttu-id="e5da3-128">Gör följande för att avblockera filen:</span><span class="sxs-lookup"><span data-stu-id="e5da3-128">To unblock the file, do the following:</span></span>

    -  <span data-ttu-id="e5da3-129">Högerklicka zip-filen.</span><span class="sxs-lookup"><span data-stu-id="e5da3-129">Right-click the zip file.</span></span>
    -  <span data-ttu-id="e5da3-130">Välj **Egenskaper** och sedan **Avblockera**.</span><span class="sxs-lookup"><span data-stu-id="e5da3-130">Select **Properties** and then select **Unblock**.</span></span> 

- <span data-ttu-id="e5da3-131">Packa upp och kör PackageDeployer.exe.</span><span class="sxs-lookup"><span data-stu-id="e5da3-131">Unzip and run PackageDeployer.exe.</span></span>

- <span data-ttu-id="e5da3-132">Installera lösningen Potentiell kund till kontanter i din Sales-instans.</span><span class="sxs-lookup"><span data-stu-id="e5da3-132">Install the Prospect to Cash solution in your Sales instance.</span></span>

    - <span data-ttu-id="e5da3-133">Välj distributionstypen **Office 365**.</span><span class="sxs-lookup"><span data-stu-id="e5da3-133">Select the **Office 365** Deployment type.</span></span>
    - <span data-ttu-id="e5da3-134">Välj **Visa avancerade**.</span><span class="sxs-lookup"><span data-stu-id="e5da3-134">Select **Show advanced**.</span></span>
    - <span data-ttu-id="e5da3-135">Välj en **Region** för att köra en snabbinstallation.</span><span class="sxs-lookup"><span data-stu-id="e5da3-135">For a quick installation, select a **Region**.</span></span> <span data-ttu-id="e5da3-136">Om du väljer **Vet inte** kommer systemet att söka efter samtliga regioner, och installationen kommer att ta längre tid.</span><span class="sxs-lookup"><span data-stu-id="e5da3-136">If you select **Don’t know**, the system searches for all regions and it will take longer to install.</span></span>
    - <span data-ttu-id="e5da3-137">Ange **Användarnamn** och **Lösenord** för en administratörsanvändare som innehar användarbehörighet att installera.</span><span class="sxs-lookup"><span data-stu-id="e5da3-137">Enter **User name** and **Password** for an admin user who has the user rights to install.</span></span>

