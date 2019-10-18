---
title: Bearbeta kravbrev
description: I det här avsnittet visas hur du skapar, skriver ut och bokför kravbrev.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/01/2019
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
ms.openlocfilehash: 326d9375670cb4f4990a4f7070bf923a28b2c025
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2180006"
---
# <a name="process-collection-letters"></a><span data-ttu-id="244e1-103">Bearbeta kravbrev</span><span class="sxs-lookup"><span data-stu-id="244e1-103">Process collection letters</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="244e1-104">I det här avsnittet visas hur du skapar, skriver ut och bokför kravbrev.</span><span class="sxs-lookup"><span data-stu-id="244e1-104">This topic shows how to create, print, and post collection letters.</span></span> <span data-ttu-id="244e1-105">I den här uppgiften används demonstrationsföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="244e1-105">This task uses the USMF demo company.</span></span>

## <a name="set-up-a-collection-letter-sequence-on-the-posting-profile"></a><span data-ttu-id="244e1-106">Ställ in en kravbrevsserie för bokföringsprofilen</span><span class="sxs-lookup"><span data-stu-id="244e1-106">Set up a collection letter sequence on the posting profile</span></span>
1. <span data-ttu-id="244e1-107">Gå till **Navigeringsfönster > Moduler > Kredit och inkasso > Inställningar > Kundbokföringsprofiler**.</span><span class="sxs-lookup"><span data-stu-id="244e1-107">Go to **Navigation pane > Modules > Credit and collections > Setup > Customer posting profiles**.</span></span>
2. <span data-ttu-id="244e1-108">Klicka på **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="244e1-108">Click **Edit**.</span></span>
3. <span data-ttu-id="244e1-109">Välj en kravbrevssekvens i listrutan.</span><span class="sxs-lookup"><span data-stu-id="244e1-109">Select a collection letter sequence from the drop-down list.</span></span> <span data-ttu-id="244e1-110">Om du inte vill skapa kravbrev för transaktioner med denna bokföringsprofil, lämna fältet tomt.</span><span class="sxs-lookup"><span data-stu-id="244e1-110">If you do not want to generate collection letters for transactions using this posting profile, leave the field blank.</span></span>  
4. <span data-ttu-id="244e1-111">Expandera fliken **Registerbegränsningar** för att ändra hur kravbrev bearbetas.</span><span class="sxs-lookup"><span data-stu-id="244e1-111">Expand the **Table restrictions** tab to change the way that collection letters are processed.</span></span> <span data-ttu-id="244e1-112">Om detta fält har satts till **Ja** skapas kravbrev för denna bokföringsprofil.</span><span class="sxs-lookup"><span data-stu-id="244e1-112">If this field is set to **Yes**, then collection letters will be created for this posting profile.</span></span>  

