---
title: Beräkna ränta
description: I den här proceduren visas hur du skapar, skriver ut och bokför räntefakturor.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPosting, SysQueryForm, CustInterestNote, SrsReportViewerForm
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7170a7a14237058064ed3091e9437cae312e6bd5
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2188773"
---
# <a name="process-interest"></a><span data-ttu-id="c8153-103">Beräkna ränta</span><span class="sxs-lookup"><span data-stu-id="c8153-103">Process interest</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c8153-104">I den här proceduren visas hur du skapar, skriver ut och bokför räntefakturor.</span><span class="sxs-lookup"><span data-stu-id="c8153-104">This procedure shows how to create, print, and post interest notes.</span></span> <span data-ttu-id="c8153-105">I den här uppgiften används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="c8153-105">This task uses the USMF demo company.</span></span>


## <a name="set-up-interest-on-the-posting-profile"></a><span data-ttu-id="c8153-106">Ställ in ränta i bokföringsprofilen</span><span class="sxs-lookup"><span data-stu-id="c8153-106">Set up interest on the posting profile</span></span>
1. <span data-ttu-id="c8153-107">I **navigeringsfönstret**, gå till **Moduler > Kredit och inkasso > Inställningar > Kundbokföringsprofiler**.</span><span class="sxs-lookup"><span data-stu-id="c8153-107">In the **Navigation pane**, go to **Modules > Credit and collections > Setup > Customer posting profiles**.</span></span>
2. <span data-ttu-id="c8153-108">Klicka på **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="c8153-108">Click **Edit**.</span></span>
3. <span data-ttu-id="c8153-109">På **snabbfliken Inställningar**, i fältet **Räntekod**, välj en räntekod i den nedrullningsbara listan.</span><span class="sxs-lookup"><span data-stu-id="c8153-109">In the **Setup fastTab**, in the **Interest code** field, select an interest code from the drop-down list.</span></span> <span data-ttu-id="c8153-110">Om du inte vill skapa beräkna ränta för transaktioner med denna bokföringsprofil, lämna fältet tomt.</span><span class="sxs-lookup"><span data-stu-id="c8153-110">If you do not want interest calculated for transactions using this posting profile, leave the field blank.</span></span> <span data-ttu-id="c8153-111">Snabbfliken **Registerbegränsning** gör det möjligt att ändra hur ränta bearbetas.</span><span class="sxs-lookup"><span data-stu-id="c8153-111">The **Table restriction** fastTab allows you to change the way that interest is processed.</span></span> <span data-ttu-id="c8153-112">Om detta fält har satts till Ja, beräknas ränta för denna bokföringsprofil.</span><span class="sxs-lookup"><span data-stu-id="c8153-112">If this field is set to Yes, then interest will be calculated for this posting profile.</span></span>  

