---
title: "Visa och utvärdera resultaten för en enkät"
description: "Detta hjälpavsnitt förklarar hur visar och utvärderar resultaten för enkäter som svarande slutför."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: KMCollection, KMKnowledgeCollectorCollection, KMKnowledgeCollectorUserResults
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 17444
ms.assetid: 6570206a-b2c4-4025-8715-432fe6652b78
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 68dde5f6d67b48dad753e9f4c4123fb9e9e6b53a
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="view-and-evaluate-the-results-of-a-questionnaire"></a><span data-ttu-id="d8b7c-103">Visa och utvärdera resultaten för en enkät</span><span class="sxs-lookup"><span data-stu-id="d8b7c-103">View and evaluate the results of a questionnaire</span></span>

<span data-ttu-id="d8b7c-104">Detta hjälpavsnitt förklarar hur visar och utvärderar resultaten för enkäter som svarande slutför.</span><span class="sxs-lookup"><span data-stu-id="d8b7c-104">This topic explains how you can view and evaluate the results of questionnaires that respondents complete.</span></span> 

<span data-ttu-id="d8b7c-105">Efter att svaranden har slutfört en enkät går det att visa och utvärdera enkätresultaten på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="d8b7c-105">After respondents complete a questionnaire, you can view and evaluate the questionnaire results in the following ways:</span></span>

-   <span data-ttu-id="d8b7c-106">**Slutförda svarssessioner** – Visa information om de enkäter som svarande har slutfört och generera rapporter om du vill summera svar och eventuella poäng.</span><span class="sxs-lookup"><span data-stu-id="d8b7c-106">**Completed answer sessions** – View details about the questionnaires that respondents have completed, and generate reports to summarize answers and any points that were earned.</span></span>
-   <span data-ttu-id="d8b7c-107">**Resultatgrupper** – Visa information om resultatgrupper för statistik för enkäter.</span><span class="sxs-lookup"><span data-stu-id="d8b7c-107">**Result groups** – View result group details and statistics for questionnaires.</span></span> <span data-ttu-id="d8b7c-108">Resultatgruppsstatistiken kan skapas för antingen en enskild svarssession för en enkät eller för alla svarssessioner.</span><span class="sxs-lookup"><span data-stu-id="d8b7c-108">Result group statistics can be generated for either a single answer session  of a questionnaire or all answer sessions.</span></span>
-   <span data-ttu-id="d8b7c-109">**Enkätstatistik** – Ange villkor för att beräkna statistik för en viss grupp svarande.</span><span class="sxs-lookup"><span data-stu-id="d8b7c-109">**Questionnaire statistics** – Specify criteria to calculate statistics for a specific group of respondents.</span></span>

<span data-ttu-id="d8b7c-110">Du kan även generera olika rapporter om du vill visa resultat sorterade efter person, svarssession eller resultatgrupp.</span><span class="sxs-lookup"><span data-stu-id="d8b7c-110">You can also generate various reports to view results that are sorted by person, answer session, or result group.</span></span> <span data-ttu-id="d8b7c-111">Följande rapporter som är relaterad till ifyllda enkäter är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="d8b7c-111">The following reports that are related to completed questionnaires are available:</span></span>

-   <span data-ttu-id="d8b7c-112">Svar</span><span class="sxs-lookup"><span data-stu-id="d8b7c-112">Answers</span></span>
-   <span data-ttu-id="d8b7c-113">Svar per enkät</span><span class="sxs-lookup"><span data-stu-id="d8b7c-113">Answers per questionnaire</span></span>
-   <span data-ttu-id="d8b7c-114">Svar per person</span><span class="sxs-lookup"><span data-stu-id="d8b7c-114">Answers per person</span></span>
-   <span data-ttu-id="d8b7c-115">Återrapporteringsanalys</span><span class="sxs-lookup"><span data-stu-id="d8b7c-115">Feedback analysis</span></span>

