---
title: Generera sjukförsäkringsrapporter i förmånshanteringen
description: I det här avsnittet beskrivs hur förmånshantering kan hjälpa dig att spåra information som rapporteras i formulär 1095-B och formulär 1095-C för arbetsgivarmandatet för sjukförsäkring (ACA).
author: andreabichsel
manager: tfehr
ms.date: 12/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-12-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 2e4b250f4a059719067a9e19bbf3ce4aecc9bb1f
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/03/2021
ms.locfileid: "5114340"
---
# <a name="generate-aca-reports-in-benefits-management"></a><span data-ttu-id="d8a62-103">Generera ACA-rapporter i förmånshanteringen</span><span class="sxs-lookup"><span data-stu-id="d8a62-103">Generate ACA reports in Benefits management</span></span>

<span data-ttu-id="d8a62-104">Förmånshanteringen kan hjälpa dig att spåra information som rapporteras i formulär 1095-B och formulär 1095-C för arbetsgivarmandatet för sjukförsäkring (ACA).</span><span class="sxs-lookup"><span data-stu-id="d8a62-104">Benefits management helps you track information that is reported on Form 1095-B and Form 1095-C for the Affordable Care Act (ACA) employer mandate.</span></span> <span data-ttu-id="d8a62-105">Precis som ACA-rapporteringsfunktionerna i den gamla arbetsytan **Förmåner** gäller denna funktion endast juridiska personer i USA.</span><span class="sxs-lookup"><span data-stu-id="d8a62-105">Like the ACA reporting capability in the old **Benefits** workspace, this functionality applies only to legal entities in the United States.</span></span>

