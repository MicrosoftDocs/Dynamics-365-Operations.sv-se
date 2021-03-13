---
title: Generera ACA-rapporter (Affordable Care Act)
description: Sjukförsäkringsrapportering genererar formulär 1095-B och 1095-C till stöd för delen **Arbetsgivarmandat** i sjukförsäkringen.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
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
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 56ff879603a31956db877b45aec11b15371b69f5
ms.sourcegitcommit: 5c1b5ef40ce7359b3f1955535a250718d863badb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/09/2021
ms.locfileid: "5142166"
---
# <a name="generate-aca-reports"></a><span data-ttu-id="03184-103">Generera ACA-rapporter</span><span class="sxs-lookup"><span data-stu-id="03184-103">Generate ACA reports</span></span>

<span data-ttu-id="03184-104">Sjukförsäkringsrapportering genererar formulär 1095-B och 1095-C till stöd för delen **Arbetsgivarmandat** i sjukförsäkringen.</span><span class="sxs-lookup"><span data-stu-id="03184-104">Affordable Care Act (ACA) reporting generates forms 1095-B and 1095-C in support of the **Employer Mandate** portion of the Affordable Care Act.</span></span>

> [!NOTE]
> <span data-ttu-id="03184-105">Sjukförsäkringsrapportering är bara aktiverad för juridiska personer i USA.</span><span class="sxs-lookup"><span data-stu-id="03184-105">ACA reporting is only enabled for legal entities in the United States.</span></span>

## <a name="getting-started"></a><span data-ttu-id="03184-106">Komma igång</span><span class="sxs-lookup"><span data-stu-id="03184-106">Getting started</span></span>

<span data-ttu-id="03184-107">Om du vill spåra information för formulären 1095-B och 1095-C måste du först skapa en eller flera disponeringsgrupper för sjukförsäkring.</span><span class="sxs-lookup"><span data-stu-id="03184-107">To track information for forms 1095-B and 1095-C, you must first create one or more Affordable care coverage groups.</span></span> <span data-ttu-id="03184-108">Disponeringsgrupper för sjukförsäkring indikerar:</span><span class="sxs-lookup"><span data-stu-id="03184-108">Affordable Care coverage groups indicate:</span></span>

- <span data-ttu-id="03184-109">Täckningserbjudande för en medarbetare</span><span class="sxs-lookup"><span data-stu-id="03184-109">The offer of coverage for an employee</span></span>
- <span data-ttu-id="03184-110">Medarbetarens andel av den lägsta månadspremien, om kostnaden överstiger den federala fattigdomsgränsen</span><span class="sxs-lookup"><span data-stu-id="03184-110">The employee’s share of the lowest cost monthly premium, if the cost is above the federal poverty line</span></span>
- <span data-ttu-id="03184-111">Skyddsramar som används av arbetsgivaren, om tillämpligt</span><span class="sxs-lookup"><span data-stu-id="03184-111">Safe Harbor used by the employer, if applicable</span></span>

<span data-ttu-id="03184-112">Med täckningsgrupper för sjukförsäkring kan du hantera information för dessa fält utan att behöva ändra varje enskild medarbetarpost där villkoren är desamma.</span><span class="sxs-lookup"><span data-stu-id="03184-112">Affordable Care coverage groups allow you to manage the information for these fields without changing every employee record where the conditions are the same.</span></span> <span data-ttu-id="03184-113">Du kan enkelt tilldela sjukförsäkringsskyddsgrupper till en eller flera anställda med hjälp av funktionen för **masstilldelning** på sidan.</span><span class="sxs-lookup"><span data-stu-id="03184-113">You can easily assign Affordable Care coverage groups to one or more employees by using the **Mass assign** option on the page.</span></span>

## <a name="maintaining-multiple-versions-of-a-coverage-group"></a><span data-ttu-id="03184-114">Underhålla flera versioner av en försäkringsskyddsgrupp</span><span class="sxs-lookup"><span data-stu-id="03184-114">Maintaining multiple versions of a coverage group</span></span>

