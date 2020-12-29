---
title: Ställ in prioriterade underhållsarbetare
description: I det här avsnittet beskrivs hur du ställer in prioriterade underhållsarbetare i Tillgångshantering.
author: josaw1
manager: tfehr
ms.date: 08/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkerPreferred
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: c0637609a34890360a3b81355a8d21ef1b9faf8c
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437617"
---
# <a name="set-up-preferred-maintenance-workers"></a><span data-ttu-id="e1b25-103">Ställ in prioriterade underhållsarbetare</span><span class="sxs-lookup"><span data-stu-id="e1b25-103">Set up preferred maintenance workers</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="e1b25-104">Under schemaläggning av arbetsorder kan du göra en inställning för hur underhållsarbetare eller arbetargrupper allokeras för att slutföra arbetsordern.</span><span class="sxs-lookup"><span data-stu-id="e1b25-104">During work order scheduling, you can make a preference regarding which maintenance worker or worker group is allocated to complete the work order.</span></span> <span data-ttu-id="e1b25-105">Användningen av den här funktionen är valfri, men den kan hjälpa dig att göra ett val för den mest kvalificerade underhållsarbetaren för att slutföra ett jobb, baserat på arbetarnas färdigheter och kompetenser.</span><span class="sxs-lookup"><span data-stu-id="e1b25-105">The use of this functionality is optional, but it can help you make a choice for the most qualified maintenance worker to complete a job, based on worker skills and competencies.</span></span> <span data-ttu-id="e1b25-106">Endast underhållsarbetare som är tillgängliga vid planeringstiden tidsplaneras.</span><span class="sxs-lookup"><span data-stu-id="e1b25-106">Only maintenance workers that are available at scheduling time will be scheduled.</span></span> <span data-ttu-id="e1b25-107">Om en förinställd inställning för underhållsarbetare matchar en arbetsorder under planeringen, men underhållsarbetaren allokeras till andra jobb, planeras arbetsordern till en annan, tillgänglig, underhållsarbetare.</span><span class="sxs-lookup"><span data-stu-id="e1b25-107">If a preferred maintenance worker setup matches a work order during scheduling, but the maintenance worker is allocated to other jobs, the work order will be scheduled to another available maintenance worker.</span></span>

<span data-ttu-id="e1b25-108">Innan du kan ställa in prioriterade underhållsarbetare måste du först ställa in underhållsarbetare och arbetsgrupper.</span><span class="sxs-lookup"><span data-stu-id="e1b25-108">Before you can set up preferred maintenance workers, you must first set up the maintenance workers and worker groups.</span></span> <span data-ttu-id="e1b25-109">Information om hur du ställer in underhållsarbetare och arbetargrupper finns i [Underhållsarbetare och arbetargrupper](../setup-for-objects/workers-and-worker-groups.md).</span><span class="sxs-lookup"><span data-stu-id="e1b25-109">For a description about how to set up maintenance workers and worker groups, see to [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md).</span></span>

## <a name="set-up-preferred-workers"></a><span data-ttu-id="e1b25-110">Ställa in prioriterade arbetare</span><span class="sxs-lookup"><span data-stu-id="e1b25-110">Set up preferred workers</span></span>

<span data-ttu-id="e1b25-111">En prioriterad underhållsarbetare eller arbetargrupp kan relateras till en eller flera av följande:</span><span class="sxs-lookup"><span data-stu-id="e1b25-111">A preferred maintenance worker or worker group can be related to one or more of the following:</span></span>

- <span data-ttu-id="e1b25-112">handel</span><span class="sxs-lookup"><span data-stu-id="e1b25-112">trade</span></span>  
- <span data-ttu-id="e1b25-113">variant för typen av underhållsjobb</span><span class="sxs-lookup"><span data-stu-id="e1b25-113">maintenance job type variant</span></span>  
- <span data-ttu-id="e1b25-114">underhållsjobbtyp</span><span class="sxs-lookup"><span data-stu-id="e1b25-114">maintenance job type</span></span>  
- <span data-ttu-id="e1b25-115">kategori för typ av underhållsjobb</span><span class="sxs-lookup"><span data-stu-id="e1b25-115">maintenance job type category</span></span>  
- <span data-ttu-id="e1b25-116">tillgång</span><span class="sxs-lookup"><span data-stu-id="e1b25-116">asset</span></span>  
- <span data-ttu-id="e1b25-117">tillgångstyp</span><span class="sxs-lookup"><span data-stu-id="e1b25-117">asset type</span></span>  

<span data-ttu-id="e1b25-118">Ju fler val du gör för samma post, desto mer specifika blir inställningarna.</span><span class="sxs-lookup"><span data-stu-id="e1b25-118">The more selections you make for the same record, the more specific your setup will be.</span></span>

1. <span data-ttu-id="e1b25-119">Klicka på **Tillgångshantering** > **Inställningar** > **Arbetare** > **Prioriterade underhållsarbetare**.</span><span class="sxs-lookup"><span data-stu-id="e1b25-119">Click **Asset management** > **Setup** > **Workers** > **Preferred maintenance workers**.</span></span>

2. <span data-ttu-id="e1b25-120">Klicka på **Ny** om du vill skapa en ny post.</span><span class="sxs-lookup"><span data-stu-id="e1b25-120">Click **New** to create a new record.</span></span>

