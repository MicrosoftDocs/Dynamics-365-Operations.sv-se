---
title: Skapa en serviceorder manuellt
description: Du kan skapa serviceorder manuellt med hjälp av ett serviceavtal eller med formuläret **Serviceorder**.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 51cfdb94a368df9e7082af3c768c79df44000342
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437695"
---
# <a name="create-service-orders-manually"></a><span data-ttu-id="67210-103">Skapa en serviceorder manuellt</span><span class="sxs-lookup"><span data-stu-id="67210-103">Create service orders manually</span></span>    

[!include [banner](../includes/banner.md)]


<span data-ttu-id="67210-104">Du kan skapa serviceorder manuellt med hjälp av ett serviceavtal eller med formuläret **Serviceorder**.</span><span class="sxs-lookup"><span data-stu-id="67210-104">You can create service orders manually by using a service agreement or by using the **Service orders** form.</span></span> <span data-ttu-id="67210-105">Du kan även skapa en serviceorder från ett projekt.</span><span class="sxs-lookup"><span data-stu-id="67210-105">You can also create a service order from a project.</span></span>

> [!TIP]
> <P><span data-ttu-id="67210-106">Du kan använda automatiserade processer för att skapa serviceorder.</span><span class="sxs-lookup"><span data-stu-id="67210-106">You can use automated processes to create service orders.</span></span> 

## <a name="create-a-service-order-manually-from-a-service-agreement"></a><span data-ttu-id="67210-107">Skapa en serviceorder manuellt från serviceavtalet</span><span class="sxs-lookup"><span data-stu-id="67210-107">Create a service order manually from a service agreement</span></span>

1.  <span data-ttu-id="67210-108">Klicka på **servicehantering** \> **allmänt** \> **serviceavtal** \> **serviceavtal**.</span><span class="sxs-lookup"><span data-stu-id="67210-108">Click **Service management** \> **Common** \> **Service agreements** \> **Service agreements**.</span></span>

2.  <span data-ttu-id="67210-109">Välj ett serviceavtal eller skapa ett nytt.</span><span class="sxs-lookup"><span data-stu-id="67210-109">Select a service agreement or create a new service agreement.</span></span>

3.  <span data-ttu-id="67210-110">Klicka på fliken **leverera** och gruppen **skapa**, klicka **planerade serviceorder** för att öppna formuläret **skapa serviceorder**.</span><span class="sxs-lookup"><span data-stu-id="67210-110">Click the **Deliver** tab and in the **Create** group click **Planned service orders** to open the **Create service orders** form.</span></span>

## <a name="create-a-service-order-manually-in-the-service-orders-form"></a><span data-ttu-id="67210-111">Skapa en serviceorder manuellt i formuläret för serviceorder</span><span class="sxs-lookup"><span data-stu-id="67210-111">Create a service order manually in the Service orders form</span></span>

1.  <span data-ttu-id="67210-112">Klicka på noden **Servicehantering** \> **Vanligt** \> **Serviceorder** \> **Serviceorder**.</span><span class="sxs-lookup"><span data-stu-id="67210-112">Click **Service management** \> **Common** \> **Service orders** \> **Service orders**.</span></span>

2.  <span data-ttu-id="67210-113">Tryck på CTRL+N om du vill skapa en ny serviceorder.</span><span class="sxs-lookup"><span data-stu-id="67210-113">Press Ctrl+N to create a new service order.</span></span>

3.  <span data-ttu-id="67210-114">Skapa serviceorderrader för serviceordern.</span><span class="sxs-lookup"><span data-stu-id="67210-114">Create service order lines for the service order.</span></span>

> [!NOTE]
> <P><span data-ttu-id="67210-115">Om kryssrutan <STRONG>Tillåt utan serviceavtal</STRONG> i formuläret <STRONG>Servicehanteringsparametrar</STRONG> är markerad kan du bokföra transaktionerna från serviceorderraderna utan att koppla serviceordern till ett serviceavtal.</span><span class="sxs-lookup"><span data-stu-id="67210-115">If the <STRONG>Allow without service agreement</STRONG> check box in the <STRONG>Service management parameters</STRONG> form is selected, you can post the transactions from the service order lines without attaching the service order to a service agreement.</span></span> <span data-ttu-id="67210-116">Om kryssrutan är avmarkerad måste du knyta den manuellt skapade serviceordern till ett projekt innan du kan bokföra serviceorderraderna.</span><span class="sxs-lookup"><span data-stu-id="67210-116">If the check box is cleared, you must attach the manually created service order to a project before posting the service order lines.</span></span></P>

