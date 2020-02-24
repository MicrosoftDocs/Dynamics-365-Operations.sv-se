---
title: Konfigurera typer av tjänstledighet och frånvaro
description: Ställ in tjänstledighetstyper som medarbetarna kan göra i Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 1748ec2a888a50af9b9260720dfd439adc4686f9
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010638"
---
# <a name="configure-leave-and-absence-types"></a><span data-ttu-id="5e390-103">Konfigurera typer av tjänstledighet och frånvaro</span><span class="sxs-lookup"><span data-stu-id="5e390-103">Configure leave and absence types</span></span>

<span data-ttu-id="5e390-104">Tjänstledighetstyper i Dynamics 365 Human Resources definierar olika typer av frånvaro som medarbetare kan rapportera.</span><span class="sxs-lookup"><span data-stu-id="5e390-104">Leave types in Dynamics 365 Human Resources define the types of absences that employees can report.</span></span> <span data-ttu-id="5e390-105">Du kan skräddarsy tjänstledighetstyper enligt organisationens behov.</span><span class="sxs-lookup"><span data-stu-id="5e390-105">You can tailor leave types according to the needs of your organization.</span></span> <span data-ttu-id="5e390-106">Exempel på tjänstledighetstyper:</span><span class="sxs-lookup"><span data-stu-id="5e390-106">Examples of leave types include:</span></span>

- <span data-ttu-id="5e390-107">Betald ledighet (PTO)</span><span class="sxs-lookup"><span data-stu-id="5e390-107">Paid time off (PTO)</span></span>
- <span data-ttu-id="5e390-108">Obetald tjänstledighet</span><span class="sxs-lookup"><span data-stu-id="5e390-108">Unpaid leave</span></span>
- <span data-ttu-id="5e390-109">Betald semester</span><span class="sxs-lookup"><span data-stu-id="5e390-109">Paid vacation</span></span>
- <span data-ttu-id="5e390-110">Sjukfrånvaro</span><span class="sxs-lookup"><span data-stu-id="5e390-110">Sick leave</span></span>
- <span data-ttu-id="5e390-111">Sjukledighet</span><span class="sxs-lookup"><span data-stu-id="5e390-111">Medical leave</span></span>
- <span data-ttu-id="5e390-112">Föräldraledighet</span><span class="sxs-lookup"><span data-stu-id="5e390-112">Family leave</span></span>
- <span data-ttu-id="5e390-113">Kortvarig funktionsnedsättning</span><span class="sxs-lookup"><span data-stu-id="5e390-113">Short-term disability</span></span>
- <span data-ttu-id="5e390-114">Ledighet p.g.a. dödsfall</span><span class="sxs-lookup"><span data-stu-id="5e390-114">Bereavement leave</span></span>

## <a name="add-a-leave-type"></a><span data-ttu-id="5e390-115">Lägg till en tjänstledighetstyp</span><span class="sxs-lookup"><span data-stu-id="5e390-115">Add a leave type</span></span>

1. <span data-ttu-id="5e390-116">På sidan **tjänstledighet och frånvaro** välj fliken **Länkar**.</span><span class="sxs-lookup"><span data-stu-id="5e390-116">On the **Leave and absence** page, select the **Links** tab.</span></span>

2. <span data-ttu-id="5e390-117">Under **Inställningar**, välj **Typer av tjänstledighet och frånvaro**.</span><span class="sxs-lookup"><span data-stu-id="5e390-117">Under **Setup**, select **Leave and absence types**.</span></span>

3. <span data-ttu-id="5e390-118">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="5e390-118">Select **New**.</span></span>

4. <span data-ttu-id="5e390-119">Ange ett namn för tjänstledighetstyp under **Typ**, välj ett arbetsflöde från **arbetsflödes-ID** och ange en beskrivning under **Beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="5e390-119">Enter a name for the leave type under **Type**, select a workflow from **Workflow ID**, and enter a description under **Description**.</span></span>

5. <span data-ttu-id="5e390-120">I **Allmänhet**, välj **Ingen**, **Schemalagd** eller **Ej schemalagd** från listrutan **Kategori**.</span><span class="sxs-lookup"><span data-stu-id="5e390-120">In **General**, select **None**, **Scheduled**, or **Unscheduled** from the **Category** dropdown.</span></span>

6. <span data-ttu-id="5e390-121">Välj en inkomstkod i listrutan **inkomstkod**.</span><span class="sxs-lookup"><span data-stu-id="5e390-121">Select an earning code from the **Earning code** dropdown.</span></span>

7. <span data-ttu-id="5e390-122">Ange **under orsakskod** som krävs om du vill kräva en orsakskod.</span><span class="sxs-lookup"><span data-stu-id="5e390-122">Under **Reason code required**, choose whether you want to require a reason code.</span></span> <span data-ttu-id="5e390-123">Om du vill kräva orsakskoder kan du behöva lägga till dem.</span><span class="sxs-lookup"><span data-stu-id="5e390-123">If you want to require reason codes, you might need to add them.</span></span> <span data-ttu-id="5e390-124">Under **Orsakskoder**, välj **Lägg till**, välj en orsakskod och markera sedan kryssrutan **Aktivera** bredvid den.</span><span class="sxs-lookup"><span data-stu-id="5e390-124">Under **Reason codes**, select **Add**, select a reason code, and then select the **Enabled** checkbox next to it.</span></span>

