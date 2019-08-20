---
title: Bearbeta kravbrev
description: I den här proceduren visas hur du skapar, skriver ut och bokför kravbrev.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 12/04/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPosting, CustCollectionLetterNote
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2018-12-01
ms.dyn365.ops.version: 8.1.3
ms.openlocfilehash: 8db80b184d565f71f62f99051c7378c4e6e45fb9
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2019
ms.locfileid: "1834425"
---
# <a name="process-collection-letters"></a><span data-ttu-id="5f1ac-103">Bearbeta kravbrev</span><span class="sxs-lookup"><span data-stu-id="5f1ac-103">Process collection letters</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="5f1ac-104">I den här proceduren visas hur du skapar, skriver ut och bokför kravbrev.</span><span class="sxs-lookup"><span data-stu-id="5f1ac-104">This procedure shows how to create, print, and post collection letters.</span></span> <span data-ttu-id="5f1ac-105">I den här uppgiften används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="5f1ac-105">This task uses the USMF demo company.</span></span>

## <a name="set-up-a-collection-letter-sequence-on-the-posting-profile"></a><span data-ttu-id="5f1ac-106">Ställ in en kravbrevsserie för bokföringsprofilen</span><span class="sxs-lookup"><span data-stu-id="5f1ac-106">Set up a collection letter sequence on the posting profile</span></span>
1. <span data-ttu-id="5f1ac-107">Gå till **Kredit och inkasso > Inställningar > Kundbokföringsprofiler**.</span><span class="sxs-lookup"><span data-stu-id="5f1ac-107">Go to **Credit and collections > Setup > Customer posting profiles**.</span></span>
2. <span data-ttu-id="5f1ac-108">Klicka på **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="5f1ac-108">Click **Edit**.</span></span>
3. <span data-ttu-id="5f1ac-109">Välj en kravbrevssekvens i listrutan.</span><span class="sxs-lookup"><span data-stu-id="5f1ac-109">Select a collection letter sequence from the drop-down list.</span></span> <span data-ttu-id="5f1ac-110">Om du inte vill skapa kravbrev för transaktioner med denna bokföringsprofil, lämna fältet tomt.</span><span class="sxs-lookup"><span data-stu-id="5f1ac-110">If you do not want to generate collection letters for transactions using this posting profile, leave the field blank.</span></span>  
4. <span data-ttu-id="5f1ac-111">Expandera registerbegränsningsfliken för att ändra hur kravbrev bearbetas.</span><span class="sxs-lookup"><span data-stu-id="5f1ac-111">Expand the table restriction tab to change the way that collection letters are processed.</span></span> <span data-ttu-id="5f1ac-112">Om detta fält har satts till **Ja** skapas kravbrev för denna bokföringsprofil.</span><span class="sxs-lookup"><span data-stu-id="5f1ac-112">If this field is set to **Yes**, then collection letters will be created for this posting profile.</span></span>  

