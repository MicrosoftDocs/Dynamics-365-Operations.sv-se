---
title: Konfigurera automatiska uppgifter i ett arbetsflöde
description: I det här avsnittet beskrivs hur du konfigurerar egenskaperna för en automatisk uppgift.
author: ChrisGarty
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 192061
ms.assetid: c0aceb57-b5e6-4ef3-91e7-89a21c9f048a
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4f02b128036ebc0bd8789ecafd1e72e26fe31436
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5747965"
---
# <a name="configure-automated-tasks-in-a-workflow"></a><span data-ttu-id="9a8a1-103">Konfigurera automatiska uppgifter i ett arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="9a8a1-103">Configure automated tasks in a workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9a8a1-104">I det här avsnittet beskrivs hur du konfigurerar egenskaperna för en automatisk uppgift.</span><span class="sxs-lookup"><span data-stu-id="9a8a1-104">This topic explains how to configure the properties for an automated task.</span></span>

<span data-ttu-id="9a8a1-105">Högerklicka på uppgiften och klicka sedan på **Egenskaper** för att öppna sidan **Egenskaper** om du vill konfigurera en automatisk uppgift i arbetsflödesredigeraren.</span><span class="sxs-lookup"><span data-stu-id="9a8a1-105">To configure an automated task in the workflow editor, right-click the task, and then click **Properties** to open the **Properties** page.</span></span> <span data-ttu-id="9a8a1-106">Använd sedan följande procedurer när du vill konfigurera egenskaperna för den automatiska uppgiften.</span><span class="sxs-lookup"><span data-stu-id="9a8a1-106">Then use the following procedures to configure the properties for the automated task.</span></span>

## <a name="name-the-task"></a><span data-ttu-id="9a8a1-107">Ange ett namn på uppgiften</span><span class="sxs-lookup"><span data-stu-id="9a8a1-107">Name the task</span></span>

<span data-ttu-id="9a8a1-108">Följ dessa steg när du vill ange ett namn för den automatiska uppgiften.</span><span class="sxs-lookup"><span data-stu-id="9a8a1-108">Follow these steps to enter a name for the automated task.</span></span>

1. <span data-ttu-id="9a8a1-109">Klicka på **Grundinställningar** i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="9a8a1-109">In the left pane, click **Basic Settings**.</span></span>
2. <span data-ttu-id="9a8a1-110">I fältet **Namn** anger du ett unikt namn för uppgiften.</span><span class="sxs-lookup"><span data-stu-id="9a8a1-110">In the **Name** field, enter a unique name for the task.</span></span>

## <a name="specify-when-notifications-are-sent"></a><span data-ttu-id="9a8a1-111">Ange när meddelanden ska skickas</span><span class="sxs-lookup"><span data-stu-id="9a8a1-111">Specify when notifications are sent</span></span>

<span data-ttu-id="9a8a1-112">Du kan skicka meddelanden till andra personer när en automatisk uppgift har körts eller annullerats.</span><span class="sxs-lookup"><span data-stu-id="9a8a1-112">You can send notifications to people when an automated task has been run or canceled.</span></span> <span data-ttu-id="9a8a1-113">Följ dessa steg för att ange när meddelanden skickas och vem de skickas till.</span><span class="sxs-lookup"><span data-stu-id="9a8a1-113">Follow these steps to specify when notifications are sent, and who they are sent to.</span></span>

1. <span data-ttu-id="9a8a1-114">Klicka på **Meddelanden** i det vänstra fönstret.</span><span class="sxs-lookup"><span data-stu-id="9a8a1-114">In the left pane, click **Notifications**.</span></span>
2. <span data-ttu-id="9a8a1-115">Markera kryssrutan bredvid händelserna för att skicka meddelanden för:</span><span class="sxs-lookup"><span data-stu-id="9a8a1-115">Select the check box next to the events to send notifications for:</span></span>

    - <span data-ttu-id="9a8a1-116">**Utförande** – Meddelanden skickas när uppgiften har körts.</span><span class="sxs-lookup"><span data-stu-id="9a8a1-116">**Execution** – Notifications are sent when the task has been run.</span></span>
    - <span data-ttu-id="9a8a1-117">**Annullerad** – Meddelanden skickas när uppgiften har annullerats.</span><span class="sxs-lookup"><span data-stu-id="9a8a1-117">**Canceled** – Notifications are sent when the task has been canceled.</span></span>