## <a name="create-a-service-order-from-a-project"></a><span data-ttu-id="67210-117">Skapa en serviceorder från Projekt</span><span class="sxs-lookup"><span data-stu-id="67210-117">Create a service order from a project</span></span>

1.  <span data-ttu-id="67210-118">Klicka på **Projekthantering och redovisning** \> **Vanligt** \> **Projekt** \> **Alla projekt**.</span><span class="sxs-lookup"><span data-stu-id="67210-118">Click **Project management and accounting** \> **Common** \> **Projects** \> **All projects**.</span></span>

2.  <span data-ttu-id="67210-119">I formuläret **Projekt** i **åtgärdsfönstret** klickar du på fliken **Hantera** \> och **Service** \> **Serviceorder**.</span><span class="sxs-lookup"><span data-stu-id="67210-119">In the **Projects** form, on the **Action Pane**, click the **Manage** tab \> click **Service** \> **Service orders**.</span></span>

3.  <span data-ttu-id="67210-120">Följ tidigare procedur för att skapa en serviceorder manuellt i formuläret **Serviceorder**.</span><span class="sxs-lookup"><span data-stu-id="67210-120">Follow the previous procedure to create a service order manually in the **Service orders** form.</span></span> <span data-ttu-id="67210-121">Fältet **Projekt-ID**, visar projektreferensen.</span><span class="sxs-lookup"><span data-stu-id="67210-121">The **Project ID** field displays the project reference.</span></span>

> [!NOTE]
> <P><span data-ttu-id="67210-122">Om kryssrutan <STRONG>Tillåt utan serviceavtal</STRONG> i formuläret <STRONG>Servicehanteringsparametrar</STRONG> är markerad kan du bokföra transaktionerna från serviceorderraderna utan att koppla serviceordern till ett serviceavtal.</span><span class="sxs-lookup"><span data-stu-id="67210-122">If the <STRONG>Allow without service agreement</STRONG> check box in the <STRONG>Service management parameters</STRONG> form is selected, you can post the transactions from the service order lines without attaching the service order to a service agreement.</span></span> <span data-ttu-id="67210-123">Om kryssrutan är avmarkerad måste du knyta den manuellt skapade serviceordern till ett projekt innan du kan bokföra serviceorderraderna.</span><span class="sxs-lookup"><span data-stu-id="67210-123">If the check box is cleared, you must attach the manually created service order to a project before posting the service order lines.</span></span></P>

## <a name="create-a-service-order-from-the-sales-order-form"></a><span data-ttu-id="67210-124">Skapa serviceorder från en försäljningsorderformuläret</span><span class="sxs-lookup"><span data-stu-id="67210-124">Create a service order from the Sales order form</span></span>

<span data-ttu-id="67210-125">Du kan skapa en serviceorder från formuläret **försäljningsorder** genom att använda guiden **skapa en ny serviceorder baserat på försäljningsordern**.</span><span class="sxs-lookup"><span data-stu-id="67210-125">You can create a service order from the **Sales orders** form by using the **Create a new service order based on the sales order** wizard.</span></span>

1.  <span data-ttu-id="67210-126">Klicka på **Försäljning och marknadsföring** \> **Allmänt** \> **Försäljningsorder** \> **Alla försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="67210-126">Click **Sales and marketing** \> **Common** \> **Sales orders** \> **All sales orders**.</span></span>

2.  <span data-ttu-id="67210-127">Öppna relevant försäljningsordern.</span><span class="sxs-lookup"><span data-stu-id="67210-127">Open the relevant sales order.</span></span>

