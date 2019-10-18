---
title: Stänga räkenskapsåret
description: Denna procedur vägleder dig genom stegen i årsbokslutsprocessen som överför saldon till ett nytt räkenskapsår.
author: aprilolson
manager: AnnBe
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerParameters, LedgerFiscalCloseGroup, LedgerFiscalCloseAddLedger, SysLookupMultiSelectGrid, LedgerFiscalCloseRunGroup
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c12f0842f6e8edf3b51d12d0e008eb09acf8c374
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2179911"
---
# <a name="close-the-fiscal-year"></a><span data-ttu-id="ac873-103">Stänga räkenskapsåret</span><span class="sxs-lookup"><span data-stu-id="ac873-103">Close the fiscal year</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="ac873-104">Denna procedur vägleder dig genom stegen i årsbokslutsprocessen som överför saldon till ett nytt räkenskapsår.</span><span class="sxs-lookup"><span data-stu-id="ac873-104">This procedure steps through the year end close process that transfers balances to a new fiscal year.</span></span>


## <a name="validate-year-end-close-parameters"></a><span data-ttu-id="ac873-105">Validera årsbokslutsparametrar</span><span class="sxs-lookup"><span data-stu-id="ac873-105">Validate year-end close parameters</span></span>
1. <span data-ttu-id="ac873-106">Gå till **Navigeringsfönster > Moduler > Redovisning > Redovisningsinställning > Allmänna redovisningsparametrar**.</span><span class="sxs-lookup"><span data-stu-id="ac873-106">Go to **Navigation pane > Modules > General ledger > Ledger setup > General ledger parameters**.</span></span>
2. <span data-ttu-id="ac873-107">Expandera avsnittet **Stängning av räkenskapsår**.</span><span class="sxs-lookup"><span data-stu-id="ac873-107">Expand the **Fiscal year close** section.</span></span>
3. <span data-ttu-id="ac873-108">Välj Ja eller Nej för alternativet **Radera UB-transaktioner vid överföring**.</span><span class="sxs-lookup"><span data-stu-id="ac873-108">Select 'Yes' or 'No' for the **Delete close-of-year transactions during transfer** option.</span></span>
    
    <span data-ttu-id="ac873-109">Om räkenskapsåret redan har stängts och årsbokslutet körs igen, är den här inställningen viktig.</span><span class="sxs-lookup"><span data-stu-id="ac873-109">If the fiscal year has already been closed and the year-end close is being run again, this setting is important.</span></span> <span data-ttu-id="ac873-110">Om verifikationen är inställd på "Yes", kommer verifikationen för föregående årsbokslut att raderas och en ny verifikation skapas för alla konton som startar saldon.</span><span class="sxs-lookup"><span data-stu-id="ac873-110">If set to Yes, the voucher for the previous year-end close will be deleted, and a new voucher will be created for all accounts beginning balances.</span></span> <span data-ttu-id="ac873-111">Om inställningen är "No" kommer föregående verifikation att bli kvar, och en ny kupong kommer endast att skapas för justeringar av poster som bokfördes efter det sista årsbokslutet.</span><span class="sxs-lookup"><span data-stu-id="ac873-111">If set to No, the previous voucher will remain and a new voucher will only be created for adjusting entries that were posted after the last year-end close.</span></span>

