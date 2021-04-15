---
title: Konfigurera uppgiftshantering
description: I det här avsnittet beskrivs hur du konfigurerar funktioner för uppgiftshantering i Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 02/10/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 742d49b1b7b46952d0a8bb6c8a33cde2a35d124f
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5791714"
---
# <a name="configure-task-management"></a><span data-ttu-id="e366a-103">Konfigurera uppgiftshantering</span><span class="sxs-lookup"><span data-stu-id="e366a-103">Configure task management</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="e366a-104">I det här avsnittet beskrivs hur du konfigurerar funktioner för uppgiftshantering i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="e366a-104">This topic describes how to configure task management features in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="e366a-105">Innan Dynamics 365 Commerce chefer och medarbetare kan använda funktionerna för aktivitets hantering i Commerce måste du konfigurera uppgiftshanteringen.</span><span class="sxs-lookup"><span data-stu-id="e366a-105">Before Dynamics 365 Commerce managers and employees can use the task management features in Commerce, task management must be configured.</span></span> <span data-ttu-id="e366a-106">Konfigurationssteg omfattar beviljande av behörigheter till chefer och medarbetare, distribution av behörigheter till kassaklienter, inställning av kassameddelanden och konfigurering av panelen **Uppgifter** på startsidan för en kassaprogram.</span><span class="sxs-lookup"><span data-stu-id="e366a-106">Configuration steps include granting permissions to managers and employees, distributing permissions to point of sale (POS) clients, setting up POS notifications, and configuring the **Tasks** tile on the home page of a POS application.</span></span>

## <a name="configure-permissions-for-store-managers"></a><span data-ttu-id="e366a-107">Konfigurera behörigheter för butikshanterare</span><span class="sxs-lookup"><span data-stu-id="e366a-107">Configure permissions for store managers</span></span>

<span data-ttu-id="e366a-108">Alla arbetare i ett visst butik kan visa alla uppgifter som är tilldelade till det arkivet.</span><span class="sxs-lookup"><span data-stu-id="e366a-108">Every worker in a given store can view all tasks that are assigned to that store.</span></span> <span data-ttu-id="e366a-109">De kan också uppdatera status för de uppgifter som har tilldelats dem.</span><span class="sxs-lookup"><span data-stu-id="e366a-109">They can also update the status of the tasks that are assigned to them.</span></span> <span data-ttu-id="e366a-110">Profiler som butikschefer måste dock ha behörigheten uppgiftshantering för att hantera uppgifter som är tilldelade till butiken och för att skapa uppgifter för enskilda syften.</span><span class="sxs-lookup"><span data-stu-id="e366a-110">However, personas such as store managers must have task management permissions to manage tasks that are assigned to the store and to create single-purpose tasks.</span></span>

<span data-ttu-id="e366a-111">Konfigurera behörigheter av uppgiftshantering för butikschefer enligt följande instruktioner.</span><span class="sxs-lookup"><span data-stu-id="e366a-111">To configure task management permissions for store managers, follow these steps.</span></span>

