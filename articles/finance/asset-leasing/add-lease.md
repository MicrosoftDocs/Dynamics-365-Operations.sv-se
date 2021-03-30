---
title: Lägga till och kopiera leasing (förhandsversion)
description: I det här ämnet beskrivs hur du skapar en ny leasing genom att ange information om den i Leasing av tillgångar, eller genom att kopiera information från en befintlig leasing.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 325a1b7948f3cb8033fa93b7c36f1f1f6b7dbb27
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5220021"
---
# <a name="add-or-copy-leases-preview"></a><span data-ttu-id="94ac4-103">Lägga till och kopiera leasing (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="94ac4-103">Add or copy leases (Preview)</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="94ac4-104">I det här ämnet beskrivs hur du skapar en leasing från grunden i Leasing av tillgångar och hur du skapar en leasing genom att kopiera en befintlig leasing.</span><span class="sxs-lookup"><span data-stu-id="94ac4-104">This topic explains how to create a lease from scratch in Asset leasing, and also how to create a lease by copying an existing lease.</span></span> <span data-ttu-id="94ac4-105">Processen att skapa en leasing från grunden omfattar att ange information för den nya leasingen och sedan skapa en leasingplan.</span><span class="sxs-lookup"><span data-stu-id="94ac4-105">The process for creating a lease from scratch involves entering information for the new lease and then creating a lease schedule.</span></span> <span data-ttu-id="94ac4-106">När minst en leasing har konfigurerats kan det vara enklare att kopiera informationen från en befintlig leasing och sedan redigera informationen efter behov för att skapa en ny leasing.</span><span class="sxs-lookup"><span data-stu-id="94ac4-106">After at least one lease has been set up, you might find it easier to copy the information from an existing lease and then edit that information as you require to create a new lease.</span></span>

## <a name="create-a-lease"></a><span data-ttu-id="94ac4-107">Skapa en leasing</span><span class="sxs-lookup"><span data-stu-id="94ac4-107">Create a lease</span></span>

<span data-ttu-id="94ac4-108">Följ dessa steg för att skapa en leasing i Leasing av tillgångar.</span><span class="sxs-lookup"><span data-stu-id="94ac4-108">Follow these steps to create a lease in Asset leasing.</span></span>

1. <span data-ttu-id="94ac4-109">På sidan **Sammanfattning av leasing** i åtgärdsfönstret väljer du **Ny**.</span><span class="sxs-lookup"><span data-stu-id="94ac4-109">On the **Lease summary** page, on the Action Pane, select **New**.</span></span>
2. <span data-ttu-id="94ac4-110">Ange information om leasingen.</span><span class="sxs-lookup"><span data-stu-id="94ac4-110">Enter the lease information.</span></span> <span data-ttu-id="94ac4-111">Obligatoriska fält har röda kantlinjer.</span><span class="sxs-lookup"><span data-stu-id="94ac4-111">Fields that are required have red borders.</span></span>

## <a name="create-a-lease-schedule"></a><span data-ttu-id="94ac4-112">Skapa en leasingplan</span><span class="sxs-lookup"><span data-stu-id="94ac4-112">Create a lease schedule</span></span>

<span data-ttu-id="94ac4-113">När du har angett all information för leasingen skapar du leasingplanen genom att följa stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="94ac4-113">After you've finished entering information for the lease, follow these steps to create a lease schedule.</span></span>

> [!NOTE]
> <span data-ttu-id="94ac4-114">De ekonomiska dimensionerna kan ändras baserat på anpassade ekonomiska dimensioner.</span><span class="sxs-lookup"><span data-stu-id="94ac4-114">The financial dimensions might change based on any custom financial dimensions.</span></span>

1. <span data-ttu-id="94ac4-115">Välj **Skapa scheman** för att generera leasingböckerna.</span><span class="sxs-lookup"><span data-stu-id="94ac4-115">Select **Create schedules** to generate the lease books.</span></span> <span data-ttu-id="94ac4-116">Leasingböckerna inkluderar planer för betalning, amortering, avskrivning och utgifts.</span><span class="sxs-lookup"><span data-stu-id="94ac4-116">The lease books include the payment, amortization, depreciation, and expense schedules.</span></span>
2. <span data-ttu-id="94ac4-117">Välj fliken **Böcker** för att få tillgång till leasingböcker och visa de nya planer som skapats.</span><span class="sxs-lookup"><span data-stu-id="94ac4-117">To access the lease books and view the newly created schedules, select the **Books** tab.</span></span>

    <span data-ttu-id="94ac4-118">På sidan **Information om bok** visas hur leasingen redovisas av de böcker som har tilldelats till den.</span><span class="sxs-lookup"><span data-stu-id="94ac4-118">The **Book details** page shows how the lease is accounted for by the books that have been allocated to it.</span></span> <span data-ttu-id="94ac4-119">Härifrån kan du visa leasingplaner.</span><span class="sxs-lookup"><span data-stu-id="94ac4-119">From here, you can view the lease schedules.</span></span>

    <span data-ttu-id="94ac4-120">Betalningsplanen innehåller inmatningar från fliken **Betalningsplanrader** på sidan **Lägg till leasing**.</span><span class="sxs-lookup"><span data-stu-id="94ac4-120">The payment schedule contains the inputs from the **Payment schedule lines** tab on the **Add lease** page.</span></span> <span data-ttu-id="94ac4-121">Du kan fortfarande ändra varje betalningsbelopp och variabel betalning.</span><span class="sxs-lookup"><span data-stu-id="94ac4-121">You can still change each payment amount and variable payment.</span></span> <span data-ttu-id="94ac4-122">Leasingskulden beräknas utifrån det ändrade betalningsplanen.</span><span class="sxs-lookup"><span data-stu-id="94ac4-122">The lease liability is calculated based on the modified payment schedule.</span></span>