## <a name="create-collection-letters"></a><span data-ttu-id="5f1ac-113">Skapa kravbrev</span><span class="sxs-lookup"><span data-stu-id="5f1ac-113">Create collection letters</span></span>
1. <span data-ttu-id="5f1ac-114">Gå till **Kredit och inkasso > Kravbrev > Skapa kravbrev**.</span><span class="sxs-lookup"><span data-stu-id="5f1ac-114">Go to **Credit and collections > Collection letter > Create collection letters**.</span></span>
2. <span data-ttu-id="5f1ac-115">Välj transaktionstyperna för kravbrev.</span><span class="sxs-lookup"><span data-stu-id="5f1ac-115">Select the transaction types for which you will collect letters.</span></span> <span data-ttu-id="5f1ac-116">Alla öppna transaktioner för dessa typer inkluderas i beräkningen.</span><span class="sxs-lookup"><span data-stu-id="5f1ac-116">All of the open transactions for these types will be included in the calculation.</span></span>  
2. <span data-ttu-id="5f1ac-117">I fältet **Kravbrev** väljer du ett alternativ.</span><span class="sxs-lookup"><span data-stu-id="5f1ac-117">In the **Collection letter** field, select an option.</span></span>
3. <span data-ttu-id="5f1ac-118">Ange datumet för det aktuella kravbrevet.</span><span class="sxs-lookup"><span data-stu-id="5f1ac-118">Enter the date of the collection letter.</span></span>
4. <span data-ttu-id="5f1ac-119">Välj en bokföringsprofil om du har ändrat **Använd bokföringsprofil från** till **Välj**.</span><span class="sxs-lookup"><span data-stu-id="5f1ac-119">Select a posting profile if you changed **Use posting profile from** to **Select**.</span></span> <span data-ttu-id="5f1ac-120">Det finns två typer av profilalternativ:</span><span class="sxs-lookup"><span data-stu-id="5f1ac-120">There are two posting profile options:</span></span>   
   - <span data-ttu-id="5f1ac-121">**Konto** – Använd bokföringsprofilen som är tilldelad till kundkontot för respektive räntefaktura.</span><span class="sxs-lookup"><span data-stu-id="5f1ac-121">**Account** – Use the posting profile that is assigned to the customer account for each interest note.</span></span>   
   - <span data-ttu-id="5f1ac-122">**Välj** – Använd den bokföringsprofil som du väljer i fältet **Bokföringsprofil**.</span><span class="sxs-lookup"><span data-stu-id="5f1ac-122">**Select** – Use the posting profile that you select in the **Posting profile** field.</span></span>  
5. <span data-ttu-id="5f1ac-123">Expandera avsnittet **Poster som ska ingå**.</span><span class="sxs-lookup"><span data-stu-id="5f1ac-123">Expand the **Records to include** section.</span></span>
6. <span data-ttu-id="5f1ac-124">Klicka på **Filter**.</span><span class="sxs-lookup"><span data-stu-id="5f1ac-124">Click **Filter**.</span></span>
7. <span data-ttu-id="5f1ac-125">I fältet **Kriterier**, ange ett kund-ID.</span><span class="sxs-lookup"><span data-stu-id="5f1ac-125">In the **Criteria** field, enter a Customer ID.</span></span> <span data-ttu-id="5f1ac-126">Till exempel "US-001".</span><span class="sxs-lookup"><span data-stu-id="5f1ac-126">For example, enter 'US-001'.</span></span>
8. <span data-ttu-id="5f1ac-127">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="5f1ac-127">Click **OK**.</span></span>
9. <span data-ttu-id="5f1ac-128">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="5f1ac-128">Click **OK**.</span></span>

