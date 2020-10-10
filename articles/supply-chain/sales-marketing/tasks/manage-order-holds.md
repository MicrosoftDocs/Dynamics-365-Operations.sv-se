---
title: Hantera orderspärrar
description: Denna procedur visar hur du spärrar kundförsäljningsorder, hur du arbetar med utcheckning av spärrade order, samt hur du tar bort orderspärrar.
author: omulvad
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MCRHoldCodeTable, SalesTableListPage, SalesCreateOrder, SalesTable, MCRHoldCodeTrans, MCRHoldCheckOutOverride, MCRHoldCodeTable, MCRItemListCopying, MCRItemListTable, MCROMHoldList
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: edb3c6941af132f9ea1bf9f52f94cd6acc008d6c
ms.sourcegitcommit: 54da65a7da0efd4f0d9760c5b14ff785b28751c4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2020
ms.locfileid: "3830066"
---
# <a name="manage-order-holds"></a><span data-ttu-id="38dfc-103">Hantera orderspärrar</span><span class="sxs-lookup"><span data-stu-id="38dfc-103">Manage order holds</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="38dfc-104">Denna procedur visar hur du spärrar kundförsäljningsorder, hur du arbetar med utcheckning av spärrade order, samt hur du tar bort orderspärrar.</span><span class="sxs-lookup"><span data-stu-id="38dfc-104">This procedure demonstrates how to place customer sales orders on hold, how to work with order hold checkouts, and how to remove order holds.</span></span> <span data-ttu-id="38dfc-105">En order kan spärras av flera olika orsaker.</span><span class="sxs-lookup"><span data-stu-id="38dfc-105">An order might be placed on hold for a variety of reasons.</span></span> <span data-ttu-id="38dfc-106">Du kan till exempel hålla en order tills en kundadress eller betalningsmetod kan bekräftas eller tills en chef kan granska kundens kreditgräns.</span><span class="sxs-lookup"><span data-stu-id="38dfc-106">For example, you might hold an order until a customer address or payment method can be verified or until a manager can review the customer's credit limit.</span></span> <span data-ttu-id="38dfc-107">En spärrad order kan inte behandlas av lagerstället för transport.</span><span class="sxs-lookup"><span data-stu-id="38dfc-107">While the order on hold, it cannot be processed by the warehouse for shipping.</span></span> 

<span data-ttu-id="38dfc-108">Du kan köra den här proceduren i demonstrationsföretaget USMF eller på dina egna data.</span><span class="sxs-lookup"><span data-stu-id="38dfc-108">You can run this procedure in demo data company USMF or on your own data.</span></span>


## <a name="set-up-order-holds"></a><span data-ttu-id="38dfc-109">Ställ in orderspärrar</span><span class="sxs-lookup"><span data-stu-id="38dfc-109">Set up order holds</span></span>
1. <span data-ttu-id="38dfc-110">Gå till **Navigeringsfönster > Moduler > Försäljning och marknadsföring > Inställningar > Försäljningsorder > Koder för spärrad order**.</span><span class="sxs-lookup"><span data-stu-id="38dfc-110">Go to **Navigation pane > Modules > Sales and marketing > Setup > Sales orders > Order hold codes**.</span></span>
2. <span data-ttu-id="38dfc-111">Klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="38dfc-111">Click **New**.</span></span>
3. <span data-ttu-id="38dfc-112">Ange ett värde i fältet **Spärrkod**.</span><span class="sxs-lookup"><span data-stu-id="38dfc-112">In the **Hold code** field, type a value.</span></span> <span data-ttu-id="38dfc-113">Skriv till exempel "Ring tillbaka".</span><span class="sxs-lookup"><span data-stu-id="38dfc-113">For example, type 'Call back'.</span></span>  
4. <span data-ttu-id="38dfc-114">I fältet **Beskrivning** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="38dfc-114">In the **Description** field, type a value.</span></span>
    - <span data-ttu-id="38dfc-115">Till exempel spärrad order som inväntar att kunden ringer tillbaka.</span><span class="sxs-lookup"><span data-stu-id="38dfc-115">For example, Order held waiting for customer callback.</span></span>  
    - <span data-ttu-id="38dfc-116">Du kan också markera kryssrutan **Ta bort reservationer** för att ta bort alla fysiska reservationer från ordern när spärrkoden läggs till.</span><span class="sxs-lookup"><span data-stu-id="38dfc-116">Optionally, select the **Remove reservations** check box to remove any physical reservations from the order when this hold code is added.</span></span>  
