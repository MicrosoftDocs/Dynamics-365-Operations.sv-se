---
title: Ange initiala lönesaldon
description: Avsnittet beskriver stegen för att ange initiala saldon för lönekoder, förmåner, avdrag och moms. Denna information är viktig för partnerföretag som vill migrera eller överföra data för en ny implementering av lönelistor från ett annat system.
author: andreabichsel
manager: AnnBe
ms.date: 11/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: 20931
ms.assetid: b48b1cb2-6e66-467e-9c0e-09b6a4aeb9fe
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2017-07-01
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 209636d6416a784d298bcfb134f5486c1f5cf202
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/09/2021
ms.locfileid: "5568555"
---
# <a name="enter-payroll-beginning-balances"></a><span data-ttu-id="b853a-104">Ange initiala lönesaldon</span><span class="sxs-lookup"><span data-stu-id="b853a-104">Enter payroll beginning balances</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b853a-105">Avsnittet beskriver stegen för att ange initiala saldon för lönekoder, förmåner, avdrag och moms.</span><span class="sxs-lookup"><span data-stu-id="b853a-105">The topic describes the steps for entering beginning balances for earning codes, deductions, benefits, and taxes.</span></span> <span data-ttu-id="b853a-106">Denna information är viktig för partnerföretag som överför data för en ny implementering av lönelistor från ett annat system.</span><span class="sxs-lookup"><span data-stu-id="b853a-106">This information is valuable for partners who transfer data for a new Payroll implementation from another system.</span></span> <span data-ttu-id="b853a-107">Vi bekräftar följande information när du förbereder inmatningen av initiala lönesaldon:</span><span class="sxs-lookup"><span data-stu-id="b853a-107">To prepare to enter beginning payroll balances, we verify the following information:</span></span>

- <span data-ttu-id="b853a-108">Medarbetarposter anges och finns tillgängliga i systemet</span><span class="sxs-lookup"><span data-stu-id="b853a-108">Employee records are entered and available in the system</span></span>
- <span data-ttu-id="b853a-109">Följande uppgifter har konfigurerats och tilldelats medarbetare:</span><span class="sxs-lookup"><span data-stu-id="b853a-109">The following data is set up and assigned to employees:</span></span>

    - <span data-ttu-id="b853a-110">Lönecykler och löneperioder</span><span class="sxs-lookup"><span data-stu-id="b853a-110">Pay cycles and pay periods</span></span>
    - <span data-ttu-id="b853a-111">Inkomstkoder</span><span class="sxs-lookup"><span data-stu-id="b853a-111">Earning codes</span></span>
    - <span data-ttu-id="b853a-112">Moms</span><span class="sxs-lookup"><span data-stu-id="b853a-112">Taxes</span></span>
    - <span data-ttu-id="b853a-113">Förmåner och avdrag</span><span class="sxs-lookup"><span data-stu-id="b853a-113">Benefits and deductions</span></span>

- <span data-ttu-id="b853a-114">Företaget bör har valt ett datum där initiala lönesaldon kan ställas in.</span><span class="sxs-lookup"><span data-stu-id="b853a-114">The company should have chosen a date where payroll beginning balances can be set.</span></span>
- <span data-ttu-id="b853a-115">Informationen samlades in för alla inkomster och förmåner/avdrag, förmånsbidrag, medarbetar- och arbetsgivarmoms deras hittillsvarande belopp under hittillsvarande år från det äldre systemet.</span><span class="sxs-lookup"><span data-stu-id="b853a-115">Information was gathered on all earnings, benefits/deductions, benefit contributions, employee taxes, and employer taxes and their YTD amounts from the legacy system.</span></span>

