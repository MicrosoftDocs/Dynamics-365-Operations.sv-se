---
title: Avbryt serviceorder
description: "Du kan avbryta en serviceorder eller serviceorderrad från själva serviceordern, och du kan avbryta flera serviceorder genom att köra ett periodiskt jobb."
author: YuyuScheller
manager: AnnBe
ms.date: 05/01/2018
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
ms.openlocfilehash: 8e5ad119c28bba18b75bb5ed7854e94a4e734d55
ms.contentlocale: sv-se
ms.lasthandoff: 05/08/2018

---

# <a name="cancel-service-orders"></a><span data-ttu-id="1c3c9-103">Avbryt serviceorder</span><span class="sxs-lookup"><span data-stu-id="1c3c9-103">Cancel service orders</span></span>   

[!include [banner](../includes/banner.md)]


<span data-ttu-id="1c3c9-104">Du kan avbryta en serviceorder eller serviceorderrad från själva serviceordern, och du kan avbryta flera serviceorder genom att köra ett periodiskt jobb.</span><span class="sxs-lookup"><span data-stu-id="1c3c9-104">You can cancel a service order or service order line from the service order itself, or you can cancel multiple service orders by running a periodic job.</span></span>


> [!NOTE]
> <P><span data-ttu-id="1c3c9-105">Du kan inte avbryta en serviceorder om detta inte är tillåtet i serviceorderns aktuella fas, om serviceordern innehåller artikelbehov eller om serviceordern redan har bokförts.</span><span class="sxs-lookup"><span data-stu-id="1c3c9-105">Service orders cannot be canceled if the stage of the service order does not allow cancelation, if the service order has item requirements, or if the service order has already been posted.</span></span></P>


## <a name="cancel-a-service-order-in-the-service-orders-form"></a><span data-ttu-id="1c3c9-106">Avbryta en serviceorder i formuläret för serviceorder</span><span class="sxs-lookup"><span data-stu-id="1c3c9-106">Cancel a service order in the Service orders form</span></span>

1.  <span data-ttu-id="1c3c9-107">Klicka på noden **Servicehantering** \> **Vanligt** \> **Serviceorder** \> **Serviceorder**.</span><span class="sxs-lookup"><span data-stu-id="1c3c9-107">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span> <span data-ttu-id="1c3c9-108">Välj serviceorder och klicka sedan på **Avbryt order** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="1c3c9-108">Select the service order, and on the Action Pane, click **Cancel order**.</span></span>

## <a name="cancel-a-service-order-line"></a><span data-ttu-id="1c3c9-109">Avbryta en serviceorderrad</span><span class="sxs-lookup"><span data-stu-id="1c3c9-109">Cancel a service order line</span></span>

1.  <span data-ttu-id="1c3c9-110">Klicka på noden **Servicehantering** \> **Vanligt** \> **Serviceorder** \> **Serviceorder**.</span><span class="sxs-lookup"><span data-stu-id="1c3c9-110">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span> <span data-ttu-id="1c3c9-111">Dubbelklicka på den serviceorder som innehåller raden du vill annullera.</span><span class="sxs-lookup"><span data-stu-id="1c3c9-111">Double-click the service order that contains the line you want to cancel.</span></span>

2.  <span data-ttu-id="1c3c9-112">Välj serviceorderraden som du vill avbryta och klicka sedan på **Avbryt orderrad** för att ändra status för raden till **Har avbrutits**.</span><span class="sxs-lookup"><span data-stu-id="1c3c9-112">Select the service order line that you want to cancel, and then click **Cancel order line** to change the status of the line to **Canceled**.</span></span>


> [!TIP]
> <P><span data-ttu-id="1c3c9-113">Om du vill återkalla annulleringen av en serviceorderrad och ändra tillbaka status till <STRONG>Skapad</STRONG>, klickar du på <STRONG>Återkalla avbrott</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="1c3c9-113">To reverse the cancellation of a service order line and change the status back to <STRONG>Created</STRONG>, click <STRONG>Revoke cancel</STRONG>.</span></span></P>


## <a name="cancel-multiple-service-orders"></a><span data-ttu-id="1c3c9-114">Avbryta flera serviceorder</span><span class="sxs-lookup"><span data-stu-id="1c3c9-114">Cancel multiple service orders</span></span>

1.  <span data-ttu-id="1c3c9-115">Klicka på **Servicehantering**\>**Periodisk**\>**Serviceorder**\>**Avbryt serviceorder**.</span><span class="sxs-lookup"><span data-stu-id="1c3c9-115">Click **Service management** \> **Periodic** \> **Service orders** \> **Cancel service orders**.</span></span>

2.  <span data-ttu-id="1c3c9-116">Klicka på **Välj**.</span><span class="sxs-lookup"><span data-stu-id="1c3c9-116">Click the **Select** button.</span></span>

3.  <span data-ttu-id="1c3c9-117">I formuläret **Förfrågan** i kolumnen **Kriterier** väljer du de serviceorder som du vill avbryta.</span><span class="sxs-lookup"><span data-stu-id="1c3c9-117">In the **Inquiry** form, in the **Criteria** column, select the service orders that you want to cancel.</span></span>

4.  <span data-ttu-id="1c3c9-118">Klicka på **OK** när du vill stänga formuläret **Förfrågan**.</span><span class="sxs-lookup"><span data-stu-id="1c3c9-118">Click **OK** to close the **Inquiry** form.</span></span>

5.  <span data-ttu-id="1c3c9-119">Markera kryssrutan **Visa informationslogg** om du vill skapa en informationslogg som anger avbrutna serviceorder.</span><span class="sxs-lookup"><span data-stu-id="1c3c9-119">Select the **Show Infolog** check box to generate an Infolog that lists the canceled service orders.</span></span>

6.  <span data-ttu-id="1c3c9-120">Markera kryssrutan **Återkalla avbrott** om du vill återkalla statusen **Har avbrutits** för en serviceorder.</span><span class="sxs-lookup"><span data-stu-id="1c3c9-120">Select the **Revoke cancel** check box if you want to reverse the **Canceled** status of a service order.</span></span>

7.  <span data-ttu-id="1c3c9-121">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="1c3c9-121">Click **OK**.</span></span>

<span data-ttu-id="1c3c9-122">Markerade serviceorder kommer då antingen att annulleras eller få sin status **Har avbrutits** ändrad till **Pågår**.</span><span class="sxs-lookup"><span data-stu-id="1c3c9-122">The selected service orders are either canceled or their progress status of **Canceled** has been reversed to **In process**.</span></span>


> [!NOTE]
> <P><span data-ttu-id="1c3c9-123">Om du markerar kryssrutan <STRONG>Återkalla avbrott</STRONG> kommer serviceorder med statusen <STRONG>Har avbrutits</STRONG> att återkallas och inga serviceorder med statusen <STRONG>Pågår</STRONG> avbryts.</span><span class="sxs-lookup"><span data-stu-id="1c3c9-123">If you select the <STRONG>Revoke cancel</STRONG> check box, service orders with a progress status of <STRONG>Canceled</STRONG> are reversed and service orders with a progress status of <STRONG>In process</STRONG> are not canceled.</span></span></P>


  



