---
title: Ställ in prioriterade underhållsarbetare
description: I det här avsnittet beskrivs hur du ställer in prioriterade underhållsarbetare i Tillgångshantering.
author: josaw1
manager: AnnBe
ms.date: 08/19/2019
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
ms.openlocfilehash: 8f26be81e7057d0cea1473d81452216251633ad9
ms.sourcegitcommit: f93ead945afe5ae18706c66bce6e64a6b57aac50
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/19/2019
ms.locfileid: "1887421"
---
# <a name="preferred-maintenance-workers"></a><span data-ttu-id="5d876-103">Prioriterade underhållsarbetare</span><span class="sxs-lookup"><span data-stu-id="5d876-103">Preferred maintenance workers</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="5d876-104">Du kan göra en inställning för hur underhållsarbetare allokeras för att slutföra arbetsorder under tidsplaneringen av arbetsordern.</span><span class="sxs-lookup"><span data-stu-id="5d876-104">You can make a preference regarding which maintenance workers are allocated to complete work orders during work order scheduling.</span></span> <span data-ttu-id="5d876-105">Användningen av den här funktionen är valfri, men den kan hjälpa dig att göra ett val för den mest kvalificerade underhållsarbetaren för att slutföra ett jobb, baserat på arbetarnas färdigheter och kompetenser.</span><span class="sxs-lookup"><span data-stu-id="5d876-105">The use of this functionality is optional, but it can help you make a choice for the most qualified maintenance worker to complete a job, based on worker skills and competencies.</span></span> <span data-ttu-id="5d876-106">Under tidsplaneringen av arbetsordern används därför inställningarna i **Prioriterade underhållsarbetare** för att fastställa om en viss underhållsarbetare eller arbetargrupp ska tidsplaneras för en arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="5d876-106">Therefore, during work order scheduling, the setup in **Preferred maintenance workers** is used to determine if a specific maintenance worker or worker group should be scheduled for a work order.</span></span> <span data-ttu-id="5d876-107">Endast underhållsarbetare som är tillgängliga vid planeringstiden tidsplaneras.</span><span class="sxs-lookup"><span data-stu-id="5d876-107">Only maintenance workers that are available at scheduling time will be scheduled.</span></span> <span data-ttu-id="5d876-108">Om en förinställd inställning för underhållsarbetare matchar en arbetsorder under planeringen, men underhållsarbetaren allokeras till andra jobb, planeras arbetsordern till en annan, tillgänglig, underhållsarbetare.</span><span class="sxs-lookup"><span data-stu-id="5d876-108">If a preferred maintenance worker setup matches a work order during scheduling, but the maintenance worker is allocated to other jobs, the work order will be scheduled to another, available, maintenance worker.</span></span>

<span data-ttu-id="5d876-109">Innan du kan ställa in prioriterade underhållsarbetare måste du först ställa in underhållsarbetare och arbetargrupper som ska vara tillgängliga för val.</span><span class="sxs-lookup"><span data-stu-id="5d876-109">Before you can set up preferred maintenance workers, you must first set up the maintenance workers and worker groups that should be available for selection.</span></span> <span data-ttu-id="5d876-110">Information om hur du ställer in underhållsarbetare och arbetargrupper finns i [Underhållsarbetare och arbetargrupper](../setup-for-objects/workers-and-worker-groups.md).</span><span class="sxs-lookup"><span data-stu-id="5d876-110">Refer to [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md) for a description on how to set up maintenance workers and worker groups.</span></span>

## <a name="set-up-preferred-workers"></a><span data-ttu-id="5d876-111">Ställa in prioriterade arbetare</span><span class="sxs-lookup"><span data-stu-id="5d876-111">Set up preferred workers</span></span>

<span data-ttu-id="5d876-112">En prioriterad underhållsarbetare eller arbetargrupp kan relateras till en viss</span><span class="sxs-lookup"><span data-stu-id="5d876-112">A preferred maintenance worker or worker group can be related to a specific</span></span>

