---
title: Skapa uppgiftslistor och lägga till uppgifter
description: I det här avsnittet beskrivs hur du skapar en uppgiftslista och lägger till uppgifter till dem i Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 02/10/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Release 10.0.9
ms.openlocfilehash: 1cab31784db9f3242dce20e98762088436a5a8f8
ms.sourcegitcommit: 80cbb7d22267aa6a0ae0568d0063fb95556958a5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/11/2020
ms.locfileid: "3036842"
---
# <a name="create-task-lists-and-add-tasks"></a><span data-ttu-id="61cb8-103">Skapa uppgiftslistor och lägga till uppgifter</span><span class="sxs-lookup"><span data-stu-id="61cb8-103">Create task lists and add tasks</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="61cb8-104">I det här avsnittet beskrivs hur du skapar en uppgiftslista och lägger till uppgifter till dem i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="61cb8-104">This topic describes how to create task lists and add tasks to them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="61cb8-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="61cb8-105">Overview</span></span>

<span data-ttu-id="61cb8-106">En *uppgift* definierar en specifik del av arbetet eller en åtgärd som någon måste utföra på eller före ett angivet förfallodatum.</span><span class="sxs-lookup"><span data-stu-id="61cb8-106">A *task* defines a specific piece of work or an action that someone must complete on or before a specified due date.</span></span> <span data-ttu-id="61cb8-107">I Dynamics 365 Commerce kan en uppgift innehålla detaljerade instruktioner och information om en kontaktperson.</span><span class="sxs-lookup"><span data-stu-id="61cb8-107">In Dynamics 365 Commerce, a task can include detailed instructions and information about a contact person.</span></span> <span data-ttu-id="61cb8-108">Den kan också inkludera länkar till operationer på arbetsplatsen, kassaåtgärder (POS) eller webbplatssidor, för att förbättra produktiviteten och ge den kontext som uppgiftsägaren kräver för att kunna slutföra uppgiften på ett effektivt sätt.</span><span class="sxs-lookup"><span data-stu-id="61cb8-108">It can also include links to back-office operations, point of sale (POS) operations, or site pages, to help improve productivity and provide the context that the task owner requires to complete the task efficiently.</span></span>

<span data-ttu-id="61cb8-109">En *uppgiftslista* är en samling uppgifter som måste utföras som en del av en affärsprocess.</span><span class="sxs-lookup"><span data-stu-id="61cb8-109">A *task list* is a collection of tasks that must be completed as part of a business process.</span></span> <span data-ttu-id="61cb8-110">Det kan till exempel finnas en uppgiftslista som en ny arbetare måste fylla i vid registrering, en uppgiftslista för kassörer som arbetar kvällsskift eller en uppgiftslista som måste slutföras för att förbereda butiken för en kommande julsäsong.</span><span class="sxs-lookup"><span data-stu-id="61cb8-110">For example, there might be a task list that a new worker must complete during onboarding, a task list for cashiers who work evening shifts, or a task list that must be completed to prepare the store for an upcoming holiday season.</span></span> <span data-ttu-id="61cb8-111">I Commerce kan varje uppgiftslista som har ett måldatum tilldelas ett valfritt antal butiker eller medarbetare, och den kan konfigureras att återkomma.</span><span class="sxs-lookup"><span data-stu-id="61cb8-111">In Commerce, every task list that has a target date can be assigned to any number of stores or employees, and it can be configured to recur.</span></span>

<span data-ttu-id="61cb8-112">Både chefer och arbetare kan skapa uppgiftslistor i Commerce backoffice och sedan tilldela dem till en uppsättning butiker.</span><span class="sxs-lookup"><span data-stu-id="61cb8-112">Both managers and workers can create task lists in Commerce back office, and then assign them to a set of stores.</span></span>

## <a name="create-a-task-list"></a><span data-ttu-id="61cb8-113">Skapa en uppgiftslista</span><span class="sxs-lookup"><span data-stu-id="61cb8-113">Create a task list</span></span>

<span data-ttu-id="61cb8-114">Gör så här om du vill skapa en uppgiftslista.</span><span class="sxs-lookup"><span data-stu-id="61cb8-114">To create a task list, follow these steps.</span></span>

1. <span data-ttu-id="61cb8-115">Gå till **Retail och Commerce \> Uppgiftshantering \> Administration av uppgiftshantering**.</span><span class="sxs-lookup"><span data-stu-id="61cb8-115">Go to **Retail and Commerce \> Task management \> Task management administration**.</span></span>
1. <span data-ttu-id="61cb8-116">Välj **Ny** och ange sedan värden i fälten **Namn**, **Beskrivning** och **Ägare**.</span><span class="sxs-lookup"><span data-stu-id="61cb8-116">Select **New**, and then enter values in the **Name**, **Description**, and **Owner** fields.</span></span>
1. <span data-ttu-id="61cb8-117">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="61cb8-117">Select **Save**.</span></span>

