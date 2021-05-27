---
title: Medarbetare som ansvarar för godkännande av avvikelser
description: I detta ämne beskrivs hur du konfigurerar arbetare som ansvarar för godkännande av avvikelser.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2d3f647de2c188661c2c9c5f31e2642c3f8ca0b5
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021790"
---
# <a name="workers-responsible-for-approving-nonconformances"></a><span data-ttu-id="59f74-103">Medarbetare som ansvarar för godkännande av avvikelser</span><span class="sxs-lookup"><span data-stu-id="59f74-103">Workers responsible for approving nonconformances</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="59f74-104">I detta ämne beskrivs hur du konfigurerar arbetare som ansvarar för godkännande av avvikelser.</span><span class="sxs-lookup"><span data-stu-id="59f74-104">This topic describes how to configure workers that are responsible for approving nonconformances.</span></span>

<span data-ttu-id="59f74-105">Avvikelser måste godkännas innan användarna kan börja registrera information som korrigeringar eller funktioner.</span><span class="sxs-lookup"><span data-stu-id="59f74-105">Nonconformances must be approved before users can start to enter details such as corrections or operations.</span></span> <span data-ttu-id="59f74-106">Innan användarna kan godkänna eller avvisa avvikelseer måste deras användar-ID (användarpost) länkas till en medarbetarpost.</span><span class="sxs-lookup"><span data-stu-id="59f74-106">Before users can approve or reject nonconformances, their user ID (user record) must be linked to a worker record.</span></span> <span data-ttu-id="59f74-107">Om du vill kan du även konfigurera medarbetare som ansvarar för kvalitet och sedan tillåta en medarbetare att godkänna arbete på uppdrag av en annan medarbetare.</span><span class="sxs-lookup"><span data-stu-id="59f74-107">You can optionally configure workers that are responsible for quality and then allow one worker to approve work on behalf of another worker.</span></span>

## <a name="enable-a-user-for-nonconformance-processing"></a><span data-ttu-id="59f74-108">Gör det möjligt för en användare att bearbeta avvikelser</span><span class="sxs-lookup"><span data-stu-id="59f74-108">Enable a user for nonconformance processing</span></span>

<span data-ttu-id="59f74-109">Innan en användare kan godkänna eller avvisa avvikelseer måste du koppla deras användarpost till en medarbetarpost.</span><span class="sxs-lookup"><span data-stu-id="59f74-109">Before a user can approve or reject nonconformances, you must link their user record to a worker record.</span></span> <span data-ttu-id="59f74-110">Godkännandefälten kan sedan ställas in automatiskt, och den aktuella användaren kan automatiskt fyllas i för tidrapporten.</span><span class="sxs-lookup"><span data-stu-id="59f74-110">The approval fields can then be automatically set, and the current user can be automatically filled in for the timesheet.</span></span> <span data-ttu-id="59f74-111">Innan användaren kan använda dokumentanteckningarna måste du aktivera dokumenthantering bland deras användaralternativ.</span><span class="sxs-lookup"><span data-stu-id="59f74-111">Before the user can use the document notes, you must activate document handling in their user options.</span></span>

1. <span data-ttu-id="59f74-112">Gå till **Systemadministration \> Användare \> Användare**.</span><span class="sxs-lookup"><span data-stu-id="59f74-112">Go to **System administration \> Users \> Users**.</span></span>
1. <span data-ttu-id="59f74-113">Sök efter och öppna den användare som ska kunna godkänna eller avvisa avvikelser.</span><span class="sxs-lookup"><span data-stu-id="59f74-113">Find and open the user who should be able to approve or reject nonconformances.</span></span>
1. <span data-ttu-id="59f74-114">Ställ in fältet **Person** som namnet på den medarbetare som är relaterad till den aktuella användarposten.</span><span class="sxs-lookup"><span data-stu-id="59f74-114">Set the **Person** field to the name of the worker that is related to the current user record.</span></span>
1. <span data-ttu-id="59f74-115">I åtgärdsfönstret väljer du **Användaralternativ**.</span><span class="sxs-lookup"><span data-stu-id="59f74-115">On the Action Pane, select **User options**.</span></span>
1. <span data-ttu-id="59f74-116">På sidan **Alternativ** för den aktuella användarposten, på fliken **Inställningar**, anger du alternativet **Aktivera dokumenthantering** som *Ja*.</span><span class="sxs-lookup"><span data-stu-id="59f74-116">On the **Options** page for the current user record, on the **Preferences** tab, set the **Enable document handling** option to *Yes*.</span></span>
1. <span data-ttu-id="59f74-117">Stäng sidorna.</span><span class="sxs-lookup"><span data-stu-id="59f74-117">Close the pages.</span></span>