3.  <span data-ttu-id="67210-128">På fliken **försäljningsorder**, klicka på **Serviceorder** för att starta guiden **Skapa en ny serviceorder baserat på försäljningsordern**.</span><span class="sxs-lookup"><span data-stu-id="67210-128">On the **Sales order** tab, click **Service order** to start the **Create a new service order based on the sales order** wizard.</span></span>

4.  <span data-ttu-id="67210-129">Klicka på **nästa \>**, och gör sedan följande steg på sidan **Välj avtal för serviceorder**:</span><span class="sxs-lookup"><span data-stu-id="67210-129">Click **Next \>**, and then complete the following steps on the **Select agreement for service order** page:</span></span>
    
      - <span data-ttu-id="67210-130">Använd fältet **Serviceavtal** för att välja det nya serviceavtal som den nya serviceordern ska kopplas till.</span><span class="sxs-lookup"><span data-stu-id="67210-130">Use the **Service agreement** field to select the service agreement with which the new service order should be associated.</span></span>
    
      - <span data-ttu-id="67210-131">Valfritt: Använd fältet **Projekt-ID** och koppla serviceordern till ett projekt.</span><span class="sxs-lookup"><span data-stu-id="67210-131">Optional: Use the **Project ID** field to associate this service order with a particular project.</span></span>

5.  <span data-ttu-id="67210-132">Klicka på **nästa \>**, och gör sedan följande steg på sidan **Skapa serviceorder**:</span><span class="sxs-lookup"><span data-stu-id="67210-132">Click **Next \>**, and then complete the following steps on the **Create service order** page:</span></span>
    
      - <span data-ttu-id="67210-133">Ange datum och tid då servicesamtalet ska inledas i fältet **Prioriterad servicetid**.</span><span class="sxs-lookup"><span data-stu-id="67210-133">Enter a date and time for the service call to begin in the **Preferred service time** field.</span></span>
    
      - <span data-ttu-id="67210-134">Valfritt: Ändra texten i fältet **Beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="67210-134">Optional: Modify the text in the **Description** field.</span></span> <span data-ttu-id="67210-135">Som standard innehåller detta fält en beskrivning av det serviceavtal som du valde på föregående sida.</span><span class="sxs-lookup"><span data-stu-id="67210-135">By default, this field contains the description of the service agreement that you selected on the previous page.</span></span>
    
      - <span data-ttu-id="67210-136">I fältet **Ansvarig** väljer du sedan ID:t på den medarbetare som ansvarar för avtalet och, om du känner till det, ID:t på den tekniker som kunden vill ska genomföra servicesamtalet.</span><span class="sxs-lookup"><span data-stu-id="67210-136">In the **Responsible** field, select the ID of the employee who is responsible for the agreement, and if you know what it is, enter the ID of the customer's preferred technician for the service call.</span></span>
    
      - <span data-ttu-id="67210-137">I fältet **Kontakt-ID** väljer du person i kundens företag som ska kontaktas för denna serviceorder.</span><span class="sxs-lookup"><span data-stu-id="67210-137">In the **Contact ID** field, select the person in the customer's company who should be contacted regarding this service order.</span></span>

6.  <span data-ttu-id="67210-138">Klicka på **Nästa\>** och klicka sedan på **Slutför**.</span><span class="sxs-lookup"><span data-stu-id="67210-138">Click **Next \>**, and then click **Finish**.</span></span>


## <a name="see-also"></a><span data-ttu-id="67210-139">Se även</span><span class="sxs-lookup"><span data-stu-id="67210-139">See also</span></span>

[<span data-ttu-id="67210-140">Serviceorder</span><span class="sxs-lookup"><span data-stu-id="67210-140">Service orders</span></span>](service-orders.md)

[<span data-ttu-id="67210-141">Skapa serviceorder automatiskt</span><span class="sxs-lookup"><span data-stu-id="67210-141">Create service orders automatically</span></span>](create-service-orders-automatically.md)

<span data-ttu-id="67210-142">[Skapa serviceorder (klassformulär)](https://technet.microsoft.com/library/aa553901\(v=ax.60\))</span><span class="sxs-lookup"><span data-stu-id="67210-142">[Create service orders (class form)](https://technet.microsoft.com/library/aa553901\(v=ax.60\))</span></span> 