## <a name="answer-session-results"></a><span data-ttu-id="d8b7c-116">Svarssessionsresultat</span><span class="sxs-lookup"><span data-stu-id="d8b7c-116">Answer session results</span></span>
<span data-ttu-id="d8b7c-117">Efter att svarande slutför en enkät kan du visa resultaten för slutförda svarssessioner.</span><span class="sxs-lookup"><span data-stu-id="d8b7c-117">After respondents complete a questionnaire, you can view the results of the completed answer sessions.</span></span> <span data-ttu-id="d8b7c-118">En svarssession är en användarens svar på en enkät.</span><span class="sxs-lookup"><span data-stu-id="d8b7c-118">An answer session is one user’s response to a questionnaire.</span></span> <span data-ttu-id="d8b7c-119">Du kan visa information om slutförda svarssessioner på sidan **Svar**.</span><span class="sxs-lookup"><span data-stu-id="d8b7c-119">You can view details about completed answer sessions on the **Answers** page.</span></span> <span data-ttu-id="d8b7c-120">Svarssessionerna som finns på sidan **Svar** filtreras på olika sätt, beroende på hur du öppnar sidan:</span><span class="sxs-lookup"><span data-stu-id="d8b7c-120">The answer sessions that are included on the **Answers** page are filtered in various ways, depending on how you open the page:</span></span>

-   <span data-ttu-id="d8b7c-121">Alla enkäter</span><span class="sxs-lookup"><span data-stu-id="d8b7c-121">All questionnaires</span></span>
-   <span data-ttu-id="d8b7c-122">En viss enkät</span><span class="sxs-lookup"><span data-stu-id="d8b7c-122">A specific questionnaire</span></span>
-   <span data-ttu-id="d8b7c-123">En viss person</span><span class="sxs-lookup"><span data-stu-id="d8b7c-123">A specific person</span></span>

<span data-ttu-id="d8b7c-124">På sidan **Svar** kan du visa information om svar, poäng, den svarandes svar i varje resultatgrupp och frågehierarkin som användes på den valda enkäten, om en frågehierarki användes.</span><span class="sxs-lookup"><span data-stu-id="d8b7c-124">From the **Answers** page, you can view details about answers, points that were earned, a respondent’s responses in each result group, and the question hierarchy that was used on the selected questionnaire, if a question hierarchy was used.</span></span> <span data-ttu-id="d8b7c-125">Du kan även generera och skriva ut följande rapporter:</span><span class="sxs-lookup"><span data-stu-id="d8b7c-125">You can also generate and print the following reports:</span></span>

-   <span data-ttu-id="d8b7c-126">**Resultatrapport** – Den här rapporten visar en grafisk representation av poäng per resultatgrupp för den valda svarssessionen.</span><span class="sxs-lookup"><span data-stu-id="d8b7c-126">**Results report** – This report shows a graphical representation of the points that were earned per result group for the selected answer session.</span></span>
-   <span data-ttu-id="d8b7c-127">**Svarsrapport** – Rapporten visar de svaren som svarande valde för varje fråga i enkäten.</span><span class="sxs-lookup"><span data-stu-id="d8b7c-127">**Answer report** – This report shows the answers that the respondent selected for each question on the questionnaire.</span></span>
-   <span data-ttu-id="d8b7c-128">**Felaktiga svar** – Den här rapporten visar information om felaktiga svar som den svarade markerade.</span><span class="sxs-lookup"><span data-stu-id="d8b7c-128">**Incorrect answers** – This report shows information that is related to the incorrect answers that the respondent selected.</span></span>

<span data-ttu-id="d8b7c-129">**Notering:** Rapporten **Resultat** är endast tillgänglig om du använder resultatgrupper i enkäten och om du har valt **Resultatsida** på sidan **Enkäter**.</span><span class="sxs-lookup"><span data-stu-id="d8b7c-129">**Note:** The **Results** report is available only if you use results groups on the questionnaire, and if you selected **Results page** on the **Questionnaires** page.</span></span> <span data-ttu-id="d8b7c-130">Rapporten **Svar** och rapporten **Felaktiga svar** är tillgängliga om du markerade **Svarsrapport** på sidan **Enkäter**.</span><span class="sxs-lookup"><span data-stu-id="d8b7c-130">The **Answer** report and the **Incorrect answers** report are available only if you selected **Answer report** on the **Questionnaires** page.</span></span>

## <a name="questionnaire-statistics"></a><span data-ttu-id="d8b7c-131">Enkätstatistik</span><span class="sxs-lookup"><span data-stu-id="d8b7c-131">Questionnaire statistics</span></span>
<span data-ttu-id="d8b7c-132">Du kan använda enkätstatistik om du vill analysera resultaten i en ifylld enkät baserat på beräkningar som du definierar.</span><span class="sxs-lookup"><span data-stu-id="d8b7c-132">You can use questionnaire statistics to analyze the results of a completed questionnaire, based on calculations that you define.</span></span> <span data-ttu-id="d8b7c-133">Om du vill definiera beräkningar måste du utföra följande uppgifter:</span><span class="sxs-lookup"><span data-stu-id="d8b7c-133">To define calculations, you must complete the following tasks:</span></span>