## <a name="calculate-interest"></a><span data-ttu-id="c8153-113">Beräkna ränta</span><span class="sxs-lookup"><span data-stu-id="c8153-113">Calculate interest</span></span>
1. <span data-ttu-id="c8153-114">I **navigeringsfönstret**, gå till **Moduler > Kredit och inkasso > Ränta > Skapa räntefakturor**.</span><span class="sxs-lookup"><span data-stu-id="c8153-114">In the **Navigation pane**, go to **Modules > Credit and collections > Interest > Create interest notes**.</span></span>
2. <span data-ttu-id="c8153-115">Du måste välja transaktionstyperna för att beräkna ränta.</span><span class="sxs-lookup"><span data-stu-id="c8153-115">You must select the transaction types for which you will calculate interest.</span></span> <span data-ttu-id="c8153-116">Alla öppna transaktioner för dessa typer inkluderas i beräkningen.</span><span class="sxs-lookup"><span data-stu-id="c8153-116">All of the open transactions for these types will be included in the calculation.</span></span>  
3. <span data-ttu-id="c8153-117">Om du ställer in **Ränta** till Ja beräknas ränta på ränta.</span><span class="sxs-lookup"><span data-stu-id="c8153-117">If you set **Interest** to 'Yes', you will calculate interest on interest.</span></span> <span data-ttu-id="c8153-118">Du kanske du vill kontrollera lagar som styr beräkningen av ränta på ränta som inkluderar för dessa transaktioner.</span><span class="sxs-lookup"><span data-stu-id="c8153-118">You may want to check the laws governing the calculation of interest on interest before including these transactions.</span></span>  
4. <span data-ttu-id="c8153-119">I fältet **Från datum** anger du ett datum från vilket ränta ska beräknas.</span><span class="sxs-lookup"><span data-stu-id="c8153-119">In the **From date** field, enter a date from which the interest will be calculated.</span></span> <span data-ttu-id="c8153-120">Om du inte anger ett **Från datum** annulleras alla ej bokförda räntefakturor och ränta beräknas på nytt från transaktionsdatum.</span><span class="sxs-lookup"><span data-stu-id="c8153-120">If you do not specific a **From date**, then all unposted interest notes will be canceled and interest will be recalculated from the transaction date.</span></span>
5. <span data-ttu-id="c8153-121">I fältet **Till datum** anger du ett datum till vilket ränta ska beräknas.</span><span class="sxs-lookup"><span data-stu-id="c8153-121">In the **To date** field, enter a date to which the interest would be calculated.</span></span>
6. <span data-ttu-id="c8153-122">Välj ett alternativ i fältet **Använd bokföringsprofil från**.</span><span class="sxs-lookup"><span data-stu-id="c8153-122">In the **Use posting profile from** field, select an option.</span></span> <span data-ttu-id="c8153-123">Det finns tre alternativ för bokföringsprofil:</span><span class="sxs-lookup"><span data-stu-id="c8153-123">There are three posting profile options:</span></span>
    - <span data-ttu-id="c8153-124">Konto – Använd bokföringsprofilen som är tilldelad till kundkontot för respektive räntefaktura.</span><span class="sxs-lookup"><span data-stu-id="c8153-124">Account – Use the posting profile that is assigned to the customer account for each interest note.</span></span> 
    - <span data-ttu-id="c8153-125">Välj – Använd den bokföringsprofil som du väljer i fältet Bokföringsprofil.</span><span class="sxs-lookup"><span data-stu-id="c8153-125">Select – Use the posting profile that you select in the Posting profile field.</span></span>
    - <span data-ttu-id="c8153-126">Transaktion – Använd bokföringsprofilen från den transaktioner där ränta beräknas för varje räntefaktura.</span><span class="sxs-lookup"><span data-stu-id="c8153-126">Transaction – Use the individual posting profile from transactions on which interest is calculated for each interest note.</span></span> <span data-ttu-id="c8153-127">Transaktioner som inte har en tilldelad bokföringsprofil kommer använda bokföringsprofilen som angetts i området Redovisning och moms i formuläret Parametrar för kundreskontra.</span><span class="sxs-lookup"><span data-stu-id="c8153-127">Transactions that do not have an assigned posting profile will use the posting profile that is specified in the Ledger and sales tax area of the Accounts receivable parameters form.</span></span>  
7. <span data-ttu-id="c8153-128">Expandera snabbfliken **Poster som ska ingå**.</span><span class="sxs-lookup"><span data-stu-id="c8153-128">Expand the **Records to include** fastTab.</span></span>
8. <span data-ttu-id="c8153-129">Klicka på **Filter**.</span><span class="sxs-lookup"><span data-stu-id="c8153-129">Click **Filter**.</span></span>
9. <span data-ttu-id="c8153-130">I fältet **Kriterier**, ange ett kund-ID.</span><span class="sxs-lookup"><span data-stu-id="c8153-130">In the **Criteria** field, enter a Customer ID.</span></span> <span data-ttu-id="c8153-131">Till exempel "US-001".</span><span class="sxs-lookup"><span data-stu-id="c8153-131">For example, enter 'US-001'.</span></span>
6. <span data-ttu-id="c8153-132">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="c8153-132">Click **OK**.</span></span>
7. <span data-ttu-id="c8153-133">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="c8153-133">Click **OK**.</span></span>