4. <span data-ttu-id="ac873-112">Välj Ja eller Nej för **Skapa UB-transaktioner vid överföring**.</span><span class="sxs-lookup"><span data-stu-id="ac873-112">Select 'Yes' or 'No' for the **Create closing transactions during transfer** option.</span></span>

    <span data-ttu-id="ac873-113">Om inställningen är "Yes", skapas två transaktioner.</span><span class="sxs-lookup"><span data-stu-id="ac873-113">If set to Yes, two transactions are created.</span></span> <span data-ttu-id="ac873-114">En verifikation skapas i det räkenskapsår som stäng i syfte att sänka saldona för PL-huvudbokskontona till noll, och en andra verifikation skapas i nästkommande räkenskapsår för de nya saldona.</span><span class="sxs-lookup"><span data-stu-id="ac873-114">One voucher is created in the fiscal year being closed to bring the balances of the P&L ledger accounts down to zero and a second voucher is created in the next fiscal year for the beginning balances.</span></span> <span data-ttu-id="ac873-115">Om inställt på "No" kommer en enda verifikation att skapas i nästa räkenskapsår för de nya saldona.</span><span class="sxs-lookup"><span data-stu-id="ac873-115">If set to No, a single voucher is created in the next fiscal year for the beginning balances.</span></span>  

5. <span data-ttu-id="ac873-116">Välj Ja eller Nej för statusen **Ställ in räkenskapsårets status på permanent stängd**.</span><span class="sxs-lookup"><span data-stu-id="ac873-116">Select 'Yes' or 'No' for the **Set fiscal year status to permanently closed** option.</span></span>

    <span data-ttu-id="ac873-117">Om inställt på "Yes", kommer räkenskapsårsstatusen att ställas in som "Permanently closed".</span><span class="sxs-lookup"><span data-stu-id="ac873-117">If set to Yes, the fiscal year status will be set to Permanently closed.</span></span>  <span data-ttu-id="ac873-118">Eftersom ett permanent stängt år inte kan öppnas på nytt, är det bäst att ange detta alternativ som "No".</span><span class="sxs-lookup"><span data-stu-id="ac873-118">Because a permanently closed year cannot be reopened, it would be a best practice to set this option to No.</span></span>  

6. <span data-ttu-id="ac873-119">Välj Ja eller Nej för alternativet **verifikationsnummer måste fyllas i under årsbokslutet**.</span><span class="sxs-lookup"><span data-stu-id="ac873-119">Select 'Yes' or 'No' for the **Voucher number must be filled in during the year end close** option.</span></span>

    <span data-ttu-id="ac873-120">Om inställt på "Yes" måste ett verifikationsnummer anges manuellt under processen för årsbokslutet.</span><span class="sxs-lookup"><span data-stu-id="ac873-120">If set to Yes, a voucher number must be manually entered during the year end close process.</span></span> <span data-ttu-id="ac873-121">En nummerserie används inte för att generera detta verifikationsnummer.</span><span class="sxs-lookup"><span data-stu-id="ac873-121">A number sequence is not used to generate this voucher number.</span></span> <span data-ttu-id="ac873-122">Det bästa är att ange detta som "Yes".</span><span class="sxs-lookup"><span data-stu-id="ac873-122">It's a best practice to set this to Yes.</span></span>  

7. <span data-ttu-id="ac873-123">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="ac873-123">Close the page.</span></span>
8. <span data-ttu-id="ac873-124">Gå till **Redovisning > Periodstängning > Årsbokslut**.</span><span class="sxs-lookup"><span data-stu-id="ac873-124">Go to **General ledger > Period close > Year end close**.</span></span>
9. <span data-ttu-id="ac873-125">Klicka på **Ny** för att skapa en årsbokslutsmall.</span><span class="sxs-lookup"><span data-stu-id="ac873-125">Click **New** to create a year-end close template.</span></span>

    <span data-ttu-id="ac873-126">En mall kan skapas för en grupp juridiska personer för vilka du vill köra årsbokslutet.</span><span class="sxs-lookup"><span data-stu-id="ac873-126">A template can be created for a group of legal entities for which to run the year-end close.</span></span> <span data-ttu-id="ac873-127">Denna mall kan återanvändas året efter år.</span><span class="sxs-lookup"><span data-stu-id="ac873-127">This template can be reused year after year.</span></span>  

