---
title: Registrera förbrukning
description: Det här avsnittet innehåller förklaringar av hur du registrerar förbrukning i Tillgångshantering.
author: josaw1
manager: AnnBe
ms.date: 08/21/2019
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
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 3d23375ec7ebe9b43c2d2e3e376e26c348131bd3
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/18/2019
ms.locfileid: "2812270"
---
# <a name="register-consumption"></a><span data-ttu-id="3c1c5-103">Registrera förbrukning</span><span class="sxs-lookup"><span data-stu-id="3c1c5-103">Register consumption</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="3c1c5-104">När ett underhållsjobb har slutförts på en arbetsorder är nästa steg att göra förbrukningsregistreringar och bokföra journalerna.</span><span class="sxs-lookup"><span data-stu-id="3c1c5-104">When a maintenance job has been completed on a work order, the next step is to make consumption registrations and post the journals.</span></span> <span data-ttu-id="3c1c5-105">Du kan göra registreringar av följande förbrukningstyper: timmar, artiklar och utgifter.</span><span class="sxs-lookup"><span data-stu-id="3c1c5-105">You can make registrations on the following consumption types: Hours, items, and expenses.</span></span> <span data-ttu-id="3c1c5-106">De olika förbrukningstyperna registreras och bokförs på **Arbetsorderjournaler**.</span><span class="sxs-lookup"><span data-stu-id="3c1c5-106">The different consumption types are registered and posted on the **Work order journals** page.</span></span> <span data-ttu-id="3c1c5-107">Journalinställningarna i **Tillgångshantering** används för att skapa och bokföra separata journaler för timmar, artiklar och utgifter i modulen **Projekthantering och redovisning**.</span><span class="sxs-lookup"><span data-stu-id="3c1c5-107">The journal setup in **Asset Management** is used for creating and posting separate journals for hours, items, and expenses in the **Project management and accounting** module.</span></span>

<span data-ttu-id="3c1c5-108">I vissa fall kanske kan lägga till eller ta bort prognosrader på en arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="3c1c5-108">In some cases, you may be able to add or delete forecast lines on a work order.</span></span> <span data-ttu-id="3c1c5-109">Inställningen av en livscykeltillstånd för arbetsorder, den relaterade projekttypen och de fasregler som gäller för projekttypen bestämmer om du kan lägga till eller redigera journalrader.</span><span class="sxs-lookup"><span data-stu-id="3c1c5-109">The setup of a work order lifecycle state, the related project type, and the stage rules related to the project type determine if you are able to add or edit journal lines.</span></span> <span data-ttu-id="3c1c5-110">Mer information om livscykeltillstånd för arbetsorder och relaterade projektfaser finns i [Prognoser, arbetsorder och projekt](../integration-to-project-management-and-accounting/forecasts-work-orders-and-projects.md).</span><span class="sxs-lookup"><span data-stu-id="3c1c5-110">Read more about work order lifecycle states and related project stages in [Forecasts, work orders, and projects](../integration-to-project-management-and-accounting/forecasts-work-orders-and-projects.md).</span></span>

>[!NOTE]
><span data-ttu-id="3c1c5-111">Det är möjligt att ställa in automatisk bokföring av journaler i ett livscykeltillstånd för arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="3c1c5-111">It is possible to set up automatic posting of journals on a work order lifecycle state.</span></span> <span data-ttu-id="3c1c5-112">Mer information finns i [Livscykeltillstånd för arbetsorder](../setup-for-work-orders/work-order-lifecycle-states.md).</span><span class="sxs-lookup"><span data-stu-id="3c1c5-112">Refer to [Work order lifecycle states](../setup-for-work-orders/work-order-lifecycle-states.md) for more information.</span></span>

1. <span data-ttu-id="3c1c5-113">Klicka på **Tillgångshantering** > **Allmänt** > **Arbetsorder** > **Alla arbetsorder** eller **Aktiva arbetsorder**.</span><span class="sxs-lookup"><span data-stu-id="3c1c5-113">Click **Asset management** > **Common** > **Work orders** > **All Work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="3c1c5-114">Välj arbetsorder och klicka på **Journaler**.</span><span class="sxs-lookup"><span data-stu-id="3c1c5-114">Select the work order, and click **Journals**.</span></span>

3. <span data-ttu-id="3c1c5-115">Klicka på **Kopiera från prognos** om du vill överföra alla prognosrader som kan kopplas till arbetsordern.</span><span class="sxs-lookup"><span data-stu-id="3c1c5-115">Click **Copy from forecast** to transfer any forecast lines that may be connected to the work order.</span></span> <span data-ttu-id="3c1c5-116">Du kan välja vilka förbrukningstyper du vill överföra.</span><span class="sxs-lookup"><span data-stu-id="3c1c5-116">You can select which consumption types you want to transfer.</span></span>

4. <span data-ttu-id="3c1c5-117">Om det behövs kan du lägga till fler förbrukningsrader på relevant snabbflik genom att klicka på **Lägg till rad** och fylla i data på raden.</span><span class="sxs-lookup"><span data-stu-id="3c1c5-117">If necessary, you can add more consumption lines on the relevant FastTab by clicking **Add line** and filling out data on the line.</span></span>