1. <span data-ttu-id="e366a-112">Gå till **Retail och Commerce \> Medarbetare \> Behörighetsgrupper**.</span><span class="sxs-lookup"><span data-stu-id="e366a-112">Go to **Retail and Commerce \> Employees \> Permission groups**.</span></span>
1. <span data-ttu-id="e366a-113">Välj en specifik behörighetsgrupp (till exempel **chef**) och välj sedan **redigera**.</span><span class="sxs-lookup"><span data-stu-id="e366a-113">Select a specific permission group (for example, **Manager**), and then select **Edit**.</span></span>
1. <span data-ttu-id="e366a-114">På snabbfliken **behörigheter** anger du alternativet **tillåt uppgiftshantering** till **ja**.</span><span class="sxs-lookup"><span data-stu-id="e366a-114">On the **Permissions** FastTab, set the **Allow task management** option to **Yes**.</span></span>
1. <span data-ttu-id="e366a-115">På snabbfliken **meddelanden** lägger du till operationen **uppgiftshantering** och anger ett värde i fältet **visningsordning**.</span><span class="sxs-lookup"><span data-stu-id="e366a-115">On the **Notifications** FastTab, add the **Task management** operation, and enter a value in the **Display order** field.</span></span> <span data-ttu-id="e366a-116">Ange till exempel **2** om operationen **Orderuppfyllelse** redan har värdet **Visningsordning** av **1**.</span><span class="sxs-lookup"><span data-stu-id="e366a-116">For example, enter **2** if the **Order fulfillment** operation already has a **Display order** value of **1**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="e366a-117">Om en icke-chef person måste ha behörighet för uppgiftshantering i POS kan du bevilja behörighet till personen.</span><span class="sxs-lookup"><span data-stu-id="e366a-117">If a non-manager persona must have task management permissions in the POS, you can grant permission to the individual.</span></span> <span data-ttu-id="e366a-118">Du kan också skapa en ny behörighetsgrupp för icke-chefer och ange alternativet **Tillåt uppgiftshantering** till **ja**.</span><span class="sxs-lookup"><span data-stu-id="e366a-118">Alternatively, you can create a new permission group for non-managers and set the **Allow task management** option to **Yes**.</span></span>

<span data-ttu-id="e366a-119">Följande illustration visar hur du konfigurerar behörigheter av uppgiftshantering för butikschefer.</span><span class="sxs-lookup"><span data-stu-id="e366a-119">The following illustration shows how to configure task management permissions for store managers.</span></span>

![Konfigurera behörigheter av uppgiftshantering för butikschefer](media/HQ-POS-Tasks-Notifications-User-Permission.png)

## <a name="configure-permissions-for-employees"></a><span data-ttu-id="e366a-121">Konfigurera behörigheter för medarbetare</span><span class="sxs-lookup"><span data-stu-id="e366a-121">Configure permissions for employees</span></span>

<span data-ttu-id="e366a-122">Medarbetare måste ha behörighet att skapa uppgiftslistor, hantera tilldelningskriterier och konfigurera återkommande uppgifter för en uppgiftslista.</span><span class="sxs-lookup"><span data-stu-id="e366a-122">Employees must have permissions to create task lists, manage assignment criteria, and configure the recurrence of any task list.</span></span> <span data-ttu-id="e366a-123">Om du vill konfigurera dessa behörigheter tilldelar du medarbetare till roll **butikshanterarens roll**.</span><span class="sxs-lookup"><span data-stu-id="e366a-123">To configure these permissions, you assign employees to the **Retail task manager** role.</span></span>

<span data-ttu-id="e366a-124">Följ dessa steg för att konfigurera behörigheter för en anställd.</span><span class="sxs-lookup"><span data-stu-id="e366a-124">To configure permissions for an employee, follow these steps.</span></span>

1. <span data-ttu-id="e366a-125">Gå till **Retail och Commerce \> Anställda \> Användare**.</span><span class="sxs-lookup"><span data-stu-id="e366a-125">Go to **Retail and Commerce \> Employees \> Users**.</span></span>
1. <span data-ttu-id="e366a-126">Välj en medarbetare.</span><span class="sxs-lookup"><span data-stu-id="e366a-126">Select an employee.</span></span>
1. <span data-ttu-id="e366a-127">På snabbfliken **Användarens roller** klicka på **Tilldela roller**.</span><span class="sxs-lookup"><span data-stu-id="e366a-127">On the **User's roles** FastTab, select **Assign roles**.</span></span>
1. <span data-ttu-id="e366a-128">I dialogrutan **Tilldela roller till användare**, välj rollen **butikshanterarens roll** och klicka sedan på **OK**.</span><span class="sxs-lookup"><span data-stu-id="e366a-128">In the **Assign roles to user** dialog box, select the **Retail task manager** role, and then select **OK**.</span></span>

