---
title: Felhantering
description: I det här avsnittet beskrivs felhantering i Tillgångshantering.
author: josaw1
manager: AnnBe
ms.date: 08/13/2019
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
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 48c90a8b776cc16804de8e20ada7d8ca347fa5b9
ms.sourcegitcommit: 802dbf0a744d70f9e546632d419415b0993331ab
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/13/2019
ms.locfileid: "1874749"
---
# <a name="fault-management"></a><span data-ttu-id="d95a2-103">Felhantering</span><span class="sxs-lookup"><span data-stu-id="d95a2-103">Fault management</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="d95a2-104">I tillgångshantering kan du använda feldesignern för att ställa in felsymtom, felområden och feltyper för tillgångstyper.</span><span class="sxs-lookup"><span data-stu-id="d95a2-104">In Asset Management, you can use the fault designer to set up fault symptoms, fault areas, and fault types on asset types.</span></span> <span data-ttu-id="d95a2-105">På så sätt kan du hantera fel som upptäcks på tillgångar.</span><span class="sxs-lookup"><span data-stu-id="d95a2-105">In this way, you can manage faults that are detected on assets.</span></span> <span data-ttu-id="d95a2-106">Dessutom kan felorsaker och förslag om hur du korrigerar fel registreras på en arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="d95a2-106">Additionally, fault causes and suggestions for fixing faults can be registered on a work order.</span></span>

<span data-ttu-id="d95a2-107">Processen för felregistrering och felhantering består av dessa steg.</span><span class="sxs-lookup"><span data-stu-id="d95a2-107">The process for fault registration and management consists of these steps.</span></span>

1. <span data-ttu-id="d95a2-108">Skapa en lista med felsymptom, felområden och feltyper som kan uppstå på dina tillgångstyper.</span><span class="sxs-lookup"><span data-stu-id="d95a2-108">Create a list of fault symptoms, fault areas, and fault types that might occur on your asset types.</span></span>
2. <span data-ttu-id="d95a2-109">Ställ in symptom, felområden och feltyper i feldesignern.</span><span class="sxs-lookup"><span data-stu-id="d95a2-109">In the fault designer, set up symptoms, fault areas, and fault types.</span></span>

<span data-ttu-id="d95a2-110">Här följer några exempel på hur du förstår skillnaden mellan felsymtom, felområden och feltyper.</span><span class="sxs-lookup"><span data-stu-id="d95a2-110">Here are some examples to help you understand the difference between fault symptoms, fault areas, and fault types.</span></span>

<span data-ttu-id="d95a2-111">**Felsymptom:**</span><span class="sxs-lookup"><span data-stu-id="d95a2-111">**Fault symptoms:**</span></span>

- <span data-ttu-id="d95a2-112">Ej balanserade spänningar</span><span class="sxs-lookup"><span data-stu-id="d95a2-112">Unbalanced voltages</span></span>
- <span data-ttu-id="d95a2-113">Kortslutning</span><span class="sxs-lookup"><span data-stu-id="d95a2-113">Short circuit</span></span>
- <span data-ttu-id="d95a2-114">Buller</span><span class="sxs-lookup"><span data-stu-id="d95a2-114">Noise</span></span>
- <span data-ttu-id="d95a2-115">Läckage</span><span class="sxs-lookup"><span data-stu-id="d95a2-115">Leak</span></span>
- <span data-ttu-id="d95a2-116">Vibrationer</span><span class="sxs-lookup"><span data-stu-id="d95a2-116">Vibrations</span></span>

<span data-ttu-id="d95a2-117">**Felområden:**</span><span class="sxs-lookup"><span data-stu-id="d95a2-117">**Fault areas:**</span></span>

- <span data-ttu-id="d95a2-118">Elektriskt</span><span class="sxs-lookup"><span data-stu-id="d95a2-118">Electrical</span></span>
- <span data-ttu-id="d95a2-119">Mekaniskt</span><span class="sxs-lookup"><span data-stu-id="d95a2-119">Mechanical</span></span>
- <span data-ttu-id="d95a2-120">Hydrauliskt</span><span class="sxs-lookup"><span data-stu-id="d95a2-120">Hydraulic</span></span>
- <span data-ttu-id="d95a2-121">Pneumatiskt</span><span class="sxs-lookup"><span data-stu-id="d95a2-121">Pneumatic</span></span>

