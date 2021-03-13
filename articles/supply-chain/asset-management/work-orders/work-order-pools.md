---
title: Arbetsorderpooler
description: I det här avsnittet beskrivs hur du arbetar med arbetsorderpooler i Tillgångshantering.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkOrderTablePoolPart, EntAssetWorkOrderPoolReferenceInfoPart, EntAssetWorkOrderPool, EntAssetWorkOrderPoolPreviewPart
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: afea5b8d0f958c3ab53d6cef8c9a0e9030d7c67b
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/16/2021
ms.locfileid: "5017527"
---
# <a name="work-order-pools"></a><span data-ttu-id="6801f-103">Arbetsorderpooler</span><span class="sxs-lookup"><span data-stu-id="6801f-103">Work order pools</span></span>

[!include [banner](../../includes/banner.md)]


<span data-ttu-id="6801f-104">Du kan använda arbetsorderpooler för att gruppera arbetsorder som har något gemensamt.</span><span class="sxs-lookup"><span data-stu-id="6801f-104">You can use work order pools to group work orders that have something in common.</span></span> <span data-ttu-id="6801f-105">Här följer några exempel på vad du kan skapa arbetsorderpooler för:</span><span class="sxs-lookup"><span data-stu-id="6801f-105">Here are some examples of things that you can create  work order pools for:</span></span>

- <span data-ttu-id="6801f-106">Arbetslag, t.ex. underhållslag A eller underhållslag B</span><span class="sxs-lookup"><span data-stu-id="6801f-106">Work crews, for example, Maintenance Crew A or Maintenance Crew B</span></span>  

- <span data-ttu-id="6801f-107">Yrkesfärdigheter, t.ex. elektriker eller rörmokare</span><span class="sxs-lookup"><span data-stu-id="6801f-107">Professional skills, such as electricians or plumbers</span></span>  

- <span data-ttu-id="6801f-108">Fysiska platser</span><span class="sxs-lookup"><span data-stu-id="6801f-108">Physical locations</span></span>  

- <span data-ttu-id="6801f-109">Tidsscheman, t.ex. veckor eller andra perioder</span><span class="sxs-lookup"><span data-stu-id="6801f-109">Time schedules, such as weeks or other periods</span></span>  

<span data-ttu-id="6801f-110">När du behöver kan du placera en arbetsorder i flera arbetsorderpooler.</span><span class="sxs-lookup"><span data-stu-id="6801f-110">As you require, you can put one work order in multiple work order pools.</span></span>


## <a name="create-a-work-order-pool"></a><span data-ttu-id="6801f-111">Skapa en arbetsorderpool</span><span class="sxs-lookup"><span data-stu-id="6801f-111">Create a work order pool</span></span>

<span data-ttu-id="6801f-112">På listsidan **Alla arbetsorderpooler** eller **Aktiva arbetsorderpooler** kan du få en översikt över dina arbetsorderpooler och skapa nya pooler.</span><span class="sxs-lookup"><span data-stu-id="6801f-112">On the **All work order pools** or **Active work order pools** list page, you can get an overview of your work order pools and create new pools.</span></span>

1. <span data-ttu-id="6801f-113">Klicka på **Tillgångshantering** > **Allmänt** > **Arbetsorderpooler** > **Alla arbetsorderpooler** eller **Aktiva arbetsorderpooler**.</span><span class="sxs-lookup"><span data-stu-id="6801f-113">Select **Asset management** > **Common** > **Work order pools** > **All work order pools** or **Active work order pools**.</span></span>

2. <span data-ttu-id="6801f-114">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="6801f-114">Select **New**.</span></span>

3. <span data-ttu-id="6801f-115">I fältet **Pool** anger du ett ID för arbetsorderpoolen.</span><span class="sxs-lookup"><span data-stu-id="6801f-115">In the **Pool** field, enter an ID for the work order pool.</span></span>