<span data-ttu-id="b853a-116">När du planerar att ange initiala balanser, överväg då hur pass detaljerade datan måste vara.</span><span class="sxs-lookup"><span data-stu-id="b853a-116">As you plan to enter beginning balances, consider how detailed the data needs to be.</span></span> <span data-ttu-id="b853a-117">De flesta företag anger ett enda, konsoliderat belopp under hittillsvarande år till dags dato.</span><span class="sxs-lookup"><span data-stu-id="b853a-117">Most businesses enter a single, consolidated year-to-date amount.</span></span> <span data-ttu-id="b853a-118">Om mer detaljerad information skulle krävas kan saldon emellertid anges kvartalsvis.</span><span class="sxs-lookup"><span data-stu-id="b853a-118">However if more detailed information is needed, balances can be entered in quarterly increments.</span></span> <span data-ttu-id="b853a-119">Valet av erforderlig detaljnivå avgör hur många manuella löneutdrag som måste skapas för varje arbetstagare.</span><span class="sxs-lookup"><span data-stu-id="b853a-119">Deciding the level of detail that's needed determines how many manual pay statements must be created for each worker.</span></span> <span data-ttu-id="b853a-120">För ett enstaka belopp till dags dato behövs endast ett manuellt utdrag för respektive medarbetare.</span><span class="sxs-lookup"><span data-stu-id="b853a-120">For a single year-to-date amount, only one manual statement is needed for each employee.</span></span> <span data-ttu-id="b853a-121">För att göra detta använder du hittillsvarande belopp under året till dags dato, från det slutliga löneutdraget från det tidigare systemet som det belopp som bokförs i det nya lönesystemet.</span><span class="sxs-lookup"><span data-stu-id="b853a-121">To do this, use year-to-date amounts from the final pay statement from the previous system as the amount entered in the new payroll system.</span></span>

<span data-ttu-id="b853a-122">I följande exempel visas hur du kan ange medarbetarens initiala lönesaldon, inklusive inkomstkoder, förmåner/avdrag och moms.</span><span class="sxs-lookup"><span data-stu-id="b853a-122">The following example shows how you can enter employee payroll beginning balances, including earning codes, benefits/deductions, and taxes.</span></span> <span data-ttu-id="b853a-123">I ett verkligt exempel skulle det finnas en radartikel för varje inkomstkod, förmånsavdrag, förmånsbidrag, medarbetar- och arbetsgivarskatt där det angivna beloppet är lika med beloppet under hittillsvarande år fram till dags dato.</span><span class="sxs-lookup"><span data-stu-id="b853a-123">In a real-world example you would have a line item for each earning code, benefit deduction, benefit contribution, employee tax and employer tax with the amount entered being the year-to-date amount.</span></span> <span data-ttu-id="b853a-124">Med hjälp av denna förteckning över koder och belopp följer du instruktionerna för att skapa ett manuellt inkomst- och betalningsutdrag med inaktiverad redovisning om du vill flytta över ingående saldon i betalningsändamål.</span><span class="sxs-lookup"><span data-stu-id="b853a-124">Using that list of codes and amounts, follow the steps for creating a manual earning and pay statement with accounting disabled to bring over beginning balances for payroll purposes.</span></span> <span data-ttu-id="b853a-125">Du kan inaktivera redovisningen eftersom du inte vill bokföra detta betalningsutdrag för initial saldo i redovisningen.</span><span class="sxs-lookup"><span data-stu-id="b853a-125">You disable accounting because you won't want to post this beginning balance pay statement to your general ledger.</span></span> <span data-ttu-id="b853a-126">Detta gjordes i det äldre systemet och kommer att överföras till det nya systemet när du anger initiala saldon i redovisningen.</span><span class="sxs-lookup"><span data-stu-id="b853a-126">That was done in the legacy system and will come over to the new system when you set beginning balances in General ledger.</span></span>

### <a name="a-how-to-set-up-earnings-codes-to-be-used-on-payroll-beginning-balances"></a><span data-ttu-id="b853a-127">A.</span><span class="sxs-lookup"><span data-stu-id="b853a-127">A.</span></span> <span data-ttu-id="b853a-128">Hur du ställer in inkomstkoder som ska användas för ingående lönesaldon på lönelistan</span><span class="sxs-lookup"><span data-stu-id="b853a-128">How to set up earnings codes to be used on payroll beginning balances</span></span>

<span data-ttu-id="b853a-129">När du anger initiala lönesaldon för lönelistor, se då till att de inkomstkoder som du ska använda konfigureras med alternativet ”Tillåt redigering av tariffer för inkomstutdrag" är aktiverat.</span><span class="sxs-lookup"><span data-stu-id="b853a-129">When you enter payroll beginning balances, be sure the earning codes that you will be using are configured with the "Allow editing of earning statement rates" option enabled.</span></span> <span data-ttu-id="b853a-130">Detta gör att du manuellt kan ange beloppet från det äldre systemet.</span><span class="sxs-lookup"><span data-stu-id="b853a-130">This will allow you to manually key the amount from the legacy system.</span></span> 