8. <span data-ttu-id="5e390-125">Under **begränsa åtkomst till valda roller** väljer du om du vill begränsa åtkomsten.</span><span class="sxs-lookup"><span data-stu-id="5e390-125">Under **Restrict access to selected roles**, choose whether you want to restrict access.</span></span> <span data-ttu-id="5e390-126">Välj sedan säkerhetsrollerna under **säkerhetsroller för denna tjänstledighetstyp**.</span><span class="sxs-lookup"><span data-stu-id="5e390-126">Then select the security roles under **Security roles for this leave type**.</span></span> <span data-ttu-id="5e390-127">Säkerhetsrollerna definieras i det arbetsflöde du markerade under **arbetsflödes-ID** tidigare i den här proceduren.</span><span class="sxs-lookup"><span data-stu-id="5e390-127">The security roles are defined in the workflow you selected under **Workflow ID** earlier in this procedure.</span></span>

9. <span data-ttu-id="5e390-128">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="5e390-128">Select **Save**.</span></span>

## <a name="configure-preview-features"></a><span data-ttu-id="5e390-129">Konfigurera förhandsfunktioner</span><span class="sxs-lookup"><span data-stu-id="5e390-129">Configure preview features</span></span>

<span data-ttu-id="5e390-130">Om du har aktiverat förhandsfunktioner för tjänstledighet och frånvaro, måste du också konfigurera inställningarna för dem.</span><span class="sxs-lookup"><span data-stu-id="5e390-130">If you've enabled preview features for Leave and absence, you need to configure settings for them, too.</span></span>

[!include [banner](includes/preview-feature-leave-absence.md)]

1. <span data-ttu-id="5e390-131">Ange avrundningsalternativ för tjänstledighetstypen.</span><span class="sxs-lookup"><span data-stu-id="5e390-131">Set rounding options for the leave type.</span></span> <span data-ttu-id="5e390-132">Alternativen inkluderar **Ingen**, **Upp**, **Ned** och **Närmast**.</span><span class="sxs-lookup"><span data-stu-id="5e390-132">Options include **None**, **Up**, **Down**, and **Nearest**.</span></span> <span data-ttu-id="5e390-133">Du kan också ställa in avrundningsprecision för tjänstledighetstypen.</span><span class="sxs-lookup"><span data-stu-id="5e390-133">You can also set rounding precision for the leave type.</span></span>

2. <span data-ttu-id="5e390-134">Ange **helgdagskorrigering** för tjänstledighetstypen.</span><span class="sxs-lookup"><span data-stu-id="5e390-134">Set **Holiday correction** for the leave type.</span></span> <span data-ttu-id="5e390-135">När du väljer det här alternativet använder personal antalet helgdagar som infaller en arbetsdag för att avgöra hur ledighetstypen ska skjutas upp.</span><span class="sxs-lookup"><span data-stu-id="5e390-135">When you select this option, Human Resources uses the number of holidays that fall on a work day to determine how to accrue time off for the leave type.</span></span> <span data-ttu-id="5e390-136">Om t.ex. juldagen infaller på en måndag kommer personalavdelningen att subtrahera en dag från tjänstledighetstypen när periodiseringen bearbetas.</span><span class="sxs-lookup"><span data-stu-id="5e390-136">For example, if Christmas Day falls on a Monday, Human Resources will subtract one day from the leave type when processing accruals.</span></span>

   <span data-ttu-id="5e390-137">Du kan ange helgdagar arbetstidskalender.</span><span class="sxs-lookup"><span data-stu-id="5e390-137">You set holidays in the working time calendar.</span></span> <span data-ttu-id="5e390-138">Mer information finns i [skapa en arbetstidskalender](hr-leave-and-absence-working-time-calendar.md)</span><span class="sxs-lookup"><span data-stu-id="5e390-138">For more information, see [Create a working time calendar](hr-leave-and-absence-working-time-calendar.md)</span></span>

## <a name="see-also"></a><span data-ttu-id="5e390-139">Se även</span><span class="sxs-lookup"><span data-stu-id="5e390-139">See also</span></span>

- [<span data-ttu-id="5e390-140">Översikt över tjänstledighet och frånvaro</span><span class="sxs-lookup"><span data-stu-id="5e390-140">Leave and absence overview</span></span>](hr-leave-and-absence-overview.md)
- [<span data-ttu-id="5e390-141">Skapa en plan för tjänstledighet och frånvaro</span><span class="sxs-lookup"><span data-stu-id="5e390-141">Create a leave and absence plan</span></span>](hr-leave-and-absence-plans.md)
- [<span data-ttu-id="5e390-142">Skapa en arbetstidskalender</span><span class="sxs-lookup"><span data-stu-id="5e390-142">Create a working time calendar</span></span>](hr-leave-and-absence-working-time-calendar.md)