<span data-ttu-id="03184-115">Du kan underhålla flera versioner av valfri försäkringsskyddsgrupp.</span><span class="sxs-lookup"><span data-stu-id="03184-115">You can maintain multiple versions of any coverage group.</span></span> <span data-ttu-id="03184-116">Med den här funktionen kan du göra ändringar utan att behöva skapa en ny grupp och tilldela om medarbetare till den.</span><span class="sxs-lookup"><span data-stu-id="03184-116">This functionality allows you to make changes without having to create a new group and reassign employees to it.</span></span> 

<span data-ttu-id="03184-117">När du har skapat täckningsgrupper för sjukförsäkring kan du masstilldela grupperna till medarbetare med alternativet **Masstilldelning**.</span><span class="sxs-lookup"><span data-stu-id="03184-117">After you’ve created ACA coverage groups, you can mass assign the groups to employees with the **Mass assignment** option.</span></span> <span data-ttu-id="03184-118">Du kan också enskilt ange om du vill spåra och rapportera sjukförsäkringsinformation, samt tilldela en medarbetare till en disponeringsgrupp för sjukförsäkring.</span><span class="sxs-lookup"><span data-stu-id="03184-118">You can also individually indicate whether to track and report ACA information, and assign an employee to an Affordable Care coverage group.</span></span>

<span data-ttu-id="03184-119">Du behöver inte spåra viss täckningsinformation för sjukförsäkring, till exempel för deltidsanställda.</span><span class="sxs-lookup"><span data-stu-id="03184-119">You don't need to track some ACA coverage information, such as for part-time employees.</span></span> <span data-ttu-id="03184-120">Ange i det här fallet fältet **Rapportomfattning** som **Nej**.</span><span class="sxs-lookup"><span data-stu-id="03184-120">In this case, set the **Report coverage** field to **No**.</span></span> <span data-ttu-id="03184-121">Även om du måste tilldela varje enskild medarbetare spårbar sjukförsäkringsinformation till en täckningsgrupp för sjukförsäkring, kan du ändå ändra följande alternativ för månader med olika värden:</span><span class="sxs-lookup"><span data-stu-id="03184-121">Although you must assign each employee with trackable ACA information to an Affordable Care coverage group, you can still change the following options for months with different values:</span></span>

- <span data-ttu-id="03184-122">**Erbjudande om försäkringsskydd**</span><span class="sxs-lookup"><span data-stu-id="03184-122">**Offer of coverage**</span></span>
- <span data-ttu-id="03184-123">**Medarbetarens del av kostnaden**</span><span class="sxs-lookup"><span data-stu-id="03184-123">**Employee share of cost**</span></span>
- <span data-ttu-id="03184-124">**Safe Harbor**</span><span class="sxs-lookup"><span data-stu-id="03184-124">**Safe Harbor**</span></span>

<span data-ttu-id="03184-125">Om du vill ange undantag för värden för täckningsgrupper för sjukförsäkring väljer du länken **Sjukförsäkringstäckning** på sidan **Medarbetardetaljer** under avsnittet **Ytterligare information** på **Anställningsfliken**.</span><span class="sxs-lookup"><span data-stu-id="03184-125">To enter exceptions for Affordable Care coverage group values, select the **Affordable Care Coverage** link on the **Worker detail** page under the **Additional information** section on the **Employment tab**.</span></span>

## <a name="reporting-health-care-coverage"></a><span data-ttu-id="03184-126">Rapportering av hälsovårdstäckning</span><span class="sxs-lookup"><span data-stu-id="03184-126">Reporting health care coverage</span></span>

<span data-ttu-id="03184-127">Förutom att spåra vad händer om någon sjukförsäkringstäckning erbjudits till heltidsanställda, måste ytterligare information redovisas på 1095-C om arbetsgivaren erbjuder arbetsgivarsponsrad, självförsäkrad hälsotäckning som medarbetaren är anmäld för (oavsett om deras anställningsstatus är heltid eller deltid).</span><span class="sxs-lookup"><span data-stu-id="03184-127">In addition to tracking health insurance coverage offered to full-time employees, if the employer offers employer-sponsored self-insured health coverage for which the employee is enrolled (regardless of whether their employment status is full-time or part-time), additional information needs to be reported on the 1095-C.</span></span> <span data-ttu-id="03184-128">Varje medarbetare (inklusive beroende) som omfattas av arbetsgivarsponsrade förmånsplaner måste inkluderas i rapporten för de månader som de omfattades.</span><span class="sxs-lookup"><span data-stu-id="03184-128">Each employee (including dependents) covered by the employer-sponsored benefit plans needs to be included on the report for the months they were covered.</span></span> 