### <a name="b-create-earnings-statement-for-an-employee-to-have-a-beginning-balance"></a><span data-ttu-id="b853a-131">B.</span><span class="sxs-lookup"><span data-stu-id="b853a-131">B.</span></span> <span data-ttu-id="b853a-132">Skapa inkomstutdrag för en medarbetare för att få ett initialt saldo</span><span class="sxs-lookup"><span data-stu-id="b853a-132">Create earnings statement for an employee to have a beginning balance</span></span>

<span data-ttu-id="b853a-133">Det här steget skapar manuellt ett inkomstutdrag för respektive arbetstagare för det äldre systemet sista löneperiod, vilket skapar inkomstutdragsraderna i det nya lönesystemet.</span><span class="sxs-lookup"><span data-stu-id="b853a-133">This step manually creates an earnings statement for each worker for the last pay period of the legacy system, which creates the earning statement lines in the new payroll system.</span></span> <span data-ttu-id="b853a-134">Ange en rad per inkomstkod samt belopp och timmar för hittillsvarande år fram till dags dato.</span><span class="sxs-lookup"><span data-stu-id="b853a-134">Enter one line per earning code and the YTD amount and hours.</span></span> <span data-ttu-id="b853a-135">Exempelstegen är som följer:</span><span class="sxs-lookup"><span data-stu-id="b853a-135">The sample steps are as follows:</span></span>

1. <span data-ttu-id="b853a-136">Öppna sidan **Alla intäktsutdrag** och klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="b853a-136">Open the **All earnings statements** page and click **New**.</span></span>

    <span data-ttu-id="b853a-137">Ange följande:</span><span class="sxs-lookup"><span data-stu-id="b853a-137">Enter the following:</span></span> 

    | <span data-ttu-id="b853a-138">Fält</span><span class="sxs-lookup"><span data-stu-id="b853a-138">Field</span></span>      | <span data-ttu-id="b853a-139">Värde</span><span class="sxs-lookup"><span data-stu-id="b853a-139">Value</span></span>                 |
    |------------|-----------------------|
    | <span data-ttu-id="b853a-140">Arbetare</span><span class="sxs-lookup"><span data-stu-id="b853a-140">Worker</span></span>     | <span data-ttu-id="b853a-141">Michael Redmond</span><span class="sxs-lookup"><span data-stu-id="b853a-141">Michael Redmond</span></span>       |
    | <span data-ttu-id="b853a-142">Lönecykel</span><span class="sxs-lookup"><span data-stu-id="b853a-142">Pay cycle</span></span>  | <span data-ttu-id="b853a-143">sm</span><span class="sxs-lookup"><span data-stu-id="b853a-143">sm</span></span>                    |
    | <span data-ttu-id="b853a-144">Löneperiod</span><span class="sxs-lookup"><span data-stu-id="b853a-144">Pay period</span></span> | <span data-ttu-id="b853a-145">2016-06-16 - 2017-06-30</span><span class="sxs-lookup"><span data-stu-id="b853a-145">6/16/2017 - 6/30/2017</span></span> |

