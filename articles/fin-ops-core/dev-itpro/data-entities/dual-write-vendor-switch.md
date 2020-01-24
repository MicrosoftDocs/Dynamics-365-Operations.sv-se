---
title: Växla mellan leverantörsdesigner
description: I det här avsnittet beskrivs hur du växlar mellan integreringen av leverantörsdata mellan Finance and Operations-appar och Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 09/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-09-20
ms.openlocfilehash: 204d788e72e79e7acf744d24cbeacb0f9b47da7d
ms.sourcegitcommit: 3306e451f04df01c51d8d332306b135d8ae1e254
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/09/2019
ms.locfileid: "2902735"
---
# <a name="switch-between-vendor-designs"></a><span data-ttu-id="7d2bf-103">Växla mellan leverantörsdesigner</span><span class="sxs-lookup"><span data-stu-id="7d2bf-103">Switch between vendor designs</span></span>

[!include [banner](../includes/banner.md)]

## <a name="vendor-data-flow"></a><span data-ttu-id="7d2bf-104">Leveranstörsdataflöde</span><span class="sxs-lookup"><span data-stu-id="7d2bf-104">Vendor data flow</span></span> 

<span data-ttu-id="7d2bf-105">Om du använder Dynamics 365-appar för leverantörshantering och vill isolera leverantörsinformation från kunder kan du använda denna grundläggande leverantörsdesign.</span><span class="sxs-lookup"><span data-stu-id="7d2bf-105">If you use other Dynamics 365 apps for vendor mastering and you want to isolate vendor information from customers, use this basic vendor design.</span></span>  

![Grundläggande leverantörsflöde](media/dual-write-vendor-data-flow.png)
 
<span data-ttu-id="7d2bf-107">Om du vill använda andra Dynamics 365-appar för leverantörshantering och vill fortsätta använda entiteten **Konto** för att lagra leverantörsinformationen kan du använda denna leverantörsdesignen.</span><span class="sxs-lookup"><span data-stu-id="7d2bf-107">If you use other Dynamics 365 apps for vendor mastering and you want to continue to use the **Account** entity for storing vendor information, use this extended vendor design.</span></span> <span data-ttu-id="7d2bf-108">I den här designen lagras utökad leverantörsinformation, t.ex. spärrstatus för leverantör och leverantörsprofilen lagras i entiteten **leverantörer** i Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="7d2bf-108">In this design, extended vendor information like vendor on-hold status and vendor profile is stored in the **vendors** entity in Common Data Service.</span></span> 

![Utökat leveranstörsflöde](media/dual-write-vendor-detail.jpg)
 
<span data-ttu-id="7d2bf-110">Följ stegen nedan för att använda den utökade leverantörsdesignen:</span><span class="sxs-lookup"><span data-stu-id="7d2bf-110">Follow the below steps to use the extended vendor design:</span></span> 
 
1. <span data-ttu-id="7d2bf-111">Lösningspaketet **SupplyChainCommon** innehåller arbetsflödesprocessmallar som visas i följande bild.</span><span class="sxs-lookup"><span data-stu-id="7d2bf-111">The **SupplyChainCommon** solution package contains the workflow process templates as shown in the following image.</span></span>
    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="7d2bf-112">![Arbetsflödesprocessmallar](media/dual-write-switch-3.png)</span><span class="sxs-lookup"><span data-stu-id="7d2bf-112">![Workflow process templates](media/dual-write-switch-3.png)</span></span>
2. <span data-ttu-id="7d2bf-113">Skapa nya arbetsflödesprocesser med hjälp av arbetsflödesprocessmallar:</span><span class="sxs-lookup"><span data-stu-id="7d2bf-113">Create new workflow processes using the workflow process templates:</span></span> 
    1. <span data-ttu-id="7d2bf-114">Skapa en ny arbetsflödesprocess för entiteten **leverantör** med hjälp av arbetsflödesprocessmallen **Skapa leverantörer i entiteten konto** och klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="7d2bf-114">Create a new workflow process for the **Vendor** entity using the **Create Vendors in Account Entity** workflow process template and click **OK**.</span></span> <span data-ttu-id="7d2bf-115">Det här arbetsflödet hanterar scenariot för skapande av leverantörer för entiteten **konto**.</span><span class="sxs-lookup"><span data-stu-id="7d2bf-115">This workflow handles the vendor creation scenario for the **Account** entity.</span></span>
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="7d2bf-116">![Skapa leverantörer i entiteten konto](media/dual-write-switch-4.png)</span><span class="sxs-lookup"><span data-stu-id="7d2bf-116">![Create Vendors in Account Entity](media/dual-write-switch-4.png)</span></span>
    2. <span data-ttu-id="7d2bf-117">Skapa en ny arbetsflödesprocess för entiteten **leverantör** med hjälp av arbetsflödesprocessmallen **entiteten uppdatera konto** och klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="7d2bf-117">Create a new workflow process for the **Vendor** entity using the **Update Accounts Entity** workflow process template and click **OK**.</span></span> <span data-ttu-id="7d2bf-118">Det här arbetsflödet hanterar scenariot för uppdatering av leverantörer för entiteten **konto**.</span><span class="sxs-lookup"><span data-stu-id="7d2bf-118">This workflow handles the vendor update scenario for the **Account** entity.</span></span> 
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="7d2bf-119">![Entiteten uppdatera konto](media/dual-write-switch-5.png)</span><span class="sxs-lookup"><span data-stu-id="7d2bf-119">![Update Accounts Entity](media/dual-write-switch-5.png)</span></span>
    3. <span data-ttu-id="7d2bf-120">Skapa nya arbetsflödesprocesser från mallarna som skapas i entiteten **konton**.</span><span class="sxs-lookup"><span data-stu-id="7d2bf-120">Create new workflow processes from the templates created on the **Accounts** entity.</span></span> 
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="7d2bf-121">![Skapa leverantörer i entiteten leverantörer](media/dual-write-switch-6.png)
        > </span><span class="sxs-lookup"><span data-stu-id="7d2bf-121">![Create vendors in vendors entity](media/dual-write-switch-6.png)
        > </span></span>[!div class="mx-imgBorder"]
<span data-ttu-id="7d2bf-122">![Uppdatera entiteten leverantörer](media/dual-write-switch-7.png)</span><span class="sxs-lookup"><span data-stu-id="7d2bf-122">![Update vendors entity](media/dual-write-switch-7.png)</span></span>
    4. <span data-ttu-id="7d2bf-123">Du kan konfigurera arbetsflödena som arbetsflöden i realtid eller i bakgrunden baserat på dina krav.</span><span class="sxs-lookup"><span data-stu-id="7d2bf-123">You can configure the workflows as real-time or background workflows based on your requirements.</span></span> 
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="7d2bf-124">![Konvertera till ett arbetsflöde i bakgrunden](media/dual-write-switch-8.png)</span><span class="sxs-lookup"><span data-stu-id="7d2bf-124">![Convert to a background workflow](media/dual-write-switch-8.png)</span></span>
    5. <span data-ttu-id="7d2bf-125">Aktivera de arbetsflöden som du skapade på entiteterna **konto** och **leverantör** för att börja använda entiteten **Konto** för lagring av leverantörsinformation.</span><span class="sxs-lookup"><span data-stu-id="7d2bf-125">Activate the workflows that you created on the **Account** and **Vendor** entities to start using the **Account** entity for storing vendor information.</span></span> 
 