5. <span data-ttu-id="38dfc-117">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="38dfc-117">Click **Save**.</span></span>

## <a name="place-order-on-hold"></a><span data-ttu-id="38dfc-118">Spärra order</span><span class="sxs-lookup"><span data-stu-id="38dfc-118">Place order on hold</span></span>
1. <span data-ttu-id="38dfc-119">Gå till **Navigeringsfönster > Moduler > Försäljning och marknadsföring > Försäljningsorder > Alla försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="38dfc-119">Go to **Navigation pane > Modules > Sales and marketing > Sales orders > All sales orders**.</span></span>
2. <span data-ttu-id="38dfc-120">Klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="38dfc-120">Click **New**.</span></span>
3. <span data-ttu-id="38dfc-121">Ange eller välj ett värde i fältet **Kundkonto**.</span><span class="sxs-lookup"><span data-stu-id="38dfc-121">In the **Customer account** field, enter or select a value.</span></span>
4. <span data-ttu-id="38dfc-122">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="38dfc-122">Click **OK**.</span></span>
5. <span data-ttu-id="38dfc-123">I fältet **artikelnummer** anger du eller väljer ett värde.</span><span class="sxs-lookup"><span data-stu-id="38dfc-123">In the **Item number** field, enter or select a value.</span></span>
6. <span data-ttu-id="38dfc-124">Ange ett nummer i fältet **Kvantitet**.</span><span class="sxs-lookup"><span data-stu-id="38dfc-124">In the **Quantity** field, enter a number.</span></span>
7. <span data-ttu-id="38dfc-125">I **åtgärdsrutan**, klicka på **Försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="38dfc-125">On the **Action Pane**, click **Sales order**.</span></span>
8. <span data-ttu-id="38dfc-126">Klicka på **Spärrade order**.</span><span class="sxs-lookup"><span data-stu-id="38dfc-126">Click **Order holds**.</span></span>
9. <span data-ttu-id="38dfc-127">Klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="38dfc-127">Click **New**.</span></span>
10. <span data-ttu-id="38dfc-128">Välj den kod som du har skapat i föregående underaktivitet i kodfältet **Spärrkod**.</span><span class="sxs-lookup"><span data-stu-id="38dfc-128">In the **Hold code** field, select the code you have created in the previous subtask.</span></span>
11. <span data-ttu-id="38dfc-129">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="38dfc-129">Click **Save**.</span></span>
12. <span data-ttu-id="38dfc-130">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="38dfc-130">Close the page.</span></span>
13. <span data-ttu-id="38dfc-131">Gå till **försäljning och marknadsföring > beställningar > alla försäljningsorder**.</span><span class="sxs-lookup"><span data-stu-id="38dfc-131">Go to **Sales and marketing > Sales orders > All sales orders**.</span></span>
14. <span data-ttu-id="38dfc-132">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="38dfc-132">In the list, mark the selected row.</span></span> <span data-ttu-id="38dfc-133">För spärrade order markeras fälten "Behandla inte" och "Spärrad".</span><span class="sxs-lookup"><span data-stu-id="38dfc-133">Orders that are currently on hold have the "Do not process" and "Hold" fields marked.</span></span>
15. <span data-ttu-id="38dfc-134">I åtgärdsrutan, klicka **Plocka och packa**.</span><span class="sxs-lookup"><span data-stu-id="38dfc-134">On the Action Pane, click **Pick and pack**.</span></span>