2. <span data-ttu-id="b853a-146">I fliken **Rad för inkomstutdrag** anger du följande:</span><span class="sxs-lookup"><span data-stu-id="b853a-146">In the **Earnings statement line** tab, enter the following:</span></span>

    <span data-ttu-id="b853a-147">Rad 1: Fliken **Rad för inkomsutdrag**</span><span class="sxs-lookup"><span data-stu-id="b853a-147">Line 1: **Earning statement line** tab</span></span>

    | <span data-ttu-id="b853a-148">Fält</span><span class="sxs-lookup"><span data-stu-id="b853a-148">Field</span></span>            | <span data-ttu-id="b853a-149">Värde</span><span class="sxs-lookup"><span data-stu-id="b853a-149">Value</span></span>       |
    |------------------|-------------|
    | <span data-ttu-id="b853a-150">Inkomstkod</span><span class="sxs-lookup"><span data-stu-id="b853a-150">Earnings code</span></span>    | <span data-ttu-id="b853a-151">Standardlön</span><span class="sxs-lookup"><span data-stu-id="b853a-151">Regular pay</span></span> |
    | <span data-ttu-id="b853a-152">Kvantitet</span><span class="sxs-lookup"><span data-stu-id="b853a-152">Quantity</span></span>         | <span data-ttu-id="b853a-153">1.00</span><span class="sxs-lookup"><span data-stu-id="b853a-153">1.00</span></span>        |
    | <span data-ttu-id="b853a-154">Kurs</span><span class="sxs-lookup"><span data-stu-id="b853a-154">Rate</span></span>             | <span data-ttu-id="b853a-155">30,000</span><span class="sxs-lookup"><span data-stu-id="b853a-155">30,000</span></span>      |
    | <span data-ttu-id="b853a-156">Flik för radinformation</span><span class="sxs-lookup"><span data-stu-id="b853a-156">Line details tab</span></span> |             |
    | <span data-ttu-id="b853a-157">Manuellt</span><span class="sxs-lookup"><span data-stu-id="b853a-157">Manual</span></span>           | <span data-ttu-id="b853a-158">(markerad)</span><span class="sxs-lookup"><span data-stu-id="b853a-158">(marked)</span></span>    |

    <span data-ttu-id="b853a-159">Rad 2: Fliken **Rad för inkomstutrag**</span><span class="sxs-lookup"><span data-stu-id="b853a-159">Line 2: **Earning statement line** tab</span></span>

    | <span data-ttu-id="b853a-160">Fält</span><span class="sxs-lookup"><span data-stu-id="b853a-160">Field</span></span>            | <span data-ttu-id="b853a-161">Värde</span><span class="sxs-lookup"><span data-stu-id="b853a-161">Value</span></span>    |
    |------------------|----------|
    | <span data-ttu-id="b853a-162">Inkomstkod</span><span class="sxs-lookup"><span data-stu-id="b853a-162">Earnings code</span></span>    | <span data-ttu-id="b853a-163">Bonus</span><span class="sxs-lookup"><span data-stu-id="b853a-163">Bonus</span></span>    |
    | <span data-ttu-id="b853a-164">Kvantitet</span><span class="sxs-lookup"><span data-stu-id="b853a-164">Quantity</span></span>         | <span data-ttu-id="b853a-165">1.0000</span><span class="sxs-lookup"><span data-stu-id="b853a-165">1.0000</span></span>   |
    | <span data-ttu-id="b853a-166">Kurs</span><span class="sxs-lookup"><span data-stu-id="b853a-166">Rate</span></span>             | <span data-ttu-id="b853a-167">4250.00</span><span class="sxs-lookup"><span data-stu-id="b853a-167">4250.00</span></span>  |
    | <span data-ttu-id="b853a-168">Flik för radinformation</span><span class="sxs-lookup"><span data-stu-id="b853a-168">Line details tab</span></span> |          |
    | <span data-ttu-id="b853a-169">Manuell</span><span class="sxs-lookup"><span data-stu-id="b853a-169">Manual</span></span>           | <span data-ttu-id="b853a-170">(markerad)</span><span class="sxs-lookup"><span data-stu-id="b853a-170">(marked)</span></span> |

    <span data-ttu-id="b853a-171">Rad 3: Fliken **Rad för inkomstutdrag**</span><span class="sxs-lookup"><span data-stu-id="b853a-171">Line 3: **Earning statement line** tab</span></span>

    | <span data-ttu-id="b853a-172">Fält</span><span class="sxs-lookup"><span data-stu-id="b853a-172">Field</span></span>           | <span data-ttu-id="b853a-173">Värde</span><span class="sxs-lookup"><span data-stu-id="b853a-173">Value</span></span>      |
    |-----------------|------------|
    | <span data-ttu-id="b853a-174">Inkomstkod</span><span class="sxs-lookup"><span data-stu-id="b853a-174">Earnings code</span></span>   | <span data-ttu-id="b853a-175">Provision</span><span class="sxs-lookup"><span data-stu-id="b853a-175">Commission</span></span> |
    | <span data-ttu-id="b853a-176">Kvantitet</span><span class="sxs-lookup"><span data-stu-id="b853a-176">Quantity</span></span>        | <span data-ttu-id="b853a-177">1.0000</span><span class="sxs-lookup"><span data-stu-id="b853a-177">1.0000</span></span>     |
    | <span data-ttu-id="b853a-178">Kurs</span><span class="sxs-lookup"><span data-stu-id="b853a-178">Rate</span></span>            | <span data-ttu-id="b853a-179">1 299,00</span><span class="sxs-lookup"><span data-stu-id="b853a-179">!,299.00</span></span>   |
    | <span data-ttu-id="b853a-180">Kurs</span><span class="sxs-lookup"><span data-stu-id="b853a-180">Rate</span></span>            | <span data-ttu-id="b853a-181">1,299.00</span><span class="sxs-lookup"><span data-stu-id="b853a-181">1,299.00</span></span>   |
    | <span data-ttu-id="b853a-182">Flik för radinformation</span><span class="sxs-lookup"><span data-stu-id="b853a-182">Line detail tab</span></span> |            |
    | <span data-ttu-id="b853a-183">Manuell</span><span class="sxs-lookup"><span data-stu-id="b853a-183">Manual</span></span>          | <span data-ttu-id="b853a-184">(markerad)</span><span class="sxs-lookup"><span data-stu-id="b853a-184">(Marked)</span></span>   |

    > [!NOTE]
    > <span data-ttu-id="b853a-185">Sätta det **manuella** skjutreglaget till **Ja** på fliken **Radinformation** för respektive rad för inkomstutdrag är nyckeln till att initiala saldon ska anges för respektive arbetstagare.</span><span class="sxs-lookup"><span data-stu-id="b853a-185">Setting the **Manual** slider to **Yes** in the **Line Details** tab for each earnings statement line is key to have payroll beginning balances entered for each worker.</span></span>

