---
title: Skapa avancerade kontrakt för fakturering baserat på status
description: I det här avsnittet beskrivs hur du skapar projektkontrakt så att du kan skapa fakturor för kunder, baserat på en procentsats av färdigt arbete.
author: RadhikaRS
manager: AnnBe
ms.date: 03/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: 90cae104d0abad909606ef6a0e0c45ed95e74de2
ms.sourcegitcommit: dfef2faf881b2db1bd0f016df36e2b838105312b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/22/2020
ms.locfileid: "3282849"
---
# <a name="create-advanced-contracts-for-billing-based-on-progress"></a><span data-ttu-id="abf73-103">Skapa avancerade kontrakt för fakturering baserat på status</span><span class="sxs-lookup"><span data-stu-id="abf73-103">Create advanced contracts for billing based on progress</span></span>
[!include [banner](../includes/banner.md)]

<span data-ttu-id="abf73-104">I det här avsnittet beskrivs hur du skapar projektkontrakt så att du kan skapa fakturor för kunder, baserat på en procentsats av färdigt arbete.</span><span class="sxs-lookup"><span data-stu-id="abf73-104">This topic explains how to create project contracts so that you can create invoices for customers, based on a percentage of completed work.</span></span> <span data-ttu-id="abf73-105">Fakturabeloppen beräknas automatiskt för budgetkategorier av arbete som du anger för ett projekt.</span><span class="sxs-lookup"><span data-stu-id="abf73-105">Invoice amounts are automatically calculated for the budget categories of work that you set up for a project.</span></span> <span data-ttu-id="abf73-106">Tajmingen med fakturor har ställts in, när du förhandlar projektkontraktet till kunden.</span><span class="sxs-lookup"><span data-stu-id="abf73-106">The invoice timing is set when you negotiate the project contract with the customer.</span></span>

<span data-ttu-id="abf73-107">Använd förfaranden i detta avsnitt om du vill ställa in ett kontrakt, ett associerat projekt och ett faktureringsreglerna för att beräkna fakturabelopp för budgetkategorier, av arbete som du anger för projektet.</span><span class="sxs-lookup"><span data-stu-id="abf73-107">Use the procedures in this topic to set up a contract, an associated project, and the billing rules that calculate invoice amounts for the budget categories of work that you set up for the project.</span></span>

<span data-ttu-id="abf73-108">När du har skapat kontraktet och projekt, kan du ställa in information om projektet.</span><span class="sxs-lookup"><span data-stu-id="abf73-108">After you've created the contract and the project, you can set up the details of the project.</span></span> <span data-ttu-id="abf73-109">Du kan till exempel definiera aktiviteterna och tilldela anställda till projektet.</span><span class="sxs-lookup"><span data-stu-id="abf73-109">For example, you can define activities and assign workers to the project.</span></span>

## <a name="example"></a><span data-ttu-id="abf73-110">Exempel</span><span class="sxs-lookup"><span data-stu-id="abf73-110">Example</span></span>

<span data-ttu-id="abf73-111">Din organisation är en firma för programvaruutveckling.</span><span class="sxs-lookup"><span data-stu-id="abf73-111">Your organization is a software development firm.</span></span> <span data-ttu-id="abf73-112">Du går med på att sammanställa ett lönelista redovisningpaket för en kund för en total kostnad av 20 000 USD.</span><span class="sxs-lookup"><span data-stu-id="abf73-112">You agree to develop a payroll accounting package for a customer for a total fee of 20,000 US dollars (USD).</span></span> <span data-ttu-id="abf73-113">Organisationen förbinder sig att fakturera kunden när du slutför de specifika procentandelarna av projektet.</span><span class="sxs-lookup"><span data-stu-id="abf73-113">Your organization agrees to invoice the customer as you complete specific percentages of the project.</span></span> <span data-ttu-id="abf73-114">Du ställer in följande projektkategorier för arbetet så att du kan använda dem i faktureringsprocessen:</span><span class="sxs-lookup"><span data-stu-id="abf73-114">You set up the following project categories for the work, so that you can use them in the billing process:</span></span>

- <span data-ttu-id="abf73-115">Konsultarbete</span><span class="sxs-lookup"><span data-stu-id="abf73-115">Consulting</span></span>
- <span data-ttu-id="abf73-116">Design</span><span class="sxs-lookup"><span data-stu-id="abf73-116">Design</span></span>
- <span data-ttu-id="abf73-117">Installation</span><span class="sxs-lookup"><span data-stu-id="abf73-117">Installation</span></span>