3. <span data-ttu-id="9a8a1-118">Välj raden för en händelse som du valde i steg 2.</span><span class="sxs-lookup"><span data-stu-id="9a8a1-118">Select the row for an event that you selected in step 2.</span></span>
4. <span data-ttu-id="9a8a1-119">Ange meddelandetexten i textrutan i fliken **Meddelandetext**.</span><span class="sxs-lookup"><span data-stu-id="9a8a1-119">On the **Notification text** tab, in the text box, enter the text of the notification.</span></span>
5. <span data-ttu-id="9a8a1-120">Om du vill anpassa meddelandet kan du infoga platshållare.</span><span class="sxs-lookup"><span data-stu-id="9a8a1-120">To personalize the notification, you can insert placeholders.</span></span> <span data-ttu-id="9a8a1-121">Platshållare ersätts med lämpliga data när meddelandet visas för användarna.</span><span class="sxs-lookup"><span data-stu-id="9a8a1-121">Placeholders are replaced with appropriate data when the notification is shown to users.</span></span> <span data-ttu-id="9a8a1-122">Följ dessa steg när du vill infoga en platshållare:</span><span class="sxs-lookup"><span data-stu-id="9a8a1-122">Follow these steps to insert a placeholder:</span></span>

    1. <span data-ttu-id="9a8a1-123">Klicka på den plats i textrutan där platshållaren ska visas.</span><span class="sxs-lookup"><span data-stu-id="9a8a1-123">In the text box, click where the placeholder should appear.</span></span>
    2. <span data-ttu-id="9a8a1-124">Klicka på **Infoga platshållare**.</span><span class="sxs-lookup"><span data-stu-id="9a8a1-124">Click **Insert placeholder**.</span></span>
    3. <span data-ttu-id="9a8a1-125">Välj önskad platshållare i listan som visas.</span><span class="sxs-lookup"><span data-stu-id="9a8a1-125">In the list that appears, select the placeholder to insert.</span></span>
    4. <span data-ttu-id="9a8a1-126">Klicka på **Infoga**.</span><span class="sxs-lookup"><span data-stu-id="9a8a1-126">Click **Insert**.</span></span>

6. <span data-ttu-id="9a8a1-127">Om du vill lägga till översättningar av meddelandet följer du dessa steg:</span><span class="sxs-lookup"><span data-stu-id="9a8a1-127">To add translations of the notification, follow these steps:</span></span>

    1. <span data-ttu-id="9a8a1-128">Klicka på **Översättningar**.</span><span class="sxs-lookup"><span data-stu-id="9a8a1-128">Click **Translations**.</span></span>
    2. <span data-ttu-id="9a8a1-129">Klicka på **Lägg till** på sidan som visas.</span><span class="sxs-lookup"><span data-stu-id="9a8a1-129">On the page that appears, click **Add**.</span></span>
    3. <span data-ttu-id="9a8a1-130">I listan som visas väljer du det språk som du skriver texten i.</span><span class="sxs-lookup"><span data-stu-id="9a8a1-130">In the list that appears, select the language that you're entering the text in.</span></span>
    4. <span data-ttu-id="9a8a1-131">I fältet **Översatt text** anger du texten.</span><span class="sxs-lookup"><span data-stu-id="9a8a1-131">In the **Translated text** field, enter the text.</span></span>
    5. <span data-ttu-id="9a8a1-132">Om du vill anpassa texten kan du infoga platshållare enligt vad som beskrivs i steg 5.</span><span class="sxs-lookup"><span data-stu-id="9a8a1-132">To personalize the text, you can insert placeholders as described in step 5.</span></span>
    6. <span data-ttu-id="9a8a1-133">Klicka på **Stäng**.</span><span class="sxs-lookup"><span data-stu-id="9a8a1-133">Click **Close**.</span></span>