3. <span data-ttu-id="b853a-186">I fönstret **Åtgärd** klickar du på **Frisläpp intäktsutdrag** USA-FED ER-FICA.</span><span class="sxs-lookup"><span data-stu-id="b853a-186">On the **Action** pane, click **Release earnings statement** USA-FED-ER-FICA.</span></span>
4. <span data-ttu-id="b853a-187">I fönstret **Åtgärd** klickar du på **Löneutdrag** för att öppna sidan **Skapa löneutdrag** och anger följande:</span><span class="sxs-lookup"><span data-stu-id="b853a-187">On the **Action** pane click **Pay statement** to open the **Generate pay statements** page and set the following:</span></span>

    | <span data-ttu-id="b853a-188">Fält</span><span class="sxs-lookup"><span data-stu-id="b853a-188">Field</span></span>              | <span data-ttu-id="b853a-189">Värde</span><span class="sxs-lookup"><span data-stu-id="b853a-189">Value</span></span>     |
    |--------------------|-----------|
    | <span data-ttu-id="b853a-190">Betalningsdatum</span><span class="sxs-lookup"><span data-stu-id="b853a-190">Payment date</span></span>       | <span data-ttu-id="b853a-191">6/30/2017</span><span class="sxs-lookup"><span data-stu-id="b853a-191">6/30/2017</span></span> |
    | <span data-ttu-id="b853a-192">Typ av lönekörning</span><span class="sxs-lookup"><span data-stu-id="b853a-192">Payment run type</span></span>   | <span data-ttu-id="b853a-193">Manuell</span><span class="sxs-lookup"><span data-stu-id="b853a-193">Manual</span></span>    |
    | <span data-ttu-id="b853a-194">Inaktivera redovisning</span><span class="sxs-lookup"><span data-stu-id="b853a-194">Disable accounting</span></span> |   <span data-ttu-id="b853a-195">Ja</span><span class="sxs-lookup"><span data-stu-id="b853a-195">Yes</span></span>     |

    > [!NOTE] 
    > <span data-ttu-id="b853a-196">Detta är endast tillgängligt när betalningens körningstyp är manuell och där användaren vill inaktivera redovisningen för betalningskörningen.</span><span class="sxs-lookup"><span data-stu-id="b853a-196">This is only available when the payment run type is manual and wherein the user want to disable accounting on the pay run.</span></span>

    <span data-ttu-id="b853a-197">Klicka på **OK** och stäng **Informationsloggen**.</span><span class="sxs-lookup"><span data-stu-id="b853a-197">Click **OK** and close the **Infolog**.</span></span>

#### <a name="why-the-disable-accounting-slider-needs-to-set-to-yes-when-generating-pay-statements"></a><span data-ttu-id="b853a-198">Varför måste skjutereglaget ställas in på Ja vid generering av lönerapporter?</span><span class="sxs-lookup"><span data-stu-id="b853a-198">Why the Disable Accounting slider needs to set to Yes when generating pay statements?</span></span>

