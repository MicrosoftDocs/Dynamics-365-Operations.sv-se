---
title: "Lägg till en adress till en serviceorder"
description: "I det här avsnittet beskrivs hur du lägger till en kundadress till en serviceorder."
author: YuyuScheller
manager: AnnBe
ms.date: 05/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: e6dfa27b2101e84fbab678e781c26126cf1db898
ms.contentlocale: sv-se
ms.lasthandoff: 05/08/2018

---

# <a name="add-an-address-to-a-service-order"></a><span data-ttu-id="c7aff-103">Lägg till en adress till en serviceorder</span><span class="sxs-lookup"><span data-stu-id="c7aff-103">Add an address to a service order</span></span>    

[!include [banner](../includes/banner.md)]


<span data-ttu-id="c7aff-104">I det här avsnittet beskrivs hur du lägger till en kundadress till en serviceorder.</span><span class="sxs-lookup"><span data-stu-id="c7aff-104">This topic describes how to add a customer address to a service order.</span></span> <span data-ttu-id="c7aff-105">När du skapar en serviceorder förs adressinformationen över från det projekt som serviceordern är kopplad till.</span><span class="sxs-lookup"><span data-stu-id="c7aff-105">When you create a service order, the address information is transferred from the project that the service order is attached to.</span></span> <span data-ttu-id="c7aff-106">Du kan dock välja en alternativ plats från adresser som redan finns i Microsoft Dynamics AX för kunder, leverantörer, platser, lagerställen, serviceorder och projekt.</span><span class="sxs-lookup"><span data-stu-id="c7aff-106">However, you can select an alternative location from addresses that are already entered in Microsoft Dynamics AX for customers, vendors, sites, warehouses, service orders, and projects.</span></span>

<span data-ttu-id="c7aff-107">Du kan också skapa en ny adress.</span><span class="sxs-lookup"><span data-stu-id="c7aff-107">You can also create a new address.</span></span> <span data-ttu-id="c7aff-108">Som standard överförs den nya adressen till projektet.</span><span class="sxs-lookup"><span data-stu-id="c7aff-108">By default, the new address is transferred to the project.</span></span> <span data-ttu-id="c7aff-109">Du kan dock ange att den nya adressen bara är relevant för den här instansen av tjänsten.</span><span class="sxs-lookup"><span data-stu-id="c7aff-109">However, you can specify that the new address is only relevant for this instance of the service.</span></span> <span data-ttu-id="c7aff-110">Om du gör det överförs den nya adressen inte till projektet.</span><span class="sxs-lookup"><span data-stu-id="c7aff-110">If you do, the new address is not transferred to the project.</span></span>

## <a name="create-a-customer-address-for-a-service-order"></a><span data-ttu-id="c7aff-111">Skapa en kundadress för en serviceorder</span><span class="sxs-lookup"><span data-stu-id="c7aff-111">Create a customer address for a service order</span></span>

<span data-ttu-id="c7aff-112">Om du vill lägga till en adress till en serviceorder:</span><span class="sxs-lookup"><span data-stu-id="c7aff-112">To add an address to a service order, follow these steps:</span></span>

1.  <span data-ttu-id="c7aff-113">Klicka på noden **Servicehantering** \> **Vanligt** \> **Serviceorder** \> **Serviceorder**.</span><span class="sxs-lookup"><span data-stu-id="c7aff-113">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="c7aff-114">Öppna den serviceorder som du vill skapa en adress för.</span><span class="sxs-lookup"><span data-stu-id="c7aff-114">Open the service order that you want to create an address for.</span></span>

3.  <span data-ttu-id="c7aff-115">I **åtgärdsfönstret**, klicka på **Redigera** och klicka sedan på **Huvudvy**.</span><span class="sxs-lookup"><span data-stu-id="c7aff-115">On the **Action Pane**, click **Edit**, and then click **Header view**.</span></span>

4.  <span data-ttu-id="c7aff-116">På snabbfliken **adress** klicka på **lägga till adress**.</span><span class="sxs-lookup"><span data-stu-id="c7aff-116">On the **Address** FastTab, click **Add address**.</span></span>

5.  <span data-ttu-id="c7aff-117">Ange ett unikt namn för adressen och fyll i de återstående fälten i formuläret **Ny adress**.</span><span class="sxs-lookup"><span data-stu-id="c7aff-117">In the **New address** form, enter a unique name for the address and complete the remaining fields.</span></span> 
    

    > [!WARNING]
    > <P><span data-ttu-id="c7aff-118">Om du anger samma namn som en befintlig adress, kommer informationen som du anger i de återstående fälten skriva över informationen för den befintliga adressen.</span><span class="sxs-lookup"><span data-stu-id="c7aff-118">If you enter the same name as an existing address, the information that you enter in the remaining fields will overwrite information for the existing address.</span></span></P>


6.  <span data-ttu-id="c7aff-119">Klicka på **OK** för att kopiera den nya adressen till din serviceorder.</span><span class="sxs-lookup"><span data-stu-id="c7aff-119">Click **OK** to copy the new address to your service order.</span></span>

## <a name="specify-an-alternative-address-on-a-service-order"></a><span data-ttu-id="c7aff-120">Ange en alternativ adress på en serviceorder</span><span class="sxs-lookup"><span data-stu-id="c7aff-120">Specify an alternative address on a service order</span></span>

<span data-ttu-id="c7aff-121">Om du vill lägga till en alternativ adress till en serviceorder:</span><span class="sxs-lookup"><span data-stu-id="c7aff-121">To add an alternative address to a service order, follow these steps:</span></span>

1.  <span data-ttu-id="c7aff-122">Klicka på noden **Servicehantering** \> **Vanligt** \> **Serviceorder** \> **Serviceorder**.</span><span class="sxs-lookup"><span data-stu-id="c7aff-122">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="c7aff-123">Öppna den serviceorder som du vill ange en alternativ adress för.</span><span class="sxs-lookup"><span data-stu-id="c7aff-123">Open the service order that you want to enter an alternative address for.</span></span>

3.  <span data-ttu-id="c7aff-124">I **åtgärdsfönstret**, klicka på **Redigera** och klicka sedan på **Huvudvy**.</span><span class="sxs-lookup"><span data-stu-id="c7aff-124">On the **Action Pane**, click **Edit**, and then click **Header view**.</span></span>

4.  <span data-ttu-id="c7aff-125">På snabbfliken **adress** klicka på **Annan adress**.</span><span class="sxs-lookup"><span data-stu-id="c7aff-125">On the **Address** FastTab, click **Other address**.</span></span>

5.  <span data-ttu-id="c7aff-126">I formuläret **Val av adress** i fältet **posttyp** väljer du **serviceorder**.</span><span class="sxs-lookup"><span data-stu-id="c7aff-126">In the **Address selection** form, in the **Record type** field, select **Service orders**.</span></span>

6.  <span data-ttu-id="c7aff-127">Välj en adress och klicka sedan på **OK** om du vill kopiera den till din serviceorder.</span><span class="sxs-lookup"><span data-stu-id="c7aff-127">Select an address, and then click **OK** to copy it to your service order.</span></span>


  