## <a name="print-interest-notes"></a><span data-ttu-id="c8153-134">Skriv ut räntefakturor</span><span class="sxs-lookup"><span data-stu-id="c8153-134">Print interest notes</span></span>
1. <span data-ttu-id="c8153-135">I **navigeringsfönstret**, gå till **Moduler > Kredit och inkasso > Ränta > Granska och beräkna räntefakturor**.</span><span class="sxs-lookup"><span data-stu-id="c8153-135">In the **Navigation pane**, go to **Modules > Credit and collections > Interest > Review and process interest notes**.</span></span>
2. <span data-ttu-id="c8153-136">Välj Skapad i fältet **Status**.</span><span class="sxs-lookup"><span data-stu-id="c8153-136">In the **Status** field, select 'Created'.</span></span>
3. <span data-ttu-id="c8153-137">Välj Ej utskrivet i fältet **Utskriven.**</span><span class="sxs-lookup"><span data-stu-id="c8153-137">In the **Printed** field, select 'Not printed'.</span></span>
4. <span data-ttu-id="c8153-138">Klicka på **Skriv ut**.</span><span class="sxs-lookup"><span data-stu-id="c8153-138">Click **Print**.</span></span>
5. <span data-ttu-id="c8153-139">Expandera snabbfliken **Poster som ska ingå**.</span><span class="sxs-lookup"><span data-stu-id="c8153-139">Expand the **Records to include** fastTab.</span></span>
6. <span data-ttu-id="c8153-140">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="c8153-140">Click **OK**.</span></span>
7. <span data-ttu-id="c8153-141">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="c8153-141">Close the page.</span></span>

## <a name="post-the-interest-note"></a><span data-ttu-id="c8153-142">Bokför räntefakturan</span><span class="sxs-lookup"><span data-stu-id="c8153-142">Post the interest note</span></span>
1. <span data-ttu-id="c8153-143">Välj en räntefakktura som är klar att bokföra (status skapas).</span><span class="sxs-lookup"><span data-stu-id="c8153-143">Select an interest note that is ready to post (status is created).</span></span>
2. <span data-ttu-id="c8153-144">Klicka på **Bokför**.</span><span class="sxs-lookup"><span data-stu-id="c8153-144">Click **Post**.</span></span>
3. <span data-ttu-id="c8153-145">Ange bokföringsdatumet för räntefakturan.</span><span class="sxs-lookup"><span data-stu-id="c8153-145">Enter the posting date for the interest note.</span></span> <span data-ttu-id="c8153-146">Välj Ja för att skapa en redovisningstransaktion för varje räntefaktura.</span><span class="sxs-lookup"><span data-stu-id="c8153-146">Select Yes to create a general ledger transaction for each interest note.</span></span> <span data-ttu-id="c8153-147">Om du inte mväljer Ja ackumuleras räntan på alla räntefakturor till kunden och bokförs i redovisningen i en enda transaktion.</span><span class="sxs-lookup"><span data-stu-id="c8153-147">If you do not select Yes, the interest on all interest notes to the customer is accumulated and posted to the general ledger in one transaction.</span></span>  
4. <span data-ttu-id="c8153-148">Expandera snabbfliken **Poster som ska ingå**.</span><span class="sxs-lookup"><span data-stu-id="c8153-148">Expand the **Records to include** fastTab.</span></span>
5. <span data-ttu-id="c8153-149">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="c8153-149">Click **OK**.</span></span>
6. <span data-ttu-id="c8153-150">Välj Bokförd i fältet **Status.**</span><span class="sxs-lookup"><span data-stu-id="c8153-150">In the **Status** field, select 'Posted'.</span></span>