<span data-ttu-id="abf73-118">Du ställer också in faktureringsregler som automatiskt beräknar fakturabelopp för procent av projektarbete, som utförs för varje kategori.</span><span class="sxs-lookup"><span data-stu-id="abf73-118">You also set up billing rules that automatically calculate the invoice amounts for the percentage of project work that is completed in each category.</span></span>

<span data-ttu-id="abf73-119">Budgetchefen skapar en budget för projektkategorier.</span><span class="sxs-lookup"><span data-stu-id="abf73-119">The budget manager creates a budget for the project categories.</span></span> <span data-ttu-id="abf73-120">Beloppet för slutfört arbete beräknas automatiskt som en procentandel av faktiskt arbete jämfört med budgeterade belopp.</span><span class="sxs-lookup"><span data-stu-id="abf73-120">The amount of completed work is automatically calculated as a percentage of actual work in comparison to the budgeted amounts.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="abf73-121">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="abf73-121">Prerequisites</span></span>

<span data-ttu-id="abf73-122">Innan du skapar ett projekt som använder faktureringsregler måste du ställa in nummer serier för faktureringsregler och en avgiftsjournal som används för att bokföra förfallna faktureringar.</span><span class="sxs-lookup"><span data-stu-id="abf73-122">Before you create a project that uses billing rules, you must set up the number sequences for billing rules and a fee journal that is used to post progress billings.</span></span>

1. <span data-ttu-id="abf73-123">Gå till **Projektledning och redovisning** \> **Inställningar** \> **Parametrar för projekthantering och redovisning**.</span><span class="sxs-lookup"><span data-stu-id="abf73-123">Go to **Project management and accounting** \> **Setup** \> **Project management and accounting parameters**.</span></span>
2. <span data-ttu-id="abf73-124">På sidan **Parametrar för projekthantering och redovisning** på fliken **nummer serier** på sidan projekthantering och redovisningsparametrar.</span><span class="sxs-lookup"><span data-stu-id="abf73-124">On the **Project management and accounting parameters** page, on the **Number sequences** tab, set up the number sequence that you want to use when billing rules are created.</span></span>
3. <span data-ttu-id="abf73-125">Gå till **Projekthantering och redovisning** \> **Journaler** \> **Avgift**.</span><span class="sxs-lookup"><span data-stu-id="abf73-125">Go to **Project management and accounting** \> **Journals** \> **Fee**.</span></span>
4. <span data-ttu-id="abf73-126">På sidan **Avgiftsjournal**, välj **Ny** och ange journalnamnet.</span><span class="sxs-lookup"><span data-stu-id="abf73-126">On the **Fee journal** page, select **New**, and enter the journal name.</span></span>

## <a name="create-a-contract-for-progress-billings"></a><span data-ttu-id="abf73-127">Skapa ett kontrakt för delfakturering</span><span class="sxs-lookup"><span data-stu-id="abf73-127">Create a contract for progress billings</span></span>

<span data-ttu-id="abf73-128">Använd den här proceduren för att skapa en projektkontrakt för ett fastprisprojekt.</span><span class="sxs-lookup"><span data-stu-id="abf73-128">Use this procedure to create a project contract for a fixed-price project.</span></span> <span data-ttu-id="abf73-129">Du skapar en projektfaktura när utfört arbetet på projektet, når en viss procent.</span><span class="sxs-lookup"><span data-stu-id="abf73-129">You create a project invoice when the work that is completed on the project reaches a specified percentage.</span></span>

1. <span data-ttu-id="abf73-130">Gå till **Projekthantering och redovisning** \> **Projekt** \> **Projektkontrakt**.</span><span class="sxs-lookup"><span data-stu-id="abf73-130">Go to **Project management and accounting** \> **Projects** \> **Project contracts**.</span></span>
2. <span data-ttu-id="abf73-131">Välj **Projektkontrakt** på sidan **Leveranssätt**.</span><span class="sxs-lookup"><span data-stu-id="abf73-131">On the **Project contracts** page, select **New**.</span></span>
3. <span data-ttu-id="abf73-132">I dialogrutan **nytt projektkontrakt** anger du följande fält:</span><span class="sxs-lookup"><span data-stu-id="abf73-132">In the **New project contract** dialog box, set the following fields:</span></span>

    - <span data-ttu-id="abf73-133">**Namn**</span><span class="sxs-lookup"><span data-stu-id="abf73-133">**Name**</span></span>
    - <span data-ttu-id="abf73-134">**Finansieringstyp**</span><span class="sxs-lookup"><span data-stu-id="abf73-134">**Funding type**</span></span>
    - <span data-ttu-id="abf73-135">**Finansieringskälla**</span><span class="sxs-lookup"><span data-stu-id="abf73-135">**Funding source**</span></span>
    - <span data-ttu-id="abf73-136">**Försäljningsvaluta** – som standard används denna valuta för kundfakturor som är kopplade till projektkontraktet.</span><span class="sxs-lookup"><span data-stu-id="abf73-136">**Sales currency** – By default, this currency is used for customer invoices that are associated with the project contract.</span></span> <span data-ttu-id="abf73-137">Du kan dock ändra försäljningsvaluta för en viss kundfaktura.</span><span class="sxs-lookup"><span data-stu-id="abf73-137">However, you can change the sales currency on a specific customer invoice.</span></span>