- <span data-ttu-id="5d876-113">handel</span><span class="sxs-lookup"><span data-stu-id="5d876-113">trade</span></span>  
- <span data-ttu-id="5d876-114">variant för typen av underhållsjobb</span><span class="sxs-lookup"><span data-stu-id="5d876-114">maintenance job type variant</span></span>  
- <span data-ttu-id="5d876-115">underhållsjobbtyp</span><span class="sxs-lookup"><span data-stu-id="5d876-115">maintenance job type</span></span>  
- <span data-ttu-id="5d876-116">kategori för typ av underhållsjobb</span><span class="sxs-lookup"><span data-stu-id="5d876-116">maintenance job type category</span></span>  
- <span data-ttu-id="5d876-117">tillgång</span><span class="sxs-lookup"><span data-stu-id="5d876-117">asset</span></span>  
- <span data-ttu-id="5d876-118">tillgångstyp</span><span class="sxs-lookup"><span data-stu-id="5d876-118">asset type</span></span>  

<span data-ttu-id="5d876-119">eller en kombination av dessa urval.</span><span class="sxs-lookup"><span data-stu-id="5d876-119">or a combination of those selections.</span></span> <span data-ttu-id="5d876-120">Ju fler val du gör för samma post, desto mer specifika blir inställningarna.</span><span class="sxs-lookup"><span data-stu-id="5d876-120">The more selections you make for the same record, the more specific your setup will be.</span></span>

1. <span data-ttu-id="5d876-121">Klicka på **Tillgångshantering** > **Inställningar** > **Arbetare** > **Prioriterade underhållsarbetare**.</span><span class="sxs-lookup"><span data-stu-id="5d876-121">Click **Asset management** > **Setup** > **Workers** > **Preferred maintenance workers**.</span></span>

2. <span data-ttu-id="5d876-122">Klicka på **Ny** om du vill skapa en ny post.</span><span class="sxs-lookup"><span data-stu-id="5d876-122">Click **New** to create a new record.</span></span>

3. <span data-ttu-id="5d876-123">Börja med att skapa en "standardinställning" för underhållsarbetare eller arbetargrupp som inte har några val i fälten som visas i punktlistan ovan.</span><span class="sxs-lookup"><span data-stu-id="5d876-123">Start by creating a "default" maintenance worker or worker group setup that has no selections in the fields shown in the bullet list above.</span></span> <span data-ttu-id="5d876-124">Det innebär att du bara gör ett val i fältet **Prioriterad underhållsarbetargrupp** eller fältet **Prioriterad underhållsarbetare**.</span><span class="sxs-lookup"><span data-stu-id="5d876-124">This means that you only make a selection in the **Preferred maintenance worker group** field or the **Preferred maintenance worker** field.</span></span> <span data-ttu-id="5d876-125">I bilden nedan visas ett exempel i den första posten där "Begäranden" har valts som prioriterad underhållsarbetargrupp.</span><span class="sxs-lookup"><span data-stu-id="5d876-125">In the figure below, you see an example in the first record in which "Requests" is selected as preferred maintenance worker group.</span></span>

>[!NOTE]
><span data-ttu-id="5d876-126">Standardinställningen kommer att användas vid schemaläggning av arbetsorder om ingen annan, mer specifik kombination matchar innehållet i arbetsordern under schemaläggningen av arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="5d876-126">The default setup will be used during work order scheduling in case no other, more specific, combination matches the contents of the work order during work order scheduling.</span></span>