<span data-ttu-id="d8a62-106">Om du vill använda den här funktionen måste du först aktivera **Avancerad förmånshantering**.</span><span class="sxs-lookup"><span data-stu-id="d8a62-106">To use this functionality, you must first turn on **Advanced Benefits Management**.</span></span> <span data-ttu-id="d8a62-107">Mer information, inklusive viktiga förbehåll angående förmånshantering, finns i [Aktivera eller inaktivera förmånshantering](hr-admin-manage-features.md#enable-or-disable-benefits-management).</span><span class="sxs-lookup"><span data-stu-id="d8a62-107">For more information, including important caveats about Benefits management, see [Enable or disable Benefits management](hr-admin-manage-features.md#enable-or-disable-benefits-management).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d8a62-108">Du kan bara använda ACA-rapportering från antingen arbetsytan **Förmånshantering** eller den gamla arbetsytan **Förmåner**, men inte från båda.</span><span class="sxs-lookup"><span data-stu-id="d8a62-108">You can use ACA reporting only from either the **Benefits management** workspace or the old **Benefits** workspace, not from both.</span></span> <span data-ttu-id="d8a62-109">Om du till exempel har växlat till Förmånshantering blir ACA-rapporteringen bara tillgänglig från arbetsytan **Förmånshantering**, inte från den gamla arbetsytan **Förmåner**.</span><span class="sxs-lookup"><span data-stu-id="d8a62-109">For example, if you switched to Benefits management, ACA reporting is available only from the **Benefits management** workspace, not from the old **Benefits** workspace.</span></span>
>
> <span data-ttu-id="d8a62-110">Om du växlar till Förmånshantering mitt under ett registreringsår måste du konfigurera medarbetardata korrekt för hela året i Förmånshanteringen.</span><span class="sxs-lookup"><span data-stu-id="d8a62-110">If you switch to Benefits management in the middle of an enrollment year, you must correctly configure employee data for the whole year in Benefits management.</span></span> <span data-ttu-id="d8a62-111">På det här sättet ser du till att du får korrekt rapporteringsinformation för hela året.</span><span class="sxs-lookup"><span data-stu-id="d8a62-111">In this way, you ensure that you will receive accurate reporting information for the whole year.</span></span>

## <a name="getting-started"></a><span data-ttu-id="d8a62-112">Komma igång</span><span class="sxs-lookup"><span data-stu-id="d8a62-112">Getting started</span></span>

<span data-ttu-id="d8a62-113">Om du vill spåra information för 1095-formulär måste du först skapa en eller flera disponeringsgrupper för sjukförsäkring.</span><span class="sxs-lookup"><span data-stu-id="d8a62-113">To track information for 1095 forms, first create one or more Affordable Care coverage groups.</span></span> <span data-ttu-id="d8a62-114">Grupperna visar följande information:</span><span class="sxs-lookup"><span data-stu-id="d8a62-114">These groups indicate the following information:</span></span>

- <span data-ttu-id="d8a62-115">Det disponeringserbjudande som medarbetaren har tillhandahållits</span><span class="sxs-lookup"><span data-stu-id="d8a62-115">The offer of coverage that was provided to an employee</span></span>
- <span data-ttu-id="d8a62-116">Medarbetarens andel av den lägsta månadspremien, om kostnaden överstiger den federala fattigdomsgränsen</span><span class="sxs-lookup"><span data-stu-id="d8a62-116">The employee's share of the lowest-cost monthly premium, if the cost is above the federal poverty line</span></span>
- <span data-ttu-id="d8a62-117">De skyddsramar som används av arbetsgivaren, om tillämpligt</span><span class="sxs-lookup"><span data-stu-id="d8a62-117">The safe harbor that is used by the employer, if applicable</span></span>

<span data-ttu-id="d8a62-118">Med disponeringsgrupper för sjukförsäkring kan du hantera denna information för flera medarbetarposter med samma villkor.</span><span class="sxs-lookup"><span data-stu-id="d8a62-118">Affordable Care coverage groups help you manage this information for multiple employee records that have the same conditions.</span></span> <span data-ttu-id="d8a62-119">Du kan enkelt tilldela grupper till en eller flera medarbetare.</span><span class="sxs-lookup"><span data-stu-id="d8a62-119">You can easily assign groups to one or more employees.</span></span>

### <a name="create-or-edit-an-affordable-care-coverage-group"></a><span data-ttu-id="d8a62-120">Skapa eller redigera en disponeringsgrupp för sjukförsäkring</span><span class="sxs-lookup"><span data-stu-id="d8a62-120">Create or edit an Affordable Care coverage group</span></span>

1. <span data-ttu-id="d8a62-121">I arbetsytan **Förmånshantering** väljer du **Disponeringsgrupp för sjukförsäkring**.</span><span class="sxs-lookup"><span data-stu-id="d8a62-121">In the **Benefits management** workspace, select **Affordable Care coverage group**.</span></span>

    ![Välja disponeringsgrupp för sjukförsäkring](./media/hr-benefits-management-aca-coverage-group.png)

2. <span data-ttu-id="d8a62-123">Välj **Ny** om du vill skapa en ny disponeringsgrupp för sjukförsäkring, eller **Redigera** för att ändra en befintlig grupp.</span><span class="sxs-lookup"><span data-stu-id="d8a62-123">Select **New** to create a new Affordable Care coverage group or **Edit** to change an existing group.</span></span>

    ![Välja Ny eller Redigera](./media/hr-benefits-management-aca-new.png)

3. <span data-ttu-id="d8a62-125">Ange följande fält.</span><span class="sxs-lookup"><span data-stu-id="d8a62-125">Set the following fields.</span></span>

    | <span data-ttu-id="d8a62-126">Fält</span><span class="sxs-lookup"><span data-stu-id="d8a62-126">Field</span></span> | <span data-ttu-id="d8a62-127">beskrivning</span><span class="sxs-lookup"><span data-stu-id="d8a62-127">Description</span></span> |
    |---|---|
    | <span data-ttu-id="d8a62-128">Namn</span><span class="sxs-lookup"><span data-stu-id="d8a62-128">Name</span></span> | <span data-ttu-id="d8a62-129">Ange ett namn på gruppen.</span><span class="sxs-lookup"><span data-stu-id="d8a62-129">Enter a name for the group.</span></span> |
    | <span data-ttu-id="d8a62-130">beskrivning</span><span class="sxs-lookup"><span data-stu-id="d8a62-130">Description</span></span> | <span data-ttu-id="d8a62-131">Ange en beskrivning för gruppen.</span><span class="sxs-lookup"><span data-stu-id="d8a62-131">Enter a description of the group.</span></span> |
    | <span data-ttu-id="d8a62-132">Erbjudande om försäkringsskydd</span><span class="sxs-lookup"><span data-stu-id="d8a62-132">Offer of coverage</span></span> | <span data-ttu-id="d8a62-133">Den omfattning som erbjuds medarbetare, dessas make/maka eller partner samt deras beroende.</span><span class="sxs-lookup"><span data-stu-id="d8a62-133">The coverage that is offered to employees, their spouse or partner, and their dependents.</span></span> |
    | <span data-ttu-id="d8a62-134">Medarbetarens del av kostnaden</span><span class="sxs-lookup"><span data-stu-id="d8a62-134">Employee share of cost</span></span> | <span data-ttu-id="d8a62-135">Det belopp som medarbetaren är ansvarig för.</span><span class="sxs-lookup"><span data-stu-id="d8a62-135">The amount that the employee is responsible for.</span></span> |
    | <span data-ttu-id="d8a62-136">Tillämplig safe harbor för avsnitt 4980H</span><span class="sxs-lookup"><span data-stu-id="d8a62-136">Applicable section 4980H safe harbor</span></span> | <span data-ttu-id="d8a62-137">4980H-koden för skyddsramar eller kod för övergångslättnad.</span><span class="sxs-lookup"><span data-stu-id="d8a62-137">The 4980H safe harbor or transition relief code.</span></span> |
    | <span data-ttu-id="d8a62-138">Planens startmånad</span><span class="sxs-lookup"><span data-stu-id="d8a62-138">Plan start month</span></span> | <span data-ttu-id="d8a62-139">Välj den kalendermånaden när förmånsplanens år börjar.</span><span class="sxs-lookup"><span data-stu-id="d8a62-139">Select the calendar month when your benefit plan year begins.</span></span> |
    | <span data-ttu-id="d8a62-140">Grupp giltig från</span><span class="sxs-lookup"><span data-stu-id="d8a62-140">Group valid from</span></span> | <span data-ttu-id="d8a62-141">Det första datum då posten är giltig.</span><span class="sxs-lookup"><span data-stu-id="d8a62-141">The first date when this record is valid.</span></span> |
    | <span data-ttu-id="d8a62-142">Grupp giltig till</span><span class="sxs-lookup"><span data-stu-id="d8a62-142">Group valid through</span></span> | <span data-ttu-id="d8a62-143">Det sista datum då posten är giltig.</span><span class="sxs-lookup"><span data-stu-id="d8a62-143">The last date when this record is valid.</span></span> <span data-ttu-id="d8a62-144">Om det inte finns något utgångsdatum anger du **Aldrig**.</span><span class="sxs-lookup"><span data-stu-id="d8a62-144">If there is no expiration date, enter **Never**.</span></span> |

    ![Skapa en disponeringsgrupp](./media/hr-benefits-management-aca-new-group.png)

4. <span data-ttu-id="d8a62-146">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="d8a62-146">Select **Save**.</span></span>

### <a name="assign-multiple-employees-to-an-affordable-care-coverage-group"></a><span data-ttu-id="d8a62-147">Tilldela flera medarbetare till en disponeringsgrupp för sjukförsäkring</span><span class="sxs-lookup"><span data-stu-id="d8a62-147">Assign multiple employees to an Affordable Care coverage group</span></span>

1. <span data-ttu-id="d8a62-148">I arbetsytan **Förmånshantering** väljer du **Disponeringsgrupp för sjukförsäkring**.</span><span class="sxs-lookup"><span data-stu-id="d8a62-148">In the **Benefits management** workspace, select **Affordable Care coverage group**.</span></span>
2. <span data-ttu-id="d8a62-149">Välj den grupp som medarbetare ska tilldelas till.</span><span class="sxs-lookup"><span data-stu-id="d8a62-149">Select the group to assign employees to.</span></span>
3. <span data-ttu-id="d8a62-150">Välj **Masstilldelning**.</span><span class="sxs-lookup"><span data-stu-id="d8a62-150">Select **Mass assignment**.</span></span>

    ![Välja Masstilldelning](./media/hr-benefits-management-aca-mass-assignment.png)

4. <span data-ttu-id="d8a62-152">Välj medarbetare i listan och välj sedan **Tilldela**.</span><span class="sxs-lookup"><span data-stu-id="d8a62-152">Select employees in the list, and then select **Assign**.</span></span>

    ![Tilldela valda medarbetare till en grupp](./media/hr-benefits-management-aca-assign-coverage-group.png)

## <a name="maintain-multiple-versions-of-coverage-options"></a><span data-ttu-id="d8a62-154">Underhålla flera versioner av försäkringsskyddsalternativ</span><span class="sxs-lookup"><span data-stu-id="d8a62-154">Maintain multiple versions of coverage options</span></span>

<span data-ttu-id="d8a62-155">Du kan underhålla flera versioner av valfri försäkringsskyddsgrupp.</span><span class="sxs-lookup"><span data-stu-id="d8a62-155">You can maintain multiple versions of any coverage group.</span></span> <span data-ttu-id="d8a62-156">När något ändras i organisationen eller bland de förmåner som erbjuds, kan du hålla gruppens information uppdaterad utan att behöva skapa en ny grupp och tilldela om medarbetare till den.</span><span class="sxs-lookup"><span data-stu-id="d8a62-156">When something changes in your organization or the benefits that are offered, you can keep the group's information up to date without having to create a new group and reassign employees to it.</span></span>

<span data-ttu-id="d8a62-157">När du har skapat disponeringsgrupper för sjukförsäkring kan du masstilldela medarbetare till dem.</span><span class="sxs-lookup"><span data-stu-id="d8a62-157">After you've created Affordable Care coverage groups, you can mass-assign employees to them.</span></span> <span data-ttu-id="d8a62-158">Du kan också tilldela medarbetare till grupper individuellt och ange om ACA-information spåras och rapporteras.</span><span class="sxs-lookup"><span data-stu-id="d8a62-158">You can also individually assign employees to groups, and indicate whether ACA information is tracked and reported.</span></span>

<span data-ttu-id="d8a62-159">Om du inte behöver spåra och rapportera ACA-information för en medarbetare, kan du ange alternativet **Rapportdisponering** som **Nej**.</span><span class="sxs-lookup"><span data-stu-id="d8a62-159">If you don't have to track and report ACA information for an employee, you can set the **Report coverage** option to **No**.</span></span> <span data-ttu-id="d8a62-160">Du kanske till exempel har deltidsanställda som inte kräver ACA-rapportering.</span><span class="sxs-lookup"><span data-stu-id="d8a62-160">For example, you might have part-time employees who don't require ACA reporting.</span></span>

### <a name="override-default-values-for-an-employee"></a><span data-ttu-id="d8a62-161">Åsidosätta standardvärden för en medarbetare</span><span class="sxs-lookup"><span data-stu-id="d8a62-161">Override default values for an employee</span></span>

<span data-ttu-id="d8a62-162">För medarbetare som tilldelats till en disponeringsgrupp för sjukförsäkring kan du ändra följande alternativ under samtliga månader som kräver olika värden:</span><span class="sxs-lookup"><span data-stu-id="d8a62-162">For employees who are assigned to an Affordable Care coverage group, you can change the following options for any months that require different values:</span></span>

- <span data-ttu-id="d8a62-163">Erbjudande om försäkringsskydd</span><span class="sxs-lookup"><span data-stu-id="d8a62-163">Offer of coverage</span></span>
- <span data-ttu-id="d8a62-164">Medarbetarens del av kostnaden</span><span class="sxs-lookup"><span data-stu-id="d8a62-164">Employee share of cost</span></span>
- <span data-ttu-id="d8a62-165">Tillämplig safe harbor för avsnitt 4980H</span><span class="sxs-lookup"><span data-stu-id="d8a62-165">Applicable section 4980H safe harbor</span></span>

> [!NOTE]
> <span data-ttu-id="d8a62-166">För 2020 års ACA-rapporter måste du rapportera både arbets- och hempostnummer i formulär 1095-C.</span><span class="sxs-lookup"><span data-stu-id="d8a62-166">For 2020 ACA reports, you must report both work and home ZIP Codes on Form 1095-C.</span></span> <span data-ttu-id="d8a62-167">Värden fylls i automatiskt baserat på för tillfället aktiva platser.</span><span class="sxs-lookup"><span data-stu-id="d8a62-167">Values are automatically filled in, based on current active locations.</span></span> <span data-ttu-id="d8a62-168">Om någon av dessa platser var annorlunda under någon del av året måste du åsidosätta värdet.</span><span class="sxs-lookup"><span data-stu-id="d8a62-168">If either location was different during any part of the year, you must override the value.</span></span> <span data-ttu-id="d8a62-169">Fältet **Postnummer** (rad 17) i rapport 1095-C fylls endast i om koden **Disponeringserbjudande** innehåller **1L** till **1Q** enligt följande:</span><span class="sxs-lookup"><span data-stu-id="d8a62-169">The **ZIP Code** field (line 17) of the 1095-C report is filled in only if the **Offer of coverage** code contains **1L** through **1Q**, as follows:</span></span>
>
> - <span data-ttu-id="d8a62-170">**1L, 1M eller 1N:** Det primära postnumret för bostaden</span><span class="sxs-lookup"><span data-stu-id="d8a62-170">**1L, 1M, or 1N:** The primary residence ZIP Code</span></span>
> - <span data-ttu-id="d8a62-171">**1O, 1P, 1Q:** Det primära postnumret för arbetsplatsen</span><span class="sxs-lookup"><span data-stu-id="d8a62-171">**1O, 1P, 1Q:** The primary work ZIP Code</span></span>

<span data-ttu-id="d8a62-172">Gör på följande sätt om du vill ange undantag för värden i en disponeringsgrupp för sjukförsäkring.</span><span class="sxs-lookup"><span data-stu-id="d8a62-172">To enter exceptions for any values of an Affordable Care coverage group, follow these steps.</span></span>

1. <span data-ttu-id="d8a62-173">I arbetsytan **personalhantering** välj **länkar** och välj sedan **arbetare**.</span><span class="sxs-lookup"><span data-stu-id="d8a62-173">In the **Personnel management** workspace, select **Links**, and then select **Workers**.</span></span>
2. <span data-ttu-id="d8a62-174">Välj medarbetaren i listan.</span><span class="sxs-lookup"><span data-stu-id="d8a62-174">Select the employee in the list.</span></span>
3. <span data-ttu-id="d8a62-175">På fliken **Anställning**, i avsnittet **Mer information**, väljer du **Disponering för sjukförsäkring**.</span><span class="sxs-lookup"><span data-stu-id="d8a62-175">On the **Employment** tab, in the **More information** section, select **Affordable Care coverage**.</span></span>

    ![Ändra alternativ för en medarbetare](./media/hr-benefits-management-aca-change-single-employee.png)

4. <span data-ttu-id="d8a62-177">Välj **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="d8a62-177">Select **Edit**.</span></span>
5. <span data-ttu-id="d8a62-178">Markera kryssrutan **Åsidosätt standard** och ändra sedan erforderliga värden efter behov för samtliga månader som måste ändras.</span><span class="sxs-lookup"><span data-stu-id="d8a62-178">For each month that requires changes, select the **Override default** check box, and then change the other values as required.</span></span>

    ![Åsidosätta standardvärden](./media/hr-benefits-management-aca-override-default.png)

6. <span data-ttu-id="d8a62-180">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="d8a62-180">Select **Save**.</span></span>

## <a name="report-health-care-coverage"></a><span data-ttu-id="d8a62-181">Rapportera sjukvårdstäckning</span><span class="sxs-lookup"><span data-stu-id="d8a62-181">Report health care coverage</span></span>

<span data-ttu-id="d8a62-182">Du måste spåra eventuell arbetsgivarsponsrad, självförförsäkrad sjukförsäkringstäckning för hel- och deltidsanställda.</span><span class="sxs-lookup"><span data-stu-id="d8a62-182">You must track any employer-sponsored, self-insured health care coverage for full-time and part-time employees.</span></span> <span data-ttu-id="d8a62-183">Inkludera varje medarbetare, tillsammans med sina beroende, i 1095-C-rapporten för de månader som de täcks.</span><span class="sxs-lookup"><span data-stu-id="d8a62-183">Include each employee, together with their dependents, on the 1095-C report for the months when they were covered.</span></span>

<span data-ttu-id="d8a62-184">Följ de här stegen när du vill ange om en förmånsplan måste rapporteras.</span><span class="sxs-lookup"><span data-stu-id="d8a62-184">To indicate whether a benefit plan must be reported, follow these steps.</span></span>

1. <span data-ttu-id="d8a62-185">I arbetsytan **Förmånshantering** väljer du **Förmånsplaner**.</span><span class="sxs-lookup"><span data-stu-id="d8a62-185">In the **Benefits management** workspace, select **Benefit plans**.</span></span>
2. <span data-ttu-id="d8a62-186">Välj den förmånsplan som ska rapporteras.</span><span class="sxs-lookup"><span data-stu-id="d8a62-186">Select the benefit plan to report.</span></span>
3. <span data-ttu-id="d8a62-187">Välj **Redigera**.</span><span class="sxs-lookup"><span data-stu-id="d8a62-187">Select **Edit**.</span></span>
4. <span data-ttu-id="d8a62-188">Ställ in alternativet **Rapporteras under sjukförsäkringar** som **Ja**.</span><span class="sxs-lookup"><span data-stu-id="d8a62-188">Set the **Reported under the Affordable Care Act** option to **Yes**.</span></span>

    ![Rapportering av hälsovårdstäckning](./media/hr-benefits-management-aca-report-coverage.png)

5. <span data-ttu-id="d8a62-190">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="d8a62-190">Select **Save**.</span></span>

<span data-ttu-id="d8a62-191">Om en medarbetare väljer sjukvårdstäckning för en beroende medarbetare, bestäms den beroende täckningsperiod av det datum då den beroende medarbetaren registrerades eller togs bort.</span><span class="sxs-lookup"><span data-stu-id="d8a62-191">If an employee chooses health care coverage for a dependent, the dependent's coverage period is determined by the date when the dependent was enrolled or removed.</span></span> <span data-ttu-id="d8a62-192">Disponeringsdatum för beroende beräknas automatiskt baserat på perioden när den beroende var berättigad och aktiv i en plan under registreringsåret.</span><span class="sxs-lookup"><span data-stu-id="d8a62-192">Coverage dates for dependents are automatically calculated based on the period when the dependent was eligible and active in a plan during the enrollment year.</span></span>

## <a name="generate-1095-b-and-1095-c-forms"></a><span data-ttu-id="d8a62-193">Generera 1095-B- och 1095-C-formulär</span><span class="sxs-lookup"><span data-stu-id="d8a62-193">Generate 1095-B and 1095-C forms</span></span>

<span data-ttu-id="d8a62-194">Du kan skapa ACA 1095-B- och 1095-C-formulär och sedan distribuera dessa till var och en av dina medarbetare.</span><span class="sxs-lookup"><span data-stu-id="d8a62-194">You can generate ACA 1095-B and 1095-C forms, and then distribute them to each of your employees.</span></span> <span data-ttu-id="d8a62-195">Du kan också generera formulär 1095-C och motsvarande 1094-C-överföringsfiler som skickas till Skatteverket.</span><span class="sxs-lookup"><span data-stu-id="d8a62-195">You can also electronically generate Form 1095-C and the corresponding 1094-C transmittal files to send to the Internal Revenue Service (IRS).</span></span>

1. <span data-ttu-id="d8a62-196">I arbetsytan **Förmånshantering** väljer du **formuläret ACA 1095-B** eller **formuläret ACA 1095-C**.</span><span class="sxs-lookup"><span data-stu-id="d8a62-196">In the **Benefits management** workspace, select **ACA 1095-B form** or **ACA 1095-C form**.</span></span>
2. <span data-ttu-id="d8a62-197">Ändra parametrarna efter behov och välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="d8a62-197">Change the parameters as required, and then select **OK**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d8a62-198">Om du skriver ut formulär 1095-C till mer än 500 anställda får du mer än en PDF-fil.</span><span class="sxs-lookup"><span data-stu-id="d8a62-198">If you're printing 1095-C forms for more than 500 employees, you will receive more than one PDF file.</span></span> <span data-ttu-id="d8a62-199">Vi rekommenderar att du ökar värdet för fältet **Maximal filstorlek i megabyte** på sidan **Parametrar för dokumenthantering** till **150**.</span><span class="sxs-lookup"><span data-stu-id="d8a62-199">We recommend that you increase the value of the **Maximum file size in megabytes** field on the **Document management parameters** page to **150**.</span></span> <span data-ttu-id="d8a62-200">(Om du snabbt vill öppna den sidan kan du använda sökfältet i navigeringsfältet.)</span><span class="sxs-lookup"><span data-stu-id="d8a62-200">(To quickly open that page, you can use the search field on the navigation bar.)</span></span>
    >
    > ![Ändra den maximala filstorleken](./media/hr-benefits-management-aca-maximum-file-size.png)

3. <span data-ttu-id="d8a62-202">Om du vill kontrollera rapporternas status och visa dem använder du sökfältet i navigeringsfältet för att öppna sidan **Jobb för elektronisk rapportering**.</span><span class="sxs-lookup"><span data-stu-id="d8a62-202">To check the status of your reports and view them, use the search field on the navigation bar to open the **Electronic reporting jobs** page.</span></span>

    ![Söka efter sidan Elektroniska rapporteringsjobb](./media/hr-benefits-management-aca-search-electronic-reporting-jobs.png)

4. <span data-ttu-id="d8a62-204">Markera rapporten som du vill visa och välj sedan **Visa filer**.</span><span class="sxs-lookup"><span data-stu-id="d8a62-204">Select the report to view, and then select **Show files**.</span></span>

    ![Visar filer](./media/hr-benefits-management-aca-show-files.png)

5. <span data-ttu-id="d8a62-206">Välj **Öppen**.</span><span class="sxs-lookup"><span data-stu-id="d8a62-206">Select **Open**.</span></span>

    ![Öppna en fil](./media/hr-benefits-management-aca-open-file.png)

6. <span data-ttu-id="d8a62-208">Öppna zip-filen i meddelandefältet som visas längst ned i webbläsaren och markera sedan rapporten.</span><span class="sxs-lookup"><span data-stu-id="d8a62-208">From the Notification bar that appears at the bottom of the browser window, open the zip file, and then select the report.</span></span> <span data-ttu-id="d8a62-209">Du kan visa eller skriva ut PDF-filen.</span><span class="sxs-lookup"><span data-stu-id="d8a62-209">You can view or print the PDF file.</span></span>

    ![Exempel 1095-C-formulär](./media/hr-benefits-management-aca-1095-c-form.png)

## <a name="view-aca-coverage-information"></a><span data-ttu-id="d8a62-211">Visa information om ACA-disponering</span><span class="sxs-lookup"><span data-stu-id="d8a62-211">View ACA coverage information</span></span>

<span data-ttu-id="d8a62-212">Sidan **Sjukförsäkringstäckning** visar följande information:</span><span class="sxs-lookup"><span data-stu-id="d8a62-212">The **Worker Affordable Care coverage** page shows the following information:</span></span>

- <span data-ttu-id="d8a62-213">Medarbetare som är tilldelade till respektive disponeringsgrupp</span><span class="sxs-lookup"><span data-stu-id="d8a62-213">Employees who are assigned to each coverage group</span></span>
- <span data-ttu-id="d8a62-214">Medarbetare som inte behöver tas med i en rapport</span><span class="sxs-lookup"><span data-stu-id="d8a62-214">Employees who don't have to be included on a report</span></span>
- <span data-ttu-id="d8a62-215">Ej tilldelade medarbetare</span><span class="sxs-lookup"><span data-stu-id="d8a62-215">Unassigned employees</span></span>

<span data-ttu-id="d8a62-216">Följ stegen nedan om du vill visa denna information.</span><span class="sxs-lookup"><span data-stu-id="d8a62-216">To view this information, follow these steps.</span></span>

1. <span data-ttu-id="d8a62-217">I arbetsytan **Förmånshantering** väljer du **Sjukförsäkringstäckning för medarbetare**.</span><span class="sxs-lookup"><span data-stu-id="d8a62-217">In the **Benefits management** workspace, select **Worker Affordable Care coverage**.</span></span>
2. <span data-ttu-id="d8a62-218">I fältet **Gruppnamn** väljer du en grupp.</span><span class="sxs-lookup"><span data-stu-id="d8a62-218">In the **Group name** field, select a group.</span></span>

    ![Visa ACA-täckning](./media/hr-benefits-management-aca-view-coverage.png)

<span data-ttu-id="d8a62-220">Om något av standardvärdena från täckningsgruppen för sjukförsäkring har åsidosatts, visas en asterisk bredvid värdet som har ändrats.</span><span class="sxs-lookup"><span data-stu-id="d8a62-220">If any default values from the Affordable Care coverage group have been overridden, an asterisk appears next to the value that was changed.</span></span> <span data-ttu-id="d8a62-221">Om värdena för alla 12 månader är desamma och inte har åsidosatts, visas värdet i kolumnen **Samtliga 12 månader**.</span><span class="sxs-lookup"><span data-stu-id="d8a62-221">If the values for all 12 months are the same and haven't been overridden, the value appears in the **All 12 months** column.</span></span>

<span data-ttu-id="d8a62-222">Du kan visa medarbetare som är markerade som icke-rapporteringsbara för sjukförsäkring och som inte kommer att kräva ett 1095-C-formulär.</span><span class="sxs-lookup"><span data-stu-id="d8a62-222">You can view employees who are marked as not ACA-reportable, and who won't require a Form 1095-C.</span></span> <span data-ttu-id="d8a62-223">I fältet **Filtrera efter** väljer du **Ej rapporteringsbar för sjukförsäkring**.</span><span class="sxs-lookup"><span data-stu-id="d8a62-223">In the **Filter by** field, select **Not ACA reportable**.</span></span>

<span data-ttu-id="d8a62-224">Du kan visa medarbetare som inte är tilldelade till någon grupp eller som är tilldelade till en utgången grupp.</span><span class="sxs-lookup"><span data-stu-id="d8a62-224">You can view employees who aren't assigned to a group, or who are assigned to an expired group.</span></span> <span data-ttu-id="d8a62-225">I fältet **Filtrera efter** väljer du **Ej tilldelad eller utgången grupp**.</span><span class="sxs-lookup"><span data-stu-id="d8a62-225">In the **Filter by** field, select **Unassigned or expired group**.</span></span>

### <a name="export-to-excel"></a><span data-ttu-id="d8a62-226">Exportera till Excel</span><span class="sxs-lookup"><span data-stu-id="d8a62-226">Export to Excel</span></span>

<span data-ttu-id="d8a62-227">Om du vill exportera någon av listorna till Microsoft Excel följer du dessa steg.</span><span class="sxs-lookup"><span data-stu-id="d8a62-227">To export any of the lists to Microsoft Excel, follow these steps.</span></span>

1. <span data-ttu-id="d8a62-228">Välj knappen **Öppna i Microsoft Office**.</span><span class="sxs-lookup"><span data-stu-id="d8a62-228">Select the **Open in Microsoft Office** button.</span></span>
2. <span data-ttu-id="d8a62-229">Välj **Tillfälligt register för HCM Personal för internt bruk**.</span><span class="sxs-lookup"><span data-stu-id="d8a62-229">Select **HCM Human Resources temporary table for internal use**.</span></span>
3. <span data-ttu-id="d8a62-230">Välj **Hämta**.</span><span class="sxs-lookup"><span data-stu-id="d8a62-230">Select **Download**.</span></span>

### <a name="view-aca-reportable-dependents"></a><span data-ttu-id="d8a62-231">Visa ACA-pliktiga beroenden</span><span class="sxs-lookup"><span data-stu-id="d8a62-231">View ACA-reportable dependents</span></span>

<span data-ttu-id="d8a62-232">Om du måste rapportera täckta personer eftersom du tillhandahåller självförsäkrad täckning, kan du visa beroende personer som omfattas av förmånsplaner och som har markerats som **pliktiga för sjukförsäkring**.</span><span class="sxs-lookup"><span data-stu-id="d8a62-232">If you must report covered individuals because you provide self-insured coverage, you can view dependents who are covered under benefit plans that are marked as **ACA reportable**.</span></span> <span data-ttu-id="d8a62-233">I åtgärdsfönstret väljer du **Visa täckning för beroende person**.</span><span class="sxs-lookup"><span data-stu-id="d8a62-233">On the Action Pane, select **View Dependent coverage**.</span></span>

![Visa beroendetäckning](./media/hr-benefits-management-aca-view-dependent-coverage.png)

<span data-ttu-id="d8a62-235">Taäckningsinformation för medarbetarens beroenden visas.</span><span class="sxs-lookup"><span data-stu-id="d8a62-235">Coverage information for the employee's dependents is shown.</span></span>

![Medförsäkringsskydd](./media/hr-benefits-management-aca-dependents.png)

> [!NOTE]
> <span data-ttu-id="d8a62-237">På sidan visas endast förmånsplaner som är markerade som **pliktiga för sjukförsäkring**.</span><span class="sxs-lookup"><span data-stu-id="d8a62-237">The page shows only benefits plans that are marked as **ACA reportable**.</span></span>
