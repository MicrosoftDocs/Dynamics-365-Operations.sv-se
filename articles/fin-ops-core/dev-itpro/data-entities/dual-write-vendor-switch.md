---
title: Växla mellan leverantörsdesign
description: ''
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
ms.openlocfilehash: 4e97ff0b0e6195b5e3703e15a0bb0de7644ef8d1
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/06/2019
ms.locfileid: "2772374"
---
# <a name="switch-between-vendor-designs"></a><span data-ttu-id="c0568-102">Växla mellan leverantörsdesign</span><span class="sxs-lookup"><span data-stu-id="c0568-102">Switch between vendor designs</span></span>

[!include [banner](../includes/banner.md)]

## <a name="vendor-data-flow"></a><span data-ttu-id="c0568-103">Leveranstörsdataflöde</span><span class="sxs-lookup"><span data-stu-id="c0568-103">Vendor data flow</span></span> 

<span data-ttu-id="c0568-104">Om du använder Dynamics 365-appar för leverantörshantering och vill isolera leverantörsinformation från kunder kan du använda denna grundläggande leverantörsdesign.</span><span class="sxs-lookup"><span data-stu-id="c0568-104">If you use other Dynamics 365 apps for vendor mastering and you want to isolate vendor information from customers, use this basic vendor design.</span></span>  

![Grundläggande leverantörsflöde](media/dual-write-switch-1.png)
 
<span data-ttu-id="c0568-106">Om du vill använda andra Dynamics 365-appar för leverantörshantering och vill fortsätta använda entiteten **Konto** för att lagra leverantörsinformationen kan du använda denna leverantörsdesignen.</span><span class="sxs-lookup"><span data-stu-id="c0568-106">If you use other Dynamics 365 apps for vendor mastering and you want to continue to use the **Account** entity for storing vendor information, use this extended vendor design.</span></span> <span data-ttu-id="c0568-107">I den här designen lagras utökad leverantörsinformation, t.ex. spärrstatus för leverantör och leverantörsprofilen lagras i entiteten **leverantörer** i Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="c0568-107">In this design, extended vendor information like vendor on-hold status and vendor profile is stored in the **vendors** entity in Common Data Service.</span></span> 

![Utökat leveranstörsflöde](media/dual-write-switch-2.png)
 
<span data-ttu-id="c0568-109">Följ stegen nedan för att använda den utökade leverantörsdesignen:</span><span class="sxs-lookup"><span data-stu-id="c0568-109">Follow the below steps to use the extended vendor design:</span></span> 
 
1. <span data-ttu-id="c0568-110">Lösningspaketet **SupplyChainCommon** innehåller arbetsflödesprocessmallar som visas i följande bild.</span><span class="sxs-lookup"><span data-stu-id="c0568-110">The **SupplyChainCommon** solution package contains the workflow process templates as shown in the following image.</span></span>
    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="c0568-111">![Arbetsflödesprocessmallar](media/dual-write-switch-3.png)</span><span class="sxs-lookup"><span data-stu-id="c0568-111">![Workflow process templates](media/dual-write-switch-3.png)</span></span>
2. <span data-ttu-id="c0568-112">Skapa nya arbetsflödesprocesser med hjälp av arbetsflödesprocessmallar:</span><span class="sxs-lookup"><span data-stu-id="c0568-112">Create new workflow processes using the workflow process templates:</span></span> 
    1. <span data-ttu-id="c0568-113">Skapa en ny arbetsflödesprocess för entiteten **leverantör** med hjälp av arbetsflödesprocessmallen **Skapa leverantörer i entiteten konto** och klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="c0568-113">Create a new workflow process for the **Vendor** entity using the **Create Vendors in Account Entity** workflow process template and click **OK**.</span></span> <span data-ttu-id="c0568-114">Det här arbetsflödet hanterar scenariot för skapande av leverantörer för entiteten **konto**.</span><span class="sxs-lookup"><span data-stu-id="c0568-114">This workflow handles the vendor creation scenario for the **Account** entity.</span></span>
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="c0568-115">![Skapa leverantörer i entiteten konto](media/dual-write-switch-4.png)</span><span class="sxs-lookup"><span data-stu-id="c0568-115">![Create Vendors in Account Entity](media/dual-write-switch-4.png)</span></span>
    2. <span data-ttu-id="c0568-116">Skapa en ny arbetsflödesprocess för entiteten **leverantör** med hjälp av arbetsflödesprocessmallen **entiteten uppdatera konto** och klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="c0568-116">Create a new workflow process for the **Vendor** entity using the **Update Accounts Entity** workflow process template and click **OK**.</span></span> <span data-ttu-id="c0568-117">Det här arbetsflödet hanterar scenariot för uppdatering av leverantörer för entiteten **konto**.</span><span class="sxs-lookup"><span data-stu-id="c0568-117">This workflow handles the vendor update scenario for the **Account** entity.</span></span> 
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="c0568-118">![Entiteten uppdatera konto](media/dual-write-switch-5.png)</span><span class="sxs-lookup"><span data-stu-id="c0568-118">![Update Accounts Entity](media/dual-write-switch-5.png)</span></span>
    3. <span data-ttu-id="c0568-119">Skapa nya arbetsflödesprocesser från mallarna som skapas i entiteten **konton**.</span><span class="sxs-lookup"><span data-stu-id="c0568-119">Create new workflow processes from the templates created on the **Accounts** entity.</span></span> 
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="c0568-120">![Skapa leverantörer i entiteten leverantörer](media/dual-write-switch-6.png)
        > </span><span class="sxs-lookup"><span data-stu-id="c0568-120">![Create vendors in vendors entity](media/dual-write-switch-6.png)
        > </span></span>[!div class="mx-imgBorder"]
<span data-ttu-id="c0568-121">![Uppdatera entiteten leverantörer](media/dual-write-switch-7.png)</span><span class="sxs-lookup"><span data-stu-id="c0568-121">![Update vendors entity](media/dual-write-switch-7.png)</span></span>
    4. <span data-ttu-id="c0568-122">Du kan konfigurera arbetsflödena som arbetsflöden i realtid eller i bakgrunden baserat på dina krav.</span><span class="sxs-lookup"><span data-stu-id="c0568-122">You can configure the workflows as real-time or background workflows based on your requirements.</span></span> 
        > [!div class="mx-imgBorder"]
        > <span data-ttu-id="c0568-123">![Konvertera till ett arbetsflöde i bakgrunden](media/dual-write-switch-8.png)</span><span class="sxs-lookup"><span data-stu-id="c0568-123">![Convert to a background workflow](media/dual-write-switch-8.png)</span></span>
    5. <span data-ttu-id="c0568-124">Aktivera de arbetsflöden som du skapade på entiteterna **konto** och **leverantör** för att börja använda Customer Engagement-entiteten **Konto** för lagring av leverantörsinformation.</span><span class="sxs-lookup"><span data-stu-id="c0568-124">Activate the workflows that you created on the **Account** and **Vendor** entities to start using the Customer Engagement **Account** entity for storing vendor information.</span></span> 
 