3. <span data-ttu-id="e1b25-121">Börja med att skapa en "standard" underhållsarbetare eller arbetsgrupp.</span><span class="sxs-lookup"><span data-stu-id="e1b25-121">Start by creating a "default" maintenance worker or worker group.</span></span> <span data-ttu-id="e1b25-122">Det innebär att du bara gör ett val i fältet **Prioriterad underhållsarbetargrupp** eller fältet **Prioriterad underhållsarbetare**.</span><span class="sxs-lookup"><span data-stu-id="e1b25-122">This means that you only make a selection in the **Preferred maintenance worker group** field or the **Preferred maintenance worker** field.</span></span> <span data-ttu-id="e1b25-123">I skärmbilden nedan visas ett exempel i den första posten där "Begäranden" har valts som **Prioriterad underhållsarbetargrupp**.</span><span class="sxs-lookup"><span data-stu-id="e1b25-123">In the screenshot below, you see an example in the first record in which "Requests" is selected as **Preferred maintenance worker group**.</span></span>

    [!NOTE] <span data-ttu-id="e1b25-124">Den här standardinställningen kommer att användas vid schemaläggning av arbetsorder om ingen annan, mer specifik kombination matchar innehållet i arbetsordern.</span><span class="sxs-lookup"><span data-stu-id="e1b25-124">The default setup will be used during work order scheduling if no other, more specific, combination matches the contents of the work order.</span></span>

4. <span data-ttu-id="e1b25-125">Upprepa steg 2 för att skapa en ny post.</span><span class="sxs-lookup"><span data-stu-id="e1b25-125">Repeat step 2 to create a new record.</span></span> <span data-ttu-id="e1b25-126">Gör de val som krävs, beroende på detaljnivån för den prioriterade arbetaren eller arbetargruppen.</span><span class="sxs-lookup"><span data-stu-id="e1b25-126">Make the required selections, depending on the detail level for the preferred worker or worker group.</span></span> 

    <span data-ttu-id="e1b25-127">*Exempel:* I skärmbilden nedan väljs underhållsarbetaren Shawn Richardson som prioriterad arbetare.</span><span class="sxs-lookup"><span data-stu-id="e1b25-127">*Example:* In the screenshot below, in the sixth record, the maintenance worker Shawn Richardson is selected as preferred worker.</span></span> <span data-ttu-id="e1b25-128">Han väljs automatiskt under tidsplaneringen av en arbetsorder som innehåller tillgången CH-BP1-03-02 och underhållsjobbtypen "Lokalbedömning", om han är tillgänglig vid den schemalagda tiden.</span><span class="sxs-lookup"><span data-stu-id="e1b25-128">He will automatically be selected during scheduling of a work order that includes the asset "CH-BP1-03-02 and the maintenance job type "Facility assessment", if he is available at the scheduled time.</span></span>

    [!NOTE] <span data-ttu-id="e1b25-129">När en prioriterad underhållsarbetare väljs under arbetsorderplaneringen går Tillgångshantering igenom alla poster för **Prioriterade underhållsarbetare** för att söka efter en eventuell matchning, och kontrollerar alltid den mest specifika kombinationen först.</span><span class="sxs-lookup"><span data-stu-id="e1b25-129">Generally, when a preferred maintenance worker is selected during work order scheduling, Asset Management goes through all **Preferred maintenance workers** records to check for a possible match, always checking the most specific combination first.</span></span> <span data-ttu-id="e1b25-130">Om det inte går att hitta någon matchning används "standard"-posten med ett val i fältet **Prioriterad underhållsarbetargrupp** eller fältet **Prioriterad underhållsarbetare**.</span><span class="sxs-lookup"><span data-stu-id="e1b25-130">If no match is found, the "default" record with a selection in either the **Preferred maintenance worker group** field or the **Preferred maintenance worker** field is used.</span></span>

![Figur 1](media/02-work-order-scheduling.png)

<span data-ttu-id="e1b25-132">Du kan också ställa in *ansvariga* underhållsarbetare som kan väljas när en begäran om underhåll eller en arbetsorder skapas.</span><span class="sxs-lookup"><span data-stu-id="e1b25-132">You can also set up *responsible* maintenance workers who can be selected when a maintenance request or a work order is created.</span></span> <span data-ttu-id="e1b25-133">Du kan redigera valet i **Alla arbetsorder** och **Alla underhållsbegäranden** om det behövs.</span><span class="sxs-lookup"><span data-stu-id="e1b25-133">You can edit the selection in **All work orders** and **All maintenance requests**, if required.</span></span> <span data-ttu-id="e1b25-134">Mer information finns i [Ansvariga underhållsarbetare](../setup-for-maintenance-requests/responsible-workers.md).</span><span class="sxs-lookup"><span data-stu-id="e1b25-134">For more information, see [Responsible maintenance workers](../setup-for-maintenance-requests/responsible-workers.md).</span></span>

<span data-ttu-id="e1b25-135">Under tidsplaneringen av arbetsordern beräknas olika poäng för att fastställa vilka arbetare som ska utföra jobben som hör till en arbetsorder (dessa poäng ställs in i **Parametrar för tillgångshantering** > **länken Schemaläggning av arbetsorder**).</span><span class="sxs-lookup"><span data-stu-id="e1b25-135">During work order scheduling, different scores are calculated to determine which workers should complete the jobs related to a work order (those scores are set up in **Asset management parameters** > **Work order scheduling** link).</span></span> <span data-ttu-id="e1b25-136">Om två eller fler prioriterade underhållsarbetare eller ansvariga underhållsarbetare får samma poäng vid tidsplaneringen av arbetsordern väljs en av dem slumpmässigt.</span><span class="sxs-lookup"><span data-stu-id="e1b25-136">If two or more preferred maintenance workers or responsible maintenance workers get the same score during work order scheduling, one worker is randomly selected.</span></span> <span data-ttu-id="e1b25-137">I annat fall är det alltid arbetaren med högst poäng som allokeras för att slutföra en arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="e1b25-137">Otherwise, it is always the worker with the highest score who is allocated to complete a work order.</span></span>