## <a name="create-collection-letters"></a><span data-ttu-id="244e1-113">Skapa kravbrev</span><span class="sxs-lookup"><span data-stu-id="244e1-113">Create collection letters</span></span>
1. <span data-ttu-id="244e1-114">Gå till **Navigeringsfönster > Moduler > Kredit och inkasso > Kravbrev > Skapa kravbrev**.</span><span class="sxs-lookup"><span data-stu-id="244e1-114">Go to **Navigation pane > Modules > Credit and collections > Collection letter > Create collection letters**.</span></span>
2. <span data-ttu-id="244e1-115">Välj transaktionstyperna för kravbrev.</span><span class="sxs-lookup"><span data-stu-id="244e1-115">Select the transaction types for which you will collect letters.</span></span> <span data-ttu-id="244e1-116">Alla öppna transaktioner för dessa typer inkluderas i beräkningen.</span><span class="sxs-lookup"><span data-stu-id="244e1-116">All of the open transactions for these types will be included in the calculation.</span></span>  
3. <span data-ttu-id="244e1-117">I fältet **Kravbrev** väljer du ett alternativ.</span><span class="sxs-lookup"><span data-stu-id="244e1-117">In the **Collection letter** field, select an option.</span></span>
4. <span data-ttu-id="244e1-118">Ange datum för kravbrevet i fältet **Datum för kravbrev**.</span><span class="sxs-lookup"><span data-stu-id="244e1-118">In the **Collection letter date** field, enter the date of the collection letter.</span></span>
5. <span data-ttu-id="244e1-119">Välj en bokföringsprofil om du har ändrat **Använd bokföringsprofil från** till **Välj**.</span><span class="sxs-lookup"><span data-stu-id="244e1-119">Select a posting profile if you changed **Use posting profile from** to **Select**.</span></span> <span data-ttu-id="244e1-120">Det finns två typer av profilalternativ:</span><span class="sxs-lookup"><span data-stu-id="244e1-120">There are two posting profile options:</span></span>   

   - <span data-ttu-id="244e1-121">**Konto** – Använd bokföringsprofilen som är tilldelad till kundkontot för respektive räntefaktura.</span><span class="sxs-lookup"><span data-stu-id="244e1-121">**Account** – Use the posting profile that is assigned to the customer account for each interest note.</span></span>   
   - <span data-ttu-id="244e1-122">**Välj** – Använd den bokföringsprofil som du väljer i fältet **Bokföringsprofil**.</span><span class="sxs-lookup"><span data-stu-id="244e1-122">**Select** – Use the posting profile that you select in the **Posting profile** field.</span></span>  

6. <span data-ttu-id="244e1-123">Expandera avsnittet **Poster som ska ingå**.</span><span class="sxs-lookup"><span data-stu-id="244e1-123">Expand the **Records to include** section.</span></span>
7. <span data-ttu-id="244e1-124">Välj **filter**.</span><span class="sxs-lookup"><span data-stu-id="244e1-124">Select **Filter**.</span></span>
8. <span data-ttu-id="244e1-125">I fältet **Kriterier**, ange ett kund-ID.</span><span class="sxs-lookup"><span data-stu-id="244e1-125">In the **Criteria** field, enter a Customer ID.</span></span> <span data-ttu-id="244e1-126">Till exempel "US-001".</span><span class="sxs-lookup"><span data-stu-id="244e1-126">For example, enter 'US-001'.</span></span>
9. <span data-ttu-id="244e1-127">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="244e1-127">Select **OK**.</span></span>
10. <span data-ttu-id="244e1-128">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="244e1-128">Select **OK**.</span></span>