4. <span data-ttu-id="6801f-116">Ange sedan ett namn i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="6801f-116">the **Name** field, enter a name.</span></span>

5. <span data-ttu-id="6801f-117">Ange alternativet **Aktiv** till **Ja** om du vill ange att arbetsorderpoolen är aktiv.</span><span class="sxs-lookup"><span data-stu-id="6801f-117">Set the **Active** option to **Yes** to indicate that the work order pool is active.</span></span>

6. <span data-ttu-id="6801f-118">Ange alternativet **Ta bort arbetsorderrelationer** till **Ja** om du vill att arbetsorder automatiskt ska tas bort från arbetsorderpoolen.</span><span class="sxs-lookup"><span data-stu-id="6801f-118">Set the **Delete work order relations** option to **Yes** if work orders should automatically be removed from the work order pool.</span></span>

7. <span data-ttu-id="6801f-119">I fältet **Ta bort livscykeltillstånd** väljer du arbetsorderns livscykeltillstånd.</span><span class="sxs-lookup"><span data-stu-id="6801f-119">In the **Delete lifecycle state** field, select the work order lifecycle state.</span></span> <span data-ttu-id="6801f-120">Livscykeltillståndet för arbetsordern för att slutföra en arbetsorder kan t.ex. ställas in för att automatiskt ta bort relationer till arbetsorderpooler.</span><span class="sxs-lookup"><span data-stu-id="6801f-120">For example, the work order lifecycle state for completing a work order could be set to automatically delete relations to work order pools.</span></span>

    <span data-ttu-id="6801f-121">Du kan börja lägga till arbetsorder till din arbetsorderpool omedelbart.</span><span class="sxs-lookup"><span data-stu-id="6801f-121">You can start adding work orders to your work order pool right away.</span></span>

8. <span data-ttu-id="6801f-122">På snabbfliken **Arbetsorder** klickar du på **Lägg till rad**.</span><span class="sxs-lookup"><span data-stu-id="6801f-122">On the **Work orders** FastTab, select **Add line**.</span></span>

9. <span data-ttu-id="6801f-123">Välj en arbetsorder i fältet **Arbetsorder**.</span><span class="sxs-lookup"><span data-stu-id="6801f-123">In the **Work order** field, select a work order.</span></span> <span data-ttu-id="6801f-124">Det relaterade fälten uppdateras automatiskt.</span><span class="sxs-lookup"><span data-stu-id="6801f-124">The related fields are automatically updated.</span></span>

10. <span data-ttu-id="6801f-125">Upprepa steg 8 till och med 9 om du vill lägga till fler arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="6801f-125">Repeat steps 8 through 9 to add more work orders.</span></span>

11. <span data-ttu-id="6801f-126">Om de arbetsorder som du la till ska utföras i en specifik ordning kan du i fältet **sorteringsordning** kan du ange siffrorna **1**, **2**, **3** osv för att ange den ordningen.</span><span class="sxs-lookup"><span data-stu-id="6801f-126">If the work orders that you added should be done in a specific order, in the **Sort order** field, you can enter the numbers **1**, **2**, **3**, and so on, to specify that order.</span></span>

12. <span data-ttu-id="6801f-127">Om du vill visa en lista med alla arbetsorder som har inkluderats i arbetsordern går du till åtgärdsfönstret på fliken **Arbetsorderpool** i gruppen **Visa arbetsorderpoolrelaterad** och välj **arbetsorder** för att öppna listsidan **alla arbetsorder**.</span><span class="sxs-lookup"><span data-stu-id="6801f-127">To view a list of all the work orders that are included in the work order pool, on the Action Pane, on the **Work order pool** tab, in the **View work order pool related** group, select **Work orders** to open the **All work orders** list page.</span></span>