## <a name="distribute-permissions-to-pos-clients"></a><span data-ttu-id="e366a-129">Distribuera behörigheter till kassaklienter</span><span class="sxs-lookup"><span data-stu-id="e366a-129">Distribute permissions to POS clients</span></span>

<span data-ttu-id="e366a-130">Innan medarbetarna kan använda kassaklienter måste behörigheterna distribueras och synkroniseras till dessa klienter.</span><span class="sxs-lookup"><span data-stu-id="e366a-130">Before employees can use POS clients, permissions must be distributed and synced to those clients.</span></span>

<span data-ttu-id="e366a-131">Distribuera behörigheter till kassaklienter enligt följande instruktioner.</span><span class="sxs-lookup"><span data-stu-id="e366a-131">To distribute permissions to POS clients, follow these steps.</span></span>

1. <span data-ttu-id="e366a-132">Gå till **Butik och handel \> Butik och handel-IT \> Distributionsschema**.</span><span class="sxs-lookup"><span data-stu-id="e366a-132">Go to **Retail and Commerce \> Retail and Commerce IT \> Distribution schedule**.</span></span>
1. <span data-ttu-id="e366a-133">Välj **1060** (**Personal**) distributionsschema och välj sedan **Kör nu**.</span><span class="sxs-lookup"><span data-stu-id="e366a-133">Select the **1060** (**Staff**) distribution schedule, and then select **Run now**.</span></span>
1. <span data-ttu-id="e366a-134">Välj **1070** (**Kanalkonfiguration**) distributionsschema och välj sedan **Kör nu**.</span><span class="sxs-lookup"><span data-stu-id="e366a-134">Select the **1070** (**Channel configuration**) distribution schedule, and then select **Run now**.</span></span>

## <a name="configure-pos-notifications-for-tasks"></a><span data-ttu-id="e366a-135">Konfigurera kassameddelanden för uppgifter</span><span class="sxs-lookup"><span data-stu-id="e366a-135">Configure POS notifications for tasks</span></span>

<span data-ttu-id="e366a-136">Uppgiftshantering måste konfigureras så att meddelanden är tillgängliga i kassaprogrammet.</span><span class="sxs-lookup"><span data-stu-id="e366a-136">Task management must be configured so that notifications are available in the POS application.</span></span>

<span data-ttu-id="e366a-137">Gör på följande vis för att konfigurera kassameddelanden.</span><span class="sxs-lookup"><span data-stu-id="e366a-137">To configure POS notifications for tasks, follow these steps.</span></span>

1. <span data-ttu-id="e366a-138">Navigera till **Retail och Commerce \> Kanalinställningar \> Kassainställningar \> Kassa \> Kassaoperationer**.</span><span class="sxs-lookup"><span data-stu-id="e366a-138">Go to **Retail and Commerce \> Channel setup \> POS setup \> POS \> POS operations**.</span></span>
1. <span data-ttu-id="e366a-139">Sökåtgärd **1400** (**Uppgiftshantering**) och markera kryssrutan **Aktivera meddelanden**.</span><span class="sxs-lookup"><span data-stu-id="e366a-139">Find operation **1400** (**Task management**), and select the **Enable notifications** check box for it.</span></span>

<span data-ttu-id="e366a-140">Följande bild visar åtgärder **Uppgiftshantering** på sidan **Kassaoperationer**.</span><span class="sxs-lookup"><span data-stu-id="e366a-140">The following illustration shows the **Task management** operation on the **POS operations** page.</span></span>

![Åtgärden uppgiftshantering på sidan kassaåtgärder](media/HQ-POS-Tasks-Notifications.png)

<span data-ttu-id="e366a-142">Mer information om hur du konfigurerar kassameddelanden finns i [Visa ordermeddelanden i POS](notifications-pos.md).</span><span class="sxs-lookup"><span data-stu-id="e366a-142">For more information about how to configure POS notifications, see [Show order notifications in the point of sale (POS)](notifications-pos.md).</span></span>

