---
title: Skapa arbetsorder från underhållsbegäran
description: I det här avsnittet beskrivs hur du skapar en arbetsorder från en underhållsbegäran i tillgångshantering.
author: josaw1
manager: AnnBe
ms.date: 10/01/2019
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
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: c42f259a57675c3dbac829d6d671e91982ef9011
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/10/2019
ms.locfileid: "2571701"
---
# <a name="create-work-orders-from-maintenance-requests"></a><span data-ttu-id="e12fe-103">Skapa arbetsorder från underhållsbegäran</span><span class="sxs-lookup"><span data-stu-id="e12fe-103">Create work orders from maintenance requests</span></span>

[!include [banner](../../includes/banner.md)]

 


<span data-ttu-id="e12fe-104">När du har skapat underhållsbegäran kan du enkelt konvertera dem till arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="e12fe-104">After you've created maintenance requests, you can easily convert them to work orders.</span></span> <span data-ttu-id="e12fe-105">I det här avsnittet beskrivs det snabbaste sättet att arbeta med underhållsbegäran, uppdatera flera underhållsbegäran samtidigt och sedan skapa en arbetsorder för flera underhållsbegäran samtidigt.</span><span class="sxs-lookup"><span data-stu-id="e12fe-105">This topic describes the quickest way to work with maintenance requests, update several maintenance requests at the same time, and then create a work order for several maintenance requests at the same time.</span></span> <span data-ttu-id="e12fe-106">På sidan **aktiva underhållsbegäran** eller **underhållsbegäran för min funktionella plats** kan du också arbeta med en underhållsbegäran i taget och konvertera en underhållsbegäran till en arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="e12fe-106">On the **Active maintenance requests** or **My functional location maintenance requests** page, you can also work with one maintenance request at a time and convert one maintenance request to a work order.</span></span>

> [!NOTE]
> <span data-ttu-id="e12fe-107">Varje underhållsbegäran kan endast relateras till en arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="e12fe-107">Every maintenance request can be related to only one work order.</span></span> <span data-ttu-id="e12fe-108">Flera underhållsbegäran kan dock inkluderas i en arbetsorder, även om underhållsbegäran har olika tillgångar.</span><span class="sxs-lookup"><span data-stu-id="e12fe-108">However, multiple maintenance requests can be included in one work order, even if the maintenance requests have different assets.</span></span>

1. <span data-ttu-id="e12fe-109">Välj **tillgångshantering** \> **allmänt** \> **underhållbegäran** \> **alla underhållbegäran**.</span><span class="sxs-lookup"><span data-stu-id="e12fe-109">Select **Asset management** \> **Common** \> **maintenance requests** \> **All maintenance requests**.</span></span>
2. <span data-ttu-id="e12fe-110">Innan du kan skapa en arbetsorder från underhållbegäran måste du minst välja en underhållsjobbtyp för underhållbegäran och även en underhålljobbtypvariant och handel, om den här informationen är relevant.</span><span class="sxs-lookup"><span data-stu-id="e12fe-110">Before you can create a work order from maintenance requests, you must select, at a minimum, a maintenance job type for the maintenance requests, and also a maintenance job type variant and trade, if this information is relevant.</span></span> <span data-ttu-id="e12fe-111">I rutnätsvyn kan du enkelt uppdatera information för en underhållsbegäran.</span><span class="sxs-lookup"><span data-stu-id="e12fe-111">In the grid view, you can easily update information for a maintenance request.</span></span>
3. <span data-ttu-id="e12fe-112">När du är redo att skapa en arbetsorder väljer du de underhållbegäran som ska inkluderas i den.</span><span class="sxs-lookup"><span data-stu-id="e12fe-112">When you're ready to create a work order, select the maintenance requests to include in it.</span></span>

    - <span data-ttu-id="e12fe-113">Om du väljer flera underhållbegäran för att konvertera till en arbetsorder måstebåde fältet **tillgång** och fältet **underhållsjobbtyp** anges innan du skapar arbetsordern.</span><span class="sxs-lookup"><span data-stu-id="e12fe-113">If you select several maintenance requests to convert to a work order, both the **Asset** field and the **Maintenance job type** field must be set before you create the work order.</span></span>
    - <span data-ttu-id="e12fe-114">Om du väljer en underhållsbegäran för att konvertera till en arbetsorder måste endast fältet **tillgång** anges innan du skapar arbetsordern.</span><span class="sxs-lookup"><span data-stu-id="e12fe-114">If you select one maintenance request to convert to a work order, only the **Asset** field must be set before you create the work order.</span></span> <span data-ttu-id="e12fe-115">När du skapar arbetsordern kan du dock välja en typ av underhållsjobb (och en relaterad typ av underhållsjobbtypvariant och handel, om den här informationen är relevant) i dialogrutan **skapa arbetsorder**.</span><span class="sxs-lookup"><span data-stu-id="e12fe-115">However, when you create the work order, you can select a maintenance job type (and a related maintenance job type variant and trade, if this information is relevant) in the **Create work order** dialog box.</span></span>

4. <span data-ttu-id="e12fe-116">Välj **arbetsorder**.</span><span class="sxs-lookup"><span data-stu-id="e12fe-116">Select **Work order**.</span></span>
5. <span data-ttu-id="e12fe-117">I dialogrutan **skapa arbetsorder** anger du fälten och väljer sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="e12fe-117">In the **Create work order** dialog box, set the fields, and then select **OK**.</span></span>

    <span data-ttu-id="e12fe-118">Ett meddelandefält kan meddela dig att en ny arbetsorder har skapats.</span><span class="sxs-lookup"><span data-stu-id="e12fe-118">A message bar might notify you that a new work order has been created.</span></span>

    <span data-ttu-id="e12fe-119">När du skapar en arbetsorder som baseras på en underhållbegäran, om tillgången som är relaterad till underhållbegäran ingår i ett garantiavtal, meddelar dessutom ett meddelandefält dig om garantiavtalet.</span><span class="sxs-lookup"><span data-stu-id="e12fe-119">Additionally, when you create a work order that is based on a maintenance request, if the asset that is related to the maintenance request is included in a warranty agreement, a message bar notifies you about the warranty agreement.</span></span>

6. <span data-ttu-id="e12fe-120">Välj **tillgångshantering** \> **allmänt** \> **arbetsorder** \> **alla arbetsorder** och öppna den nya arbetsordern.</span><span class="sxs-lookup"><span data-stu-id="e12fe-120">Select **Asset management** \> **Common** \> **Work orders** \> **All work orders**, and open the new work order.</span></span>

    ![Öppna ny arbetsorder](media/05-manage-maintenance-requests.png)