<span data-ttu-id="d95a2-122">**Feltyper:**</span><span class="sxs-lookup"><span data-stu-id="d95a2-122">**Fault types:**</span></span>

- <span data-ttu-id="d95a2-123">Felaktig huvudstatorlindning</span><span class="sxs-lookup"><span data-stu-id="d95a2-123">Faulty main stator winding</span></span>
- <span data-ttu-id="d95a2-124">Trasig diod</span><span class="sxs-lookup"><span data-stu-id="d95a2-124">Faulty diode</span></span>
- <span data-ttu-id="d95a2-125">Smutsiga lindningar</span><span class="sxs-lookup"><span data-stu-id="d95a2-125">Dirty windings</span></span>
- <span data-ttu-id="d95a2-126">Defekt generator</span><span class="sxs-lookup"><span data-stu-id="d95a2-126">Defective generator</span></span>
- <span data-ttu-id="d95a2-127">Defekt sensor</span><span class="sxs-lookup"><span data-stu-id="d95a2-127">Defective sensor</span></span>

## <a name="create-fault-symptoms"></a><span data-ttu-id="d95a2-128">Skapa felsymptom</span><span class="sxs-lookup"><span data-stu-id="d95a2-128">Create fault symptoms</span></span>

<span data-ttu-id="d95a2-129">Följ dessa steg för att skapa en lista över symptom som kan användas i feldesignern.</span><span class="sxs-lookup"><span data-stu-id="d95a2-129">Follow these steps to create a list of symptoms that can be used in the fault designer.</span></span>

1. <span data-ttu-id="d95a2-130">Välj **Tillgångshantering** \> **Inställningar** \> **Fel** \> **Felsymptom**.</span><span class="sxs-lookup"><span data-stu-id="d95a2-130">Select **Asset management** \> **Setup** \> **Fault** \> **Fault symptoms**.</span></span>
2. <span data-ttu-id="d95a2-131">Välj **Ny** för att skapa en post.</span><span class="sxs-lookup"><span data-stu-id="d95a2-131">Select **New** to create a record.</span></span>
3. <span data-ttu-id="d95a2-132">Ange ett namn på felsymptomet i fältet **Felsymptom**.</span><span class="sxs-lookup"><span data-stu-id="d95a2-132">In the **Fault symptom** field, enter a name for the fault symptom.</span></span>
4. <span data-ttu-id="d95a2-133">Ange en beskrivning i fältet **beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="d95a2-133">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="d95a2-134">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="d95a2-134">Select **Save**.</span></span>

## <a name="create-fault-areas"></a><span data-ttu-id="d95a2-135">Skapa felområden</span><span class="sxs-lookup"><span data-stu-id="d95a2-135">Create fault areas</span></span>

<span data-ttu-id="d95a2-136">Följ dessa steg för att skapa en lista över områden eller platser som kan användas i feldesignern.</span><span class="sxs-lookup"><span data-stu-id="d95a2-136">Follow these steps to create a list of areas or locations that can be used in the fault designer.</span></span>

1. <span data-ttu-id="d95a2-137">Välj **Tillgångshantering** \> **Inställningar** \> **Fel** \> **Felområden**.</span><span class="sxs-lookup"><span data-stu-id="d95a2-137">Select **Asset management** \> **Setup** \> **Fault** \> **Fault areas**.</span></span>
2. <span data-ttu-id="d95a2-138">Välj **Ny** för att skapa en post.</span><span class="sxs-lookup"><span data-stu-id="d95a2-138">Select **New** to create a record.</span></span>
3. <span data-ttu-id="d95a2-139">Ange ett namn på felområdet i fältet **Felområde**.</span><span class="sxs-lookup"><span data-stu-id="d95a2-139">In the **Fault area** field, enter a name for the fault area.</span></span>
4. <span data-ttu-id="d95a2-140">Ange en beskrivning i fältet **beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="d95a2-140">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="d95a2-141">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="d95a2-141">Select **Save**.</span></span>

## <a name="create-fault-types"></a><span data-ttu-id="d95a2-142">Skapa feltyper</span><span class="sxs-lookup"><span data-stu-id="d95a2-142">Create fault types</span></span>