10. <span data-ttu-id="ac873-128">Ange ett mallnamn för årsbokslut i fältet **Gruppnamn**.</span><span class="sxs-lookup"><span data-stu-id="ac873-128">In the **Group name** field, enter a year-end close template name..</span></span>
11. <span data-ttu-id="ac873-129">I fältet **räkenskapskalender** väljer du det räkenskapsår som mallen ska skapas för.</span><span class="sxs-lookup"><span data-stu-id="ac873-129">In the **Fiscal calendar** field, select the fiscal year for which the template will be created.</span></span>

    <span data-ttu-id="ac873-130">Endast juridiska personer som använder samma räkenskapsår kan grupperas tillsammans mallen för årsbokslut.</span><span class="sxs-lookup"><span data-stu-id="ac873-130">Only legal entities which use the same fiscal year can be grouped together in the year-end close template.</span></span> <span data-ttu-id="ac873-131">Detta eftersom årsbokslutet görs genom att välja ett räkenskapsår, inte ett datum.</span><span class="sxs-lookup"><span data-stu-id="ac873-131">This is because the year end close is done by selecting a fiscal year, not a date.</span></span>  

12. <span data-ttu-id="ac873-132">I **åtgärdsfönstret**, klicka på **spara**.</span><span class="sxs-lookup"><span data-stu-id="ac873-132">On the **Action pane**, click **Save**.</span></span>
13. <span data-ttu-id="ac873-133">I avsnittet **juridiska personer** klickar du på **Lägg till** för att välja juridiska personer för den här mallen.</span><span class="sxs-lookup"><span data-stu-id="ac873-133">In the **Legal entities** section, click **Add** to select the legal entities for this template.</span></span>
    
    <span data-ttu-id="ac873-134">Juridiska personer kan läggas till, antingen genom att välja de juridiska personerna eller genom att välja en organisationshierarki.</span><span class="sxs-lookup"><span data-stu-id="ac873-134">Legal entities can be added by either selecting the legal entities or by selecting an organizational hierarchy.</span></span>  <span data-ttu-id="ac873-135">Endast juridiska personer med en organisationshierarki med samma markerade räkenskapskalender läggs till.</span><span class="sxs-lookup"><span data-stu-id="ac873-135">Only legal entities with the organizational hierarchy with the same fiscal calendar selected will be added.</span></span>  

14. <span data-ttu-id="ac873-136">Välj antingen de juridiska personerna eller organisationshierarkin.</span><span class="sxs-lookup"><span data-stu-id="ac873-136">Select either the legal entities or the organizational hierarchy.</span></span>
15. <span data-ttu-id="ac873-137">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="ac873-137">Click **OK**.</span></span>
16. <span data-ttu-id="ac873-138">Välj "Ja" eller "Nej" i **Överför balansräkningsdimensioner**.</span><span class="sxs-lookup"><span data-stu-id="ac873-138">Select 'Yes' or 'No' in the **Transfer balance sheet dimension**.</span></span>

    <span data-ttu-id="ac873-139">Det bästa är att ange detta alternativ som "Yes" för balansräkningskonton.</span><span class="sxs-lookup"><span data-stu-id="ac873-139">It's best practice to set this option to Yes for Balance sheet accounts.</span></span> <span data-ttu-id="ac873-140">Detta kommer att bibehålla de ekonomiska dimensionerna i bokförda transaktioner när nya saldon ska skapas för balansräkningskontona.</span><span class="sxs-lookup"><span data-stu-id="ac873-140">This will maintain the financial dimensions on posted transactions when creating the beginning balances for the balance sheet accounts.</span></span> <span data-ttu-id="ac873-141">För vinst - och förlustkonton kan du välja att underhålla stäng ekonomiska dimensioner (Close all) när saldona flyttas till balanserade vinstmedel, eller också kan du välja att byta ut de ekonomiska dimensionerna med ett annat dimensionsvärde (Close single).</span><span class="sxs-lookup"><span data-stu-id="ac873-141">For profit and loss accounts, you can select to maintain the financial dimensions (Close all) when the balances are moved to Retained earnings or you can select to have the financial dimensions replaced with a different dimension value (Close single).</span></span> <span data-ttu-id="ac873-142">Om du väljer Close single kan du definiera ett specifikt dimensionsvärde för varje dimension, eller till och med välja att lämna den tom.</span><span class="sxs-lookup"><span data-stu-id="ac873-142">If you choose Close single, you can define a specific dimension value for each dimension or even choose to leave it blank.</span></span>  

