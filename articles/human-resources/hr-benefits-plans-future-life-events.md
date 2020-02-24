---
title: Konfigurera kommande livshändelser
description: Du kan schemalägga framtida livhändelser i Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitFutureLifeEvents
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 655070e52e3d1f43ca6904ce3218582868f193fe
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010613"
---
# <a name="configure-future-life-events"></a><span data-ttu-id="f48d8-103">Konfigurera kommande livshändelser</span><span class="sxs-lookup"><span data-stu-id="f48d8-103">Configure future life events</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="f48d8-104">Du kan schemalägga framtida livhändelser i Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="f48d8-104">You can schedule future life events in Dynamics 365 Human Resources.</span></span>

1. <span data-ttu-id="f48d8-105">I arbetsytan **Förmånshantering** under **inställningar**, välj **Framtida livshändelser**.</span><span class="sxs-lookup"><span data-stu-id="f48d8-105">In the **Benefits management** workspace, under **Setup**, select **Future life events**.</span></span>

2. <span data-ttu-id="f48d8-106">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="f48d8-106">Select **New**.</span></span>

3. <span data-ttu-id="f48d8-107">Ange värden för de följande fälten:</span><span class="sxs-lookup"><span data-stu-id="f48d8-107">Specify values for the following fields:</span></span>

   | <span data-ttu-id="f48d8-108">Fält</span><span class="sxs-lookup"><span data-stu-id="f48d8-108">Field</span></span> | <span data-ttu-id="f48d8-109">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="f48d8-109">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="f48d8-110">Datum för livshändelse</span><span class="sxs-lookup"><span data-stu-id="f48d8-110">Life event date</span></span> | <span data-ttu-id="f48d8-111">Systemet bearbetar alla händelser under anmälningsperioden som inträffar fram till detta datum.</span><span class="sxs-lookup"><span data-stu-id="f48d8-111">The system processes all events during the enrollment period that occur up until this date.</span></span> |
   | <span data-ttu-id="f48d8-112">Lifehändelse har loggats</span><span class="sxs-lookup"><span data-stu-id="f48d8-112">Life event logged</span></span> | <span data-ttu-id="f48d8-113">Datum och den tid då livshändelsen loggades.</span><span class="sxs-lookup"><span data-stu-id="f48d8-113">Date and time when the life event is logged.</span></span> |
   | <span data-ttu-id="f48d8-114">Loggtyp</span><span class="sxs-lookup"><span data-stu-id="f48d8-114">Log type</span></span> | <span data-ttu-id="f48d8-115">Visar om åtgärden är något av följande:</span><span class="sxs-lookup"><span data-stu-id="f48d8-115">Shows whether the action is one of the following:</span></span></br></br><span data-ttu-id="f48d8-116">- **Uppdatera** – en ändring i en befintlig post som följer upp livhändelser</span><span class="sxs-lookup"><span data-stu-id="f48d8-116">- **Update** – a change to an existing record that is tracking life events</span></span></br></br><span data-ttu-id="f48d8-117">- **Infoga** – skapandet av en ny tjänstehändelsepost</span><span class="sxs-lookup"><span data-stu-id="f48d8-117">- **Insert** – the creation of a new life event record</span></span> |
   | <span data-ttu-id="f48d8-118">ID för livshändelsetyp</span><span class="sxs-lookup"><span data-stu-id="f48d8-118">Life event type ID</span></span> | <span data-ttu-id="f48d8-119">Unik identifierare för livshändelsen.</span><span class="sxs-lookup"><span data-stu-id="f48d8-119">The life event type unique identifier.</span></span> |
   | <span data-ttu-id="f48d8-120">Livshändelsetyp</span><span class="sxs-lookup"><span data-stu-id="f48d8-120">Life event type</span></span> | <span data-ttu-id="f48d8-121">En katalysator för att uppdatera en medarbetares förmånsanmälan.</span><span class="sxs-lookup"><span data-stu-id="f48d8-121">A catalyst to updating an employee’s benefits enrollment.</span></span> <span data-ttu-id="f48d8-122">Mer information finns i avsnittet om utlösare för livscykelhändelser.</span><span class="sxs-lookup"><span data-stu-id="f48d8-122">For more details, see the Life event triggers section.</span></span> |
   | <span data-ttu-id="f48d8-123">Status</span><span class="sxs-lookup"><span data-stu-id="f48d8-123">Status</span></span> | <span data-ttu-id="f48d8-124">Anger om livshändelsen har bearbetats eller inte.</span><span class="sxs-lookup"><span data-stu-id="f48d8-124">Whether the life event has been processed or not.</span></span> |
   | <span data-ttu-id="f48d8-125">Rad</span><span class="sxs-lookup"><span data-stu-id="f48d8-125">Line</span></span> | <span data-ttu-id="f48d8-126">Radnumret för den framtida livshändelsen.</span><span class="sxs-lookup"><span data-stu-id="f48d8-126">The line number of the future life event.</span></span> |

4. <span data-ttu-id="f48d8-127">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="f48d8-127">Select **Save**.</span></span> 