## <a name="print-collection-letters"></a><span data-ttu-id="244e1-129">Skriv ut kravbrev</span><span class="sxs-lookup"><span data-stu-id="244e1-129">Print collection letters</span></span>
1. <span data-ttu-id="244e1-130">Gå till **Navigeringsfönster > Moduler > Kredit och inkasso > Kravbrev > Granska och bearbeta kravbrev**.</span><span class="sxs-lookup"><span data-stu-id="244e1-130">Go to **navigation pane > Modules > Credit and collections > Collection letter > Review and process collection letters**.</span></span>
2. <span data-ttu-id="244e1-131">I fältet **Status**, välj **Skapad**.</span><span class="sxs-lookup"><span data-stu-id="244e1-131">In the **Status** field, select **Created**.</span></span>
3. <span data-ttu-id="244e1-132">I fältet **Utskrivet**, välj **Ej utskrivet**.</span><span class="sxs-lookup"><span data-stu-id="244e1-132">In the **Printed** field, select **Not printed**.</span></span>
4. <span data-ttu-id="244e1-133">Välj **Skriv ut**.</span><span class="sxs-lookup"><span data-stu-id="244e1-133">Select **Print**.</span></span>
5. <span data-ttu-id="244e1-134">Välj **Kravbrevsnotering**.</span><span class="sxs-lookup"><span data-stu-id="244e1-134">Select **Collection letter note**.</span></span>
6. <span data-ttu-id="244e1-135">Ange sista datum för bokföring i avsnittet **Parametrar**.</span><span class="sxs-lookup"><span data-stu-id="244e1-135">In the **Parameters** section, enter the cutoff date for postings.</span></span>
7. <span data-ttu-id="244e1-136">Expandera avsnittet **Poster som ska ingå** och ange information om kravbrevsnoteringen.</span><span class="sxs-lookup"><span data-stu-id="244e1-136">Expand the **Records to include** section and enter the details of the Collection letter note.</span></span>
8. <span data-ttu-id="244e1-137">Välj **OK** för att skriva ut kravbrevet.</span><span class="sxs-lookup"><span data-stu-id="244e1-137">Select **OK** to print the collection letter.</span></span>
9. <span data-ttu-id="244e1-138">Bokför kravbrevet.</span><span class="sxs-lookup"><span data-stu-id="244e1-138">Post the collection letter.</span></span>

    1. <span data-ttu-id="244e1-139">Vald **bokföring**</span><span class="sxs-lookup"><span data-stu-id="244e1-139">Select **Post**.</span></span>
    1. <span data-ttu-id="244e1-140">Ange bokföringsdatumet för kravbrevet.</span><span class="sxs-lookup"><span data-stu-id="244e1-140">Enter the posting date for the collection letter.</span></span>
    1. <span data-ttu-id="244e1-141">Expandera avsnittet **Poster som ska ingå**.</span><span class="sxs-lookup"><span data-stu-id="244e1-141">Expand the **Records to include** section.</span></span>
    1. <span data-ttu-id="244e1-142">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="244e1-142">Select **OK**.</span></span>
    1. <span data-ttu-id="244e1-143">I fältet **Status**, välj **Bokförd**.</span><span class="sxs-lookup"><span data-stu-id="244e1-143">In the **Status** field, select **Posted**.</span></span>
    1. <span data-ttu-id="244e1-144">Välj ett alternativ i fältet **Utskriven**.</span><span class="sxs-lookup"><span data-stu-id="244e1-144">In the **Printed** field, select an option.</span></span>

## <a name="control-collection-letters-at-the-customer-level"></a><span data-ttu-id="244e1-145">Kontrollera kravbrev på kundnivån</span><span class="sxs-lookup"><span data-stu-id="244e1-145">Control collection letters at the customer level</span></span>
<span data-ttu-id="244e1-146">Du kan också ställa in kravbrev på kundnivån så att kravbrevskoden spåras för varje transaktion, men bearbetningen av kravbrev ska baseras på en enda kravbrevsnivå som sparats för kunden.</span><span class="sxs-lookup"><span data-stu-id="244e1-146">You can also set up collection letters at the customer level so that the collection letter code for each transaction is tracked, but the collection letter processing will be based on a single collection letter level that is stored for the customer.</span></span> <span data-ttu-id="244e1-147">Det enda kravbrevet innehåller alla transaktioner som har förfallit för kunden.</span><span class="sxs-lookup"><span data-stu-id="244e1-147">The single collection letter will contain all transactions that are overdue for the customer.</span></span> <span data-ttu-id="244e1-148">Eftersom respitdagar nu spåras på kundnivå kommer nästa kravbrev inte att skickas förrän antalet respitdagar har passerat för nästa kravbrev i sekvensen, även om transaktioner blir försenade efter det att sista kravbrevet skickats.</span><span class="sxs-lookup"><span data-stu-id="244e1-148">Because the grace days are now tracked on the customer level, the next collection letter will not be sent until the number of grace days has passed for the next collection letter in the sequence, even though transactions become overdue after the last collection letter was sent.</span></span> <span data-ttu-id="244e1-149">Det här alternativet minskar antalet kravbrev som du skickar per kund.</span><span class="sxs-lookup"><span data-stu-id="244e1-149">This option reduces the number of collection letters you will send per customer.</span></span> 