4. <span data-ttu-id="94ac4-123">När du är klar med granskningen av betalningsplanen väljer du **Bekräfta plan**.</span><span class="sxs-lookup"><span data-stu-id="94ac4-123">After you've finished reviewing the payment schedule, select **Confirm schedule**.</span></span> <span data-ttu-id="94ac4-124">När planen har bekräftats går det inte längre att redigera leasingen.</span><span class="sxs-lookup"><span data-stu-id="94ac4-124">After the schedule is confirmed, the lease is no longer available for editing.</span></span>

    > [!NOTE]
    > <span data-ttu-id="94ac4-125">Leasingperioden beräknas automatiskt från betalningsplanraderna på sidan **Lägg till leasing**.</span><span class="sxs-lookup"><span data-stu-id="94ac4-125">The system automatically calculates the lease term from the payment schedule lines on the **Add lease** page.</span></span>
    >
    > <span data-ttu-id="94ac4-126">Om du vill beräkna leasingperioden i månader hittar systemet skillnaden mellan start- och slutdatum för en viss betalningsplanrad.</span><span class="sxs-lookup"><span data-stu-id="94ac4-126">To calculate the lease term in months, the system finds the difference between the start date and the end date for a specific payment schedule line.</span></span> <span data-ttu-id="94ac4-127">Därefter flyttas du till nästa betalningsplanrad och hittar differensen igen.</span><span class="sxs-lookup"><span data-stu-id="94ac4-127">It then moves to the next payment schedule line and finds the difference again.</span></span> <span data-ttu-id="94ac4-128">Slutligen summerar systemet alla belopp för att bestämma leasingperioden i månader.</span><span class="sxs-lookup"><span data-stu-id="94ac4-128">Finally, the system sums all the amounts to determine the lease term in months.</span></span>

5. <span data-ttu-id="94ac4-129">Om du vill visa de beräknade räntekostnaden för perioden öppnar du sidan **Plan för amortering av skuld**.</span><span class="sxs-lookup"><span data-stu-id="94ac4-129">To view the calculated period interest expenses, open the **Liability amortization schedule** page.</span></span> <span data-ttu-id="94ac4-130">Om du vill visa beräknad linjär avskrivning öppnar du sidan **Avskrivningsplan för tillgången**.</span><span class="sxs-lookup"><span data-stu-id="94ac4-130">To view calculated straight-line depreciation, open the **Asset depreciation schedule** page.</span></span>
6. <span data-ttu-id="94ac4-131">När du har granskat det beräknade beloppet kan du skapa den första bokföringsjournalposten på sidan **Första redovisningstillfälle**.</span><span class="sxs-lookup"><span data-stu-id="94ac4-131">After you've finished reviewing the calculated amount, you can create the initial recognition journal entry on the **Initial recognition** page.</span></span> <span data-ttu-id="94ac4-132">Ett meddelande visas om att journalen har skapats.</span><span class="sxs-lookup"><span data-stu-id="94ac4-132">You receive a message that states that the journal has been created.</span></span>

    > [!NOTE]
    > <span data-ttu-id="94ac4-133">Journalposten bokförs inte i redovisningen förrän du har bokfört transaktionen manuellt.</span><span class="sxs-lookup"><span data-stu-id="94ac4-133">The journal entry isn't posted to General ledger until you manually post the entry.</span></span>

7. <span data-ttu-id="94ac4-134">Om du vill granska den föreslagna redovisningstransaktionen innan du bokför den väljer du **Journal för leasing av tillgång**.</span><span class="sxs-lookup"><span data-stu-id="94ac4-134">To review the proposed initial recognition entry before you post it, select **Asset leasing journal**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="94ac4-135">Det går inte att skapa till journalen för leasing av tillgång manuellt.</span><span class="sxs-lookup"><span data-stu-id="94ac4-135">The Asset leasing journal can't be created manually.</span></span> <span data-ttu-id="94ac4-136">Den skapas automatiskt när leasingplanerna skapas.</span><span class="sxs-lookup"><span data-stu-id="94ac4-136">It's automatically created when lease schedules are created.</span></span>