13. <span data-ttu-id="6801f-128">För att beräkna och visa kapacitetsbelastning för underhållsschemat, ej tidsplanerade arbetsorder och tidsplanerade arbetsordrar, i åtgärdsfönstret, på fliken **Arbetsorderpool** i gruppen **Visa arbetsorderpoolrelaterad**, välj **Artikelprognoser** för att öppna dialogrutan **Beräkna artikelprognoser**.</span><span class="sxs-lookup"><span data-stu-id="6801f-128">To calculate and view capacity load for the maintenance schedule, unscheduled work orders, and scheduled work orders, on the Action Pane, on the **Work order pool** tab, in the **View work order pool related** group, select **Capacity load** to open the **Calculate capacity load** dialog.</span></span>

14. <span data-ttu-id="6801f-129">För att beräkna och visa prognoser för artiklar (reservdelar och andra obligatoriska artiklar) som är relaterade till underhållsschema, ej tidsplanerade arbetsorder och tidsplanerade arbetsordrar, i åtgärdsfönstret, på **Arbetsorderpool** i gruppen **Visa arbetsorderpoolrelaterad**, välj **Artikelprognoser** för att öppna **Beräkna artikelprognoser**.</span><span class="sxs-lookup"><span data-stu-id="6801f-129">To calculate and view forecasts for items (spare parts and other required items) that are related to maintenance schedule, unscheduled work orders, and scheduled work orders, on the Action Pane, on the **Work order pool** tab, in the **View work order pool related** group, select **Item forecast** to open the **Calculate item forecast** dialog.</span></span>

15. <span data-ttu-id="6801f-130">För att se en lista över inköpskrav som är relaterade till arbetsordrarna i arbetsorderpoolen, i åtgärdsfönstret, på **Arbetsorderpool** i gruppen **Anskaffning**, välj **Inköp för arbetsorder** för att öppna listsidan **Inköp för arbetsorder**.</span><span class="sxs-lookup"><span data-stu-id="6801f-130">To view a list of purchase requisitions that are related to the work orders in the work order pool, on the Action Pane, on the **Work order pool** tab, in the **Procurement** group, select **Work order purchase requisition** to open the **Work order purchase requisition** list page.</span></span>

16. <span data-ttu-id="6801f-131">För att se en lista över inköpskrav som är relaterade till arbetsordrarna i arbetsorderpoolen, i åtgärdsfönstret, på **Arbetsorderpool** i gruppen **Anskaffning**, välj **Inköpsrekvisition för arbetsorder** för att öppna listsidan **Inköpsrekvisition för arbetsorder**.</span><span class="sxs-lookup"><span data-stu-id="6801f-131">To view a list of purchase orders that are related to the work orders in the work order pool, on the Action Pane, on the **Work order pool** tab, in the **Procurement** group, select **Work order purchase** to open the **Work order purchase** list page.</span></span>

>[!NOTE]
><span data-ttu-id="6801f-132">När en arbetsorderpool inte längre är relevant för din arbetsplanering ställer du in alternativet **Aktiv** för den poolen till **Nej** i listvyn på sidan **Arbetsorderpool**.</span><span class="sxs-lookup"><span data-stu-id="6801f-132">When a work order pool is no longer relevant to your work planning, set the **Active** option for that pool to **No** in the list view of the **Work order pool** page.</span></span>

<span data-ttu-id="6801f-133">Om du vill radera alla arbetsorderrader anger du alternativet **Ta bort arbetsorderrelationer** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="6801f-133">To delete all worker order lines, set the **Delete work order relations** option to **Yes**.</span></span> <span data-ttu-id="6801f-134">Det här alternativet är användbart om du t.ex. vill skapa en tom pool som du kan använda senare för andra arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="6801f-134">This option is useful if, for example, you want to create an empty pool that you can use later for other work orders.</span></span> <span data-ttu-id="6801f-135">När du är redo att använda arbetsorderpoolen för att skapa nya arbetsordrelationer senare, kom ihåg att ställa in alternativet **Ta bort arbetsorderrelationer** till **Nej**.</span><span class="sxs-lookup"><span data-stu-id="6801f-135">When you're ready to use the work order pool to create new work order relations later, remember to set the **Delete work order relations** option to **No**.</span></span>