<span data-ttu-id="03184-129">Du kan ange huruvida varje förmånsplan måste rapporteras genom att välja kryssrutan **Rapportera till sjukförsäkring**.</span><span class="sxs-lookup"><span data-stu-id="03184-129">You can indicate whether or not each benefit plan must be reported by selecting the **ACA reportable** check box.</span></span>

<span data-ttu-id="03184-130">Om medarbetare har valt att låta något beroende omfattas av en förmån anger du dessutom de datum då beroendet omfattades för samtliga anställda på sidan **Underhåll förmåner**.</span><span class="sxs-lookup"><span data-stu-id="03184-130">In addition, if employees have chosen to have any of their dependents covered under a benefit, you can indicate the dates the dependent was covered for each employee on the **Maintain benefits** page.</span></span> <span data-ttu-id="03184-131">Om du vill indikera att beroendet täcks av förmånen väljer du knappen **Redigera** i åtgärdsfönstret på snabbfliken **Beroenden**.</span><span class="sxs-lookup"><span data-stu-id="03184-131">To indicate that the dependent is covered under the benefit, select the **Edit** button in the action pane of the **Dependents** fast tab.</span></span>

<span data-ttu-id="03184-132">På sidan **Datumhanterare för beroendetäckning** anger du de datum då beroenden omfattades av förmånen.</span><span class="sxs-lookup"><span data-stu-id="03184-132">On the **Dependent coverage date manager** page, you can indicate the dates the dependent was covered by the benefit.</span></span> <span data-ttu-id="03184-133">Om du anger datum på den här sidan kommer kryssrutan **Täckning** automatiskt att markeras på sidan **Bibehåll förmåner**.</span><span class="sxs-lookup"><span data-stu-id="03184-133">Entering dates on this page will automatically select the **Covered** checkbox on the **Maintain benefits** page.</span></span>

## <a name="generate-1095-b-and-1095-c-forms"></a><span data-ttu-id="03184-134">Generera 1095-B- och 1095-C-formulär</span><span class="sxs-lookup"><span data-stu-id="03184-134">Generate 1095-B and 1095-C forms</span></span>

<span data-ttu-id="03184-135">Du kan också skapa 1095-B- och 1095-C-formulär inifrån själva produkten och distribuera dessa till var och en av dina medarbetare.</span><span class="sxs-lookup"><span data-stu-id="03184-135">You can also generate 1095-B and 1095-C forms from within the product, and distribute them to each of your employees.</span></span> <span data-ttu-id="03184-136">Systemet kan också elektroniskt generera 1095-C-formulär och överföringsfilerna för 1094-C IRS.</span><span class="sxs-lookup"><span data-stu-id="03184-136">The system can also electronically generate 1095-C forms and the 1094-C IRS transmittal files.</span></span>  

<span data-ttu-id="03184-137">När du genererar formuläret 1095-C anger du lämpligt taxeringsår och om personnummer ska döljas.</span><span class="sxs-lookup"><span data-stu-id="03184-137">When generating the 1095-C form, enter the appropriate tax year and indicate if social security numbers should be masked.</span></span> <span data-ttu-id="03184-138">Om du skriver ut formulär 1095-C till mer än 500 anställda får du mer än en PDF-fil.</span><span class="sxs-lookup"><span data-stu-id="03184-138">If you're printing 1095-C forms for more than 500 employees, you'll receive more than one PDF file.</span></span> <span data-ttu-id="03184-139">Det’s rekommenderas att du ökar **Största filstorlek** i fönstret **Dokumenthanteringsparametrar** till 150 MB.</span><span class="sxs-lookup"><span data-stu-id="03184-139">It’s recommended that you increase the **Maximum file size** in the **Document management parameters** window to 150 MB.</span></span>

## <a name="viewing-information"></a><span data-ttu-id="03184-140">Visa information</span><span class="sxs-lookup"><span data-stu-id="03184-140">Viewing information</span></span>