5. <span data-ttu-id="3c1c5-118">Klicka på **Validera journaler** om du vill validera journalraderna före bokföring.</span><span class="sxs-lookup"><span data-stu-id="3c1c5-118">Click **Validate journals** to validate the journal lines before posting.</span></span>

6. <span data-ttu-id="3c1c5-119">Klicka på **Bokför journaler** för att bokföra journalraderna.</span><span class="sxs-lookup"><span data-stu-id="3c1c5-119">Click **Post journals** to post the journal lines.</span></span>

7. <span data-ttu-id="3c1c5-120">När du har bokfört förbrukningsjournalerna kan du uppdatera livscykelstadiet för arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="3c1c5-120">After you've posted the consumption journals, you can update the work order lifecycle state.</span></span> <span data-ttu-id="3c1c5-121">Om du till exempel vill ange att arbetsordern har slutförts, kan du uppdatera livscykel stadiet till "avslutad".</span><span class="sxs-lookup"><span data-stu-id="3c1c5-121">For example, to indicate that the work order has been completed, you can update the lifecycle state to "Ended".</span></span>

    - <span data-ttu-id="3c1c5-122">I fältet **Visa** som placerades högst upp på sidan **Arbetsorderjournaler** väljer du vilka journalrader som ska visas: **alla**, **inte bokförda** eller **bokförda**.</span><span class="sxs-lookup"><span data-stu-id="3c1c5-122">In the **Show** field at the top of the **Work order journals** page, select which journal lines you want to see: **All**, **Not posted**, or **Posted**.</span></span> <span data-ttu-id="3c1c5-123">Bokförda journaler är markerade i kryssrutan **Bokförd**.</span><span class="sxs-lookup"><span data-stu-id="3c1c5-123">Posted journals have a check mark in the **Posted** check box.</span></span>  
    - <span data-ttu-id="3c1c5-124">När artikelrader skapas i arbetsorderjournalen överförs automatiskt produktdimensioner och spårningsdimensioner som är relaterade till artikeln till journalraden.</span><span class="sxs-lookup"><span data-stu-id="3c1c5-124">When item lines are created in the work order journal, product dimensions and tracking dimensions related to the item are automatically transferred to the journal line.</span></span>  

<span data-ttu-id="3c1c5-125">På bilden nedan visas ett exempel på tim- och artikelregistreringar i en arbetsorder i **Arbetsorderjournaler**.</span><span class="sxs-lookup"><span data-stu-id="3c1c5-125">The screenshot below shows an example of hour and item registrations on a work order in **Work order journals**.</span></span>

![Figur 1](media/01-consumption.png)


## <a name="split-hours-on-work-orders-with-several-work-order-jobs"></a><span data-ttu-id="3c1c5-127">Dela timmar på arbetsorder med flera arbetsorderjobb</span><span class="sxs-lookup"><span data-stu-id="3c1c5-127">Split hours on work orders with several work order jobs</span></span>

<span data-ttu-id="3c1c5-128">Om en arbetsorder innehåller flera jobb för arbetsorder kan du registrera arbetstimmar med funktionen **Dela timmar**, vilket innebär att en timregistreringsrad kan fördelas jämnt på varje arbetsorderjobb.</span><span class="sxs-lookup"><span data-stu-id="3c1c5-128">If a work order contains several work order jobs, you can register work hours using the **Split hours** functionality, meaning one hour registration line can be distributed evenly on each work order job.</span></span>

1. <span data-ttu-id="3c1c5-129">Klicka på **Tillgångshantering** > **Allmänt** > **Arbetsorder** > **Alla arbetsorder** eller **Aktiva arbetsorder**.</span><span class="sxs-lookup"><span data-stu-id="3c1c5-129">Click **Asset management** > **Common** > **Work orders** > **All Work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="3c1c5-130">Välj arbetsorder och klicka på **Journaler**.</span><span class="sxs-lookup"><span data-stu-id="3c1c5-130">Select the work order and click **Journals**.</span></span>

3. <span data-ttu-id="3c1c5-131">Välj den timregistreringsrad som du vill dela och klicka på **Dela timmar**.</span><span class="sxs-lookup"><span data-stu-id="3c1c5-131">Select the hour registration line you want to split, and click **Split hours**.</span></span>

4. <span data-ttu-id="3c1c5-132">I dialogrutan **Dela timmar på underhållsjobb för arbetsorder** visas namnet på den arbetare som är inloggad i automatiskt i fältet **Arbetare**.</span><span class="sxs-lookup"><span data-stu-id="3c1c5-132">In the **Split hours on work order maintenance jobs** dialog, the name of the worker who is logged in is automatically shown in the **Worker** field.</span></span> <span data-ttu-id="3c1c5-133">Om det behövs kan du välja en annan arbetare.</span><span class="sxs-lookup"><span data-stu-id="3c1c5-133">If required, you can select another worker.</span></span>

