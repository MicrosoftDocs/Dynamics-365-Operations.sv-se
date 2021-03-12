---
title: Skapa en artikelersättningsorder
description: Ersättningsorder skapas vanligtvis efter att en produkt har returnerats och inspekterats.
author: josaw1
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReturnTableListPage, ReturnReplaceItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c0006ea9ec64cd95a709ec91509cb3a9828df160
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4996661"
---
# <a name="create-an-item-replacement-order"></a><span data-ttu-id="fdf4b-103">Skapa en artikelersättningsorder</span><span class="sxs-lookup"><span data-stu-id="fdf4b-103">Create an item replacement order</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="fdf4b-104">Ersättningsorder skapas vanligtvis efter att en produkt har returnerats och inspekterats.</span><span class="sxs-lookup"><span data-stu-id="fdf4b-104">Item replacement orders are usually created after a product is returned and inspected.</span></span> <span data-ttu-id="fdf4b-105">Om en artikel måste ersättas innan den returneras eller om artikeln inte kommer att returneras kan du emellertid skapa en ersättningsorder omedelbart efter att du har skapat en returorder.</span><span class="sxs-lookup"><span data-stu-id="fdf4b-105">However, when an item must be replaced before it has been returned, or when the original item will not be returned, you can create an item replacement order immediately after you create a return order.</span></span>

## <a name="create-a-replacement-order-after-you-receive-an-item-that-is-returned"></a><span data-ttu-id="fdf4b-106">Skapa en ersättningsorder efter att du har tagit emot en artikel som returneras</span><span class="sxs-lookup"><span data-stu-id="fdf4b-106">Create a replacement order after you receive an item that is returned</span></span>

1.  <span data-ttu-id="fdf4b-107">Klicka på **Försäljning och marknadsföring** \> **Returorder** \> **Alla returorder** \> **Alla försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="fdf4b-107">Click **Sales and marketing** \> **Common** \> **Return orders** \> **All return orders**.</span></span>

2.  <span data-ttu-id="fdf4b-108">Skapa en ny returorder eller välj en returnerad order i listan för att öppna formuläret **Returorder - RMA-nummer: %1, %2**.</span><span class="sxs-lookup"><span data-stu-id="fdf4b-108">Create a new return order, or select a returned order from the list to open the **Return order - RMA number: %1, %2** form.</span></span>

3.  <span data-ttu-id="fdf4b-109">Klicka på **rad**, och välj sedan **ersättningsartikeln**.</span><span class="sxs-lookup"><span data-stu-id="fdf4b-109">Click **Return line**, and then select **Replacement item**.</span></span>

4.  <span data-ttu-id="fdf4b-110">Välj artikeln som ska ersätta den returnerade artikeln med.</span><span class="sxs-lookup"><span data-stu-id="fdf4b-110">Select the item to replace the returned item with.</span></span> <span data-ttu-id="fdf4b-111">Ange artikelspecifikationerna och klicka sedan på **Verkställ**.</span><span class="sxs-lookup"><span data-stu-id="fdf4b-111">Enter the item specifications, and then click **Apply**.</span></span>

5.  <span data-ttu-id="fdf4b-112">Klicka på **Följesedel** för att generera följesedeln för returordern.</span><span class="sxs-lookup"><span data-stu-id="fdf4b-112">Click **Packing slip** to generate the packing slip for the return order.</span></span> <span data-ttu-id="fdf4b-113">En försäljningsorder skapas för ersättningsartikeln du har valt.</span><span class="sxs-lookup"><span data-stu-id="fdf4b-113">A sales order is generated for the replacement item that you selected.</span></span>
    
    <span data-ttu-id="fdf4b-114">Efter att försäljningsordern har skapats för ersättningsartikeln, försäljningsavtal söks automatiskt och, om det finns en lämplig försäljningsavtal, används den till försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="fdf4b-114">After the sales order is created for the replacement item, sales agreements are automatically searched and if there is an applicable sales agreement, it is applied to the sales order.</span></span>

## <a name="create-a-replacement-order-before-you-receive-an-item-that-will-be-returned"></a><span data-ttu-id="fdf4b-115">Skapa en ersättningsorder, innan du tar emot en artikel som ska returneras</span><span class="sxs-lookup"><span data-stu-id="fdf4b-115">Create a replacement order before you receive an item that will be returned</span></span>

1.  <span data-ttu-id="fdf4b-116">Klicka på **Försäljning och marknadsföring** \> **Returorder** \> **Alla returorder** \> **Alla försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="fdf4b-116">Click **Sales and marketing** \> **Common** \> **Return orders** \> **All return orders**.</span></span>