-   <span data-ttu-id="d8b7c-134">Välj kriterier för beräkningen och visa statistiken.</span><span class="sxs-lookup"><span data-stu-id="d8b7c-134">Select criteria to calculate and display the statistics.</span></span>
    -   <span data-ttu-id="d8b7c-135">Du kan visa statistik per enkät, frågor, frågerader eller resultatgrupper.</span><span class="sxs-lookup"><span data-stu-id="d8b7c-135">You can show statistics by questionnaire, questions, question rows, or results groups.</span></span>
    -   <span data-ttu-id="d8b7c-136">Välj den typ av diagram som ska användas när du visar resultat.</span><span class="sxs-lookup"><span data-stu-id="d8b7c-136">Select the type of chart that will be used when you view results.</span></span>
    -   <span data-ttu-id="d8b7c-137">Väljer persontyper i nätverket, såsom medarbetare, kontaktpersoner eller sökande vars svar du vill inkludera.</span><span class="sxs-lookup"><span data-stu-id="d8b7c-137">Select the types of people from the network, such as employees, contact persons, or applicants, to include answers for.</span></span> <span data-ttu-id="d8b7c-138">Du kan också ta med svar från enkäter som slutfördes anonymt.</span><span class="sxs-lookup"><span data-stu-id="d8b7c-138">You can also include answers from questionnaires that were completed anonymously.</span></span>
    -   <span data-ttu-id="d8b7c-139">Ställ in intervall som baseras på ålder eller tjänsteålder för att analysera resultaten.</span><span class="sxs-lookup"><span data-stu-id="d8b7c-139">Set up intervals that are based on age or seniority to analyze results.</span></span>
-   <span data-ttu-id="d8b7c-140">Välj eller bekräfta inställningar som begränsar ämnet för statistiken.</span><span class="sxs-lookup"><span data-stu-id="d8b7c-140">Select or verify settings that refine the subject of the statistics.</span></span> <span data-ttu-id="d8b7c-141">Genom att t ex välja ett postnummer kan du analysera resultat för alla svarande inom ett visst geografiskt område.</span><span class="sxs-lookup"><span data-stu-id="d8b7c-141">For example, by selecting a ZIP Code or postal code, you can analyze results for all respondents within a specific geographic area.</span></span>
-   <span data-ttu-id="d8b7c-142">Välj eller verifiera kriterier för att analysera resultaten efter svarande- eller enkätegenskaper.</span><span class="sxs-lookup"><span data-stu-id="d8b7c-142">Select or verify criteria to analyze results by respondent or questionnaire characteristics.</span></span> <span data-ttu-id="d8b7c-143">Om du väljer till exempel **Postnummer**, kan du analysera korrelationen mellan den svarandes plats och rätta svar.</span><span class="sxs-lookup"><span data-stu-id="d8b7c-143">For example, by selecting **ZIP/postal code**, you can analyze the correlation between a respondent’s location and correct answers.</span></span>

<span data-ttu-id="d8b7c-144">Inställningar som du definierar sparas så att du kan använda den för att regelbundet räkna om resultat.</span><span class="sxs-lookup"><span data-stu-id="d8b7c-144">The settings that you define are saved and can be used to periodically recalculate results.</span></span>

<a name="see-also"></a><span data-ttu-id="d8b7c-145">Se även</span><span class="sxs-lookup"><span data-stu-id="d8b7c-145">See also</span></span>
--------

[<span data-ttu-id="d8b7c-146">Utforma enkäter</span><span class="sxs-lookup"><span data-stu-id="d8b7c-146">Designing questionnaires</span></span>](design-questionnaires.md)

[<span data-ttu-id="d8b7c-147">Använda enkäter</span><span class="sxs-lookup"><span data-stu-id="d8b7c-147">Using questionnaires</span></span>](questionnaires.md)

[<span data-ttu-id="d8b7c-148">Distribuera och slutföra enkäter</span><span class="sxs-lookup"><span data-stu-id="d8b7c-148">Distributing and completing questionnaires</span></span>](distribute-questionnaires.md)