<span data-ttu-id="d95a2-143">Följ dessa steg för att skapa en lista över feltyper som kan användas i feldesignern.</span><span class="sxs-lookup"><span data-stu-id="d95a2-143">Follow these steps to create a list of fault types that can be used in the fault designer.</span></span>

1. <span data-ttu-id="d95a2-144">Välj **Tillgångshantering** \> **Inställningar** \> **Fel** \> **Feltyper**.</span><span class="sxs-lookup"><span data-stu-id="d95a2-144">Select **Asset management** \> **Setup** \> **Fault** \> **Fault types**.</span></span>
2. <span data-ttu-id="d95a2-145">Välj **Ny** för att skapa en post.</span><span class="sxs-lookup"><span data-stu-id="d95a2-145">Select **New** to create a record.</span></span>
3. <span data-ttu-id="d95a2-146">Ange ett namn på feltypen i fältet **Feltyp**.</span><span class="sxs-lookup"><span data-stu-id="d95a2-146">In the **Fault type** field, enter a name for the fault type.</span></span>
4. <span data-ttu-id="d95a2-147">Ange en beskrivning i fältet **beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="d95a2-147">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="d95a2-148">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="d95a2-148">Select **Save**.</span></span>

## <a name="set-up-the-fault-designer"></a><span data-ttu-id="d95a2-149">Ställa in feldesignern</span><span class="sxs-lookup"><span data-stu-id="d95a2-149">Set up the fault designer</span></span>

<span data-ttu-id="d95a2-150">I feldesignern ställer du in feldata för tillgångstyper.</span><span class="sxs-lookup"><span data-stu-id="d95a2-150">In the fault designer, you set up fault data on asset types.</span></span>

1. <span data-ttu-id="d95a2-151">Välj **Tillgångshantering** \> **Inställningar** \> **Fel** \> **Feldesigner**.</span><span class="sxs-lookup"><span data-stu-id="d95a2-151">Select **Asset management** \> **Setup** \> **Fault** \> **Fault designer**.</span></span>
2. <span data-ttu-id="d95a2-152">I det vänstra fönstret väljer du den typ av tillgång som du vill ställa in en felpost för.</span><span class="sxs-lookup"><span data-stu-id="d95a2-152">In the left pane, select the type of asset to set up a fault record for.</span></span>
3. <span data-ttu-id="d95a2-153">På snabbfliken **Felsymptom** väljer du **Lägg till rad** och väljer sedan ett felsymptom i fältet **Felsymptom**.</span><span class="sxs-lookup"><span data-stu-id="d95a2-153">On the **Fault symptom** FastTab, select **Add line**, and then, in the **Fault symptom** field, select a fault symptom.</span></span>
4. <span data-ttu-id="d95a2-154">På snabbfliken **Felområde** väljer du **Lägg till rad** och väljer sedan ett felområde i fältet **Felområde**.</span><span class="sxs-lookup"><span data-stu-id="d95a2-154">On the **Fault area** FastTab, select **Add line**, and then, in the **Fault area** field select a fault area.</span></span>
5. <span data-ttu-id="d95a2-155">På snabbfliken **Feltyp** väljer du **Lägg till rad** och väljer sedan en feltyp i fältet **Feltyp**.</span><span class="sxs-lookup"><span data-stu-id="d95a2-155">On the **Fault type** FastTab, select **Add line**, and then, in the **Fault type** field, select a fault type.</span></span>
6. <span data-ttu-id="d95a2-156">Om du snabbt vill skapa kombinationer av alla befintliga felsymptom, felområden och feltyper för den valda tillgångstypen väljer du **Skapa felkombinationer**.</span><span class="sxs-lookup"><span data-stu-id="d95a2-156">To quickly create combinations of all existing fault symptoms, areas, and types for the selected asset type, select **Create fault combinations**.</span></span> <span data-ttu-id="d95a2-157">Den här funktionen är användbar om du har lagt till många felsymptom, felområden och feltyper.</span><span class="sxs-lookup"><span data-stu-id="d95a2-157">This function is useful if you've added many fault symptoms, areas, and types.</span></span> <span data-ttu-id="d95a2-158">Det är enklare att ta bort raderna för de kombinationer som inte är relevanta för tillgångstypen än att skapa nya rader manuellt.</span><span class="sxs-lookup"><span data-stu-id="d95a2-158">It's easier to delete the lines for any combinations that aren't relevant to the asset type than to create new lines manually.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d95a2-159">Om du vill kopiera inställningarna för felsymptom, felområden och feltyper från en tillgångstyp till den valda tillgångstypen väljer du **Kopiera från tillgångstyp**.</span><span class="sxs-lookup"><span data-stu-id="d95a2-159">To copy the setup of fault symptoms, areas, and types from one asset type to the selected asset type, select **Copy from asset type**.</span></span>

