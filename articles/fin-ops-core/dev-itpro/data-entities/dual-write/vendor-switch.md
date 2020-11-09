---
title: Växla mellan leverantörsdesigner
description: I det här avsnittet beskrivs hur du växlar integreringen av leverantörsdata mellan Finance and Operations-appar och Common Data Service.
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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-09-20
ms.openlocfilehash: 0ecc401706911f8b92146b95bb6415185df8b451
ms.sourcegitcommit: 0a741b131ed71f6345d4219a47cf5f71fec6744b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "3997562"
---
# <a name="switch-between-vendor-designs"></a><span data-ttu-id="85b7e-103">Växla mellan leverantörsdesigner</span><span class="sxs-lookup"><span data-stu-id="85b7e-103">Switch between vendor designs</span></span>

[!include [banner](../../includes/banner.md)]



## <a name="vendor-data-flow"></a><span data-ttu-id="85b7e-104">Leveranstörsdataflöde</span><span class="sxs-lookup"><span data-stu-id="85b7e-104">Vendor data flow</span></span> 

<span data-ttu-id="85b7e-105">Om du väljer att använda entiteten **Konto** för att lagra leverantörer av typen **Organisation** och entiteten **Kontakt** för att lagra leverantörer av typen **Person** konfigurerar du följande arbetsflöden.</span><span class="sxs-lookup"><span data-stu-id="85b7e-105">If you choose to use the **Account** entity to store vendors of the **Organization** type and the **Contact** entity to store vendors of the **Person** type, configure the following workflows.</span></span> <span data-ttu-id="85b7e-106">I annat fall är den här konfigurationen inte obligatorisk.</span><span class="sxs-lookup"><span data-stu-id="85b7e-106">Otherwise, this configuration isn't required.</span></span>

## <a name="use-the-extended-vendor-design-for-vendors-of-the-organization-type"></a><span data-ttu-id="85b7e-107">Använd den utökade leverantörsutformningen för leverantörer av typen organisation</span><span class="sxs-lookup"><span data-stu-id="85b7e-107">Use the extended vendor design for vendors of the Organization type</span></span>

<span data-ttu-id="85b7e-108">Lösningspaketet **Dynamics365FinanceExtended** innehåller följande mallar för arbetsflödesprocesser.</span><span class="sxs-lookup"><span data-stu-id="85b7e-108">The **Dynamics365FinanceExtended** solution package contains the following workflow process templates.</span></span> <span data-ttu-id="85b7e-109">Du ska skapa ett arbetsflöde för varje mall.</span><span class="sxs-lookup"><span data-stu-id="85b7e-109">You will create a workflow for each template.</span></span>

+ <span data-ttu-id="85b7e-110">Skapa leverantörer i entiteten konton</span><span class="sxs-lookup"><span data-stu-id="85b7e-110">Create Vendors in Accounts Entity</span></span>
+ <span data-ttu-id="85b7e-111">Skapa leverantörer i entiteten leverantörer</span><span class="sxs-lookup"><span data-stu-id="85b7e-111">Create Vendors in Vendors Entity</span></span>
+ <span data-ttu-id="85b7e-112">Uppdatera leverantörer i entiteten konton</span><span class="sxs-lookup"><span data-stu-id="85b7e-112">Update Vendors in Accounts Entity</span></span>
+ <span data-ttu-id="85b7e-113">Uppdatera leverantörer i entiteten leverantörer</span><span class="sxs-lookup"><span data-stu-id="85b7e-113">Update Vendors in Vendors Entity</span></span>

<span data-ttu-id="85b7e-114">Skapa nya arbetsflödesprocesser med hjälp av arbetsflödesprocessmallar genom att följa stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="85b7e-114">To create new workflow processes by using the workflow process templates, follow these steps.</span></span>

1. <span data-ttu-id="85b7e-115">Skapa en ny arbetsflödesprocess för entiteten **leverantör** och välj arbetsflödesprocessmallen **Skapa leverantörer i entiteten konton**.</span><span class="sxs-lookup"><span data-stu-id="85b7e-115">Create a workflow process for the **Vendor** entity, and select the **Create Vendors in Accounts Entity** workflow process template.</span></span> <span data-ttu-id="85b7e-116">Välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="85b7e-116">Then select **OK**.</span></span> <span data-ttu-id="85b7e-117">Det här arbetsflödet hanterar scenariot för skapande av leverantörer för entiteten **konto**.</span><span class="sxs-lookup"><span data-stu-id="85b7e-117">This workflow handles the vendor creation scenario for the **Account** entity.</span></span>

    ![Arbetsflödesprocess Skapa leverantörer i entiteten konton](media/create_process.png)