## <a name="configure-the-tasks-tile-on-a-pos-application-home-page"></a><span data-ttu-id="e366a-143">Konfigurera uppgiftspanelen på en kassaprogram startsida</span><span class="sxs-lookup"><span data-stu-id="e366a-143">Configure the Tasks tile on a POS application home page</span></span>

<span data-ttu-id="e366a-144">Innan du konfigurerar panelen **Uppgift** på startsidan för att kassaprogram, se [Skärmlayouter för POS](pos-screen-layouts.md) för information om hur du konfigurerar och lägger till nya knappar i en kassaskärmlayout.</span><span class="sxs-lookup"><span data-stu-id="e366a-144">Before you configure the **Tasks** tile on the home page of a POS application, see [Screen layouts for the point of sale (POS)](pos-screen-layouts.md) for information about how to configure and add new buttons to a POS screen layout.</span></span>

<span data-ttu-id="e366a-145">Konfigurera **uppgift** på en kassaprogram startsida, följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="e366a-145">To configure the **Tasks** tile on a POS application home page, follow these steps.</span></span>

1. <span data-ttu-id="e366a-146">Gå till **Retail och Commerce \> Kanalinställningar \> Kassainställningar \> Kassa \> Skärmlayout**.</span><span class="sxs-lookup"><span data-stu-id="e366a-146">Go to **Retail and Commerce \> Channel setup \> POS setup \> POS \> Screen layouts**.</span></span>
1. <span data-ttu-id="e366a-147">Välj en skärmlayout, välj en storlek på layouten och välj en knappsats.</span><span class="sxs-lookup"><span data-stu-id="e366a-147">Select a screen layout, select a layout size, and select a button grid.</span></span>
1. <span data-ttu-id="e366a-148">På snabbfliken **Knappsatser**, välj **Designer** om du vill redigera den valda knappsatsen.</span><span class="sxs-lookup"><span data-stu-id="e366a-148">On the **Button grids** FastTab, select **Designer** to edit the selected button grid.</span></span>
1. <span data-ttu-id="e366a-149">Lägg till en panel för **Uppgifter** till rätt avsnitt på startsidan.</span><span class="sxs-lookup"><span data-stu-id="e366a-149">Add a **Tasks** tile to the appropriate section of the home page.</span></span>

<span data-ttu-id="e366a-150">Följande illustration visar ett exempel på panelen **Uppgifter** på en kassas startsida.</span><span class="sxs-lookup"><span data-stu-id="e366a-150">The following illustration shows an example of a **Tasks** tile on a POS home page.</span></span>

![Paneluppgift på en startsida för kassa](media/POS-home-screen-tasks-button-image.png)

## <a name="additional-resources"></a><span data-ttu-id="e366a-152">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="e366a-152">Additional resources</span></span>

[<span data-ttu-id="e366a-153">Översikt över uppgiftshantering</span><span class="sxs-lookup"><span data-stu-id="e366a-153">Task management overview</span></span>](task-mgmt-overview.md)

[<span data-ttu-id="e366a-154">Skapa uppgiftslistor och lägga till uppgifter</span><span class="sxs-lookup"><span data-stu-id="e366a-154">Create task lists and add tasks</span></span>](task-mgmt-create-lists.md)

[<span data-ttu-id="e366a-155">Tilldela uppgiftslistor till butiker eller medarbetare</span><span class="sxs-lookup"><span data-stu-id="e366a-155">Assign task lists to stores or employees</span></span>](task-mgmt-assign-lists.md)

[<span data-ttu-id="e366a-156">Uppgiftshantering i POS</span><span class="sxs-lookup"><span data-stu-id="e366a-156">Task management in POS</span></span>](task-mgmt-POS.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
