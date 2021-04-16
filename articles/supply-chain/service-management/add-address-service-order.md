---
title: Lägg till en adress till en serviceorder
description: I det här avsnittet beskrivs hur du lägger till en kundadress till en serviceorder.
author: ShylaThompson
ms.date: 05/02/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a54ec439fc88dc9688bbb3d6b833b5d80482f024
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5824664"
---
# <a name="add-an-address-to-a-service-order"></a><span data-ttu-id="b0559-103">Lägg till en adress till en serviceorder</span><span class="sxs-lookup"><span data-stu-id="b0559-103">Add an address to a service order</span></span>    

[!include [banner](../includes/banner.md)]


<span data-ttu-id="b0559-104">I det här avsnittet beskrivs hur du lägger till en kundadress till en serviceorder.</span><span class="sxs-lookup"><span data-stu-id="b0559-104">This topic describes how to add a customer address to a service order.</span></span> <span data-ttu-id="b0559-105">När du skapar en serviceorder förs adressinformationen över från det projekt som serviceordern är kopplad till.</span><span class="sxs-lookup"><span data-stu-id="b0559-105">When you create a service order, the address information is transferred from the project that the service order is attached to.</span></span> <span data-ttu-id="b0559-106">Du kan dock välja en alternativ plats från adresser som redan finns i Microsoft Dynamics AX för kunder, leverantörer, platser, lagerställen, serviceorder och projekt.</span><span class="sxs-lookup"><span data-stu-id="b0559-106">However, you can select an alternative location from addresses that are already entered in Microsoft Dynamics AX for customers, vendors, sites, warehouses, service orders, and projects.</span></span>

<span data-ttu-id="b0559-107">Du kan också skapa en ny adress.</span><span class="sxs-lookup"><span data-stu-id="b0559-107">You can also create a new address.</span></span> <span data-ttu-id="b0559-108">Som standard överförs den nya adressen till projektet.</span><span class="sxs-lookup"><span data-stu-id="b0559-108">By default, the new address is transferred to the project.</span></span> <span data-ttu-id="b0559-109">Du kan dock ange att den nya adressen bara är relevant för den här instansen av tjänsten.</span><span class="sxs-lookup"><span data-stu-id="b0559-109">However, you can specify that the new address is only relevant for this instance of the service.</span></span> <span data-ttu-id="b0559-110">Om du gör det överförs den nya adressen inte till projektet.</span><span class="sxs-lookup"><span data-stu-id="b0559-110">If you do, the new address is not transferred to the project.</span></span>

## <a name="create-a-customer-address-for-a-service-order"></a><span data-ttu-id="b0559-111">Skapa en kundadress för en serviceorder</span><span class="sxs-lookup"><span data-stu-id="b0559-111">Create a customer address for a service order</span></span>

<span data-ttu-id="b0559-112">Om du vill lägga till en adress till en serviceorder:</span><span class="sxs-lookup"><span data-stu-id="b0559-112">To add an address to a service order, follow these steps:</span></span>

1.  <span data-ttu-id="b0559-113">Klicka på noden **Servicehantering** \> **Vanligt** \> **Serviceorder** \> **Serviceorder**.</span><span class="sxs-lookup"><span data-stu-id="b0559-113">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="b0559-114">Öppna den serviceorder som du vill skapa en adress för.</span><span class="sxs-lookup"><span data-stu-id="b0559-114">Open the service order that you want to create an address for.</span></span>

3.  <span data-ttu-id="b0559-115">I **åtgärdsfönstret**, klicka på **Redigera** och klicka sedan på **Huvudvy**.</span><span class="sxs-lookup"><span data-stu-id="b0559-115">On the **Action Pane**, click **Edit**, and then click **Header view**.</span></span>

4.  <span data-ttu-id="b0559-116">På snabbfliken **adress** klicka på **lägga till adress**.</span><span class="sxs-lookup"><span data-stu-id="b0559-116">On the **Address** FastTab, click **Add address**.</span></span>

5.  <span data-ttu-id="b0559-117">Ange ett unikt namn för adressen och fyll i de återstående fälten i formuläret **Ny adress**.</span><span class="sxs-lookup"><span data-stu-id="b0559-117">In the **New address** form, enter a unique name for the address and complete the remaining fields.</span></span> 
    

    > [!WARNING]
    > <P><span data-ttu-id="b0559-118">Om du anger samma namn som en befintlig adress, kommer informationen som du anger i de återstående fälten skriva över informationen för den befintliga adressen.</span><span class="sxs-lookup"><span data-stu-id="b0559-118">If you enter the same name as an existing address, the information that you enter in the remaining fields will overwrite information for the existing address.</span></span></P>


6.  <span data-ttu-id="b0559-119">Klicka på **OK** för att kopiera den nya adressen till din serviceorder.</span><span class="sxs-lookup"><span data-stu-id="b0559-119">Click **OK** to copy the new address to your service order.</span></span>

## <a name="specify-an-alternative-address-on-a-service-order"></a><span data-ttu-id="b0559-120">Ange en alternativ adress på en serviceorder</span><span class="sxs-lookup"><span data-stu-id="b0559-120">Specify an alternative address on a service order</span></span>

<span data-ttu-id="b0559-121">Om du vill lägga till en alternativ adress till en serviceorder:</span><span class="sxs-lookup"><span data-stu-id="b0559-121">To add an alternative address to a service order, follow these steps:</span></span>

1.  <span data-ttu-id="b0559-122">Klicka på noden **Servicehantering** \> **Vanligt** \> **Serviceorder** \> **Serviceorder**.</span><span class="sxs-lookup"><span data-stu-id="b0559-122">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="b0559-123">Öppna den serviceorder som du vill ange en alternativ adress för.</span><span class="sxs-lookup"><span data-stu-id="b0559-123">Open the service order that you want to enter an alternative address for.</span></span>

3.  <span data-ttu-id="b0559-124">I **åtgärdsfönstret**, klicka på **Redigera** och klicka sedan på **Huvudvy**.</span><span class="sxs-lookup"><span data-stu-id="b0559-124">On the **Action Pane**, click **Edit**, and then click **Header view**.</span></span>

4.  <span data-ttu-id="b0559-125">På snabbfliken **adress** klicka på **Annan adress**.</span><span class="sxs-lookup"><span data-stu-id="b0559-125">On the **Address** FastTab, click **Other address**.</span></span>

5.  <span data-ttu-id="b0559-126">I formuläret **Val av adress** i fältet **posttyp** väljer du **serviceorder**.</span><span class="sxs-lookup"><span data-stu-id="b0559-126">In the **Address selection** form, in the **Record type** field, select **Service orders**.</span></span>

6.  <span data-ttu-id="b0559-127">Välj en adress och klicka sedan på **OK** om du vill kopiera den till din serviceorder.</span><span class="sxs-lookup"><span data-stu-id="b0559-127">Select an address, and then click **OK** to copy it to your service order.</span></span>


  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]