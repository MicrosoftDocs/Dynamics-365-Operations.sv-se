---
title: Arbetsorderpooler
description: I det här avsnittet beskrivs hur du arbetar med arbetsorderpooler i Tillgångshantering.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 069fa02073808fd7bbaac9bc1603e49ce4d450eb
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875904"
---
# <a name="work-order-pools"></a><span data-ttu-id="63260-103">Arbetsorderpooler</span><span class="sxs-lookup"><span data-stu-id="63260-103">Work order pools</span></span>


[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


<span data-ttu-id="63260-104">Du kan använda arbetsorderpooler för att gruppera arbetsorder som har något gemensamt.</span><span class="sxs-lookup"><span data-stu-id="63260-104">You can use work order pools to group work orders that have something in common.</span></span> <span data-ttu-id="63260-105">Du kan till exempel skapa pooler för arbetsorder för</span><span class="sxs-lookup"><span data-stu-id="63260-105">For example, you can create work order pools for</span></span>

- <span data-ttu-id="63260-106">arbetslag, t.ex. underhållslag A, underhållslag B</span><span class="sxs-lookup"><span data-stu-id="63260-106">work crews, for example, Maintenance Crew A, Maintenance Crew B</span></span>  

- <span data-ttu-id="63260-107">yrkesfärdigheter, t ex. elektriker eller rörmokare</span><span class="sxs-lookup"><span data-stu-id="63260-107">professional skills, for example, electricians or plumbers</span></span>  

- <span data-ttu-id="63260-108">fysiska platser</span><span class="sxs-lookup"><span data-stu-id="63260-108">physical locations</span></span>  

- <span data-ttu-id="63260-109">tidsscheman, t. ex. veckor eller andra perioder</span><span class="sxs-lookup"><span data-stu-id="63260-109">time schedules, for example, weeks or other periods</span></span>  


<span data-ttu-id="63260-110">Vid behov kan en arbetsorder placeras i flera av arbetsorderpoolerna.</span><span class="sxs-lookup"><span data-stu-id="63260-110">If required, one work order can be placed in many work order pools.</span></span>


## <a name="create-work-order-pool"></a><span data-ttu-id="63260-111">Skapa arbetsorderpool</span><span class="sxs-lookup"><span data-stu-id="63260-111">Create work order pool</span></span>

<span data-ttu-id="63260-112">I **Alla arbetsorderpooler** eller **Aktiva arbetsorderpooler** kan du få en översikt över dina arbetsorderpooler och skapa nya pooler.</span><span class="sxs-lookup"><span data-stu-id="63260-112">In **All work order pools** or **Active work order pools**, you can get an overview of your work order pools and create new pools.</span></span>

1. <span data-ttu-id="63260-113">Klicka på **Tillgångshantering** > **Allmänt** > **Arbetsorderpooler** > **Alla arbetsorderpooler** eller **Aktiva arbetsorderpooler**.</span><span class="sxs-lookup"><span data-stu-id="63260-113">Click **Asset management** > **Common** > **Work order pools** > **All work order pools** or **Active work order pools**.</span></span>

2. <span data-ttu-id="63260-114">Klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="63260-114">Click **New**.</span></span>

3. <span data-ttu-id="63260-115">Infoga ett ID för arbetsorderpool i fältet **Pool** och ett namn i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="63260-115">Insert a work order pool ID in the **Pool** field and a name in the **Name** field.</span></span>

4. <span data-ttu-id="63260-116">Välj "Ja" på växlingsknappen **Aktiv** om du vill ange att arbetsorderpoolen är aktiv.</span><span class="sxs-lookup"><span data-stu-id="63260-116">Select "Yes" on the **Active** toggle button to indicate that the work order pool is active.</span></span>

5. <span data-ttu-id="63260-117">Välj "Ja" på växlingsknappen **Ta bort arbetsorderrelationer** om du vill att arbetsorder automatiskt ska tas bort från arbetsorderpoolen.</span><span class="sxs-lookup"><span data-stu-id="63260-117">Select "Yes" on the **Delete work order relations** toggle button if you want work orders to be automatically removed from the work order pool.</span></span>

6. <span data-ttu-id="63260-118">I fältet **Ta bort livscykeltillstånd** väljer du arbetsorderns livscykeltillstånd.</span><span class="sxs-lookup"><span data-stu-id="63260-118">In the **Delete lifecycle state** field, select the work order lifecycle state.</span></span> <span data-ttu-id="63260-119">Livscykeltillståndet för arbetsordern för att slutföra en arbetsorder kan t.ex. ställas in för att automatiskt ta bort relationer till arbetsorderpooler.</span><span class="sxs-lookup"><span data-stu-id="63260-119">For example, the work order lifecycle state for completing a work order could be set to automatically delete relations to work order pools.</span></span>

7. <span data-ttu-id="63260-120">Du kan börja lägga till arbetsorder till din arbetsorderpool omedelbart.</span><span class="sxs-lookup"><span data-stu-id="63260-120">You can start adding work orders to your work order pool right away.</span></span> <span data-ttu-id="63260-121">På snabbfliken **Arbetsorder** klickar du på **Lägg till rad**.</span><span class="sxs-lookup"><span data-stu-id="63260-121">On the **Work orders** FastTab, click **Add line**.</span></span>

8. <span data-ttu-id="63260-122">Välj en arbetsorder i fältet **Arbetsorder**.</span><span class="sxs-lookup"><span data-stu-id="63260-122">Select a work order in the **Work order** field.</span></span> <span data-ttu-id="63260-123">Det relaterade fälten uppdateras automatiskt.</span><span class="sxs-lookup"><span data-stu-id="63260-123">The related fields are automatically updated.</span></span>

9. <span data-ttu-id="63260-124">Upprepa steg 7-8 om du vill lägga till fler arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="63260-124">Repeat steps 7-8 if you want to add more work orders.</span></span>

10. <span data-ttu-id="63260-125">I fältet **Sorteringsordning** kan du ange om arbetsorder ska utföras i en viss ordning.</span><span class="sxs-lookup"><span data-stu-id="63260-125">In the **Sort order** field, you can indicate if the work orders should be carried out in a certain order.</span></span> <span data-ttu-id="63260-126">Infoga nummer 1, 2, 3 och så vidare för att ange en specifik sekvens för de valda arbetsorderna.</span><span class="sxs-lookup"><span data-stu-id="63260-126">Insert numbers 1, 2, 3, and so on to indicate a specific sequence for the selected work orders.</span></span>

11. <span data-ttu-id="63260-127">Klicka på knappen **Arbetsorder** om du vill visa en lista över alla arbetsorder som ingår i arbetsorderpoolen.</span><span class="sxs-lookup"><span data-stu-id="63260-127">Click the **Work orders** button to see a list of all the work orders included in the work order pool.</span></span>

12. <span data-ttu-id="63260-128">Klicka på knappen **Kapacitetsbeläggning** för att öppna **Kapacitetsbeläggning** för att beräkna och visa kapacitetsbeläggning för underhållsschema, ej tidsplanerade arbetsorder och tidsplanerade arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="63260-128">Click the **Capacity load** button to open **Capacity load** to calculate and view capacity load for maintenance schedule, not-scheduled work orders, and scheduled work orders.</span></span>

13. <span data-ttu-id="63260-129">Klicka på knappen **Artikelprognos** om du öppna **Artikelprognos** för att beräkna och visa prognoser för artiklar (reservdelar och andra nödvändiga artiklar) relaterade till ett underhållsschema, ej tidsplanerade arbetsorder och tidsplanerade arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="63260-129">Click the **Item forecast** button to open **Item forecast** to calculate and view forecasts for items (spare parts and other required items) related to maintenance schedule, not-scheduled work orders, and scheduled work orders.</span></span>

14. <span data-ttu-id="63260-130">Klicka på knappen **Inköpsrekvisition för arbetsorder** för att öppna listan **Inköpsrekvisition för arbetsorder** och visa en lista med inköpsrekvisitioner relaterade till arbetsorderna i arbetsorderpoolen.</span><span class="sxs-lookup"><span data-stu-id="63260-130">Click the **Work order purchase requisition** button to open the **Work order purchase requisition** list to see a list of purchase requisitions related to the work orders in the work order pool.</span></span>

15. <span data-ttu-id="63260-131">Klicka på knappen **Arbetsorderinköp** för att öppna listan **Arbetsorderinköp** och visa en lista med inköpsorder relaterade till arbetsorderna i arbetsorderpoolen.</span><span class="sxs-lookup"><span data-stu-id="63260-131">Click the **Work order purchase** button to open the **Work order purchase** list to see a list of purchase orders related to the work orders in the work order pool.</span></span>

>[!NOTE]
><span data-ttu-id="63260-132">När en arbetsorderpool inte längre är relevant för din arbetsplanering ställer du in kryssrutan **Aktiv** för den poolen till "Nej" i listvyn **Arbetsorderpool**.</span><span class="sxs-lookup"><span data-stu-id="63260-132">When a work order pool is no longer relevant for your work planning, set the **Active** check box for that pool to "No" in the **Work order pool** list view.</span></span>

<span data-ttu-id="63260-133">Markera kryssrutan **Ta bort arbetsorderrelationer** om du vill ta bort alla arbetsorderrader, t.ex. för att skapa en tom pool som du senare kan använda för andra arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="63260-133">Select the **Delete work order relations** check box if you want to delete all work order lines, for example to create an empty pool that you can later use for other work orders.</span></span> <span data-ttu-id="63260-134">Kom ihåg att avmarkera **Ta bort arbetsorderrelationer** om du vill använda arbetsorderpoolen för att skapa nya arbetsorderrelationer senare.</span><span class="sxs-lookup"><span data-stu-id="63260-134">Remember to clear the **Delete work order relations** check box if you want to use the work order pool to create new work order relations later.</span></span>


![Figur 1](media/22-work-orders.png)


## <a name="add-work-order-to-a-work-order-pool"></a><span data-ttu-id="63260-136">Lägga till arbetsorder i en arbetsorderpool</span><span class="sxs-lookup"><span data-stu-id="63260-136">Add work order to a work order pool</span></span>

<span data-ttu-id="63260-137">Som beskrivs i avsnittet ovan kan du lägga till arbetsorder till en arbetsorderpool när du skapar poolen.</span><span class="sxs-lookup"><span data-stu-id="63260-137">As described in the section above, you can add work orders to a work order pool when you create the pool.</span></span> <span data-ttu-id="63260-138">Du kan också lägga till en arbetsorder till en arbetsorderpool från en listorna **Alla arbetsorder**.</span><span class="sxs-lookup"><span data-stu-id="63260-138">You can also add a work order to a work order pool from one of the **All work orders** list.</span></span>

1. <span data-ttu-id="63260-139">Klicka på **Tillgångshantering** > **Allmänt** > **Arbetsorder** > **Alla arbetsorder** eller **Aktiva arbetsorder**.</span><span class="sxs-lookup"><span data-stu-id="63260-139">Click **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="63260-140">Välj arbetsorder i listan och klicka på **Arbetsorderpool**.</span><span class="sxs-lookup"><span data-stu-id="63260-140">Select the work order in the list, and click **Work order pool**.</span></span>

3. <span data-ttu-id="63260-141">Välj "Lägg till" i fältet **Lägg till/ta bort**.</span><span class="sxs-lookup"><span data-stu-id="63260-141">Select "Add" in the **Add/remove** field.</span></span>

4. <span data-ttu-id="63260-142">Välj arbetsorderpoolen i fältet **Pool**.</span><span class="sxs-lookup"><span data-stu-id="63260-142">Select the work order pool in the **Pool** field.</span></span>

5. <span data-ttu-id="63260-143">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="63260-143">Click **OK**.</span></span>

6. <span data-ttu-id="63260-144">När du har lagt till en arbetsorder i en arbetsorderpool, och vill placera arbetsordern i en viss serie i poolen: öppna en av listsidorna för arbetsorderpooler, välj poolen och klicka på **Redigera** och justera sorteringsordningen för arbetsorderna som ingår i poolen i formuläret **Arbetsorderpool** > snabbfliken **Arbetsorder** > fältet **Sorteringsordning**.</span><span class="sxs-lookup"><span data-stu-id="63260-144">After you have added a work order to a work order pool, if you want to place the work order in a specific sequence in the pool: Open one of the work order pools list pages, select the pool and click **Edit**, and adjust the sort order of the work orders included in pool in the **Work order pool** form > **Work orders** FastTab > **Sort order** field.</span></span>

<span data-ttu-id="63260-145">Om du vill ta bort den valda arbetsordern från en arbetsorderpool väljer du "Ta bort" i steg 3.</span><span class="sxs-lookup"><span data-stu-id="63260-145">If you want to remove the selected work order from a work order pool, select "Remove" in step 3.</span></span>