2. <span data-ttu-id="85b7e-119">Skapa en ny arbetsflödesprocess för entiteten **leverantör** och välj arbetsflödesprocessmallen **Uppdatera leverantörer i entiteten konton**.</span><span class="sxs-lookup"><span data-stu-id="85b7e-119">Create a workflow process for the **Vendor** entity, and select the **Update Vendors in Accounts Entity** workflow process template.</span></span> <span data-ttu-id="85b7e-120">Välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="85b7e-120">Then select **OK**.</span></span> <span data-ttu-id="85b7e-121">Det här arbetsflödet hanterar scenariot för uppdatering av leverantörer för entiteten **konto**.</span><span class="sxs-lookup"><span data-stu-id="85b7e-121">This workflow handles the vendor update scenario for the **Account** entity.</span></span>
3. <span data-ttu-id="85b7e-122">Skapa en ny arbetsflödesprocess för entiteten **Konto** och välj arbetsflödesprocessmallen **Skapa leverantörer i entiteten leverantörer**.</span><span class="sxs-lookup"><span data-stu-id="85b7e-122">Create a workflow process for the **Account** entity, and select the **Create Vendors in Vendors Entity** workflow process template.</span></span>
4. <span data-ttu-id="85b7e-123">Skapa en ny arbetsflödesprocess för entiteten **Konto** och välj arbetsflödesprocessmallen **Uppdatera leverantörer i entiteten leverantörer**.</span><span class="sxs-lookup"><span data-stu-id="85b7e-123">Create a workflow process for the **Account** entity, and select the **Update Vendors in Vendors Entity** workflow process template.</span></span>
5. <span data-ttu-id="85b7e-124">Du kan konfigurera arbetsflödena som antingen arbetsflöden i realtid eller i bakgrunden beroende på dina krav.</span><span class="sxs-lookup"><span data-stu-id="85b7e-124">You can configure the workflows as either real-time workflows or background workflows, depending on your requirements.</span></span> <span data-ttu-id="85b7e-125">Om du vill konfigurera ett arbetsflöde som ett bakgrundsarbetsflöde väljer du **Konvertera till ett arbetsflöde i bakgrunden**.</span><span class="sxs-lookup"><span data-stu-id="85b7e-125">To configure a workflow as a background workflow, select **Convert to a background workflow**.</span></span>

    ![Knappen Konvertera till ett arbetsflöde i bakgrunden](media/background_workflow.png)

6. <span data-ttu-id="85b7e-127">Aktivera de arbetsflöden som du skapade för entiteterna **konto** och **leverantör** för att börja använda entiteten **Konto** för att lagra leverantörsinformation av typen **Organisation**.</span><span class="sxs-lookup"><span data-stu-id="85b7e-127">Activate the workflows that you created for the **Account** and **Vendor** entities to start to use the **Account** entity to store information for vendors of the **Organization** type.</span></span>

## <a name="use-the-extended-vendor-design-for-vendors-of-the-person-type"></a><span data-ttu-id="85b7e-128">Använd den utökade leverantörsutformningen för leverantörer av typen person</span><span class="sxs-lookup"><span data-stu-id="85b7e-128">Use the extended vendor design for vendors of the Person type</span></span>

<span data-ttu-id="85b7e-129">Lösningspaketet **Dynamics365FinanceExtended** innehåller följande mallar för arbetsflödesprocesser.</span><span class="sxs-lookup"><span data-stu-id="85b7e-129">The **Dynamics365FinanceExtended** solution package contains the following workflow process templates.</span></span> <span data-ttu-id="85b7e-130">Du ska skapa ett arbetsflöde för varje mall.</span><span class="sxs-lookup"><span data-stu-id="85b7e-130">You will create a workflow for each template.</span></span>