4. <span data-ttu-id="5d876-127">Upprepa steg 2 för att skapa en ny post.</span><span class="sxs-lookup"><span data-stu-id="5d876-127">Repeat step 2 to create a new record.</span></span> <span data-ttu-id="5d876-128">Gör de val som krävs, beroende på detaljnivån för den prioriterade arbetaren eller arbetargruppen.</span><span class="sxs-lookup"><span data-stu-id="5d876-128">Make the required selections, depending on the detail level for the preferred worker or worker group.</span></span> <span data-ttu-id="5d876-129">*Exempel:* I den sjätte posten i bilden nedan väljs underhållsarbetaren Shawn Richardson som prioriterad arbetare.</span><span class="sxs-lookup"><span data-stu-id="5d876-129">*Example:* In the figure below, in the sixth record, the maintenance worker Shawn Richardson is selected as preferred worker.</span></span> <span data-ttu-id="5d876-130">Han väljs automatiskt under tidsplaneringen av en arbetsorder som innehåller tillgången CH-BP1-03-02 och underhållsjobbtypen "Lokalbedömning", om han är tillgänglig vid den schemalagda tiden.</span><span class="sxs-lookup"><span data-stu-id="5d876-130">He will automatically be selected during scheduling of a work order that includes the asset "CH-BP1-03-02 and the maintennace job type "Facility assessment", if he is available at the scheduled time.</span></span>

>[!NOTE]
><span data-ttu-id="5d876-131">När en prioriterad underhållsarbetare väljs under arbetsorderplaneringen går Tillgångshantering igenom alla poster för **Prioriterade underhållsarbetare** för att söka efter en eventuell matchning, och kontrollerar alltid den mest specifika kombinationen först.</span><span class="sxs-lookup"><span data-stu-id="5d876-131">Generally, when a preferred maintenance worker is selected during work order scheduling, Asset Management goes through all **Preferred maintenance workers** records to check for a possible match, always checking the most specific combination first.</span></span> <span data-ttu-id="5d876-132">Om det inte går att hitta någon matchning används "standard"-posten med ett val i fältet **Prioriterad underhållsarbetargrupp** eller fältet **Prioriterad underhållsarbetare**.</span><span class="sxs-lookup"><span data-stu-id="5d876-132">If no match is found, the "default" record with a selection in either the **Preferred maintenance worker group** field or the **Preferred maintenance worker** field is used.</span></span>


![Figur 1](media/02-work-order-scheduling.png)

<span data-ttu-id="5d876-134">Du kan också ställa in ansvariga underhållsarbetare som kan väljas när en begäran om underhåll eller en arbetsorder skapas.</span><span class="sxs-lookup"><span data-stu-id="5d876-134">You can also set up responsible maintenance workers who can be selected when a maintenance request or a work order is created.</span></span> <span data-ttu-id="5d876-135">I **Alla arbetsorder** och **Alla underhållsbegäranden** kan du redigera urvalet om det behövs.</span><span class="sxs-lookup"><span data-stu-id="5d876-135">In **All work orders** and **All maintenance requests**, you can edit the selection, if required.</span></span> <span data-ttu-id="5d876-136">Mer information finns i [Ansvariga underhållsarbetare](../setup-for-maintenance-requests/responsible-workers.md).</span><span class="sxs-lookup"><span data-stu-id="5d876-136">Refer to [Responsible maintenance workers](../setup-for-maintenance-requests/responsible-workers.md) for more information.</span></span>

<span data-ttu-id="5d876-137">Under tidsplaneringen av arbetsordern beräknas olika poäng för att fastställa vilka arbetare som ska utföra jobben som hör till en arbetsorder (dessa poäng ställs in i **Parametrar för tillgångshantering** > **länken Schemaläggning av arbetsorder**).</span><span class="sxs-lookup"><span data-stu-id="5d876-137">During work order scheduling, different scores are calculated to determine which workers should complete the jobs related to a work order (those scores are set up in **Asset management parameters** > **Work order scheduling** link).</span></span> <span data-ttu-id="5d876-138">Om två eller fler prioriterade underhållsarbetare eller ansvariga underhållsarbetare får samma poäng vid tidsplaneringen av arbetsordern väljs en av dem slumpmässigt.</span><span class="sxs-lookup"><span data-stu-id="5d876-138">If two or more preferred maintenance workers or responsible maintenance workers get the same score during work order scheduling, one worker is randomly selected.</span></span> <span data-ttu-id="5d876-139">I annat fall är det alltid arbetaren med högst poäng som allokeras för att slutföra en arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="5d876-139">Otherwise, it is always the worker with the highest score who is allocated to complete a work order.</span></span>