## <a name="manage-order-holds"></a><span data-ttu-id="38dfc-135">Hantera orderspärrar</span><span class="sxs-lookup"><span data-stu-id="38dfc-135">Manage order holds</span></span>
1. <span data-ttu-id="38dfc-136">Gå till **Försäljning och marknadsföring > Försäljningsorder > Öppna order > Spärrade order**.</span><span class="sxs-lookup"><span data-stu-id="38dfc-136">Go to **Sales and marketing > Sales orders > Open orders > Order holds**.</span></span> <span data-ttu-id="38dfc-137">Sidfunktionerna för **spärrad order** fungerar som en arbetsyta, där du kan få en översikt över alla aktuella och bearbetade spärrningar och hantera dem samt tillhörande försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="38dfc-137">**Order holds** page functions as a workbench where you can get an overview of all the current and processed holds, and handle them and associated sales orders.</span></span>     
2. <span data-ttu-id="38dfc-138">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="38dfc-138">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="38dfc-139">Klicka på **Frisläpp spärr** i **åtgärdsfönstret**.</span><span class="sxs-lookup"><span data-stu-id="38dfc-139">On the **Action Pane**, click **Hold checkout**.</span></span>
4. <span data-ttu-id="38dfc-140">Klicka på **Frisläpp**.</span><span class="sxs-lookup"><span data-stu-id="38dfc-140">Click **Check out**.</span></span>
5. <span data-ttu-id="38dfc-141">Avmarkera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="38dfc-141">In the list, unmark the selected row.</span></span> <span data-ttu-id="38dfc-142">Fältet **Frisläpp till** anger nu ditt användar-ID.</span><span class="sxs-lookup"><span data-stu-id="38dfc-142">The **Checkout out to** field now shows your user ID.</span></span>   
6. <span data-ttu-id="38dfc-143">Klicka på **Rensa frisläpp**.</span><span class="sxs-lookup"><span data-stu-id="38dfc-143">Click **Clear checkout**.</span></span>
7. <span data-ttu-id="38dfc-144">Klicka på **Rensa spärr** i **åtgärdsfönstret**.</span><span class="sxs-lookup"><span data-stu-id="38dfc-144">On the **Action Pane**, click **Clear hold**.</span></span>
    - <span data-ttu-id="38dfc-145">När du vill ta bort spärren och tillåta att ordern går vidare till nästa steg, måste du rensa spärren.</span><span class="sxs-lookup"><span data-stu-id="38dfc-145">When you are ready to remove the hold and allow the order to proceed to the next fulfilment step, you must clear the hold.</span></span> <span data-ttu-id="38dfc-146">Du kan köra åtgärden Rensa spärrar om ordern inte kräver några ändringar.</span><span class="sxs-lookup"><span data-stu-id="38dfc-146">If the order requires no changes, you can run the Clear holds action.</span></span> <span data-ttu-id="38dfc-147">Om ordern måste uppdateras kan du emellertid använda åtgärden Rensa och ändra när du rensar en spärr.</span><span class="sxs-lookup"><span data-stu-id="38dfc-147">However, you can use the Clear and modify action if, when clearing a hold, the order has to be updated.</span></span>      
    - <span data-ttu-id="38dfc-148">Åtgärden **Rensa och skicka in** gäller endast när du använder kundtjänstfunktionerna.</span><span class="sxs-lookup"><span data-stu-id="38dfc-148">The **Clear and submit** action is only applicable when you use Call center functionality.</span></span>  
8. <span data-ttu-id="38dfc-149">Klicka på **Rensa spärrar**.</span><span class="sxs-lookup"><span data-stu-id="38dfc-149">Click **Clear holds**.</span></span> <span data-ttu-id="38dfc-150">Spärren har nu tagits bort från ordern och från listan över aktiva spärrningar.</span><span class="sxs-lookup"><span data-stu-id="38dfc-150">The hold has now been cleared from the order and removed from the list of Active holds.</span></span> <span data-ttu-id="38dfc-151">Ändra värdet i fältet Visa för att visa samtliga spärrningar eller deras underuppsättningar enligt en viss status.</span><span class="sxs-lookup"><span data-stu-id="38dfc-151">To see all the holds or their subset according to a specific status, change the value in the Show field.</span></span>     