### <a name="set-up-the-customer-to-control-collection-letters-at-the-customer-level"></a><span data-ttu-id="244e1-150">Ställ in kund för att kontrollera kravbrev på kundnivå</span><span class="sxs-lookup"><span data-stu-id="244e1-150">Set up the customer to control collection letters at the customer level</span></span>
1.  <span data-ttu-id="244e1-151">Gå till **navigeringfönster > Moduler > Kredit och inkasso > Inställningar > Parametrar för kundreskontra** och välj fliken **samlingar**.</span><span class="sxs-lookup"><span data-stu-id="244e1-151">Go to **Navigation pane > Modules > Credit and collections > Setup > Accounts receivable parameters** and select the **Collections** tab.</span></span> 
2.  <span data-ttu-id="244e1-152">Ändra värdet för **skapa kravbrev per** till **kund**.</span><span class="sxs-lookup"><span data-stu-id="244e1-152">Change the value of **Create collection letter per** to **Customer**.</span></span> 
3.  <span data-ttu-id="244e1-153">Gå till **Navigeringsfönster > Moduler > Kredit och inkasso > Kravbrev > Granska och bearbeta kravbrev**.</span><span class="sxs-lookup"><span data-stu-id="244e1-153">Go to **navigation pane > Modules > Credit and collections > Collection letter > Review and process collection letters**.</span></span> <span data-ttu-id="244e1-154">Bara ett kravbrev kommer att skapas för en kund med alla förfallna transaktioner.</span><span class="sxs-lookup"><span data-stu-id="244e1-154">Only one collection letter will be generated for a customer with all the overdue transactions.</span></span>

## <a name="ignore-payments-and-credit-memos-when-calculating-the-collection-letter-code"></a><span data-ttu-id="244e1-155">Ignorera betalningar och kreditnotor när du beräknar kravbrevskod</span><span class="sxs-lookup"><span data-stu-id="244e1-155">Ignore payments and credit memos when calculating the collection letter code</span></span>
<span data-ttu-id="244e1-156">Om du inkluderar betalningar och kreditnotor i de transaktioner som ska inkluderas i kravbrev kanske du betalningar eller kreditnotor som kommer att utlösa ett kravbrev.</span><span class="sxs-lookup"><span data-stu-id="244e1-156">If you include payments and credit memos in the transactions that will be included in the collection letters, you may have payments or credit memos that will trigger a collection letter.</span></span> <span data-ttu-id="244e1-157">Du kan kontrollera hur betalningar och kreditnotor kontrollerar kravbrevskoden genom att ändra värdet för parametern **Ignorera betalningar och kreditnotor när du beräknar kravbrevskod**.</span><span class="sxs-lookup"><span data-stu-id="244e1-157">You can control how payments and credit memos control the collection letter code by changing the value of the **Ignore payments and credit memos when calculating the collection letter code** parameter.</span></span> 

<span data-ttu-id="244e1-158">Om du vill ignorera betalningar och kreditnotor när du beräknar kravbrevskod, gör följande.</span><span class="sxs-lookup"><span data-stu-id="244e1-158">To ignore payments and credit memos when calculating the collection letter code, do the following.</span></span>

1. <span data-ttu-id="244e1-159">Gå till **navigeringfönster > Moduler > Kredit och inkasso > Inställningar > Parametrar för kundreskontra** och klicka på fliken **Samlingar**.</span><span class="sxs-lookup"><span data-stu-id="244e1-159">Go to **Navigation pane > Modules > Credit and collections > Setup > Accounts receivable parameters** and click the **Collections** tab.</span></span> 
2. <span data-ttu-id="244e1-160">Ändra värdet för **Ignorera betalningar och kreditnotor när du beräknar kravbrevskod** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="244e1-160">Change the value of **Ignore payments and credit memos when calculating the collection letter code** to **Yes**.</span></span>
