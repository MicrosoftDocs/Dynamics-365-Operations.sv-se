---
title: Skapa en processmall i Attract
description: Det här avsnittet ger information om hur du skapar processmallar i Attract.
author: hasrivas
manager: AnnBe
ms.date: 10/15/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Talent
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: hasrivas
ms.search.validFrom: 2018-10-01
ms.dyn365.ops.version: AX 8.1
ms.openlocfilehash: 2b9cac68093be65584192757229c20b1a1546342
ms.sourcegitcommit: 2ebea3cbddfa0a5ef0e0fd13d3693da6152bc288
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/30/2019
ms.locfileid: "306261"
---
# <a name="create-a-process-template-in-attract"></a><span data-ttu-id="81d3c-103">Skapa en processmall i Attract</span><span class="sxs-lookup"><span data-stu-id="81d3c-103">Create a process template in Attract</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="81d3c-104">A *mall för nyanställning* innehåller de aktiviteter som ska ingå i anställningsprocessen för ett jobb.</span><span class="sxs-lookup"><span data-stu-id="81d3c-104">A *hiring process template* contains all the activities that should be included as part of the hiring process for a job.</span></span> <span data-ttu-id="81d3c-105">Det här avsnittet beskriver elementen i en processmall i Microsoft Dynamics 365 for Talent: Attract.</span><span class="sxs-lookup"><span data-stu-id="81d3c-105">This topic describes the elements of a process template in Microsoft Dynamics 365 for Talent: Attract.</span></span> <span data-ttu-id="81d3c-106">Här förklaras också hur du skapar en mall.</span><span class="sxs-lookup"><span data-stu-id="81d3c-106">It also explains how to create a template.</span></span>

> [!NOTE]
> <span data-ttu-id="81d3c-107">Mallen är en del av tillägg för Comprehensive Hiring för Attract.</span><span class="sxs-lookup"><span data-stu-id="81d3c-107">Template creation is part of the Comprehensive Hiring Add-on for Attract.</span></span>

## <a name="template-management"></a><span data-ttu-id="81d3c-108">Mallhantering</span><span class="sxs-lookup"><span data-stu-id="81d3c-108">Template management</span></span>

<span data-ttu-id="81d3c-109">Organisationer kan bestämma om teammedlemmar eller endast administratörer kan skapa processmallar i Attract.</span><span class="sxs-lookup"><span data-stu-id="81d3c-109">Organizations can decide whether team members or only admins can create process templates in Attract.</span></span> <span data-ttu-id="81d3c-110">Konfigurera mallhantering genom att gå till **Administratörscenter** \> **Mallhantering**.</span><span class="sxs-lookup"><span data-stu-id="81d3c-110">To configure template management, go to **Admin Center** \> **Template management**.</span></span> <span data-ttu-id="81d3c-111">Aktivera mallhantering för att skapa deras egna mallar.</span><span class="sxs-lookup"><span data-stu-id="81d3c-111">To let team members create their own templates, turn on template management.</span></span> <span data-ttu-id="81d3c-112">Om du inte aktiverar mallhantering kan endast administratörer skapa mallar.</span><span class="sxs-lookup"><span data-stu-id="81d3c-112">If you don't turn on template management, only admins can create templates.</span></span>

## <a name="default-template"></a><span data-ttu-id="81d3c-113">Standardmall</span><span class="sxs-lookup"><span data-stu-id="81d3c-113">Default template</span></span>

<span data-ttu-id="81d3c-114">Endast administratörer kan ange standardmallen.</span><span class="sxs-lookup"><span data-stu-id="81d3c-114">Only admins can set the default template.</span></span> <span data-ttu-id="81d3c-115">Standardmallen används om en mall inte markerats när ett jobb skapas.</span><span class="sxs-lookup"><span data-stu-id="81d3c-115">The default template is used if a template isn't selected when a job is created.</span></span> <span data-ttu-id="81d3c-116">För att konfigurera standardmallen, gå till **Administratörscenter** \> **Mallhantering**.</span><span class="sxs-lookup"><span data-stu-id="81d3c-116">To set the default template, go to **Admin Center** \> **Template management**.</span></span> <span data-ttu-id="81d3c-117">Markera knappen med tre punkter på kortet för mallen som bör vara standardmallen (**...**) och välj sedan **ange som standard**.</span><span class="sxs-lookup"><span data-stu-id="81d3c-117">On the card for the template that should be the default template, select the ellipsis button (**...**), and then select **Set as default**.</span></span>

## <a name="create-a-process-template"></a><span data-ttu-id="81d3c-118">Skapa en processmall</span><span class="sxs-lookup"><span data-stu-id="81d3c-118">Create a process template</span></span>