<span data-ttu-id="b853a-199">Att ställa in skjutreglaget på **Ja** förhindrar att rader i löneutdraget distribueras till redovisningen.</span><span class="sxs-lookup"><span data-stu-id="b853a-199">Setting the slider to **Yes** prevents lines in the pay statement from being distributed to General ledger.</span></span> <span data-ttu-id="b853a-200">Redovisningsbeloppen uppdaterar tidigare när kontosaldon från äldre system angavs.</span><span class="sxs-lookup"><span data-stu-id="b853a-200">General ledger amounts were updating earlier when account balances from the legacy system were entered.</span></span> <span data-ttu-id="b853a-201">Att ange ingående balanser för löner låter dig skapa rapporter som innehåller information från föregående år och för att identifiera gränser av förmåns- och skattemässiga skäl.</span><span class="sxs-lookup"><span data-stu-id="b853a-201">Entering beginning balances for Payroll lets you generate reports that include information from prior years, as well as for identifying limits for benefit and tax purposes.</span></span>

### <a name="c-create-pay-statements-for-employees"></a><span data-ttu-id="b853a-202">C.</span><span class="sxs-lookup"><span data-stu-id="b853a-202">C.</span></span> <span data-ttu-id="b853a-203">Skapa löneutdrag för anställda</span><span class="sxs-lookup"><span data-stu-id="b853a-203">Create pay statements for employees</span></span>

<span data-ttu-id="b853a-204">Du måste kontrollera att betalningsutdrag korrekt återspeglar lönedatan när du genererar löneutdrag med initiala saldon.</span><span class="sxs-lookup"><span data-stu-id="b853a-204">After you generate pay statements that have beginning balances, you must verify that the pay statements accurately reflect payroll data.</span></span> <span data-ttu-id="b853a-205">Du måste även manuellt uppdatera förmåns- och skatteinformationen så att denna matchar värdena i det föregående lönesystemet.</span><span class="sxs-lookup"><span data-stu-id="b853a-205">You must also manually update the benefit and taxes information to match the values in the previous payroll system.</span></span> <span data-ttu-id="b853a-206">När du har bekräftat att beloppen från föregående lönesystem matchar beloppen på aktuella löneutdrag, måste du slutföra löneutdragen.</span><span class="sxs-lookup"><span data-stu-id="b853a-206">After you verify that the amounts from the previous payroll system match the amounts on the current pay statements, you must finalize the pay statements.</span></span>

1. <span data-ttu-id="b853a-207">Öppna sidan **Alla löneutdrag**.</span><span class="sxs-lookup"><span data-stu-id="b853a-207">Open the **All pay statements** page.</span></span>
2. <span data-ttu-id="b853a-208">Markera det senast genererade löneutdraget för Michael Redmond</span><span class="sxs-lookup"><span data-stu-id="b853a-208">Highlight the last generated pay statement for Michael Redmond</span></span>
3. <span data-ttu-id="b853a-209">Klicka på **Redigera** för att öppna sidan **Löneutdrag**.</span><span class="sxs-lookup"><span data-stu-id="b853a-209">Click **Edit** to open the **Pay statement** page.</span></span>
4. <span data-ttu-id="b853a-210">Öppna fliken **Förmånsavdrag** och ange följande:</span><span class="sxs-lookup"><span data-stu-id="b853a-210">Open the **Benefit deductions** tab and enter the following:</span></span>

    | <span data-ttu-id="b853a-211">Fält</span><span class="sxs-lookup"><span data-stu-id="b853a-211">Field</span></span>             | <span data-ttu-id="b853a-212">Värde</span><span class="sxs-lookup"><span data-stu-id="b853a-212">Value</span></span>            |
    |-------------------|------------------|
    | <span data-ttu-id="b853a-213">Förmån</span><span class="sxs-lookup"><span data-stu-id="b853a-213">Benefit</span></span>           | <span data-ttu-id="b853a-214">Avdragsbelopp</span><span class="sxs-lookup"><span data-stu-id="b853a-214">Deduction amount</span></span> |
    | <span data-ttu-id="b853a-215">401K</span><span class="sxs-lookup"><span data-stu-id="b853a-215">401K</span></span>              | <span data-ttu-id="b853a-216">Delta</span><span class="sxs-lookup"><span data-stu-id="b853a-216">Participate</span></span>      |
    | <span data-ttu-id="b853a-217">Tandvård</span><span class="sxs-lookup"><span data-stu-id="b853a-217">Dental</span></span>            | <span data-ttu-id="b853a-218">SubSp</span><span class="sxs-lookup"><span data-stu-id="b853a-218">SubSp</span></span>            |
    | <span data-ttu-id="b853a-219">Utgifter för beroendevård</span><span class="sxs-lookup"><span data-stu-id="b853a-219">Dep care spending</span></span> | <span data-ttu-id="b853a-220">Delta</span><span class="sxs-lookup"><span data-stu-id="b853a-220">Participate</span></span>      |
    | <span data-ttu-id="b853a-221">Vision</span><span class="sxs-lookup"><span data-stu-id="b853a-221">Vision</span></span>            | <span data-ttu-id="b853a-222">SupSp</span><span class="sxs-lookup"><span data-stu-id="b853a-222">SupSp</span></span>            |

