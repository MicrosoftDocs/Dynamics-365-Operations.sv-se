---
title: Skapa serviceorder automatiskt
description: "Du kan skapa serviceorder, antingen för ett serviceavtal eller för flera serviceavtal."
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
ms.openlocfilehash: c39e5b5eb79859b0a76c357edfee953ca90c0c4a
ms.contentlocale: sv-se
ms.lasthandoff: 05/08/2018

---

# <a name="create-service-orders-automatically"></a><span data-ttu-id="ffcff-103">Skapa serviceorder automatiskt</span><span class="sxs-lookup"><span data-stu-id="ffcff-103">Create service orders automatically</span></span>    

[!include [banner](../includes/banner.md)]


<span data-ttu-id="ffcff-104">Du kan skapa serviceorder, antingen för ett serviceavtal eller för flera serviceavtal.</span><span class="sxs-lookup"><span data-stu-id="ffcff-104">You can create service orders for one service agreement or for several service agreements.</span></span> <span data-ttu-id="ffcff-105">När du har skapat dem kan du visa dina serviceorder i formuläret **Serviceorder**.</span><span class="sxs-lookup"><span data-stu-id="ffcff-105">When they are created, you can view your service orders in the **Service orders** form.</span></span>

<span data-ttu-id="ffcff-106">Serviceorder skapas bara för serviceavtalets giltighetsperiod.</span><span class="sxs-lookup"><span data-stu-id="ffcff-106">Service orders are created only for the valid period of the service agreement.</span></span> <span data-ttu-id="ffcff-107">Om det intervall som du anger i dialogrutan **Skapa serviceorder** ligger före serviceavtalets startdatum eller efter dess slutdatum, skapas bara serviceorder för den del av intervallet som överensstämmer med serviceavtalet.</span><span class="sxs-lookup"><span data-stu-id="ffcff-107">If the interval that you specify in the **Create service orders** form is before the starting date or after the ending date of the service agreement, service orders are created only for the part of the interval that is within the service agreement dates.</span></span>

<span data-ttu-id="ffcff-108">När du skapar serviceorder manuellt eller automatiskt från serviceavtalsraden, måste serviceordern infalla inom det tidsintervall som definieras av start- och slutdatumen för raden, såvida du inte anger något slutdatum på raden.</span><span class="sxs-lookup"><span data-stu-id="ffcff-108">When you create service orders manually or automatically from the service agreement line, the service order must be in the time interval that is defined by the starting and ending dates for the line, unless you do not specify an ending date on the line.</span></span>

## <a name="create-service-orders-automatically-for-a-service-agreement"></a><span data-ttu-id="ffcff-109">Skapa serviceorder automatiskt för ett serviceavtal</span><span class="sxs-lookup"><span data-stu-id="ffcff-109">Create service orders automatically for a service agreement</span></span>

1.  <span data-ttu-id="ffcff-110">Klicka på **servicehantering** \> **allmänt** \> **serviceavtal** \> **serviceavtal**.</span><span class="sxs-lookup"><span data-stu-id="ffcff-110">Click **Service management** \> **Common** \> **Service agreements** \> **Service agreements**.</span></span>

2.  <span data-ttu-id="ffcff-111">Välj ett serviceavtal.</span><span class="sxs-lookup"><span data-stu-id="ffcff-111">Select a service agreement.</span></span>

3.  <span data-ttu-id="ffcff-112">Klicka på fliken **Leverera** och klicka på fliken **planerade serviceorder**.</span><span class="sxs-lookup"><span data-stu-id="ffcff-112">Click the **Deliver** tab, and then click **Planned service orders**.</span></span>

4.  <span data-ttu-id="ffcff-113">Ange datum i fälten **Från datum** och **Till datum** för att definiera serviceperioden.</span><span class="sxs-lookup"><span data-stu-id="ffcff-113">Specify dates in the **From date** and **To date** fields to define the service period.</span></span>

5.  <span data-ttu-id="ffcff-114">Välj kryssrutan **Visa informationslogg** om du vill visa en lista med de serviceorder som skapas.</span><span class="sxs-lookup"><span data-stu-id="ffcff-114">Select the **Show Infolog** check box to display a list of the service orders that are created.</span></span>

6.  <span data-ttu-id="ffcff-115">Välj transaktionstyper i fältgruppen **Inkludera transaktionstyper**.</span><span class="sxs-lookup"><span data-stu-id="ffcff-115">Select transaction types in the **Include transaction types** field group.</span></span> <span data-ttu-id="ffcff-116">Transaktionstyperna representerar raderna som skapas i serviceavtalet och varje transaktionstyp som du väljer genererar flera serviceorder, beroende på vilket serviceintervall som finns angivet på serviceavtalsraden.</span><span class="sxs-lookup"><span data-stu-id="ffcff-116">The transaction types represent the lines that are created in the service agreement, and each transaction type that you select generates several service orders, depending on the service interval that is specified on the service agreement line.</span></span>

7.  <span data-ttu-id="ffcff-117">Markera kryssrutan **Kontinuerlig** om du vill skapa sådana serviceorder som saknas inom en kontinuerlig serie av serviceorder .</span><span class="sxs-lookup"><span data-stu-id="ffcff-117">To create any service orders that are missing from continuous series of service orders, select the **Continuous** check box.</span></span>

8.  <span data-ttu-id="ffcff-118">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="ffcff-118">Click **OK**.</span></span>

## <a name="create-service-orders-automatically-for-several-service-agreements"></a><span data-ttu-id="ffcff-119">Skapa serviceorder automatiskt för flera serviceavtal</span><span class="sxs-lookup"><span data-stu-id="ffcff-119">Create service orders automatically for several service agreements</span></span>

1.  <span data-ttu-id="ffcff-120">Klicka på **Servicehantering**\>**Periodisk**\>**Serviceorder**\>**Skapa serviceorder**.</span><span class="sxs-lookup"><span data-stu-id="ffcff-120">Click **Service management** \> **Periodic** \> **Service orders** \> **Create service orders**.</span></span>

2.  <span data-ttu-id="ffcff-121">Klicka på **Välj** för att välja alternativ för att lägga till eller ta bort kriterier för att skapa serviceorder.</span><span class="sxs-lookup"><span data-stu-id="ffcff-121">Click **Select** to make selections to add or remove criteria to use to create service orders.</span></span>

3.  <span data-ttu-id="ffcff-122">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="ffcff-122">Click **OK**.</span></span>

## <a name="see-also"></a><span data-ttu-id="ffcff-123">Se även</span><span class="sxs-lookup"><span data-stu-id="ffcff-123">See also</span></span>

[<span data-ttu-id="ffcff-124">Serviceorder</span><span class="sxs-lookup"><span data-stu-id="ffcff-124">Service orders</span></span>](service-orders.md)

[<span data-ttu-id="ffcff-125">Skapa serviceorder automatiskt</span><span class="sxs-lookup"><span data-stu-id="ffcff-125">Automatically creating service orders</span></span>](auto-create-service-orders.md)

  