+ <span data-ttu-id="85b7e-131">Skapa leverantörer av typen person i entiteten leverantörer</span><span class="sxs-lookup"><span data-stu-id="85b7e-131">Create Vendors of type Person in Vendors Entity</span></span>
+ <span data-ttu-id="85b7e-132">Skapa leverantörer av typen person i entiteten kontakt</span><span class="sxs-lookup"><span data-stu-id="85b7e-132">Create Vendors of type Person in Contacts Entity</span></span>
+ <span data-ttu-id="85b7e-133">Uppdatera leverantörer av typen person i entiteten kontakt</span><span class="sxs-lookup"><span data-stu-id="85b7e-133">Update Vendors of type Person in Contacts Entity</span></span>
+ <span data-ttu-id="85b7e-134">Uppdatera leverantörer av typen person i entiteten leverantörer</span><span class="sxs-lookup"><span data-stu-id="85b7e-134">Update Vendors of type Person in Vendors Entity</span></span>

<span data-ttu-id="85b7e-135">Skapa nya arbetsflödesprocesser med hjälp av arbetsflödesprocessmallar genom att följa stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="85b7e-135">To create new workflow processes by using the workflow process templates, follow these steps.</span></span>

1. <span data-ttu-id="85b7e-136">Skapa en ny arbetsflödesprocess för entiteten **leverantör** och välj arbetsflödesprocessmallen **Skapa leverantörer av typen person i entiteten kontakt**.</span><span class="sxs-lookup"><span data-stu-id="85b7e-136">Create a workflow process for the **Vendor** entity, and select the **Create Vendors of type Person in Contacts Entity** workflow process template.</span></span> <span data-ttu-id="85b7e-137">Välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="85b7e-137">Then select **OK**.</span></span> <span data-ttu-id="85b7e-138">Det här arbetsflödet hanterar scenariot för skapande av leverantörer för entiteten **Kontakt**.</span><span class="sxs-lookup"><span data-stu-id="85b7e-138">This workflow handles the vendor creation scenario for the **Contact** entity.</span></span>
2. <span data-ttu-id="85b7e-139">Skapa en ny arbetsflödesprocess för entiteten **leverantör** och välj arbetsflödesprocessmallen **Uppdatera leverantörer av typen person i entiteten kontakt**.</span><span class="sxs-lookup"><span data-stu-id="85b7e-139">Create a workflow process for the **Vendor** entity, and select the **Update Vendors of type Person in Contacts Entity** workflow process template.</span></span> <span data-ttu-id="85b7e-140">Välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="85b7e-140">Then select **OK**.</span></span> <span data-ttu-id="85b7e-141">Det här arbetsflödet hanterar scenariot för uppdatering av leverantörer för entiteten **Kontakt**.</span><span class="sxs-lookup"><span data-stu-id="85b7e-141">This workflow handles the vendor update scenario for the **Contact** entity.</span></span>
3. <span data-ttu-id="85b7e-142">Skapa en ny arbetsflödesprocess för entiteten **Kontakt** och välj arbetsflödesprocessmallen **Skapa leverantörer av typen person i entiteten leverantörer**.</span><span class="sxs-lookup"><span data-stu-id="85b7e-142">Create a workflow process for the **Contact** entity, and select the **Create Vendors of type Person in Vendors Entity** template.</span></span>
4. <span data-ttu-id="85b7e-143">Skapa en ny arbetsflödesprocess för entiteten **Kontakt** och välj arbetsflödesprocessmallen **Uppdatera leverantörer av typen person i entiteten leverantörer**.</span><span class="sxs-lookup"><span data-stu-id="85b7e-143">Create a workflow process for the **Contact** entity, and select the **Update Vendors of type Person in Vendors Entity** template.</span></span>
5. <span data-ttu-id="85b7e-144">Du kan konfigurera arbetsflödena som antingen arbetsflöden i realtid eller i bakgrunden beroende på dina krav.</span><span class="sxs-lookup"><span data-stu-id="85b7e-144">You can configure the workflows as either real-time workflows or background workflows, depending on your requirements.</span></span> <span data-ttu-id="85b7e-145">Om du vill konfigurera ett arbetsflöde som ett bakgrundsarbetsflöde väljer du **Konvertera till ett arbetsflöde i bakgrunden**.</span><span class="sxs-lookup"><span data-stu-id="85b7e-145">To configure a workflow as a background workflow, select **Convert to a background workflow**.</span></span>
6. <span data-ttu-id="85b7e-146">Aktivera de arbetsflöden som du skapade för entiteterna **Kontakt** och **leverantör** för att börja använda entiteten **Kontakt** för att lagra leverantörsinformation av typen **Person**.</span><span class="sxs-lookup"><span data-stu-id="85b7e-146">Activate the workflows that you created on the **Contact** and **Vendor** entities to start to use the **Contact** entity to store information for vendors of the **Person** type.</span></span>