## <a name="add-tasks-to-a-task-list"></a><span data-ttu-id="61cb8-118">Lägga till uppgifter i en uppgiftslista</span><span class="sxs-lookup"><span data-stu-id="61cb8-118">Add tasks to a task list</span></span>

<span data-ttu-id="61cb8-119">Om du vill lägga till uppgifter till en uppgiftslista gör du följande.</span><span class="sxs-lookup"><span data-stu-id="61cb8-119">To add tasks to a task list, follow these steps.</span></span>
 
1. <span data-ttu-id="61cb8-120">På snabbfliken **uppgifter** i en befintlig uppgiftslista väljer du **ny** om du vill lägga till en uppgift.</span><span class="sxs-lookup"><span data-stu-id="61cb8-120">On the **Tasks** FastTab of an existing task list, select **New** to add a task.</span></span>
1. <span data-ttu-id="61cb8-121">I dialogrutan **Skapa en ny uppgift** i fältet **Namn** anger du ett namn för uppgiften.</span><span class="sxs-lookup"><span data-stu-id="61cb8-121">In the **Create a new task** dialog box, in the **Name** field, enter a name for the task.</span></span>
1. <span data-ttu-id="61cb8-122">I fältet **Förfallen data förskjuten från måldatum** anger du ett positivt eller negativt heltalsvärde.</span><span class="sxs-lookup"><span data-stu-id="61cb8-122">In the **Due data offset from target date** field, enter a positive or negative integer value.</span></span> <span data-ttu-id="61cb8-123">Ange till exempel, ange **-2** om uppgiften ska vara slutförd två dagar före förfallodatum för uppgiftslistan.</span><span class="sxs-lookup"><span data-stu-id="61cb8-123">For example, enter **-2** if the task should be completed two days before the task list's due date.</span></span>
1. <span data-ttu-id="61cb8-124">Ange detaljerade instruktioner i fältet **Anteckningar**.</span><span class="sxs-lookup"><span data-stu-id="61cb8-124">In the **Notes** field, enter detailed instructions.</span></span>
1. <span data-ttu-id="61cb8-125">I fältet **kontaktperson** anger du namnet på en ämnesexpert som uppgiftsägaren kan kontakta om han eller hon behöver hjälp.</span><span class="sxs-lookup"><span data-stu-id="61cb8-125">In the **Contact person** field, enter the name of a subject matter expert that the task owner can contact if he or she needs help.</span></span>
1. <span data-ttu-id="61cb8-126">I fältet **Uppgiftslänk**, ange en länk baserat på uppgiftens natur.</span><span class="sxs-lookup"><span data-stu-id="61cb8-126">In the **Task link** field, enter a link, based on the nature of the task.</span></span>

> [!TIP]
> <span data-ttu-id="61cb8-127">Du kan använda fältet **Tilldelad till** för att tilldela uppgifter till någon medan du skapar en uppgiftslista, rekommenderar vi att du undviker att tilldela uppgifter under skapandet av uppgiftslistan.</span><span class="sxs-lookup"><span data-stu-id="61cb8-127">Although you can use the **Assigned to** field to assign tasks to someone while you're creating a task list, we recommend that you avoid assigning tasks during task list creation.</span></span> <span data-ttu-id="61cb8-128">Tilldela i stället uppgifterna när listan är instansierad för enskilda butiker.</span><span class="sxs-lookup"><span data-stu-id="61cb8-128">Instead, assign the tasks after the list is instantiated for individual stores.</span></span>

## <a name="use-task-links-to-help-improve-worker-productivity"></a><span data-ttu-id="61cb8-129">Använd aktivitetslänkar för att hjälpa till att förbättra produktiviteten i arbetare</span><span class="sxs-lookup"><span data-stu-id="61cb8-129">Use task links to help improve worker productivity</span></span>

<span data-ttu-id="61cb8-130">Med hjälp av Commerce kan du länka uppgifter till specifika kassaoperationer, t.ex. att köra en försäljningsrapport, visa en utbildningsvideo för den nya personal orienteringen eller utföra en backoffice-operation.</span><span class="sxs-lookup"><span data-stu-id="61cb8-130">Commerce lets you link tasks to specific POS operations, such as running a sales report, viewing an online training video for new employee orientation, or performing a back-office operation.</span></span> <span data-ttu-id="61cb8-131">Den här funktionen hjälper aktivitetsägarna att få den information som de behöver för att utföra en uppgift på ett effektivt sätt.</span><span class="sxs-lookup"><span data-stu-id="61cb8-131">This feature helps task owners get the information that they need to complete a task efficiently.</span></span>

