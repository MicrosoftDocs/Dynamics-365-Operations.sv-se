---
title: Konfigurera kommande livshändelser
description: Du kan schemalägga framtida livhändelser i Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
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
ms.openlocfilehash: f10d7b6c9b45f6cedc16972fb157e43b7e0c40b3
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2021
ms.locfileid: "5114337"
---
# <a name="configure-future-life-events"></a><span data-ttu-id="7336b-103">Konfigurera kommande livshändelser</span><span class="sxs-lookup"><span data-stu-id="7336b-103">Configure future life events</span></span>

<span data-ttu-id="7336b-104">Du kan schemalägga framtida livhändelser i Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="7336b-104">You can schedule future life events in Dynamics 365 Human Resources.</span></span>

1. <span data-ttu-id="7336b-105">I arbetsytan **Förmånshantering** under **inställningar**, välj **Framtida livshändelser**.</span><span class="sxs-lookup"><span data-stu-id="7336b-105">In the **Benefits management** workspace, under **Setup**, select **Future life events**.</span></span>

2. <span data-ttu-id="7336b-106">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="7336b-106">Select **New**.</span></span>

3. <span data-ttu-id="7336b-107">Ange värden för de följande fälten:</span><span class="sxs-lookup"><span data-stu-id="7336b-107">Specify values for the following fields:</span></span>

   | <span data-ttu-id="7336b-108">Fält</span><span class="sxs-lookup"><span data-stu-id="7336b-108">Field</span></span> | <span data-ttu-id="7336b-109">Beskrivning</span><span class="sxs-lookup"><span data-stu-id="7336b-109">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="7336b-110">Datum för livshändelse</span><span class="sxs-lookup"><span data-stu-id="7336b-110">Life event date</span></span> | <span data-ttu-id="7336b-111">Systemet bearbetar alla händelser under anmälningsperioden som inträffar fram till detta datum.</span><span class="sxs-lookup"><span data-stu-id="7336b-111">The system processes all events during the enrollment period that occur up until this date.</span></span> |
   | <span data-ttu-id="7336b-112">Lifehändelse har loggats</span><span class="sxs-lookup"><span data-stu-id="7336b-112">Life event logged</span></span> | <span data-ttu-id="7336b-113">Datum och den tid då livshändelsen loggades.</span><span class="sxs-lookup"><span data-stu-id="7336b-113">Date and time when the life event is logged.</span></span> |
   | <span data-ttu-id="7336b-114">Loggtyp</span><span class="sxs-lookup"><span data-stu-id="7336b-114">Log type</span></span> | <span data-ttu-id="7336b-115">Visar om åtgärden är något av följande:</span><span class="sxs-lookup"><span data-stu-id="7336b-115">Shows whether the action is one of the following:</span></span></br></br><span data-ttu-id="7336b-116">- **Uppdatera** – en ändring i en befintlig post som följer upp livhändelser</span><span class="sxs-lookup"><span data-stu-id="7336b-116">- **Update** – a change to an existing record that is tracking life events</span></span></br></br><span data-ttu-id="7336b-117">- **Infoga** – skapandet av en ny tjänstehändelsepost</span><span class="sxs-lookup"><span data-stu-id="7336b-117">- **Insert** – the creation of a new life event record</span></span> |
   | <span data-ttu-id="7336b-118">ID för livshändelsetyp</span><span class="sxs-lookup"><span data-stu-id="7336b-118">Life event type ID</span></span> | <span data-ttu-id="7336b-119">Unik identifierare för livshändelsen.</span><span class="sxs-lookup"><span data-stu-id="7336b-119">The life event type unique identifier.</span></span> |
   | <span data-ttu-id="7336b-120">Livshändelsetyp</span><span class="sxs-lookup"><span data-stu-id="7336b-120">Life event type</span></span> | <span data-ttu-id="7336b-121">En katalysator för att uppdatera en medarbetares förmånsanmälan.</span><span class="sxs-lookup"><span data-stu-id="7336b-121">A catalyst to updating an employee’s benefits enrollment.</span></span> <span data-ttu-id="7336b-122">Mer information finns i avsnittet om utlösare för livscykelhändelser.</span><span class="sxs-lookup"><span data-stu-id="7336b-122">For more details, see the Life event triggers section.</span></span> |
   | <span data-ttu-id="7336b-123">Status</span><span class="sxs-lookup"><span data-stu-id="7336b-123">Status</span></span> | <span data-ttu-id="7336b-124">Anger om livshändelsen har bearbetats eller inte.</span><span class="sxs-lookup"><span data-stu-id="7336b-124">Whether the life event has been processed or not.</span></span> |
   | <span data-ttu-id="7336b-125">Rad</span><span class="sxs-lookup"><span data-stu-id="7336b-125">Line</span></span> | <span data-ttu-id="7336b-126">Radnumret för den framtida livshändelsen.</span><span class="sxs-lookup"><span data-stu-id="7336b-126">The line number of the future life event.</span></span> |

4. <span data-ttu-id="7336b-127">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="7336b-127">Select **Save**.</span></span> 