4. <span data-ttu-id="abf73-138">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="abf73-138">Select **OK**.</span></span> <span data-ttu-id="abf73-139">Informationen kopieras till huvudet på sidan **Projektkontrakt**.</span><span class="sxs-lookup"><span data-stu-id="abf73-139">The information is copied to the header of the **Project contracts** page.</span></span>
5. <span data-ttu-id="abf73-140">På sidan **Projektkontrakt** fyll i resten av den information som krävs för projektet.</span><span class="sxs-lookup"><span data-stu-id="abf73-140">On the **Project contracts** page, fill in the rest of the required information for the project.</span></span>

## <a name="create-a-project-for-progress-billings"></a><span data-ttu-id="abf73-141">Skapa ett projekt för delfakturering</span><span class="sxs-lookup"><span data-stu-id="abf73-141">Create a project for progress billings</span></span>

<span data-ttu-id="abf73-142">Följ dessa steg för att skapa ett projekt och alla delprojekt som är associerade med ett projektkontrakt.</span><span class="sxs-lookup"><span data-stu-id="abf73-142">Follow these steps to create a project and any subprojects that are associated with a project contract.</span></span>

1. <span data-ttu-id="abf73-143">Gå till **Projekthantering och redovisning** \> **Projekt** \> **Alla projekt**.</span><span class="sxs-lookup"><span data-stu-id="abf73-143">Go to **Project management and accounting** \> **Projects** \> **All projects**.</span></span>
2. <span data-ttu-id="abf73-144">På sidan **Alla projekt**, välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="abf73-144">On the **All projects** page, select **New**.</span></span>
3. <span data-ttu-id="abf73-145">I dialogrutan **Nytt projekt** i fältet **Projekttyp**, välj **Tid och material**.</span><span class="sxs-lookup"><span data-stu-id="abf73-145">In the **New project** dialog box, in the **Project type** field, select **Time and material**.</span></span>
4. <span data-ttu-id="abf73-146">Välj en projektgrupp</span><span class="sxs-lookup"><span data-stu-id="abf73-146">Select a project group.</span></span> <span data-ttu-id="abf73-147">En projektgrupp definierar bokföringsinformation för projekt som tilldelats gruppen.</span><span class="sxs-lookup"><span data-stu-id="abf73-147">A project group defines the posting information for the projects that are assigned to the group.</span></span>
5. <span data-ttu-id="abf73-148">Markera **Skapa projekt**.</span><span class="sxs-lookup"><span data-stu-id="abf73-148">Select **Create project**.</span></span>
6. <span data-ttu-id="abf73-149">Ange projektfasen till **Pågår** efter att du har skapat projektet.</span><span class="sxs-lookup"><span data-stu-id="abf73-149">After the project is created, set the project stage to **In process**.</span></span>

## <a name="create-a-budget-for-a-project"></a><span data-ttu-id="abf73-150">Skapa en budget för ett projekt</span><span class="sxs-lookup"><span data-stu-id="abf73-150">Create a budget for a project</span></span>

<span data-ttu-id="abf73-151">Budgetkategorierna används för att beräkna automatiskt fakturabeloppen för procent av arbete som utförs för varje kategori.</span><span class="sxs-lookup"><span data-stu-id="abf73-151">Budget categories are used to automatically calculate the invoice amounts for the percentage of work that is completed for each category.</span></span> <span data-ttu-id="abf73-152">Skapa budgetkategorier för de uppskattade kostnaderna genom att följa stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="abf73-152">Follow these steps to create budget categories for the estimated costs.</span></span>