## <a name="print-collection-letters"></a><span data-ttu-id="5f1ac-129">Skriv ut kravbrev</span><span class="sxs-lookup"><span data-stu-id="5f1ac-129">Print collection letters</span></span>
1. <span data-ttu-id="5f1ac-130">Gå till **Kredit och inkasso > Kravbrev > Granska och bearbeta kravbrev**.</span><span class="sxs-lookup"><span data-stu-id="5f1ac-130">Go to **Credit and collections > Collection letter > Review and process collection letters**.</span></span>
2. <span data-ttu-id="5f1ac-131">I fältet **Status**, välj **Skapad**.</span><span class="sxs-lookup"><span data-stu-id="5f1ac-131">In the **Status** field, select **Created**.</span></span>
3. <span data-ttu-id="5f1ac-132">I fältet **Utskrivet**, välj **Ej utskrivet**.</span><span class="sxs-lookup"><span data-stu-id="5f1ac-132">In the **Printed** field, select **Not printed**.</span></span>
4. <span data-ttu-id="5f1ac-133">Klicka på **Skriv ut**.</span><span class="sxs-lookup"><span data-stu-id="5f1ac-133">Click **Print**.</span></span>
5. <span data-ttu-id="5f1ac-134">Klicka på **kravbrevsnotering**.</span><span class="sxs-lookup"><span data-stu-id="5f1ac-134">Click **Collection letter note**.</span></span>
6. <span data-ttu-id="5f1ac-135">Expandera avsnittet **Poster som ska ingå**.</span><span class="sxs-lookup"><span data-stu-id="5f1ac-135">Expand the **Records to include** section.</span></span>
7. <span data-ttu-id="5f1ac-136">Ange slutdatumet för bokföringar.</span><span class="sxs-lookup"><span data-stu-id="5f1ac-136">Enter the cutoff date for postings.</span></span>
8. <span data-ttu-id="5f1ac-137">Klicka på **OK** för att skriva ut kravbrevet.</span><span class="sxs-lookup"><span data-stu-id="5f1ac-137">Click **OK** to print the collection letter.</span></span>
9. <span data-ttu-id="5f1ac-138">Bokför kravbrevet.</span><span class="sxs-lookup"><span data-stu-id="5f1ac-138">Post the collection letter.</span></span>
   1. <span data-ttu-id="5f1ac-139">Klicka på **Bokför**.</span><span class="sxs-lookup"><span data-stu-id="5f1ac-139">Click **Post**.</span></span>
   2. <span data-ttu-id="5f1ac-140">Ange bokföringsdatumet för kravbrevet.</span><span class="sxs-lookup"><span data-stu-id="5f1ac-140">Enter the posting date for the collection letter.</span></span>
   3. <span data-ttu-id="5f1ac-141">Expandera avsnittet **Poster som ska ingå**.</span><span class="sxs-lookup"><span data-stu-id="5f1ac-141">Expand the **Records to include** section.</span></span>
   4. <span data-ttu-id="5f1ac-142">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="5f1ac-142">Click **OK**.</span></span>
   5. <span data-ttu-id="5f1ac-143">I fältet **Status**, välj **Bokförd**.</span><span class="sxs-lookup"><span data-stu-id="5f1ac-143">In the **Status** field, select **Posted**.</span></span>
   6. <span data-ttu-id="5f1ac-144">Välj ett alternativ i fältet **Utskriven**.</span><span class="sxs-lookup"><span data-stu-id="5f1ac-144">In the **Printed** field, select an option.</span></span>

## <a name="control-collection-letters-at-the-customer-level"></a><span data-ttu-id="5f1ac-145">Kontrollera kravbrev på kundnivån</span><span class="sxs-lookup"><span data-stu-id="5f1ac-145">Control collection letters at the customer level</span></span>
<span data-ttu-id="5f1ac-146">Du kan också ställa in kravbrev på kundnivån så att kravbrevskoden spåras för varje transaktion, men bearbetningen av kravbrev ska baseras på en enda kravbrevsnivå som sparats för kunden.</span><span class="sxs-lookup"><span data-stu-id="5f1ac-146">You can also set up collection letters at the customer level so that the collection letter code for each transaction is tracked, but the collection letter processing will be based on a single collection letter level that is stored for the customer.</span></span> <span data-ttu-id="5f1ac-147">Det enda kravbrevet innehåller alla transaktioner som har förfallit för kunden.</span><span class="sxs-lookup"><span data-stu-id="5f1ac-147">The single collection letter will contain all transactions that are overdue for the customer.</span></span> <span data-ttu-id="5f1ac-148">Eftersom respitdagar nu spåras på kundnivå kommer nästa kravbrev inte att skickas förrän antalet respitdagar har passerat för nästa kravbrev i sekvensen, även om transaktioner blir försenade efter det att sista kravbrevet skickats.</span><span class="sxs-lookup"><span data-stu-id="5f1ac-148">Because the grace days are now tracked on the customer level, the next collection letter will not be sent until the number of grace days has passed for the next collection letter in the sequence, even though transactions become overdue after the last collection letter was sent.</span></span> <span data-ttu-id="5f1ac-149">Det här alternativet minskar antalet kravbrev som du skickar per kund.</span><span class="sxs-lookup"><span data-stu-id="5f1ac-149">This option reduces the number of collection letters you will send per customer.</span></span> 