<span data-ttu-id="61cb8-132">Lägg till aktivitetslänkar under tiden som du skapar en uppgift genom att följa stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="61cb8-132">To add task links while you create a task, follow these steps.</span></span>

1. <span data-ttu-id="61cb8-133">På snabbfliken **uppgifter** i en befintlig uppgiftslista väljer du **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="61cb8-133">On the **Tasks** FastTab of an existing task list, select **Edit**.</span></span>
1. <span data-ttu-id="61cb8-134">I dialogrutan **Redigera uppgift** i fältet **Uppgiftslänk**, välj ett eller flera av följande alternativ:</span><span class="sxs-lookup"><span data-stu-id="61cb8-134">In the **Edit task** dialog box, in the **Task link** field, select one or more of the following options:</span></span>

    - <span data-ttu-id="61cb8-135">Välj **menyalternativet** för att konfigurera en backoffice-operation, t.ex. "produktuppsättning".</span><span class="sxs-lookup"><span data-stu-id="61cb8-135">Select **Menu item** to configure a back-office operation, such as "Product kits."</span></span>
    - <span data-ttu-id="61cb8-136">Välj **kassaoperation** för att konfigurera en kassaoperation, t.ex. försäljningsrapporter.</span><span class="sxs-lookup"><span data-stu-id="61cb8-136">Select **POS Operation** to configure a POS operation, such as "Sales reports."</span></span>
    - <span data-ttu-id="61cb8-137">Välj **URL** om du vill konfigurera en absolut URL.</span><span class="sxs-lookup"><span data-stu-id="61cb8-137">Select **URL** to configure an absolute URL.</span></span>

<span data-ttu-id="61cb8-138">Följande bild visar hur du väljer aktivitetslänkar i dialogrutan **redigera uppgift**.</span><span class="sxs-lookup"><span data-stu-id="61cb8-138">The following illustration shows the selection of task links in the **Edit task** dialog box.</span></span>

![Markera aktivitetslänkar i dialogrutan redigera uppgift](media/HQ-POS-Tasks-Linking.png)

### <a name="configure-a-pos-operation-so-that-it-can-be-linked-to-a-task"></a><span data-ttu-id="61cb8-140">Konfigurera en kassaoperation så att den kan länkas till en uppgift</span><span class="sxs-lookup"><span data-stu-id="61cb8-140">Configure a POS operation so that it can be linked to a task</span></span>

<span data-ttu-id="61cb8-141">Konfigurera en kassaoperation så att den kan länkas till en uppgift med följande steg.</span><span class="sxs-lookup"><span data-stu-id="61cb8-141">To configure a POS operation so that it can be linked to a task, follow these steps.</span></span>

1. <span data-ttu-id="61cb8-142">Navigera till **Retail och Commerce \> Kanalinställningar \> Kassainställningar \> Kassa \> Kassaoperationer**.</span><span class="sxs-lookup"><span data-stu-id="61cb8-142">Go to **Retail and Commerce \> Channel setup \> POS setup \> POS \> POS operations**.</span></span>
1. <span data-ttu-id="61cb8-143">Välj **redigera**, sök efter kassaoperationen och markera sedan kryssrutan **Aktivera aktivitetshantering** för den.</span><span class="sxs-lookup"><span data-stu-id="61cb8-143">Select **Edit**, find the POS operation, and then select the **Enable Task Management** check box for it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="61cb8-144">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="61cb8-144">Additional resources</span></span>

[<span data-ttu-id="61cb8-145">Översikt över uppgiftshantering</span><span class="sxs-lookup"><span data-stu-id="61cb8-145">Task management overview</span></span>](task-mgmt-overview.md)

[<span data-ttu-id="61cb8-146">Konfigurera uppgiftshantering</span><span class="sxs-lookup"><span data-stu-id="61cb8-146">Configure task management</span></span>](task-mgmt-configure.md)

[<span data-ttu-id="61cb8-147">Tilldela uppgiftslistor till butiker eller medarbetare</span><span class="sxs-lookup"><span data-stu-id="61cb8-147">Assign task lists to stores or employees</span></span>](task-mgmt-assign-lists.md)

[<span data-ttu-id="61cb8-148">Uppgiftshantering i kassan</span><span class="sxs-lookup"><span data-stu-id="61cb8-148">Task management in POS</span></span>](task-mgmt-POS.md)