1. <span data-ttu-id="abf73-153">Gå till **Projekthantering och redovisning** \> **Projekt** \> **Alla projekt**.</span><span class="sxs-lookup"><span data-stu-id="abf73-153">Go to **Project management and accounting** \> **Projects** \> **All projects**.</span></span>
2. <span data-ttu-id="abf73-154">På sidan **Alla projektet**, välj och öppna det projekt du vill.</span><span class="sxs-lookup"><span data-stu-id="abf73-154">On the **All projects** page, select and open the project that you want.</span></span>
3. <span data-ttu-id="abf73-155">På sidan **Projekt** i åtgärdsfönstret **Plan** i gruppen **Budget**, välj **Projektbudget**.</span><span class="sxs-lookup"><span data-stu-id="abf73-155">On the **Projects** page, on the Action Pane, on the **Plan** tab, in the **Budget** group, select **Project budget**.</span></span>
4. <span data-ttu-id="abf73-156">På sidan **Projektbudget** ange en uppskattad kostnad för varje kategori i projektet.</span><span class="sxs-lookup"><span data-stu-id="abf73-156">On the **Project budget** page, enter an estimated cost for each category in the project.</span></span>

## <a name="create-billing-rules-for-progress-billings"></a><span data-ttu-id="abf73-157">Skapa faktureringsregler för delfakturering</span><span class="sxs-lookup"><span data-stu-id="abf73-157">Create billing rules for progress billings</span></span>

1. <span data-ttu-id="abf73-158">Gå till **Projekthantering och redovisning** \> **Projekt** \> **Projektkontrakt**.</span><span class="sxs-lookup"><span data-stu-id="abf73-158">Go to **Project management and accounting** \> **Projects** \> **Project contracts**.</span></span>
2. <span data-ttu-id="abf73-159">På sidan **projektkontrakt** väljer du och öppnar ett projektkontrakt.</span><span class="sxs-lookup"><span data-stu-id="abf73-159">On the **Project contracts** page, select and open a project contract.</span></span>
3. <span data-ttu-id="abf73-160">På sidan projektkontrakt, på snabbfliken **faktureringsregler**, välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="abf73-160">On the project contract page, on the **Billing rules** FastTab, select **Add**.</span></span>
4. <span data-ttu-id="abf73-161">På sidan **Faktureringsregel** i fältet **Radtyp**, välj **Förlopp**.</span><span class="sxs-lookup"><span data-stu-id="abf73-161">On the **Billing rule** page, in the **Line type** field, select **Progress**.</span></span>
5. <span data-ttu-id="abf73-162">På snabbfliken **Information om faktureringsregelrad** i fältet **kontraktsvärde**, ange kontraktets totala värde.</span><span class="sxs-lookup"><span data-stu-id="abf73-162">On the **Billing rule line details** FastTab, in the **Contract value** field, enter the total value of the contract.</span></span>
6. <span data-ttu-id="abf73-163">Välj kategori att bokföra avgiftstransaktionen till i fältet **kategori**.</span><span class="sxs-lookup"><span data-stu-id="abf73-163">In the **Category** field, select the category to post the fee transaction to.</span></span>
7. <span data-ttu-id="abf73-164">Välj det projekt eller den uppgift som använder den här faktureringsregeln i fältet **projekt**.</span><span class="sxs-lookup"><span data-stu-id="abf73-164">In the **Project** field, select the project that uses this billing rule.</span></span>
8. <span data-ttu-id="abf73-165">Valfritt: Tilldela faktureringsregeln till ytterligare projekt.</span><span class="sxs-lookup"><span data-stu-id="abf73-165">Optional: Assign the billing rule to additional projects.</span></span> <span data-ttu-id="abf73-166">På snabbfliken **Projekt** i avsnittet **Tillgängliga projekt**, välj ett projekt och välj sedan högerpilen för att lägga till projektet i avsnittet **Valda projekt**.</span><span class="sxs-lookup"><span data-stu-id="abf73-166">On the **Project** FastTab, in the **Available projects** section, select a project, and then select the right arrow button to add the project to the **Selected projects** section.</span></span>
9. <span data-ttu-id="abf73-167">Valfritt: Beräkna procentbeloppet som kunden innehåller från betalningar i en faktura.</span><span class="sxs-lookup"><span data-stu-id="abf73-167">Optional: Calculate the percentage amount that the customer withholds from payments on an invoice.</span></span> <span data-ttu-id="abf73-168">På snabbfliken **Villkor för innehållen betalning**, välj finansieringskällan och sedan i fältet **kvarhållandeprocentsats**, ange kvarhållandeprocentsatsen.</span><span class="sxs-lookup"><span data-stu-id="abf73-168">On the **Payment retention terms** FastTab, select the funding source, and then, in the **Retention percentage** field, enter the retention percentage.</span></span>
10. <span data-ttu-id="abf73-169">Upprepa dessa steg för att skapa ytterligare faktureringsregler för projektkontraktet.</span><span class="sxs-lookup"><span data-stu-id="abf73-169">Repeat these steps to create additional billing rules for the project contract.</span></span>