### <a name="set-up-the-customer-to-control-collection-letters-at-the-customer-level"></a><span data-ttu-id="5f1ac-150">Ställ in kund för att kontrollera kravbrev på kundnivå</span><span class="sxs-lookup"><span data-stu-id="5f1ac-150">Set up the customer to control collection letters at the customer level</span></span>
1.  <span data-ttu-id="5f1ac-151">Gå till **Kredit och inkasso > Inställningar > Parametrar för kundreskontra** och klicka på fliken **samlingar**.</span><span class="sxs-lookup"><span data-stu-id="5f1ac-151">Go to **Credit and collections > Setup > Accounts receivable parameters** and click the **Collections** tab.</span></span> 
2.  <span data-ttu-id="5f1ac-152">Ändra värdet för **skapa kravbrev per** till **kund**.</span><span class="sxs-lookup"><span data-stu-id="5f1ac-152">Change the value of **Create collection letter per** to **Customer**.</span></span> 
3.  <span data-ttu-id="5f1ac-153">Gå till **Kredit och inkasso > Kravbrev > Granska och bearbeta kravbrev**.</span><span class="sxs-lookup"><span data-stu-id="5f1ac-153">Go to **Credit and collections > Collection letter > Review and process collection letters**.</span></span> <span data-ttu-id="5f1ac-154">Bara ett kravbrev kommer att skapas för en kund med alla förfallna transaktioner.</span><span class="sxs-lookup"><span data-stu-id="5f1ac-154">Only one collection letter will be generated for a customer with all the overdue transactions.</span></span>

## <a name="ignore-payments-and-credit-memos-when-calculating-the-collection-letter-code"></a><span data-ttu-id="5f1ac-155">Ignorera betalningar och kreditnotor när du beräknar kravbrevskod</span><span class="sxs-lookup"><span data-stu-id="5f1ac-155">Ignore payments and credit memos when calculating the collection letter code</span></span>
<span data-ttu-id="5f1ac-156">Om du inkluderar betalningar och kreditnotor i de transaktioner som ska inkluderas i kravbrev kanske du betalningar eller kreditnotor som kommer att utlösa ett kravbrev.</span><span class="sxs-lookup"><span data-stu-id="5f1ac-156">If you include payments and credit memos in the transactions that will be included in the collection letters, you may have payments or credit memos that will trigger a collection letter.</span></span> <span data-ttu-id="5f1ac-157">Du kan kontrollera hur betalningar och kreditnotor kontrollerar kravbrevskoden genom att ändra värdet för parametern **Ignorera betalningar och kreditnotor när du beräknar kravbrevskod**.</span><span class="sxs-lookup"><span data-stu-id="5f1ac-157">You can control how payments and credit memos control the collection letter code by changing the value of the **Ignore payments and credit memos when calculating the collection letter code** parameter.</span></span> 

<span data-ttu-id="5f1ac-158">Om du vill ignorera betalningar och kreditnotor när du beräknar kravbrevskod, gör följande.</span><span class="sxs-lookup"><span data-stu-id="5f1ac-158">To ignore payments and credit memos when calculating the collection letter code, do the following.</span></span>
1. <span data-ttu-id="5f1ac-159">Gå till **Kredit och inkasso > Inställningar > Parametrar för kundreskontra** och klicka på fliken **samlingar**.</span><span class="sxs-lookup"><span data-stu-id="5f1ac-159">Go to **Credit and collections > Setup > Accounts receivable parameters** and click the **Collections** tab.</span></span> 
2. <span data-ttu-id="5f1ac-160">Ändra värdet för **Ignorera betalningar och kreditnotor när du beräknar kravbrevskod** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="5f1ac-160">Change the value of **Ignore payments and credit memos when calculating the collection letter code** to **Yes**.</span></span>