## <a name="define-workers-that-are-responsible-for-quality"></a><span data-ttu-id="59f74-118">Definiera medarbetare som ansvarar för kvalitet</span><span class="sxs-lookup"><span data-stu-id="59f74-118">Define workers that are responsible for quality</span></span>

1. <span data-ttu-id="59f74-119">Gå till **Lagerhantering \> Inställningar \> Kvalitetskontroll \> Medarbetare med kvalitetsansvar**.</span><span class="sxs-lookup"><span data-stu-id="59f74-119">Go to **Inventory management \> Setup \> Quality control \> Workers responsible for quality**.</span></span>
2. <span data-ttu-id="59f74-120">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="59f74-120">On the Action Pane, select **New**.</span></span>
3. <span data-ttu-id="59f74-121">I fältet **Medarbetare** väljer du den medarbetare som anger kvalitetsdata.</span><span class="sxs-lookup"><span data-stu-id="59f74-121">In the **Worker** field, select the worker that enters quality data.</span></span>
4. <span data-ttu-id="59f74-122">I fältet **Ansvarig medarbetare** väljer du den medarbetare i vars ställe den valda medarbetaren utför arbete.</span><span class="sxs-lookup"><span data-stu-id="59f74-122">In the **Worker responsible** field, select the worker that the selected worker enters work on behalf of.</span></span> <span data-ttu-id="59f74-123">När avvikelser skapas och uppdateras anges denne medarbetare som standard i fälten **Medarbetare**.</span><span class="sxs-lookup"><span data-stu-id="59f74-123">When nonconformances are created and updated, this worker will be entered by default in **Worker** fields.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="59f74-124">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="59f74-124">Additional resources</span></span>

- [<span data-ttu-id="59f74-125">Kvalitetshantering – översikt</span><span class="sxs-lookup"><span data-stu-id="59f74-125">Quality management overview</span></span>](quality-management-processes.md)
- [<span data-ttu-id="59f74-126">Aktivera kvalitets- och avvikelsehantering</span><span class="sxs-lookup"><span data-stu-id="59f74-126">Enable quality and nonconformance management</span></span>](enable-quality-management.md)
- [<span data-ttu-id="59f74-127">Kvalitetsavgifter</span><span class="sxs-lookup"><span data-stu-id="59f74-127">Quality charges</span></span>](quality-charges.md)
- [<span data-ttu-id="59f74-128">Karantänzoner för avvikelser</span><span class="sxs-lookup"><span data-stu-id="59f74-128">Quarantine zones for nonconformances</span></span>](quality-quarantine-zones.md)
- [<span data-ttu-id="59f74-129">Diagnostyper för avvikelser</span><span class="sxs-lookup"><span data-stu-id="59f74-129">Diagnostic types for nonconformances</span></span>](quality-diagnostic-types.md)
- [<span data-ttu-id="59f74-130">Kvalitetsavgifter för avvikelser</span><span class="sxs-lookup"><span data-stu-id="59f74-130">Quality charges for nonconformances</span></span>](quality-charges.md)
- [<span data-ttu-id="59f74-131">Funktioner för avvikelser</span><span class="sxs-lookup"><span data-stu-id="59f74-131">Operations for nonconformances</span></span>](quality-operations.md)
- [<span data-ttu-id="59f74-132">Kvalitetsstyrning för lagerprocesser</span><span class="sxs-lookup"><span data-stu-id="59f74-132">Quality management for warehouse processes</span></span>](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