5. <span data-ttu-id="b853a-223">I fliken **Förmånsbidrag** anger du följande:</span><span class="sxs-lookup"><span data-stu-id="b853a-223">In the **Benefit contributions** tab and enter the following:</span></span>

    | <span data-ttu-id="b853a-224">Fält</span><span class="sxs-lookup"><span data-stu-id="b853a-224">Field</span></span>   | <span data-ttu-id="b853a-225">Värde</span><span class="sxs-lookup"><span data-stu-id="b853a-225">Value</span></span>               |
    |---------|---------------------|
    | <span data-ttu-id="b853a-226">Förmån</span><span class="sxs-lookup"><span data-stu-id="b853a-226">Benefit</span></span> | <span data-ttu-id="b853a-227">Förmånsbelopp</span><span class="sxs-lookup"><span data-stu-id="b853a-227">Contribution amount</span></span> |
    | <span data-ttu-id="b853a-228">401K</span><span class="sxs-lookup"><span data-stu-id="b853a-228">401K</span></span>    | <span data-ttu-id="b853a-229">Delta</span><span class="sxs-lookup"><span data-stu-id="b853a-229">Participate</span></span>         |
    | <span data-ttu-id="b853a-230">Tandvård</span><span class="sxs-lookup"><span data-stu-id="b853a-230">Dental</span></span>  | <span data-ttu-id="b853a-231">SubSp</span><span class="sxs-lookup"><span data-stu-id="b853a-231">SubSp</span></span>               |
    | <span data-ttu-id="b853a-232">Vision</span><span class="sxs-lookup"><span data-stu-id="b853a-232">Vision</span></span>  | <span data-ttu-id="b853a-233">SubSp</span><span class="sxs-lookup"><span data-stu-id="b853a-233">SubSp</span></span>               |

6. <span data-ttu-id="b853a-234">I fliken **Skatteavdrag** anger du följande:</span><span class="sxs-lookup"><span data-stu-id="b853a-234">In the **Tax deductions** tab, enter the following:</span></span>

    | <span data-ttu-id="b853a-235">Fält</span><span class="sxs-lookup"><span data-stu-id="b853a-235">Field</span></span>           | <span data-ttu-id="b853a-236">Värde</span><span class="sxs-lookup"><span data-stu-id="b853a-236">Value</span></span>            |
    |-----------------|------------------|
    | <span data-ttu-id="b853a-237">Skattekod</span><span class="sxs-lookup"><span data-stu-id="b853a-237">Tax code</span></span>        | <span data-ttu-id="b853a-238">Avdragsbelopp</span><span class="sxs-lookup"><span data-stu-id="b853a-238">Deduction amount</span></span> |
    | <span data-ttu-id="b853a-239">USA-FED-ER-FICA</span><span class="sxs-lookup"><span data-stu-id="b853a-239">USA-FED-ER-FICA</span></span> | <span data-ttu-id="b853a-240">1600.00</span><span class="sxs-lookup"><span data-stu-id="b853a-240">1600.00</span></span>          |
    | <span data-ttu-id="b853a-241">USA-FED-ER-MEDI</span><span class="sxs-lookup"><span data-stu-id="b853a-241">USA-FED-ER-MEDI</span></span> | <span data-ttu-id="b853a-242">825.75</span><span class="sxs-lookup"><span data-stu-id="b853a-242">825.75</span></span>           |