<span data-ttu-id="03184-141">Du kan använda sidan **Affordable Care-täckning för arbetstagare** om du vill se vilka medarbetare som har tilldelats respektive försäkringsskyddsgrupp, vilka medarbetare som inte behöver ingå i en rapport, samt vilka medarbetare som inte har tilldelats.</span><span class="sxs-lookup"><span data-stu-id="03184-141">You can use the **Worker Affordable Care coverage** page to see which employees have been assigned to each coverage group, which employees don’t need to be included on a report, and which employees are unassigned.</span></span>

<span data-ttu-id="03184-142">Om något av standardvärdena från täckningsgruppen för sjukförsäkring har åsidosatts, visas en asterisk bredvid värdet som har ändrats.</span><span class="sxs-lookup"><span data-stu-id="03184-142">If any of the default values from the Affordable Care coverage group have been overridden, an asterisk will appear next to the value that was changed.</span></span> <span data-ttu-id="03184-143">Om värdena för alla 12 månader är desamma och inte har åsidosatts, anges värdet i kolumnen **Samtliga 12 månader**.</span><span class="sxs-lookup"><span data-stu-id="03184-143">If the values for all 12 months are the same and haven’t been overridden, the value will print in the **All 12 months** column.</span></span>

<span data-ttu-id="03184-144">Du kan också använda förfrågningsfönstret för att förstå vilka medarbetare som har flaggats som icke-pliktiga för sjukförsäkring.</span><span class="sxs-lookup"><span data-stu-id="03184-144">You can also use the inquiry window to understand which employees have been flagged as not ACA reportable.</span></span> <span data-ttu-id="03184-145">Du behöver inte spåra huruvida täckning erbjudits dem, och du behöver heller inte utfärda 1095-C till dem vid årets slut.</span><span class="sxs-lookup"><span data-stu-id="03184-145">You don’t need to track whether coverage was offered to them and won't need to issue a 1095-C to them at the end of the year.</span></span> <span data-ttu-id="03184-146">Välj **Icke-pliktig för sjukförsäkring** i fältet **Filtrera efter** om du vill generera en lista över alla anställda som inte får ett 1095-C.</span><span class="sxs-lookup"><span data-stu-id="03184-146">Select **Not ACA reportable** in the **Filter by** field to generate a list of all employees who won't receive a 1095-C.</span></span>

<span data-ttu-id="03184-147">Du kan dessutom visa de anställda som inte har tilldelats (fältet **Rapporttäckning för sjukförsäkring** är tomt) eller de som har tilldelats till en täckningsgrupp för sjukförsäkring som har löpt ut för året som valts i fältet **År**.</span><span class="sxs-lookup"><span data-stu-id="03184-147">In addition, you can view any employees who are unassigned (the **ACA Report coverage** field is empty) or who have been assigned to an Affordable Care coverage group that is expired for the year selected in the **Year** field.</span></span>

<span data-ttu-id="03184-148">Du kan exportera listor över medarbetare som har skapats med något av filtreringsalternativen till Excel.</span><span class="sxs-lookup"><span data-stu-id="03184-148">You can export lists of employees that were generated using any of the filtering options to Excel.</span></span>

<span data-ttu-id="03184-149">Om du behöver rapportera täckta personer eftersom du tillhandahåller självförsäkrad täckning, kan du visa alla beroende personer som omfattas av förmånsplaner och som har markerats som **pliktiga för sjukförsäkring**.</span><span class="sxs-lookup"><span data-stu-id="03184-149">If you need to report covered individuals because you provide self-insured coverage, you can view any dependents covered under benefit plans marked as **ACA reportable**.</span></span> <span data-ttu-id="03184-150">Välj **Visa beroendetäckning** i åtgärdsfältet.</span><span class="sxs-lookup"><span data-stu-id="03184-150">Select **View Dependent coverage** on the action pane.</span></span>

> [!NOTE]
> <span data-ttu-id="03184-151">Endast förmånsplaner markerade som **sjukförsäkringspliktiga** visas i förfrågningsfönstret.</span><span class="sxs-lookup"><span data-stu-id="03184-151">Only benefit plans marked as **ACA reportable** display in the inquiry window.</span></span>
