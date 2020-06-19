---
title: Konfigurera kommande livshändelser
description: Du kan schemalägga framtida livhändelser i Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitFutureLifeEvents, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 78c65faa4ae0f428184700a912998e9dded026c5
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2020
ms.locfileid: "3429415"
---
# <a name="configure-future-life-events"></a><span data-ttu-id="3e9fa-103">Konfigurera kommande livshändelser</span><span class="sxs-lookup"><span data-stu-id="3e9fa-103">Configure future life events</span></span>

<span data-ttu-id="3e9fa-104">Du kan schemalägga framtida livhändelser i Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="3e9fa-104">You can schedule future life events in Dynamics 365 Human Resources.</span></span>

1. <span data-ttu-id="3e9fa-105">I arbetsytan **Förmånshantering** under **inställningar**, välj **Framtida livshändelser**.</span><span class="sxs-lookup"><span data-stu-id="3e9fa-105">In the **Benefits management** workspace, under **Setup**, select **Future life events**.</span></span>

2. <span data-ttu-id="3e9fa-106">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="3e9fa-106">Select **New**.</span></span>

3. <span data-ttu-id="3e9fa-107">Ange värden för de följande fälten:</span><span class="sxs-lookup"><span data-stu-id="3e9fa-107">Specify values for the following fields:</span></span>

   | <span data-ttu-id="3e9fa-108">Fält</span><span class="sxs-lookup"><span data-stu-id="3e9fa-108">Field</span></span> | <span data-ttu-id="3e9fa-109">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="3e9fa-109">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="3e9fa-110">Datum för livshändelse</span><span class="sxs-lookup"><span data-stu-id="3e9fa-110">Life event date</span></span> | <span data-ttu-id="3e9fa-111">Systemet bearbetar alla händelser under anmälningsperioden som inträffar fram till detta datum.</span><span class="sxs-lookup"><span data-stu-id="3e9fa-111">The system processes all events during the enrollment period that occur up until this date.</span></span> |
   | <span data-ttu-id="3e9fa-112">Lifehändelse har loggats</span><span class="sxs-lookup"><span data-stu-id="3e9fa-112">Life event logged</span></span> | <span data-ttu-id="3e9fa-113">Datum och den tid då livshändelsen loggades.</span><span class="sxs-lookup"><span data-stu-id="3e9fa-113">Date and time when the life event is logged.</span></span> |
   | <span data-ttu-id="3e9fa-114">Loggtyp</span><span class="sxs-lookup"><span data-stu-id="3e9fa-114">Log type</span></span> | <span data-ttu-id="3e9fa-115">Visar om åtgärden är något av följande:</span><span class="sxs-lookup"><span data-stu-id="3e9fa-115">Shows whether the action is one of the following:</span></span></br></br><span data-ttu-id="3e9fa-116">- **Uppdatera** – en ändring i en befintlig post som följer upp livhändelser</span><span class="sxs-lookup"><span data-stu-id="3e9fa-116">- **Update** – a change to an existing record that is tracking life events</span></span></br></br><span data-ttu-id="3e9fa-117">- **Infoga** – skapandet av en ny tjänstehändelsepost</span><span class="sxs-lookup"><span data-stu-id="3e9fa-117">- **Insert** – the creation of a new life event record</span></span> |
   | <span data-ttu-id="3e9fa-118">ID för livshändelsetyp</span><span class="sxs-lookup"><span data-stu-id="3e9fa-118">Life event type ID</span></span> | <span data-ttu-id="3e9fa-119">Unik identifierare för livshändelsen.</span><span class="sxs-lookup"><span data-stu-id="3e9fa-119">The life event type unique identifier.</span></span> |
   | <span data-ttu-id="3e9fa-120">Livshändelsetyp</span><span class="sxs-lookup"><span data-stu-id="3e9fa-120">Life event type</span></span> | <span data-ttu-id="3e9fa-121">En katalysator för att uppdatera en medarbetares förmånsanmälan.</span><span class="sxs-lookup"><span data-stu-id="3e9fa-121">A catalyst to updating an employee’s benefits enrollment.</span></span> <span data-ttu-id="3e9fa-122">Mer information finns i avsnittet om utlösare för livscykelhändelser.</span><span class="sxs-lookup"><span data-stu-id="3e9fa-122">For more details, see the Life event triggers section.</span></span> |
   | <span data-ttu-id="3e9fa-123">Status</span><span class="sxs-lookup"><span data-stu-id="3e9fa-123">Status</span></span> | <span data-ttu-id="3e9fa-124">Anger om livshändelsen har bearbetats eller inte.</span><span class="sxs-lookup"><span data-stu-id="3e9fa-124">Whether the life event has been processed or not.</span></span> |
   | <span data-ttu-id="3e9fa-125">Rad</span><span class="sxs-lookup"><span data-stu-id="3e9fa-125">Line</span></span> | <span data-ttu-id="3e9fa-126">Radnumret för den framtida livshändelsen.</span><span class="sxs-lookup"><span data-stu-id="3e9fa-126">The line number of the future life event.</span></span> |

4. <span data-ttu-id="3e9fa-127">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="3e9fa-127">Select **Save**.</span></span> 