7. <span data-ttu-id="b853a-243">I fliken **Skattebidrag** anger du följande:</span><span class="sxs-lookup"><span data-stu-id="b853a-243">In the **Tax contributions** tab enter the following:</span></span>
8. <span data-ttu-id="b853a-244">Klicka på **Beräkna**.</span><span class="sxs-lookup"><span data-stu-id="b853a-244">Click **Calculate**.</span></span>

    > [!IMPORTANT] 
    > <span data-ttu-id="b853a-245">Validera summorna i löneutdraget så att de matchar saldot till dags dato det äldre systemet för arbetstagaren.</span><span class="sxs-lookup"><span data-stu-id="b853a-245">Validate the totals of the pay statement that they match the YTD of the legacy system for the worker.</span></span> <span data-ttu-id="b853a-246">Du kanske vill avstå från att slutföra i nästa steg för att istället validera samtliga löneutdrag sammanlagt.</span><span class="sxs-lookup"><span data-stu-id="b853a-246">You may want to hold off on finalizing in the next step to do some overall validating of all pay statements in aggregate.</span></span> <span data-ttu-id="b853a-247">Kör igenom alla löneutdrag och slutför dem när de väl har validerats.</span><span class="sxs-lookup"><span data-stu-id="b853a-247">Once validated run through all the pay statements and finalize them.</span></span>

<span data-ttu-id="b853a-248">Samma tillvägagångssätt kan vid behov göras kvartalsvis för alla föregående kvartal under varje år.</span><span class="sxs-lookup"><span data-stu-id="b853a-248">The same process can be done in quarter increments if necessary for all prior quarters in each year.</span></span> <span data-ttu-id="b853a-249">Detta behövs bara om kunden behöver visa data kvartalsvis utan att gå tillbaka till det äldre systemet.</span><span class="sxs-lookup"><span data-stu-id="b853a-249">This is only needed if the customer needs to see the data by quarter without going back to the legacy system.</span></span>

## <a name="if-you-make-a-mistake-entering-beginning-balances-for-an-employee"></a><span data-ttu-id="b853a-250">Om du gör ett misstag när du anger initiala saldon för en medarbetare</span><span class="sxs-lookup"><span data-stu-id="b853a-250">If you make a mistake Entering Beginning Balances for an Employee</span></span>

<span data-ttu-id="b853a-251">Det går att återföra och omregistrera transaktioner.</span><span class="sxs-lookup"><span data-stu-id="b853a-251">It is possible to reverse and reenter transactions.</span></span> <span data-ttu-id="b853a-252">Om du vill återföra transaktionen är allt du behöver göra är att slutföra följande steg på sidan **Alla löneutdrag**.</span><span class="sxs-lookup"><span data-stu-id="b853a-252">To reverse the transaction, all you have to do is to complete the follow steps on the **All pay statements** page.</span></span>

1. <span data-ttu-id="b853a-253">Klicka på **Återför**.</span><span class="sxs-lookup"><span data-stu-id="b853a-253">Click **Reverse**.</span></span>
2. <span data-ttu-id="b853a-254">Klicka på **Ja** när meddelandet ”När du återför detta löneutdrag kommer ett utdrag om löneåterförande att skapas för att kompensera detta löneutdrag.</span><span class="sxs-lookup"><span data-stu-id="b853a-254">Click **Yes** when the message "When you reverse this pay statement, a reversing pay statement will be created to offset this pay statement.</span></span> <span data-ttu-id="b853a-255">Ingetdera löneutdrag kan redigeras.</span><span class="sxs-lookup"><span data-stu-id="b853a-255">Neither pay statement can be edited.</span></span> <span data-ttu-id="b853a-256">Vill du återföra detta löneudrag?"</span><span class="sxs-lookup"><span data-stu-id="b853a-256">Do you want to reverse this pay statement?"</span></span> <span data-ttu-id="b853a-257">visningar.</span><span class="sxs-lookup"><span data-stu-id="b853a-257">displays.</span></span> 

<span data-ttu-id="b853a-258">När du återför löneutdraget kan du generera ett nytt löneutdrag för arbetaren från inkomstutdrag som du skapade tidigare.</span><span class="sxs-lookup"><span data-stu-id="b853a-258">After you reverse the pay statement, you can generate a new pay statement for the worker from the earnings statement that you created previously.</span></span> <span data-ttu-id="b853a-259">Kom ihåg att korrigera felaktiga rader på inkomstutdraget innan du skapar nya löneutdrag och generera sedan nya löneutdrag med korrekt belopp.</span><span class="sxs-lookup"><span data-stu-id="b853a-259">Be sure to fix any incorrect lines on the earnings statement before you generate the new pay statement, and then generate new pay statements with the correct amounts.</span></span> 


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]