7. <span data-ttu-id="9a8a1-134">Ange vem meddelandena ska skickas till i fliken **Mottagare**.</span><span class="sxs-lookup"><span data-stu-id="9a8a1-134">On the **Recipient** tab, specify who the notifications are sent to.</span></span> <span data-ttu-id="9a8a1-135">I följande register väljer du ett av alternativen och följer sedan de ytterligare stegen för detta alternativ innan du går vidare till steg 8.</span><span class="sxs-lookup"><span data-stu-id="9a8a1-135">Select one of the options in the following table, and then follow the additional steps for that option before you go to step 8.</span></span>

    <table>
    <thead>
    <tr>
    <th><span data-ttu-id="9a8a1-136">Alternativ</span><span class="sxs-lookup"><span data-stu-id="9a8a1-136">Option</span></span></th>
    <th><span data-ttu-id="9a8a1-137">Meddelandemottagare</span><span class="sxs-lookup"><span data-stu-id="9a8a1-137">Notification recipients</span></span></th>
    <th><span data-ttu-id="9a8a1-138">Ytterligare steg</span><span class="sxs-lookup"><span data-stu-id="9a8a1-138">Additional steps</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr>
    <td><span data-ttu-id="9a8a1-139">Deltagare</span><span class="sxs-lookup"><span data-stu-id="9a8a1-139">Participant</span></span></td>
    <td><span data-ttu-id="9a8a1-140">Användare som tilldelas en specifik grupp eller roll</span><span class="sxs-lookup"><span data-stu-id="9a8a1-140">Users who are assigned to a specific group or role</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="9a8a1-141">Välj <strong>Deltagare</strong> i fliken <strong>Rollbaserad</strong> i listan <strong>Deltagartyp</strong> innan du väljer den grupp- eller rolltyp som du vill skicka meddelanden till.</span><span class="sxs-lookup"><span data-stu-id="9a8a1-141">After you select <strong>Participant</strong>, on the <strong>Role based</strong> tab, in the <strong>Type of participant</strong> list, select the type of group or role to send notifications to.</span></span></li>
    <li><span data-ttu-id="9a8a1-142">Välj den grupp eller roll som du vill skicka meddelanden till i listan <strong>Deltagare</strong>.</span><span class="sxs-lookup"><span data-stu-id="9a8a1-142">In the <strong>Participant</strong> list, select the group or role to send notifications to.</span></span></li>
    </ol>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="9a8a1-143">Användare av arbetsflöde</span><span class="sxs-lookup"><span data-stu-id="9a8a1-143">Workflow user</span></span></td>
    <td><span data-ttu-id="9a8a1-144">Användare som deltar i det aktuella arbetsflödet</span><span class="sxs-lookup"><span data-stu-id="9a8a1-144">Users who participate in the current workflow</span></span></td>
    <td>
    <ul>
    <li><span data-ttu-id="9a8a1-145">När du har valt <strong>Användare av arbetsflöde</strong> i fliken <strong>Användare av arbetsflöde</strong> väljer du en användare som deltar i arbetsflödet i listan <strong>Användare av arbetsflöde</strong>.</span><span class="sxs-lookup"><span data-stu-id="9a8a1-145">After you select <strong>Workflow user</strong>, on the <strong>Workflow user</strong> tab, in the <strong>Workflow user</strong> list, select a user who participates in the workflow.</span></span></li>
    </ul>
    </td>
    </tr>
    <tr>
    <td><span data-ttu-id="9a8a1-146">Användare</span><span class="sxs-lookup"><span data-stu-id="9a8a1-146">User</span></span></td>
    <td><span data-ttu-id="9a8a1-147">Specifika användare</span><span class="sxs-lookup"><span data-stu-id="9a8a1-147">Specific users</span></span></td>
    <td>
    <ol>
    <li><span data-ttu-id="9a8a1-148">Klicka på fliken <strong>Användare</strong> när du har valt <strong>Användare</strong>.</span><span class="sxs-lookup"><span data-stu-id="9a8a1-148">After you select <strong>User</strong>, click the <strong>User</strong> tab.</span></span></li>
    <li><span data-ttu-id="9a8a1-149">Listan <strong>Tillgängliga användare</strong> innehåller alla användare.</span><span class="sxs-lookup"><span data-stu-id="9a8a1-149">The <strong>Available users</strong> list includes all users.</span></span> <span data-ttu-id="9a8a1-150">Markera de användare som du vill skicka meddelanden till, och flytta sedan dessa användare till listan <strong>Markerade användare</strong>.</span><span class="sxs-lookup"><span data-stu-id="9a8a1-150">Select the users to send notifications to, and then move those users to the <strong>Selected users</strong> list.</span></span></li>
    </ol>
    </td>
    </tr>
    </tbody>
    </table>

8. <span data-ttu-id="9a8a1-151">Upprepa stegen 3 till och med 7 för varje enskild händelse du valde i steg 2.</span><span class="sxs-lookup"><span data-stu-id="9a8a1-151">Repeat steps 3 through 7 for each event that you selected in step 2.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]