17. <span data-ttu-id="ac873-143">Klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="ac873-143">Click **Save**.</span></span>
18. <span data-ttu-id="ac873-144">Starta årsbokslutet genom att välja **Kör årsbokslut** i **åtgärdsfönstret**.</span><span class="sxs-lookup"><span data-stu-id="ac873-144">Start the year-end close by choosing **Run fiscal close** on the **Action Pane**.</span></span> <span data-ttu-id="ac873-145">Årsbokslutet körs för den valda mallen.</span><span class="sxs-lookup"><span data-stu-id="ac873-145">The year-end close will be run for the selected template.</span></span>  
19. <span data-ttu-id="ac873-146">Välj alla eller en underuppsättning juridiska personer från den mall för vilken du vill köra årsbokslutet.</span><span class="sxs-lookup"><span data-stu-id="ac873-146">Select all or a subset of legal entities from the template for which to run the year-end close.</span></span>

    <span data-ttu-id="ac873-147">När årsbokslutet först körs, kan de flesta organisationer välja att köra årsbokslutet för samtliga juridiska personer i mallen i syfte att skapa ingående saldon.</span><span class="sxs-lookup"><span data-stu-id="ac873-147">When first running the year-end close, to get beginning balance,s most organizations may choose to run the year-end close for all legal entities within the template.</span></span> <span data-ttu-id="ac873-148">Om postjusteringar utförs efter det, kan du välja att köra årsbokslutet för enbart de juridiska personerna som har justeringar.</span><span class="sxs-lookup"><span data-stu-id="ac873-148">If adjusting entries are made after that, you may choose to run the year-end close for only the legal entities that have adjustments.</span></span>  

20. <span data-ttu-id="ac873-149">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="ac873-149">Click **OK**.</span></span>
21. <span data-ttu-id="ac873-150">Markera det räkenskapsår du vill köra årsbokslutet för.</span><span class="sxs-lookup"><span data-stu-id="ac873-150">Select the fiscal year for which to run the year-end close.</span></span>
22. <span data-ttu-id="ac873-151">Ange ett värde i fältet **Voucher**.</span><span class="sxs-lookup"><span data-stu-id="ac873-151">In the **Voucher field**, type a value.</span></span> <span data-ttu-id="ac873-152">Det bästa är att inkludera räkenskapsåret i verifikationsnummer, detta för att göra det enklare att hitta verifikationen för årsbokslutet som skapas.</span><span class="sxs-lookup"><span data-stu-id="ac873-152">It's best practice to include the fiscal year in the voucher number, to make it easier to find the year-end close voucher that is created.</span></span>  
23. <span data-ttu-id="ac873-153">Årsbokslutets standardvärden som ska köras i batch.</span><span class="sxs-lookup"><span data-stu-id="ac873-153">The year-end close defaults to run in batch.</span></span> <span data-ttu-id="ac873-154">Det bästa är att låta långvariga processer köras i batch-läge.</span><span class="sxs-lookup"><span data-stu-id="ac873-154">It's best practice for long-running processes to run in batch mode.</span></span> <span data-ttu-id="ac873-155">Detta är vanligtvis en av dessa processer, vilket är orsaken till att standardinställningen är att använda batch-läge.</span><span class="sxs-lookup"><span data-stu-id="ac873-155">This is typically one of those processes, which is why the default is to use batch mode.</span></span>  
24. <span data-ttu-id="ac873-156">Klicka på **OK**.</span><span class="sxs-lookup"><span data-stu-id="ac873-156">Click **OK**.</span></span>