8. <span data-ttu-id="94ac4-137">När du är klar med granskningen av den journalposten för det första bokföringstillfället och du är redo att bokföra den, väljer du **Bokför** för att redovisa ROU-tillgången och leasingskulden i redovisningen.</span><span class="sxs-lookup"><span data-stu-id="94ac4-137">When you've finished reviewing the initial recognition journal entry and are ready to post it, select **Post** to recognize the right-of-use (ROU) asset and lease liability in General ledger.</span></span>

## <a name="copy-a-lease"></a><span data-ttu-id="94ac4-138">Kopiera leasing</span><span class="sxs-lookup"><span data-stu-id="94ac4-138">Copy a lease</span></span>

<span data-ttu-id="94ac4-139">Med Leasing av tillgångar kan du kopiera informationen om en leasing för att skapa en ny leasing med samma information.</span><span class="sxs-lookup"><span data-stu-id="94ac4-139">Asset leasing lets you copy the details of a lease to create a new lease that has the same information.</span></span> <span data-ttu-id="94ac4-140">Du kan sedan ändra leasingfälten innan du skapar planerna för den kopierade leasingen.</span><span class="sxs-lookup"><span data-stu-id="94ac4-140">You can then change the lease fields before you create the schedules for the copied lease.</span></span>

1. <span data-ttu-id="94ac4-141">På sidan **Sammanfattning av leasing** väljer du leasingen som ska kopieras och i åtgärdsfönstret väljer du sedan **Kopiera leasing**.</span><span class="sxs-lookup"><span data-stu-id="94ac4-141">On the **Lease summary** page, select the lease to copy, and then, on the Action Pane, select **Copy lease**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="94ac4-142">Om parametern **Manuell** är inaktiverad för nummerserien för leasing-ID:n, genereras nästa nummer i serien automatiskt som leasing-ID för den kopierade leasingen.</span><span class="sxs-lookup"><span data-stu-id="94ac4-142">If the **Manual** parameter is turned off for the number sequence for lease IDs, the next number in the sequence is automatically generated as the lease ID of the copied lease.</span></span> <span data-ttu-id="94ac4-143">Om parametern **Manuell** är aktiverad visas ett meddelande där du uppmanas att ange leasing-ID innan du kan fortsätta kopiera leasingen.</span><span class="sxs-lookup"><span data-stu-id="94ac4-143">If the **Manual** parameter is turned on, you receive a message that prompts you to enter the lease ID before you proceed to copy the lease.</span></span>

2. <span data-ttu-id="94ac4-144">Välj **Kopiera**.</span><span class="sxs-lookup"><span data-stu-id="94ac4-144">Select **Copy**.</span></span> <span data-ttu-id="94ac4-145">Leasinginformationen från den valda leasingen kopieras till en ny leasing.</span><span class="sxs-lookup"><span data-stu-id="94ac4-145">The lease details from the selected lease are copied to a new lease.</span></span> <span data-ttu-id="94ac4-146">Du kan sedan redigera informationen om den nya leasingen innan du sparar den och skapar leasingplanerna.</span><span class="sxs-lookup"><span data-stu-id="94ac4-146">You can then edit the details of the new lease before you save it and create the lease schedules.</span></span>

## <a name="asset-leasing-journal"></a><span data-ttu-id="94ac4-147">Journal för leasing av tillgång</span><span class="sxs-lookup"><span data-stu-id="94ac4-147">Asset leasing journal</span></span>

<span data-ttu-id="94ac4-148">Alla journalposter som skapas i Leasing av tillgång ingår i journalen för leasing av tillgång.</span><span class="sxs-lookup"><span data-stu-id="94ac4-148">All journal entries that are created in Asset leasing are contained in the Asset leasing journal.</span></span> <span data-ttu-id="94ac4-149">På sidan **Journal för leasing av tillgång** (**Leasing av tillgångar \> Journalposter \> Journal för leasing av tillgång**) kan du filtrera efter bokföringsstatus, visa specifika journalposter och verifikationerna och bokföra ej bokförda journalposter.</span><span class="sxs-lookup"><span data-stu-id="94ac4-149">On the **Asset leasing journal** page (**Asset leasing \> Journal entries \> Asset leasing journal**), you can filter by posting status, view specific journal entries and the vouchers, and post unposted journal entries.</span></span>

> [!NOTE]
> <span data-ttu-id="94ac4-150">Det går inte att skapa till journalen för leasing av tillgång manuellt.</span><span class="sxs-lookup"><span data-stu-id="94ac4-150">The Asset leasing journal can't be created manually.</span></span> <span data-ttu-id="94ac4-151">Den skapas automatiskt när leasingplanerna skapas.</span><span class="sxs-lookup"><span data-stu-id="94ac4-151">It's automatically created when lease schedules are created.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]