<span data-ttu-id="6801f-136">I bilden nedan visas ett exempel på listsidan **Arbetsorderpool**.</span><span class="sxs-lookup"><span data-stu-id="6801f-136">The illustration below shows an example of the **Work order pool** list page.</span></span>

![Figur 1](media/22-work-orders.png)


## <a name="add-a-work-order-to-a-work-order-pool"></a><span data-ttu-id="6801f-138">Lägga till en arbetsorder i en arbetsorderpool</span><span class="sxs-lookup"><span data-stu-id="6801f-138">Add a work order to a work order pool</span></span>

<span data-ttu-id="6801f-139">Som beskrivs i avsnittet ovan kan du lägga till arbetsorder till en arbetsorderpool när du skapar poolen.</span><span class="sxs-lookup"><span data-stu-id="6801f-139">As described in the previous section, you can add work orders to a work order pool when you create that pool.</span></span> <span data-ttu-id="6801f-140">Du kan också lägga till arbetsorder till en arbetsorderpool på listsidan **Alla arbetsorder** eller **Aktiva arbetsorder**.</span><span class="sxs-lookup"><span data-stu-id="6801f-140">You can also add work orders to a work order pool on the **All work orders** or **Active work orders** list page.</span></span>

1. <span data-ttu-id="6801f-141">Välj arbetsorder och sedan i åtgärdsfönstret på fliken **Arbetsorder** i gruppen **Underhåll** väljer du **Arbetsorderpool**.</span><span class="sxs-lookup"><span data-stu-id="6801f-141">Select the work order, and then, on the Action Pane, on the **Work order** tab, in the **Maintain** group, select **Work order pool**.</span></span>

2. <span data-ttu-id="6801f-142">Välj arbetsorder i listan och klicka på **Arbetsorderpool**.</span><span class="sxs-lookup"><span data-stu-id="6801f-142">Select the work order in the list, and click **Work order pool**.</span></span>

3. <span data-ttu-id="6801f-143">I dialogrutan **Underhåll arbetsorderpool** i fältet **Lägg till/ta bort** väljer du **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="6801f-143">In the **Maintain work order pool** dialog, in the **Add/remove** field, select **Add**.</span></span>

4. <span data-ttu-id="6801f-144">Välj arbetsorderpoolen i fältet **Pool**.</span><span class="sxs-lookup"><span data-stu-id="6801f-144">In the **Pool** field, select the work order pool.</span></span>

5. <span data-ttu-id="6801f-145">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="6801f-145">Select **OK**.</span></span>

6. <span data-ttu-id="6801f-146">Om du vill placera arbetsordern som du la till i en viss ordning i arbetsorderpoolen, på listsidan **Alla arbetsorderpooler** eller **Aktiva arbetsorderpooler** väljer du poolen och väljer sedan **redigera**.</span><span class="sxs-lookup"><span data-stu-id="6801f-146">To put the work order that you added in a specific order in the work order pool, on the **All work order pools** or **Active work order pools** list page, select the pool, and then select **Edit**.</span></span> <span data-ttu-id="6801f-147">På sidan **Arbetsorderpool** på snabbfliken **Arbetsorder** kan du använda fältet **Sorteringsorder** för att justera sorteringsordningen för de arbetsorder som ingår i poolen.</span><span class="sxs-lookup"><span data-stu-id="6801f-147">Then, on the **Work order pool** page, on the **Work orders** FastTab, use the **Sort order** field to adjust the sort order of the work orders that are included in pool.</span></span>

<span data-ttu-id="6801f-148">Om du vill ta bort en arbetsorder från en arbetsorderpool, upprepa dessa steg men välj **Ta bort** i steg 3.</span><span class="sxs-lookup"><span data-stu-id="6801f-148">To remove a work order from a work order pool, repeat these steps, but select **Remove** in step 3.</span></span>