2.  <span data-ttu-id="fdf4b-117">Skapa en ny returorder eller välj en returorder i listan för att öppna formuläret **Returorder - RMA-nummer: %1, %2**.</span><span class="sxs-lookup"><span data-stu-id="fdf4b-117">Create a new return order, or select a return order from the list to open the **Return order - RMA number: %1, %2** form.</span></span>

3.  <span data-ttu-id="fdf4b-118">Klicka på **Hitta försäljningsorder** om du vill identifiera försäljningsordern för den returnerade artikeln.</span><span class="sxs-lookup"><span data-stu-id="fdf4b-118">Click **Find sales order** if you want to identify the sales order for the returned item.</span></span> <span data-ttu-id="fdf4b-119">Slutför formuläret **söka efter försäljningsorder** och klicka på **OK** för att stänga formuläret och återgå till formuläret **returorder - RMA-nummer: %1, %2**.</span><span class="sxs-lookup"><span data-stu-id="fdf4b-119">Complete the **Find sales order** form and then click **OK** to close the form and return to the **Return order - RMA number: %1, %2** form.</span></span> <span data-ttu-id="fdf4b-120">Försäljningsorderraden för den returnerade artikeln kopieras till returordern.</span><span class="sxs-lookup"><span data-stu-id="fdf4b-120">The sales order line for the returned item is copied to the return order.</span></span>

4.  <span data-ttu-id="fdf4b-121">Klicka på **Ersättningsorder** för att öppna formuläret **Skapa försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="fdf4b-121">Click **Replacement order** to open the **Create sales order** form.</span></span>

5.  <span data-ttu-id="fdf4b-122">Markera kryssrutan **Kopiera returorderrader** för att överföra detaljer från den returorder som du markerade på formuläret **Returorder - RMA-nummer: %1, %2** till den här försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="fdf4b-122">Select the **Copy return order lines** check box to transfer details from the return order you selected on the **Return order - RMA number: %1, %2** form to this sales order.</span></span>

6.  <span data-ttu-id="fdf4b-123">Ange eller ändra detaljer vid behov.</span><span class="sxs-lookup"><span data-stu-id="fdf4b-123">Enter or modify details, as required.</span></span>
    
    <span data-ttu-id="fdf4b-124">Om du identifierar försäljningsordern i steg 3 och om försäljningsorderraden för returnerade artikeln är kopplad till en försäljningsavtal, kommer identifieraren för den tillämpliga försäljningsavtalet för artikelutbytesordern automatiskt visas i fältet **Försäljningsavtals-ID**.</span><span class="sxs-lookup"><span data-stu-id="fdf4b-124">If you identified the sales order in step 3, and if the sales order line for the returned item is linked to a sales agreement, the identifier of the applicable sales agreement for the item replacement order will be automatically displayed in the **Sales agreement ID** field.</span></span>

7.  <span data-ttu-id="fdf4b-125">Klicka på **OK** för att stänga **Skapa försäljningsorder** och öppna formuläret **Försäljningsorder** där du kan fortsätta att ange information för den nya försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="fdf4b-125">Click **OK** to close the **Create sales order** form and open the **Sales order** form, where you can continue to enter information for the new sales order.</span></span> <span data-ttu-id="fdf4b-126">Vissa tillämpliga returorderrader ska kopieras till den nya försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="fdf4b-126">Any applicable return order lines will be copied to the new sales order.</span></span> 
    
    <span data-ttu-id="fdf4b-127">Om identifieraren för försäljningsavtalet visas automatiskt i fältet **Försäljningsavtals-ID** har försäljningsavtalet länkats till försäljningsorderrubriken för artikelutbytesordern.</span><span class="sxs-lookup"><span data-stu-id="fdf4b-127">If the identifier of the sales agreement is automatically displayed in the **Sales agreement ID** field, then the sales agreement has been linked to the sales order header for the item replacement order.</span></span> <span data-ttu-id="fdf4b-128">Om det finns en lämplig åtagande i försäljningsavtalet som ännu inte har fullgjorts, och försäljningsorder skapas före försäljningsavtalet går ut, skapas en koppling mellan försäljningsavtalraden och försäljningsorderraden.</span><span class="sxs-lookup"><span data-stu-id="fdf4b-128">If there is an applicable commitment in the sales agreement that has not been fulfilled yet, and the sales order is created before the sales agreement expires, a link is established between the sales agreement line and the sales order line.</span></span> <span data-ttu-id="fdf4b-129">Därför information kopieras från försäljningsavtalet, till exempel artikelpris, till den nya försäljningsorderraden.</span><span class="sxs-lookup"><span data-stu-id="fdf4b-129">Therefore, information from the sales agreement, such as item price, is copied to the new sales order line.</span></span> 
  