5. <span data-ttu-id="3c1c5-134">Välj en kategori för timregistreringen i fältet **Kategori**.</span><span class="sxs-lookup"><span data-stu-id="3c1c5-134">Select a category for the hour registration in the **Category** field.</span></span>

6. <span data-ttu-id="3c1c5-135">Infoga antal arbetstimmar som ska delas i fältet **Timmar**.</span><span class="sxs-lookup"><span data-stu-id="3c1c5-135">Insert number of work hours to be split in the **Hours** field.</span></span>

    ![Figur 2](media/02-consumption.png)

7. <span data-ttu-id="3c1c5-137">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="3c1c5-137">Click **OK**.</span></span>

<span data-ttu-id="3c1c5-138">*Exempel:* På bilden nedan visas journalrader för en arbetsorder som innehåller tre arbetsorderjobb.</span><span class="sxs-lookup"><span data-stu-id="3c1c5-138">*Example:* In the screenshot below, journal lines for a work order containing three work order jobs are shown.</span></span> <span data-ttu-id="3c1c5-139">Den första raden, som innehåller tre arbetstimmar, har delats upp och en arbetstimme har registrerats för varje arbetsorderjobb.</span><span class="sxs-lookup"><span data-stu-id="3c1c5-139">The first line, containing three work hours, has been split, and one work hour is registered on each work order job.</span></span> <span data-ttu-id="3c1c5-140">När de tre timregistreringsraderna har skapats, bestämmer du vad du ska göra med den ursprungliga timregistreringsraden (den första raden i exemplet).</span><span class="sxs-lookup"><span data-stu-id="3c1c5-140">After the three hour registration lines have been created, you decide what to do with the original hour registration line (the first line in the example).</span></span> <span data-ttu-id="3c1c5-141">Du kan behålla den som den är eller ta bort den.</span><span class="sxs-lookup"><span data-stu-id="3c1c5-141">You can keep it as is or delete it.</span></span> 

![Figur 3](media/03-consumption.png)

## <a name="financial-dimensions-on-consumption-registrations"></a><span data-ttu-id="3c1c5-143">Ekonomiska dimensioner för förbrukningsregistreringar</span><span class="sxs-lookup"><span data-stu-id="3c1c5-143">Financial dimensions on consumption registrations</span></span>

<span data-ttu-id="3c1c5-144">När du gör förbrukningsregistreringar läggs ekonomiska dimensioner som hör till de olika registreringstyperna till i registreringarna i en specifik sekvens.</span><span class="sxs-lookup"><span data-stu-id="3c1c5-144">When you make consumption registrations, financial dimensions related to the different registration types are added to the registrations in a specific sequence.</span></span> 

- <span data-ttu-id="3c1c5-145">*Tim- och utgiftsregistrering:* Först läggs ekonomiska dimensioner från journalhuvudet till, om det finns några.</span><span class="sxs-lookup"><span data-stu-id="3c1c5-145">*Hour and Expense registrations:* First, financial dimensions from the journal header are added, if any.</span></span> <span data-ttu-id="3c1c5-146">Därefter läggs ekonomiska dimensioner från det relaterade arbetsorderprojektet till.</span><span class="sxs-lookup"><span data-stu-id="3c1c5-146">Next, financial dimensions from the related work order project are added.</span></span> <span data-ttu-id="3c1c5-147">Slutligen läggs ekonomiska dimensioner från resursen (arbetaren) till.</span><span class="sxs-lookup"><span data-stu-id="3c1c5-147">Finally, financial dimensions from the resource (worker) are added.</span></span>

- <span data-ttu-id="3c1c5-148">*Artikelregistreringar:* Först läggs ekonomiska dimensioner från journalhuvudet till, om det finns några.</span><span class="sxs-lookup"><span data-stu-id="3c1c5-148">*Item registrations:* First, financial dimensions from the journal header are added, if any.</span></span> <span data-ttu-id="3c1c5-149">Därefter läggs ekonomiska dimensioner från det relaterade arbetsorderprojektet till.</span><span class="sxs-lookup"><span data-stu-id="3c1c5-149">Then, financial dimensions from the related work order project are added.</span></span> <span data-ttu-id="3c1c5-150">Därefter läggs ekonomiska dimensioner från webbplatsen till.</span><span class="sxs-lookup"><span data-stu-id="3c1c5-150">Next, financial dimensions from the site are added.</span></span> <span data-ttu-id="3c1c5-151">Slutligen läggs ekonomiska dimensioner från artikeln till.</span><span class="sxs-lookup"><span data-stu-id="3c1c5-151">Finally, financial dimensions from the item are added.</span></span>

>[!NOTE]
><span data-ttu-id="3c1c5-152">För alla tre registreringstyperna valideras kombinationen av ekonomisk dimension, och ogiltiga kombinationer görs tomma.</span><span class="sxs-lookup"><span data-stu-id="3c1c5-152">For all three registration types, the financial dimension combination is validated, and invalid combinations are blanked.</span></span> <span data-ttu-id="3c1c5-153">Detta är standard inställningar med andra Finance and Operations-appar.</span><span class="sxs-lookup"><span data-stu-id="3c1c5-153">This is standard setup with other Finance and Operations apps.</span></span>