<span data-ttu-id="81d3c-119">Administratörer, rekryterare och anställningschefer kan skapa processmallar.</span><span class="sxs-lookup"><span data-stu-id="81d3c-119">Admins, recruiters, and hiring managers can create process templates.</span></span> <span data-ttu-id="81d3c-120">En processmall består av *faser* och *aktiviteter*.</span><span class="sxs-lookup"><span data-stu-id="81d3c-120">A process template consists of *stages* and *activities*.</span></span> <span data-ttu-id="81d3c-121">Faser grupperar en eller flera aktiviteter.</span><span class="sxs-lookup"><span data-stu-id="81d3c-121">Stages group together one or more activities.</span></span> <span data-ttu-id="81d3c-122">Som standard har varje processmall aktiviteterna potentiell kandidat, ansökan och erbjudanden.</span><span class="sxs-lookup"><span data-stu-id="81d3c-122">By default, every process template has Prospect, Application, and Offer activities.</span></span> <span data-ttu-id="81d3c-123">Faserna som innehåller dessa aktiviteter kan döpas om.</span><span class="sxs-lookup"><span data-stu-id="81d3c-123">The stages that contain these activities can be renamed.</span></span> <span data-ttu-id="81d3c-124">Du kan lägga till fler faser genom att markera **+ Ny fas**.</span><span class="sxs-lookup"><span data-stu-id="81d3c-124">You can add more stages by selecting **+ New Stage**.</span></span> <span data-ttu-id="81d3c-125">Du kan ta aktiviteter till en fas antingen genom att dra dem till lämplig fas eller genom att dubbelklicka på dem i aktivitetslistan.</span><span class="sxs-lookup"><span data-stu-id="81d3c-125">You can activities to a stage either by dragging them to the appropriate stage or by double-clicking them in the activity list.</span></span>

> [!NOTE]
> <span data-ttu-id="81d3c-126">Fasnamn visas för kandidater på sidan **Ansökningsstatus**.</span><span class="sxs-lookup"><span data-stu-id="81d3c-126">Stage names are visible to candidates on the **Application status** page.</span></span> <span data-ttu-id="81d3c-127">Du bör tänka på detta när du väljer namn för faser.</span><span class="sxs-lookup"><span data-stu-id="81d3c-127">You should consider this fact when you choose names for stages.</span></span>

<span data-ttu-id="81d3c-128">FÖr mer information om aktiviteter, se [Aktiviteter vid anställningsprocess i Attract](./activities-attract.md).</span><span class="sxs-lookup"><span data-stu-id="81d3c-128">To learn more about activities, see [Hiring process activities in Attract](./activities-attract.md).</span></span>

<span data-ttu-id="81d3c-129">Följ dessa steg om du vill skapa en mall för anställningsprocesser.</span><span class="sxs-lookup"><span data-stu-id="81d3c-129">Follow these steps to create a hiring process template.</span></span>

1. <span data-ttu-id="81d3c-130">Gå till **Mallar**.</span><span class="sxs-lookup"><span data-stu-id="81d3c-130">Go to **Templates**.</span></span>
2. <span data-ttu-id="81d3c-131">Välj **Nytt**.</span><span class="sxs-lookup"><span data-stu-id="81d3c-131">Select **New**.</span></span>
3. <span data-ttu-id="81d3c-132">I fältet **mallnamn**, ange ett namn för mallen och välj sedan **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="81d3c-132">In the **Template name** field, enter a name for the template, and then select **Create**.</span></span>
4. <span data-ttu-id="81d3c-133">I lista **Välj godkännandeprocessen** väljer du **standard** för att begära godkännande för ett jobb.</span><span class="sxs-lookup"><span data-stu-id="81d3c-133">In the **Choose the approval process** list, select **Default** to require approval for a job.</span></span>
5. <span data-ttu-id="81d3c-134">Välj om du vill aktivera eller inaktivera potentiella kandidater.</span><span class="sxs-lookup"><span data-stu-id="81d3c-134">Select to enable or disable prospects.</span></span>
6. <span data-ttu-id="81d3c-135">Valfritt: Lägg till eller ta bort faser.</span><span class="sxs-lookup"><span data-stu-id="81d3c-135">Optional: Add or remove stages.</span></span>

    - <span data-ttu-id="81d3c-136">Lägg till en fas genom att markera **+ Ny fas**.</span><span class="sxs-lookup"><span data-stu-id="81d3c-136">To add a stage, select **+ New Stage**.</span></span>
    - <span data-ttu-id="81d3c-137">Om du vill ta bort en fas, för pekaren över fasen och välj knappen för papperskorgen som visas.</span><span class="sxs-lookup"><span data-stu-id="81d3c-137">To remove a stage, hover the pointer over the stage, and then select the trash can button that appears.</span></span>

        > [!NOTE]
        > <span data-ttu-id="81d3c-138">Faserna potentiell kandidat, ansökan och erbjudanden kan inte tas bort, men kan ändra namn.</span><span class="sxs-lookup"><span data-stu-id="81d3c-138">Prospect, Application, and Offer stages can't be removed, but they can be renamed.</span></span>

7. <span data-ttu-id="81d3c-139">Valfritt: Lägg till eller ta bort aktiviteter.</span><span class="sxs-lookup"><span data-stu-id="81d3c-139">Optional: Add or remove activities.</span></span>

    - <span data-ttu-id="81d3c-140">Om du vill lägga till en aktivitet, drar du den från listan till höger till lämplig fas.</span><span class="sxs-lookup"><span data-stu-id="81d3c-140">To add an activity, drag it from the activity list on the right to the appropriate stage.</span></span> <span data-ttu-id="81d3c-141">Du kan också dubbelklicka på aktiviteten och sedan välja fasen som den ska läggas till i.</span><span class="sxs-lookup"><span data-stu-id="81d3c-141">Alternatively, double-click the activity, and then select the stage to add it to.</span></span>
    - <span data-ttu-id="81d3c-142">Om du vill ta bort en aktivitet, expandera den och välj sedan knappen för papperskorgen i aktivitetshuvudet.</span><span class="sxs-lookup"><span data-stu-id="81d3c-142">To remove an activity, expand it, and then select the trash can button on the activity header.</span></span>

8. <span data-ttu-id="81d3c-143">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="81d3c-143">Select **Save**.</span></span>