7. <span data-ttu-id="d95a2-160">Spara ändringarna genom att klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="d95a2-160">Select **Save** to save your changes.</span></span>

![Figur 1](media/21-setup-for-work-orders.png)

## <a name="create-fault-causes"></a><span data-ttu-id="d95a2-162">Skapa felorsaker</span><span class="sxs-lookup"><span data-stu-id="d95a2-162">Create fault causes</span></span>

<span data-ttu-id="d95a2-163">Följ dessa steg om du vill skapa en lista med kända felorsaker som kan läggas till i en arbetsorder eller en underhållsbegäran.</span><span class="sxs-lookup"><span data-stu-id="d95a2-163">Follow these steps to create a list of known fault causes that can be added to a work order or a maintenance request.</span></span>

1. <span data-ttu-id="d95a2-164">Välj **Tillgångshantering** \> **Inställningar** \> **Fel** \> **Felorsaker**.</span><span class="sxs-lookup"><span data-stu-id="d95a2-164">Select **Asset management** \> **Setup** \> **Fault** \> **Fault causes**.</span></span>
2. <span data-ttu-id="d95a2-165">Välj **Ny** för att skapa en post.</span><span class="sxs-lookup"><span data-stu-id="d95a2-165">Select **New** to create a record.</span></span>
3. <span data-ttu-id="d95a2-166">Ange ett namn på felorsaken i fältet **Felorsak**.</span><span class="sxs-lookup"><span data-stu-id="d95a2-166">In the **Fault cause** field, enter a name for the fault cause.</span></span>
4. <span data-ttu-id="d95a2-167">Ange en beskrivning i fältet **beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="d95a2-167">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="d95a2-168">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="d95a2-168">Select **Save**.</span></span>

## <a name="create-fault-remedies"></a><span data-ttu-id="d95a2-169">Skapa fellösningar</span><span class="sxs-lookup"><span data-stu-id="d95a2-169">Create fault remedies</span></span>

<span data-ttu-id="d95a2-170">Följ dessa steg om du vill skapa en lista med förslag på lösningar och reparationer som kan läggas till i en arbetsorder eller en underhållsbegäran.</span><span class="sxs-lookup"><span data-stu-id="d95a2-170">Follow these steps to create a list of suggestions for remedy and repair that can be added to a work order or a maintenance request.</span></span>

1. <span data-ttu-id="d95a2-171">Välj **Tillgångshantering** \> **Inställningar** \> **Fel** \> **Fellösningar**.</span><span class="sxs-lookup"><span data-stu-id="d95a2-171">Select **Asset management** \> **Setup** \> **Fault** \> **Fault remedies**.</span></span>
2. <span data-ttu-id="d95a2-172">Välj **Ny** för att skapa en post.</span><span class="sxs-lookup"><span data-stu-id="d95a2-172">Select **New** to create a record.</span></span>
3. <span data-ttu-id="d95a2-173">Ange ett namn på fellösningen i fältet **Fellösning**.</span><span class="sxs-lookup"><span data-stu-id="d95a2-173">In the **Fault remedy** field, enter a name for the fault remedy.</span></span>
4. <span data-ttu-id="d95a2-174">Ange en beskrivning i fältet **beskrivning**.</span><span class="sxs-lookup"><span data-stu-id="d95a2-174">In the **Description** field, enter a description.</span></span>
5. <span data-ttu-id="d95a2-175">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="d95a2-175">Select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="d95a2-176">Du kan ändra namnen på dina felsymtom, felområden, feltyper, felorsaker och fellösningar.</span><span class="sxs-lookup"><span data-stu-id="d95a2-176">You can change the names of your fault symptoms, areas, types, causes, and remedies as you require.</span></span> <span data-ttu-id="d95a2-177">Namnändringarna återspeglas automatiskt i de relaterade felregistreringarna.</span><span class="sxs-lookup"><span data-stu-id="d95a2-177">The name changes are automatically reflected in the related fault registrations.</span></span>
